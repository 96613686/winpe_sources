# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800017c0`
- end: `0x1800019af`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z`
- size: `495`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001520`
- `0x180001670`
- `0x180002030`
- `0x180002c80`

## callees

- `0x1800017c0`
- `0x180001b10`
- `0x180001be0`
- `0x180004acc`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180001857`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180001873`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180001857`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180001873`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001886`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800018a8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001915`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000192c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000193c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000194c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001959`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001886`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1800018a8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001915`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000192c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000193c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18000194c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180001959`

## pseudocode

```c
_WORD *__fastcall std::wstring::_Copy(unsigned __int64 *Src, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r15
  unsigned __int64 *v4; // rbx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rax
  _QWORD *v8; // rsi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  void *v11; // rax
  const void *v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  char *v15; // rcx
  char *v16; // rax
  unsigned __int64 v17; // rcx
  _WORD *result; // rax
  _QWORD *v19; // rdx
  _QWORD v20[13]; // [rsp+0h] [rbp-68h] BYREF
  unsigned __int64 *v21; // [rsp+70h] [rbp+8h]
  __int64 v24; // [rsp+88h] [rbp+20h]

  v21 = Src;
  v20[4] = -2;
  v3 = a3;
  v4 = Src;
  v5 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v6 = Src[3];
    Src = (unsigned __int64 *)(v6 >> 1);
    if ( v6 >> 1 > v5 / 3 )
    {
      v5 = (unsigned __int64)Src + v6;
      if ( v6 > 0x7FFFFFFFFFFFFFFELL - (__int64)Src )
        v5 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  else
  {
    v5 = a2;
  }
  try
  {
    v7 = v5 + 1;
    if ( v5 == -1 )
    {
      v8 = 0;
    }
    else
    {
      if ( v7 > 0x7FFFFFFFFFFFFFFFLL )
        std::_Xbad_alloc();
      v9 = 2 * v7;
      if ( 2 * v7 < 0x1000 )
      {
        v8 = operator new(v9);
        if ( !v8 )
          _invalid_parameter_noinfo_noreturn();
      }
      else
      {
        v10 = v9 + 39;
        if ( v9 + 39 < v9 )
          std::_Xbad_alloc();
        v11 = operator new(v10);
        if ( !v11 )
          _invalid_parameter_noinfo_noreturn();
        v8 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v8 - 1) = v11;
      }
    }
  }
  catch ( ... )
  {
    try
    {
      v24 = std::_Wrap_alloc<std::allocator<wchar_t>>::allocate(Src, a2 + 1);
    }
    catch ( ... )
    {
      v19 = v20;
      LOBYTE(v19) = 1;
      std::wstring::_Tidy(v21, v19, 0);
      throw;
    }
    v4 = v21;
    v3 = a3;
    v5 = a2;
    v8 = (_QWORD *)v24;
  }
  if ( v3 )
  {
    if ( v4[3] < 8 )
      v12 = v4;
    else
      v12 = (const void *)*v4;
    memcpy_0(v8, v12, 2 * v3);
  }
  v13 = v4[3];
  if ( v13 >= 8 )
  {
    v14 = v13 + 1;
    v15 = (char *)*v4;
    if ( v14 > 0x7FFFFFFFFFFFFFFFLL )
      _invalid_parameter_noinfo_noreturn();
    if ( 2 * v14 >= 0x1000 )
    {
      if ( ((unsigned __int8)v15 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v16 = (char *)*((_QWORD *)v15 - 1);
      if ( v16 >= v15 )
        _invalid_parameter_noinfo_noreturn();
      v17 = v15 - v16;
      if ( v17 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v17 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v15 = v16;
    }
    operator delete(v15);
  }
  v4[3] = 7;
  v4[2] = 0;
  if ( v4[3] < 8 )
    result = v4;
  else
    result = (_WORD *)*v4;
  *result = 0;
  *v4 = (unsigned __int64)v8;
  v4[3] = v5;
  v4[2] = v3;
  if ( v4[3] >= 8 )
    v4 = v8;
  *((_WORD *)v4 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800017c0  mov     [rsp+arg_10], r8
0x1800017c5  mov     [rsp+arg_8], rdx
0x1800017ca  mov     [rsp+arg_0], rcx
0x1800017cf  push    rbx
0x1800017d0  push    rsi
0x1800017d1  push    rdi
0x1800017d2  push    r12
0x1800017d4  push    r14
0x1800017d6  push    r15
0x1800017d8  sub     rsp, 38h
0x1800017dc  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800017e5  mov     r15, r8
0x1800017e8  mov     rbx, rcx
0x1800017eb  mov     rdi, rdx
0x1800017ee  or      rdi, 7
0x1800017f2  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800017fc  cmp     rdi, r9
0x1800017ff  jbe     short loc_180001806
0x180001801  mov     rdi, rdx
0x180001804  jmp     short loc_180001837
0x180001806  mov     r8, [rcx+18h]
0x18000180a  mov     rcx, r8
0x18000180d  shr     rcx, 1
0x180001810  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000181a  mul     rdi
0x18000181d  shr     rdx, 1
0x180001820  cmp     rcx, rdx
0x180001823  jbe     short loc_180001837
0x180001825  mov     rax, r9
0x180001828  sub     rax, rcx
0x18000182b  cmp     r8, rax
0x18000182e  lea     rdi, [rcx+r8]
0x180001832  jbe     short loc_180001837
0x180001834  mov     rdi, r9
0x180001837  lea     rax, [rdi+1]
0x18000183b  mov     r12, 7FFFFFFFFFFFFFFFh
0x180001845  test    rax, rax
0x180001848  jnz     short loc_180001852
0x18000184a  xor     r14d, r14d
0x18000184d  mov     esi, r14d
0x180001850  jmp     short loc_1800018B2
0x180001852  cmp     rax, r12
0x180001855  jbe     short loc_18000185D
0x180001857  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000185d  lea     rcx, [rax+rax]; unsigned __int64
0x180001861  cmp     rcx, 1000h
0x180001868  jb      short loc_18000189B
0x18000186a  lea     rax, [rcx+27h]
0x18000186e  cmp     rax, rcx
0x180001871  ja      short loc_180001879
0x180001873  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180001879  mov     rcx, rax; unsigned __int64
0x18000187c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001881  test    rax, rax
0x180001884  jnz     short loc_18000188D
0x180001886  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000188d  lea     rsi, [rax+27h]
0x180001891  and     rsi, 0FFFFFFFFFFFFFFE0h
0x180001895  mov     [rsi-8], rax
0x180001899  jmp     short loc_1800018AF
0x18000189b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800018a0  mov     rsi, rax
0x1800018a3  test    rax, rax
0x1800018a6  jnz     short loc_1800018AF
0x1800018a8  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1800018af  xor     r14d, r14d
0x1800018b2  jmp     short loc_1800018DB
0x1800018b4  xor     r14d, r14d
0x1800018b7  mov     r12, 7FFFFFFFFFFFFFFFh
0x1800018c1  mov     rbx, [rsp+68h+arg_0]
0x1800018c6  mov     r15, [rsp+68h+arg_10]
0x1800018ce  mov     rdi, [rsp+68h+arg_8]
0x1800018d3  mov     rsi, [rsp+68h+arg_18]
0x1800018db  test    r15, r15
0x1800018de  jz      short loc_180001900
0x1800018e0  cmp     qword ptr [rbx+18h], 8
0x1800018e5  jb      short loc_1800018EC
0x1800018e7  mov     rdx, [rbx]
0x1800018ea  jmp     short loc_1800018EF
0x1800018ec  mov     rdx, rbx; Src
0x1800018ef  test    r15, r15
0x1800018f2  jz      short loc_180001900
0x1800018f4  lea     r8, [r15+r15]; Size
0x1800018f8  mov     rcx, rsi; void *
0x1800018fb  call    memcpy_0
0x180001900  mov     rax, [rbx+18h]
0x180001904  cmp     rax, 8
0x180001908  jb      short loc_180001968
0x18000190a  inc     rax
0x18000190d  mov     rcx, [rbx]
0x180001910  cmp     rax, r12
0x180001913  jbe     short loc_18000191C
0x180001915  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18000191c  add     rax, rax
0x18000191f  cmp     rax, 1000h
0x180001925  jb      short loc_180001963
0x180001927  test    cl, 1Fh
0x18000192a  jz      short loc_180001933
0x18000192c  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001933  mov     rax, [rcx-8]
0x180001937  cmp     rax, rcx
0x18000193a  jb      short loc_180001943
0x18000193c  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001943  sub     rcx, rax
0x180001946  cmp     rcx, 8
0x18000194a  jnb     short loc_180001953
0x18000194c  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001953  cmp     rcx, 27h ; '''
0x180001957  jbe     short loc_180001960
0x180001959  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180001960  mov     rcx, rax; void *
0x180001963  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001968  mov     qword ptr [rbx+18h], 7
0x180001970  mov     [rbx+10h], r14
0x180001974  cmp     qword ptr [rbx+18h], 8
0x180001979  jb      short loc_180001980
0x18000197b  mov     rax, [rbx]
0x18000197e  jmp     short loc_180001983
0x180001980  mov     rax, rbx
0x180001983  mov     [rax], r14w
0x180001987  mov     [rbx], rsi
0x18000198a  mov     [rbx+18h], rdi
0x18000198e  mov     [rbx+10h], r15
0x180001992  cmp     qword ptr [rbx+18h], 8
0x180001997  jb      short loc_18000199C
0x180001999  mov     rbx, rsi
0x18000199c  mov     [rbx+r15*2], r14w
0x1800019a1  add     rsp, 38h
0x1800019a5  pop     r15
0x1800019a7  pop     r14
0x1800019a9  pop     r12
0x1800019ab  pop     rdi
0x1800019ac  pop     rsi
0x1800019ad  pop     rbx
0x1800019ae  retn
```
