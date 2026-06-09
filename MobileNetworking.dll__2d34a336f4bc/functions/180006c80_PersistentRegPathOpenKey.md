# PersistentRegPathOpenKey

- ea: `0x180006c80`
- end: `0x180006d84`
- name: `PersistentRegPathOpenKey`
- size: `260`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, DWORD, REGSAM, PHKEY phkResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006c80`
- `0x1800073c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006cf7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006d2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006d5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006cf7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006d2a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006d5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006cc3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006d04`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006cc3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006d04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d52`

## pseudocode

```c
__int64 __fastcall PersistentRegPathOpenKey(signed int a1, const wchar_t *a2, DWORD a3, REGSAM a4, PHKEY phkResult)
{
  wchar_t *v10; // r14
  unsigned int i; // r12d
  unsigned int PersistentRegPath; // r15d
  unsigned int v13; // ebx
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 512;
  if ( a1 >= 41 )
    return 87;
  v10 = (wchar_t *)malloc(0x400u);
  if ( !v10 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v14, v10);
    if ( PersistentRegPath != 234 )
      break;
    free(v10);
    v10 = (wchar_t *)malloc(2LL * v14);
    if ( !v10 )
      return 14;
    if ( i >= 3 )
      goto LABEL_11;
  }
  if ( PersistentRegPath )
  {
    if ( v10 )
LABEL_11:
      free(v10);
    return PersistentRegPath;
  }
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, a3, a4, phkResult);
  free(v10);
  return v13;
}

```

## disassembly

```asm
0x180006c80  push    rbx
0x180006c82  push    rbp
0x180006c83  push    rsi
0x180006c84  push    rdi
0x180006c85  sub     rsp, 38h
0x180006c89  mov     [rsp+58h+arg_0], 200h
0x180006c91  mov     edi, r9d
0x180006c94  mov     esi, r8d
0x180006c97  mov     rbp, rdx
0x180006c9a  mov     ebx, ecx
0x180006c9c  cmp     ecx, 29h ; ')'
0x180006c9f  jl      short loc_180006CAF
0x180006ca1  mov     eax, 57h ; 'W'
0x180006ca6  add     rsp, 38h
0x180006caa  pop     rdi
0x180006cab  pop     rsi
0x180006cac  pop     rbp
0x180006cad  pop     rbx
0x180006cae  retn
0x180006caf  mov     [rsp+58h+arg_8], r12
0x180006cb4  mov     ecx, 400h; Size
0x180006cb9  mov     [rsp+58h+arg_10], r14
0x180006cbe  mov     [rsp+58h+var_28], r15
0x180006cc3  call    cs:__imp_malloc
0x180006cc9  mov     r14, rax
0x180006ccc  test    rax, rax
0x180006ccf  jz      loc_180006D67
0x180006cd5  xor     r12d, r12d
0x180006cd8  mov     r9, r14
0x180006cdb  lea     r8, [rsp+58h+arg_0]
0x180006ce0  mov     rdx, rbp
0x180006ce3  mov     ecx, ebx
0x180006ce5  call    GetPersistentRegPath
0x180006cea  mov     r15d, eax
0x180006ced  cmp     eax, 0EAh
0x180006cf2  jnz     short loc_180006D1D
0x180006cf4  mov     rcx, r14; Block
0x180006cf7  call    cs:__imp_free
0x180006cfd  mov     ecx, [rsp+58h+arg_0]
0x180006d01  add     rcx, rcx; Size
0x180006d04  call    cs:__imp_malloc
0x180006d0a  mov     r14, rax
0x180006d0d  test    rax, rax
0x180006d10  jz      short loc_180006D67
0x180006d12  cmp     r12d, 3
0x180006d16  jnb     short loc_180006D27
0x180006d18  inc     r12d
0x180006d1b  jmp     short loc_180006CD8
0x180006d1d  test    r15d, r15d
0x180006d20  jz      short loc_180006D35
0x180006d22  test    r14, r14
0x180006d25  jz      short loc_180006D30
0x180006d27  mov     rcx, r14; Block
0x180006d2a  call    cs:__imp_free
0x180006d30  mov     eax, r15d
0x180006d33  jmp     short loc_180006D6C
0x180006d35  mov     rax, [rsp+58h+arg_20]
0x180006d3d  mov     r9d, edi; samDesired
0x180006d40  mov     r8d, esi; ulOptions
0x180006d43  mov     [rsp+58h+phkResult], rax; phkResult
0x180006d48  mov     rdx, r14; lpSubKey
0x180006d4b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006d52  call    cs:__imp_RegOpenKeyExW
0x180006d58  mov     rcx, r14; Block
0x180006d5b  mov     ebx, eax
0x180006d5d  call    cs:__imp_free
0x180006d63  mov     eax, ebx
0x180006d65  jmp     short loc_180006D6C
0x180006d67  mov     eax, 0Eh
0x180006d6c  mov     r14, [rsp+58h+arg_10]
0x180006d71  mov     r12, [rsp+58h+arg_8]
0x180006d76  mov     r15, [rsp+58h+var_28]
0x180006d7b  add     rsp, 38h
0x180006d7f  pop     rdi
0x180006d80  pop     rsi
0x180006d81  pop     rbp
0x180006d82  pop     rbx
0x180006d83  retn
```
