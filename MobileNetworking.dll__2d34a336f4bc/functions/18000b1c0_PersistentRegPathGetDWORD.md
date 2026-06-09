# PersistentRegPathGetDWORD

- ea: `0x18000b1c0`
- end: `0x18000b2cf`
- name: `PersistentRegPathGetDWORD`
- size: `271`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, const WCHAR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800073c0`
- `0x18000b1c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b239`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b267`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b2a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b239`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b267`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b2a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b204`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b249`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b204`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b249`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b29c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b29c`

## pseudocode

```c
__int64 __fastcall PersistentRegPathGetDWORD(signed int a1, const wchar_t *a2, const WCHAR *a3, void *a4)
{
  wchar_t *v9; // rdi
  unsigned int i; // ebx
  unsigned int PersistentRegPath; // esi
  unsigned int ValueW; // ebx
  DWORD pcbData[4]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+8h] BYREF

  pcbData[0] = 4;
  v14 = 512;
  if ( a1 >= 41 )
    return 87;
  v9 = (wchar_t *)malloc(0x400u);
  if ( !v9 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v14, v9);
    if ( PersistentRegPath != 234 )
      break;
    free(v9);
    v9 = (wchar_t *)malloc(2LL * v14);
    if ( !v9 )
      return 14;
    if ( i >= 3 )
      goto LABEL_10;
  }
  if ( PersistentRegPath )
  {
LABEL_10:
    free(v9);
    return PersistentRegPath;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v9, a3, 0x18u, 0, a4, pcbData);
  free(v9);
  return ValueW;
}

```

## disassembly

```asm
0x18000b1c0  mov     rax, rsp
0x18000b1c3  mov     [rax+10h], rbx
0x18000b1c7  mov     [rax+18h], rbp
0x18000b1cb  push    rsi
0x18000b1cc  push    rdi
0x18000b1cd  push    r12
0x18000b1cf  push    r14
0x18000b1d1  push    r15
0x18000b1d3  sub     rsp, 50h
0x18000b1d7  mov     dword ptr [rax-38h], 4
0x18000b1de  mov     r15, r9
0x18000b1e1  mov     dword ptr [rax+8], 200h
0x18000b1e8  mov     r12, r8
0x18000b1eb  mov     r14, rdx
0x18000b1ee  mov     ebp, ecx
0x18000b1f0  cmp     ecx, 29h ; ')'
0x18000b1f3  jl      short loc_18000B1FF
0x18000b1f5  mov     eax, 57h ; 'W'
0x18000b1fa  jmp     loc_18000B2B6
0x18000b1ff  mov     ecx, 400h; Size
0x18000b204  call    cs:__imp_malloc
0x18000b20a  mov     rdi, rax
0x18000b20d  test    rax, rax
0x18000b210  jz      loc_18000B2B1
0x18000b216  xor     ebx, ebx
0x18000b218  mov     r9, rdi
0x18000b21b  lea     r8, [rsp+78h+arg_0]
0x18000b223  mov     rdx, r14
0x18000b226  mov     ecx, ebp
0x18000b228  call    GetPersistentRegPath
0x18000b22d  mov     esi, eax
0x18000b22f  cmp     eax, 0EAh
0x18000b234  jnz     short loc_18000B260
0x18000b236  mov     rcx, rdi; Block
0x18000b239  call    cs:__imp_free
0x18000b23f  mov     ecx, [rsp+78h+arg_0]
0x18000b246  add     rcx, rcx; Size
0x18000b249  call    cs:__imp_malloc
0x18000b24f  mov     rdi, rax
0x18000b252  test    rax, rax
0x18000b255  jz      short loc_18000B2B1
0x18000b257  cmp     ebx, 3
0x18000b25a  jnb     short loc_18000B264
0x18000b25c  inc     ebx
0x18000b25e  jmp     short loc_18000B218
0x18000b260  test    esi, esi
0x18000b262  jz      short loc_18000B271
0x18000b264  mov     rcx, rdi; Block
0x18000b267  call    cs:__imp_free
0x18000b26d  mov     eax, esi
0x18000b26f  jmp     short loc_18000B2B6
0x18000b271  lea     rax, [rsp+78h+var_38]
0x18000b276  mov     r9d, 18h; dwFlags
0x18000b27c  mov     [rsp+78h+pcbData], rax; pcbData
0x18000b281  mov     r8, r12; lpValue
0x18000b284  mov     [rsp+78h+pvData], r15; pvData
0x18000b289  mov     rdx, rdi; lpSubKey
0x18000b28c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000b293  mov     [rsp+78h+pdwType], 0; pdwType
0x18000b29c  call    cs:__imp_RegGetValueW
0x18000b2a2  mov     rcx, rdi; Block
0x18000b2a5  mov     ebx, eax
0x18000b2a7  call    cs:__imp_free
0x18000b2ad  mov     eax, ebx
0x18000b2af  jmp     short loc_18000B2B6
0x18000b2b1  mov     eax, 0Eh
0x18000b2b6  lea     r11, [rsp+78h+var_28]
0x18000b2bb  mov     rbx, [r11+38h]
0x18000b2bf  mov     rbp, [r11+40h]
0x18000b2c3  mov     rsp, r11
0x18000b2c6  pop     r15
0x18000b2c8  pop     r14
0x18000b2ca  pop     r12
0x18000b2cc  pop     rdi
0x18000b2cd  pop     rsi
0x18000b2ce  retn
```
