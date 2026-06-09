# RegistryKey::GetNumValues(void)

- ea: `0x180026fe8`
- end: `0x1800270db`
- name: `?GetNumValues@RegistryKey@@QEBAKXZ`
- size: `243`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180028784`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x180026fe8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027060`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027060`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetNumValues(HKEY *this)
{
  HKEY v1; // rcx
  unsigned int v2; // ebx
  _BYTE pExceptionObject[208]; // [rsp+60h] [rbp-E8h] BYREF
  DWORD lpcValues; // [rsp+130h] [rbp-18h] BYREF

  v1 = *this;
  lpcValues = 0;
  v2 = RegQueryInfoKeyW(v1, 0, 0, 0, 0, 0, 0, &lpcValues, 0, 0, 0, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v2);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v2);
    throw (Win32Exception *)pExceptionObject;
  }
  return lpcValues;
}

```

## disassembly

```asm
0x180026fe8  mov     r11, rsp
0x180026feb  push    rbx
0x180026fec  sub     rsp, 140h
0x180026ff3  mov     rax, cs:__security_cookie
0x180026ffa  xor     rax, rsp
0x180026ffd  mov     [rsp+148h+var_10], rax
0x180027005  mov     rcx, [rcx]; hKey
0x180027008  lea     rax, [r11-18h]
0x18002700c  mov     [rsp+148h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180027015  xor     r9d, r9d; lpReserved
0x180027018  mov     [rsp+148h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180027021  xor     r8d, r8d; lpcchClass
0x180027024  mov     [rsp+148h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18002702d  xor     edx, edx; lpClass
0x18002702f  mov     [rsp+148h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180027038  mov     [rsp+148h+lpcValues], rax; lpcValues
0x18002703d  mov     [rsp+148h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180027046  mov     [rsp+148h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18002704f  mov     [rsp+148h+lpcSubKeys], 0; lpcSubKeys
0x180027058  mov     dword ptr [r11-18h], 0
0x180027060  call    cs:__imp_RegQueryInfoKeyW
0x180027066  mov     ebx, eax
0x180027068  test    eax, eax
0x18002706a  jz      short loc_1800270BB
0x18002706c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027073  lea     rax, WPP_GLOBAL_Control
0x18002707a  cmp     rcx, rax
0x18002707d  jz      short loc_18002709D
0x18002707f  cmp     byte ptr [rcx+19h], 2
0x180027083  jb      short loc_18002709D
0x180027085  mov     rcx, [rcx+10h]
0x180027089  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027090  mov     edx, 14h
0x180027095  mov     r9d, ebx
0x180027098  call    WPP_SF_d
0x18002709d  mov     edx, ebx; int
0x18002709f  lea     rcx, [rsp+148h+pExceptionObject]; this
0x1800270a4  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800270a9  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800270b0  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800270b5  call    _CxxThrowException_0
0x1800270bb  mov     eax, [rsp+148h+var_18]
0x1800270c2  mov     rcx, [rsp+148h+var_10]
0x1800270ca  xor     rcx, rsp; StackCookie
0x1800270cd  call    __security_check_cookie
0x1800270d2  add     rsp, 140h
0x1800270d9  pop     rbx
0x1800270da  retn
```
