# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140008188`
- end: `0x140008295`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `269`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000829c`

## callees

- `0x140001530`
- `0x140008188`
- `0x140008368`
- `0x140008568`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000821f`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000821f`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 v15; // [rsp+0h] [rbp-58h] BYREF
  void *v16; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = a1[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    v10 = 0;
    if ( v4 != -1 && (v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0) )
      std::_Xbad_alloc();
    v16 = v10;
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)&v15;
    v13 = 0;
    v14 = a2 + 1;
    if ( a2 == -1 || v14 <= 0x7FFFFFFFFFFFFFFFLL && (v13 = operator new(2 * v14)) != 0 )
    {
      v16 = v13;
      goto LABEL_10;
    }
    std::_Xbad_alloc();
LABEL_10:
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = v16;
  }
  if ( v3 )
  {
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_QWORD *)*v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = v4;
  result = v5;
  if ( v4 >= 8 )
    result = v10;
  v5[2] = v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140008188  mov     [rsp+arg_10], r8
0x14000818d  mov     [rsp+arg_8], rdx
0x140008192  mov     [rsp+arg_0], rcx
0x140008197  push    rbx
0x140008198  push    rsi
0x140008199  push    rdi
0x14000819a  push    r14
0x14000819c  push    r15
0x14000819e  sub     rsp, 30h
0x1400081a2  mov     r15, r8
0x1400081a5  mov     rbx, rdx
0x1400081a8  mov     rdi, rcx
0x1400081ab  or      rdx, 7
0x1400081af  mov     r9, 7FFFFFFFFFFFFFFEh
0x1400081b9  cmp     rdx, r9
0x1400081bc  ja      short loc_1400081F2
0x1400081be  mov     rbx, rdx
0x1400081c1  mov     r8, [rcx+18h]
0x1400081c5  mov     rcx, r8
0x1400081c8  shr     rcx, 1
0x1400081cb  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400081d5  mul     rdx
0x1400081d8  shr     rdx, 1
0x1400081db  cmp     rcx, rdx
0x1400081de  jbe     short loc_1400081F2
0x1400081e0  mov     rax, r9
0x1400081e3  sub     rax, rcx
0x1400081e6  cmp     r8, rax
0x1400081e9  lea     rbx, [rcx+r8]
0x1400081ed  jbe     short loc_1400081F2
0x1400081ef  mov     rbx, r9
0x1400081f2  lea     rcx, [rbx+1]
0x1400081f6  xor     esi, esi
0x1400081f8  mov     r14d, esi
0x1400081fb  test    rcx, rcx
0x1400081fe  jz      short loc_140008225
0x140008200  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000820a  cmp     rcx, rax
0x14000820d  ja      short loc_14000821F
0x14000820f  add     rcx, rcx; Size
0x140008212  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008217  mov     r14, rax
0x14000821a  test    rax, rax
0x14000821d  jnz     short loc_140008225
0x14000821f  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140008225  mov     [rsp+58h+var_38], r14
0x14000822a  jmp     short loc_140008242
0x14000822c  xor     esi, esi
0x14000822e  mov     rdi, [rsp+58h+arg_0]
0x140008233  mov     r15, [rsp+58h+arg_10]
0x140008238  mov     rbx, [rsp+58h+arg_8]
0x14000823d  mov     r14, [rsp+58h+var_38]
0x140008242  test    r15, r15
0x140008245  jz      short loc_140008261
0x140008247  cmp     qword ptr [rdi+18h], 8
0x14000824c  jb      short loc_140008253
0x14000824e  mov     rdx, [rdi]
0x140008251  jmp     short loc_140008256
0x140008253  mov     rdx, rdi
0x140008256  mov     r8, r15
0x140008259  mov     rcx, r14
0x14000825c  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140008261  xor     r8d, r8d
0x140008264  mov     dl, 1
0x140008266  mov     rcx, rdi
0x140008269  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000826e  mov     [rdi], r14
0x140008271  mov     [rdi+18h], rbx
0x140008275  mov     rax, rdi
0x140008278  cmp     rbx, 8
0x14000827c  cmovnb  rax, r14
0x140008280  mov     [rdi+10h], r15
0x140008284  mov     [rax+r15*2], si
0x140008289  add     rsp, 30h
0x14000828d  pop     r15
0x14000828f  pop     r14
0x140008291  pop     rdi
0x140008292  pop     rsi
0x140008293  pop     rbx
0x140008294  retn
```
