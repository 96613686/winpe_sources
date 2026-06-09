# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180010290`
- end: `0x180010305`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001485c`
- `0x180014c60`

## callees

- `0x180010290`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800102d2`
- `msvcrt!memcpy_s` at `0x1800102d2`

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
0x180010290  mov     [rsp+arg_0], rbx
0x180010295  mov     [rsp+arg_8], rsi
0x18001029a  push    rdi
0x18001029b  sub     rsp, 20h
0x18001029f  mov     rbx, r9
0x1800102a2  mov     rdi, rcx
0x1800102a5  cmp     rcx, rdx
0x1800102a8  jz      short loc_1800102E6
0x1800102aa  test    r8, r8
0x1800102ad  jz      short loc_1800102E6
0x1800102af  cmp     byte ptr [r8], 0
0x1800102b3  jz      short loc_1800102E6
0x1800102b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800102b9  inc     rax
0x1800102bc  cmp     byte ptr [r8+rax], 0
0x1800102c1  jnz     short loc_1800102B9
0x1800102c3  lea     rsi, [rax+1]
0x1800102c7  sub     rdx, rdi; DestinationSize
0x1800102ca  cmp     rdx, rsi
0x1800102cd  jb      short loc_1800102E6
0x1800102cf  mov     r9, rsi; SourceSize
0x1800102d2  call    cs:__imp_memcpy_s
0x1800102d8  test    rbx, rbx
0x1800102db  jz      short loc_1800102E0
0x1800102dd  mov     [rbx], rdi
0x1800102e0  lea     rax, [rsi+rdi]
0x1800102e4  jmp     short loc_1800102F5
0x1800102e6  test    rbx, rbx
0x1800102e9  jz      short loc_1800102F2
0x1800102eb  mov     qword ptr [r9], 0
0x1800102f2  mov     rax, rdi
0x1800102f5  mov     rbx, [rsp+28h+arg_0]
0x1800102fa  mov     rsi, [rsp+28h+arg_8]
0x1800102ff  add     rsp, 20h
0x180010303  pop     rdi
0x180010304  retn
```
