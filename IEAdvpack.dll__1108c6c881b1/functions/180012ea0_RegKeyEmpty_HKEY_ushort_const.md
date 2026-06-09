# RegKeyEmpty(HKEY__ *,ushort const *)

- ea: `0x180012ea0`
- end: `0x180012f41`
- name: `?RegKeyEmpty@@YAHPEAUHKEY__@@PEBG@Z`
- size: `161`
- prototype: `_BOOL8 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012f48`
- `0x180013280`

## callees

- `0x180012ea0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180012f2e`
- `ADVAPI32!RegCloseKey` at `0x180012f2e`
- `ADVAPI32!RegOpenKeyExW` at `0x180012ece`
- `ADVAPI32!RegOpenKeyExW` at `0x180012ece`
- `ADVAPI32!RegEnumValueW` at `0x180012f1b`
- `ADVAPI32!RegEnumValueW` at `0x180012f1b`
- `ADVAPI32!RegEnumKeyW` at `0x180012ee9`
- `ADVAPI32!RegEnumKeyW` at `0x180012ee9`

## pseudocode

```c
_BOOL8 __fastcall RegKeyEmpty(HKEY a1, const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  WCHAR Name; // [rsp+70h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v2 = 0;
  cchName = 1;
  if ( !RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) )
  {
    if ( RegEnumKeyW(hKey, 0, &Name, cchName) == 259 )
      v2 = RegEnumValueW(hKey, 0, &Name, &cchName, 0, 0, 0, 0) == 259;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180012ea0  mov     rax, rsp
0x180012ea3  mov     [rax+8], rbx
0x180012ea7  push    rbp
0x180012ea8  sub     rsp, 50h
0x180012eac  mov     qword ptr [rax-18h], 0
0x180012eb4  lea     rax, [rax-18h]
0x180012eb8  xor     ebx, ebx
0x180012eba  mov     [rsp+58h+phkResult], rax; phkResult
0x180012ebf  mov     r9d, 20019h; samDesired
0x180012ec5  xor     r8d, r8d; ulOptions
0x180012ec8  lea     ebp, [rbx+1]
0x180012ecb  mov     [rax+38h], ebp
0x180012ece  call    cs:__imp_RegOpenKeyExW
0x180012ed4  test    eax, eax
0x180012ed6  jnz     short loc_180012F34
0x180012ed8  mov     r9d, [rsp+58h+cchName]; cchName
0x180012edd  lea     r8, [rsp+58h+Name]; lpName
0x180012ee2  mov     rcx, [rsp+58h+hKey]; hKey
0x180012ee7  xor     edx, edx; dwIndex
0x180012ee9  call    cs:__imp_RegEnumKeyW
0x180012eef  cmp     eax, 103h
0x180012ef4  jnz     short loc_180012F29
0x180012ef6  mov     rcx, [rsp+58h+hKey]; hKey
0x180012efb  lea     r9, [rsp+58h+cchName]; lpcchValueName
0x180012f00  mov     [rsp+58h+lpcbData], rbx; lpcbData
0x180012f05  lea     r8, [rsp+58h+Name]; lpValueName
0x180012f0a  mov     [rsp+58h+lpData], rbx; lpData
0x180012f0f  xor     edx, edx; dwIndex
0x180012f11  mov     [rsp+58h+lpType], rbx; lpType
0x180012f16  mov     [rsp+58h+phkResult], rbx; lpReserved
0x180012f1b  call    cs:__imp_RegEnumValueW
0x180012f21  cmp     eax, 103h
0x180012f26  cmovz   ebx, ebp
0x180012f29  mov     rcx, [rsp+58h+hKey]; hKey
0x180012f2e  call    cs:__imp_RegCloseKey
0x180012f34  mov     eax, ebx
0x180012f36  mov     rbx, [rsp+58h+arg_0]
0x180012f3b  add     rsp, 50h
0x180012f3f  pop     rbp
0x180012f40  retn
```
