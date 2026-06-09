# Container::Manager::Hcs::Details::ComputeSystemImpl::InitiateAsyncHcsCall(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &,Container::Manager::Hcs::Details::ComputeSystemImpl::AsyncHcsCall,std::optional<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>)

- ea: `0x180180c74`
- end: `0x180180fc7`
- name: `?InitiateAsyncHcsCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$AsyncOperation@X@Csl@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4AsyncHcsCall@12345@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `851`
- prototype: `__int64 __fastcall(int, int, int, int, PCWSTR options)`
- caller_count: `7`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180123ce8`
- `0x18012475c`
- `0x180124c00`
- `0x180124df0`
- `0x180124ed8`
- `0x180182010`
- `0x1801820b0`

## callees

- `0x180004fc4`
- `0x18003dbf8`
- `0x18003de70`
- `0x18003f7d8`
- `0x1800471dc`
- `0x1800491e8`
- `0x180050510`
- `0x180053ea0`
- `0x1801735f0`
- `0x18017fcf0`
- `0x180180c74`
- `0x180182288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180180e5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180180e5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180e90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180eb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180d27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180e90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180180eb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180180e7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180e9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180d35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180180e9e`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x180180d8d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsTerminateComputeSystem` at `0x180180d8d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsStartComputeSystem` at `0x180180e47`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsStartComputeSystem` at `0x180180e47`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsShutDownComputeSystem` at `0x180180da8`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsShutDownComputeSystem` at `0x180180da8`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSaveComputeSystem` at `0x180180df3`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSaveComputeSystem` at `0x180180df3`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsResumeComputeSystem` at `0x180180e0b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsResumeComputeSystem` at `0x180180e0b`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180180f74`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180180f74`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsPauseComputeSystem` at `0x180180e2f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsPauseComputeSystem` at `0x180180e2f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCrashComputeSystem` at `0x180180dcf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCrashComputeSystem` at `0x180180dcf`

## string_xrefs

- `0x180180faf`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::InitiateAsyncHcsCall(
        __int64 a1,
        _QWORD *a2,
        char *a3,
        int a4,
        WCHAR *options)
{
  __int64 v9; // rax
  HCS_OPERATION v10; // r12
  HCS_OPERATION v11; // rbx
  RTL_SRWLOCK *v12; // rdi
  DWORD LastError; // ebx
  int v14; // edi
  HRESULT started; // eax
  WCHAR *v16; // r8
  const WCHAR *v17; // r8
  const WCHAR *v18; // r8
  DWORD v19; // ebx
  HCS_OPERATION v20; // rbx
  utl::_RefCountBase *v21; // rcx
  utl::_RefCountBase *v22; // r15
  char v24; // [rsp+28h] [rbp-48h] BYREF
  HCS_OPERATION v25; // [rsp+30h] [rbp-40h]
  utl::_RefCountBase *v26; // [rsp+38h] [rbp-38h]
  utl::_RefCountBase *v27; // [rsp+40h] [rbp-30h]
  HCS_OPERATION operation; // [rsp+48h] [rbp-28h] BYREF
  utl::_RefCountBase *v29[2]; // [rsp+50h] [rbp-20h]
  char v30; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  RTL_SRWLOCK *SRWLock; // [rsp+B0h] [rbp+40h]

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v9 = Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(a1, &operation);
  v10 = *(HCS_OPERATION *)(v9 + 24);
  Csl::AsyncOperation<void>::operator=(a2, v9);
  Csl::AsyncOperation<void>::Cleanup(&operation);
  if ( v29[1] )
    utl::_RefCountBase::_DecStrong(v29[1]);
  v11 = operation;
  operation = 0;
  if ( v11 )
  {
    Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(v11);
    operator delete(v11, (const struct std::nothrow_t *)0x30);
  }
  v12 = *(RTL_SRWLOCK **)a3;
  if ( *(_QWORD *)a3 )
  {
    LastError = GetLastError();
    ReleaseSRWLockExclusive(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)a3 = 0;
  if ( a4 )
  {
    switch ( a4 )
    {
      case 1:
        if ( *((_QWORD *)options + 3) <= 7u )
          v18 = options;
        else
          v18 = *(const WCHAR **)options;
        started = HcsPauseComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, v18);
        break;
      case 2:
        started = HcsResumeComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      case 3:
        if ( *((_QWORD *)options + 3) <= 7u )
          v17 = options;
        else
          v17 = *(const WCHAR **)options;
        started = HcsSaveComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, v17);
        break;
      case 4:
        if ( *((_QWORD *)options + 3) <= 7u )
          v16 = options;
        else
          v16 = *(WCHAR **)options;
        started = HcsCrashComputeSystem(*(_QWORD *)(a1 + 24), v10, v16);
        break;
      case 5:
        started = HcsShutDownComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      case 6:
        started = HcsTerminateComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
        break;
      default:
        v14 = -2147418113;
        goto LABEL_32;
    }
  }
  else
  {
    started = HcsStartComputeSystem(*(HCS_SYSTEM *)(a1 + 24), v10, 0);
  }
  v14 = started;
