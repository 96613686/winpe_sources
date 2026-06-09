# PrivacyAwareCapabilityCheck(void *,void *,ushort const *,bool,PrivacyCapCheckResult *,uint)

- ea: `0x180013b70`
- end: `0x180013cbc`
- name: `?PrivacyAwareCapabilityCheck@@YAJPEAX0PEBG_NPEAW4PrivacyCapCheckResult@@I@Z`
- size: `332`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessHandle@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, enum PrivacyCapCheckResult *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800139e0`

## callees

- `0x180007fac`
- `0x18000d4e0`
- `0x18000f01c`
- `0x180012680`
- `0x180013740`
- `0x180013ab4`
- `0x180013b70`
- `0x180013e68`
- `0x180014400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c84`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180013bfb`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180013bfb`

## string_xrefs

- `0x180013bee`: `broadFileSystemAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrivacyAwareCapabilityCheck(
        HANDLE ProcessHandle,
        void *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        enum PrivacyCapCheckResult *a5)
{
  void *v5; // rdi
  enum PrivacyCapCheckResult *v7; // rsi
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  int ImpersonationTokenFromProcess; // eax
  unsigned __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rcx
  _QWORD v19[3]; // [rsp+20h] [rbp-30h] BYREF
  int v20; // [rsp+38h] [rbp-18h]
  enum PrivacyCapCheckResult *v21; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  void *v23; // [rsp+90h] [rbp+40h] BYREF
  char v24; // [rsp+98h] [rbp+48h] BYREF

  v5 = a2;
  v7 = a5;
  *(_DWORD *)a5 = 103;
  v24 = 0;
  v23 = 0;
  if ( !a2 )
  {
    if ( !ProcessHandle )
    {
      v8 = -2147024891;
      v9 = 188;
LABEL_14:
      v12 = (unsigned int)v8;
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v23,
      0);
    ImpersonationTokenFromProcess = GetImpersonationTokenFromProcess(ProcessHandle, v10, &v23);
    v8 = ImpersonationTokenFromProcess;
    if ( ImpersonationTokenFromProcess < 0 )
    {
      v12 = (unsigned int)ImpersonationTokenFromProcess;
      v9 = 191;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
        (const char *)v12,
        v19[0]);
      goto LABEL_16;
    }
    v5 = v23;
  }
  v13 = CapabilityCheck(v5, L"broadFileSystemAccess", &v24);
  if ( v13 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecore\\base\\windows.storage\\src\\camcheckhelpers.h",
            (const char *)(unsigned int)v13,
            v19[0]);
LABEL_9:
    v8 = v14;
LABEL_16:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    return (unsigned int)v8;
  }
  if ( !v24 )
  {
    v8 = 0;
    goto LABEL_16;
  }
  v8 = IsTokenLowIL(v5);
  if ( v8 < 0 )
  {
    v9 = 203;
    goto LABEL_14;
  }
  LOBYTE(v15) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageItemPrivacyChecks>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_StorageItemPrivacyChecks>::GetImpl'::`2'::impl,
    v15);
  if ( !v8 )
  {
    v19[0] = ProcessHandle;
    v19[1] = v5;
    v19[2] = L"broadFileSystemAccess";
    v20 = 0;
    v21 = v7;
    CurrentThreadId = GetCurrentThreadId();
    v14 = Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(
            v18,
            CurrentThreadId,
            (__int64)v19);
    goto LABEL_9;
  }
  *(_DWORD *)v7 = 3;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
  return 0;
}

