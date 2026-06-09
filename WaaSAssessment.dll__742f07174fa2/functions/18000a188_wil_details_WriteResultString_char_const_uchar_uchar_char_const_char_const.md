# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000a188`
- end: `0x18000a1fd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aed4`
- `0x18000f010`

## callees

- `0x18000a188`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a1ca`
- `msvcrt!memcpy_s` at `0x18000a1ca`

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
0x18000a188  mov     [rsp+arg_0], rbx
0x18000a18d  mov     [rsp+arg_8], rsi
0x18000a192  push    rdi
0x18000a193  sub     rsp, 20h
0x18000a197  mov     rbx, r9
0x18000a19a  mov     rdi, rcx
0x18000a19d  cmp     rcx, rdx
0x18000a1a0  jz      short loc_18000A1DE
0x18000a1a2  test    r8, r8
0x18000a1a5  jz      short loc_18000A1DE
0x18000a1a7  cmp     byte ptr [r8], 0
0x18000a1ab  jz      short loc_18000A1DE
0x18000a1ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a1b1  inc     rax
0x18000a1b4  cmp     byte ptr [r8+rax], 0
0x18000a1b9  jnz     short loc_18000A1B1
0x18000a1bb  lea     rsi, [rax+1]
0x18000a1bf  sub     rdx, rdi; DestinationSize
0x18000a1c2  cmp     rdx, rsi
0x18000a1c5  jb      short loc_18000A1DE
0x18000a1c7  mov     r9, rsi; SourceSize
0x18000a1ca  call    cs:__imp_memcpy_s
0x18000a1d0  test    rbx, rbx
0x18000a1d3  jz      short loc_18000A1D8
0x18000a1d5  mov     [rbx], rdi
0x18000a1d8  lea     rax, [rsi+rdi]
0x18000a1dc  jmp     short loc_18000A1ED
0x18000a1de  test    rbx, rbx
0x18000a1e1  jz      short loc_18000A1EA
0x18000a1e3  mov     qword ptr [r9], 0
0x18000a1ea  mov     rax, rdi
0x18000a1ed  mov     rbx, [rsp+28h+arg_0]
0x18000a1f2  mov     rsi, [rsp+28h+arg_8]
0x18000a1f7  add     rsp, 20h
0x18000a1fb  pop     rdi
0x18000a1fc  retn
```
