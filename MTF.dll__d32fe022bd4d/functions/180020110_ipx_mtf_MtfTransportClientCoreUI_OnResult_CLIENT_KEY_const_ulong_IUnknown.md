# ipx::mtf::MtfTransportClientCoreUI::OnResult(_CLIENT_KEY const *,ulong,IUnknown *)

- ea: `0x180020110`
- end: `0x1800209e0`
- name: `?OnResult@MtfTransportClientCoreUI@mtf@ipx@@UEAAJPEBU_CLIENT_KEY@@KPEAUIUnknown@@@Z`
- size: `2256`
- prototype: `__int64 __fastcall(ipx::mtf::MtfTransportClientCoreUI *__hidden this, const struct _CLIENT_KEY *, unsigned int, struct IUnknown *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180002d88`
- `0x1800046d4`
- `0x180006074`
- `0x18001e89c`
- `0x180020110`
- `0x1800225bc`
- `0x180022c0c`
- `0x180023b50`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002076e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800207f6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020848`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002076e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800207f6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020848`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180020323`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800208b3`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180020928`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180020323`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800208b3`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180020928`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020211`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020211`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020153`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800201b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800203b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020153`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800201b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800203b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002021f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020458`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002021f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020458`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180020339`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800208c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002093e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180020339`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800208c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002093e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::OnResult(
        ipx::mtf::MtfTransportClientCoreUI *this,
        const struct _CLIENT_KEY *a2,
        unsigned int a3,
        struct IUnknown *a4)
{
  RTL_SRWLOCK *v8; // r14
  int v9; // eax
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // r14
  __int64 v13; // rcx
  char v14; // al
  const char *v15; // r9
  int v16; // eax
  int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // ebx
  struct IUnknown *v20; // rbx
  unsigned int v21; // r14d
  __int64 v22; // xmm6_8
  __int64 v23; // rdx
  __int64 v24; // r15
  void *v25; // rax
  __int64 v26; // r15
  int v27; // eax
  unsigned int v28; // ebx
  struct IUnknown *v29; // r14
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rcx
  int v33; // eax
  const char *v34; // r9
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // edx
  __int64 v38; // rcx
  int v39; // r13d
  char *v40; // rbx
  int v41; // eax
  unsigned int v42; // r15d
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rcx
  int v49; // [rsp+20h] [rbp-A8h]
  __int64 v50; // [rsp+30h] [rbp-98h] BYREF
  struct IUnknown *v51; // [rsp+38h] [rbp-90h] BYREF
  char *v52; // [rsp+40h] [rbp-88h]
  struct IUnknown *Parameter; // [rsp+48h] [rbp-80h] BYREF
  __int64 v54; // [rsp+50h] [rbp-78h]
  HANDLE Timer; // [rsp+58h] [rbp-70h]
  __int64 v56; // [rsp+60h] [rbp-68h] BYREF
  struct IUnknown *v57[2]; // [rsp+68h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  LODWORD(v51) = a3;
  v8 = (RTL_SRWLOCK *)((char *)this + 288);
  AcquireSRWLockExclusive((PSRWLOCK)this + 36);
  v9 = (*(__int64 (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 8LL))(this);
  if ( v9 == 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    return 0;
  }
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  try
  {
    v57[1] = (struct IUnknown *)this;
    v12 = *((_QWORD *)this + 31);
    if ( v12 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v12 + 16));
      if ( *(_DWORD *)(v12 + 56) == a3
        && *(_DWORD *)(v12 + 24) == *(_DWORD *)a2
        && *(_DWORD *)(v12 + 28) == *((_DWORD *)a2 + 1)
        && *(_WORD *)(v12 + 32) == *((_WORD *)a2 + 4) )
      {
        if ( a4 )
          ((void (__fastcall *)(struct IUnknown *))a4->lpVtbl->AddRef)(a4);
        v13 = *(_QWORD *)(v12 + 48);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        *(_QWORD *)(v12 + 48) = a4;
        SetEvent(*(HANDLE *)(v12 + 40));
        if ( v12 != -16 )
          ReleaseSRWLockExclusive((PSRWLOCK)(v12 + 16));
        v14 = 1;
      }
      else
      {
        if ( v12 != -16 )
          ReleaseSRWLockExclusive((PSRWLOCK)(v12 + 16));
        v14 = 0;
      }
      if ( v14 )
      {
        (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
        return 0;
      }
    }
    v16 = *((_DWORD *)this + 67);
    if ( *((_DWORD *)this + 65) == 1 )
    {
      if ( v16 == 256 || *((_DWORD *)this + 66) != 32 )
      {
        Parameter = 0;
        v22 = *(_QWORD *)a2;
        v54 = *(_QWORD *)a2;
        LODWORD(v51) = *((_DWORD *)a2 + 2);
        Timer = (HANDLE)__PAIR64__(a3, (unsigned int)v51);
        if ( a4 )
          ((void (__fastcall *)(struct IUnknown *))a4->lpVtbl->AddRef)(a4);
        Parameter = a4;
        AcquireSRWLockExclusive((PSRWLOCK)this + 35);
        v52 = (char *)this + 280;
        if ( *((_QWORD *)this + 39) <= (unsigned __int64)(*((_QWORD *)this + 41) + 1LL) )
          std::deque<ipx::mtf::MtfTransportClientCoreUI::RESULTITEM>::_Growmap((char *)this + 296);
        v23 = *((_QWORD *)this + 39) - 1LL;
        *((_QWORD *)this + 40) &= v23;
        v24 = v23 & (*((_QWORD *)this + 41) + *((_QWORD *)this + 40));
        if ( !*(_QWORD *)(*((_QWORD *)this + 38) + 8 * v24) )
        {
          v25 = operator new(0x18u);
          if ( !v25 )
            std::_Xbad_alloc();
          *(_QWORD *)(*((_QWORD *)this + 38) + 8 * v24) = v25;
        }
        v26 = *(_QWORD *)(*((_QWORD *)this + 38) + 8 * v24);
        *(_QWORD *)v26 = a4;
        if ( a4 )
          ((void (__fastcall *)(struct IUnknown *))a4->lpVtbl->AddRef)(a4);
        *(_QWORD *)(v26 + 8) = v22;
        *(_DWORD *)(v26 + 16) = (_DWORD)v51;
        *(_DWORD *)(v26 + 20) = a3;
        ++*((_QWORD *)this + 41);
        if ( this != (ipx::mtf::MtfTransportClientCoreUI *)-280LL )
          ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
        if ( a4 )
          ((void (__fastcall *)(struct IUnknown *))a4->lpVtbl->Release)(a4);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 29) + 176LL))(
          *((_QWORD *)this + 29),
          *((_QWORD *)this + 30),
          4);
        (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
        return 0;
      }
      else
      {
        v51 = 0;
        v17 = ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(this, a4, &v51);
        v19 = v17;
        if ( v17 >= 0 )
        {
          CRPCTimeout::CRPCTimeout(&Parameter, v18);
          v20 = v51;
          v21 = (*(__int64 (__fastcall **)(_QWORD, const struct _CLIENT_KEY *, _QWORD, struct IUnknown *))(**((_QWORD **)this + 42) + 24LL))(
                  *((_QWORD *)this + 42),
                  a2,
                  a3,
                  v51);
          if ( (int)v54 >= 0 )
          {
            LODWORD(v54) = -2147467259;
            CoDisableCallCancellation(0);
            if ( Timer )
            {
              DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
              Timer = 0;
            }
          }
          if ( v20 )
            ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
          (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
          return v21;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AB,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
            (const char *)(unsigned int)v17,
            v49);
          if ( v51 )
            ((void (__fastcall *)(struct IUnknown *))v51->lpVtbl->Release)(v51);
          (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
          return v19;
        }
      }
    }
    if ( v16 == 256 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        v10);
    v57[0] = 0;
    v27 = ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(this, a4, v57);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v27,
        v49);
      if ( v57[0] )
        ((void (__fastcall *)(struct IUnknown *))v57[0]->lpVtbl->Release)(v57[0]);
      (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
      return v28;
    }
    v50 = 0;
    v29 = v57[0];
    v30 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v57[0]->lpVtbl->QueryInterface)(
            v57[0],
            &GUID_0000000c_0000_0000_c000_000000000046,
            &v50);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v30,
        v49);
      v32 = v50;
      v50 = 0;
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
LABEL_97:
      (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
      return v31;
    }
    v52 = 0;
    v56 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v50 + 40LL))(v50, 0, 2, &v56);
    v31 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v33,
        v49);
      v35 = v50;
      v50 = 0;
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
      goto LABEL_97;
    }
    if ( HIDWORD(v56) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        v34);
    v36 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(*(_QWORD *)v50 + 40LL))(v50, v52, 0, 0);
    v31 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v36,
        v49);
      v38 = v50;
      v50 = 0;
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
      goto LABEL_97;
    }
    if ( *((_DWORD *)this + 66) == 32 )
    {
      v39 = v56 + 24;
      v40 = (char *)operator new[]((unsigned int)(v56 + 24));
      v52 = v40;
      *(_QWORD *)v40 = *(_QWORD *)a2;
      *((_DWORD *)v40 + 2) = *((_DWORD *)a2 + 2);
      *((_DWORD *)v40 + 3) = (_DWORD)v51;
      *((_DWORD *)v40 + 4) = v39;
      *((_WORD *)v40 + 10) = 260;
      v41 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD))(*(_QWORD *)v50 + 24LL))(
              v50,
              (_DWORD *)v40 + 6,
              (unsigned int)v56,
              0);
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v41,
          v49);
        operator delete[](v40);
        v43 = v50;
        v50 = 0;
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        if ( v29 )
          ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
