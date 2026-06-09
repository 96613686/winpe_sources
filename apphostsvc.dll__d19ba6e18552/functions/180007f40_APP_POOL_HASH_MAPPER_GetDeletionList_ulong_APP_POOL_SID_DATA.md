# APP_POOL_HASH_MAPPER::GetDeletionList(ulong *,APP_POOL_SID_DATA * *)

- ea: `0x180007f40`
- end: `0x180008215`
- name: `?GetDeletionList@APP_POOL_HASH_MAPPER@@QEAAJPEAKPEAPEAUAPP_POOL_SID_DATA@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(APP_POOL_HASH_MAPPER *__hidden this, unsigned int *, struct APP_POOL_SID_DATA **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800024ac`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000154c`
- `0x180001b60`
- `0x180007f40`
- `0x180008c1f`

## import_xrefs

- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007f8c`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007fb3`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180008020`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x1800080ef`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180008116`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000817d`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007f8c`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007fb3`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180008020`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x1800080ef`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180008116`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x18000817d`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007f97`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007fbe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007fd9`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000802b`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008046`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008054`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800080fa`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008121`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008188`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800081a3`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800081b5`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000820d`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007f97`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007fbe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007fd9`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000802b`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008046`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008054`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800080fa`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008121`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180008188`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800081a3`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x1800081b5`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18000820d`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007fa5`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180008012`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180008108`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000816f`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007fa5`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180008012`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180008108`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x18000816f`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007f7e`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x1800080e1`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007f7e`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x1800080e1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000814b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000814b`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180008005`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180008162`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180008005`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180008162`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007fcd`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18000803a`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180008197`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007fcd`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x18000803a`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180008197`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall APP_POOL_HASH_MAPPER::GetDeletionList(
        APP_POOL_HASH_MAPPER *this,
        unsigned int *a2,
        struct APP_POOL_SID_DATA **a3)
{
  unsigned int v4; // r15d
  int v5; // edi
  unsigned int v6; // r14d
  char *v7; // r12
  const struct CLKRHashTable_Iterator *v8; // rax
  const struct CLKRHashTable_Iterator *v9; // rax
  char v10; // bl
  unsigned int v11; // eax
  const struct CLKRHashTable_Iterator *v12; // rax
  unsigned __int64 v13; // rax
  bool v14; // cf
  size_t v15; // rax
  _QWORD *v16; // rax
  char *v17; // rsi
  const struct CLKRHashTable_Iterator *v18; // rax
  const struct CLKRHashTable_Iterator *v19; // rax
  __int64 v20; // rdx
  const struct CLKRHashTable_Iterator *v21; // rax
  char v22; // bl
  _BYTE v24[16]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v25; // [rsp+40h] [rbp-49h]
  __int16 v26; // [rsp+4Ch] [rbp-3Dh]
  _BYTE v27[40]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v28[96]; // [rsp+80h] [rbp-9h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = (char *)this + 8;
  v8 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin((char *)this + 8, v28);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24, v8);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
  v9 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v7, v28);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27, v9);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
  v10 = CLKRHashTable_Iterator::operator!=(v24, v27);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
  while ( v10 )
  {
    v11 = v6 + 1;
    if ( *(_DWORD *)(*(_QWORD *)(v25 + 8LL * v26 + 24) + 72LL) != -1 )
      v11 = v6;
    v6 = v11;
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v24);
    v12 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v7, v28);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27, v12);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
    v10 = CLKRHashTable_Iterator::operator!=(v24, v27);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
  if ( v6 )
  {
    v13 = (unsigned __int64)v6 << 6;
    if ( !is_mul_ok(v6, 0x40u) )
      v13 = -1;
    v14 = __CFADD__(v13, 8);
    v15 = v13 + 8;
    if ( v14 )
      v15 = -1;
    v16 = operator new(v15);
    if ( v16 )
    {
      *v16 = v6;
      v17 = (char *)(v16 + 1);
      `eh vector constructor iterator'(
        v16 + 1,
        0x40u,
        v6,
        (void (*)(void *))APP_POOL_SID_DATA::APP_POOL_SID_DATA,
        (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
    }
    else
    {
      v17 = 0;
    }
    if ( v17 )
    {
      memset_0(v17, 0, (unsigned __int64)v6 << 6);
      v18 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v7, v28);
      CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24, v18);
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
      v19 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v7, v28);
      CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27, v19);
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
      while ( 1 )
      {
        v22 = CLKRHashTable_Iterator::operator!=(v24, v27);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
        if ( !v22 )
          break;
        v20 = *(_QWORD *)(v25 + 8LL * v26 + 24);
        if ( *(_DWORD *)(v20 + 72) == -1 )
        {
          v5 = STRU::Copy((STRU *)&v17[64 * (unsigned __int64)v4], *(const unsigned __int16 **)(v20 + 40));
          if ( v5 < 0 )
          {
            CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
            goto LABEL_23;
          }
          ++v4;
        }
        CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v24);
        v21 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v7, v28);
        CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27, v21);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
      }
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
      *a2 = v6;
      *a3 = (struct APP_POOL_SID_DATA *)v17;
      if ( v5 >= 0 )
        return (unsigned int)v5;
