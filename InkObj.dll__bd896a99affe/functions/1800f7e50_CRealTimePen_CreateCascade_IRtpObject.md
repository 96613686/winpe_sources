# CRealTimePen::CreateCascade(IRtpObject *)

- ea: `0x1800f7e50`
- end: `0x1800f8231`
- name: `?CreateCascade@CRealTimePen@@UEAAJPEAUIRtpObject@@@Z`
- size: `993`
- prototype: `__int64 __fastcall(CRealTimePen *__hidden this, struct IRtpObject *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c20`
- `0x180010350`
- `0x180012d28`
- `0x1800217b0`
- `0x180032700`
- `0x180037f74`
- `0x1800394a0`
- `0x180039fe4`
- `0x180041748`
- `0x180079728`
- `0x1800f7e50`
- `0x1800f88dc`
- `0x18010c010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1800f7fbe`
- `msvcrt!_beginthreadex` at `0x1800f7fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7ff6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f7fd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f7fd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7f1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7f59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7f1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f7f59`

## pseudocode

```c
__int64 __fastcall CRealTimePen::CreateCascade(CRealTimePen *this, struct IRtpObject *a2)
{
  CRealTimePen *v2; // r12
  char *v4; // r13
  signed int v6; // ebx
  uintptr_t *v8; // r14
  __int64 (__fastcall **v9)(struct IRtpObject *, GUID *, __int64 *); // rax
  signed int LastError; // eax
  int v11; // edi
  HANDLE EventW; // rax
  signed int v13; // eax
  uintptr_t v14; // rax
  signed int v15; // eax
  volatile int *v16; // rax
  CComDllModule *v17; // rcx
  volatile int *v18; // rdi
  volatile int *v19; // rcx
  int v20; // eax
  __int64 (__fastcall **v21)(struct IRtpObject *, GUID *, __int64 *); // rax
  int v22; // eax
  int v23; // edi
  __int64 v24; // rcx
  __int64 (__fastcall **v25)(struct IRtpObject *, GUID *, __int64 *); // rax
  int v26; // eax
  int v27; // edi
  __int64 v28; // rax
  __int64 v29; // [rsp+30h] [rbp-40h]
  __int64 v30; // [rsp+38h] [rbp-38h]
  _BYTE v31[16]; // [rsp+40h] [rbp-30h] BYREF
  __int128 ArgList; // [rsp+50h] [rbp-20h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h]
  __int64 ThrdAddr; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+50h] BYREF
  struct IUnknown *v36; // [rsp+C8h] [rbp+58h] BYREF

  v2 = (CRealTimePen *)((char *)this - 16);
  LODWORD(ThrdAddr) = 0;
  v4 = (char *)this - 8;
  InputEventLock::InputEventLock(
    v31,
    ((unsigned __int64)this - 8) & ((unsigned __int128)-(__int128)((unsigned __int64)this - 16) >> 64),
    &ThrdAddr,
    11);
  v6 = ThrdAddr;
  if ( (int)ThrdAddr < 0 )
    goto LABEL_2;
  if ( !(unsigned int)CRealTimePen::InternalIsEnabled(v2) )
  {
    v8 = (uintptr_t *)((char *)this + 360);
    if ( !*((_QWORD *)this + 45) )
    {
      v29 = *((_QWORD *)this + 9);
      v30 = *((_QWORD *)this + 47);
      v9 = *(__int64 (__fastcall ***)(struct IRtpObject *, GUID *, __int64 *))a2;
      v35 = 0;
      v6 = ((__int64 (__fastcall *)(struct IRtpObject *, __int64 *))v9[40])(a2, &v35);
      if ( v35 )
      {
        v33 = 0;
        ArgList = 0;
        *(_QWORD *)&ArgList = CreateEventW(0, 1, 0, 0);
        if ( !(_QWORD)ArgList )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
        v11 = v6;
        if ( v6 >= 0 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)&ArgList + 1) = EventW;
          if ( EventW )
          {
            *((_QWORD *)this + 46) = EventW;
          }
          else
          {
            v13 = GetLastError();
            v6 = v13;
            if ( v13 > 0 )
              v6 = (unsigned __int16)v13 | 0x80070000;
            v11 = v6;
            if ( v6 < 0 )
              goto LABEL_22;
          }
          v33 = 0;
          LODWORD(ThrdAddr) = 0;
          v14 = _beginthreadex(0, 0, CRealTimePen::QueueThreadProc, &ArgList, 0, (unsigned int *)&ThrdAddr);
          *v8 = v14;
          if ( v14 )
          {
            WaitForSingleObject((HANDLE)ArgList, 0xFFFFFFFF);
            if ( v33 )
              goto LABEL_22;
            SafeCloseHandle((void **)this + 45);
            *v8 = 0;
            v6 = -2147220957;
          }
          else
          {
            v15 = GetLastError();
            v6 = v15;
            if ( v15 > 0 )
              v6 = (unsigned __int16)v15 | 0x80070000;
          }
          v11 = v6;
        }
LABEL_22:
        SafeCloseHandle((void **)&ArgList);
        if ( v11 < 0 )
          goto LABEL_43;
        v16 = (volatile int *)WinMalloc(0x30u);
        v18 = v16;
        if ( !v16 )
        {
          v6 = -2147024882;
          goto LABEL_42;
        }
        *((_DWORD *)v16 + 2) = 0;
        *((_QWORD *)v16 + 4) = 0;
        *((_QWORD *)v16 + 5) = 0;
        *(_QWORD *)v16 = &ATL::CComObject<CStylusInputShim>::`vftable';
        CComDllModule::Lock(v17);
        ATL::SafeIncrementReferenceMultiThread(v18 + 2);
        ATL::SafeDecrementReferenceMultiThread(v19);
        v36 = 0;
        v20 = (**(__int64 (__fastcall ***)(volatile int *, GUID *, struct IUnknown **))v18)(
                v18,
                &GUID_b1f54bb8_16a2_4afd_aa51_190cce9e6a8e,
                &v36);
        v6 = v20;
        if ( v20 < 0 )
        {
          v23 = v20;
        }
        else
        {
          v21 = *(__int64 (__fastcall ***)(struct IRtpObject *, GUID *, __int64 *))a2;
          ThrdAddr = 0;
          v22 = (*v21)(a2, &GUID_46ea2855_1838_4088_b1c4_010d53f65140, &ThrdAddr);
          v6 = v22;
          if ( v22 >= 0 )
          {
            v22 = (*(__int64 (__fastcall **)(volatile int *, __int64, _QWORD))(*(_QWORD *)v18 + 24LL))(v18, ThrdAddr, 0);
            v6 = v22;
          }
          v23 = v22;
          ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ThrdAddr);
          if ( v23 >= 0 )
          {
            v24 = *((_QWORD *)this + 10);
            if ( v24 )
              (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v24 + 56LL))(v24, 0, 1);
            ATL::AtlComPtrAssign((struct IUnknown **)this + 10, v36);
          }
        }
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v36);
        if ( v23 < 0
          || (v6 = (*(__int64 (__fastcall **)(struct IRtpObject *, __int64))(*(_QWORD *)a2 + 312LL))(a2, v33), v6 < 0) )
        {
LABEL_42:
          if ( v6 >= 0 )
          {
LABEL_2:
            InputEventLock::~InputEventLock((InputEventLock *)v31);
            return (unsigned int)v6;
          }
LABEL_43:
          CRealTimePen::DestroyQueueThread(v2);
          ATL::AtlComPtrAssign((struct IUnknown **)this + 10, 0);
          (*(void (__fastcall **)(CRealTimePen *, __int64))(*(_QWORD *)v2 + 48LL))(v2, v29);
          (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 312LL))(v4, v30);
          goto LABEL_2;
        }
        v25 = *(__int64 (__fastcall ***)(struct IRtpObject *, GUID *, __int64 *))a2;
        ThrdAddr = 0;
        v26 = ((__int64 (__fastcall *)(struct IRtpObject *, __int64 *))v25[35])(a2, &ThrdAddr);
        v6 = v26;
        if ( v26 < 0 )
        {
          v27 = v26;
        }
        else
        {
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)ThrdAddr + 120LL))(ThrdAddr, 0);
          v27 = v6;
          if ( v6 >= 0 )
            goto LABEL_39;
        }
        (*(void (__fastcall **)(struct IRtpObject *, __int64))(*(_QWORD *)a2 + 48LL))(a2, v35);
