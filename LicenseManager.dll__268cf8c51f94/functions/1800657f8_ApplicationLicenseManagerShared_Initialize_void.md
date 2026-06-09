# ApplicationLicenseManagerShared::Initialize(void)

- ea: `0x1800657f8`
- end: `0x18006589b`
- name: `?Initialize@ApplicationLicenseManagerShared@@QEAAXXZ`
- size: `163`
- prototype: `void(ApplicationLicenseManagerShared *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006547c`

## callees

- `0x1800593bc`
- `0x1800657f8`
- `0x1800658a4`
- `0x180065908`
- `0x180076e64`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006580c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006580c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065894`
- `ext-ms-win-core-licensemanager-l1-1-0!CreateApplicationLicenseManager` at `0x18006582e`
- `ext-ms-win-core-licensemanager-l1-1-0!CreateApplicationLicenseManager` at `0x18006582e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ApplicationLicenseManagerShared::Initialize(ApplicationLicenseManagerShared *this)
{
  __int64 v1; // rcx
  int ApplicationLicenseManager; // eax
  __int64 v3; // rax
  ApplicationLicenseManagerShared *v4; // rcx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ApplicationLicenseManagerShared *v7; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+38h] [rbp+10h]

  v7 = this;
  EnterCriticalSection(&g_shared);
  v8 = &g_shared;
  if ( (unsigned __int8)IsCompareContentIdPresent(v1) )
  {
    ApplicationLicenseManager = CreateApplicationLicenseManager(
                                  &GUID_90e2000c_b946_42fa_892f_94506f30ca4f,
                                  &qword_1800F2AC8);
    if ( ApplicationLicenseManager < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\applicensemanager.cpp",
        (const char *)(unsigned int)ApplicationLicenseManager,
        v5);
  }
  else
  {
    v3 = CreateOneStoreApplicationLicenseManager(&v7);
    Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(&qword_1800F2AC8, v3);
    v4 = v7;
    if ( v7 )
    {
      v7 = 0;
      (*(void (__fastcall **)(ApplicationLicenseManagerShared *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  LeaveCriticalSection(&g_shared);
}

```

## disassembly

```asm
0x1800657f8  mov     [rsp+arg_0], rcx
0x1800657fd  push    rbx; int
0x1800657fe  sub     rsp, 20h
0x180065802  lea     rbx, ?g_shared@@3VApplicationLicenseManagerShared@@A; ApplicationLicenseManagerShared g_shared
0x180065809  mov     rcx, rbx; lpCriticalSection
0x18006580c  call    cs:__imp_EnterCriticalSection
0x180065812  mov     [rsp+28h+arg_8], rbx
0x180065817  call    IsCompareContentIdPresent
0x18006581c  test    al, al
0x18006581e  jz      short loc_180065852
0x180065820  lea     rdx, qword_1800F2AC8
0x180065827  lea     rcx, _GUID_90e2000c_b946_42fa_892f_94506f30ca4f
0x18006582e  call    cs:__imp_CreateApplicationLicenseManager
0x180065834  mov     rcx, [rsp+28h]; this
0x180065839  test    eax, eax
0x18006583b  jns     short loc_18006588C
0x18006583d  mov     r9d, eax; char *
0x180065840  lea     r8, aOnecoreuapEndu_33; "onecoreuap\\enduser\\winstore\\licensem"...
0x180065847  mov     edx, 69h ; 'i'; void *
0x18006584c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065852  lea     rcx, [rsp+28h+arg_0]
0x180065857  call    ?CreateOneStoreApplicationLicenseManager@@YA?AV?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; CreateOneStoreApplicationLicenseManager(IServiceProvider *)
0x18006585c  mov     rdx, rax
0x18006585f  lea     rcx, qword_1800F2AC8
0x180065866  call    ??4?$ComPtr@UILicenseIdentityInternal@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseIdentityInternal>::operator=(Microsoft::WRL::ComPtr<ILicenseIdentityInternal> &&)
0x18006586b  nop
0x18006586c  mov     rcx, [rsp+28h+arg_0]
0x180065871  test    rcx, rcx
0x180065874  jz      short loc_18006588C
0x180065876  mov     [rsp+28h+arg_0], 0
0x18006587f  mov     rax, [rcx]
0x180065882  mov     rax, [rax+10h]
0x180065886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006588b  nop
0x18006588c  mov     rcx, rbx
0x18006588f  add     rsp, 20h
0x180065893  pop     rbx
0x180065894  jmp     cs:__imp_LeaveCriticalSection
```
