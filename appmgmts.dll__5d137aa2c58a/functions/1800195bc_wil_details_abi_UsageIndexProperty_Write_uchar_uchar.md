# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800195bc`
- end: `0x1800196a4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017718`

## callees

- `0x180001fe6`
- `0x1800195bc`
- `0x180019c40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001961f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001961f`

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
0x1800195bc  push    rbx
0x1800195be  push    rbp
0x1800195bf  push    rsi
0x1800195c0  push    rdi
0x1800195c1  push    r14
0x1800195c3  push    r15
0x1800195c5  sub     rsp, 28h
0x1800195c9  mov     al, [rcx+2]
0x1800195cc  xor     ebp, ebp
0x1800195ce  mov     r9, [rdx]
0x1800195d1  mov     rdi, r8
0x1800195d4  mov     r15, rdx
0x1800195d7  mov     rsi, rcx
0x1800195da  cmp     al, 1
0x1800195dc  jnz     short loc_1800195FA
0x1800195de  lea     rbx, [r9+2]
0x1800195e2  cmp     rbx, r8
0x1800195e5  ja      loc_180019675
0x1800195eb  test    r9, r9
0x1800195ee  jz      short loc_18001961F
0x1800195f0  movzx   eax, word ptr [rcx+4]
0x1800195f4  mov     [r9], ax
0x1800195f8  jmp     short loc_180019635
0x1800195fa  cmp     al, 2
0x1800195fc  jnz     short loc_180019632
0x1800195fe  lea     rbx, [r9+4]
0x180019602  cmp     rbx, rdi
0x180019605  ja      short loc_180019675
0x180019607  test    r9, r9
0x18001960a  jz      short loc_18001961F
0x18001960c  lea     rax, [rcx+4]
0x180019610  test    rax, rax
0x180019613  jz      short loc_18001961C
0x180019615  mov     eax, [rax]
0x180019617  mov     [r9], eax
0x18001961a  jmp     short loc_180019635
0x18001961c  mov     [r9], eax
0x18001961f  call    cs:__imp__o__errno
0x180019625  mov     dword ptr [rax], 16h
0x18001962b  call    _invalid_parameter_noinfo
0x180019630  jmp     short loc_180019635
0x180019632  mov     rbx, r9
0x180019635  cmp     [rsi], bp
0x180019638  jnz     short loc_180019663
0x18001963a  lea     r14, [rbx+2]
0x18001963e  cmp     r14, rdi
0x180019641  ja      short loc_180019675
0x180019643  lea     rbp, [rsi+8]
0x180019647  mov     rdx, rdi
0x18001964a  sub     rdx, rbx; DestinationSize
0x18001964d  mov     r8, rbp; Source
0x180019650  mov     r9d, 2; SourceSize
0x180019656  mov     rcx, rbx; Destination
0x180019659  call    memcpy_s
0x18001965e  mov     rbx, r14
0x180019661  jmp     short loc_180019667
0x180019663  lea     rbp, [rsi+8]
0x180019667  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18001966c  lea     rax, [r9+rbx]
0x180019670  cmp     rax, rdi
0x180019673  jbe     short loc_180019679
0x180019675  xor     al, al
0x180019677  jmp     short loc_180019697
0x180019679  mov     r8, [rsi+18h]; Source
0x18001967d  sub     rdi, rbx
0x180019680  mov     rdx, rdi; DestinationSize
0x180019683  mov     rcx, rbx; Destination
0x180019686  call    memcpy_s
0x18001968b  movzx   ecx, word ptr [rbp+0]
0x18001968f  mov     al, 1
0x180019691  add     rcx, rbx
0x180019694  mov     [r15], rcx
0x180019697  add     rsp, 28h
0x18001969b  pop     r15
0x18001969d  pop     r14
0x18001969f  pop     rdi
0x1800196a0  pop     rsi
0x1800196a1  pop     rbp
0x1800196a2  pop     rbx
0x1800196a3  retn
```
