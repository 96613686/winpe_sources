# CInkRecoContext::GetPredictionText(ushort const *)

- ea: `0x1800a55e0`
- end: `0x1800a577e`
- name: `?GetPredictionText@CInkRecoContext@@UEAAJPEBG@Z`
- size: `414`
- prototype: `int(CInkRecoContext *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180083f58`
- `0x1800a55e0`
- `0x1800c4560`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5691`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a5683`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a5683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a56be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a56be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5752`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5752`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a573d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a573d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkRecoContext::GetPredictionText(CInkRecoContext *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  unsigned int v6; // esi
  signed int TextPrediction; // ebx
  _QWORD *v8; // r15
  HANDLE EventW; // rax
  signed int LastError; // eax
  int (*v11)(unsigned int, unsigned __int8 *, struct tagVARIANT *__struct_ptr, struct tagPREDICTION_RESULT_PACKET *); // r9
  _QWORD *v12; // r14
  _BYTE v14[72]; // [rsp+30h] [rbp-48h] BYREF
  DWORD dwindex; // [rsp+80h] [rbp+8h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v14, (struct _RTL_CRITICAL_SECTION *)((char *)this + 168));
  v5 = (_QWORD *)((char *)this - 64);
  if ( !*((_QWORD *)this + 30) )
  {
    v6 = -2147418113;
    goto LABEL_22;
  }
  try
  {
    if ( *((_QWORD *)this + 6) )
    {
      (*(void (__fastcall **)(char *))(v5[2] + 200LL))((char *)this - 48);
      TextPrediction = 0;
    }
    else
    {
      LOBYTE(v4) = 1;
      TextPrediction = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v5 + 72LL))(v5, v4);
      if ( TextPrediction < 0 )
        goto LABEL_26;
      if ( !*((_QWORD *)this + 6) )
        TextPrediction = -2147418113;
      if ( TextPrediction < 0 )
        goto LABEL_26;
    }
    v8 = (_QWORD *)((char *)this + 112);
    if ( *((_QWORD *)this + 14) )
      goto LABEL_15;
    EventW = CreateEventW(0, 0, 0, 0);
    *v8 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      TextPrediction = LastError;
      if ( LastError > 0 )
        TextPrediction = (unsigned __int16)LastError | 0x80070000;
    }
    if ( TextPrediction >= 0 )
    {
LABEL_15:
      CInkRecognizer::InternalUpdateUserDict(*((CInkRecognizer **)this + 7), 0);
      v12 = CoTaskMemAlloc(8u);
      if ( v12 )
      {
        *((_WORD *)this + 72) = 0x4000;
        *((_QWORD *)this + 19) = *((_QWORD *)this + 30);
        *v12 = v8;
        TextPrediction = BackgroundGetTextPrediction(
                           *(HRECOCONTEXT *)(*((_QWORD *)this + 6) + 16LL),
                           a2,
                           (struct tagPREDICTION_MODE *)(*((_QWORD *)this + 30) + 4LL),
                           v11,
                           v12);
        if ( TextPrediction >= 0 )
        {
          dwindex = 0;
          TextPrediction = -2147418113;
          if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 14, &dwindex) >= 0 )
            TextPrediction = *((_DWORD *)this + 35);
        }
        CoTaskMemFree(v12);
      }
      else
      {
        TextPrediction = -2147024882;
      }
    }
  }
  catch ( ... )
  {
    dwindex = ReportWispException();
    TextPrediction = dwindex;
  }
LABEL_26:
  v6 = TextPrediction;
LABEL_22:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v14);
  return v6;
}

