# RegOpenKeyEx_Wrapper

- ea: `0x1800281b4`
- end: `0x180028202`
- name: `RegOpenKeyEx_Wrapper`
- size: `78`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, PHKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027ef4`
- `0x1800285cc`

## callees

- `0x1800281b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281f3`

## pseudocode

```c
LSTATUS __fastcall RegOpenKeyEx_Wrapper(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, REGSAM a4, PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
  if ( result == 5 )
    return RegOpenKeyExW(hKey, lpSubKey, 4u, a4, phkResult);
  return result;
}

```

## disassembly

```asm
0x1800281b4  push    rbx
0x1800281b6  push    rbp
0x1800281b7  push    rsi
0x1800281b8  push    rdi
0x1800281b9  sub     rsp, 38h
0x1800281bd  mov     rbp, [rsp+58h+arg_20]
0x1800281c5  xor     r8d, r8d; ulOptions
0x1800281c8  mov     [rsp+58h+phkResult], rbp; phkResult
0x1800281cd  mov     ebx, r9d
0x1800281d0  mov     rdi, rdx
0x1800281d3  mov     rsi, rcx
0x1800281d6  call    cs:__imp_RegOpenKeyExW
0x1800281dc  cmp     eax, 5
0x1800281df  jnz     short loc_1800281F9
0x1800281e1  mov     r9d, ebx; samDesired
0x1800281e4  mov     [rsp+58h+phkResult], rbp; phkResult
0x1800281e9  lea     r8d, [rax-1]; ulOptions
0x1800281ed  mov     rdx, rdi; lpSubKey
0x1800281f0  mov     rcx, rsi; hKey
0x1800281f3  call    cs:__imp_RegOpenKeyExW
0x1800281f9  add     rsp, 38h
0x1800281fd  pop     rdi
0x1800281fe  pop     rsi
0x1800281ff  pop     rbp
0x180028200  pop     rbx
0x180028201  retn
```
