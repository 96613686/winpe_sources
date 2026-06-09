# PersistentRegPathSetValue

- ea: `0x18000b470`
- end: `0x18000b56d`
- name: `PersistentRegPathSetValue`
- size: `253`
- prototype: `__int64 __fastcall(signed int, const wchar_t *, const WCHAR *, DWORD, LPCVOID lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b400`

## callees

- `0x1800073c0`
- `0x18000b470`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b4df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b50a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b547`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b4df`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b50a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b547`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4ad`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4ec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4ad`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b4ec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000b53c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000b53c`

## pseudocode

```c
__int64 __fastcall PersistentRegPathSetValue(
        signed int a1,
        const wchar_t *a2,
        const WCHAR *a3,
        DWORD a4,
        LPCVOID lpData,
        DWORD cbData)
{
  wchar_t *v11; // rdi
  unsigned int i; // ebx
  unsigned int PersistentRegPath; // esi
  unsigned int v14; // ebx
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 512;
  if ( a1 >= 41 )
    return 87;
  v11 = (wchar_t *)malloc(0x400u);
  if ( !v11 )
    return 14;
  for ( i = 0; ; ++i )
  {
    PersistentRegPath = GetPersistentRegPath(a1, a2, &v15, v11);
    if ( PersistentRegPath != 234 )
      break;
    free(v11);
    v11 = (wchar_t *)malloc(2LL * v15);
    if ( !v11 )
      return 14;
    if ( i >= 3 )
      goto LABEL_10;
  }
  if ( PersistentRegPath )
  {
LABEL_10:
    free(v11);
    return PersistentRegPath;
  }
  v14 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v11, a3, a4, lpData, cbData);
  free(v11);
  return v14;
}

```

## disassembly

```asm
0x18000b470  mov     [rsp+arg_8], rbx
0x18000b475  mov     [rsp+arg_10], rbp
0x18000b47a  push    rsi
0x18000b47b  push    rdi
0x18000b47c  push    r12
0x18000b47e  push    r14
0x18000b480  push    r15
0x18000b482  sub     rsp, 30h
0x18000b486  mov     [rsp+58h+arg_0], 200h
0x18000b48e  mov     r15d, r9d
0x18000b491  mov     r12, r8
0x18000b494  mov     r14, rdx
0x18000b497  mov     ebp, ecx
0x18000b499  cmp     ecx, 29h ; ')'
0x18000b49c  jl      short loc_18000B4A8
0x18000b49e  mov     eax, 57h ; 'W'
0x18000b4a3  jmp     loc_18000B556
0x18000b4a8  mov     ecx, 400h; Size
0x18000b4ad  call    cs:__imp_malloc
0x18000b4b3  mov     rdi, rax
0x18000b4b6  test    rax, rax
0x18000b4b9  jz      loc_18000B551
0x18000b4bf  xor     ebx, ebx
0x18000b4c1  mov     r9, rdi
0x18000b4c4  lea     r8, [rsp+58h+arg_0]
0x18000b4c9  mov     rdx, r14
0x18000b4cc  mov     ecx, ebp
0x18000b4ce  call    GetPersistentRegPath
0x18000b4d3  mov     esi, eax
0x18000b4d5  cmp     eax, 0EAh
0x18000b4da  jnz     short loc_18000B503
0x18000b4dc  mov     rcx, rdi; Block
0x18000b4df  call    cs:__imp_free
0x18000b4e5  mov     ecx, [rsp+58h+arg_0]
0x18000b4e9  add     rcx, rcx; Size
0x18000b4ec  call    cs:__imp_malloc
0x18000b4f2  mov     rdi, rax
0x18000b4f5  test    rax, rax
0x18000b4f8  jz      short loc_18000B551
0x18000b4fa  cmp     ebx, 3
0x18000b4fd  jnb     short loc_18000B507
0x18000b4ff  inc     ebx
0x18000b501  jmp     short loc_18000B4C1
0x18000b503  test    esi, esi
0x18000b505  jz      short loc_18000B514
0x18000b507  mov     rcx, rdi; Block
0x18000b50a  call    cs:__imp_free
0x18000b510  mov     eax, esi
0x18000b512  jmp     short loc_18000B556
0x18000b514  mov     eax, [rsp+58h+arg_28]
0x18000b51b  mov     r9d, r15d; dwType
0x18000b51e  mov     [rsp+58h+cbData], eax; cbData
0x18000b522  mov     r8, r12; lpValueName
0x18000b525  mov     rax, [rsp+58h+arg_20]
0x18000b52d  mov     rdx, rdi; lpSubKey
0x18000b530  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b537  mov     [rsp+58h+lpData], rax; lpData
0x18000b53c  call    cs:__imp_RegSetKeyValueW
0x18000b542  mov     rcx, rdi; Block
0x18000b545  mov     ebx, eax
0x18000b547  call    cs:__imp_free
0x18000b54d  mov     eax, ebx
0x18000b54f  jmp     short loc_18000B556
0x18000b551  mov     eax, 0Eh
0x18000b556  mov     rbx, [rsp+58h+arg_8]
0x18000b55b  mov     rbp, [rsp+58h+arg_10]
0x18000b560  add     rsp, 30h
0x18000b564  pop     r15
0x18000b566  pop     r14
0x18000b568  pop     r12
0x18000b56a  pop     rdi
0x18000b56b  pop     rsi
0x18000b56c  retn
```
