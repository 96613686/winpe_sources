# WorkLoop(void)

- ea: `0x140003ab8`
- end: `0x140003c41`
- name: `?WorkLoop@@YAKXZ`
- size: `393`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140003cf8`

## callees

- `0x1400021cf`
- `0x1400035d0`
- `0x1400036c8`
- `0x140003714`
- `0x140003ab8`
- `0x140004360`
- `0x140005010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003b28`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003bcc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003b28`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003bcc`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003bf7`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003c11`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003bf7`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003c11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b90`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003ad7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003ad7`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140003b1c`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140003b1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140003b52`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140003b52`

## pseudocode

```c
__int64 WorkLoop(void)
{
  HRESULT inited; // ebx
  LPVOID ppv; // [rsp+50h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-138h] BYREF

  inited = CoInitializeEx(0, 0);
  if ( inited >= 0 )
  {
    inited = CoInitializeSecurity(0, -1, 0, 0, 2u, 3u, 0, 0x40u, 0);
    if ( inited < 0 )
      goto LABEL_3;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    GetVersionExW(&VersionInformation);
    if ( VersionInformation.dwMajorVersion == 5 && VersionInformation.dwMinorVersion == 1 )
      goto LABEL_11;
    ppv = 0;
    if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv) < 0 )
    {
      CoUninitialize();
      return (unsigned int)-2147024882;
    }
    inited = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( inited >= 0 )
    {
LABEL_11:
      inited = InitFactories();
      if ( inited >= 0 )
      {
        WindowsDispatch();
        if ( g_HostRegisterProfile )
        {
          CoRevokeClassObject(g_HostRegisterProfile);
          g_HostRegisterProfile = 0;
        }
        if ( g_HostRegisterNoProfile )
        {
          CoRevokeClassObject(g_HostRegisterNoProfile);
          g_HostRegisterNoProfile = 0;
        }
      }
      UninitComServer();
    }
    else
    {
LABEL_3:
      CoUninitialize();
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140003ab8  push    rbx
0x140003aba  sub     rsp, 190h
0x140003ac1  mov     rax, cs:__security_cookie
0x140003ac8  xor     rax, rsp
0x140003acb  mov     [rsp+198h+var_18], rax
0x140003ad3  xor     edx, edx; dwCoInit
0x140003ad5  xor     ecx, ecx; pvReserved
0x140003ad7  call    cs:__imp_CoInitializeEx
0x140003add  mov     ebx, eax
0x140003adf  test    eax, eax
0x140003ae1  js      loc_140003BD9
0x140003ae7  mov     [rsp+198h+pReserved3], 0; pReserved3
0x140003af0  xor     r9d, r9d; pReserved1
0x140003af3  mov     [rsp+198h+dwCapabilities], 40h ; '@'; dwCapabilities
0x140003afb  xor     r8d, r8d; asAuthSvc
0x140003afe  mov     [rsp+198h+pAuthList], 0; pAuthList
0x140003b07  or      edx, 0FFFFFFFFh; cAuthSvc
0x140003b0a  mov     [rsp+198h+dwImpLevel], 3; dwImpLevel
0x140003b12  xor     ecx, ecx; pSecDesc
0x140003b14  mov     [rsp+198h+dwAuthnLevel], 2; dwAuthnLevel
0x140003b1c  call    cs:__imp_CoInitializeSecurity
0x140003b22  mov     ebx, eax
0x140003b24  test    eax, eax
0x140003b26  jns     short loc_140003B33
0x140003b28  call    cs:__imp_CoUninitialize
0x140003b2e  jmp     loc_140003C26
0x140003b33  xor     edx, edx; Val
0x140003b35  lea     rcx, [rsp+198h+VersionInformation.dwMajorVersion]; void *
0x140003b3a  mov     r8d, 118h; Size
0x140003b40  call    memset_0
0x140003b45  lea     rcx, [rsp+198h+VersionInformation]; lpVersionInformation
0x140003b4a  mov     [rsp+198h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140003b52  call    cs:__imp_GetVersionExW
0x140003b58  cmp     [rsp+198h+VersionInformation.dwMajorVersion], 5
0x140003b5d  mov     ebx, 1
0x140003b62  jnz     short loc_140003B6A
0x140003b64  cmp     [rsp+198h+VersionInformation.dwMinorVersion], ebx
0x140003b68  jz      short loc_140003BDD
0x140003b6a  lea     rax, [rsp+198h+ppv]
0x140003b6f  mov     [rsp+198h+ppv], 0
0x140003b78  lea     r9, IID_IGlobalOptions; riid
0x140003b7f  mov     qword ptr [rsp+198h+dwAuthnLevel], rax; ppv
0x140003b84  mov     r8d, ebx; dwClsContext
0x140003b87  lea     rcx, CLSID_GlobalOptions; rclsid
0x140003b8e  xor     edx, edx; pUnkOuter
0x140003b90  call    cs:__imp_CoCreateInstance
0x140003b96  test    eax, eax
0x140003b98  js      short loc_140003BCC
0x140003b9a  mov     rcx, [rsp+198h+ppv]
0x140003b9f  mov     r8, rbx
0x140003ba2  mov     edx, ebx
0x140003ba4  mov     rax, [rcx]
0x140003ba7  mov     rax, [rax+18h]
0x140003bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bb0  mov     rcx, [rsp+198h+ppv]
0x140003bb5  mov     ebx, eax
0x140003bb7  mov     rax, [rcx]
0x140003bba  mov     rax, [rax+10h]
0x140003bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bc3  test    ebx, ebx
0x140003bc5  jns     short loc_140003BDD
0x140003bc7  jmp     loc_140003B28
0x140003bcc  call    cs:__imp_CoUninitialize
0x140003bd2  mov     ebx, 8007000Eh
0x140003bd7  jmp     short loc_140003C26
0x140003bd9  test    ebx, ebx
0x140003bdb  js      short loc_140003C26
0x140003bdd  call    ?InitFactories@@YAJXZ; InitFactories(void)
0x140003be2  mov     ebx, eax
0x140003be4  test    eax, eax
0x140003be6  js      short loc_140003C21
0x140003be8  call    ?WindowsDispatch@@YAXXZ; WindowsDispatch(void)
0x140003bed  mov     ecx, cs:?g_HostRegisterProfile@@3KA; dwRegister
0x140003bf3  test    ecx, ecx
0x140003bf5  jz      short loc_140003C07
0x140003bf7  call    cs:__imp_CoRevokeClassObject
0x140003bfd  mov     cs:?g_HostRegisterProfile@@3KA, 0; ulong g_HostRegisterProfile
0x140003c07  mov     ecx, cs:?g_HostRegisterNoProfile@@3KA; dwRegister
0x140003c0d  test    ecx, ecx
0x140003c0f  jz      short loc_140003C21
0x140003c11  call    cs:__imp_CoRevokeClassObject
0x140003c17  mov     cs:?g_HostRegisterNoProfile@@3KA, 0; ulong g_HostRegisterNoProfile
0x140003c21  call    ?UninitComServer@@YAJXZ; UninitComServer(void)
0x140003c26  mov     eax, ebx
0x140003c28  mov     rcx, [rsp+198h+var_18]
0x140003c30  xor     rcx, rsp; StackCookie
0x140003c33  call    __security_check_cookie
0x140003c38  add     rsp, 190h
0x140003c3f  pop     rbx
0x140003c40  retn
```
