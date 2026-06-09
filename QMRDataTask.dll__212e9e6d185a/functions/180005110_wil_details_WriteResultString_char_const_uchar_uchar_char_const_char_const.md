# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180005110`
- end: `0x180005185`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e40c`
- `0x18000e810`

## callees

- `0x180005110`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005152`
- `msvcrt!memcpy_s` at `0x180005152`

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
0x180005110  mov     [rsp+arg_0], rbx
0x180005115  mov     [rsp+arg_8], rsi
0x18000511a  push    rdi
0x18000511b  sub     rsp, 20h
0x18000511f  mov     rbx, r9
0x180005122  mov     rdi, rcx
0x180005125  cmp     rcx, rdx
0x180005128  jz      short loc_180005166
0x18000512a  test    r8, r8
0x18000512d  jz      short loc_180005166
0x18000512f  cmp     byte ptr [r8], 0
0x180005133  jz      short loc_180005166
0x180005135  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005139  inc     rax
0x18000513c  cmp     byte ptr [r8+rax], 0
0x180005141  jnz     short loc_180005139
0x180005143  lea     rsi, [rax+1]
0x180005147  sub     rdx, rdi; DestinationSize
0x18000514a  cmp     rdx, rsi
0x18000514d  jb      short loc_180005166
0x18000514f  mov     r9, rsi; SourceSize
0x180005152  call    cs:__imp_memcpy_s
0x180005158  test    rbx, rbx
0x18000515b  jz      short loc_180005160
0x18000515d  mov     [rbx], rdi
0x180005160  lea     rax, [rsi+rdi]
0x180005164  jmp     short loc_180005175
0x180005166  test    rbx, rbx
0x180005169  jz      short loc_180005172
0x18000516b  mov     qword ptr [r9], 0
0x180005172  mov     rax, rdi
0x180005175  mov     rbx, [rsp+28h+arg_0]
0x18000517a  mov     rsi, [rsp+28h+arg_8]
0x18000517f  add     rsp, 20h
0x180005183  pop     rdi
0x180005184  retn
```
