# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140008184`
- end: `0x14000826c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000715c`

## callees

- `0x140001eae`
- `0x140005808`
- `0x140008184`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400081e7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400081e7`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x140008184  push    rbx
0x140008186  push    rbp
0x140008187  push    rsi
0x140008188  push    rdi
0x140008189  push    r14
0x14000818b  push    r15
0x14000818d  sub     rsp, 28h
0x140008191  mov     al, [rcx+2]
0x140008194  xor     ebp, ebp
0x140008196  mov     r9, [rdx]
0x140008199  mov     rdi, r8
0x14000819c  mov     r15, rdx
0x14000819f  mov     rsi, rcx
0x1400081a2  cmp     al, 1
0x1400081a4  jnz     short loc_1400081C2
0x1400081a6  lea     rbx, [r9+2]
0x1400081aa  cmp     rbx, r8
0x1400081ad  ja      loc_14000823D
0x1400081b3  test    r9, r9
0x1400081b6  jz      short loc_1400081E7
0x1400081b8  movzx   eax, word ptr [rcx+4]
0x1400081bc  mov     [r9], ax
0x1400081c0  jmp     short loc_1400081FD
0x1400081c2  cmp     al, 2
0x1400081c4  jnz     short loc_1400081FA
0x1400081c6  lea     rbx, [r9+4]
0x1400081ca  cmp     rbx, rdi
0x1400081cd  ja      short loc_14000823D
0x1400081cf  test    r9, r9
0x1400081d2  jz      short loc_1400081E7
0x1400081d4  lea     rax, [rcx+4]
0x1400081d8  test    rax, rax
0x1400081db  jz      short loc_1400081E4
0x1400081dd  mov     eax, [rax]
0x1400081df  mov     [r9], eax
0x1400081e2  jmp     short loc_1400081FD
0x1400081e4  mov     [r9], eax
0x1400081e7  call    cs:__imp__o__errno
0x1400081ed  mov     dword ptr [rax], 16h
0x1400081f3  call    _invalid_parameter_noinfo
0x1400081f8  jmp     short loc_1400081FD
0x1400081fa  mov     rbx, r9
0x1400081fd  cmp     [rsi], bp
0x140008200  jnz     short loc_14000822B
0x140008202  lea     r14, [rbx+2]
0x140008206  cmp     r14, rdi
0x140008209  ja      short loc_14000823D
0x14000820b  lea     rbp, [rsi+8]
0x14000820f  mov     rdx, rdi
0x140008212  sub     rdx, rbx; DestinationSize
0x140008215  mov     r8, rbp; Source
0x140008218  mov     r9d, 2; SourceSize
0x14000821e  mov     rcx, rbx; Destination
0x140008221  call    memcpy_s
0x140008226  mov     rbx, r14
0x140008229  jmp     short loc_14000822F
0x14000822b  lea     rbp, [rsi+8]
0x14000822f  movzx   r9d, word ptr [rbp+0]; SourceSize
0x140008234  lea     rax, [r9+rbx]
0x140008238  cmp     rax, rdi
0x14000823b  jbe     short loc_140008241
0x14000823d  xor     al, al
0x14000823f  jmp     short loc_14000825F
0x140008241  mov     r8, [rsi+18h]; Source
0x140008245  sub     rdi, rbx
0x140008248  mov     rdx, rdi; DestinationSize
0x14000824b  mov     rcx, rbx; Destination
0x14000824e  call    memcpy_s
0x140008253  movzx   ecx, word ptr [rbp+0]
0x140008257  mov     al, 1
0x140008259  add     rcx, rbx
0x14000825c  mov     [r15], rcx
0x14000825f  add     rsp, 28h
0x140008263  pop     r15
0x140008265  pop     r14
0x140008267  pop     rdi
0x140008268  pop     rsi
0x140008269  pop     rbp
0x14000826a  pop     rbx
0x14000826b  retn
```
