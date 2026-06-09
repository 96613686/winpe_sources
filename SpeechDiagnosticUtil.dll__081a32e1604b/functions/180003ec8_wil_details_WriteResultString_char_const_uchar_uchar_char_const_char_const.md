# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003ec8`
- end: `0x180003f3d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bc0`
- `0x180009904`

## callees

- `0x180003ec8`
- `0x180006534`

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
0x180003ec8  mov     [rsp+arg_0], rbx
0x180003ecd  mov     [rsp+arg_8], rsi
0x180003ed2  push    rdi
0x180003ed3  sub     rsp, 20h
0x180003ed7  mov     rbx, r9
0x180003eda  mov     rdi, rcx
0x180003edd  cmp     rcx, rdx
0x180003ee0  jz      short loc_180003F1D
0x180003ee2  test    r8, r8
0x180003ee5  jz      short loc_180003F1D
0x180003ee7  cmp     byte ptr [r8], 0
0x180003eeb  jz      short loc_180003F1D
0x180003eed  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003ef1  inc     rax
0x180003ef4  cmp     byte ptr [r8+rax], 0
0x180003ef9  jnz     short loc_180003EF1
0x180003efb  lea     rsi, [rax+1]
0x180003eff  sub     rdx, rdi; DestinationSize
0x180003f02  cmp     rdx, rsi
0x180003f05  jb      short loc_180003F1D
0x180003f07  mov     r9, rsi; SourceSize
0x180003f0a  call    memcpy_s
0x180003f0f  test    rbx, rbx
0x180003f12  jz      short loc_180003F17
0x180003f14  mov     [rbx], rdi
0x180003f17  lea     rax, [rsi+rdi]
0x180003f1b  jmp     short loc_180003F2C
0x180003f1d  test    rbx, rbx
0x180003f20  jz      short loc_180003F29
0x180003f22  mov     qword ptr [r9], 0
0x180003f29  mov     rax, rdi
0x180003f2c  mov     rbx, [rsp+28h+arg_0]
0x180003f31  mov     rsi, [rsp+28h+arg_8]
0x180003f36  add     rsp, 20h
0x180003f3a  pop     rdi
0x180003f3b  retn
```
