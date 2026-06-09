# PersistentRegPathGetValue

- ea: `0x18000b2e0`
- end: `0x18000b3ee`
- name: `PersistentRegPathGetValue`
- size: `270`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, const WCHAR *, DWORD, LPDWORD pdwType, PVOID pvData, LPDWORD pcbData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800073c0`
- `0x18000b2e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b34f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b37a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b3c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b34f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b37a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b3c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b31d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b35c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b31d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b35c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b3bb`

## pseudocode

```c
__int64 __fastcall PersistentRegPathGetValue(
        signed int a1,
        const wchar_t *a2,
        const WCHAR *a3,
        DWORD a4,
        LPDWORD pdwType,
        PVOID pvData,
        LPDWORD pcbData)
{
  wchar_t *v12; // rdi
  unsigned int i; // ebx
  unsigned int PersistentRegPath; // esi
  unsigned int ValueW; // ebx
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF

  v16 = 512;
  if ( a1 >= 41 )
    return 87;
  v12 = (wchar_t *)malloc(0x400u);
  if ( !v12 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v16, v12);
    if ( PersistentRegPath != 234 )
      break;
    free(v12);
    v12 = (wchar_t *)malloc(2LL * v16);
    if ( !v12 )
      return 14;
    if ( i >= 3 )
      goto LABEL_10;
  }
  if ( PersistentRegPath )
  {
LABEL_10:
    free(v12);
    return PersistentRegPath;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v12, a3, a4, pdwType, pvData, pcbData);
  free(v12);
  return ValueW;
}

```

## disassembly

```asm
0x18000b2e0  mov     [rsp+arg_8], rbx
0x18000b2e5  mov     [rsp+arg_10], rbp
0x18000b2ea  push    rsi
0x18000b2eb  push    rdi
0x18000b2ec  push    r12
0x18000b2ee  push    r14
0x18000b2f0  push    r15
0x18000b2f2  sub     rsp, 40h
0x18000b2f6  mov     [rsp+68h+arg_0], 200h
0x18000b2fe  mov     r15d, r9d
0x18000b301  mov     r12, r8
0x18000b304  mov     r14, rdx
0x18000b307  mov     ebp, ecx
0x18000b309  cmp     ecx, 29h ; ')'
0x18000b30c  jl      short loc_18000B318
0x18000b30e  mov     eax, 57h ; 'W'
0x18000b313  jmp     loc_18000B3D5
0x18000b318  mov     ecx, 400h; Size
0x18000b31d  call    cs:__imp_malloc
0x18000b323  mov     rdi, rax
0x18000b326  test    rax, rax
0x18000b329  jz      loc_18000B3D0
0x18000b32f  xor     ebx, ebx
0x18000b331  mov     r9, rdi
0x18000b334  lea     r8, [rsp+68h+arg_0]
0x18000b339  mov     rdx, r14
0x18000b33c  mov     ecx, ebp
0x18000b33e  call    GetPersistentRegPath
0x18000b343  mov     esi, eax
0x18000b345  cmp     eax, 0EAh
0x18000b34a  jnz     short loc_18000B373
0x18000b34c  mov     rcx, rdi; Block
0x18000b34f  call    cs:__imp_free
0x18000b355  mov     ecx, [rsp+68h+arg_0]
0x18000b359  add     rcx, rcx; Size
0x18000b35c  call    cs:__imp_malloc
0x18000b362  mov     rdi, rax
0x18000b365  test    rax, rax
0x18000b368  jz      short loc_18000B3D0
0x18000b36a  cmp     ebx, 3
0x18000b36d  jnb     short loc_18000B377
0x18000b36f  inc     ebx
0x18000b371  jmp     short loc_18000B331
0x18000b373  test    esi, esi
0x18000b375  jz      short loc_18000B384
0x18000b377  mov     rcx, rdi; Block
0x18000b37a  call    cs:__imp_free
0x18000b380  mov     eax, esi
0x18000b382  jmp     short loc_18000B3D5
0x18000b384  mov     rax, [rsp+68h+arg_30]
0x18000b38c  mov     r9d, r15d; dwFlags
0x18000b38f  mov     [rsp+68h+pcbData], rax; pcbData
0x18000b394  mov     r8, r12; lpValue
0x18000b397  mov     rax, [rsp+68h+arg_28]
0x18000b39f  mov     rdx, rdi; lpSubKey
0x18000b3a2  mov     [rsp+68h+pvData], rax; pvData
0x18000b3a7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b3ae  mov     rax, [rsp+68h+arg_20]
0x18000b3b6  mov     [rsp+68h+pdwType], rax; pdwType
0x18000b3bb  call    cs:__imp_RegGetValueW
0x18000b3c1  mov     rcx, rdi; Block
0x18000b3c4  mov     ebx, eax
0x18000b3c6  call    cs:__imp_free
0x18000b3cc  mov     eax, ebx
0x18000b3ce  jmp     short loc_18000B3D5
0x18000b3d0  mov     eax, 0Eh
0x18000b3d5  lea     r11, [rsp+68h+var_28]
0x18000b3da  mov     rbx, [r11+38h]
0x18000b3de  mov     rbp, [r11+40h]
0x18000b3e2  mov     rsp, r11
0x18000b3e5  pop     r15
0x18000b3e7  pop     r14
0x18000b3e9  pop     r12
0x18000b3eb  pop     rdi
0x18000b3ec  pop     rsi
0x18000b3ed  retn
```
