# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005fb4`
- end: `0x1800060c3`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000617c`

## callees

- `0x1800015e0`
- `0x180005fb4`
- `0x1800062ac`
- `0x18000670c`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180006048`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180006048`

## pseudocode

```c
const void **__fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  const void **result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  void *v24; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = (const void **)a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 24);
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
      goto LABEL_9;
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
LABEL_9:
      v10 = 0;
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
      v24 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = (const void **)a1;
    v3 = a3;
    v4 = a2;
    v10 = v24;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 8 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180005fb4  mov     [rsp+arg_10], r8
0x180005fb9  mov     [rsp+arg_8], rdx
0x180005fbe  mov     [rsp+arg_0], rcx
0x180005fc3  push    rbx
0x180005fc4  push    rsi
0x180005fc5  push    rdi
0x180005fc6  push    r14
0x180005fc8  push    r15
0x180005fca  sub     rsp, 20h
0x180005fce  mov     r15, r8
0x180005fd1  mov     rbx, rdx
0x180005fd4  mov     rdi, rcx
0x180005fd7  or      rdx, 7
0x180005fdb  mov     r9, 7FFFFFFFFFFFFFFEh
0x180005fe5  cmp     rdx, r9
0x180005fe8  ja      short loc_18000601E
0x180005fea  mov     rbx, rdx
0x180005fed  mov     r8, [rcx+18h]
0x180005ff1  mov     rcx, r8
0x180005ff4  shr     rcx, 1
0x180005ff7  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006001  mul     rdx
0x180006004  shr     rdx, 1
0x180006007  cmp     rcx, rdx
0x18000600a  jbe     short loc_18000601E
0x18000600c  mov     rax, r9
0x18000600f  sub     rax, rcx
0x180006012  cmp     r8, rax
0x180006015  lea     rbx, [rcx+r8]
0x180006019  jbe     short loc_18000601E
0x18000601b  mov     rbx, r9
0x18000601e  lea     rcx, [rbx+1]
0x180006022  xor     esi, esi
0x180006024  test    rcx, rcx
0x180006027  jz      short loc_180006054
0x180006029  mov     rax, 7FFFFFFFFFFFFFFFh
0x180006033  cmp     rcx, rax
0x180006036  ja      short loc_180006048
0x180006038  add     rcx, rcx; Size
0x18000603b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006040  mov     r14, rax
0x180006043  test    rax, rax
0x180006046  jnz     short loc_180006057
0x180006048  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000604f  nop     dword ptr [rax+rax+00h]
0x180006054  mov     r14, rsi
0x180006057  jmp     short loc_18000606F
0x180006059  xor     esi, esi
0x18000605b  mov     rdi, [rsp+48h+arg_0]
0x180006060  mov     r15, [rsp+48h+arg_10]
0x180006065  mov     rbx, [rsp+48h+arg_8]
0x18000606a  mov     r14, [rsp+48h+arg_18]
0x18000606f  test    r15, r15
0x180006072  jz      short loc_18000608E
0x180006074  cmp     qword ptr [rdi+18h], 8
0x180006079  jb      short loc_180006080
0x18000607b  mov     rdx, [rdi]
0x18000607e  jmp     short loc_180006083
0x180006080  mov     rdx, rdi
0x180006083  mov     r8, r15
0x180006086  mov     rcx, r14
0x180006089  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18000608e  xor     r8d, r8d
0x180006091  mov     dl, 1
0x180006093  mov     rcx, rdi
0x180006096  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000609b  mov     [rdi], r14
0x18000609e  mov     [rdi+18h], rbx
0x1800060a2  mov     rax, rdi
0x1800060a5  cmp     rbx, 8
0x1800060a9  cmovnb  rax, r14
0x1800060ad  mov     [rdi+10h], r15
0x1800060b1  mov     [rax+r15*2], si
0x1800060b6  add     rsp, 20h
0x1800060ba  pop     r15
0x1800060bc  pop     r14
0x1800060be  pop     rdi
0x1800060bf  pop     rsi
0x1800060c0  pop     rbx
0x1800060c1  retn
```
