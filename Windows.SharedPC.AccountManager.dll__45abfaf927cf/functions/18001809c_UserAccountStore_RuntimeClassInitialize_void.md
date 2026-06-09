# UserAccountStore::RuntimeClassInitialize(void)

- ea: `0x18001809c`
- end: `0x180018187`
- name: `?RuntimeClassInitialize@UserAccountStore@@QEAAJXZ`
- size: `235`
- prototype: `__int64 __fastcall(UserAccountStore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f03c`

## callees

- `0x180006e2c`
- `0x180007328`
- `0x18000a5c4`
- `0x18000ccd4`
- `0x180014360`
- `0x180017a30`
- `0x18001809c`
- `0x1800198d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018150`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018150`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180018126`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180018126`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800180ff`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800180ff`

## string_xrefs

- `0x1800180c3`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180018138`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserAccountStore::RuntimeClassInitialize(RTL_SRWLOCK *this)
{
  int v2; // eax
  PVOID Ptr; // rsi
  NTSTATUS v4; // eax
  const char *v5; // r9
  __int64 result; // rax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+60h] [rbp+8h] BYREF

  v2 = Microsoft::WRL::Details::MakeAndInitialize<LocalAccountController,ILocalAccountController,>((__int64)&this[11]);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x30,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v2,
        ObjectAttributes.Length);
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    Ptr = this[10].Ptr;
    if ( Ptr )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
      LsaClose(Ptr);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
    }
    this[10].Ptr = 0;
    v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &this[10].Ptr);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x34,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v4,
        ObjectAttributes.Length);
    AcquireSRWLockExclusive(this + 6);
    v9 = this + 6;
    UserAccountStore::ReconcileAccounts((UserAccountStore *)this);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v9) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x3F,
                    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
                    v5);
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x18001809c  mov     [rsp+arg_8], rbx
0x1800180a1  mov     [rsp+arg_10], rsi
0x1800180a6  push    rdi
0x1800180a7  sub     rsp, 50h
0x1800180ab  mov     rdi, rcx
0x1800180ae  add     rcx, 58h ; 'X'
0x1800180b2  call    ??$MakeAndInitialize@VLocalAccountController@@UILocalAccountController@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UILocalAccountController@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<LocalAccountController,ILocalAccountController,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ILocalAccountController>>)
0x1800180b7  mov     rcx, [rsp+58h]; this
0x1800180bc  test    eax, eax
0x1800180be  jns     short loc_1800180D4
0x1800180c0  mov     r9d, eax; char *
0x1800180c3  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800180ca  mov     edx, 30h ; '0'; void *
0x1800180cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800180d4  xorps   xmm0, xmm0
0x1800180d7  movups  xmmword ptr [rsp+58h+ObjectAttributes.Length], xmm0; int
0x1800180dc  movups  xmmword ptr [rsp+58h+ObjectAttributes.ObjectName], xmm0
0x1800180e1  movups  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800180e6  lea     rbx, [rdi+50h]
0x1800180ea  mov     rsi, [rbx]
0x1800180ed  test    rsi, rsi
0x1800180f0  jz      short loc_18001810F
0x1800180f2  lea     rcx, [rsp+58h+arg_0]; this
0x1800180f7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800180fc  mov     rcx, rsi; ObjectHandle
0x1800180ff  call    cs:__imp_LsaClose
0x180018105  lea     rcx, [rsp+58h+arg_0]; this
0x18001810a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001810f  mov     qword ptr [rbx], 0
0x180018116  mov     r9, rbx; PolicyHandle
0x180018119  mov     r8d, 801h; DesiredAccess
0x18001811f  lea     rdx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x180018124  xor     ecx, ecx; SystemName
0x180018126  call    cs:__imp_LsaOpenPolicy
0x18001812c  mov     rcx, [rsp+58h]; this
0x180018131  test    eax, eax
0x180018133  jns     short loc_180018149
0x180018135  mov     r9d, eax; char *
0x180018138  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001813f  mov     edx, 34h ; '4'; void *
0x180018144  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180018149  lea     rbx, [rdi+30h]
0x18001814d  mov     rcx, rbx; SRWLock
0x180018150  call    cs:__imp_AcquireSRWLockExclusive
0x180018156  mov     [rsp+58h+arg_0], rbx
0x18001815b  mov     rcx, rdi; this
0x18001815e  call    ?ReconcileAccounts@UserAccountStore@@AEAAXXZ; UserAccountStore::ReconcileAccounts(void)
0x180018163  nop
0x180018164  lea     rcx, [rsp+58h+arg_0]
0x180018169  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001816e  xor     eax, eax
0x180018170  jmp     short loc_180018176
0x180018172  mov     eax, dword ptr [rsp+58h+arg_0]
0x180018176  mov     rbx, [rsp+58h+arg_8]
0x18001817b  mov     rsi, [rsp+58h+arg_10]
0x180018180  add     rsp, 50h
0x180018184  pop     rdi
0x180018185  retn
```