LABEL_32:
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  if ( a3 == &v24 )
  {
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
  else
  {
    SRWLock = *(RTL_SRWLOCK **)a3;
    if ( *(_QWORD *)a3 )
    {
      v19 = GetLastError();
      ReleaseSRWLockExclusive(SRWLock);
      SetLastError(v19);
    }
    *(_QWORD *)a3 = a1 + 32;
  }
  if ( v14 < 0 )
  {
    Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(a1, &operation, v10);
    if ( !v30 )
      std::_Throw_bad_optional_access();
    v20 = operation;
    v25 = operation;
    operation = 0;
    v21 = v29[0];
    v26 = v29[0];
    v22 = v29[1];
    v27 = v29[1];
    *(_OWORD *)v29 = 0;
    if ( a4 == 6 )
    {
      if ( v14 == -2143878896 )
      {
        v14 = 0;
        Csl::CompletionEvent<void>::CompleteInternal(v21, 0);
      }
    }
    else if ( *(_DWORD *)(a1 + 44) )
    {
      v14 = -2143878905;
    }
    else if ( v14 == -2143878896 && a4 != 5 )
    {
      v14 = -2143878906;
    }
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)(unsigned int)v14,
        3);
    if ( v22 )
      utl::_RefCountBase::_DecStrong(v22);
    if ( v20 )
      HcsCloseOperation(v20);
  }
  if ( *((_BYTE *)options + 32) )
    std::wstring::~wstring(options);
  return a2;
}

