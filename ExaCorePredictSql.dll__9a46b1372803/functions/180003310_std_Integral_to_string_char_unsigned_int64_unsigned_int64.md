# std::_Integral_to_string<char,unsigned __int64>(unsigned __int64)

- ea: `0x180003310`
- end: `0x1800033bc`
- name: `??$_Integral_to_string@D_K@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@_K@Z`
- size: `172`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800033c0`

## callees

- `0x180003310`
- `0x1800038a0`
- `0x180003a70`

## pseudocode

```c
unsigned __int64 *__fastcall std::_Integral_to_string<char,unsigned __int64>(unsigned __int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // r9
  _BYTE v6[3]; // [rsp+3Dh] [rbp-1Bh] BYREF

  v2 = (unsigned __int64)v6;
  do
  {
    *(_BYTE *)--v2 = a2 % 0xA + 48;
    a2 /= 0xAu;
  }
  while ( a2 );
  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( (_BYTE *)v2 != v6 )
    std::string::assign(a1, v2, (size_t)&v6[-v2]);
  return a1;
}

```

## disassembly

```asm
0x180003310  push    rbx
0x180003312  sub     rsp, 50h
0x180003316  mov     rax, cs:__security_cookie
0x18000331d  xor     rax, rsp
0x180003320  mov     [rsp+58h+var_18], rax
0x180003325  xor     r10d, r10d
0x180003328  lea     r9, [rsp+58h+var_1B]
0x18000332d  mov     [rsp+58h+var_38], r10d
0x180003332  mov     r8, rdx
0x180003335  mov     rbx, rcx
0x180003338  mov     r11, 0CCCCCCCCCCCCCCCDh
0x180003342  nop     dword ptr [rax+00h]
0x180003346  nop     word ptr [rax+rax+00000000h]
0x180003350  dec     r9
0x180003353  mov     rax, r11
0x180003356  mul     r8
0x180003359  shr     rdx, 3
0x18000335d  movzx   eax, dl
0x180003360  shl     al, 2
0x180003363  lea     ecx, [rax+rdx]
0x180003366  add     cl, cl
0x180003368  sub     r8b, cl
0x18000336b  add     r8b, 30h ; '0'
0x18000336f  mov     [r9], r8b
0x180003372  mov     r8, rdx
0x180003375  test    rdx, rdx
0x180003378  jnz     short loc_180003350
0x18000337a  lea     rax, [rsp+58h+var_1B]
0x18000337f  mov     qword ptr [rbx+18h], 0Fh
0x180003387  mov     [rbx+10h], r10
0x18000338b  mov     [rbx], r10b
0x18000338e  cmp     r9, rax
0x180003391  jz      short loc_1800033A6
0x180003393  lea     r8, [rsp+58h+var_1B]
0x180003398  mov     rdx, r9; Src
0x18000339b  sub     r8, r9; Size
0x18000339e  mov     rcx, rbx; void *
0x1800033a1  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x1800033a6  mov     rax, rbx
0x1800033a9  mov     rcx, [rsp+58h+var_18]
0x1800033ae  xor     rcx, rsp; StackCookie
0x1800033b1  call    __security_check_cookie
0x1800033b6  add     rsp, 50h
0x1800033ba  pop     rbx
0x1800033bb  retn
```
