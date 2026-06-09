# ShieldProvider::ShieldImpersonateWcosGuest(void)

- ea: `0x1800d356c`
- end: `0x1800d374a`
- name: `?ShieldImpersonateWcosGuest@ShieldProvider@@YAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d412c`

## callees

- `0x1800071fc`
- `0x18000787c`
- `0x18000a7cc`
- `0x18000a7ec`
- `0x1800d1ddc`
- `0x1800d1e00`
- `0x1800d356c`
- `0x1800d8874`
- `0x1800d8910`
- `0x1800d89ac`
- `0x1800d8a98`
- `0x1800d8b38`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800d3674`
- `KERNEL32!CloseHandle` at `0x1800d36c5`
- `KERNEL32!CloseHandle` at `0x1800d3674`
- `KERNEL32!CloseHandle` at `0x1800d36c5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d3713`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d3713`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800d36e9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800d36e9`

## string_xrefs

- `0x1800d35e7`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderserviceutil.cpp`
- `0x1800d3637`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderserviceutil.cpp`
- `0x1800d36fc`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderserviceutil.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldImpersonateWcosGuest(ShieldProvider *this)
{
  unsigned int LastError; // ebx
  __int64 v2; // rdx
  __int64 v3; // r9
  _QWORD *v4; // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  HANDLE v8; // rbx
  int v9; // eax
  HANDLE v10; // rbx
  const char *v11; // r9
  __int64 v12; // rdx
  int v14[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  int v16; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+20h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+60h] [rbp+28h] BYREF
  _QWORD *v19; // [rsp+68h] [rbp+30h] BYREF

  v19 = 0;
  v16 = 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(this) )
  {
    v4 = v19;
    if ( v19 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v14);
      UMgrFreeSessionUsers(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
    }
    v19 = 0;
    v5 = UMgrEnumerateSessionUsers(&v16, &v19);
    LastError = v5;
    if ( v5 < 0 )
    {
      v3 = (unsigned int)v5;
      v2 = 313;
      goto LABEL_7;
    }
    if ( !v16 )
    {
      LastError = -2147418113;
      v2 = 314;
      v3 = 2147549183LL;
      goto LABEL_7;
    }
    DuplicateTokenHandle = 0;
    hObject = 0;
    if ( (unsigned __int8)IsUMgrQueryUserTokenPresent() )
    {
      v8 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v14);
        CloseHandle(v8);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
      }
      hObject = 0;
      v9 = UMgrQueryUserToken(*v19, &hObject);
      LastError = v9;
      if ( v9 >= 0 )
      {
        v10 = DuplicateTokenHandle;
        if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v14);
          CloseHandle(v10);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
        }
        DuplicateTokenHandle = 0;
        if ( DuplicateToken(hObject, SecurityImpersonation, &DuplicateTokenHandle) )
        {
          if ( ImpersonateLoggedOnUser(DuplicateTokenHandle) )
          {
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
            LastError = 0;
            goto LABEL_26;
          }
          v12 = 322;
        }
        else
        {
          v12 = 321;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v12,
                      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldu"
                                    "til\\shieldproviderserviceutil.cpp",
                      v11);
        goto LABEL_13;
      }
      v7 = (unsigned int)v9;
      v6 = 319;
    }
    else
    {
      LastError = -2147467263;
      v6 = 318;
      v7 = 2147500033LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldprovi"
                    "derserviceutil.cpp",
      (const char *)v7,
      v14[0]);
LABEL_13:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
    goto LABEL_26;
  }
  LastError = -2147467263;
  v2 = 312;
  v3 = 2147500033LL;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\shieldutil\\shieldprovide"
                  "rserviceutil.cpp",
    (const char *)v3,
    v14[0]);
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v19);
  return LastError;
}

```

## disassembly

