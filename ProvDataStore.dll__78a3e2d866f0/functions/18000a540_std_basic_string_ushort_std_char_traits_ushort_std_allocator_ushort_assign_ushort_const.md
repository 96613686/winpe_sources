# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x18000a540`
- end: `0x18000a646`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `262`
- prototype: `__int64 *__fastcall(__int64 *, char *Src)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180009430`
- `0x18000c26c`
- `0x18000da1c`
- `0x180010750`
- `0x180010ae4`

## callees

- `0x1800065dc`
- `0x18000a034`
- `0x18000a3c8`
- `0x18000a540`
- `0x180010f36`

## pseudocode

```c
__int64 *__fastcall std::wstring::assign(__int64 *a1, char *Src)
{
  __int64 *v3; // rbx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  void *v7; // rcx
  _WORD *v8; // rcx
  __int64 v9; // rcx

  v3 = a1;
  if ( *(_WORD *)Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Src[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = a1[3];
  if ( v5 < 8 )
    v6 = (char *)a1;
  else
    v6 = (char *)*a1;
  if ( Src >= v6 )
  {
    if ( v5 >= 8 )
      a1 = (__int64 *)*a1;
    if ( (char *)a1 + 2 * v3[2] > Src )
      return (__int64 *)std::wstring::assign(v3);
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5 < v4 )
  {
    std::wstring::_Copy((const void **)v3, v4, v3[2]);
    if ( !v4 )
      return v3;
    goto LABEL_16;
  }
  if ( v4 )
  {
LABEL_16:
    if ( (unsigned __int64)v3[3] < 8 )
      v7 = v3;
    else
      v7 = (void *)*v3;
    memcpy_0(v7, Src, 2 * v4);
    if ( (unsigned __int64)v3[3] < 8 )
      v9 = (__int64)v3;
    else
      v9 = *v3;
    v3[2] = v4;
    *(_WORD *)(v9 + 2 * v4) = 0;
    return v3;
  }
  if ( v5 < 8 )
    v8 = v3;
  else
    v8 = (_WORD *)*v3;
  v3[2] = 0;
  *v8 = 0;
  return v3;
}

```

## disassembly

```asm
0x18000a540  push    rbx
0x18000a542  push    rbp
0x18000a543  push    rsi
0x18000a544  push    rdi
0x18000a545  sub     rsp, 28h
0x18000a549  xor     ebp, ebp
0x18000a54b  mov     rsi, rdx
0x18000a54e  mov     rbx, rcx
0x18000a551  cmp     [rdx], bp
0x18000a554  jnz     short loc_18000A55A
0x18000a556  mov     edi, ebp
0x18000a558  jmp     short loc_18000A567
0x18000a55a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a55e  inc     rdi
0x18000a561  cmp     [rdx+rdi*2], bp
0x18000a565  jnz     short loc_18000A55E
0x18000a567  mov     rdx, [rcx+18h]
0x18000a56b  cmp     rdx, 8
0x18000a56f  jb      short loc_18000A576
0x18000a571  mov     rax, [rcx]
0x18000a574  jmp     short loc_18000A579
0x18000a576  mov     rax, rbx
0x18000a579  cmp     rsi, rax
0x18000a57c  jb      short loc_18000A5BE
0x18000a57e  cmp     rdx, 8
0x18000a582  jb      short loc_18000A587
0x18000a584  mov     rcx, [rcx]
0x18000a587  mov     rax, [rbx+10h]
0x18000a58b  lea     rcx, [rcx+rax*2]
0x18000a58f  cmp     rcx, rsi
0x18000a592  jbe     short loc_18000A5BE
0x18000a594  cmp     rdx, 8
0x18000a598  jb      short loc_18000A59F
0x18000a59a  mov     rax, [rbx]
0x18000a59d  jmp     short loc_18000A5A2
0x18000a59f  mov     rax, rbx
0x18000a5a2  sub     rsi, rax
0x18000a5a5  mov     r9, rdi
0x18000a5a8  sar     rsi, 1
0x18000a5ab  mov     rdx, rbx
0x18000a5ae  mov     r8, rsi
0x18000a5b1  mov     rcx, rbx; void *
0x18000a5b4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a5b9  mov     rbx, rax
0x18000a5bc  jmp     short loc_18000A634
0x18000a5be  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a5c8  cmp     rdi, rax
0x18000a5cb  ja      short loc_18000A640
0x18000a5cd  cmp     rdx, rdi
0x18000a5d0  jnb     short loc_18000A5F2
0x18000a5d2  mov     r8, [rbx+10h]
0x18000a5d6  mov     rdx, rdi
0x18000a5d9  mov     rcx, rbx; Src
0x18000a5dc  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a5e1  test    rdi, rdi
0x18000a5e4  jz      short loc_18000A634
0x18000a5e6  cmp     qword ptr [rbx+18h], 8
0x18000a5eb  jb      short loc_18000A60E
0x18000a5ed  mov     rcx, [rbx]
0x18000a5f0  jmp     short loc_18000A611
0x18000a5f2  test    rdi, rdi
0x18000a5f5  jnz     short loc_18000A5E6
0x18000a5f7  cmp     rdx, 8
0x18000a5fb  jb      short loc_18000A602
0x18000a5fd  mov     rcx, [rbx]
0x18000a600  jmp     short loc_18000A605
0x18000a602  mov     rcx, rbx
0x18000a605  mov     [rbx+10h], rbp
0x18000a609  mov     [rcx], bp
0x18000a60c  jmp     short loc_18000A634
0x18000a60e  mov     rcx, rbx; void *
0x18000a611  lea     r8, [rdi+rdi]; Size
0x18000a615  mov     rdx, rsi; Src
0x18000a618  call    memcpy_0
0x18000a61d  cmp     qword ptr [rbx+18h], 8
0x18000a622  jb      short loc_18000A629
0x18000a624  mov     rcx, [rbx]
0x18000a627  jmp     short loc_18000A62C
0x18000a629  mov     rcx, rbx
0x18000a62c  mov     [rbx+10h], rdi
0x18000a630  mov     [rcx+rdi*2], bp
0x18000a634  mov     rax, rbx
0x18000a637  add     rsp, 28h
0x18000a63b  pop     rdi
0x18000a63c  pop     rsi
0x18000a63d  pop     rbp
0x18000a63e  pop     rbx
0x18000a63f  retn
0x18000a640  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