```

## disassembly

```asm
0x1800a55e0  push    rbx
0x1800a55e2  push    rsi
0x1800a55e3  push    rdi
0x1800a55e4  push    r12
0x1800a55e6  push    r14
0x1800a55e8  push    r15
0x1800a55ea  sub     rsp, 48h
0x1800a55ee  mov     r12, rdx
0x1800a55f1  mov     rdi, rcx
0x1800a55f4  lea     rdx, [rcx+0A8h]; struct _RTL_CRITICAL_SECTION *
0x1800a55fb  lea     rcx, [rsp+78h+var_48]; this
0x1800a5600  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a5605  nop
0x1800a5606  lea     rcx, [rdi-40h]
0x1800a560a  cmp     qword ptr [rcx+130h], 0
0x1800a5612  jnz     short loc_1800A561E
0x1800a5614  mov     esi, 8000FFFFh
0x1800a5619  jmp     loc_1800A5764
0x1800a561e  cmp     qword ptr [rdi+30h], 0
0x1800a5623  jnz     short loc_1800A5654
0x1800a5625  mov     rax, [rcx]
0x1800a5628  mov     dl, 1
0x1800a562a  mov     rax, [rax+48h]
0x1800a562e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5633  mov     ebx, eax
0x1800a5635  mov     esi, 8000FFFFh
0x1800a563a  test    eax, eax
0x1800a563c  js      loc_1800A5759
0x1800a5642  cmp     qword ptr [rdi+30h], 0
0x1800a5647  cmovz   ebx, esi
0x1800a564a  test    ebx, ebx
0x1800a564c  js      loc_1800A5759
0x1800a5652  jmp     short loc_1800A566F
0x1800a5654  mov     rax, [rcx+10h]
0x1800a5658  lea     rcx, [rdi-30h]
0x1800a565c  mov     rax, [rax+0C8h]
0x1800a5663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5668  xor     ebx, ebx
0x1800a566a  mov     esi, 8000FFFFh
0x1800a566f  lea     r15, [rdi+70h]
0x1800a5673  cmp     qword ptr [r15], 0
0x1800a5677  jnz     short loc_1800A56AE
0x1800a5679  xor     r9d, r9d; lpName
0x1800a567c  xor     r8d, r8d; bInitialState
0x1800a567f  xor     edx, edx; bManualReset
0x1800a5681  xor     ecx, ecx; lpEventAttributes
0x1800a5683  call    cs:__imp_CreateEventW
0x1800a5689  mov     [r15], rax
0x1800a568c  test    rax, rax
0x1800a568f  jnz     short loc_1800A56A6
0x1800a5691  call    cs:__imp_GetLastError
0x1800a5697  mov     ebx, eax
0x1800a5699  test    eax, eax
0x1800a569b  jle     short loc_1800A56A6
0x1800a569d  movzx   ebx, ax
0x1800a56a0  or      ebx, 80070000h
0x1800a56a6  test    ebx, ebx
0x1800a56a8  js      loc_1800A5759
0x1800a56ae  xor     edx, edx; bool
0x1800a56b0  mov     rcx, [rdi+38h]; this
0x1800a56b4  call    ?InternalUpdateUserDict@CInkRecognizer@@IEAAJ_N@Z; CInkRecognizer::InternalUpdateUserDict(bool)
0x1800a56b9  mov     ecx, 8; cb
0x1800a56be  call    cs:__imp_CoTaskMemAlloc
0x1800a56c4  mov     r14, rax
0x1800a56c7  test    rax, rax
0x1800a56ca  jnz     short loc_1800A56D6
0x1800a56cc  mov     ebx, 8007000Eh
0x1800a56d1  jmp     loc_1800A5759
0x1800a56d6  mov     word ptr [rdi+90h], 4000h
0x1800a56df  mov     rax, [rdi+0F0h]
0x1800a56e6  mov     [rdi+98h], rax
0x1800a56ed  mov     [r14], r15
0x1800a56f0  mov     r8, [rdi+0F0h]
0x1800a56f7  add     r8, 4; struct tagPREDICTION_MODE *
0x1800a56fb  mov     rcx, [rdi+30h]
0x1800a56ff  mov     [rsp+78h+lpdwindex], r14; void *
0x1800a5704  mov     rdx, r12; unsigned __int16 *
0x1800a5707  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a570b  call    ?BackgroundGetTextPrediction@@YAJPEAUHRECOCONTEXT__@@PEBGPEAUtagPREDICTION_MODE@@P6AJKPEAEUtagVARIANT@@PEAUtagPREDICTION_RESULT_PACKET@@@ZPEAX@Z; BackgroundGetTextPrediction(HRECOCONTEXT__ *,ushort const *,tagPREDICTION_MODE *,long (*)(ulong,uchar *,tagVARIANT,tagPREDICTION_RESULT_PACKET *),void *)
0x1800a5710  mov     ebx, eax
0x1800a5712  test    eax, eax
0x1800a5714  js      short loc_1800A574F
0x1800a5716  mov     [rsp+78h+dwindex], 0
0x1800a5721  lea     r9, [rdi+70h]; pHandles
0x1800a5725  lea     rax, [rsp+78h+dwindex]
0x1800a572d  mov     [rsp+78h+lpdwindex], rax; lpdwindex
0x1800a5732  mov     edx, 493E0h; dwTimeout
0x1800a5737  xor     ecx, ecx; dwFlags
0x1800a5739  lea     r8d, [rcx+1]; cHandles
0x1800a573d  call    cs:__imp_CoWaitForMultipleHandles
0x1800a5743  test    eax, eax
0x1800a5745  mov     ebx, esi
0x1800a5747  js      short loc_1800A574F
0x1800a5749  mov     ebx, [rdi+8Ch]
0x1800a574f  mov     rcx, r14; pv
0x1800a5752  call    cs:__imp_CoTaskMemFree
0x1800a5758  nop
0x1800a5759  jmp     short loc_1800A5762
0x1800a575b  mov     ebx, [rsp+78h+dwindex]
0x1800a5762  mov     esi, ebx
0x1800a5764  lea     rcx, [rsp+78h+var_48]; this
0x1800a5769  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a576e  mov     eax, esi
0x1800a5770  add     rsp, 48h
0x1800a5774  pop     r15
0x1800a5776  pop     r14
0x1800a5778  pop     r12
0x1800a577a  pop     rdi
0x1800a577b  pop     rsi
0x1800a577c  pop     rbx
0x1800a577d  retn
```
