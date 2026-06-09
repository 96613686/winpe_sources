# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006e80`
- end: `0x140006f87`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `263`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140007098`

## callees

- `0x1400014b4`
- `0x140001658`
- `0x140006e80`
- `0x140007204`
- `0x140007998`

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
0x140006e80  mov     [rsp+arg_10], r8
0x140006e85  mov     [rsp+arg_8], rdx
0x140006e8a  mov     [rsp+arg_0], rcx
0x140006e8f  push    rbx
0x140006e90  push    rsi
0x140006e91  push    rdi
0x140006e92  push    r14
0x140006e94  push    r15
0x140006e96  sub     rsp, 20h
0x140006e9a  mov     r15, r8
0x140006e9d  mov     rbx, rdx
0x140006ea0  mov     rdi, rcx
0x140006ea3  or      rdx, 7
0x140006ea7  mov     r9, 7FFFFFFFFFFFFFFEh
0x140006eb1  cmp     rdx, r9
0x140006eb4  ja      short loc_140006EEA
0x140006eb6  mov     rbx, rdx
0x140006eb9  mov     r8, [rcx+18h]
0x140006ebd  mov     rcx, r8
0x140006ec0  shr     rcx, 1
0x140006ec3  mov     rax, 0AAAAAAAAAAAAAAABh
0x140006ecd  mul     rdx
0x140006ed0  shr     rdx, 1
0x140006ed3  cmp     rcx, rdx
0x140006ed6  jbe     short loc_140006EEA
0x140006ed8  mov     rax, r9
0x140006edb  sub     rax, rcx
0x140006ede  cmp     r8, rax
0x140006ee1  lea     rbx, [rcx+r8]
0x140006ee5  jbe     short loc_140006EEA
0x140006ee7  mov     rbx, r9
0x140006eea  lea     rcx, [rbx+1]
0x140006eee  xor     esi, esi
0x140006ef0  test    rcx, rcx
0x140006ef3  jz      short loc_140006F19
0x140006ef5  mov     rax, 7FFFFFFFFFFFFFFFh
0x140006eff  cmp     rcx, rax
0x140006f02  ja      short loc_140006F14
0x140006f04  add     rcx, rcx; Size
0x140006f07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006f0c  mov     r14, rax
0x140006f0f  test    rax, rax
0x140006f12  jnz     short loc_140006F1C
0x140006f14  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140006f19  mov     r14, rsi
0x140006f1c  jmp     short loc_140006F34
0x140006f1e  xor     esi, esi
0x140006f20  mov     rdi, [rsp+48h+arg_0]
0x140006f25  mov     r15, [rsp+48h+arg_10]
0x140006f2a  mov     rbx, [rsp+48h+arg_8]
0x140006f2f  mov     r14, [rsp+48h+arg_18]
0x140006f34  test    r15, r15
0x140006f37  jz      short loc_140006F53
0x140006f39  cmp     qword ptr [rdi+18h], 8
0x140006f3e  jb      short loc_140006F45
0x140006f40  mov     rdx, [rdi]
0x140006f43  jmp     short loc_140006F48
0x140006f45  mov     rdx, rdi
0x140006f48  mov     r8, r15
0x140006f4b  mov     rcx, r14
0x140006f4e  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140006f53  xor     r8d, r8d
0x140006f56  mov     dl, 1
0x140006f58  mov     rcx, rdi
0x140006f5b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140006f60  mov     [rdi], r14
0x140006f63  mov     [rdi+18h], rbx
0x140006f67  mov     rax, rdi
0x140006f6a  cmp     rbx, 8
0x140006f6e  cmovnb  rax, r14
0x140006f72  mov     [rdi+10h], r15
0x140006f76  mov     [rax+r15*2], si
0x140006f7b  add     rsp, 20h
0x140006f7f  pop     r15
0x140006f81  pop     r14
0x140006f83  pop     rdi
0x140006f84  pop     rsi
0x140006f85  pop     rbx
0x140006f86  retn
```
