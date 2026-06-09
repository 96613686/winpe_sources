# AllocGpoPathFromClassStorePath(ushort const *)

- ea: `0x180023de4`
- end: `0x180023ea9`
- name: `?AllocGpoPathFromClassStorePath@@YAPEAGPEBG@Z`
- size: `197`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c258`
- `0x180027f84`

## callees

- `0x180023de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023dfa`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e11`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023dfa`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180023e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e3a`

## pseudocode

```c
unsigned __int16 *__fastcall AllocGpoPathFromClassStorePath(const unsigned __int16 *a1)
{
  wchar_t *v1; // rax
  wchar_t *v2; // rax
  _WORD *v3; // rdi
  __int64 v4; // rax
  SIZE_T v5; // rbx
  _WORD *v6; // rax
  void *v7; // rdx
  SIZE_T v8; // rbx
  __int64 v9; // rcx
  _WORD *v10; // rcx

  v1 = wcschr(a1, 0x2Cu);
  if ( !v1 )
    return 0;
  v2 = wcschr(v1 + 1, 0x2Cu);
  if ( !v2 )
    return 0;
  v3 = v2 + 1;
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  v5 = (unsigned int)(2 * v4 + 2);
  v6 = LocalAlloc(0, v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  v8 = v5 >> 1;
  if ( !v8 )
    goto LABEL_14;
  v9 = 2147483646;
  do
  {
    if ( !v9 )
      break;
    if ( !*v3 )
      break;
    *v6++ = *v3++;
    --v9;
    --v8;
  }
  while ( v8 );
  v10 = v6 - 1;
  if ( v8 )
    v10 = v6;
  *v10 = 0;
  if ( !v8 )
  {
LABEL_14:
    LocalFree(v7);
    return 0;
  }
  return (unsigned __int16 *)v7;
}

```

## disassembly

```asm
0x180023de4  mov     [rsp+arg_0], rbx
0x180023de9  mov     [rsp+arg_8], rsi
0x180023dee  push    rdi
0x180023def  sub     rsp, 20h
0x180023df3  mov     ebx, 2Ch ; ','
0x180023df8  mov     edx, ebx; Ch
0x180023dfa  call    cs:__imp_wcschr
0x180023e00  xor     esi, esi
0x180023e02  test    rax, rax
0x180023e05  jz      loc_180023E97
0x180023e0b  mov     edx, ebx; Ch
0x180023e0d  lea     rcx, [rax+2]; Str
0x180023e11  call    cs:__imp_wcschr
0x180023e17  test    rax, rax
0x180023e1a  jz      short loc_180023E97
0x180023e1c  lea     rdi, [rax+2]
0x180023e20  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023e24  inc     rax
0x180023e27  cmp     [rdi+rax*2], si
0x180023e2b  jnz     short loc_180023E24
0x180023e2d  lea     eax, ds:2[rax*2]
0x180023e34  xor     ecx, ecx; uFlags
0x180023e36  mov     edx, eax; uBytes
0x180023e38  mov     ebx, eax
0x180023e3a  call    cs:__imp_LocalAlloc
0x180023e40  mov     rdx, rax
0x180023e43  test    rax, rax
0x180023e46  jz      short loc_180023E97
0x180023e48  shr     rbx, 1
0x180023e4b  jz      short loc_180023E86
0x180023e4d  mov     ecx, 7FFFFFFEh
0x180023e52  test    rcx, rcx
0x180023e55  jz      short loc_180023E76
0x180023e57  movzx   r8d, word ptr [rdi]
0x180023e5b  test    r8w, r8w
0x180023e5f  jz      short loc_180023E76
0x180023e61  mov     [rax], r8w
0x180023e65  add     rdi, 2
0x180023e69  add     rax, 2
0x180023e6d  dec     rcx
0x180023e70  sub     rbx, 1
0x180023e74  jnz     short loc_180023E52
0x180023e76  test    rbx, rbx
0x180023e79  lea     rcx, [rax-2]
0x180023e7d  cmovnz  rcx, rax
0x180023e81  mov     [rcx], si
0x180023e84  jnz     short loc_180023E92
0x180023e86  mov     rcx, rdx; hMem
0x180023e89  call    cs:__imp_LocalFree
0x180023e8f  mov     rdx, rsi
0x180023e92  mov     rax, rdx
0x180023e95  jmp     short loc_180023E99
0x180023e97  xor     eax, eax
0x180023e99  mov     rbx, [rsp+28h+arg_0]
0x180023e9e  mov     rsi, [rsp+28h+arg_8]
0x180023ea3  add     rsp, 20h
0x180023ea7  pop     rdi
0x180023ea8  retn
```
