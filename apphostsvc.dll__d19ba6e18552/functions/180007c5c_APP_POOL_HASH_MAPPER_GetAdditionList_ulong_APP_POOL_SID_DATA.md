# APP_POOL_HASH_MAPPER::GetAdditionList(ulong *,APP_POOL_SID_DATA * *)

- ea: `0x180007c5c`
- end: `0x180007f37`
- name: `?GetAdditionList@APP_POOL_HASH_MAPPER@@QEAAJPEAKPEAPEAUAPP_POOL_SID_DATA@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(APP_POOL_HASH_MAPPER *__hidden this, unsigned int *, struct APP_POOL_SID_DATA **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180002348`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000154c`
- `0x180001b60`
- `0x180007c5c`
- `0x180008a10`
- `0x180008c1f`

## import_xrefs

- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007ca4`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007ccb`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007d1a`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007df1`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007e18`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007e9c`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007ca4`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007ccb`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007d1a`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007df1`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007e18`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180007e9c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007caf`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007cd6`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d25`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d40`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d4e`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007dfc`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007e23`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ea7`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ec2`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ed4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007f2f`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007caf`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007cd6`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d25`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d40`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007d4e`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007dfc`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007e23`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ea7`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ec2`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007ed4`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180007f2f`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007cbd`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007d0c`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007e0a`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007e8e`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007cbd`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007d0c`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007e0a`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007e8e`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007c96`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007de3`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007c96`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180007de3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007e53`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007e53`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180007cff`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180007e81`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180007cff`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180007e81`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007d34`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007eb6`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007d34`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180007eb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall APP_POOL_HASH_MAPPER::GetAdditionList(
        APP_POOL_HASH_MAPPER *this,
        unsigned int *a2,
        struct APP_POOL_SID_DATA **a3)
{
  int SIDFromHash; // edi
  unsigned int v4; // r14d
  char *v5; // r12
  const struct CLKRHashTable_Iterator *v6; // rax
  const struct CLKRHashTable_Iterator *v7; // rax
  unsigned int v8; // eax
  const struct CLKRHashTable_Iterator *v9; // rax
  char v10; // bl
  unsigned __int64 v11; // rax
  bool v12; // cf
  size_t v13; // rax
  _QWORD *v14; // rax
  char *v15; // rsi
  unsigned int v16; // r15d
  const struct CLKRHashTable_Iterator *v17; // rax
  const struct CLKRHashTable_Iterator *v18; // rax
  __int64 v19; // rbx
  const struct CLKRHashTable_Iterator *v20; // rax
  char v21; // bl
  _BYTE v23[16]; // [rsp+38h] [rbp-59h] BYREF
  __int64 v24; // [rsp+48h] [rbp-49h]
  __int16 v25; // [rsp+54h] [rbp-3Dh]
  _BYTE v26[40]; // [rsp+60h] [rbp-31h] BYREF
  _BYTE v27[96]; // [rsp+88h] [rbp-9h] BYREF

  SIDFromHash = 0;
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v5 = (char *)this + 8;
  v6 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin((char *)this + 8, v27);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v23, v6);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
  v7 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v5, v27);
  CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26, v7);
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
  while ( 1 )
  {
    v10 = CLKRHashTable_Iterator::operator!=(v23, v26);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26);
    if ( !v10 )
      break;
    v8 = v4 + 1;
    if ( *(_DWORD *)(*(_QWORD *)(v24 + 8LL * v25 + 24) + 72LL) != 1 )
      v8 = v4;
    v4 = v8;
    CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v23);
    v9 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v5, v27);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26, v9);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
  }
  CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v23);
  if ( v4 )
  {
    v11 = (unsigned __int64)v4 << 6;
    if ( !is_mul_ok(v4, 0x40u) )
      v11 = -1;
    v12 = __CFADD__(v11, 8);
    v13 = v11 + 8;
    if ( v12 )
      v13 = -1;
    v14 = operator new(v13);
    if ( v14 )
    {
      *v14 = v4;
      v15 = (char *)(v14 + 1);
      `eh vector constructor iterator'(
        v14 + 1,
        0x40u,
        v4,
        (void (*)(void *))APP_POOL_SID_DATA::APP_POOL_SID_DATA,
        (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
    }
    else
    {
      v15 = 0;
    }
    if ( !v15 )
      return (unsigned int)-2147024882;
    v16 = 0;
    memset_0(v15, 0, (unsigned __int64)v4 << 6);
    v17 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v5, v27);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v23, v17);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
    v18 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v5, v27);
    CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26, v18);
    CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
    while ( 1 )
    {
      v21 = CLKRHashTable_Iterator::operator!=(v23, v26);
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26);
      if ( !v21 )
      {
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v23);
        *a2 = v4;
        *a3 = (struct APP_POOL_SID_DATA *)v15;
        return (unsigned int)SIDFromHash;
      }
      v19 = *(_QWORD *)(v24 + 8LL * v25 + 24);
      if ( *(_DWORD *)(v19 + 72) == 1 )
      {
        SIDFromHash = STRU::Copy((STRU *)&v15[64 * (unsigned __int64)v16], *(const unsigned __int16 **)(v19 + 40));
        if ( SIDFromHash < 0
          || (SIDFromHash = MakeSIDFromHash(*(ULONG **)(v19 + 64), (void **)&v15[64 * (unsigned __int64)v16 + 56]),
              SIDFromHash < 0) )
        {
          CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v23);
          `eh vector destructor iterator'(
            v15,
            0x40u,
            *((_QWORD *)v15 - 1),
            (void (*)(void *))APP_POOL_SID_DATA::~APP_POOL_SID_DATA);
          operator delete(v15 - 8);
          return (unsigned int)SIDFromHash;
        }
        ++v16;
      }
      CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v23);
      v20 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v5, v27);
      CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v26, v20);
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
    }
  }
  return (unsigned int)SIDFromHash;
}

```

## disassembly

```asm
0x180007c5c  mov     rax, rsp
0x180007c5f  mov     [rax+20h], rbx
0x180007c63  mov     [rax+18h], r8
0x180007c67  mov     [rax+10h], rdx
0x180007c6b  push    rbp
0x180007c6c  push    rsi
0x180007c6d  push    rdi
0x180007c6e  push    r12
0x180007c70  push    r13
0x180007c72  push    r14
0x180007c74  push    r15
0x180007c76  lea     rbp, [rax-5Fh]
0x180007c7a  sub     rsp, 0B0h
0x180007c81  xor     edi, edi
0x180007c83  xor     r14d, r14d
0x180007c86  mov     [rdx], edi
0x180007c88  mov     [r8], rdi
0x180007c8b  lea     r12, [rcx+8]
0x180007c8f  lea     rdx, [rbp+57h+var_60]
0x180007c93  mov     rcx, r12
0x180007c96  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x180007c9c  nop
0x180007c9d  mov     rdx, rax
0x180007ca0  lea     rcx, [rbp+57h+var_B0]
0x180007ca4  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007caa  nop
0x180007cab  lea     rcx, [rbp+57h+var_60]
0x180007caf  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007cb5  nop
0x180007cb6  lea     rdx, [rbp+57h+var_60]
0x180007cba  mov     rcx, r12
0x180007cbd  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180007cc3  nop
0x180007cc4  mov     rdx, rax
0x180007cc7  lea     rcx, [rbp+57h+var_88]
0x180007ccb  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007cd1  nop
0x180007cd2  lea     rcx, [rbp+57h+var_60]
0x180007cd6  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007cdc  jmp     short loc_180007D2C
0x180007cde  movsx   rcx, [rbp+57h+var_94]
0x180007ce3  mov     rax, [rbp+57h+var_A0]
0x180007ce7  mov     rcx, [rax+rcx*8+18h]
0x180007cec  lea     eax, [r14+1]
0x180007cf0  cmp     dword ptr [rcx+48h], 1
0x180007cf4  cmovnz  eax, r14d
0x180007cf8  mov     r14d, eax
0x180007cfb  lea     rcx, [rbp+57h+var_B0]
0x180007cff  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x180007d05  lea     rdx, [rbp+57h+var_60]
0x180007d09  mov     rcx, r12
0x180007d0c  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180007d12  nop
0x180007d13  mov     rdx, rax
0x180007d16  lea     rcx, [rbp+57h+var_88]
0x180007d1a  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007d20  nop
0x180007d21  lea     rcx, [rbp+57h+var_60]
0x180007d25  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007d2b  nop
0x180007d2c  lea     rdx, [rbp+57h+var_88]
0x180007d30  lea     rcx, [rbp+57h+var_B0]
0x180007d34  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180007d3a  mov     bl, al
0x180007d3c  lea     rcx, [rbp+57h+var_88]
0x180007d40  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007d46  test    bl, bl
0x180007d48  jnz     short loc_180007CDE
0x180007d4a  lea     rcx, [rbp+57h+var_B0]
0x180007d4e  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007d54  test    r14d, r14d
0x180007d57  jz      loc_180007F0E
0x180007d5d  mov     ebx, r14d
0x180007d60  mov     r15d, 40h ; '@'
0x180007d66  mov     eax, r15d
0x180007d69  mul     rbx
0x180007d6c  lea     rcx, [r15-41h]
0x180007d70  cmovb   rax, rcx
0x180007d74  add     rax, 8
0x180007d78  cmovb   rax, rcx
0x180007d7c  mov     rcx, rax; Size
0x180007d7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d84  mov     [rbp+57h+arg_0], rax
0x180007d88  lea     rcx, ??1APP_POOL_SID_DATA@@QEAA@XZ; APP_POOL_SID_DATA::~APP_POOL_SID_DATA(void)
0x180007d8f  test    rax, rax
0x180007d92  jz      short loc_180007DB7
0x180007d94  mov     [rax], rbx
0x180007d97  lea     rsi, [rax+8]
0x180007d9b  mov     [rsp+20h], rcx; void (*)(void *)
0x180007da0  lea     r9, ??0APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x180007da7  mov     r8d, ebx; unsigned __int64
0x180007daa  mov     edx, r15d; unsigned __int64
0x180007dad  mov     rcx, rsi; void *
0x180007db0  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180007db5  jmp     short loc_180007DB9
0x180007db7  xor     esi, esi
0x180007db9  test    rsi, rsi
0x180007dbc  jnz     short loc_180007DC8
0x180007dbe  mov     edi, 8007000Eh
0x180007dc3  jmp     loc_180007F0E
0x180007dc8  xor     r15d, r15d
0x180007dcb  shl     rbx, 6
0x180007dcf  mov     r8, rbx; Size
0x180007dd2  xor     edx, edx; Val
0x180007dd4  mov     rcx, rsi; void *
0x180007dd7  call    memset_0
0x180007ddc  lea     rdx, [rbp+57h+var_60]
0x180007de0  mov     rcx, r12
0x180007de3  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x180007de9  nop
0x180007dea  mov     rdx, rax
0x180007ded  lea     rcx, [rbp+57h+var_B0]
0x180007df1  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007df7  nop
0x180007df8  lea     rcx, [rbp+57h+var_60]
0x180007dfc  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007e02  nop
0x180007e03  lea     rdx, [rbp+57h+var_60]
0x180007e07  mov     rcx, r12
0x180007e0a  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180007e10  nop
0x180007e11  mov     rdx, rax
0x180007e14  lea     rcx, [rbp+57h+var_88]
0x180007e18  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007e1e  nop
0x180007e1f  lea     rcx, [rbp+57h+var_60]
0x180007e23  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007e29  jmp     loc_180007EAE
0x180007e2e  movsx   rcx, [rbp+57h+var_94]
0x180007e33  mov     rax, [rbp+57h+var_A0]
0x180007e37  mov     rbx, [rax+rcx*8+18h]
0x180007e3c  cmp     dword ptr [rbx+48h], 1
0x180007e40  jnz     short loc_180007E7D
0x180007e42  mov     r13d, r15d
0x180007e45  shl     r13, 6
0x180007e49  add     r13, rsi
0x180007e4c  mov     rdx, [rbx+28h]
0x180007e50  mov     rcx, r13
0x180007e53  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007e59  mov     edi, eax
0x180007e5b  test    eax, eax
0x180007e5d  js      loc_180007F2B
0x180007e63  lea     rdx, [r13+38h]; void **
0x180007e67  mov     rcx, [rbx+40h]; struct APP_POOL_HASH *
0x180007e6b  call    ?MakeSIDFromHash@@YAJPEAUAPP_POOL_HASH@@PEAPEAX@Z; MakeSIDFromHash(APP_POOL_HASH *,void * *)
0x180007e70  mov     edi, eax
0x180007e72  test    eax, eax
0x180007e74  js      loc_180007F2B
0x180007e7a  inc     r15d
0x180007e7d  lea     rcx, [rbp+57h+var_B0]
0x180007e81  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x180007e87  lea     rdx, [rbp+57h+var_60]
0x180007e8b  mov     rcx, r12
0x180007e8e  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180007e94  nop
0x180007e95  mov     rdx, rax
0x180007e98  lea     rcx, [rbp+57h+var_88]
0x180007e9c  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180007ea2  nop
0x180007ea3  lea     rcx, [rbp+57h+var_60]
0x180007ea7  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007ead  nop
0x180007eae  lea     rdx, [rbp+57h+var_88]
0x180007eb2  lea     rcx, [rbp+57h+var_B0]
0x180007eb6  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180007ebc  mov     bl, al
0x180007ebe  lea     rcx, [rbp+57h+var_88]
0x180007ec2  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007ec8  test    bl, bl
0x180007eca  jnz     loc_180007E2E
0x180007ed0  lea     rcx, [rbp+57h+var_B0]
0x180007ed4  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007eda  mov     rax, [rbp+57h+arg_8]
0x180007ede  mov     [rax], r14d
0x180007ee1  mov     rax, [rbp+57h+arg_10]
0x180007ee5  mov     [rax], rsi
0x180007ee8  test    edi, edi
0x180007eea  jns     short loc_180007F0E
0x180007eec  lea     r9, ??1APP_POOL_SID_DATA@@QEAA@XZ; void (*)(void *)
0x180007ef3  mov     r8, [rsi-8]; unsigned __int64
0x180007ef7  mov     edx, 40h ; '@'; unsigned __int64
0x180007efc  mov     rcx, rsi; void *
0x180007eff  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007f04  lea     rcx, [rsi-8]; Block
0x180007f08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007f0d  nop
0x180007f0e  mov     eax, edi
0x180007f10  mov     rbx, [rsp+0E0h+arg_18]
0x180007f18  add     rsp, 0B0h
0x180007f1f  pop     r15
0x180007f21  pop     r14
0x180007f23  pop     r13
0x180007f25  pop     r12
0x180007f27  pop     rdi
0x180007f28  pop     rsi
0x180007f29  pop     rbp
0x180007f2a  retn
0x180007f2b  lea     rcx, [rbp+57h+var_B0]
0x180007f2f  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180007f35  jmp     short loc_180007EEC
```
