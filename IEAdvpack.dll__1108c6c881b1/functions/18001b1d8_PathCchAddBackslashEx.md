# PathCchAddBackslashEx

- ea: `0x18001b1d8`
- end: `0x18001b28d`
- name: `PathCchAddBackslashEx`
- size: `181`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18001b294`

## callees

- `0x180003218`
- `0x18001b1d8`

## pseudocode

```c
HRESULT __stdcall PathCchAddBackslashEx(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)
{
  size_t v6; // rax
  HRESULT result; // eax
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rcx
  unsigned __int16 *v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  if ( ppszEnd )
    *ppszEnd = 0;
  if ( pcchRemaining )
    *pcchRemaining = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszPath[v6] );
  if ( v6 >= cchPath )
    return -2147024774;
  v8 = cchPath - v6;
  v9 = &pszPath[v6];
  v10 = v9;
  v11 = v8;
  if ( !v6 || *(v9 - 1) == 92 )
  {
    result = 1;
  }
  else
  {
    result = StringCchCopyExW(v9, v8, L"\\", &v10, &v11, 0);
    if ( result < 0 )
      return result;
    v9 = v10;
    v8 = v11;
  }
  if ( ppszEnd )
    *ppszEnd = v9;
  if ( pcchRemaining )
    *pcchRemaining = v8;
  return result;
}

```

## disassembly

```asm
0x18001b1d8  mov     [rsp+arg_0], rbx
0x18001b1dd  mov     [rsp+arg_18], rsi
0x18001b1e2  push    rdi
0x18001b1e3  sub     rsp, 30h
0x18001b1e7  xor     esi, esi
0x18001b1e9  mov     rbx, r9
0x18001b1ec  mov     rdi, r8
0x18001b1ef  test    r8, r8
0x18001b1f2  jz      short loc_18001B1F7
0x18001b1f4  mov     [r8], rsi
0x18001b1f7  test    rbx, rbx
0x18001b1fa  jz      short loc_18001B1FF
0x18001b1fc  mov     [r9], rsi
0x18001b1ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b203  inc     rax
0x18001b206  cmp     [rcx+rax*2], si
0x18001b20a  jnz     short loc_18001B203
0x18001b20c  cmp     rax, rdx
0x18001b20f  jb      short loc_18001B218
0x18001b211  mov     eax, 8007007Ah
0x18001b216  jmp     short loc_18001B27D
0x18001b218  sub     rdx, rax; unsigned __int64
0x18001b21b  lea     rcx, [rcx+rax*2]; pszDest
0x18001b21f  mov     [rsp+38h+arg_8], rcx
0x18001b224  mov     [rsp+38h+arg_10], rdx
0x18001b229  test    rax, rax
0x18001b22c  jz      short loc_18001B268
0x18001b22e  mov     eax, 5Ch ; '\'
0x18001b233  cmp     ax, [rcx-2]
0x18001b237  jz      short loc_18001B268
0x18001b239  lea     rax, [rsp+38h+arg_10]
0x18001b23e  mov     [rsp+38h+var_10], esi; unsigned int
0x18001b242  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x18001b247  mov     [rsp+38h+var_18], rax; unsigned __int64 *
0x18001b24c  lea     r8, SubBlock; "\\"
0x18001b253  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001b258  test    eax, eax
0x18001b25a  js      short loc_18001B27D
0x18001b25c  mov     rcx, [rsp+38h+arg_8]
0x18001b261  mov     rdx, [rsp+38h+arg_10]
0x18001b266  jmp     short loc_18001B26D
0x18001b268  mov     eax, 1
0x18001b26d  test    rdi, rdi
0x18001b270  jz      short loc_18001B275
0x18001b272  mov     [rdi], rcx
0x18001b275  test    rbx, rbx
0x18001b278  jz      short loc_18001B27D
0x18001b27a  mov     [rbx], rdx
0x18001b27d  mov     rbx, [rsp+38h+arg_0]
0x18001b282  mov     rsi, [rsp+38h+arg_18]
0x18001b287  add     rsp, 30h
0x18001b28b  pop     rdi
0x18001b28c  retn
```
