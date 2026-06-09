# MyRegDeleteTree

- ea: `0x18005dabc`
- end: `0x18005dbca`
- name: `MyRegDeleteTree`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005a91c`
- `0x18005dabc`

## callees

- `0x18005dabc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005db7c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005db7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005dba0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005dba0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005db09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005db09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db8e`

## pseudocode

```c
LSTATUS __fastcall MyRegDeleteTree(HKEY a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !result )
  {
    memset_0(Name, 0, 0x20Au);
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        break;
      MyRegDeleteTree(hKey, Name);
    }
    RegCloseKey(hKey);
    return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18005dabc  mov     [rsp-8+arg_10], rbx
0x18005dac1  mov     [rsp-8+arg_18], rdi
0x18005dac6  push    rbp
0x18005dac7  lea     rbp, [rsp-180h]
0x18005dacf  sub     rsp, 280h
0x18005dad6  mov     rax, cs:__security_cookie
0x18005dadd  xor     rax, rsp
0x18005dae0  mov     [rbp+180h+var_10], rax
0x18005dae7  lea     rax, [rsp+280h+hKey]
0x18005daec  mov     [rsp+280h+hKey], 0
0x18005daf5  mov     r9d, 0F003Fh; samDesired
0x18005dafb  mov     [rsp+280h+phkResult], rax; phkResult
0x18005db00  xor     r8d, r8d; ulOptions
0x18005db03  mov     rdi, rdx
0x18005db06  mov     rbx, rcx
0x18005db09  call    cs:__imp_RegOpenKeyExW
0x18005db0f  test    eax, eax
0x18005db11  jnz     loc_18005DBA6
0x18005db17  xor     edx, edx; Val
0x18005db19  lea     rcx, [rsp+280h+Name]; void *
0x18005db1e  mov     r8d, 20Ah; Size
0x18005db24  call    memset_0
0x18005db29  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x18005db32  jmp     short loc_18005DB3E
0x18005db34  lea     rdx, [rsp+280h+Name]
0x18005db39  call    MyRegDeleteTree
0x18005db3e  mov     rcx, [rsp+280h+hKey]; hKey
0x18005db43  lea     rax, [rsp+280h+ftLastWriteTime]
0x18005db48  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18005db4d  lea     r9, [rsp+280h+cchName]; lpcchName
0x18005db52  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18005db5b  lea     r8, [rsp+280h+Name]; lpName
0x18005db60  mov     [rsp+280h+lpClass], 0; lpClass
0x18005db69  xor     edx, edx; dwIndex
0x18005db6b  mov     [rsp+280h+phkResult], 0; lpReserved
0x18005db74  mov     [rsp+280h+cchName], 104h
0x18005db7c  call    cs:__imp_RegEnumKeyExW
0x18005db82  mov     rcx, [rsp+280h+hKey]; hKey
0x18005db87  cmp     eax, 103h
0x18005db8c  jnz     short loc_18005DB34
0x18005db8e  call    cs:__imp_RegCloseKey
0x18005db94  xor     r9d, r9d; Reserved
0x18005db97  xor     r8d, r8d; samDesired
0x18005db9a  mov     rdx, rdi; lpSubKey
0x18005db9d  mov     rcx, rbx; hKey
0x18005dba0  call    cs:__imp_RegDeleteKeyExW
0x18005dba6  mov     rcx, [rbp+180h+var_10]
0x18005dbad  xor     rcx, rsp; StackCookie
0x18005dbb0  call    __security_check_cookie
0x18005dbb5  lea     r11, [rsp+280h+var_s0]
0x18005dbbd  mov     rbx, [r11+20h]
0x18005dbc1  mov     rdi, [r11+28h]
0x18005dbc5  mov     rsp, r11
0x18005dbc8  pop     rbp
0x18005dbc9  retn
```
