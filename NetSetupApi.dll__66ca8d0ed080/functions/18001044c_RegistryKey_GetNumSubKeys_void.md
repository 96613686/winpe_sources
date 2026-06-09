# RegistryKey::GetNumSubKeys(void)

- ea: `0x18001044c`
- end: `0x18001053f`
- name: `?GetNumSubKeys@RegistryKey@@QEBAKXZ`
- size: `243`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006af8`

## callees

- `0x1800065d4`
- `0x18000895c`
- `0x18000d18c`
- `0x18001044c`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800104c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800104c4`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetNumSubKeys(HKEY *this)
{
  HKEY v1; // rcx
  unsigned int v2; // ebx
  _BYTE pExceptionObject[208]; // [rsp+60h] [rbp-E8h] BYREF
  DWORD lpcSubKeys; // [rsp+130h] [rbp-18h] BYREF

  v1 = *this;
  lpcSubKeys = 0;
  v2 = RegQueryInfoKeyW(v1, 0, 0, 0, &lpcSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids, v2);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v2);
    throw (Win32Exception *)pExceptionObject;
  }
  return lpcSubKeys;
}

```

## disassembly

```asm
0x18001044c  mov     r11, rsp
0x18001044f  push    rbx
0x180010450  sub     rsp, 140h
0x180010457  mov     rax, cs:__security_cookie
0x18001045e  xor     rax, rsp
0x180010461  mov     [rsp+148h+var_10], rax
0x180010469  mov     rcx, [rcx]; hKey
0x18001046c  lea     rax, [r11-18h]
0x180010470  mov     [rsp+148h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180010479  xor     r9d, r9d; lpReserved
0x18001047c  mov     [rsp+148h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180010485  xor     r8d, r8d; lpcchClass
0x180010488  mov     [rsp+148h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180010491  xor     edx, edx; lpClass
0x180010493  mov     [rsp+148h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18001049c  mov     [rsp+148h+lpcValues], 0; lpcValues
0x1800104a5  mov     [rsp+148h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800104ae  mov     [rsp+148h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800104b7  mov     [rsp+148h+lpcSubKeys], rax; lpcSubKeys
0x1800104bc  mov     dword ptr [r11-18h], 0
0x1800104c4  call    cs:__imp_RegQueryInfoKeyW
0x1800104ca  mov     ebx, eax
0x1800104cc  test    eax, eax
0x1800104ce  jz      short loc_18001051F
0x1800104d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104d7  lea     rax, WPP_GLOBAL_Control
0x1800104de  cmp     rcx, rax
0x1800104e1  jz      short loc_180010501
0x1800104e3  cmp     byte ptr [rcx+19h], 2
0x1800104e7  jb      short loc_180010501
0x1800104e9  mov     rcx, [rcx+10h]
0x1800104ed  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800104f4  mov     edx, 12h
0x1800104f9  mov     r9d, ebx
0x1800104fc  call    WPP_SF_d
0x180010501  mov     edx, ebx; int
0x180010503  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180010508  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18001050d  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180010514  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180010519  call    _CxxThrowException_0
0x18001051f  mov     eax, [rsp+148h+var_18]
0x180010526  mov     rcx, [rsp+148h+var_10]
0x18001052e  xor     rcx, rsp; StackCookie
0x180010531  call    __security_check_cookie
0x180010536  add     rsp, 140h
0x18001053d  pop     rbx
0x18001053e  retn
```
