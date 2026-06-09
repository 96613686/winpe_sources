# Utils::DeleteKeyRecursive(HKEY__ *,ushort const *)

- ea: `0x1800054cc`
- end: `0x18000563d`
- name: `?DeleteKeyRecursive@Utils@@SAJPEAUHKEY__@@PEBG@Z`
- size: `369`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000383c`
- `0x1800054cc`

## callees

- `0x180004fe8`
- `0x1800054cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800055b7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800055b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000555c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000555c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055e3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000561e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000561e`

## pseudocode

```c
LSTATUS __fastcall Utils::DeleteKeyRecursive(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v4; // ebx
  DWORD v5; // eax
  LSTATUS result; // eax
  DWORD cchName; // [rsp+60h] [rbp-20h] BYREF
  LPWSTR lpName; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B0h] [rbp+30h] BYREF
  DWORD cSubKeys; // [rsp+B8h] [rbp+38h] BYREF

  hKey = 0;
  cbMaxSubKeyLen = 0;
  cSubKeys = 0;
  cchName = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !v4 )
  {
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v4 )
    {
      v5 = cSubKeys;
      do
      {
        if ( !v5 )
          break;
        lpName = 0;
        if ( (int)Utils::AllocateCchStringBuffer(cbMaxSubKeyLen, &lpName, &cbMaxSubKeyLen) < 0 )
        {
          v4 = 14;
        }
        else
        {
          cchName = cbMaxSubKeyLen;
          v4 = RegEnumKeyExW(hKey, 0, lpName, &cchName, 0, 0, 0, 0);
          if ( !v4 )
            v4 = Utils::DeleteKeyRecursive(hKey, lpName);
        }
        if ( lpName )
          LocalFree(lpName);
        v5 = --cSubKeys;
      }
      while ( !v4 );
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  result = 0;
  if ( v4 != 259 )
    result = v4;
  if ( !result )
    return RegDeleteKeyW(a1, a2);
  return result;
}

```

## disassembly

```asm
0x1800054cc  mov     [rsp-18h+arg_0], rbx
0x1800054d1  mov     [rsp-18h+arg_8], rsi
0x1800054d6  push    rbp
0x1800054d7  push    r14
0x1800054d9  push    r15
0x1800054db  mov     rbp, rsp
0x1800054de  sub     rsp, 80h
0x1800054e5  xor     r15d, r15d
0x1800054e8  lea     rax, [rbp+hKey]
0x1800054ec  mov     r9d, 0F003Fh; samDesired
0x1800054f2  mov     [rbp+hKey], r15
0x1800054f6  xor     r8d, r8d; ulOptions
0x1800054f9  mov     [rbp+cbMaxSubKeyLen], r15d
0x1800054fd  mov     [rbp+cSubKeys], r15d
0x180005501  mov     rsi, rdx
0x180005504  mov     [rbp+cchName], r15d
0x180005508  mov     r14, rcx
0x18000550b  mov     [rsp+80h+phkResult], rax; phkResult
0x180005510  call    cs:__imp_RegOpenKeyExW
0x180005516  mov     ebx, eax
0x180005518  test    eax, eax
0x18000551a  jnz     loc_180005608
0x180005520  mov     rcx, [rbp+hKey]; hKey
0x180005524  lea     rax, [rbp+cbMaxSubKeyLen]
0x180005528  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000552d  xor     r9d, r9d; lpReserved
0x180005530  mov     [rsp+80h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180005535  xor     r8d, r8d; lpcchClass
0x180005538  mov     [rsp+80h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000553d  xor     edx, edx; lpClass
0x18000553f  mov     [rsp+80h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180005544  mov     [rsp+80h+lpcValues], r15; lpcValues
0x180005549  mov     [rsp+80h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000554e  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180005553  lea     rax, [rbp+cSubKeys]
0x180005557  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18000555c  call    cs:__imp_RegQueryInfoKeyW
0x180005562  mov     ebx, eax
0x180005564  test    eax, eax
0x180005566  jnz     loc_1800055F9
0x18000556c  mov     eax, [rbp+cSubKeys]
0x18000556f  test    eax, eax
0x180005571  jz      loc_1800055F9
0x180005577  mov     ecx, [rbp+cbMaxSubKeyLen]; unsigned int
0x18000557a  lea     r8, [rbp+cbMaxSubKeyLen]; unsigned int *
0x18000557e  lea     rdx, [rbp+lpName]; unsigned __int16 **
0x180005582  mov     [rbp+lpName], r15
0x180005586  call    ?AllocateCchStringBuffer@Utils@@SAJKPEAPEAGPEAK@Z; Utils::AllocateCchStringBuffer(ulong,ushort * *,ulong *)
0x18000558b  test    eax, eax
0x18000558d  js      short loc_1800055D4
0x18000558f  mov     eax, [rbp+cbMaxSubKeyLen]
0x180005592  lea     r9, [rbp+cchName]; lpcchName
0x180005596  mov     r8, [rbp+lpName]; lpName
0x18000559a  xor     edx, edx; dwIndex
0x18000559c  mov     rcx, [rbp+hKey]; hKey
0x1800055a0  mov     [rsp+80h+lpcValues], r15; lpftLastWriteTime
0x1800055a5  mov     [rsp+80h+lpcbMaxClassLen], r15; lpcchClass
0x1800055aa  mov     [rsp+80h+lpcbMaxSubKeyLen], r15; lpClass
0x1800055af  mov     [rsp+80h+phkResult], r15; lpReserved
0x1800055b4  mov     [rbp+cchName], eax
0x1800055b7  call    cs:__imp_RegEnumKeyExW
0x1800055bd  mov     ebx, eax
0x1800055bf  test    eax, eax
0x1800055c1  jnz     short loc_1800055D9
0x1800055c3  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x1800055c7  mov     rcx, [rbp+hKey]; HKEY
0x1800055cb  call    ?DeleteKeyRecursive@Utils@@SAJPEAUHKEY__@@PEBG@Z; Utils::DeleteKeyRecursive(HKEY__ *,ushort const *)
0x1800055d0  mov     ebx, eax
0x1800055d2  jmp     short loc_1800055D9
0x1800055d4  mov     ebx, 0Eh
0x1800055d9  cmp     [rbp+lpName], r15
0x1800055dd  jz      short loc_1800055E9
0x1800055df  mov     rcx, [rbp+lpName]; hMem
0x1800055e3  call    cs:__imp_LocalFree
0x1800055e9  mov     eax, [rbp+cSubKeys]
0x1800055ec  dec     eax
0x1800055ee  mov     [rbp+cSubKeys], eax
0x1800055f1  test    ebx, ebx
0x1800055f3  jz      loc_18000556F
0x1800055f9  mov     rcx, [rbp+hKey]; hKey
0x1800055fd  test    rcx, rcx
0x180005600  jz      short loc_180005608
0x180005602  call    cs:__imp_RegCloseKey
0x180005608  cmp     ebx, 103h
0x18000560e  mov     eax, r15d
0x180005611  cmovnz  eax, ebx
0x180005614  test    eax, eax
0x180005616  jnz     short loc_180005624
0x180005618  mov     rdx, rsi; lpSubKey
0x18000561b  mov     rcx, r14; hKey
0x18000561e  call    cs:__imp_RegDeleteKeyW
0x180005624  lea     r11, [rsp+80h+var_s0]
0x18000562c  mov     rbx, [r11+20h]
0x180005630  mov     rsi, [r11+28h]
0x180005634  mov     rsp, r11
0x180005637  pop     r15
0x180005639  pop     r14
0x18000563b  pop     rbp
0x18000563c  retn
```
