# NcbCCResetGetCrashParameters

- ea: `0x180020874`
- end: `0x18002090e`
- name: `NcbCCResetGetCrashParameters`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020a90`

## callees

- `0x180016d98`
- `0x180020874`
- `0x18002c7c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800208fd`

## pseudocode

```c
LSTATUS __fastcall NcbCCResetGetCrashParameters(_DWORD *a1, __int64 *a2)
{
  bool v2; // cc
  const WCHAR *v5; // rdx
  LSTATUS result; // eax
  int Integer2; // eax
  HKEY v8; // rcx
  __int64 UlongLong; // rax
  HKEY v10; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_QWORD *)&xmmword_18004D9D0 + 1) <= 7u;
  *a2 = 86400000;
  *a1 = 5;
  v5 = (const WCHAR *)&lpSubKey;
  hKey = 0;
  if ( !v2 )
    v5 = lpSubKey;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  if ( !result )
  {
    Integer2 = GetInteger2(hKey, L"MaxCrashes", 5);
    v8 = hKey;
    *a1 = Integer2;
    UlongLong = GetUlongLong(v8);
    v10 = hKey;
    *a2 = UlongLong;
    return RegCloseKey(v10);
  }
  return result;
}

```

## disassembly

```asm
0x180020874  mov     r11, rsp
0x180020877  mov     [r11+10h], rbx
0x18002087b  push    rdi
0x18002087c  sub     rsp, 30h
0x180020880  cmp     qword ptr cs:xmmword_18004D9D0+8, 7
0x180020888  lea     rax, [r11+8]
0x18002088c  mov     rbx, rdx
0x18002088f  mov     qword ptr [rdx], 5265C00h
0x180020896  mov     rdi, rcx
0x180020899  mov     dword ptr [rcx], 5
0x18002089f  lea     rdx, lpSubKey
0x1800208a6  mov     qword ptr [r11+8], 0
0x1800208ae  cmova   rdx, qword ptr cs:lpSubKey; lpSubKey
0x1800208b6  mov     r9d, 20019h; samDesired
0x1800208bc  xor     r8d, r8d; ulOptions
0x1800208bf  mov     [r11-18h], rax
0x1800208c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800208ca  call    cs:__imp_RegOpenKeyExW
0x1800208d0  test    eax, eax
0x1800208d2  jnz     short loc_180020903
0x1800208d4  mov     rcx, [rsp+38h+hKey]
0x1800208d9  lea     r8d, [rax+5]
0x1800208dd  lea     rdx, aMaxcrashes; "MaxCrashes"
0x1800208e4  call    GetInteger2
0x1800208e9  mov     rcx, [rsp+38h+hKey]
0x1800208ee  mov     [rdi], eax
0x1800208f0  call    GetUlongLong
0x1800208f5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800208fa  mov     [rbx], rax
0x1800208fd  call    cs:__imp_RegCloseKey
0x180020903  mov     rbx, [rsp+38h+arg_8]
0x180020908  add     rsp, 30h
0x18002090c  pop     rdi
0x18002090d  retn
```