LABEL_23:
      `eh vector destructor iterator'(
        v17,
        0x40u,
        *((_QWORD *)v17 - 1),
        (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
      operator delete(v17 - 8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp-8+arg_10], rbx
0x180007f45  mov     [rsp-8+arg_8], rdx
0x180007f4a  push    rbp
0x180007f4b  push    rsi
0x180007f4c  push    rdi
0x180007f4d  push    r12
0x180007f4f  push    r13
0x180007f51  push    r14
0x180007f53  push    r15
0x180007f55  lea     rbp, [rsp-27h]
0x180007f5a  sub     rsp, 0B0h
0x180007f61  mov     r13, r8
0x180007f64  xor     r15d, r15d
0x180007f67  mov     edi, r15d
0x180007f6a  mov     r14d, r15d
0x180007f6d  mov     [rdx], r15d
0x180007f70  mov     [r8], r15
0x180007f73  lea     r12, [rcx+8]
0x180007f77  lea     rdx, [rbp+57h+var_60]
0x180007f7b  mov     rcx, r12
0x180007f7e  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x180007f84  nop
0x180007f85  mov     rdx, rax
0x180007f88  lea     rcx, [rbp+57h+var_B0]
0x180007f8c  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007f92  nop
0x180007f93  lea     rcx, [rbp+57h+var_60]
0x180007f97  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007f9d  nop
0x180007f9e  lea     rdx, [rbp+57h+var_60]
0x180007fa2  mov     rcx, r12
0x180007fa5  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180007fab  nop
0x180007fac  mov     rdx, rax
0x180007faf  lea     rcx, [rbp+57h+var_88]
0x180007fb3  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007fb9  nop
0x180007fba  lea     rcx, [rbp+57h+var_60]
0x180007fbe  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007fc4  nop
0x180007fc5  lea     rdx, [rbp+57h+var_88]
0x180007fc9  lea     rcx, [rbp+57h+var_B0]
0x180007fcd  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180007fd3  mov     bl, al
0x180007fd5  lea     rcx, [rbp+57h+var_88]
0x180007fd9  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007fdf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007fe3  jmp     short loc_18000804C
0x180007fe5  movsx   rcx, [rbp+57h+var_94]
0x180007fea  mov     rax, [rbp+57h+var_A0]
0x180007fee  mov     rcx, [rax+rcx*8+18h]
0x180007ff3  lea     eax, [r14+1]
0x180007ff7  cmp     [rcx+48h], esi
0x180007ffa  cmovnz  eax, r14d
0x180007ffe  mov     r14d, eax
0x180008001  lea     rcx, [rbp+57h+var_B0]
0x180008005  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18000800b  lea     rdx, [rbp+57h+var_60]
0x18000800f  mov     rcx, r12
0x180008012  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180008018  nop
0x180008019  mov     rdx, rax
0x18000801c  lea     rcx, [rbp+57h+var_88]
0x180008020  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180008026  nop
0x180008027  lea     rcx, [rbp+57h+var_60]
0x18000802b  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180008031  nop
0x180008032  lea     rdx, [rbp+57h+var_88]
0x180008036  lea     rcx, [rbp+57h+var_B0]
0x18000803a  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180008040  mov     bl, al
0x180008042  lea     rcx, [rbp+57h+var_88]
0x180008046  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000804c  test    bl, bl
0x18000804e  jnz     short loc_180007FE5
0x180008050  lea     rcx, [rbp+57h+var_B0]
0x180008054  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000805a  test    r14d, r14d
0x18000805d  jz      loc_1800081EC
0x180008063  mov     ebx, r14d
0x180008066  mov     eax, 40h ; '@'
0x18000806b  mul     rbx
0x18000806e  cmovb   rax, rsi
0x180008072  add     rax, 8
0x180008076  cmovb   rax, rsi
0x18000807a  mov     rcx, rax; Size
0x18000807d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008082  mov     [rbp+57h+arg_0], rax
0x180008086  lea     rcx, ??1APP_POOL_SID_DATA@@QEAA@XZ; APP_POOL_SID_DATA::~APP_POOL_SID_DATA(void)
0x18000808d  test    rax, rax
0x180008090  jz      short loc_1800080B7
0x180008092  mov     [rax], rbx
0x180008095  lea     rsi, [rax+8]
0x180008099  mov     [rsp+0E0h+var_C0], rcx; void (*)(void *)
0x18000809e  lea     r9, ??0APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x1800080a5  mov     r8d, ebx; unsigned __int64
0x1800080a8  mov     edx, 40h ; '@'; unsigned __int64
0x1800080ad  mov     rcx, rsi; void *
0x1800080b0  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800080b5  jmp     short loc_1800080BA
0x1800080b7  mov     rsi, r15
0x1800080ba  test    rsi, rsi
0x1800080bd  jnz     short loc_1800080C9
0x1800080bf  mov     edi, 8007000Eh
0x1800080c4  jmp     loc_1800081EC
0x1800080c9  shl     rbx, 6
0x1800080cd  mov     r8, rbx; Size
0x1800080d0  xor     edx, edx; Val
0x1800080d2  mov     rcx, rsi; void *
0x1800080d5  call    memset_0
0x1800080da  lea     rdx, [rbp+57h+var_60]
0x1800080de  mov     rcx, r12
0x1800080e1  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x1800080e7  nop
0x1800080e8  mov     rdx, rax
0x1800080eb  lea     rcx, [rbp+57h+var_B0]
0x1800080ef  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x1800080f5  nop
0x1800080f6  lea     rcx, [rbp+57h+var_60]
0x1800080fa  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180008100  nop
0x180008101  lea     rdx, [rbp+57h+var_60]
0x180008105  mov     rcx, r12
0x180008108  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x18000810e  nop
0x18000810f  mov     rdx, rax
0x180008112  lea     rcx, [rbp+57h+var_88]
0x180008116  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x18000811c  nop
0x18000811d  lea     rcx, [rbp+57h+var_60]
0x180008121  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180008127  jmp     short loc_18000818F
0x180008129  movsx   rcx, [rbp+57h+var_94]
0x18000812e  mov     rax, [rbp+57h+var_A0]
0x180008132  mov     rdx, [rax+rcx*8+18h]
0x180008137  cmp     dword ptr [rdx+48h], 0FFFFFFFFh
0x18000813b  jnz     short loc_18000815E
0x18000813d  mov     ecx, r15d
0x180008140  shl     rcx, 6
0x180008144  add     rcx, rsi
0x180008147  mov     rdx, [rdx+28h]
0x18000814b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008151  mov     edi, eax
0x180008153  test    eax, eax
0x180008155  js      loc_180008209
0x18000815b  inc     r15d
0x18000815e  lea     rcx, [rbp+57h+var_B0]
0x180008162  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x180008168  lea     rdx, [rbp+57h+var_60]
0x18000816c  mov     rcx, r12
0x18000816f  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180008175  nop
0x180008176  mov     rdx, rax
0x180008179  lea     rcx, [rbp+57h+var_88]
0x18000817d  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180008183  nop
0x180008184  lea     rcx, [rbp+57h+var_60]
0x180008188  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x18000818e  nop
0x18000818f  lea     rdx, [rbp+57h+var_88]
0x180008193  lea     rcx, [rbp+57h+var_B0]
0x180008197  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x18000819d  mov     bl, al
0x18000819f  lea     rcx, [rbp+57h+var_88]
0x1800081a3  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x1800081a9  test    bl, bl
0x1800081ab  jnz     loc_180008129
0x1800081b1  lea     rcx, [rbp+57h+var_B0]
0x1800081b5  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x1800081bb  mov     rax, [rbp+57h+arg_8]
0x1800081bf  mov     [rax], r14d
0x1800081c2  mov     [r13+0], rsi
0x1800081c6  test    edi, edi
0x1800081c8  jns     short loc_1800081EC
0x1800081ca  lea     r9, ??1APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x1800081d1  mov     r8, [rsi-8]; unsigned __int64
0x1800081d5  mov     edx, 40h ; '@'; unsigned __int64
0x1800081da  mov     rcx, rsi; void *
0x1800081dd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800081e2  lea     rcx, [rsi-8]; Block
0x1800081e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800081eb  nop
0x1800081ec  mov     eax, edi
0x1800081ee  mov     rbx, [rsp+0E0h+arg_10]
0x1800081f6  add     rsp, 0B0h
0x1800081fd  pop     r15
0x1800081ff  pop     r14
0x180008201  pop     r13
0x180008203  pop     r12
0x180008205  pop     rdi
0x180008206  pop     rsi
0x180008207  pop     rbp
0x180008208  retn
0x180008209  lea     rcx, [rbp+57h+var_B0]
0x18000820d  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180008213  jmp     short loc_1800081CA
```
