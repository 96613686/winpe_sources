# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006710`
- end: `0x140006823`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140003d20`
- `0x14000704c`
- `0x1400089b4`
- `0x140008ca8`
- `0x140008db0`
- `0x140008ec4`
- `0x140009fb4`
- `0x14000a0e4`
- `0x14000a640`

## callees

- `0x1400016e8`
- `0x1400017a0`
- `0x140003356`
- `0x140006710`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400067ef`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400067ef`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140006710  mov     [rsp+arg_10], r8
0x140006715  mov     [rsp+arg_8], rdx
0x14000671a  mov     [rsp+arg_0], rcx
0x14000671f  push    rbx
0x140006720  push    rsi
0x140006721  push    rdi
0x140006722  push    r14
0x140006724  push    r15
0x140006726  sub     rsp, 20h
0x14000672a  mov     r15, r8
0x14000672d  mov     rdi, rdx
0x140006730  mov     rbx, rcx
0x140006733  or      rdx, 7
0x140006737  mov     r9, 7FFFFFFFFFFFFFFEh
0x140006741  cmp     rdx, r9
0x140006744  ja      short loc_14000677A
0x140006746  mov     rdi, rdx
0x140006749  mov     r8, [rcx+18h]
0x14000674d  mov     rcx, r8
0x140006750  shr     rcx, 1
0x140006753  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000675d  mul     rdx
0x140006760  shr     rdx, 1
0x140006763  cmp     rcx, rdx
0x140006766  jbe     short loc_14000677A
0x140006768  mov     rax, r9
0x14000676b  sub     rax, rcx
0x14000676e  cmp     r8, rax
0x140006771  lea     rdi, [rcx+r8]
0x140006775  jbe     short loc_14000677A
0x140006777  mov     rdi, r9
0x14000677a  lea     rcx, [rdi+1]
0x14000677e  xor     esi, esi
0x140006780  test    rcx, rcx
0x140006783  jz      short loc_1400067AA
0x140006785  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000678f  cmp     rcx, rax
0x140006792  ja      loc_14000681C
0x140006798  add     rcx, rcx; Size
0x14000679b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400067a0  mov     r14, rax
0x1400067a3  test    rax, rax
0x1400067a6  jz      short loc_14000681C
0x1400067a8  jmp     short loc_1400067AD
0x1400067aa  mov     r14, rsi
0x1400067ad  jmp     short loc_1400067C5
0x1400067af  xor     esi, esi
0x1400067b1  mov     rbx, [rsp+48h+arg_0]
0x1400067b6  mov     r15, [rsp+48h+arg_10]
0x1400067bb  mov     rdi, [rsp+48h+arg_8]
0x1400067c0  mov     r14, [rsp+48h+arg_18]
0x1400067c5  test    r15, r15
0x1400067c8  jz      short loc_1400067E5
0x1400067ca  cmp     qword ptr [rbx+18h], 8
0x1400067cf  jb      short loc_1400067D6
0x1400067d1  mov     rdx, [rbx]
0x1400067d4  jmp     short loc_1400067D9
0x1400067d6  mov     rdx, rbx; Src
0x1400067d9  lea     r8, [r15+r15]; Size
0x1400067dd  mov     rcx, r14; void *
0x1400067e0  call    memcpy_0
0x1400067e5  cmp     qword ptr [rbx+18h], 8
0x1400067ea  jb      short loc_1400067F5
0x1400067ec  mov     rcx, [rbx]
0x1400067ef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400067f5  lea     rax, [rbx+10h]
0x1400067f9  mov     [rbx], r14
0x1400067fc  mov     [rbx+18h], rdi
0x140006800  cmp     rdi, 8
0x140006804  cmovnb  rbx, r14
0x140006808  mov     [rax], r15
0x14000680b  mov     [rbx+r15*2], si
0x140006810  add     rsp, 20h
0x140006814  pop     r15
0x140006816  pop     r14
0x140006818  pop     rdi
0x140006819  pop     rsi
0x14000681a  pop     rbx
0x14000681b  retn
0x14000681c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
