# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x1400046a0`
- end: `0x140004720`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `128`
- prototype: `char *__fastcall(char *, char *, _WORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001dbc`
- `0x1400034ac`

## callees

- `0x1400046a0`
- `0x14000f340`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<wchar_t const *>(char *a1, char *a2, _WORD *a3, _QWORD *a4)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
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
  v7 = 2 * v6 + 2;
  v8 = a2 - a1;
  if ( v8 >= v7 )
  {
    memcpy_s(a1, v8, a3, 2 * v6 + 2);
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
0x1400046a0  mov     [rsp+arg_0], rbx
0x1400046a5  mov     [rsp+arg_8], rbp
0x1400046aa  mov     [rsp+arg_10], rsi
0x1400046af  push    rdi
0x1400046b0  sub     rsp, 20h
0x1400046b4  xor     ebp, ebp
0x1400046b6  mov     rbx, r9
0x1400046b9  mov     rdi, rcx
0x1400046bc  cmp     rcx, rdx
0x1400046bf  jz      short loc_140004700
0x1400046c1  test    r8, r8
0x1400046c4  jz      short loc_140004700
0x1400046c6  cmp     [r8], bp
0x1400046ca  jz      short loc_140004700
0x1400046cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400046d0  inc     rax
0x1400046d3  cmp     [r8+rax*2], bp
0x1400046d8  jnz     short loc_1400046D0
0x1400046da  lea     rsi, ds:2[rax*2]
0x1400046e2  sub     rdx, rdi; DestinationSize
0x1400046e5  cmp     rdx, rsi
0x1400046e8  jb      short loc_140004700
0x1400046ea  mov     r9, rsi; SourceSize
0x1400046ed  call    memcpy_s
0x1400046f2  test    rbx, rbx
0x1400046f5  jz      short loc_1400046FA
0x1400046f7  mov     [rbx], rdi
0x1400046fa  lea     rax, [rsi+rdi]
0x1400046fe  jmp     short loc_14000470B
0x140004700  test    rbx, rbx
0x140004703  jz      short loc_140004708
0x140004705  mov     [r9], rbp
0x140004708  mov     rax, rdi
0x14000470b  mov     rbx, [rsp+28h+arg_0]
0x140004710  mov     rbp, [rsp+28h+arg_8]
0x140004715  mov     rsi, [rsp+28h+arg_10]
0x14000471a  add     rsp, 20h
0x14000471e  pop     rdi
0x14000471f  retn
```
