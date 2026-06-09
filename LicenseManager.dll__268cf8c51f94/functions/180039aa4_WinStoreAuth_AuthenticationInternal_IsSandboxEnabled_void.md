# WinStoreAuth::AuthenticationInternal::IsSandboxEnabled(void)

- ea: `0x180039aa4`
- end: `0x180039c3f`
- name: `?IsSandboxEnabled@AuthenticationInternal@WinStoreAuth@@YA_NXZ`
- size: `411`
- prototype: `bool __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e70`
- `0x18003ffbc`

## callees

- `0x180004644`
- `0x180039aa4`
- `0x180075e60`
- `0x1800769f4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039bbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039be4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039bbd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039be4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039b56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039b56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039c07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039c07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039af7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039af7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinStoreAuth::AuthenticationInternal::IsSandboxEnabled(WinStoreAuth::AuthenticationInternal *this)
{
  LSTATUS v1; // eax
  bool v2; // sf
  LSTATUS ValueW; // eax
  bool v4; // sf
  __int64 v5; // rcx
  WCHAR *v6; // rax
  __int64 v7; // rbx
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String1[512]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\XboxLive", 0, 0x20019u, &hkey);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( !v2 )
  {
    memset_0(String1, 0, sizeof(String1));
    pcbData = 1024;
    ValueW = RegGetValueW(hkey, 0, L"Sandbox", 2u, 0, String1, &pcbData);
    v4 = ValueW < 0;
    if ( ValueW > 0 )
      v4 = 1;
    if ( v4 )
    {
LABEL_15:
      if ( hkey )
        RegCloseKey(hkey);
      return 0;
    }
    v5 = 512;
    v6 = String1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = (512 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      if ( v7
        && CompareStringOrdinal(String1, v7, &LocaleName, 0, 1) != 2
        && CompareStringOrdinal(String1, v7, L"RETAIL", 6, 1) != 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return 1;
      }
      goto LABEL_15;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 0;
}

```

## disassembly

```asm
0x180039aa4  mov     [rsp-8+arg_0], rbx
0x180039aa9  mov     [rsp-8+arg_8], rdi
0x180039aae  push    rbp
0x180039aaf  lea     rbp, [rsp-360h]
0x180039ab7  sub     rsp, 460h
0x180039abe  mov     rax, cs:__security_cookie
0x180039ac5  xor     rax, rsp
0x180039ac8  mov     [rbp+360h+var_10], rax
0x180039acf  xor     edi, edi
0x180039ad1  mov     [rsp+460h+hkey], rdi
0x180039ad6  lea     rax, [rsp+460h+hkey]
0x180039adb  mov     [rsp+460h+phkResult], rax; phkResult
0x180039ae0  mov     r9d, 20019h; samDesired
0x180039ae6  xor     r8d, r8d; ulOptions
0x180039ae9  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\XboxLive"
0x180039af0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039af7  call    cs:__imp_RegOpenKeyExW
0x180039afd  test    eax, eax
0x180039aff  jle     short loc_180039B0B
0x180039b01  movzx   eax, ax
0x180039b04  or      eax, 80070000h
0x180039b09  test    eax, eax
0x180039b0b  js      loc_180039C0F
0x180039b11  mov     ebx, 400h
0x180039b16  mov     r8d, ebx; Size
0x180039b19  xor     edx, edx; Val
0x180039b1b  lea     rcx, [rsp+460h+String1]; void *
0x180039b20  call    memset_0
0x180039b25  mov     [rsp+460h+var_418], ebx
0x180039b29  lea     rax, [rsp+460h+var_418]
0x180039b2e  mov     [rsp+460h+pcbData], rax; pcbData
0x180039b33  lea     rax, [rsp+460h+String1]
0x180039b38  mov     [rsp+460h+pvData], rax; pvData
0x180039b3d  mov     [rsp+460h+phkResult], rdi; pdwType
0x180039b42  mov     r9d, 2; dwFlags
0x180039b48  lea     r8, aSandbox; "Sandbox"
0x180039b4f  xor     edx, edx; lpSubKey
0x180039b51  mov     rcx, [rsp+460h+hkey]; hkey
0x180039b56  call    cs:__imp_RegGetValueW
0x180039b5c  test    eax, eax
0x180039b5e  jle     short loc_180039B6A
0x180039b60  movzx   eax, ax
0x180039b63  or      eax, 80070000h
0x180039b68  test    eax, eax
0x180039b6a  js      loc_180039BFD
0x180039b70  mov     edx, 200h
0x180039b75  mov     ecx, edx
0x180039b77  lea     rax, [rsp+460h+String1]
0x180039b7c  cmp     [rax], di
0x180039b7f  jz      short loc_180039B8B
0x180039b81  add     rax, 2
0x180039b85  sub     rcx, 1
0x180039b89  jnz     short loc_180039B7C
0x180039b8b  mov     rax, rcx
0x180039b8e  sub     rdx, rcx
0x180039b91  neg     rax
0x180039b94  sbb     rbx, rbx
0x180039b97  and     rbx, rdx
0x180039b9a  test    rcx, rcx
0x180039b9d  jz      short loc_180039C0F
0x180039b9f  test    rbx, rbx
0x180039ba2  jz      short loc_180039BFD
0x180039ba4  mov     dword ptr [rsp+460h+phkResult], 1; bIgnoreCase
0x180039bac  xor     r9d, r9d; cchCount2
0x180039baf  lea     r8, LocaleName; lpString2
0x180039bb6  mov     edx, ebx; cchCount1
0x180039bb8  lea     rcx, [rsp+460h+String1]; lpString1
0x180039bbd  call    cs:__imp_CompareStringOrdinal
0x180039bc3  cmp     eax, 2
0x180039bc6  jz      short loc_180039BFD
0x180039bc8  mov     dword ptr [rsp+460h+phkResult], 1; bIgnoreCase
0x180039bd0  mov     r9d, 6; cchCount2
0x180039bd6  lea     r8, aRetail; "RETAIL"
0x180039bdd  mov     edx, ebx; cchCount1
0x180039bdf  lea     rcx, [rsp+460h+String1]; lpString1
0x180039be4  call    cs:__imp_CompareStringOrdinal
0x180039bea  cmp     eax, 2
0x180039bed  jz      short loc_180039BFD
0x180039bef  lea     rcx, [rsp+460h+hkey]
0x180039bf4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039bf9  mov     al, 1
0x180039bfb  jmp     short loc_180039C1B
0x180039bfd  mov     rcx, [rsp+460h+hkey]; hKey
0x180039c02  test    rcx, rcx
0x180039c05  jz      short loc_180039C19
0x180039c07  call    cs:__imp_RegCloseKey
0x180039c0d  jmp     short loc_180039C19
0x180039c0f  lea     rcx, [rsp+460h+hkey]
0x180039c14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039c19  xor     al, al
0x180039c1b  mov     rcx, [rbp+360h+var_10]
0x180039c22  xor     rcx, rsp; StackCookie
0x180039c25  call    __security_check_cookie
0x180039c2a  lea     r11, [rsp+460h+var_s0]
0x180039c32  mov     rbx, [r11+10h]
0x180039c36  mov     rdi, [r11+18h]
0x180039c3a  mov     rsp, r11
0x180039c3d  pop     rbp
0x180039c3e  retn
```