LABEL_81:
        (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
        return v42;
      }
      v44 = ipx::mtf::CoreUIMessageSender::Send((ipx::mtf::MtfTransportClientCoreUI *)((char *)this + 136), v40, v39);
      v42 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EE,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v44,
          v49);
        operator delete[](v40);
        v45 = v50;
        v50 = 0;
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        if ( v29 )
          ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
        goto LABEL_81;
      }
      operator delete[](v40);
    }
    else
    {
      CRPCTimeout::CRPCTimeout(&Parameter, v37);
      v46 = (*(__int64 (__fastcall **)(_QWORD, const struct _CLIENT_KEY *, _QWORD, __int64))(**((_QWORD **)this + 42)
                                                                                           + 24LL))(
              *((_QWORD *)this + 42),
              a2,
              a3,
              v50);
      v31 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F5,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v46,
          v49);
        if ( (int)v54 >= 0 )
        {
          LODWORD(v54) = -2147467259;
          CoDisableCallCancellation(0);
          if ( Timer )
          {
            DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            Timer = 0;
          }
        }
        v47 = v50;
        v50 = 0;
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        if ( v29 )
          ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
        goto LABEL_97;
      }
      if ( (int)v54 >= 0 )
      {
        LODWORD(v54) = -2147467259;
        CoDisableCallCancellation(0);
        if ( Timer )
          DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
    }
    v48 = v50;
    v50 = 0;
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( v29 )
      ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F9,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180020110  mov     rax, rsp
