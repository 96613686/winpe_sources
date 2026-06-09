# PersistentRegPathCreateKey

- ea: `0x180006d90`
- end: `0x180006ed4`
- name: `PersistentRegPathCreateKey`
- size: `324`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, DWORD, REGSAM, LPSECURITY_ATTRIBUTES lpSecurityAttributes, PHKEY phkResult, LPDWORD lpdwDisposition)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006d90`
- `0x1800073c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006e54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006e8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006ec3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006e54`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006e8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006ec3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006dc9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006e9f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006dc9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006e9f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180006e49`

## pseudocode

```c
__int64 __fastcall PersistentRegPathCreateKey(
        signed int a1,
        const wchar_t *a2,
        DWORD a3,
        REGSAM a4,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        PHKEY phkResult,
        LPDWORD lpdwDisposition)
{
  wchar_t *v11; // rbx
  unsigned int i; // r12d
  unsigned int PersistentRegPath; // eax
  unsigned int v14; // esi
  unsigned int Key; // edi
  unsigned int v17; // [rsp+80h] [rbp+8h] BYREF

  v17 = 512;
  if ( a1 >= 41 )
    return 87;
  v11 = (wchar_t *)malloc(0x400u);
  if ( !v11 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v17, v11);
    v14 = PersistentRegPath;
    if ( PersistentRegPath != 234 )
      break;
    free(v11);
    v11 = (wchar_t *)malloc(2LL * v17);
    if ( !v11 )
      return 14;
    if ( i >= 3 )
      goto LABEL_13;
  }
  if ( !PersistentRegPath )
  {
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, a3, a4, lpSecurityAttributes, phkResult, lpdwDisposition);
    free(v11);
    return Key;
  }
  if ( v11 )
LABEL_13:
    free(v11);
  return v14;
}

```

## disassembly

```asm
0x180006d90  mov     rax, rsp
0x180006d93  push    rbp
0x180006d94  push    rdi
0x180006d95  push    r14
0x180006d97  push    r15
0x180006d99  sub     rsp, 58h
0x180006d9d  mov     dword ptr [rax+8], 200h
0x180006da4  mov     r14d, r9d
0x180006da7  mov     r15d, r8d
0x180006daa  mov     rbp, rdx
0x180006dad  mov     edi, ecx
0x180006daf  cmp     ecx, 29h ; ')'
0x180006db2  jge     loc_180006E7C
0x180006db8  mov     [rax+10h], rbx
0x180006dbc  mov     ecx, 400h; Size
0x180006dc1  mov     [rax+18h], rsi
0x180006dc5  mov     [rax-28h], r12
0x180006dc9  call    cs:__imp_malloc
0x180006dcf  mov     rbx, rax
0x180006dd2  test    rax, rax
0x180006dd5  jz      loc_180006ECD
0x180006ddb  xor     r12d, r12d
0x180006dde  mov     r9, rbx
0x180006de1  lea     r8, [rsp+78h+arg_0]
0x180006de9  mov     rdx, rbp
0x180006dec  mov     ecx, edi
0x180006dee  call    GetPersistentRegPath
0x180006df3  mov     esi, eax
0x180006df5  cmp     eax, 0EAh
0x180006dfa  jz      loc_180006E8C
0x180006e00  test    eax, eax
0x180006e02  jnz     loc_180006EBB
0x180006e08  mov     rax, [rsp+78h+arg_30]
0x180006e10  xor     r9d, r9d; lpClass
0x180006e13  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180006e18  xor     r8d, r8d; Reserved
0x180006e1b  mov     rax, [rsp+78h+arg_28]
0x180006e23  mov     rdx, rbx; lpSubKey
0x180006e26  mov     [rsp+78h+phkResult], rax; phkResult
0x180006e2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006e32  mov     rax, [rsp+78h+arg_20]
0x180006e3a  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180006e3f  mov     [rsp+78h+samDesired], r14d; samDesired
0x180006e44  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x180006e49  call    cs:__imp_RegCreateKeyExW
0x180006e4f  mov     rcx, rbx; Block
0x180006e52  mov     edi, eax
0x180006e54  call    cs:__imp_free
0x180006e5a  mov     eax, edi
0x180006e5c  mov     rsi, [rsp+78h+arg_10]
0x180006e64  mov     rbx, [rsp+78h+arg_8]
0x180006e6c  mov     r12, [rsp+78h+var_28]
0x180006e71  add     rsp, 58h
0x180006e75  pop     r15
0x180006e77  pop     r14
0x180006e79  pop     rdi
0x180006e7a  pop     rbp
0x180006e7b  retn
0x180006e7c  mov     eax, 57h ; 'W'
0x180006e81  add     rsp, 58h
0x180006e85  pop     r15
0x180006e87  pop     r14
0x180006e89  pop     rdi
0x180006e8a  pop     rbp
0x180006e8b  retn
0x180006e8c  mov     rcx, rbx; Block
0x180006e8f  call    cs:__imp_free
0x180006e95  mov     ecx, [rsp+78h+arg_0]
0x180006e9c  add     rcx, rcx; Size
0x180006e9f  call    cs:__imp_malloc
0x180006ea5  mov     rbx, rax
0x180006ea8  test    rax, rax
0x180006eab  jz      short loc_180006ECD
0x180006ead  cmp     r12d, 3
0x180006eb1  jnb     short loc_180006EC0
0x180006eb3  inc     r12d
0x180006eb6  jmp     loc_180006DDE
0x180006ebb  test    rbx, rbx
0x180006ebe  jz      short loc_180006EC9
0x180006ec0  mov     rcx, rbx; Block
0x180006ec3  call    cs:__imp_free
0x180006ec9  mov     eax, esi
0x180006ecb  jmp     short loc_180006E5C
0x180006ecd  mov     eax, 0Eh
0x180006ed2  jmp     short loc_180006E5C
```
