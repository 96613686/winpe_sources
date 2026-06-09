# OSIntegration::Tools::AppContainerImpersonate::DoImpersonation(OSIntegration::Package const *)

- ea: `0x18006c4cc`
- end: `0x18006c809`
- name: `?DoImpersonation@AppContainerImpersonate@Tools@OSIntegration@@QEAAJPEBVPackage@3@@Z`
- size: `829`
- prototype: `__int64 __fastcall(OSIntegration::Tools::AppContainerImpersonate *__hidden this, const struct OSIntegration::Package *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a0250`
- `0x1800a3720`
- `0x18013b9c0`

## callees

- `0x18006c4cc`
- `0x18006cb78`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a5970`
- `0x1800baaac`
- `0x1800cdc08`
- `0x1800ce12c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c595`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c587`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c5e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c587`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c5d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c72f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c7d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c7e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c72f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c7d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c7e6`
- `ntdll!NtCreateLowBoxToken` at `0x18006c6ea`
- `ntdll!NtCreateLowBoxToken` at `0x18006c6ea`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c74a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006c74a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006c5b0`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18006c5b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c5f4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006c5f4`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x18006c641`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x18006c641`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c532`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c662`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c682`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c71b`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c776`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c7be`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c532`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c662`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c682`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c71b`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c776`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x18006c7be`

## string_xrefs

- `0x18006c50d`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`
- `0x18006c607`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`
- `0x18006c6f8`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`
- `0x18006c75b`: `onecore\admin\appmodel\OSIM\src\deh\appx\Common\AppContainerImpersonate.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OSIntegration::Tools::AppContainerImpersonate::DoImpersonation(
        OSIntegration::Tools::AppContainerImpersonate *this,
        const struct OSIntegration::Package *a2)
{
  bool v3; // zf
  int LastError; // ebx
  __int64 v6; // rcx
  HANDLE v7; // rcx
  bool v8; // cc
  int v10; // esi
  HANDLE CurrentThread; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  HANDLE v14; // rax
  Common *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r14
  HANDLE v21; // r12
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  char *v26; // rcx
  __int64 v27; // rax
  int v28; // [rsp+20h] [rbp-60h]
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp-28h] BYREF
  __int64 *v31; // [rsp+60h] [rbp-20h]
  __int64 v32; // [rsp+68h] [rbp-18h] BYREF
  char v33; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v35; // [rsp+C0h] [rbp+40h] BYREF
  int v36; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v37; // [rsp+D8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)this == -1;
  hToken = 0;
  hObject = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  if ( !v3 )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
      (const char *)0x8000FFFFLL,
      v28);
    v6 = v37;
    v37 = 0;
    if ( v6 )
      AppXFreeMemory(v6);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v7 = hToken;
    v8 = (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_7:
    if ( v8 )
      CloseHandle(v7);
    return (unsigned int)LastError;
  }
  v10 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &hObject) )
  {
    if ( GetLastError() != 1008 )
    {
      v13 = 61;
LABEL_40:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
                    v12);
LABEL_41:
      v25 = v37;
      v37 = 0;
      if ( v25 )
        AppXFreeMemory(v25);
LABEL_43:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      return (unsigned int)LastError;
    }
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      v13 = 63;
      goto LABEL_40;
    }
    LastError = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hObject,
      0);
    v14 = GetCurrentThread();
    if ( !OpenThreadToken(v14, 0xEu, 1, &hObject) )
      LastError = Common::GetHResultFromLastError(v15);
    RevertToSelf();
    if ( LastError < 0 )
    {
      v16 = 77;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
        (const char *)(unsigned int)LastError,
        v28);
      goto LABEL_41;
    }
    v10 = 0;
  }
  v17 = *((_QWORD *)a2 + 28);
  v31 = &v37;
  v32 = 0;
  v33 = 1;
  LastError = AppXGetPackageCapabilities(v17, &v36, &v32, &v35);
  if ( v33 )
  {
    v18 = *v31;
    *v31 = v32;
    if ( v18 )
      ((void (*)(void))AppXFreeMemory)();
  }
  if ( LastError < 0 )
  {
    if ( LastError == -2147024444 )
    {
      v19 = v37;
      v37 = 0;
      if ( v19 )
        AppXFreeMemory(v19);
      LastError = -2147024444;
      goto LABEL_43;
    }
    v16 = 81;
    goto LABEL_19;
  }
  v20 = *((_QWORD *)a2 + 87);
  v21 = hObject;
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hToken);
  hToken = 0;
  v22 = NtCreateLowBoxToken(&hToken, v21, 14);
  if ( v22 < 0 )
  {
    v23 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecore\\admin\\appmodel\\OSIM\\src\\deh\\appx\\Common\\AppContainerImpersonate.hpp",
            (const char *)(unsigned int)v22,
            v20);
    v24 = v37;
    LastError = v23;
    v37 = 0;
    if ( v24 )
      AppXFreeMemory(v24);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v7 = hToken;
    v8 = (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_7;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v13 = 102;
    goto LABEL_40;
  }
  if ( v10 )
  {
    v26 = 0;
    *(_QWORD *)this = hObject;
    hObject = 0;
  }
  else
  {
    v26 = (char *)hObject;
    *(_QWORD *)this = 0;
  }
  v27 = v37;
  v37 = 0;
  if ( v27 )
  {
    AppXFreeMemory(v27);
    v26 = (char *)hObject;
  }
  if ( (unsigned __int64)(v26 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v26);
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hToken);
  return 0;
}

