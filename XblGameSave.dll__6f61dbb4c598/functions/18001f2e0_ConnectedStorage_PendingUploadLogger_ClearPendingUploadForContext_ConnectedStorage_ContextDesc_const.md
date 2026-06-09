# ConnectedStorage::PendingUploadLogger::ClearPendingUploadForContext(ConnectedStorage::ContextDesc const &)

- ea: `0x18001f2e0`
- end: `0x18001f497`
- name: `?ClearPendingUploadForContext@PendingUploadLogger@ConnectedStorage@@SAXAEBVContextDesc@2@@Z`
- size: `439`
- prototype: `void __fastcall(HSTRING *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18001fd10`
- `0x18005b9cc`
- `0x1800618c4`
- `0x180062404`
- `0x180062780`

## callees

- `0x180015f7c`
- `0x18001ef04`
- `0x18001f2e0`
- `0x18001f8dc`
- `0x18001f984`
- `0x18001f9d8`
- `0x18001fa2c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f3c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f3c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f43c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001f3db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001f44f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001f3db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001f44f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f35f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f35f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f3a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f41d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f3a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f41d`

## pseudocode

```c
void __fastcall ConnectedStorage::PendingUploadLogger::ClearPendingUploadForContext(HSTRING *a1)
{
  __int64 v2; // r9
  __int64 v3; // r9
  HKEY v4; // r14
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rax
  HKEY v8[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cValues; // [rsp+A8h] [rbp+38h] BYREF
  HKEY v10; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  ConnectedStorage::GetRootKey(v8);
  if ( v8[0] )
  {
    LOBYTE(v2) = 1;
    ConnectedStorage::GetUserKeyFromRoot(&v10, v8[0], a1 + 1, v2);
    if ( v10 )
    {
      LOBYTE(v3) = 1;
      ConnectedStorage::GetXuidKeyFromUser(&hKey, v10, a1 + 2, v3);
      v4 = hKey;
      if ( hKey )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(a1[4], 0);
        RegDeleteValueW(v4, StringRawBuffer);
        cValues = 0;
        if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) && !cValues )
        {
          ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&hKey);
          v6 = WindowsGetStringRawBuffer(a1[2], 0);
          RegDeleteKeyExW(v10, v6, 0, 0);
          cValues = 0;
          if ( !RegQueryInfoKeyW(v10, 0, 0, 0, &cValues, 0, 0, 0, 0, 0, 0, 0) && !cValues )
          {
            ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&v10);
            v7 = WindowsGetStringRawBuffer(a1[1], 0);
            RegDeleteKeyExW(v8[0], v7, 0, 0);
          }
        }
      }
      ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&hKey);
    }
    if ( !ConnectedStorage::PendingUploadLogger::HasPendingUploads() )
      ConnectedStorage::ChangeServiceStart(0);
    ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)&v10);
  }
  ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)v8);
}

```

## disassembly

