# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180003640`
- end: `0x1800037e2`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `418`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002f10`
- `0x180003080`
- `0x180003470`
- `0x1800038a0`

## callees

- `0x180001b10`
- `0x180001be0`
- `0x180003640`
- `0x180004acc`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800036cd`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1800036cd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800036e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003702`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003760`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003770`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003780`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000378d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800036e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003702`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003760`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003770`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180003780`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000378d`

## pseudocode

```c
_BYTE *__fastcall std::string::_Copy(unsigned __int64 *Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 *v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rsi
  unsigned __int64 v10; // rax
  void *v11; // rax
  const void *v12; // rdx
  unsigned __int64 v13; // rax
  char *v14; // rcx
  char *v15; // rax
  unsigned __int64 v16; // rcx
  _BYTE *result; // rax
  _QWORD *v18; // rdx
  _QWORD v19[11]; // [rsp+0h] [rbp-58h] BYREF
  __int64 v23; // [rsp+78h] [rbp+20h]

  v19[4] = -2;
  v3 = a3;
  v4 = Src;
  v5 = a2 | 0xF;
  if ( (a2 | 0xF) == 0xFFFFFFFFFFFFFFFFuLL )
  {
    v5 = a2;
  }
  else
  {
    v6 = Src[3];
    v7 = v6 >> 1;
    if ( v6 >> 1 > v5 / 3 )
    {
      v5 = -2;
      if ( v6 <= -2LL - v7 )
        v5 = v7 + v6;
    }
  }
  try
  {
    v8 = v5 + 1;
    if ( v5 == -1 )
    {
      v9 = 0;
    }
    else if ( v8 < 0x1000 )
    {
      v9 = operator new(v8);
      if ( !v9 )
        _invalid_parameter_noinfo_noreturn();
    }
    else
    {
      v10 = v5 + 40;
      if ( v5 + 40 < v5 + 1 )
        std::_Xbad_alloc();
      v11 = operator new(v10);
      if ( !v11 )
        _invalid_parameter_noinfo_noreturn();
      v9 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v9 - 1) = v11;
    }
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Wrap_alloc<std::allocator<char>>::allocate(v8, a2 + 1);
    }
    catch ( ... )
    {
      v18 = v19;
      LOBYTE(v18) = 1;
      std::string::_Tidy(Src, v18, 0);
      throw;
    }
    v4 = Src;
    v3 = a3;
    v5 = a2;
    v9 = (_QWORD *)v23;
  }
  if ( v3 )
  {
    if ( v4[3] < 0x10 )
      v12 = v4;
    else
      v12 = (const void *)*v4;
    memcpy_0(v9, v12, v3);
  }
  v13 = v4[3];
  if ( v13 >= 0x10 )
  {
    v14 = (char *)*v4;
    if ( v13 + 1 >= 0x1000 )
    {
      if ( ((unsigned __int8)v14 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v15 = (char *)*((_QWORD *)v14 - 1);
      if ( v15 >= v14 )
        _invalid_parameter_noinfo_noreturn();
      v16 = v14 - v15;
      if ( v16 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v16 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v14 = v15;
    }
    operator delete(v14);
  }
  v4[3] = 15;
  v4[2] = 0;
  if ( v4[3] < 0x10 )
    result = v4;
  else
    result = (_BYTE *)*v4;
  *result = 0;
  *v4 = (unsigned __int64)v9;
  v4[3] = v5;
  v4[2] = v3;
  if ( v4[3] >= 0x10 )
    v4 = v9;
  *((_BYTE *)v4 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180003640  mov     [rsp+arg_10], r8
0x180003645  mov     [rsp+arg_8], rdx
0x18000364a  mov     [rsp+arg_0], rcx
0x18000364f  push    rbx
0x180003650  push    rsi
0x180003651  push    rdi
0x180003652  push    r14
0x180003654  sub     rsp, 38h
0x180003658  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180003661  mov     r14, r8
0x180003664  mov     rbx, rcx
0x180003667  mov     rdi, rdx
0x18000366a  or      rdi, 0Fh
0x18000366e  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180003672  jbe     short loc_180003679
0x180003674  mov     rdi, rdx
0x180003677  jmp     short loc_1800036AE
0x180003679  mov     r8, [rcx+18h]
0x18000367d  mov     rcx, r8
0x180003680  shr     rcx, 1
0x180003683  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000368d  mul     rdi
0x180003690  shr     rdx, 1
0x180003693  cmp     rcx, rdx
0x180003696  jbe     short loc_1800036AE
0x180003698  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x18000369f  mov     rax, rdi
0x1800036a2  sub     rax, rcx
0x1800036a5  cmp     r8, rax
0x1800036a8  ja      short loc_1800036AE
0x1800036aa  lea     rdi, [rcx+r8]
0x1800036ae  lea     rcx, [rdi+1]; unsigned __int64
0x1800036b2  test    rcx, rcx
0x1800036b5  jnz     short loc_1800036BB
0x1800036b7  xor     esi, esi
0x1800036b9  jmp     short loc_180003709
0x1800036bb  cmp     rcx, 1000h
0x1800036c2  jb      short loc_1800036F5
0x1800036c4  lea     rax, [rcx+27h]
0x1800036c8  cmp     rax, rcx
0x1800036cb  ja      short loc_1800036D3
0x1800036cd  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800036d3  mov     rcx, rax; unsigned __int64
0x1800036d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036db  test    rax, rax
0x1800036de  jnz     short loc_1800036E7
0x1800036e0  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800036e7  lea     rsi, [rax+27h]
0x1800036eb  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800036ef  mov     [rsi-8], rax
0x1800036f3  jmp     short loc_180003709
0x1800036f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036fa  mov     rsi, rax
0x1800036fd  test    rax, rax
0x180003700  jnz     short loc_180003709
0x180003702  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003709  jmp     short loc_18000371F
0x18000370b  mov     rbx, [rsp+58h+arg_0]
0x180003710  mov     r14, [rsp+58h+arg_10]
0x180003715  mov     rdi, [rsp+58h+arg_8]
0x18000371a  mov     rsi, [rsp+58h+arg_18]
0x18000371f  test    r14, r14
0x180003722  jz      short loc_180003743
0x180003724  cmp     qword ptr [rbx+18h], 10h
0x180003729  jb      short loc_180003730
0x18000372b  mov     rdx, [rbx]
0x18000372e  jmp     short loc_180003733
0x180003730  mov     rdx, rbx; Src
0x180003733  test    r14, r14
0x180003736  jz      short loc_180003743
0x180003738  mov     r8, r14; Size
0x18000373b  mov     rcx, rsi; void *
0x18000373e  call    memcpy_0
0x180003743  mov     rax, [rbx+18h]
0x180003747  cmp     rax, 10h
0x18000374b  jb      short loc_18000379C
0x18000374d  inc     rax
0x180003750  mov     rcx, [rbx]
0x180003753  cmp     rax, 1000h
0x180003759  jb      short loc_180003797
0x18000375b  test    cl, 1Fh
0x18000375e  jz      short loc_180003767
0x180003760  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003767  mov     rax, [rcx-8]
0x18000376b  cmp     rax, rcx
0x18000376e  jb      short loc_180003777
0x180003770  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003777  sub     rcx, rax
0x18000377a  cmp     rcx, 8
0x18000377e  jnb     short loc_180003787
0x180003780  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003787  cmp     rcx, 27h ; '''
0x18000378b  jbe     short loc_180003794
0x18000378d  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180003794  mov     rcx, rax; void *
0x180003797  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000379c  mov     qword ptr [rbx+18h], 0Fh
0x1800037a4  mov     qword ptr [rbx+10h], 0
0x1800037ac  cmp     qword ptr [rbx+18h], 10h
0x1800037b1  jb      short loc_1800037B8
0x1800037b3  mov     rax, [rbx]
0x1800037b6  jmp     short loc_1800037BB
0x1800037b8  mov     rax, rbx
0x1800037bb  mov     byte ptr [rax], 0
0x1800037be  mov     [rbx], rsi
0x1800037c1  mov     [rbx+18h], rdi
0x1800037c5  mov     [rbx+10h], r14
0x1800037c9  cmp     qword ptr [rbx+18h], 10h
0x1800037ce  jb      short loc_1800037D3
0x1800037d0  mov     rbx, rsi
0x1800037d3  mov     byte ptr [rbx+r14], 0
0x1800037d8  add     rsp, 38h
0x1800037dc  pop     r14
0x1800037de  pop     rdi
0x1800037df  pop     rsi
0x1800037e0  pop     rbx
0x1800037e1  retn
```
