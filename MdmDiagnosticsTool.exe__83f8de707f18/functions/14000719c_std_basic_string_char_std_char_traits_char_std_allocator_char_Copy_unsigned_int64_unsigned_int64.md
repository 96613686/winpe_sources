# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000719c`
- end: `0x140007276`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `218`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007414`

## callees

- `0x140001e06`
- `0x140002dd0`
- `0x14000719c`
- `0x1400075a8`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x14000719c  mov     [rsp+arg_10], r8
0x1400071a1  mov     [rsp+arg_8], rdx
0x1400071a6  mov     [rsp+arg_0], rcx
0x1400071ab  push    rbx
0x1400071ac  push    rsi
0x1400071ad  push    rdi
0x1400071ae  push    r14
0x1400071b0  sub     rsp, 28h
0x1400071b4  mov     rsi, r8
0x1400071b7  mov     rdi, rdx
0x1400071ba  mov     rbx, rcx
0x1400071bd  or      rdx, 0Fh
0x1400071c1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400071c8  cmp     rdx, r9
0x1400071cb  ja      short loc_140007201
0x1400071cd  mov     rdi, rdx
0x1400071d0  mov     r8, [rcx+18h]
0x1400071d4  mov     rcx, r8
0x1400071d7  shr     rcx, 1
0x1400071da  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400071e4  mul     rdx
0x1400071e7  shr     rdx, 1
0x1400071ea  cmp     rcx, rdx
0x1400071ed  jbe     short loc_140007201
0x1400071ef  mov     rax, r9
0x1400071f2  sub     rax, rcx
0x1400071f5  cmp     r8, rax
0x1400071f8  lea     rdi, [rcx+r8]
0x1400071fc  jbe     short loc_140007201
0x1400071fe  mov     rdi, r9
0x140007201  lea     rcx, [rdi+1]
0x140007205  xor     edx, edx
0x140007207  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14000720c  mov     r14, rax
0x14000720f  jmp     short loc_140007225
0x140007211  mov     rbx, [rsp+48h+arg_0]
0x140007216  mov     rsi, [rsp+48h+arg_10]
0x14000721b  mov     rdi, [rsp+48h+arg_8]
0x140007220  mov     r14, [rsp+48h+arg_18]
0x140007225  test    rsi, rsi
0x140007228  jz      short loc_140007244
0x14000722a  cmp     qword ptr [rbx+18h], 10h
0x14000722f  jb      short loc_140007236
0x140007231  mov     rdx, [rbx]
0x140007234  jmp     short loc_140007239
0x140007236  mov     rdx, rbx; Src
0x140007239  mov     r8, rsi; Size
0x14000723c  mov     rcx, r14; void *
0x14000723f  call    memcpy_0
0x140007244  xor     r8d, r8d
0x140007247  mov     dl, 1
0x140007249  mov     rcx, rbx
0x14000724c  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140007251  mov     [rbx], r14
0x140007254  mov     [rbx+18h], rdi
0x140007258  mov     rax, rbx
0x14000725b  cmp     rdi, 10h
0x14000725f  cmovnb  rax, r14
0x140007263  mov     [rbx+10h], rsi
0x140007267  mov     byte ptr [rax+rsi], 0
0x14000726b  add     rsp, 28h
0x14000726f  pop     r14
0x140007271  pop     rdi
0x140007272  pop     rsi
0x140007273  pop     rbx
0x140007274  retn
```