```asm
0x18001f2e0  mov     [rsp-28h+arg_0], rsi
0x18001f2e5  push    rbp
0x18001f2e6  push    rdi
0x18001f2e7  push    r12
0x18001f2e9  push    r14
0x18001f2eb  push    r15
0x18001f2ed  mov     rbp, rsp
0x18001f2f0  sub     rsp, 70h
0x18001f2f4  mov     rdi, rcx
0x18001f2f7  lea     rcx, [rbp+var_10]
0x18001f2fb  call    ?GetRootKey@ConnectedStorage@@YA?AVHKey@1@XZ; ConnectedStorage::GetRootKey(void)
0x18001f300  nop
0x18001f301  xor     r12d, r12d
0x18001f304  cmp     [rbp+var_10], r12
0x18001f308  jz      loc_18001F479
0x18001f30e  mov     r9b, 1
0x18001f311  lea     r8, [rdi+8]
0x18001f315  mov     rdx, [rbp+var_10]
0x18001f319  lea     rcx, [rbp+arg_10]
0x18001f31d  call    ?GetUserKeyFromRoot@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetUserKeyFromRoot(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001f322  nop
0x18001f323  mov     rdx, [rbp+arg_10]
0x18001f327  test    rdx, rdx
0x18001f32a  jz      loc_18001F45E
0x18001f330  mov     r9b, 1
0x18001f333  lea     r8, [rdi+10h]
0x18001f337  lea     rcx, [rbp+hKey]
0x18001f33b  call    ?GetXuidKeyFromUser@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@AEBVSimpleHStringWrapper@1@_N@Z; ConnectedStorage::GetXuidKeyFromUser(HKEY__ *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18001f340  mov     r14, [rbp+hKey]
0x18001f344  test    r14, r14
0x18001f347  jz      loc_18001F455
0x18001f34d  xor     edx, edx; length
0x18001f34f  mov     rcx, [rdi+20h]; string
0x18001f353  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f359  mov     rdx, rax; lpValueName
0x18001f35c  mov     rcx, r14; hKey
0x18001f35f  call    cs:__imp_RegDeleteValueW
0x18001f365  mov     [rbp+cValues], r12d
0x18001f369  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001f36e  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001f373  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001f378  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18001f37d  lea     rax, [rbp+cValues]
0x18001f381  mov     [rsp+70h+lpcValues], rax; lpcValues
0x18001f386  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001f38b  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18001f390  mov     [rsp+70h+lpcSubKeys], r12; lpcSubKeys
0x18001f395  xor     r9d, r9d; lpReserved
0x18001f398  xor     r8d, r8d; lpcchClass
0x18001f39b  xor     edx, edx; lpClass
0x18001f39d  mov     rcx, [rbp+hKey]; hKey
0x18001f3a1  call    cs:__imp_RegQueryInfoKeyW
0x18001f3a7  test    eax, eax
0x18001f3a9  jnz     loc_18001F455
0x18001f3af  cmp     [rbp+cValues], r12d
0x18001f3b3  jnz     loc_18001F455
0x18001f3b9  lea     rcx, [rbp+hKey]; this
0x18001f3bd  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f3c2  xor     edx, edx; length
0x18001f3c4  mov     rcx, [rdi+10h]; string
0x18001f3c8  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f3ce  xor     r9d, r9d; Reserved
0x18001f3d1  xor     r8d, r8d; samDesired
0x18001f3d4  mov     rdx, rax; lpSubKey
0x18001f3d7  mov     rcx, [rbp+arg_10]; hKey
0x18001f3db  call    cs:__imp_RegDeleteKeyExW
0x18001f3e1  mov     [rbp+cValues], r12d
0x18001f3e5  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001f3ea  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001f3ef  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001f3f4  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18001f3f9  mov     [rsp+70h+lpcValues], r12; lpcValues
0x18001f3fe  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001f403  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18001f408  lea     rax, [rbp+cValues]
0x18001f40c  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x18001f411  xor     r9d, r9d; lpReserved
0x18001f414  xor     r8d, r8d; lpcchClass
0x18001f417  xor     edx, edx; lpClass
0x18001f419  mov     rcx, [rbp+arg_10]; hKey
0x18001f41d  call    cs:__imp_RegQueryInfoKeyW
0x18001f423  test    eax, eax
0x18001f425  jnz     short loc_18001F455
0x18001f427  cmp     [rbp+cValues], r12d
0x18001f42b  jnz     short loc_18001F455
0x18001f42d  lea     rcx, [rbp+arg_10]; this
0x18001f431  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f436  xor     edx, edx; length
0x18001f438  mov     rcx, [rdi+8]; string
0x18001f43c  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f442  xor     r9d, r9d; Reserved
0x18001f445  xor     r8d, r8d; samDesired
0x18001f448  mov     rdx, rax; lpSubKey
0x18001f44b  mov     rcx, [rbp+var_10]; hKey
0x18001f44f  call    cs:__imp_RegDeleteKeyExW
0x18001f455  lea     rcx, [rbp+hKey]; this
0x18001f459  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f45e  call    ?HasPendingUploads@PendingUploadLogger@ConnectedStorage@@SA_NXZ; ConnectedStorage::PendingUploadLogger::HasPendingUploads(void)
0x18001f463  test    al, al
0x18001f465  jnz     short loc_18001F46F
0x18001f467  xor     ecx, ecx; this
0x18001f469  call    ?ChangeServiceStart@ConnectedStorage@@YAX_N@Z; ConnectedStorage::ChangeServiceStart(bool)
0x18001f46e  nop
0x18001f46f  lea     rcx, [rbp+arg_10]; this
0x18001f473  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f478  nop
0x18001f479  lea     rcx, [rbp+var_10]; this
0x18001f47d  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18001f482  mov     rsi, [rsp+70h+arg_0]
0x18001f48a  add     rsp, 70h
0x18001f48e  pop     r15
0x18001f490  pop     r14
0x18001f492  pop     r12
0x18001f494  pop     rdi
0x18001f495  pop     rbp
0x18001f496  retn
```