0x180020113  push    rbx
0x180020114  push    rsi
0x180020115  push    rdi
0x180020116  push    r12
0x180020118  push    r13
0x18002011a  push    r14
0x18002011c  push    r15
0x18002011e  sub     rsp, 90h
0x180020125  movaps  xmmword ptr [rax-48h], xmm6
0x180020129  mov     rax, cs:__security_cookie
0x180020130  xor     rax, rsp
0x180020133  mov     [rsp+0C8h+var_50], rax
0x180020138  mov     rbx, r9
0x18002013b  mov     r13d, r8d
0x18002013e  mov     dword ptr [rsp+0C8h+var_90], r8d
0x180020143  mov     r12, rdx
0x180020146  mov     rsi, rcx
0x180020149  lea     r14, [rcx+120h]
0x180020150  mov     rcx, r14; SRWLock
0x180020153  call    cs:__imp_AcquireSRWLockExclusive
0x180020159  mov     rax, [rsi]
0x18002015c  mov     rcx, rsi
0x18002015f  mov     rax, [rax+8]
0x180020163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020168  cmp     eax, 1
0x18002016b  jnz     short loc_180020186
0x18002016d  lock dec dword ptr [rsi+18h]
0x180020171  test    r14, r14
0x180020174  jz      short loc_18002017F
0x180020176  mov     rcx, r14; SRWLock
0x180020179  call    cs:__imp_ReleaseSRWLockExclusive
0x18002017f  xor     eax, eax
0x180020181  jmp     loc_18002098D
0x180020186  xor     edi, edi
0x180020188  test    r14, r14
0x18002018b  jz      short loc_180020196
0x18002018d  mov     rcx, r14; SRWLock
0x180020190  call    cs:__imp_ReleaseSRWLockExclusive
0x180020196  mov     [rsp+0C8h+var_58], rsi
0x18002019b  mov     r14, [rsi+0F8h]
0x1800201a2  test    r14, r14
0x1800201a5  jz      loc_180020254
0x1800201ab  lea     r15, [r14+10h]
0x1800201af  mov     rcx, r15; SRWLock
0x1800201b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800201b8  cmp     [r14+38h], r13d
0x1800201bc  jnz     short loc_180020229
0x1800201be  mov     eax, [r12]
0x1800201c2  cmp     [r14+18h], eax
0x1800201c6  jnz     short loc_180020229
0x1800201c8  mov     eax, [r12+4]
0x1800201cd  cmp     [r14+1Ch], eax
0x1800201d1  jnz     short loc_180020229
0x1800201d3  movzx   eax, word ptr [r12+8]
0x1800201d9  cmp     [r14+20h], ax
0x1800201de  jnz     short loc_180020229
0x1800201e0  test    rbx, rbx
0x1800201e3  jz      short loc_1800201F4
0x1800201e5  mov     rax, [rbx]
0x1800201e8  mov     rcx, rbx
0x1800201eb  mov     rax, [rax+8]
0x1800201ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f4  mov     rcx, [r14+30h]
0x1800201f8  test    rcx, rcx
0x1800201fb  jz      short loc_180020209
0x1800201fd  mov     rax, [rcx]
0x180020200  mov     rax, [rax+10h]
0x180020204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020209  mov     [r14+30h], rbx
0x18002020d  mov     rcx, [r14+28h]; hEvent
0x180020211  call    cs:__imp_SetEvent
0x180020217  test    r15, r15
0x18002021a  jz      short loc_180020225
0x18002021c  mov     rcx, r15; SRWLock
0x18002021f  call    cs:__imp_ReleaseSRWLockExclusive
0x180020225  mov     al, 1
0x180020227  jmp     short loc_18002023A
0x180020229  test    r15, r15
0x18002022c  jz      short loc_180020237
0x18002022e  mov     rcx, r15; SRWLock
0x180020231  call    cs:__imp_ReleaseSRWLockExclusive
0x180020237  mov     al, dil
0x18002023a  test    al, al
0x18002023c  jz      short loc_180020254
0x18002023e  mov     rax, [rsi]
0x180020241  mov     rcx, rsi
0x180020244  mov     rax, [rax+10h]
0x180020248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002024d  xor     eax, eax
0x18002024f  jmp     loc_18002098D
0x180020254  mov     eax, [rsi+10Ch]
0x18002025a  cmp     dword ptr [rsi+104h], 1
0x180020261  jnz     loc_1800204B3
0x180020267  cmp     eax, 100h
0x18002026c  jz      loc_180020370
0x180020272  cmp     dword ptr [rsi+108h], 20h ; ' '
0x180020279  jnz     loc_180020370
0x18002027f  mov     [rsp+0C8h+var_90], rdi
0x180020284  lea     r8, [rsp+0C8h+var_90]; struct IUnknown **
0x180020289  mov     rdx, rbx; struct IUnknown *
0x18002028c  mov     rcx, rsi; this
0x18002028f  call    ?_SerializeDeserializeData@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEAUIUnknown@@PEAPEAU4@@Z; ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(IUnknown *,IUnknown * *)
0x180020294  mov     ebx, eax
0x180020296  test    eax, eax
0x180020298  jns     short loc_1800202E4
0x18002029a  mov     rcx, [rsp+0C8h]; this
0x1800202a2  mov     r9d, eax; char *
0x1800202a5  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800202ac  mov     edx, 1ABh; void *
0x1800202b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800202b6  nop
0x1800202b7  mov     rcx, [rsp+0C8h+var_90]
0x1800202bc  test    rcx, rcx
0x1800202bf  jz      short loc_1800202CE
0x1800202c1  mov     rax, [rcx]
0x1800202c4  mov     rax, [rax+10h]
0x1800202c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202cd  nop
0x1800202ce  mov     rax, [rsi]
0x1800202d1  mov     rcx, rsi
0x1800202d4  mov     rax, [rax+10h]
0x1800202d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202dd  mov     eax, ebx
0x1800202df  jmp     loc_18002098D
0x1800202e4  lea     rcx, [rsp+0C8h+Parameter]; Parameter
0x1800202e9  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x1800202ee  nop
0x1800202ef  mov     rcx, [rsi+150h]
0x1800202f6  mov     rax, [rcx]
0x1800202f9  mov     rbx, [rsp+0C8h+var_90]
0x1800202fe  mov     r9, rbx
0x180020301  mov     r8d, r13d
0x180020304  mov     rdx, r12
0x180020307  mov     rax, [rax+18h]
0x18002030b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020310  mov     r14d, eax
0x180020313  cmp     dword ptr [rsp+0C8h+var_78], edi
0x180020317  jl      short loc_180020344
0x180020319  mov     dword ptr [rsp+0C8h+var_78], 80004005h
0x180020321  xor     ecx, ecx; pReserved
0x180020323  call    cs:__imp_CoDisableCallCancellation
0x180020329  mov     rdx, [rsp+0C8h+Timer]; Timer
0x18002032e  test    rdx, rdx
0x180020331  jz      short loc_180020344
0x180020333  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180020337  xor     ecx, ecx; TimerQueue
0x180020339  call    cs:__imp_DeleteTimerQueueTimer
0x18002033f  mov     [rsp+0C8h+Timer], rdi
0x180020344  test    rbx, rbx
0x180020347  jz      short loc_180020359
0x180020349  mov     rax, [rbx]
0x18002034c  mov     rcx, rbx
0x18002034f  mov     rax, [rax+10h]
0x180020353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020358  nop
0x180020359  mov     rax, [rsi]
0x18002035c  mov     rcx, rsi
0x18002035f  mov     rax, [rax+10h]
0x180020363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020368  mov     eax, r14d
0x18002036b  jmp     loc_18002098D
0x180020370  mov     [rsp+0C8h+Parameter], rdi
0x180020375  movsd   xmm6, qword ptr [r12]
0x18002037b  movsd   [rsp+0C8h+var_78], xmm6
0x180020381  mov     eax, [r12+8]
0x180020386  mov     dword ptr [rsp+0C8h+var_90], eax
0x18002038a  mov     dword ptr [rsp+0C8h+Timer], eax
0x18002038e  mov     dword ptr [rsp+0C8h+Timer+4], r13d
0x180020393  test    rbx, rbx
0x180020396  jz      short loc_1800203A7
0x180020398  mov     rax, [rbx]
0x18002039b  mov     rcx, rbx
0x18002039e  mov     rax, [rax+8]
0x1800203a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203a7  mov     [rsp+0C8h+Parameter], rbx
0x1800203ac  lea     r12, [rsi+118h]
0x1800203b3  mov     rcx, r12; SRWLock
0x1800203b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800203bc  mov     [rsp+0C8h+var_88], r12
0x1800203c1  lea     r14, [rsi+128h]
0x1800203c8  mov     rax, [r14+20h]
0x1800203cc  inc     rax
0x1800203cf  cmp     [r14+10h], rax
0x1800203d3  ja      short loc_1800203DD
0x1800203d5  mov     rcx, r14
0x1800203d8  call    ?_Growmap@?$deque@URESULTITEM@MtfTransportClientCoreUI@mtf@ipx@@V?$allocator@URESULTITEM@MtfTransportClientCoreUI@mtf@ipx@@@std@@@std@@IEAAX_K@Z; std::deque<ipx::mtf::MtfTransportClientCoreUI::RESULTITEM>::_Growmap(unsigned __int64)
0x1800203dd  mov     rdx, [r14+10h]
0x1800203e1  dec     rdx
0x1800203e4  and     [r14+18h], rdx
0x1800203e8  mov     r15, [r14+18h]
0x1800203ec  add     r15, [r14+20h]
0x1800203f0  and     r15, rdx
0x1800203f3  mov     rax, [r14+8]
0x1800203f7  cmp     [rax+r15*8], rdi
0x1800203fb  jnz     short loc_18002041B
0x1800203fd  mov     ecx, 18h; Size
0x180020402  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020407  mov     rcx, rax
0x18002040a  test    rax, rax
0x18002040d  jz      loc_1800209B5
0x180020413  mov     rax, [r14+8]
0x180020417  mov     [rax+r15*8], rcx
0x18002041b  mov     rax, [r14+8]
0x18002041f  mov     r15, [rax+r15*8]
0x180020423  mov     [r15], rbx
0x180020426  test    rbx, rbx
0x180020429  jz      short loc_18002043A
0x18002042b  mov     rax, [rbx]
0x18002042e  mov     rcx, rbx
0x180020431  mov     rax, [rax+8]
0x180020435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002043a  movsd   qword ptr [r15+8], xmm6
0x180020440  mov     eax, dword ptr [rsp+0C8h+var_90]
0x180020444  mov     [r15+10h], eax
0x180020448  mov     [r15+14h], r13d
0x18002044c  inc     qword ptr [r14+20h]
0x180020450  test    r12, r12
0x180020453  jz      short loc_18002045F
0x180020455  mov     rcx, r12; SRWLock
0x180020458  call    cs:__imp_ReleaseSRWLockExclusive
0x18002045e  nop
0x18002045f  test    rbx, rbx
0x180020462  jz      short loc_180020474
0x180020464  mov     rax, [rbx]
0x180020467  mov     rcx, rbx
0x18002046a  mov     rax, [rax+10h]
0x18002046e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020473  nop
0x180020474  mov     rcx, [rsi+0E8h]
0x18002047b  mov     rax, [rcx]
0x18002047e  mov     [rsp+0C8h+var_A8], edi
0x180020482  xor     r9d, r9d
0x180020485  lea     r8d, [r9+4]
0x180020489  mov     rdx, [rsi+0F0h]
0x180020490  mov     rax, [rax+0B0h]
0x180020497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002049c  nop
0x18002049d  mov     rax, [rsi]
0x1800204a0  mov     rcx, rsi
0x1800204a3  mov     rax, [rax+10h]
0x1800204a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ac  xor     eax, eax
0x1800204ae  jmp     loc_18002098D
0x1800204b3  mov     rcx, [rsp+0C8h]; this
0x1800204bb  cmp     eax, 100h
0x1800204c0  jz      loc_1800209BB
0x1800204c6  mov     [rsp+0C8h+var_60], rdi
0x1800204cb  lea     r8, [rsp+0C8h+var_60]; struct IUnknown **
0x1800204d0  mov     rdx, rbx; struct IUnknown *
0x1800204d3  mov     rcx, rsi; this
0x1800204d6  call    ?_SerializeDeserializeData@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEAUIUnknown@@PEAPEAU4@@Z; ipx::mtf::MtfTransportClientCoreUI::_SerializeDeserializeData(IUnknown *,IUnknown * *)
0x1800204db  mov     ebx, eax
0x1800204dd  test    eax, eax
0x1800204df  jns     short loc_18002052B
0x1800204e1  mov     rcx, [rsp+0C8h]; this
0x1800204e9  mov     r9d, eax; char *
0x1800204ec  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800204f3  mov     edx, 1B7h; void *
0x1800204f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204fd  nop
0x1800204fe  mov     rcx, [rsp+0C8h+var_60]
0x180020503  test    rcx, rcx
0x180020506  jz      short loc_180020515
0x180020508  mov     rax, [rcx]
0x18002050b  mov     rax, [rax+10h]
0x18002050f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020514  nop
0x180020515  mov     rax, [rsi]
0x180020518  mov     rcx, rsi
0x18002051b  mov     rax, [rax+10h]
0x18002051f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020524  mov     eax, ebx
0x180020526  jmp     loc_18002098D
0x18002052b  mov     [rsp+0C8h+var_98], rdi
0x180020530  mov     r14, [rsp+0C8h+var_60]
0x180020535  mov     rax, [r14]
0x180020538  lea     r8, [rsp+0C8h+var_98]
0x18002053d  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180020544  mov     rcx, r14
0x180020547  mov     rax, [rax]
0x18002054a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002054f  mov     ebx, eax
0x180020551  test    eax, eax
0x180020553  jns     short loc_1800205B9
0x180020555  mov     rcx, [rsp+0C8h]; this
0x18002055d  mov     r9d, eax; char *
0x180020560  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180020567  mov     edx, 1BAh; void *
0x18002056c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020571  nop
0x180020572  mov     rcx, [rsp+0C8h+var_98]
0x180020577  mov     [rsp+0C8h+var_98], rdi
0x18002057c  test    rcx, rcx
0x18002057f  jz      short loc_18002058E
0x180020581  mov     rax, [rcx]
0x180020584  mov     rax, [rax+10h]
0x180020588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002058d  nop
0x18002058e  test    r14, r14
  ... truncated ...
```
