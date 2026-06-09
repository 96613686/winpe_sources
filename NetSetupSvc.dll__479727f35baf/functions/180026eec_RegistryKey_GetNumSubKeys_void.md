# RegistryKey::GetNumSubKeys(void)

- ea: `0x180026eec`
- end: `0x180026fdf`
- name: `?GetNumSubKeys@RegistryKey@@QEBAKXZ`
- size: `243`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001aad4`
- `0x18001ac78`
- `0x1800207bc`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x180026eec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026f64`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180026f64`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v2);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v2);
    throw (Win32Exception *)pExceptionObject;
  }
  return lpcSubKeys;
}

```

## disassembly

```asm
0x180026eec  mov     r11, rsp
0x180026eef  push    rbx
0x180026ef0  sub     rsp, 140h
0x180026ef7  mov     rax, cs:__security_cookie
0x180026efe  xor     rax, rsp
0x180026f01  mov     [rsp+148h+var_10], rax
0x180026f09  mov     rcx, [rcx]; hKey
0x180026f0c  lea     rax, [r11-18h]
0x180026f10  mov     [rsp+148h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180026f19  xor     r9d, r9d; lpReserved
0x180026f1c  mov     [rsp+148h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180026f25  xor     r8d, r8d; lpcchClass
0x180026f28  mov     [rsp+148h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180026f31  xor     edx, edx; lpClass
0x180026f33  mov     [rsp+148h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180026f3c  mov     [rsp+148h+lpcValues], 0; lpcValues
0x180026f45  mov     [rsp+148h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180026f4e  mov     [rsp+148h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180026f57  mov     [rsp+148h+lpcSubKeys], rax; lpcSubKeys
0x180026f5c  mov     dword ptr [r11-18h], 0
0x180026f64  call    cs:__imp_RegQueryInfoKeyW
0x180026f6a  mov     ebx, eax
0x180026f6c  test    eax, eax
0x180026f6e  jz      short loc_180026FBF
0x180026f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f77  lea     rax, WPP_GLOBAL_Control
0x180026f7e  cmp     rcx, rax
0x180026f81  jz      short loc_180026FA1
0x180026f83  cmp     byte ptr [rcx+19h], 2
0x180026f87  jb      short loc_180026FA1
0x180026f89  mov     rcx, [rcx+10h]
0x180026f8d  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180026f94  mov     edx, 12h
0x180026f99  mov     r9d, ebx
0x180026f9c  call    WPP_SF_d
0x180026fa1  mov     edx, ebx; int
0x180026fa3  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180026fa8  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180026fad  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026fb4  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180026fb9  call    _CxxThrowException_0
0x180026fbf  mov     eax, [rsp+148h+var_18]
0x180026fc6  mov     rcx, [rsp+148h+var_10]
0x180026fce  xor     rcx, rsp; StackCookie
0x180026fd1  call    __security_check_cookie
0x180026fd6  add     rsp, 140h
0x180026fdd  pop     rbx
0x180026fde  retn
```
