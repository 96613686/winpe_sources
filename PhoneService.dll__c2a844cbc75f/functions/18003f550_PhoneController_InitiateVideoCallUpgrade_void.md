# PhoneController::_InitiateVideoCallUpgrade(void)

- ea: `0x18003f550`
- end: `0x18003f8e6`
- name: `?_InitiateVideoCallUpgrade@PhoneController@@IEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800233e0`
- `0x180023670`
- `0x180041084`
- `0x180042438`

## callees

- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x18003f550`
- `0x180051e44`
- `0x1800524c8`
- `0x180070030`
- `0x180071ba8`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f57a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f57a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f59d`

## string_xrefs

- `0x18003f580`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003f882`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003f6f6`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18003f782`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`
- `0x18003f834`: `onecoreuap\net\phone\phoneservice\service\lib\phoneline.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_InitiateVideoCallUpgrade(PhoneController *this)
{
  __int64 v2; // rcx
  char *v3; // rsi
  struct _GUID *v4; // r12
  PhoneLineStorage *v5; // rcx
  int PhoneLine; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // edi
  __int64 v10; // rcx
  GUID *v11; // rdi
  __int64 v12; // rax
  struct PhoneLine *v13; // rbx
  int v14; // eax
  BackTraceCollection *v15; // rcx
  unsigned int v16; // r14d
  struct PhoneLine *v17; // rcx
  void (__fastcall **v18)(_QWORD, _QWORD, _QWORD); // rax
  GUID *v19; // r15
  int v20; // eax
  BackTraceCollection *v21; // rcx
  _WORD *v22; // rcx
  GUID *v23; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+38h] [rbp-28h]
  struct PhoneLine *v25; // [rsp+40h] [rbp-20h] BYREF
  GUID v26; // [rsp+48h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9311);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v3 = (char *)this + 632;
  if ( *((_QWORD *)this + 82) == *((_QWORD *)this + 83)
    || !*(_DWORD *)v3
    || (v4 = (struct _GUID *)((char *)this + 636),
        *(_QWORD *)((char *)this + 636) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1)
    && *(_QWORD *)((char *)this + 644) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    v4 = (struct _GUID *)((char *)this + 636);
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9313);
    if ( *((_QWORD *)this + 82) == *((_QWORD *)this + 83)
      || !*(_DWORD *)v3
      || *(_QWORD *)&v4->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
      && *(_QWORD *)((char *)this + 644) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
  v5 = (PhoneLineStorage *)*((_QWORD *)this + 19);
  v25 = 0;
  PhoneLine = PhoneLineStorage::GetPhoneLine(v5, v4, &v25, 0);
  v8 = PhoneLine;
  if ( PhoneLine < 0 )
  {
    BackTraceCollection::Capture(v7, PhoneLine);
    Log_HREvent_7(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9316);
    if ( v25 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v25 + 16LL))(v25);
    return v8;
  }
  v10 = *((_QWORD *)this + 12);
  v23 = 0;
  v26 = GUID_00000000_0000_0000_0000_000000000000;
  PhoneCallStorage::FindCall(v10, &v23, (char *)this + 632, 0);
  v11 = v23;
  if ( v23 )
    v26 = v23[423];
  v12 = *((_QWORD *)this + 82);
  v13 = v25;
  v24 = v12;
  v23 = 0;
  v14 = WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get((char *)v25 + 32, &v23);
  v16 = v14;
  if ( v14 < 0 )
  {
    BackTraceCollection::Capture(v15, v14);
    Log_HREvent_19(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1218);
    v17 = (struct PhoneLine *)v23;
    if ( !v23 )
    {
LABEL_39:
      BackTraceCollection::Capture(v17, v16);
      Log_HREvent_7(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 9326);
      if ( v11 )
        (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v11->Data1 + 16LL))(v11);
      if ( v13 )
        (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v13 + 16LL))(v13);
      return v16;
    }
    v18 = *(void (__fastcall ***)(_QWORD, _QWORD, _QWORD))&v23->Data1;
LABEL_38:
    ((void (*)(void))v18[2])();
    goto LABEL_39;
  }
  v19 = v23;
  v25 = 0;
  if ( !v23
    || ((**(void (__fastcall ***)(GUID *, GUID *, struct PhoneLine **))&v23->Data1)(
          v23,
          &GUID_f0e8fffd_0341_4e42_adb3_9c9f91e2d911,
          &v25),
        !v25) )
  {
    v16 = -2147467262;
    Log_HREvent_19(2147500034LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1221);
    v17 = v25;
    if ( v25 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v25 + 16LL))(v25);
    if ( !v19 )
      goto LABEL_39;
    goto LABEL_37;
  }
  v20 = (*(__int64 (__fastcall **)(struct PhoneLine *, __int64, GUID *))(*(_QWORD *)v25 + 40LL))(v25, v24, &v26);
  v16 = v20;
  if ( v20 < 0 )
  {
    BackTraceCollection::Capture(v21, v20);
    Log_HREvent_19(v16, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phoneline.cpp", 1223);
    if ( v25 )
      (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_37:
    v18 = *(void (__fastcall ***)(_QWORD, _QWORD, _QWORD))&v19->Data1;
    goto LABEL_38;
  }
  if ( v25 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v25 + 16LL))(v25);
  (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v19->Data1 + 16LL))(v19);
  *(_DWORD *)v3 = 0;
  *((_DWORD *)v3 + 5) = 0;
  *v4 = GUID_00000000_0000_0000_0000_000000000000;
  v22 = (_WORD *)*((_QWORD *)v3 + 3);
  *((_QWORD *)v3 + 4) = v22;
  *v22 = 0;
  if ( v11 )
    (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v11->Data1 + 16LL))(v11);
  if ( v13 )
    (*(void (__fastcall **)(struct PhoneLine *))(*(_QWORD *)v13 + 16LL))(v13);
  return 0;
}

```

