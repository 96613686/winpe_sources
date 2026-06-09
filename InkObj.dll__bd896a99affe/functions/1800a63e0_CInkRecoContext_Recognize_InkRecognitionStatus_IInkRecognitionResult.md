# CInkRecoContext::Recognize(InkRecognitionStatus *,IInkRecognitionResult * *)

- ea: `0x1800a63e0`
- end: `0x1800a66d8`
- name: `?Recognize@CInkRecoContext@@UEAAJPEAW4InkRecognitionStatus@@PEAPEAUIInkRecognitionResult@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(CInkRecoContext *__hidden this, enum InkRecognitionStatus *, struct IInkRecognitionResult **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800365f8`
- `0x180036824`
- `0x180085ab4`
- `0x1800a38dc`
- `0x1800a63e0`
- `0x1800c4560`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6571`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a6563`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a6563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a659e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a659e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a663b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a663b`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a6627`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800a6627`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CInkRecoContext::Recognize(
        CInkRecoContext *this,
        enum InkRecognitionStatus *a2,
        struct IInkRecognitionResult **a3)
{
  __int64 v6; // r8
  const unsigned __int16 *v7; // r9
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v11; // rdx
  int v12; // ebx
  _QWORD *v13; // r15
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v16; // rsi
  struct tagPREDICTION_MODE *v17; // r9
  __int64 v18; // rax
  __int64 v19; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v20[24]; // [rsp+48h] [rbp-40h] BYREF
  int v21; // [rsp+A0h] [rbp+18h] BYREF
  DWORD dwindex; // [rsp+A8h] [rbp+20h] BYREF

  if ( a3 && a2 )
  {
    v19 = 0;
    CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v20, (struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
    v8 = *((_QWORD *)this + 33);
    if ( !v8 || (v21 = 0, (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 56LL))(v8, &v21), !v21) )
    {
      v9 = ATL::AtlSetErrorInfo(&GUID_NULL, (WCHAR *)0x457, v6, v7, &IID_IInkRecognizerContext, 0x80280008, hInstance);
      CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v20);
      ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v19);
      return v9;
    }
    if ( *((_QWORD *)this + 12) )
    {
      (*(void (__fastcall **)(CInkRecoContext *))(*(_QWORD *)this + 200LL))(this);
      v12 = 0;
    }
    else
    {
      LOBYTE(v11) = 1;
      v12 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 72LL))((char *)this - 16, v11);
      if ( v12 < 0 )
        goto LABEL_31;
      if ( !*((_QWORD *)this + 12) )
        v12 = -2147418113;
      if ( v12 < 0 )
        goto LABEL_31;
    }
    v13 = (_QWORD *)((char *)this + 160);
    if ( *((_QWORD *)this + 20) )
      goto LABEL_18;
    EventW = CreateEventW(0, 0, 0, 0);
    *v13 = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v12 >= 0 )
    {
LABEL_18:
      CInkRecognizer::InternalUpdateUserDict(*((CInkRecognizer **)this + 13), 0);
      v16 = CoTaskMemAlloc(8u);
      if ( v16 )
      {
        v17 = 0;
        v18 = *((_QWORD *)this + 36);
        if ( v18 )
        {
          v17 = (struct tagPREDICTION_MODE *)(v18 + 4);
          *((_WORD *)this + 96) = 0x4000;
          *((_QWORD *)this + 25) = v18;
        }
        *v16 = v13;
        v12 = RequestResultsAsync(
                *(HRECOCONTEXT *)(*((_QWORD *)this + 12) + 16LL),
                (int (*)(unsigned int, unsigned __int8 *, struct tagPREDICTION_RESULT_PACKET *))InkRecoSynchronousCallback,
                v16,
                v17);
        if ( v12 < 0 )
        {
          CoTaskMemFree(v16);
        }
        else
        {
          dwindex = 0;
          v12 = CoWaitForMultipleHandles(0, 0x493E0u, 1u, (LPHANDLE)this + 20, &dwindex);
          if ( v12 < 0 )
            v12 = -2147418113;
        }
      }
      else
      {
        v12 = -2147024882;
      }
      *((_WORD *)this + 96) = 0;
      *((_QWORD *)this + 25) = 0;
      if ( v12 >= 0 )
      {
        if ( *((int *)this + 47) < 0 )
        {
          *a3 = 0;
          ATL::AtlComPtrAssign((struct IUnknown **)this + 21, 0);
        }
        else
        {
          *a2 = *((enum InkRecognitionStatus *)this + 46);
          *a3 = (struct IInkRecognitionResult *)*((_QWORD *)this + 21);
          *((_QWORD *)this + 21) = 0;
        }
        v12 = *((_DWORD *)this + 47);
      }
    }
LABEL_31:
    CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v20);
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v19);
    return (unsigned int)v12;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800a63e0  mov     rax, rsp
0x1800a63e3  mov     [rax+8], rbx
0x1800a63e7  mov     [rax+10h], rsi
0x1800a63eb  push    rdi
0x1800a63ec  push    r12
0x1800a63ee  push    r13
0x1800a63f0  push    r14
0x1800a63f2  push    r15
0x1800a63f4  sub     rsp, 60h
0x1800a63f8  mov     r12, r8
0x1800a63fb  mov     r13, rdx
0x1800a63fe  mov     rdi, rcx
0x1800a6401  xor     esi, esi
0x1800a6403  test    r8, r8
0x1800a6406  jz      loc_1800A66B9
0x1800a640c  test    rdx, rdx
0x1800a640f  jz      loc_1800A66B9
0x1800a6415  mov     [rax-48h], rsi
0x1800a6419  lea     rdx, [rcx+0D8h]; struct _RTL_CRITICAL_SECTION *
0x1800a6420  lea     rcx, [rax-40h]; this
0x1800a6424  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800a6429  nop
0x1800a642a  mov     rcx, [rdi+108h]
0x1800a6431  test    rcx, rcx
0x1800a6434  jnz     short loc_1800A6485
0x1800a6436  mov     rax, cs:hInstance
0x1800a643d  mov     [rsp+88h+var_58], rax; HINSTANCE
0x1800a6442  mov     [rsp+88h+var_60], 80280008h; int
0x1800a644a  lea     rax, IID_IInkRecognizerContext
0x1800a6451  mov     [rsp+88h+lpdwindex], rax; struct _GUID *
0x1800a6456  mov     edx, 457h; unsigned __int16 *
0x1800a645b  lea     rcx, GUID_NULL; clsid
0x1800a6462  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800a6467  mov     ebx, eax
0x1800a6469  lea     rcx, [rsp+88h+var_40]; this
0x1800a646e  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a6473  nop
0x1800a6474  lea     rcx, [rsp+88h+var_48]; void *
0x1800a6479  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a647e  mov     eax, ebx
0x1800a6480  jmp     loc_1800A66BE
0x1800a6485  mov     [rsp+88h+arg_10], esi
0x1800a648c  mov     rax, [rcx]
0x1800a648f  lea     rdx, [rsp+88h+arg_10]
0x1800a6497  mov     rax, [rax+38h]
0x1800a649b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a64a0  cmp     [rsp+88h+arg_10], esi
0x1800a64a7  jnz     short loc_1800A64F8
0x1800a64a9  mov     rax, cs:hInstance
0x1800a64b0  mov     [rsp+88h+var_58], rax; HINSTANCE
0x1800a64b5  mov     [rsp+88h+var_60], 80280008h; int
0x1800a64bd  lea     rax, IID_IInkRecognizerContext
0x1800a64c4  mov     [rsp+88h+lpdwindex], rax; struct _GUID *
0x1800a64c9  mov     edx, 457h; unsigned __int16 *
0x1800a64ce  lea     rcx, GUID_NULL; clsid
0x1800a64d5  call    ?AtlSetErrorInfo@ATL@@YAJAEBU_GUID@@PEBGK10JPEAUHINSTANCE__@@@Z; ATL::AtlSetErrorInfo(_GUID const &,ushort const *,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *)
0x1800a64da  mov     ebx, eax
0x1800a64dc  lea     rcx, [rsp+88h+var_40]; this
0x1800a64e1  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a64e6  nop
0x1800a64e7  lea     rcx, [rsp+88h+var_48]; void *
0x1800a64ec  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a64f1  mov     eax, ebx
0x1800a64f3  jmp     loc_1800A66BE
0x1800a64f8  cmp     [rdi+60h], rsi
0x1800a64fc  jnz     short loc_1800A6533
0x1800a64fe  mov     rax, [rdi-10h]
0x1800a6502  mov     dl, 1
0x1800a6504  lea     rcx, [rdi-10h]
0x1800a6508  mov     rax, [rax+48h]
0x1800a650c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6511  mov     ebx, eax
0x1800a6513  mov     r14d, 8000FFFFh
0x1800a6519  test    eax, eax
0x1800a651b  js      loc_1800A6697
0x1800a6521  cmp     [rdi+60h], rsi
0x1800a6525  cmovz   ebx, r14d
0x1800a6529  test    ebx, ebx
0x1800a652b  js      loc_1800A6697
0x1800a6531  jmp     short loc_1800A654D
0x1800a6533  mov     rax, [rdi]
0x1800a6536  mov     rcx, rdi
0x1800a6539  mov     rax, [rax+0C8h]
0x1800a6540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6545  mov     ebx, esi
0x1800a6547  mov     r14d, 8000FFFFh
0x1800a654d  lea     r15, [rdi+0A0h]
0x1800a6554  cmp     [r15], rsi
0x1800a6557  jnz     short loc_1800A658E
0x1800a6559  xor     r9d, r9d; lpName
0x1800a655c  xor     r8d, r8d; bInitialState
0x1800a655f  xor     edx, edx; bManualReset
0x1800a6561  xor     ecx, ecx; lpEventAttributes
0x1800a6563  call    cs:__imp_CreateEventW
0x1800a6569  mov     [r15], rax
0x1800a656c  test    rax, rax
0x1800a656f  jnz     short loc_1800A6586
0x1800a6571  call    cs:__imp_GetLastError
0x1800a6577  mov     ebx, eax
0x1800a6579  test    eax, eax
0x1800a657b  jle     short loc_1800A6586
0x1800a657d  movzx   ebx, ax
0x1800a6580  or      ebx, 80070000h
0x1800a6586  test    ebx, ebx
0x1800a6588  js      loc_1800A6697
0x1800a658e  xor     edx, edx; bool
0x1800a6590  mov     rcx, [rdi+68h]; this
0x1800a6594  call    ?InternalUpdateUserDict@CInkRecognizer@@IEAAJ_N@Z; CInkRecognizer::InternalUpdateUserDict(bool)
0x1800a6599  mov     ecx, 8; cb
0x1800a659e  call    cs:__imp_CoTaskMemAlloc
0x1800a65a4  mov     rsi, rax
0x1800a65a7  test    rax, rax
0x1800a65aa  jnz     short loc_1800A65B6
0x1800a65ac  mov     ebx, 8007000Eh
0x1800a65b1  jmp     loc_1800A6641
0x1800a65b6  test    ebx, ebx
0x1800a65b8  js      short loc_1800A6638
0x1800a65ba  xor     r9d, r9d
0x1800a65bd  mov     rax, [rdi+120h]
0x1800a65c4  test    rax, rax
0x1800a65c7  jz      short loc_1800A65DD
0x1800a65c9  lea     r9, [rax+4]; struct tagPREDICTION_MODE *
0x1800a65cd  mov     word ptr [rdi+0C0h], 4000h
0x1800a65d6  mov     [rdi+0C8h], rax
0x1800a65dd  mov     [rsi], r15
0x1800a65e0  mov     rcx, [rdi+60h]
0x1800a65e4  mov     r8, rsi; void *
0x1800a65e7  lea     rdx, ?InkRecoSynchronousCallback@@YAJKPEAEPEAUtagPREDICTION_RESULT_PACKET@@@Z; int (*)(unsigned int, unsigned __int8 *, struct tagPREDICTION_RESULT_PACKET *)
0x1800a65ee  mov     rcx, [rcx+10h]; HRECOCONTEXT
0x1800a65f2  call    ?RequestResultsAsync@@YAJPEAUHRECOCONTEXT__@@P6AJKPEAEPEAUtagPREDICTION_RESULT_PACKET@@@ZPEAXPEAUtagPREDICTION_MODE@@@Z; RequestResultsAsync(HRECOCONTEXT__ *,long (*)(ulong,uchar *,tagPREDICTION_RESULT_PACKET *),void *,tagPREDICTION_MODE *)
0x1800a65f7  mov     ebx, eax
0x1800a65f9  test    eax, eax
0x1800a65fb  js      short loc_1800A6638
0x1800a65fd  mov     [rsp+88h+dwindex], 0
0x1800a6608  lea     r9, [rdi+0A0h]; pHandles
0x1800a660f  lea     rax, [rsp+88h+dwindex]
0x1800a6617  mov     [rsp+88h+lpdwindex], rax; lpdwindex
0x1800a661c  mov     edx, 493E0h; dwTimeout
0x1800a6621  xor     ecx, ecx; dwFlags
0x1800a6623  lea     r8d, [rcx+1]; cHandles
0x1800a6627  call    cs:__imp_CoWaitForMultipleHandles
0x1800a662d  mov     ebx, eax
0x1800a662f  test    eax, eax
0x1800a6631  jns     short loc_1800A6641
0x1800a6633  mov     ebx, r14d
0x1800a6636  jmp     short loc_1800A6641
0x1800a6638  mov     rcx, rsi; pv
0x1800a663b  call    cs:__imp_CoTaskMemFree
0x1800a6641  xor     eax, eax
0x1800a6643  mov     [rdi+0C0h], ax
0x1800a664a  mov     [rdi+0C8h], rax
0x1800a6651  test    ebx, ebx
0x1800a6653  js      short loc_1800A6697
0x1800a6655  cmp     [rdi+0BCh], eax
0x1800a665b  jl      short loc_1800A667F
0x1800a665d  mov     eax, [rdi+0B8h]
0x1800a6663  mov     [r13+0], eax
0x1800a6667  mov     rax, [rdi+0A8h]
0x1800a666e  mov     [r12], rax
0x1800a6672  mov     qword ptr [rdi+0A8h], 0
0x1800a667d  jmp     short loc_1800A6691
0x1800a667f  mov     [r12], rax
0x1800a6683  lea     rcx, [rdi+0A8h]; struct IUnknown **
0x1800a668a  xor     edx, edx; struct IUnknown *
0x1800a668c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800a6691  mov     ebx, [rdi+0BCh]
0x1800a6697  jmp     short loc_1800A66A0
0x1800a6699  mov     ebx, [rsp+88h+arg_10]
0x1800a66a0  lea     rcx, [rsp+88h+var_40]; this
0x1800a66a5  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800a66aa  nop
0x1800a66ab  lea     rcx, [rsp+88h+var_48]; void *
0x1800a66b0  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800a66b5  mov     eax, ebx
0x1800a66b7  jmp     short loc_1800A66BE
0x1800a66b9  mov     eax, 80004003h
0x1800a66be  lea     r11, [rsp+88h+var_28]
0x1800a66c3  mov     rbx, [r11+30h]
0x1800a66c7  mov     rsi, [r11+38h]
0x1800a66cb  mov     rsp, r11
0x1800a66ce  pop     r15
0x1800a66d0  pop     r14
0x1800a66d2  pop     r13
0x1800a66d4  pop     r12
0x1800a66d6  pop     rdi
0x1800a66d7  retn
```