```

## disassembly

```asm
0x18006c4cc  mov     [rsp-38h+arg_8], rbx
0x18006c4d1  push    rbp
0x18006c4d2  push    rsi
0x18006c4d3  push    rdi
0x18006c4d4  push    r12
0x18006c4d6  push    r13
0x18006c4d8  push    r14
0x18006c4da  push    r15
0x18006c4dc  mov     rbp, rsp
0x18006c4df  sub     rsp, 80h
0x18006c4e6  xor     r13d, r13d
0x18006c4e9  mov     r14, rdx
0x18006c4ec  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18006c4f0  mov     rdi, rcx
0x18006c4f3  mov     [rbp+hToken], r13
0x18006c4f7  mov     [rbp+hObject], r13
0x18006c4fb  mov     [rbp+arg_18], r13
0x18006c4ff  mov     [rbp+arg_0], r13d
0x18006c503  mov     [rbp+arg_10], r13d
0x18006c507  jz      short loc_18006C567
0x18006c509  mov     rcx, [rbp+38h]; this
0x18006c50d  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18006c514  mov     ebx, 8000FFFFh
0x18006c519  lea     edx, [r13+2Dh]; void *
0x18006c51d  mov     r9d, ebx; char *
0x18006c520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c525  mov     rcx, [rbp+arg_18]
0x18006c529  mov     [rbp+arg_18], r13
0x18006c52d  test    rcx, rcx
0x18006c530  jz      short loc_18006C538
0x18006c532  call    cs:__imp_AppXFreeMemory
0x18006c538  mov     rcx, [rbp+hObject]; hObject
0x18006c53c  lea     rax, [rcx-1]
0x18006c540  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c544  ja      short loc_18006C54C
0x18006c546  call    cs:__imp_CloseHandle
0x18006c54c  mov     rcx, [rbp+hToken]; hObject
0x18006c550  lea     rdx, [rcx-1]
0x18006c554  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18006c558  ja      short loc_18006C560
0x18006c55a  call    cs:__imp_CloseHandle
0x18006c560  mov     eax, ebx
0x18006c562  jmp     loc_18006C7EE
0x18006c567  mov     r15d, 1
0x18006c56d  mov     esi, r15d
0x18006c570  call    cs:__imp_GetCurrentThread
0x18006c576  lea     r12d, [r15+0Dh]
0x18006c57a  mov     r8d, r15d; OpenAsSelf
0x18006c57d  mov     edx, r12d; DesiredAccess
0x18006c580  lea     r9, [rbp+hObject]; TokenHandle
0x18006c584  mov     rcx, rax; ThreadHandle
0x18006c587  call    cs:__imp_OpenThreadToken
0x18006c58d  test    eax, eax
0x18006c58f  jnz     loc_18006C61E
0x18006c595  call    cs:__imp_GetLastError
0x18006c59b  cmp     eax, 3F0h
0x18006c5a0  jz      short loc_18006C5AB
0x18006c5a2  lea     edx, [r15+3Ch]
0x18006c5a6  jmp     loc_18006C757
0x18006c5ab  mov     ecx, 2; ImpersonationLevel
0x18006c5b0  call    cs:__imp_ImpersonateSelf
0x18006c5b6  test    eax, eax
0x18006c5b8  jnz     short loc_18006C5C2
0x18006c5ba  lea     edx, [rax+3Fh]
0x18006c5bd  jmp     loc_18006C757
0x18006c5c2  xor     edx, edx
0x18006c5c4  lea     rcx, [rbp+hObject]
0x18006c5c8  mov     ebx, r13d
0x18006c5cb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006c5d0  call    cs:__imp_GetCurrentThread
0x18006c5d6  lea     r9, [rbp+hObject]; TokenHandle
0x18006c5da  mov     r8d, r15d; OpenAsSelf
0x18006c5dd  mov     rcx, rax; ThreadHandle
0x18006c5e0  mov     edx, r12d; DesiredAccess
0x18006c5e3  call    cs:__imp_OpenThreadToken
0x18006c5e9  test    eax, eax
0x18006c5eb  jnz     short loc_18006C5F4
0x18006c5ed  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x18006c5f2  mov     ebx, eax
0x18006c5f4  call    cs:__imp_RevertToSelf
0x18006c5fa  test    ebx, ebx
0x18006c5fc  jns     short loc_18006C61B
0x18006c5fe  mov     edx, 4Dh ; 'M'; void *
0x18006c603  mov     rcx, [rbp+38h]; this
0x18006c607  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18006c60e  mov     r9d, ebx; char *
0x18006c611  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c616  jmp     loc_18006C769
0x18006c61b  mov     esi, r13d
0x18006c61e  mov     rcx, [r14+0E0h]
0x18006c625  lea     rax, [rbp+arg_18]
0x18006c629  lea     r9, [rbp+arg_0]
0x18006c62d  mov     [rbp+var_20], rax
0x18006c631  lea     r8, [rbp+var_18]
0x18006c635  mov     [rbp+var_18], r13
0x18006c639  lea     rdx, [rbp+arg_10]
0x18006c63d  mov     [rbp+var_10], r15b
0x18006c641  call    cs:__imp_AppXGetPackageCapabilities
0x18006c647  mov     ebx, eax
0x18006c649  cmp     [rbp+var_10], r13b
0x18006c64d  jz      short loc_18006C668
0x18006c64f  mov     r8, [rbp+var_20]
0x18006c653  mov     rdx, [rbp+var_18]
0x18006c657  mov     rcx, [r8]
0x18006c65a  mov     [r8], rdx
0x18006c65d  test    rcx, rcx
0x18006c660  jz      short loc_18006C668
0x18006c662  call    cs:__imp_AppXFreeMemory
0x18006c668  test    ebx, ebx
0x18006c66a  jns     short loc_18006C699
0x18006c66c  mov     edi, 800701C4h
0x18006c671  cmp     ebx, edi
0x18006c673  jnz     short loc_18006C68F
0x18006c675  mov     rcx, [rbp+arg_18]
0x18006c679  mov     [rbp+arg_18], r13
0x18006c67d  test    rcx, rcx
0x18006c680  jz      short loc_18006C688
0x18006c682  call    cs:__imp_AppXFreeMemory
0x18006c688  mov     ebx, edi
0x18006c68a  jmp     loc_18006C77C
0x18006c68f  mov     edx, 51h ; 'Q'
0x18006c694  jmp     loc_18006C603
0x18006c699  mov     rcx, [rbp+hToken]; hObject
0x18006c69d  mov     rbx, [rbp+arg_18]
0x18006c6a1  mov     r15d, [rbp+arg_0]
0x18006c6a5  mov     r14, [r14+2B8h]
0x18006c6ac  mov     r12, [rbp+hObject]
0x18006c6b0  lea     rax, [rcx-1]
0x18006c6b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c6b8  ja      short loc_18006C6BF
0x18006c6ba  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18006c6bf  mov     [rsp+80h+var_40], r13
0x18006c6c4  lea     rcx, [rbp+hToken]
0x18006c6c8  mov     [rsp+80h+var_48], r13d
0x18006c6cd  xor     r9d, r9d
0x18006c6d0  mov     [rsp+80h+var_50], rbx
0x18006c6d5  mov     rdx, r12
0x18006c6d8  mov     [rsp+80h+var_58], r15d
0x18006c6dd  mov     [rbp+hToken], r13
0x18006c6e1  lea     r8d, [r9+0Eh]
0x18006c6e5  mov     qword ptr [rsp+80h+var_60], r14; int
0x18006c6ea  call    cs:__imp_NtCreateLowBoxToken
0x18006c6f0  test    eax, eax
0x18006c6f2  jns     short loc_18006C746
0x18006c6f4  mov     rcx, [rbp+38h]; this
0x18006c6f8  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18006c6ff  mov     r9d, eax; char *
0x18006c702  mov     edx, 60h ; '`'; void *
0x18006c707  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006c70c  mov     rcx, [rbp+arg_18]
0x18006c710  mov     ebx, eax
0x18006c712  mov     [rbp+arg_18], r13
0x18006c716  test    rcx, rcx
0x18006c719  jz      short loc_18006C721
0x18006c71b  call    cs:__imp_AppXFreeMemory
0x18006c721  mov     rcx, [rbp+hObject]; hObject
0x18006c725  lea     rdx, [rcx-1]
0x18006c729  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18006c72d  ja      short loc_18006C735
0x18006c72f  call    cs:__imp_CloseHandle
0x18006c735  mov     rcx, [rbp+hToken]
0x18006c739  lea     rax, [rcx-1]
0x18006c73d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c741  jmp     loc_18006C558
0x18006c746  mov     rcx, [rbp+hToken]; hToken
0x18006c74a  call    cs:__imp_ImpersonateLoggedOnUser
0x18006c750  test    eax, eax
0x18006c752  jnz     short loc_18006C793
0x18006c754  lea     edx, [rax+66h]; void *
0x18006c757  mov     rcx, [rbp+38h]; this
0x18006c75b  lea     r8, aOnecoreAdminAp_143; "onecore\\admin\\appmodel\\OSIM\\src\\de"...
0x18006c762  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006c767  mov     ebx, eax
0x18006c769  mov     rcx, [rbp+arg_18]
0x18006c76d  mov     [rbp+arg_18], r13
0x18006c771  test    rcx, rcx
0x18006c774  jz      short loc_18006C77C
0x18006c776  call    cs:__imp_AppXFreeMemory
0x18006c77c  lea     rcx, [rbp+hObject]
0x18006c780  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c785  lea     rcx, [rbp+hToken]
0x18006c789  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c78e  jmp     loc_18006C560
0x18006c793  test    esi, esi
0x18006c795  jz      short loc_18006C7A7
0x18006c797  mov     rax, [rbp+hObject]
0x18006c79b  mov     rcx, r13
0x18006c79e  mov     [rdi], rax
0x18006c7a1  mov     [rbp+hObject], rcx
0x18006c7a5  jmp     short loc_18006C7AE
0x18006c7a7  mov     rcx, [rbp+hObject]
0x18006c7ab  mov     [rdi], r13
0x18006c7ae  mov     rax, [rbp+arg_18]
0x18006c7b2  mov     [rbp+arg_18], r13
0x18006c7b6  test    rax, rax
0x18006c7b9  jz      short loc_18006C7C8
0x18006c7bb  mov     rcx, rax
0x18006c7be  call    cs:__imp_AppXFreeMemory
0x18006c7c4  mov     rcx, [rbp+hObject]; hObject
0x18006c7c8  lea     rax, [rcx-1]
0x18006c7cc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c7d0  ja      short loc_18006C7D8
0x18006c7d2  call    cs:__imp_CloseHandle
0x18006c7d8  mov     rcx, [rbp+hToken]; hObject
0x18006c7dc  lea     rax, [rcx-1]
0x18006c7e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006c7e4  ja      short loc_18006C7EC
0x18006c7e6  call    cs:__imp_CloseHandle
0x18006c7ec  xor     eax, eax
0x18006c7ee  mov     rbx, [rsp+80h+arg_8]
0x18006c7f6  add     rsp, 80h
0x18006c7fd  pop     r15
0x18006c7ff  pop     r14
0x18006c801  pop     r13
0x18006c803  pop     r12
0x18006c805  pop     rdi
0x18006c806  pop     rsi
0x18006c807  pop     rbp
0x18006c808  retn
```