```asm
0x1800d356c  push    rbp
0x1800d356e  push    rbx
0x1800d356f  mov     rbp, rsp
0x1800d3572  sub     rsp, 38h
0x1800d3576  mov     [rbp+arg_18], 0
0x1800d357e  mov     [rbp+arg_0], 0
0x1800d3585  call    IsUMgrEnumerateSessionUsersPresent
0x1800d358a  test    al, al
0x1800d358c  jnz     short loc_1800D359D
0x1800d358e  mov     ebx, 80004001h
0x1800d3593  mov     edx, 138h
0x1800d3598  mov     r9d, ebx
0x1800d359b  jmp     short loc_1800D35E3
0x1800d359d  mov     rbx, [rbp+arg_18]
0x1800d35a1  test    rbx, rbx
0x1800d35a4  jz      short loc_1800D35C0
0x1800d35a6  lea     rcx, [rbp+var_18]; this
0x1800d35aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800d35af  mov     rcx, rbx
0x1800d35b2  call    UMgrFreeSessionUsers
0x1800d35b7  lea     rcx, [rbp+var_18]; this
0x1800d35bb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800d35c0  lea     rdx, [rbp+arg_18]
0x1800d35c4  mov     [rbp+arg_18], 0
0x1800d35cc  lea     rcx, [rbp+arg_0]
0x1800d35d0  call    UMgrEnumerateSessionUsers
0x1800d35d5  mov     ebx, eax
0x1800d35d7  test    eax, eax
0x1800d35d9  jns     short loc_1800D35F8
0x1800d35db  mov     r9d, eax; char *
0x1800d35de  mov     edx, 139h; void *
0x1800d35e3  mov     rcx, [rbp+10h]; this
0x1800d35e7  lea     r8, aOnecoreAmcoreA_1; "onecore\\amcore\\antimalware\\source\\s"...
0x1800d35ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d35f3  jmp     loc_1800D3738
0x1800d35f8  cmp     [rbp+arg_0], 0
0x1800d35fc  jnz     short loc_1800D360D
0x1800d35fe  mov     ebx, 8000FFFFh
0x1800d3603  mov     edx, 13Ah
0x1800d3608  mov     r9d, ebx
0x1800d360b  jmp     short loc_1800D35E3
0x1800d360d  mov     [rbp+DuplicateTokenHandle], 0
0x1800d3615  mov     [rbp+hObject], 0
0x1800d361d  call    IsUMgrQueryUserTokenPresent
0x1800d3622  test    al, al
0x1800d3624  jnz     short loc_1800D365A
0x1800d3626  mov     ebx, 80004001h
0x1800d362b  mov     edx, 13Eh; void *
0x1800d3630  mov     r9d, ebx; char *
0x1800d3633  mov     rcx, [rbp+10h]; this
0x1800d3637  lea     r8, aOnecoreAmcoreA_1; "onecore\\amcore\\antimalware\\source\\s"...
0x1800d363e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d3643  lea     rcx, [rbp+hObject]
0x1800d3647  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d364c  lea     rcx, [rbp+DuplicateTokenHandle]
0x1800d3650  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d3655  jmp     loc_1800D3738
0x1800d365a  mov     rbx, [rbp+hObject]
0x1800d365e  lea     rax, [rbx-1]
0x1800d3662  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d3666  ja      short loc_1800D3683
0x1800d3668  lea     rcx, [rbp+var_18]; this
0x1800d366c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800d3671  mov     rcx, rbx; hObject
0x1800d3674  call    cs:__imp_CloseHandle
0x1800d367a  lea     rcx, [rbp+var_18]; this
0x1800d367e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800d3683  mov     rcx, [rbp+arg_18]
0x1800d3687  lea     rdx, [rbp+hObject]
0x1800d368b  mov     [rbp+hObject], 0
0x1800d3693  mov     rcx, [rcx]
0x1800d3696  call    UMgrQueryUserToken
0x1800d369b  mov     ebx, eax
0x1800d369d  test    eax, eax
0x1800d369f  jns     short loc_1800D36AB
0x1800d36a1  mov     r9d, eax
0x1800d36a4  mov     edx, 13Fh
0x1800d36a9  jmp     short loc_1800D3633
0x1800d36ab  mov     rbx, [rbp+DuplicateTokenHandle]
0x1800d36af  lea     rax, [rbx-1]
0x1800d36b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800d36b7  ja      short loc_1800D36D4
0x1800d36b9  lea     rcx, [rbp+var_18]; this
0x1800d36bd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800d36c2  mov     rcx, rbx; hObject
0x1800d36c5  call    cs:__imp_CloseHandle
0x1800d36cb  lea     rcx, [rbp+var_18]; this
0x1800d36cf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800d36d4  mov     rcx, [rbp+hObject]; ExistingTokenHandle
0x1800d36d8  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800d36dc  mov     edx, 2; ImpersonationLevel
0x1800d36e1  mov     [rbp+DuplicateTokenHandle], 0
0x1800d36e9  call    cs:__imp_DuplicateToken
0x1800d36ef  test    eax, eax
0x1800d36f1  jnz     short loc_1800D370F
0x1800d36f3  mov     edx, 141h; void *
0x1800d36f8  mov     rcx, [rbp+10h]; this
0x1800d36fc  lea     r8, aOnecoreAmcoreA_1; "onecore\\amcore\\antimalware\\source\\s"...
0x1800d3703  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d3708  mov     ebx, eax
0x1800d370a  jmp     loc_1800D3643
0x1800d370f  mov     rcx, [rbp+DuplicateTokenHandle]; hToken
0x1800d3713  call    cs:__imp_ImpersonateLoggedOnUser
0x1800d3719  test    eax, eax
0x1800d371b  jnz     short loc_1800D3724
0x1800d371d  mov     edx, 142h
0x1800d3722  jmp     short loc_1800D36F8
0x1800d3724  lea     rcx, [rbp+hObject]
0x1800d3728  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d372d  lea     rcx, [rbp+DuplicateTokenHandle]
0x1800d3731  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d3736  xor     ebx, ebx
0x1800d3738  lea     rcx, [rbp+arg_18]
0x1800d373c  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x1800d3741  mov     eax, ebx
0x1800d3743  add     rsp, 38h
0x1800d3747  pop     rbx
0x1800d3748  pop     rbp
0x1800d3749  retn
```
