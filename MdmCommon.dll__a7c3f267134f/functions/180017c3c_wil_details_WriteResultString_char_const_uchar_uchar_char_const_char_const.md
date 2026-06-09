# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180017c3c`
- end: `0x180017cb1`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800193fc`
- `0x180019808`

## callees

- `0x180006698`
- `0x180017c3c`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(char *a1, char *a2, _BYTE *a3, _QWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  rsize_t v8; // rdx

  if ( a1 == a2 )
    goto LABEL_10;
  if ( !a3 )
    goto LABEL_10;
  if ( !*a3 )
    goto LABEL_10;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 1;
  v8 = a2 - a1;
  if ( v8 >= v6 + 1 )
  {
    memcpy_s(a1, v8, a3, v6 + 1);
    if ( a4 )
      *a4 = a1;
    return &a1[v7];
  }
  else
  {
LABEL_10:
    if ( a4 )
      *a4 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x180017c3c  mov     [rsp+arg_0], rbx
0x180017c41  mov     [rsp+arg_8], rsi
0x180017c46  push    rdi
0x180017c47  sub     rsp, 20h
0x180017c4b  mov     rbx, r9
0x180017c4e  mov     rdi, rcx
0x180017c51  cmp     rcx, rdx
0x180017c54  jz      short loc_180017C91
0x180017c56  test    r8, r8
0x180017c59  jz      short loc_180017C91
0x180017c5b  cmp     byte ptr [r8], 0
0x180017c5f  jz      short loc_180017C91
0x180017c61  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017c65  inc     rax
0x180017c68  cmp     byte ptr [r8+rax], 0
0x180017c6d  jnz     short loc_180017C65
0x180017c6f  lea     rsi, [rax+1]
0x180017c73  sub     rdx, rdi; DestinationSize
0x180017c76  cmp     rdx, rsi
0x180017c79  jb      short loc_180017C91
0x180017c7b  mov     r9, rsi; SourceSize
0x180017c7e  call    memcpy_s
0x180017c83  test    rbx, rbx
0x180017c86  jz      short loc_180017C8B
0x180017c88  mov     [rbx], rdi
0x180017c8b  lea     rax, [rsi+rdi]
0x180017c8f  jmp     short loc_180017CA0
0x180017c91  test    rbx, rbx
0x180017c94  jz      short loc_180017C9D
0x180017c96  mov     qword ptr [r9], 0
0x180017c9d  mov     rax, rdi
0x180017ca0  mov     rbx, [rsp+28h+arg_0]
0x180017ca5  mov     rsi, [rsp+28h+arg_8]
0x180017caa  add     rsp, 20h
0x180017cae  pop     rdi
0x180017caf  retn
```
