# CInkRecoContext::get_EnabledUnicodeRanges(tagVARIANT *)

- ea: `0x1800a7410`
- end: `0x1800a7597`
- name: `?get_EnabledUnicodeRanges@CInkRecoContext@@UEAAJPEAUtagVARIANT@@@Z`
- size: `391`
- prototype: `int(CInkRecoContext *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x180083ec0`
- `0x1800a7410`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7465`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7456`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a7456`
- `OLEAUT32!__imp_VariantInit` at `0x1800a7440`
- `OLEAUT32!__imp_VariantInit` at `0x1800a74e3`
- `OLEAUT32!__imp_VariantInit` at `0x1800a7440`
- `OLEAUT32!__imp_VariantInit` at `0x1800a74e3`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7536`
- `OLEAUT32!__imp_VariantClear` at `0x1800a7536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a74c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a74c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7563`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7520`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a7520`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CInkRecoContext::get_EnabledUnicodeRanges(CInkRecoContext *this, struct tagVARIANT *a2)
{
  signed int EnabledUnicodeRanges; // ebx
  __int64 v5; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v8; // rax
  void *v9; // rsi
  int (*v10)(unsigned int, unsigned __int8 *, struct tagVARIANT *__struct_ptr, struct tagPREDICTION_RESULT_PACKET *); // rdx
  _BYTE v12[56]; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+8h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v12, (struct _RTL_CRITICAL_SECTION *)((char *)this + 152));
  if ( a2 )
  {
    EnabledUnicodeRanges = 0;
    VariantInit(a2);
    if ( !*((_QWORD *)this + 12) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 12) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        EnabledUnicodeRanges = LastError;
        if ( LastError > 0 )
          EnabledUnicodeRanges = (unsigned __int16)LastError | 0x80070000;
        if ( EnabledUnicodeRanges < 0 )
          goto LABEL_21;
      }
    }
    if ( *((_QWORD *)this + 4)
      || (LOBYTE(v5) = 1,
          EnabledUnicodeRanges = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 10) + 72LL))(
                                   (char *)this - 80,
                                   v5),
          EnabledUnicodeRanges < 0) )
    {
      if ( EnabledUnicodeRanges < 0 )
        goto LABEL_21;
    }
    else if ( !*((_QWORD *)this + 4) )
    {
      EnabledUnicodeRanges = -2147418113;
      goto LABEL_21;
    }
    v8 = CoTaskMemAlloc(8u);
    v9 = v8;
    if ( v8 )
    {
      *v8 = (char *)this + 96;
      VariantInit((VARIANTARG *)((char *)this + 128));
      EnabledUnicodeRanges = BackgroundGetEnabledUnicodeRanges(*(HRECOCONTEXT *)(*((_QWORD *)this + 4) + 16LL), v10, v9);
      if ( EnabledUnicodeRanges < 0 )
      {
        CoTaskMemFree(v9);
        goto LABEL_21;
      }
      dwindex = 0;
      if ( CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 12, &dwindex) >= 0 )
      {
        EnabledUnicodeRanges = *((_DWORD *)this + 31);
        if ( EnabledUnicodeRanges >= 0 )
        {
          *(_OWORD *)&a2->vt = *((_OWORD *)this + 8);
          a2->pRecInfo = (IRecordInfo *)*((_QWORD *)this + 18);
          goto LABEL_21;
        }
      }
      else
      {
        EnabledUnicodeRanges = -2147418113;
      }
      VariantClear((VARIANTARG *)((char *)this + 128));
    }
    else
    {
      EnabledUnicodeRanges = -2147024882;
    }
