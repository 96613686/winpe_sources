# RegDeleteEntireKey(HKEY__ *,ushort const *)

- ea: `0x180040458`
- end: `0x18004058e`
- name: `?RegDeleteEntireKey@@YAJPEAUHKEY__@@PEBG@Z`
- size: `310`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003fe6c`
- `0x180040458`

## callees

- `0x180040458`
- `0x18004d900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040561`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040561`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040528`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040528`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800404f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800404f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004054b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004054b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404a7`

## pseudocode

```c
LSTATUS __fastcall RegDeleteEntireKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS result; // eax
  DWORD v5; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  if ( !result )
  {
    cSubKeys = 0;
    RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v5 = cSubKeys;
    while ( (--v5 & 0x80000000) == 0 )
    {
      cSubKeys = 260;
      if ( !RegEnumKeyExW(hKey, v5, Name, &cSubKeys, 0, 0, 0, 0) )
        RegDeleteEntireKey(hKey, Name);
    }
    result = RegCloseKey(hKey);
    if ( !result )
      return RegDeleteKeyExW(a1, a2, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180040458  mov     [rsp-8+arg_10], rbx
0x18004045d  mov     [rsp-8+arg_18], rsi
0x180040462  push    rbp
0x180040463  push    rdi
0x180040464  push    r14
0x180040466  lea     rbp, [rsp-190h]
0x18004046e  sub     rsp, 290h
0x180040475  mov     rax, cs:__security_cookie
0x18004047c  xor     rax, rsp
0x18004047f  mov     [rbp+1A0h+var_20], rax
0x180040486  lea     rax, [rsp+2A0h+hKey]
0x18004048b  xor     r14d, r14d
0x18004048e  mov     r9d, 2000000h; samDesired
0x180040494  mov     [rsp+2A0h+hKey], r14
0x180040499  xor     r8d, r8d; ulOptions
0x18004049c  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800404a1  mov     rsi, rdx
0x1800404a4  mov     rdi, rcx
0x1800404a7  call    cs:__imp_RegOpenKeyExW
0x1800404ad  test    eax, eax
0x1800404af  jnz     loc_180040567
0x1800404b5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800404ba  lea     rax, [rsp+2A0h+cSubKeys]
0x1800404bf  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800404c4  xor     r9d, r9d; lpReserved
0x1800404c7  mov     [rsp+2A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800404cc  xor     r8d, r8d; lpcchClass
0x1800404cf  mov     [rsp+2A0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800404d4  xor     edx, edx; lpClass
0x1800404d6  mov     [rsp+2A0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800404db  mov     [rsp+2A0h+lpcValues], r14; lpcValues
0x1800404e0  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800404e5  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800404ea  mov     [rsp+2A0h+phkResult], rax; lpcSubKeys
0x1800404ef  mov     [rsp+2A0h+cSubKeys], r14d
0x1800404f4  call    cs:__imp_RegQueryInfoKeyA
0x1800404fa  mov     ebx, [rsp+2A0h+cSubKeys]
0x1800404fe  jmp     short loc_180040541
0x180040500  mov     [rsp+2A0h+lpcValues], r14; lpftLastWriteTime
0x180040505  lea     r9, [rsp+2A0h+cSubKeys]; lpcchName
0x18004050a  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpcchClass
0x18004050f  lea     r8, [rsp+2A0h+Name]; lpName
0x180040514  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpClass
0x180040519  mov     edx, ebx; dwIndex
0x18004051b  mov     [rsp+2A0h+phkResult], r14; lpReserved
0x180040520  mov     [rsp+2A0h+cSubKeys], 104h
0x180040528  call    cs:__imp_RegEnumKeyExW
0x18004052e  test    eax, eax
0x180040530  jnz     short loc_180040541
0x180040532  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x180040537  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x18004053c  call    ?RegDeleteEntireKey@@YAJPEAUHKEY__@@PEBG@Z; RegDeleteEntireKey(HKEY__ *,ushort const *)
0x180040541  sub     ebx, 1
0x180040544  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180040549  jns     short loc_180040500
0x18004054b  call    cs:__imp_RegCloseKey
0x180040551  test    eax, eax
0x180040553  jnz     short loc_180040567
0x180040555  xor     r9d, r9d; Reserved
0x180040558  xor     r8d, r8d; samDesired
0x18004055b  mov     rdx, rsi; lpSubKey
0x18004055e  mov     rcx, rdi; hKey
0x180040561  call    cs:__imp_RegDeleteKeyExW
0x180040567  mov     rcx, [rbp+1A0h+var_20]
0x18004056e  xor     rcx, rsp; StackCookie
0x180040571  call    __security_check_cookie
0x180040576  lea     r11, [rsp+2A0h+var_10]
0x18004057e  mov     rbx, [r11+30h]
0x180040582  mov     rsi, [r11+38h]
0x180040586  mov     rsp, r11
0x180040589  pop     r14
0x18004058b  pop     rdi
0x18004058c  pop     rbp
0x18004058d  retn
```
