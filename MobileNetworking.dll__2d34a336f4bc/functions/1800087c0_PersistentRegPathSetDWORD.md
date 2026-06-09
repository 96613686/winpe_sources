# PersistentRegPathSetDWORD

- ea: `0x1800087c0`
- end: `0x1800088ca`
- name: `PersistentRegPathSetDWORD`
- size: `266`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, const WCHAR *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800073c0`
- `0x1800087c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008836`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008869`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800088a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008836`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008869`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800088a4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008802`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008843`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008802`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008843`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008899`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180008899`

## pseudocode

```c
__int64 __fastcall PersistentRegPathSetDWORD(signed int a1, const wchar_t *a2, const WCHAR *a3, int a4)
{
  wchar_t *v8; // rbp
  unsigned int i; // r14d
  unsigned int PersistentRegPath; // r15d
  unsigned int v11; // ebx
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+20h] BYREF

  Data = a4;
  v12 = 512;
  if ( a1 >= 41 )
    return 87;
  v8 = (wchar_t *)malloc(0x400u);
  if ( !v8 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v12, v8);
    if ( PersistentRegPath != 234 )
      break;
    free(v8);
    v8 = (wchar_t *)malloc(2LL * v12);
    if ( !v8 )
      return 14;
    if ( i >= 3 )
      goto LABEL_11;
  }
  if ( PersistentRegPath )
  {
    if ( v8 )
LABEL_11:
      free(v8);
    return PersistentRegPath;
  }
  v11 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v8, a3, 4u, &Data, 4u);
  free(v8);
  return v11;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp+Data], r9d
0x1800087c5  push    rbx
0x1800087c6  push    rsi
0x1800087c7  push    rdi
0x1800087c8  sub     rsp, 40h
0x1800087cc  mov     [rsp+58h+arg_0], 200h
0x1800087d4  mov     rsi, r8
0x1800087d7  mov     rdi, rdx
0x1800087da  mov     ebx, ecx
0x1800087dc  cmp     ecx, 29h ; ')'
0x1800087df  jl      short loc_1800087EE
0x1800087e1  mov     eax, 57h ; 'W'
0x1800087e6  add     rsp, 40h
0x1800087ea  pop     rdi
0x1800087eb  pop     rsi
0x1800087ec  pop     rbx
0x1800087ed  retn
0x1800087ee  mov     [rsp+58h+arg_8], rbp
0x1800087f3  mov     ecx, 400h; Size
0x1800087f8  mov     [rsp+58h+var_20], r14
0x1800087fd  mov     [rsp+58h+var_28], r15
0x180008802  call    cs:__imp_malloc
0x180008808  mov     rbp, rax
0x18000880b  test    rax, rax
0x18000880e  jz      loc_1800088AE
0x180008814  xor     r14d, r14d
0x180008817  mov     r9, rbp
0x18000881a  lea     r8, [rsp+58h+arg_0]
0x18000881f  mov     rdx, rdi
0x180008822  mov     ecx, ebx
0x180008824  call    GetPersistentRegPath
0x180008829  mov     r15d, eax
0x18000882c  cmp     eax, 0EAh
0x180008831  jnz     short loc_18000885C
0x180008833  mov     rcx, rbp; Block
0x180008836  call    cs:__imp_free
0x18000883c  mov     ecx, [rsp+58h+arg_0]
0x180008840  add     rcx, rcx; Size
0x180008843  call    cs:__imp_malloc
0x180008849  mov     rbp, rax
0x18000884c  test    rax, rax
0x18000884f  jz      short loc_1800088AE
0x180008851  cmp     r14d, 3
0x180008855  jnb     short loc_180008866
0x180008857  inc     r14d
0x18000885a  jmp     short loc_180008817
0x18000885c  test    r15d, r15d
0x18000885f  jz      short loc_180008874
0x180008861  test    rbp, rbp
0x180008864  jz      short loc_18000886F
0x180008866  mov     rcx, rbp; Block
0x180008869  call    cs:__imp_free
0x18000886f  mov     eax, r15d
0x180008872  jmp     short loc_1800088B3
0x180008874  lea     rax, [rsp+58h+Data]
0x180008879  mov     [rsp+58h+cbData], 4; cbData
0x180008881  mov     r9d, 4; dwType
0x180008887  mov     [rsp+58h+lpData], rax; lpData
0x18000888c  mov     r8, rsi; lpValueName
0x18000888f  mov     rdx, rbp; lpSubKey
0x180008892  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008899  call    cs:__imp_RegSetKeyValueW
0x18000889f  mov     rcx, rbp; Block
0x1800088a2  mov     ebx, eax
0x1800088a4  call    cs:__imp_free
0x1800088aa  mov     eax, ebx
0x1800088ac  jmp     short loc_1800088B3
0x1800088ae  mov     eax, 0Eh
0x1800088b3  mov     r14, [rsp+58h+var_20]
0x1800088b8  mov     rbp, [rsp+58h+arg_8]
0x1800088bd  mov     r15, [rsp+58h+var_28]
0x1800088c2  add     rsp, 40h
0x1800088c6  pop     rdi
0x1800088c7  pop     rsi
0x1800088c8  pop     rbx
0x1800088c9  retn
```