## disassembly

```asm
0x18003f550  mov     [rsp-28h+arg_8], rbx
0x18003f555  mov     [rsp-28h+arg_10], rsi
0x18003f55a  push    rbp
0x18003f55b  push    rdi
0x18003f55c  push    r12
0x18003f55e  push    r14
0x18003f560  push    r15
0x18003f562  mov     rbp, rsp
0x18003f565  sub     rsp, 60h
0x18003f569  mov     rax, cs:__security_cookie
0x18003f570  xor     rax, rsp
0x18003f573  mov     [rbp+var_8], rax
0x18003f577  mov     rbx, rcx
0x18003f57a  call    cs:__imp_GetCurrentThreadId
0x18003f580  lea     r14, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003f587  cmp     [rbx+0F0h], eax
0x18003f58d  jz      short loc_18003F5B0
0x18003f58f  mov     r8d, 245Fh
0x18003f595  mov     rdx, r14
0x18003f598  call    Log_AssertionEvent_3
0x18003f59d  call    cs:__imp_GetCurrentThreadId
0x18003f5a3  cmp     [rbx+0F0h], eax
0x18003f5a9  jz      short loc_18003F5B0
0x18003f5ab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003f5b0  lea     rsi, [rbx+278h]
0x18003f5b7  mov     rax, [rsi+20h]
0x18003f5bb  cmp     [rsi+18h], rax
0x18003f5bf  jz      short loc_18003F5E5
0x18003f5c1  cmp     dword ptr [rsi], 0
0x18003f5c4  jz      short loc_18003F5E5
0x18003f5c6  lea     r12, [rsi+4]
0x18003f5ca  mov     rax, [r12]
0x18003f5ce  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003f5d5  jnz     short loc_18003F626
0x18003f5d7  mov     rax, [r12+8]
0x18003f5dc  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18003f5e3  jnz     short loc_18003F626
0x18003f5e5  mov     r8d, 2461h
0x18003f5eb  lea     r12, [rsi+4]
0x18003f5ef  mov     rdx, r14
0x18003f5f2  call    Log_AssertionEvent_3
0x18003f5f7  mov     rax, [rsi+20h]
0x18003f5fb  cmp     [rsi+18h], rax
0x18003f5ff  jz      short loc_18003F621
0x18003f601  cmp     dword ptr [rsi], 0
0x18003f604  jz      short loc_18003F621
0x18003f606  mov     rax, [r12]
0x18003f60a  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003f611  jnz     short loc_18003F626
0x18003f613  mov     rax, [r12+8]
0x18003f618  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18003f61f  jnz     short loc_18003F626
0x18003f621  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003f626  mov     rcx, [rbx+98h]; this
0x18003f62d  lea     r8, [rbp+var_20]; struct PhoneLine **
0x18003f631  xor     r9d, r9d; struct ISecurityToken *
0x18003f634  mov     [rbp+var_20], 0
0x18003f63c  mov     rdx, r12; struct _GUID *
0x18003f63f  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x18003f644  mov     edi, eax
0x18003f646  test    eax, eax
0x18003f648  jns     short loc_18003F682
0x18003f64a  mov     edx, eax; int
0x18003f64c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003f651  mov     r9d, 2464h
0x18003f657  mov     r8, r14
0x18003f65a  mov     edx, 1
0x18003f65f  mov     ecx, edi
0x18003f661  call    Log_HREvent_7
0x18003f666  mov     rcx, [rbp+var_20]
0x18003f66a  test    rcx, rcx
0x18003f66d  jz      short loc_18003F67B
0x18003f66f  mov     rax, [rcx]
0x18003f672  mov     rax, [rax+10h]
0x18003f676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f67b  mov     eax, edi
0x18003f67d  jmp     loc_18003F8C1
0x18003f682  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003f689  mov     rcx, [rbx+60h]
0x18003f68d  lea     rdx, [rbp+var_30]
0x18003f691  xor     r9d, r9d
0x18003f694  mov     [rbp+var_30], 0
0x18003f69c  mov     r8, rsi
0x18003f69f  movdqu  [rbp+var_18], xmm0
0x18003f6a4  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x18003f6a9  mov     rdi, [rbp+var_30]
0x18003f6ad  test    rdi, rdi
0x18003f6b0  jz      short loc_18003F6BE
0x18003f6b2  movups  xmm0, xmmword ptr [rdi+1A70h]
0x18003f6b9  movdqu  [rbp+var_18], xmm0
0x18003f6be  mov     rax, [rbx+290h]
0x18003f6c5  lea     rdx, [rbp+var_30]
0x18003f6c9  mov     rbx, [rbp+var_20]
0x18003f6cd  mov     [rbp+var_28], rax
0x18003f6d1  mov     [rbp+var_30], 0
0x18003f6d9  lea     rcx, [rbx+20h]
0x18003f6dd  call    ?Get@?$WrappedComPtrBase@UIPhoneLine@@VSupportsShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneLine@@@Z; WrappedComPtrBase<IPhoneLine,SupportsShutdown,utl::recursive_mutex>::Get(IPhoneLine * *)
0x18003f6e2  mov     r14d, eax
0x18003f6e5  test    eax, eax
0x18003f6e7  jns     short loc_18003F71F
0x18003f6e9  mov     edx, eax; int
0x18003f6eb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003f6f0  mov     r9d, 4C2h
0x18003f6f6  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003f6fd  mov     edx, 1
0x18003f702  mov     ecx, r14d
0x18003f705  call    Log_HREvent_19
0x18003f70a  mov     rcx, [rbp+var_30]
0x18003f70e  test    rcx, rcx
0x18003f711  jz      loc_18003F874
0x18003f717  mov     rax, [rcx]
0x18003f71a  jmp     loc_18003F86B
0x18003f71f  mov     r15, [rbp+var_30]
0x18003f723  mov     [rbp+var_20], 0
0x18003f72b  test    r15, r15
0x18003f72e  jz      loc_18003F82E
0x18003f734  mov     rax, [r15]
0x18003f737  lea     r8, [rbp+var_20]
0x18003f73b  lea     rdx, _GUID_f0e8fffd_0341_4e42_adb3_9c9f91e2d911
0x18003f742  mov     rcx, r15
0x18003f745  mov     rax, [rax]
0x18003f748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f74d  mov     rcx, [rbp+var_20]
0x18003f751  test    rcx, rcx
0x18003f754  jz      loc_18003F82E
0x18003f75a  mov     rax, [rcx]
0x18003f75d  lea     r8, [rbp+var_18]
0x18003f761  mov     rdx, [rbp+var_28]
0x18003f765  mov     rax, [rax+28h]
0x18003f769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f76e  mov     r14d, eax
0x18003f771  test    eax, eax
0x18003f773  jns     short loc_18003F7B4
0x18003f775  mov     edx, eax; int
0x18003f777  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003f77c  mov     r9d, 4C7h
0x18003f782  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003f789  mov     edx, 1
0x18003f78e  mov     ecx, r14d
0x18003f791  call    Log_HREvent_19
0x18003f796  mov     rcx, [rbp+var_20]
0x18003f79a  test    rcx, rcx
0x18003f79d  jz      loc_18003F865
0x18003f7a3  mov     rax, [rcx]
0x18003f7a6  mov     rax, [rax+10h]
0x18003f7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7af  jmp     loc_18003F865
0x18003f7b4  mov     rcx, [rbp+var_20]
0x18003f7b8  test    rcx, rcx
0x18003f7bb  jz      short loc_18003F7C9
0x18003f7bd  mov     rax, [rcx]
0x18003f7c0  mov     rax, [rax+10h]
0x18003f7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7c9  mov     rax, [r15]
0x18003f7cc  mov     rcx, r15
0x18003f7cf  mov     rax, [rax+10h]
0x18003f7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7d8  mov     dword ptr [rsi], 0
0x18003f7de  xor     eax, eax
0x18003f7e0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003f7e7  mov     dword ptr [rsi+14h], 0
0x18003f7ee  movdqu  xmmword ptr [r12], xmm0
0x18003f7f4  mov     rcx, [rsi+18h]
0x18003f7f8  mov     [rsi+20h], rcx
0x18003f7fc  mov     [rcx], ax
0x18003f7ff  test    rdi, rdi
0x18003f802  jz      short loc_18003F813
0x18003f804  mov     rax, [rdi]
0x18003f807  mov     rcx, rdi
0x18003f80a  mov     rax, [rax+10h]
0x18003f80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f813  test    rbx, rbx
0x18003f816  jz      short loc_18003F827
0x18003f818  mov     rax, [rbx]
0x18003f81b  mov     rcx, rbx
0x18003f81e  mov     rax, [rax+10h]
0x18003f822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f827  xor     eax, eax
0x18003f829  jmp     loc_18003F8C1
0x18003f82e  mov     r14d, 80004002h
0x18003f834  lea     r8, aOnecoreuapNetP_9; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003f83b  mov     ecx, r14d
0x18003f83e  mov     r9d, 4C5h
0x18003f844  xor     edx, edx
0x18003f846  call    Log_HREvent_19
0x18003f84b  mov     rcx, [rbp+var_20]
0x18003f84f  test    rcx, rcx
0x18003f852  jz      short loc_18003F860
0x18003f854  mov     rax, [rcx]
0x18003f857  mov     rax, [rax+10h]
0x18003f85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f860  test    r15, r15
0x18003f863  jz      short loc_18003F874
0x18003f865  mov     rax, [r15]
0x18003f868  mov     rcx, r15
0x18003f86b  mov     rax, [rax+10h]
0x18003f86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f874  mov     edx, r14d; int
0x18003f877  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003f87c  mov     r9d, 246Eh
0x18003f882  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003f889  mov     edx, 1
0x18003f88e  mov     ecx, r14d
0x18003f891  call    Log_HREvent_7
0x18003f896  test    rdi, rdi
0x18003f899  jz      short loc_18003F8AA
0x18003f89b  mov     rax, [rdi]
0x18003f89e  mov     rcx, rdi
0x18003f8a1  mov     rax, [rax+10h]
0x18003f8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8aa  test    rbx, rbx
0x18003f8ad  jz      short loc_18003F8BE
0x18003f8af  mov     rcx, [rbx]
0x18003f8b2  mov     rax, [rcx+10h]
0x18003f8b6  mov     rcx, rbx
0x18003f8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8be  mov     eax, r14d
0x18003f8c1  mov     rcx, [rbp+var_8]
0x18003f8c5  xor     rcx, rsp; StackCookie
0x18003f8c8  call    __security_check_cookie
0x18003f8cd  lea     r11, [rsp+60h+var_s0]
0x18003f8d2  mov     rbx, [r11+38h]
0x18003f8d6  mov     rsi, [r11+40h]
0x18003f8da  mov     rsp, r11
0x18003f8dd  pop     r15
0x18003f8df  pop     r14
0x18003f8e1  pop     r12
0x18003f8e3  pop     rdi
0x18003f8e4  pop     rbp
0x18003f8e5  retn
```
