# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180009164`
- end: `0x18000926b`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009688`

## callees

- `0x180001444`
- `0x1800015e8`
- `0x180009164`
- `0x180009840`
- `0x180009a14`

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
  _QWORD *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *result; // rax
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+20h]

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
    v6 = (unsigned __int64)v16;
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
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = v20;
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
0x180009164  mov     [rsp+arg_10], r8
0x180009169  mov     [rsp+arg_8], rdx
0x18000916e  mov     [rsp+arg_0], rcx
0x180009173  push    rbx
0x180009174  push    rsi
0x180009175  push    rdi
0x180009176  push    r14
0x180009178  push    r15
0x18000917a  sub     rsp, 20h
0x18000917e  mov     r15, r8
0x180009181  mov     rbx, rdx
0x180009184  mov     rdi, rcx
0x180009187  or      rdx, 7
0x18000918b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180009195  cmp     rdx, r9
0x180009198  ja      short loc_1800091CE
0x18000919a  mov     rbx, rdx
0x18000919d  mov     r8, [rcx+18h]
0x1800091a1  mov     rcx, r8
0x1800091a4  shr     rcx, 1
0x1800091a7  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800091b1  mul     rdx
0x1800091b4  shr     rdx, 1
0x1800091b7  cmp     rcx, rdx
0x1800091ba  jbe     short loc_1800091CE
0x1800091bc  mov     rax, r9
0x1800091bf  sub     rax, rcx
0x1800091c2  cmp     r8, rax
0x1800091c5  lea     rbx, [rcx+r8]
0x1800091c9  jbe     short loc_1800091CE
0x1800091cb  mov     rbx, r9
0x1800091ce  lea     rcx, [rbx+1]
0x1800091d2  xor     esi, esi
0x1800091d4  test    rcx, rcx
0x1800091d7  jz      short loc_1800091FD
0x1800091d9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800091e3  cmp     rcx, rax
0x1800091e6  ja      short loc_1800091F8
0x1800091e8  add     rcx, rcx; Size
0x1800091eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800091f0  mov     r14, rax
0x1800091f3  test    rax, rax
0x1800091f6  jnz     short loc_180009200
0x1800091f8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800091fd  mov     r14, rsi
0x180009200  jmp     short loc_180009218
0x180009202  xor     esi, esi
0x180009204  mov     rdi, [rsp+48h+arg_0]
0x180009209  mov     r15, [rsp+48h+arg_10]
0x18000920e  mov     rbx, [rsp+48h+arg_8]
0x180009213  mov     r14, [rsp+48h+arg_18]
0x180009218  test    r15, r15
0x18000921b  jz      short loc_180009237
0x18000921d  cmp     qword ptr [rdi+18h], 8
0x180009222  jb      short loc_180009229
0x180009224  mov     rdx, [rdi]
0x180009227  jmp     short loc_18000922C
0x180009229  mov     rdx, rdi
0x18000922c  mov     r8, r15
0x18000922f  mov     rcx, r14
0x180009232  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180009237  xor     r8d, r8d
0x18000923a  mov     dl, 1
0x18000923c  mov     rcx, rdi
0x18000923f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009244  mov     [rdi], r14
0x180009247  mov     [rdi+18h], rbx
0x18000924b  mov     rax, rdi
0x18000924e  cmp     rbx, 8
0x180009252  cmovnb  rax, r14
0x180009256  mov     [rdi+10h], r15
0x18000925a  mov     [rax+r15*2], si
0x18000925f  add     rsp, 20h
0x180009263  pop     r15
0x180009265  pop     r14
0x180009267  pop     rdi
0x180009268  pop     rsi
0x180009269  pop     rbx
0x18000926a  retn
```