LABEL_39:
        ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&ThrdAddr);
        if ( v27 >= 0 )
        {
          v28 = *(_QWORD *)v4;
          *((_QWORD *)this + 9) = v35;
          v6 = (*(__int64 (__fastcall **)(char *))(v28 + 312))(v4);
        }
        goto LABEL_42;
      }
    }
  }
  InputEventLock::~InputEventLock((InputEventLock *)v31);
  return 2150105094LL;
}

```

## disassembly

```asm
0x1800f7e50  mov     [rsp-38h+arg_8], rbx
0x1800f7e55  push    rbp
0x1800f7e56  push    rsi
0x1800f7e57  push    rdi
0x1800f7e58  push    r12
0x1800f7e5a  push    r13
0x1800f7e5c  push    r14
0x1800f7e5e  push    r15
0x1800f7e60  mov     rbp, rsp
0x1800f7e63  sub     rsp, 70h
0x1800f7e67  lea     r12, [rcx-10h]
0x1800f7e6b  xor     edi, edi
0x1800f7e6d  mov     r15, rdx
0x1800f7e70  mov     dword ptr [rbp+arg_0], edi
0x1800f7e73  lea     r13, [rcx-8]
0x1800f7e77  mov     rsi, rcx
0x1800f7e7a  mov     rax, r12
0x1800f7e7d  lea     r8, [rbp+arg_0]
0x1800f7e81  neg     rax
0x1800f7e84  lea     r9d, [rdi+0Bh]
0x1800f7e88  lea     rcx, [rbp+var_30]
0x1800f7e8c  sbb     rdx, rdx
0x1800f7e8f  and     rdx, r13
0x1800f7e92  call    ??0InputEventLock@@QEAA@PEAUIRtpObject@@AEAJW4RtsLockType@@@Z; InputEventLock::InputEventLock(IRtpObject *,long &,RtsLockType)
0x1800f7e97  mov     ebx, dword ptr [rbp+arg_0]
0x1800f7e9a  test    ebx, ebx
0x1800f7e9c  jns     short loc_1800F7EAE
0x1800f7e9e  lea     rcx, [rbp+var_30]; this
0x1800f7ea2  call    ??1InputEventLock@@QEAA@XZ; InputEventLock::~InputEventLock(void)
0x1800f7ea7  mov     eax, ebx
0x1800f7ea9  jmp     loc_1800F8219
0x1800f7eae  mov     rcx, r12; this
0x1800f7eb1  call    ?InternalIsEnabled@CRealTimePen@@AEAAHXZ; CRealTimePen::InternalIsEnabled(void)
0x1800f7eb6  test    eax, eax
0x1800f7eb8  jnz     loc_1800F820B
0x1800f7ebe  lea     r14, [rsi+168h]
0x1800f7ec5  cmp     [r14], rdi
0x1800f7ec8  jnz     loc_1800F820B
0x1800f7ece  mov     rax, [rsi+48h]
0x1800f7ed2  lea     rdx, [rbp+arg_10]
0x1800f7ed6  mov     [rbp+var_40], rax
0x1800f7eda  mov     rcx, r15
0x1800f7edd  mov     rax, [rsi+178h]
0x1800f7ee4  mov     [rbp+var_38], rax
0x1800f7ee8  mov     rax, [r15]
0x1800f7eeb  mov     [rbp+arg_10], rdi
0x1800f7eef  mov     rax, [rax+140h]
0x1800f7ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f7efb  mov     ebx, eax
0x1800f7efd  cmp     [rbp+arg_10], rdi
0x1800f7f01  jz      loc_1800F820B
0x1800f7f07  xor     eax, eax
0x1800f7f09  xorps   xmm0, xmm0
0x1800f7f0c  xor     r9d, r9d; lpName
0x1800f7f0f  mov     [rbp+var_10], rax
0x1800f7f13  xor     r8d, r8d; bInitialState
0x1800f7f16  xor     ecx, ecx; lpEventAttributes
0x1800f7f18  movups  [rbp+ArgList], xmm0
0x1800f7f1c  lea     edx, [rax+1]; bManualReset
0x1800f7f1f  call    cs:__imp_CreateEventW
0x1800f7f25  mov     qword ptr [rbp+ArgList], rax
0x1800f7f29  test    rax, rax
0x1800f7f2c  jnz     short loc_1800F7F43
0x1800f7f2e  call    cs:__imp_GetLastError
0x1800f7f34  mov     ebx, eax
0x1800f7f36  test    eax, eax
0x1800f7f38  jle     short loc_1800F7F43
0x1800f7f3a  movzx   ebx, ax
0x1800f7f3d  or      ebx, 80070000h
0x1800f7f43  mov     edi, ebx
0x1800f7f45  test    ebx, ebx
0x1800f7f47  js      loc_1800F800D
0x1800f7f4d  xor     r9d, r9d; lpName
0x1800f7f50  xor     r8d, r8d; bInitialState
0x1800f7f53  xor     ecx, ecx; lpEventAttributes
0x1800f7f55  lea     edx, [r9+1]; bManualReset
0x1800f7f59  call    cs:__imp_CreateEventW
0x1800f7f5f  mov     qword ptr [rbp+ArgList+8], rax
0x1800f7f63  test    rax, rax
0x1800f7f66  jnz     short loc_1800F7F88
0x1800f7f68  call    cs:__imp_GetLastError
0x1800f7f6e  mov     ebx, eax
0x1800f7f70  test    eax, eax
0x1800f7f72  jle     short loc_1800F7F7D
0x1800f7f74  movzx   ebx, ax
0x1800f7f77  or      ebx, 80070000h
0x1800f7f7d  mov     edi, ebx
0x1800f7f7f  test    ebx, ebx
0x1800f7f81  jns     short loc_1800F7F8F
0x1800f7f83  jmp     loc_1800F800D
0x1800f7f88  mov     [rsi+170h], rax
0x1800f7f8f  lea     rax, [rbp+arg_0]
0x1800f7f93  mov     [rbp+var_10], 0
0x1800f7f9b  mov     [rsp+70h+ThrdAddr], rax; ThrdAddr
0x1800f7fa0  lea     r9, [rbp+ArgList]; ArgList
0x1800f7fa4  lea     r8, ?QueueThreadProc@CRealTimePen@@CAK_K@Z; StartAddress
0x1800f7fab  mov     [rsp+70h+InitFlag], 0; InitFlag
0x1800f7fb3  xor     edx, edx; StackSize
0x1800f7fb5  mov     dword ptr [rbp+arg_0], 0
0x1800f7fbc  xor     ecx, ecx; Security
0x1800f7fbe  call    cs:__imp__beginthreadex
0x1800f7fc4  mov     [r14], rax
0x1800f7fc7  test    rax, rax
0x1800f7fca  jz      short loc_1800F7FF6
0x1800f7fcc  mov     rcx, qword ptr [rbp+ArgList]; hHandle
0x1800f7fd0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800f7fd3  call    cs:__imp_WaitForSingleObject
0x1800f7fd9  cmp     [rbp+var_10], 0
0x1800f7fde  jnz     short loc_1800F800D
0x1800f7fe0  mov     rcx, r14; void **
0x1800f7fe3  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800f7fe8  mov     qword ptr [r14], 0
0x1800f7fef  mov     ebx, 80040223h
0x1800f7ff4  jmp     short loc_1800F800B
0x1800f7ff6  call    cs:__imp_GetLastError
0x1800f7ffc  mov     ebx, eax
0x1800f7ffe  test    eax, eax
0x1800f8000  jle     short loc_1800F800B
0x1800f8002  movzx   ebx, ax
0x1800f8005  or      ebx, 80070000h
0x1800f800b  mov     edi, ebx
0x1800f800d  lea     rcx, [rbp+ArgList]; void **
0x1800f8011  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x1800f8016  test    edi, edi
0x1800f8018  js      loc_1800F81C8
0x1800f801e  mov     ecx, 30h ; '0'; unsigned __int64
0x1800f8023  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800f8028  mov     rdi, rax
0x1800f802b  test    rax, rax
0x1800f802e  jz      loc_1800F81BB
0x1800f8034  mov     dword ptr [rax+8], 0
0x1800f803b  mov     qword ptr [rax+20h], 0
0x1800f8043  mov     qword ptr [rax+28h], 0
0x1800f804b  lea     rax, ??_7?$CComObject@VCStylusInputShim@@@ATL@@6B@; const ATL::CComObject<CStylusInputShim>::`vftable'
0x1800f8052  mov     [rdi], rax
0x1800f8055  call    ?Lock@CComDllModule@@QEAAJXZ; CComDllModule::Lock(void)
0x1800f805a  lea     rcx, [rdi+8]; volatile int *
0x1800f805e  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800f8063  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800f8068  mov     [rbp+arg_18], 0
0x1800f8070  lea     r8, [rbp+arg_18]
0x1800f8074  mov     rax, [rdi]
0x1800f8077  lea     rdx, _GUID_b1f54bb8_16a2_4afd_aa51_190cce9e6a8e
0x1800f807e  mov     rcx, rdi
0x1800f8081  mov     rax, [rax]
0x1800f8084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8089  mov     ebx, eax
0x1800f808b  test    eax, eax
0x1800f808d  js      short loc_1800F8107
0x1800f808f  mov     rax, [r15]
0x1800f8092  lea     r8, [rbp+arg_0]
0x1800f8096  lea     rdx, _GUID_46ea2855_1838_4088_b1c4_010d53f65140
0x1800f809d  mov     [rbp+arg_0], 0
0x1800f80a5  mov     rcx, r15
0x1800f80a8  mov     rax, [rax]
0x1800f80ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80b0  mov     ebx, eax
0x1800f80b2  test    eax, eax
0x1800f80b4  js      short loc_1800F80CE
0x1800f80b6  mov     rax, [rdi]
0x1800f80b9  xor     r8d, r8d
0x1800f80bc  mov     rdx, [rbp+arg_0]
0x1800f80c0  mov     rcx, rdi
0x1800f80c3  mov     rax, [rax+18h]
0x1800f80c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80cc  mov     ebx, eax
0x1800f80ce  lea     rcx, [rbp+arg_0]; void *
0x1800f80d2  mov     edi, eax
0x1800f80d4  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f80d9  test    edi, edi
0x1800f80db  js      short loc_1800F8109
0x1800f80dd  mov     rcx, [rsi+50h]
0x1800f80e1  test    rcx, rcx
0x1800f80e4  jz      short loc_1800F80F8
0x1800f80e6  mov     rax, [rcx]
0x1800f80e9  xor     edx, edx
0x1800f80eb  mov     rax, [rax+38h]
0x1800f80ef  lea     r8d, [rdx+1]
0x1800f80f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80f8  mov     rdx, [rbp+arg_18]; struct IUnknown *
0x1800f80fc  lea     rcx, [rsi+50h]; struct IUnknown **
0x1800f8100  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f8105  jmp     short loc_1800F8109
0x1800f8107  mov     edi, eax
0x1800f8109  lea     rcx, [rbp+arg_18]; void *
0x1800f810d  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f8112  test    edi, edi
0x1800f8114  js      loc_1800F81C0
0x1800f811a  mov     rax, [r15]
0x1800f811d  mov     rcx, r15
0x1800f8120  mov     rdx, [rbp+var_10]
0x1800f8124  mov     rax, [rax+138h]
0x1800f812b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8130  mov     ebx, eax
0x1800f8132  test    eax, eax
0x1800f8134  js      loc_1800F81C0
0x1800f813a  mov     rax, [r15]
0x1800f813d  lea     rdx, [rbp+arg_0]
0x1800f8141  mov     rcx, r15
0x1800f8144  mov     [rbp+arg_0], 0
0x1800f814c  mov     rax, [rax+118h]
0x1800f8153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8158  mov     ebx, eax
0x1800f815a  test    eax, eax
0x1800f815c  js      short loc_1800F817A
0x1800f815e  mov     rcx, [rbp+arg_0]
0x1800f8162  xor     edx, edx
0x1800f8164  mov     rax, [rcx]
0x1800f8167  mov     rax, [rax+78h]
0x1800f816b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8170  mov     ebx, eax
0x1800f8172  mov     edi, eax
0x1800f8174  test    eax, eax
0x1800f8176  jns     short loc_1800F818F
0x1800f8178  jmp     short loc_1800F817C
0x1800f817a  mov     edi, eax
0x1800f817c  mov     rax, [r15]
0x1800f817f  mov     rcx, r15
0x1800f8182  mov     rdx, [rbp+arg_10]
0x1800f8186  mov     rax, [rax+30h]
0x1800f818a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f818f  lea     rcx, [rbp+arg_0]; void *
0x1800f8193  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f8198  test    edi, edi
0x1800f819a  js      short loc_1800F81C0
0x1800f819c  mov     rax, [r13+0]
0x1800f81a0  mov     rcx, r13
0x1800f81a3  mov     rdx, [rbp+arg_10]
0x1800f81a7  mov     [rsi+48h], rdx
0x1800f81ab  mov     rax, [rax+138h]
0x1800f81b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f81b7  mov     ebx, eax
0x1800f81b9  jmp     short loc_1800F81C0
0x1800f81bb  mov     ebx, 8007000Eh
0x1800f81c0  test    ebx, ebx
0x1800f81c2  jns     loc_1800F7E9E
0x1800f81c8  mov     rcx, r12; this
0x1800f81cb  call    ?DestroyQueueThread@CRealTimePen@@AEAAJXZ; CRealTimePen::DestroyQueueThread(void)
0x1800f81d0  lea     rcx, [rsi+50h]; struct IUnknown **
0x1800f81d4  xor     edx, edx; struct IUnknown *
0x1800f81d6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f81db  mov     rax, [r12]
0x1800f81df  mov     rcx, r12
0x1800f81e2  mov     rdx, [rbp+var_40]
0x1800f81e6  mov     rax, [rax+30h]
0x1800f81ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f81ef  mov     rax, [r13+0]
0x1800f81f3  mov     rcx, r13
0x1800f81f6  mov     rdx, [rbp+var_38]
0x1800f81fa  mov     rax, [rax+138h]
0x1800f8201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8206  jmp     loc_1800F7E9E
0x1800f820b  lea     rcx, [rbp+var_30]; this
0x1800f820f  call    ??1InputEventLock@@QEAA@XZ; InputEventLock::~InputEventLock(void)
0x1800f8214  mov     eax, 80280006h
0x1800f8219  mov     rbx, [rsp+70h+arg_8]
0x1800f8221  add     rsp, 70h
0x1800f8225  pop     r15
0x1800f8227  pop     r14
0x1800f8229  pop     r13
0x1800f822b  pop     r12
0x1800f822d  pop     rdi
0x1800f822e  pop     rsi
0x1800f822f  pop     rbp
0x1800f8230  retn
```