```

## disassembly

```asm
0x180180c74  mov     [rsp-38h+arg_10], rbx
0x180180c79  mov     [rsp-38h+arg_18], r9d
0x180180c7e  mov     [rsp-38h+arg_8], rdx
0x180180c83  push    rbp
0x180180c84  push    rsi
0x180180c85  push    rdi
0x180180c86  push    r12
0x180180c88  push    r13
0x180180c8a  push    r14
0x180180c8c  push    r15
0x180180c8e  mov     rbp, rsp
0x180180c91  sub     rsp, 70h
0x180180c95  mov     esi, r9d
0x180180c98  mov     r13, r8
0x180180c9b  mov     rbx, rdx
0x180180c9e  mov     r14, rcx
0x180180ca1  xor     r15d, r15d
0x180180ca4  mov     [rbp+var_50], r15d
0x180180ca8  mov     [rdx], r15
0x180180cab  mov     [rdx+8], r15
0x180180caf  mov     [rdx+10h], r15
0x180180cb3  mov     [rbp+var_50], 1
0x180180cba  lea     rdx, [rbp+operation]
0x180180cbe  call    ?CreateOperationsForAsyncCall@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$tuple@PEAUHCS_OPERATION__@@V?$AsyncOperation@X@Csl@@@std@@XZ; Container::Manager::Hcs::Details::ComputeSystemImpl::CreateOperationsForAsyncCall(void)
0x180180cc3  mov     r12, [rax+18h]
0x180180cc7  mov     rdx, rax
0x180180cca  mov     rcx, rbx
0x180180ccd  call    ??4?$AsyncOperation@X@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::AsyncOperation<void>::operator=(Csl::AsyncOperation<void> &&)
0x180180cd2  lea     rcx, [rbp+operation]
0x180180cd6  call    ?Cleanup@?$AsyncOperation@X@Csl@@AEAAXXZ; Csl::AsyncOperation<void>::Cleanup(void)
0x180180cdb  nop
0x180180cdc  mov     rcx, [rbp+var_20+8]; this
0x180180ce0  test    rcx, rcx
0x180180ce3  jz      short loc_180180CEB
0x180180ce5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180180cea  nop
0x180180ceb  mov     rbx, [rbp+operation]
0x180180cef  mov     [rbp+operation], r15
0x180180cf3  test    rbx, rbx
0x180180cf6  jz      short loc_180180D0D
0x180180cf8  mov     rcx, rbx
0x180180cfb  call    ??1?$AsyncOperationImpl@X@Details@Csl@@QEAA@XZ; Csl::Details::AsyncOperationImpl<void>::~AsyncOperationImpl<void>(void)
0x180180d00  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180180d05  mov     rcx, rbx; void *
0x180180d08  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180180d0d  mov     rdi, [r13+0]
0x180180d11  test    rdi, rdi
0x180180d14  jz      short loc_180180D41
0x180180d16  call    cs:__imp_GetLastError
0x180180d1d  nop     dword ptr [rax+rax+00h]
0x180180d22  mov     ebx, eax
0x180180d24  mov     rcx, rdi; SRWLock
0x180180d27  call    cs:__imp_ReleaseSRWLockExclusive
0x180180d2e  nop     dword ptr [rax+rax+00h]
0x180180d33  mov     ecx, ebx; dwErrCode
0x180180d35  call    cs:__imp_SetLastError
0x180180d3c  nop     dword ptr [rax+rax+00h]
0x180180d41  mov     [r13+0], r15
0x180180d45  mov     ecx, esi
0x180180d47  mov     rsi, [rbp+options]
0x180180d4b  test    ecx, ecx
0x180180d4d  jz      loc_180180E3D
0x180180d53  sub     ecx, 1
0x180180d56  jz      loc_180180E19
0x180180d5c  sub     ecx, 1
0x180180d5f  jz      loc_180180E01
0x180180d65  sub     ecx, 1
0x180180d68  jz      short loc_180180DDD
0x180180d6a  sub     ecx, 1
0x180180d6d  jz      short loc_180180DB9
0x180180d6f  sub     ecx, 1
0x180180d72  jz      short loc_180180D9E
0x180180d74  cmp     ecx, 1
0x180180d77  jz      short loc_180180D83
0x180180d79  mov     edi, 8000FFFFh
0x180180d7e  jmp     loc_180180E55
0x180180d83  xor     r8d, r8d; options
0x180180d86  mov     rdx, r12; operation
0x180180d89  mov     rcx, [r14+18h]; computeSystem
0x180180d8d  call    cs:__imp_HcsTerminateComputeSystem
0x180180d94  nop     dword ptr [rax+rax+00h]
0x180180d99  jmp     loc_180180E53
0x180180d9e  xor     r8d, r8d; options
0x180180da1  mov     rdx, r12; operation
0x180180da4  mov     rcx, [r14+18h]; computeSystem
0x180180da8  call    cs:__imp_HcsShutDownComputeSystem
0x180180daf  nop     dword ptr [rax+rax+00h]
0x180180db4  jmp     loc_180180E53
0x180180db9  cmp     qword ptr [rsi+18h], 7
0x180180dbe  jbe     short loc_180180DC5
0x180180dc0  mov     r8, [rsi]
0x180180dc3  jmp     short loc_180180DC8
0x180180dc5  mov     r8, rsi
0x180180dc8  mov     rdx, r12
0x180180dcb  mov     rcx, [r14+18h]
0x180180dcf  call    cs:__imp_HcsCrashComputeSystem
0x180180dd6  nop     dword ptr [rax+rax+00h]
0x180180ddb  jmp     short loc_180180E53
0x180180ddd  cmp     qword ptr [rsi+18h], 7
0x180180de2  jbe     short loc_180180DE9
0x180180de4  mov     r8, [rsi]
0x180180de7  jmp     short loc_180180DEC
0x180180de9  mov     r8, rsi; options
0x180180dec  mov     rdx, r12; operation
0x180180def  mov     rcx, [r14+18h]; computeSystem
0x180180df3  call    cs:__imp_HcsSaveComputeSystem
0x180180dfa  nop     dword ptr [rax+rax+00h]
0x180180dff  jmp     short loc_180180E53
0x180180e01  xor     r8d, r8d; options
0x180180e04  mov     rdx, r12; operation
0x180180e07  mov     rcx, [r14+18h]; computeSystem
0x180180e0b  call    cs:__imp_HcsResumeComputeSystem
0x180180e12  nop     dword ptr [rax+rax+00h]
0x180180e17  jmp     short loc_180180E53
0x180180e19  cmp     qword ptr [rsi+18h], 7
0x180180e1e  jbe     short loc_180180E25
0x180180e20  mov     r8, [rsi]
0x180180e23  jmp     short loc_180180E28
0x180180e25  mov     r8, rsi; options
0x180180e28  mov     rdx, r12; operation
0x180180e2b  mov     rcx, [r14+18h]; computeSystem
0x180180e2f  call    cs:__imp_HcsPauseComputeSystem
0x180180e36  nop     dword ptr [rax+rax+00h]
0x180180e3b  jmp     short loc_180180E53
0x180180e3d  xor     r8d, r8d; options
0x180180e40  mov     rdx, r12; operation
0x180180e43  mov     rcx, [r14+18h]; computeSystem
0x180180e47  call    cs:__imp_HcsStartComputeSystem
0x180180e4e  nop     dword ptr [rax+rax+00h]
0x180180e53  mov     edi, eax
0x180180e55  lea     r15, [r14+20h]
0x180180e59  mov     rcx, r15; SRWLock
0x180180e5c  call    cs:__imp_AcquireSRWLockExclusive
0x180180e63  nop     dword ptr [rax+rax+00h]
0x180180e68  lea     rax, [rbp+var_48]
0x180180e6c  cmp     r13, rax
0x180180e6f  jz      short loc_180180EB0
0x180180e71  mov     rax, [r13+0]
0x180180e75  mov     [rbp+SRWLock], rax
0x180180e79  test    rax, rax
0x180180e7c  jz      short loc_180180EAA
0x180180e7e  call    cs:__imp_GetLastError
0x180180e85  nop     dword ptr [rax+rax+00h]
0x180180e8a  mov     ebx, eax
0x180180e8c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180180e90  call    cs:__imp_ReleaseSRWLockExclusive
0x180180e97  nop     dword ptr [rax+rax+00h]
0x180180e9c  mov     ecx, ebx; dwErrCode
0x180180e9e  call    cs:__imp_SetLastError
0x180180ea5  nop     dword ptr [rax+rax+00h]
0x180180eaa  mov     [r13+0], r15
0x180180eae  jmp     short loc_180180EC4
0x180180eb0  test    r15, r15
0x180180eb3  jz      short loc_180180EC4
0x180180eb5  mov     rcx, r15; SRWLock
0x180180eb8  call    cs:__imp_ReleaseSRWLockExclusive
0x180180ebf  nop     dword ptr [rax+rax+00h]
0x180180ec4  test    edi, edi
0x180180ec6  jns     loc_180180F81
0x180180ecc  mov     r8, r12
0x180180ecf  lea     rdx, [rbp+operation]
0x180180ed3  mov     rcx, r14
0x180180ed6  call    ?TryRemoveContextForOperation@ComputeSystemImpl@Details@Hcs@Manager@Container@@AEAA?AV?$optional@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAUHCS_OPERATION__@@@Z; Container::Manager::Hcs::Details::ComputeSystemImpl::TryRemoveContextForOperation(HCS_OPERATION__ *)
0x180180edb  nop
0x180180edc  cmp     [rbp+var_10], 0
0x180180ee0  jz      loc_180180FC1
0x180180ee6  mov     rbx, [rbp+operation]
0x180180eea  mov     [rbp+var_40], rbx
0x180180eee  mov     [rbp+operation], 0
0x180180ef6  mov     rcx, [rbp+var_20]
0x180180efa  mov     [rbp+var_38], rcx
0x180180efe  mov     r15, [rbp+var_20+8]
0x180180f02  mov     [rbp+var_30], r15
0x180180f06  xorps   xmm0, xmm0
0x180180f09  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180180f0e  mov     [rbp+var_50], 3
0x180180f15  mov     eax, [rbp+arg_18]
0x180180f18  cmp     eax, 6
0x180180f1b  jnz     short loc_180180F30
0x180180f1d  cmp     edi, 80370110h
0x180180f23  jnz     short loc_180180F4F
0x180180f25  xor     edi, edi
0x180180f27  xor     edx, edx
0x180180f29  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x180180f2e  jmp     short loc_180180F4F
0x180180f30  cmp     dword ptr [r14+2Ch], 0
0x180180f35  jbe     short loc_180180F3E
0x180180f37  mov     edi, 80370107h
0x180180f3c  jmp     short loc_180180F4F
0x180180f3e  cmp     edi, 80370110h
0x180180f44  jnz     short loc_180180F4F
0x180180f46  lea     ecx, [rdi-0Ah]
0x180180f49  cmp     eax, 5
0x180180f4c  cmovnz  edi, ecx
0x180180f4f  mov     rcx, [rbp+38h]; this
0x180180f53  test    edi, edi
0x180180f55  js      short loc_180180FAC
0x180180f57  mov     [rbp+var_50], 1
0x180180f5e  test    r15, r15
0x180180f61  jz      short loc_180180F6C
0x180180f63  mov     rcx, r15; this
0x180180f66  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180180f6b  nop
0x180180f6c  test    rbx, rbx
0x180180f6f  jz      short loc_180180F81
0x180180f71  mov     rcx, rbx; operation
0x180180f74  call    cs:__imp_HcsCloseOperation
0x180180f7b  nop     dword ptr [rax+rax+00h]
0x180180f80  nop
0x180180f81  cmp     byte ptr [rsi+20h], 0
0x180180f85  jz      short loc_180180F8F
0x180180f87  mov     rcx, rsi; void *
0x180180f8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180180f8f  mov     rax, [rbp+arg_8]
0x180180f93  mov     rbx, [rsp+70h+arg_10]
0x180180f9b  add     rsp, 70h
0x180180f9f  pop     r15
0x180180fa1  pop     r14
0x180180fa3  pop     r13
0x180180fa5  pop     r12
0x180180fa7  pop     rdi
0x180180fa8  pop     rsi
0x180180fa9  pop     rbp
0x180180faa  retn
0x180180fac  mov     r9d, edi; char *
0x180180faf  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180180fb6  mov     edx, 58Fh; void *
0x180180fbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180180fc1  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