LABEL_21:
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v12);
    return (unsigned int)EnabledUnicodeRanges;
  }
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v12);
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800a7410  push    rbx
0x1800a7412  push    rsi
0x1800a7413  push    rdi
0x1800a7414  push    r14
0x1800a7416  sub     rsp, 48h
0x1800a741a  mov     r14, rdx
0x1800a741d  mov     rdi, rcx
0x1800a7420  lea     rdx, [rcx+98h]; struct _RTL_CRITICAL_SECTION *
0x1800a7427  lea     rcx, [rsp+68h+var_38]; this
0x1800a742c  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a7431  nop
0x1800a7432  test    r14, r14
0x1800a7435  jz      loc_1800A757E
0x1800a743b  xor     ebx, ebx
0x1800a743d  mov     rcx, r14; pvarg
0x1800a7440  call    cs:__imp_VariantInit
0x1800a7446  cmp     [rdi+60h], rbx
0x1800a744a  jnz     short loc_1800A7482
0x1800a744c  xor     r9d, r9d; lpName
0x1800a744f  xor     r8d, r8d; bInitialState
0x1800a7452  xor     edx, edx; bManualReset
0x1800a7454  xor     ecx, ecx; lpEventAttributes
0x1800a7456  call    cs:__imp_CreateEventW
0x1800a745c  mov     [rdi+60h], rax
0x1800a7460  test    rax, rax
0x1800a7463  jnz     short loc_1800A7482
0x1800a7465  call    cs:__imp_GetLastError
0x1800a746b  mov     ebx, eax
0x1800a746d  test    eax, eax
0x1800a746f  jle     short loc_1800A747A
0x1800a7471  movzx   ebx, ax
0x1800a7474  or      ebx, 80070000h
0x1800a747a  test    ebx, ebx
0x1800a747c  js      loc_1800A756A
0x1800a7482  cmp     qword ptr [rdi+20h], 0
0x1800a7487  jnz     short loc_1800A74B3
0x1800a7489  mov     rax, [rdi-50h]
0x1800a748d  mov     dl, 1
0x1800a748f  lea     rcx, [rdi-50h]
0x1800a7493  mov     rax, [rax+48h]
0x1800a7497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a749c  mov     ebx, eax
0x1800a749e  test    eax, eax
0x1800a74a0  js      short loc_1800A74B3
0x1800a74a2  cmp     qword ptr [rdi+20h], 0
0x1800a74a7  jnz     short loc_1800A74BB
0x1800a74a9  mov     ebx, 8000FFFFh
0x1800a74ae  jmp     loc_1800A756A
0x1800a74b3  test    ebx, ebx
0x1800a74b5  js      loc_1800A756A
0x1800a74bb  mov     ecx, 8; cb
0x1800a74c0  call    cs:__imp_CoTaskMemAlloc
0x1800a74c6  mov     rsi, rax
0x1800a74c9  test    rax, rax
0x1800a74cc  jnz     short loc_1800A74D8
0x1800a74ce  mov     ebx, 8007000Eh
0x1800a74d3  jmp     loc_1800A756A
0x1800a74d8  lea     rcx, [rdi+60h]
0x1800a74dc  mov     [rax], rcx
0x1800a74df  add     rcx, 20h ; ' '; pvarg
0x1800a74e3  call    cs:__imp_VariantInit
0x1800a74e9  mov     rcx, [rdi+20h]
0x1800a74ed  mov     r8, rsi; void *
0x1800a74f0  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a74f4  call    ?BackgroundGetEnabledUnicodeRanges@@YAJPEAUHRECOCONTEXT__@@P6AJKPEAEUtagVARIANT@@PEAUtagPREDICTION_RESULT_PACKET@@@ZPEAX@Z; BackgroundGetEnabledUnicodeRanges(HRECOCONTEXT__ *,long (*)(ulong,uchar *,tagVARIANT,tagPREDICTION_RESULT_PACKET *),void *)
0x1800a74f9  mov     ebx, eax
0x1800a74fb  test    eax, eax
0x1800a74fd  js      short loc_1800A7560
0x1800a74ff  mov     [rsp+68h+dwindex], 0
0x1800a7507  lea     rax, [rsp+68h+dwindex]
0x1800a750c  mov     [rsp+68h+lpdwindex], rax; lpdwindex
0x1800a7511  lea     r9, [rdi+60h]; pHandles
0x1800a7515  mov     edx, 493E0h; dwTimeout
0x1800a751a  xor     ecx, ecx; dwFlags
0x1800a751c  lea     r8d, [rcx+1]; cHandles
0x1800a7520  call    cs:__imp_CoWaitForMultipleHandles
0x1800a7526  test    eax, eax
0x1800a7528  jns     short loc_1800A753E
0x1800a752a  mov     ebx, 8000FFFFh
0x1800a752f  lea     rcx, [rdi+80h]; pvarg
0x1800a7536  call    cs:__imp_VariantClear
0x1800a753c  jmp     short loc_1800A756A
0x1800a753e  mov     ebx, [rdi+7Ch]
0x1800a7541  test    ebx, ebx
0x1800a7543  js      short loc_1800A752F
0x1800a7545  movups  xmm0, xmmword ptr [rdi+80h]
0x1800a754c  movups  xmmword ptr [r14], xmm0
0x1800a7550  movsd   xmm1, qword ptr [rdi+90h]
0x1800a7558  movsd   qword ptr [r14+10h], xmm1
0x1800a755e  jmp     short loc_1800A756A
0x1800a7560  mov     rcx, rsi; pv
0x1800a7563  call    cs:__imp_CoTaskMemFree
0x1800a7569  nop
0x1800a756a  jmp     short loc_1800A7570
0x1800a756c  mov     ebx, [rsp+68h+dwindex]
0x1800a7570  lea     rcx, [rsp+68h+var_38]; this
0x1800a7575  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a757a  mov     eax, ebx
0x1800a757c  jmp     short loc_1800A758D
0x1800a757e  lea     rcx, [rsp+68h+var_38]; this
0x1800a7583  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a7588  mov     eax, 80004003h
0x1800a758d  add     rsp, 48h
0x1800a7591  pop     r14
0x1800a7593  pop     rdi
0x1800a7594  pop     rsi
0x1800a7595  pop     rbx
0x1800a7596  retn
```