```

## disassembly

```asm
0x180013b70  mov     [rsp-28h+arg_0], rbx
0x180013b75  mov     [rsp-28h+arg_18], r9b
0x180013b7a  mov     [rsp-28h+arg_10], r8
0x180013b7f  push    rbp
0x180013b80  push    rsi
0x180013b81  push    rdi
0x180013b82  push    r12
0x180013b84  push    r14
0x180013b86  mov     rbp, rsp
0x180013b89  sub     rsp, 50h
0x180013b8d  mov     rdi, rdx
0x180013b90  mov     r14, rcx
0x180013b93  mov     rsi, [rbp+arg_20]
0x180013b97  mov     dword ptr [rsi], 67h ; 'g'
0x180013b9d  mov     [rbp+arg_18], 0
0x180013ba1  mov     [rbp+arg_10], 0
0x180013ba9  test    rdx, rdx
0x180013bac  jnz     short loc_180013BEA
0x180013bae  test    rcx, rcx
0x180013bb1  jnz     short loc_180013BBF
0x180013bb3  mov     ebx, 80070005h
0x180013bb8  mov     edx, 0BCh
0x180013bbd  jmp     short loc_180013C3E
0x180013bbf  xor     edx, edx
0x180013bc1  lea     rcx, [rbp+arg_10]
0x180013bc5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180013bca  lea     r8, [rbp+arg_10]; void **
0x180013bce  mov     rcx, r14; ProcessHandle
0x180013bd1  call    ?GetImpersonationTokenFromProcess@@YAJPEAXKPEAPEAX@Z; GetImpersonationTokenFromProcess(void *,ulong,void * *)
0x180013bd6  mov     ebx, eax
0x180013bd8  test    eax, eax
0x180013bda  jns     short loc_180013BE6
0x180013bdc  mov     r9d, eax
0x180013bdf  mov     edx, 0BFh
0x180013be4  jmp     short loc_180013C41
0x180013be6  mov     rdi, [rbp+arg_10]
0x180013bea  lea     r8, [rbp+arg_18]
0x180013bee  lea     r12, aBroadfilesyste; "broadFileSystemAccess"
0x180013bf5  mov     rdx, r12
0x180013bf8  mov     rcx, rdi
0x180013bfb  call    cs:__imp_CapabilityCheck
0x180013c01  test    eax, eax
0x180013c03  jns     short loc_180013C21
0x180013c05  mov     rcx, [rbp+28h]; this
0x180013c09  mov     r9d, eax; char *
0x180013c0c  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x180013c13  mov     edx, 0C4h; void *
0x180013c18  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013c1d  mov     ebx, eax
0x180013c1f  jmp     short loc_180013C52
0x180013c21  cmp     [rbp+arg_18], 0
0x180013c25  jnz     short loc_180013C2B
0x180013c27  xor     ebx, ebx
0x180013c29  jmp     short loc_180013C52
0x180013c2b  mov     rcx, rdi; void *
0x180013c2e  call    ?IsTokenLowIL@@YAJPEAX@Z; IsTokenLowIL(void *)
0x180013c33  mov     ebx, eax
0x180013c35  test    eax, eax
0x180013c37  jns     short loc_180013C5F
0x180013c39  mov     edx, 0CBh; void *
0x180013c3e  mov     r9d, ebx; char *
0x180013c41  lea     r8, aOnecoreBaseWin_0; "onecore\\base\\windows.storage\\src\\ca"...
0x180013c48  mov     rcx, [rbp+28h]; this
0x180013c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c51  nop
0x180013c52  lea     rcx, [rbp+arg_10]
0x180013c56  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013c5b  mov     eax, ebx
0x180013c5d  jmp     short loc_180013CA8
0x180013c5f  mov     dl, 1
0x180013c61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageItemPrivacyChecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageItemPrivacyChecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageItemPrivacyChecks> `wil::Feature<__WilFeatureTraits_Feature_StorageItemPrivacyChecks>::GetImpl(void)'::`2'::impl
0x180013c68  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageItemPrivacyChecks@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageItemPrivacyChecks>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180013c6d  test    ebx, ebx
0x180013c6f  jnz     short loc_180013C97
0x180013c71  mov     [rbp+var_30], r14
0x180013c75  mov     [rbp+var_28], rdi
0x180013c79  mov     [rbp+var_20], r12
0x180013c7d  mov     [rbp+var_18], ebx
0x180013c80  mov     [rbp+var_10], rsi
0x180013c84  call    cs:__imp_GetCurrentThreadId
0x180013c8a  lea     r8, [rbp+var_30]
0x180013c8e  mov     edx, eax
0x180013c90  call    ??$RunSynchronousTaskOnMTA@V_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@ComTaskPool@Internal@Windows@@SAJW4TaskOptions@12@K$$QEAV_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_@@@Z; Windows::Internal::ComTaskPool::RunSynchronousTaskOnMTA<_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_>(Windows::Internal::TaskOptions,ulong,_lambda_419cf1979f92fcf8ac0fa6abc9b86b4a_ &&)
0x180013c95  jmp     short loc_180013C1D
0x180013c97  mov     dword ptr [rsi], 3
0x180013c9d  lea     rcx, [rbp+arg_10]
0x180013ca1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013ca6  xor     eax, eax
0x180013ca8  mov     rbx, [rsp+50h+arg_0]
0x180013cb0  add     rsp, 50h
0x180013cb4  pop     r14
0x180013cb6  pop     r12
0x180013cb8  pop     rdi
0x180013cb9  pop     rsi
0x180013cba  pop     rbp
0x180013cbb  retn
```
