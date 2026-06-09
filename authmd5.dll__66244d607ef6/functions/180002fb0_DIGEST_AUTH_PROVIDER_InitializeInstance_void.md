# DIGEST_AUTH_PROVIDER::InitializeInstance(void)

- ea: `0x180002fb0`
- end: `0x180003177`
- name: `?InitializeInstance@DIGEST_AUTH_PROVIDER@@QEAAJXZ`
- size: `455`
- prototype: `__int64 __fastcall(DIGEST_AUTH_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800042d0`

## callees

- `0x180001024`
- `0x180002fb0`
- `0x1800046d8`
- `0x180004a18`
- `0x180007010`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000304c`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800030fe`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000304c`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800030fe`

## string_xrefs

- `0x18000303b`: `DIGEST_CONTEXT_CACHE`
- `0x1800030ed`: `DIGEST_CONTEXT_CACHE`

## pseudocode

```c
__int64 __fastcall DIGEST_AUTH_PROVIDER::InitializeInstance(DIGEST_AUTH_PROVIDER *this)
{
  DIGEST_AUTH_PROVIDER *v1; // rdi
  char *v2; // rax
  char *v3; // rbx
  signed int v4; // ebx
  void (__fastcall ***v5)(_QWORD, __int64); // r8
  char *v6; // rax
  char *v7; // rbx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx

  v1 = s_pDigestAuthProvider;
  (*(void (__fastcall **)(DIGEST_AUTH_PROVIDER *, __int64))(*(_QWORD *)s_pDigestAuthProvider + 64LL))(
    s_pDigestAuthProvider,
    16);
  v2 = (char *)operator new(0x60u);
  v3 = v2;
  if ( v2 )
  {
    CLKRHashTable::CLKRHashTable(
      (CLKRHashTable *)(v2 + 8),
      "DIGEST_CONTEXT_CACHE",
      (unsigned __int64 (*)(const void *))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
      (unsigned int (*)(unsigned __int64))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
      (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
      (void (*)(const void *, int))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
      4.0,
      1u,
      0,
      0);
    *(_QWORD *)v3 = &DIGEST_CONTEXT_CACHE::`vftable';
    *((_QWORD *)v3 + 11) = 0;
    *((_QWORD *)v3 + 10) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)v1 + 2) = v3;
  if ( !v3 )
    goto LABEL_5;
  v4 = DIGEST_CONTEXT_CACHE::Initialize((void **)v3, 1);
  if ( v4 < 0 )
  {
    v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v1 + 2);
    if ( v5 )
      (**v5)(*((_QWORD *)v1 + 2), 1);
    *((_QWORD *)v1 + 2) = 0;
    goto LABEL_18;
  }
  v6 = (char *)operator new(0x60u);
  v7 = v6;
  if ( v6 )
  {
    CLKRHashTable::CLKRHashTable(
      (CLKRHashTable *)(v6 + 8),
      "DIGEST_CONTEXT_CACHE",
      (unsigned __int64 (*)(const void *))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
      (unsigned int (*)(unsigned __int64))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
      (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
      (void (*)(const void *, int))CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
      4.0,
      1u,
      0,
      0);
    *(_QWORD *)v7 = &DIGEST_CONTEXT_CACHE::`vftable';
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 10) = 0;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)v1 + 3) = v7;
  if ( !v7 )
  {
LABEL_5:
    v4 = -2147024888;
LABEL_18:
    DIGEST_AUTH_PROVIDER::TerminateInstance(v1);
    return (unsigned int)v4;
  }
  v4 = DIGEST_CONTEXT_CACHE::Initialize((void **)v7, 0);
  if ( v4 < 0 )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v1 + 3);
    if ( v8 )
      (**v8)(v8, 1);
    *((_QWORD *)v1 + 3) = 0;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x180002fb0  push    rbx
0x180002fb2  push    rbp
0x180002fb3  push    rdi
0x180002fb4  push    r12
0x180002fb6  push    r13
0x180002fb8  push    r15
0x180002fba  sub     rsp, 68h
0x180002fbe  mov     rdi, cs:?s_pDigestAuthProvider@@3PEAVDIGEST_AUTH_PROVIDER@@EA; DIGEST_AUTH_PROVIDER * s_pDigestAuthProvider
0x180002fc5  mov     edx, 10h
0x180002fca  mov     rcx, rdi
0x180002fcd  movaps  [rsp+98h+var_48], xmm6
0x180002fd2  mov     rax, [rdi]
0x180002fd5  mov     rax, [rax+40h]
0x180002fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fde  mov     ecx, 60h ; '`'; Size
0x180002fe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002fe8  movsd   xmm6, cs:__real@4010000000000000
0x180002ff0  mov     rbx, rax
0x180002ff3  lea     r15, ?_AddRefRecord@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180002ffa  mov     ebp, 1
0x180002fff  lea     r12, ?_EqualKeys@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180003006  lea     r13, ??_7DIGEST_CONTEXT_CACHE@@6B@; const DIGEST_CONTEXT_CACHE::`vftable'
0x18000300d  test    rax, rax
0x180003010  jz      short loc_180003067
0x180003012  mov     [rsp+98h+var_50], 0
0x180003017  lea     rcx, [rax+8]
0x18000301b  mov     [rsp+98h+var_58], 0
0x180003023  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18000302a  mov     [rsp+98h+var_60], ebp
0x18000302e  lea     r8, ?_ExtractKey@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x180003035  movsd   [rsp+98h+var_68], xmm6
0x18000303b  lea     rdx, aDigestContextC; "DIGEST_CONTEXT_CACHE"
0x180003042  mov     [rsp+98h+var_70], r15
0x180003047  mov     [rsp+98h+var_78], r12
0x18000304c  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003052  mov     [rbx], r13
0x180003055  mov     qword ptr [rbx+58h], 0
0x18000305d  mov     qword ptr [rbx+50h], 0
0x180003065  jmp     short loc_180003069
0x180003067  xor     ebx, ebx
0x180003069  mov     [rdi+10h], rbx
0x18000306d  test    rbx, rbx
0x180003070  jnz     short loc_18000307C
0x180003072  mov     ebx, 80070008h
0x180003077  jmp     loc_180003156
0x18000307c  mov     edx, ebp; int
0x18000307e  mov     rcx, rbx; Parameter
0x180003081  call    ?Initialize@DIGEST_CONTEXT_CACHE@@QEAAJH@Z; DIGEST_CONTEXT_CACHE::Initialize(int)
0x180003086  mov     ebx, eax
0x180003088  test    eax, eax
0x18000308a  jns     short loc_1800030B2
0x18000308c  mov     r8, [rdi+10h]
0x180003090  test    r8, r8
0x180003093  jz      short loc_1800030A5
0x180003095  mov     rcx, [r8]
0x180003098  mov     edx, ebp
0x18000309a  mov     rax, [rcx]
0x18000309d  mov     rcx, r8
0x1800030a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a5  mov     qword ptr [rdi+10h], 0
0x1800030ad  jmp     loc_180003156
0x1800030b2  mov     ecx, 60h ; '`'; Size
0x1800030b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030bc  mov     rbx, rax
0x1800030bf  test    rax, rax
0x1800030c2  jz      short loc_180003119
0x1800030c4  mov     [rsp+98h+var_50], 0
0x1800030c9  lea     rcx, [rax+8]
0x1800030cd  mov     [rsp+98h+var_58], 0
0x1800030d5  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x1800030dc  mov     [rsp+98h+var_60], ebp
0x1800030e0  lea     r8, ?_ExtractKey@?$CTypedHashTable@VDIGEST_CONTEXT_CACHE@@VDIGEST_CONTEXT_CACHE_ENTRY@@PEAVDIGEST_CONTEXT_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<DIGEST_CONTEXT_CACHE,DIGEST_CONTEXT_CACHE_ENTRY,DIGEST_CONTEXT_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x1800030e7  movsd   [rsp+98h+var_68], xmm6
0x1800030ed  lea     rdx, aDigestContextC; "DIGEST_CONTEXT_CACHE"
0x1800030f4  mov     [rsp+98h+var_70], r15
0x1800030f9  mov     [rsp+98h+var_78], r12
0x1800030fe  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003104  mov     [rbx], r13
0x180003107  mov     qword ptr [rbx+58h], 0
0x18000310f  mov     qword ptr [rbx+50h], 0
0x180003117  jmp     short loc_18000311B
0x180003119  xor     ebx, ebx
0x18000311b  mov     [rdi+18h], rbx
0x18000311f  test    rbx, rbx
0x180003122  jz      loc_180003072
0x180003128  xor     edx, edx; int
0x18000312a  mov     rcx, rbx; Parameter
0x18000312d  call    ?Initialize@DIGEST_CONTEXT_CACHE@@QEAAJH@Z; DIGEST_CONTEXT_CACHE::Initialize(int)
0x180003132  mov     ebx, eax
0x180003134  test    eax, eax
0x180003136  jns     short loc_180003162
0x180003138  mov     rcx, [rdi+18h]
0x18000313c  test    rcx, rcx
0x18000313f  jz      short loc_18000314E
0x180003141  mov     rax, [rcx]
0x180003144  mov     edx, ebp
0x180003146  mov     rax, [rax]
0x180003149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314e  mov     qword ptr [rdi+18h], 0
0x180003156  mov     rcx, rdi; this
0x180003159  call    ?TerminateInstance@DIGEST_AUTH_PROVIDER@@QEAAXXZ; DIGEST_AUTH_PROVIDER::TerminateInstance(void)
0x18000315e  mov     eax, ebx
0x180003160  jmp     short loc_180003164
0x180003162  xor     eax, eax
0x180003164  movaps  xmm6, [rsp+98h+var_48]
0x180003169  add     rsp, 68h
0x18000316d  pop     r15
0x18000316f  pop     r13
0x180003171  pop     r12
0x180003173  pop     rdi
0x180003174  pop     rbp
0x180003175  pop     rbx
0x180003176  retn
```
