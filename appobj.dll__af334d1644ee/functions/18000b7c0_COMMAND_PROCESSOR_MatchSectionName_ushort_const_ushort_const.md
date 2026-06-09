# COMMAND_PROCESSOR::MatchSectionName(ushort const *,ushort const * *)

- ea: `0x18000b7c0`
- end: `0x18000bafb`
- name: `?MatchSectionName@COMMAND_PROCESSOR@@EEAAJPEBGPEAPEBG@Z`
- size: `827`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180003700`
- `0x180004f40`
- `0x180007498`
- `0x180007f94`
- `0x18000a91c`
- `0x18000ab4c`
- `0x18000b7c0`
- `0x18000d814`
- `0x18000d850`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000ba3d`
- `msvcrt!_wcsnicmp` at `0x18000ba3d`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::MatchSectionName(
        COMMAND_PROCESSOR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3)
{
  int IsWildcardMatch; // ebx
  SECTION_TABLE_ENTRY *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  char v10; // bl
  const unsigned __int16 *v11; // r8
  __int64 v12; // rsi
  size_t v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rax
  bool v16; // r14
  __int64 v17; // r14
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  SECTION_TABLE_ENTRY *v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int16 v25; // [rsp+54h] [rbp-ACh]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v30; // [rsp+B0h] [rbp-50h]
  int v31; // [rsp+B8h] [rbp-48h]
  __int16 v32; // [rsp+BCh] [rbp-44h]
  int v33; // [rsp+C0h] [rbp-40h]
  __int16 v34; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[510]; // [rsp+D2h] [rbp-2Eh] BYREF

  v21 = 0;
  memset_0(v35, 0, sizeof(v35));
  v31 = 512;
  v30 = &v34;
  v32 = 256;
  v33 = 0;
  v34 = 0;
  v26 = 0;
  if ( !a2 || !a3 )
  {
    IsWildcardMatch = -2147024809;
    goto LABEL_42;
  }
  IsWildcardMatch = 0;
  if ( *((_DWORD *)this + 76)
    || (IsWildcardMatch = COMMAND_PROCESSOR::LoadSectionTable((COMMAND_PROCESSOR *)((char *)this - 8)),
        IsWildcardMatch >= 0) )
  {
    if ( (unsigned int)CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,unsigned short const *,CLKRHashTable,CLKRHashTable::CIterator>::FindKey(
                         (char *)this + 232,
                         a2,
                         &v21) )
    {
      if ( *a2 == 63 )
      {
        CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,unsigned short const *,CLKRHashTable,CLKRHashTable::CIterator>::begin(
          (char *)this + 232,
          v22);
        while ( 1 )
        {
          v9 = CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,unsigned short const *,CLKRHashTable,CLKRHashTable::CIterator>::end(
                 v8,
                 v27);
          if ( v24 != *(_QWORD *)(v9 + 16) || (v10 = 0, v25 != *(_WORD *)(v9 + 28)) )
            v10 = 1;
          CLKRLinearHashTable_Iterator::_AddRef((CLKRLinearHashTable_Iterator *)v28);
          if ( !v10 )
            break;
          v11 = L"*";
          LODWORD(v21) = 0;
          v12 = *(_QWORD *)(v24 + 8LL * v25 + 24);
          if ( a2[1] )
            v11 = a2 + 1;
          IsWildcardMatch = COMMAND_PROCESSOR::IsWildcardMatch(
                              (COMMAND_PROCESSOR *)v25,
                              *(const unsigned __int16 **)(v12 + 40),
                              v11,
                              (int *)&v21);
          if ( IsWildcardMatch < 0 )
            goto LABEL_35;
          if ( (_DWORD)v21 )
          {
            IsWildcardMatch = STRU::Append((STRU *)v29, *(const unsigned __int8 **)(v12 + 40));
            if ( IsWildcardMatch < 0 )
              goto LABEL_35;
            IsWildcardMatch = STRU::Append((STRU *)v29, (const unsigned __int8 *)L"\n");
            if ( IsWildcardMatch < 0 )
              goto LABEL_35;
          }
          CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v22);
        }
        CLKRLinearHashTable_Iterator::_AddRef((CLKRLinearHashTable_Iterator *)v23);
        IsWildcardMatch = -2147024809;
        (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int16 *, _QWORD))(*(_QWORD *)this + 128LL))(
          this,
          2147942487LL,
          v30,
          0);
        goto LABEL_42;
      }
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      if ( !v13 )
      {
LABEL_39:
        IsWildcardMatch = -2147024894;
LABEL_40:
        v19 = *(_QWORD *)this;
        v26 = a2;
        (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int64, const unsigned __int16 **, _DWORD))(v19 + 144))(
          this,
          2147942402LL,
          3221226487LL,
          &v26,
          0);
        goto LABEL_42;
      }
      CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,unsigned short const *,CLKRHashTable,CLKRHashTable::CIterator>::begin(
        (char *)this + 232,
        v22);
      while ( 1 )
      {
        v15 = CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,unsigned short const *,CLKRHashTable,CLKRHashTable::CIterator>::end(
                v14,
                v27);
        v16 = v24 != *(_QWORD *)(v15 + 16) || v25 != *(_WORD *)(v15 + 28);
        CLKRLinearHashTable_Iterator::_AddRef((CLKRLinearHashTable_Iterator *)v28);
        if ( !v16 )
        {
          CLKRLinearHashTable_Iterator::_AddRef((CLKRLinearHashTable_Iterator *)v23);
          goto LABEL_39;
        }
        v17 = *(_QWORD *)(v24 + 8LL * v25 + 24);
        v18 = *(unsigned int *)(v17 + 56);
        if ( v18 > v13 )
        {
          v21 = (SECTION_TABLE_ENTRY *)(*(_QWORD *)(v17 + 40) + 2 * (v18 - v13));
          if ( !_wcsnicmp(a2, (const wchar_t *)v21, v13) && *((_WORD *)v21 - 1) == 47 )
            break;
        }
        CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v22);
      }
      *a3 = *(const unsigned __int16 **)(v17 + 40);
LABEL_35:
      CLKRLinearHashTable_Iterator::_AddRef((CLKRLinearHashTable_Iterator *)v23);
    }
    else
    {
      v7 = v21;
      *a3 = (const unsigned __int16 *)*((_QWORD *)v21 + 5);
      SECTION_TABLE_ENTRY::DereferenceSectionTableEntry(v7);
    }
  }
  if ( IsWildcardMatch == -2147024894 )
    goto LABEL_40;
LABEL_42:
  BUFFER::~BUFFER((BUFFER *)v29);
  return (unsigned int)IsWildcardMatch;
}

```

## disassembly

```asm
0x18000b7c0  mov     [rsp-8+arg_18], rbx
0x18000b7c5  push    rbp
0x18000b7c6  push    rsi
0x18000b7c7  push    rdi
0x18000b7c8  push    r12
0x18000b7ca  push    r13
0x18000b7cc  push    r14
0x18000b7ce  push    r15
0x18000b7d0  lea     rbp, [rsp-1E0h]
0x18000b7d8  sub     rsp, 2E0h
0x18000b7df  mov     rax, cs:__security_cookie
0x18000b7e6  xor     rax, rsp
0x18000b7e9  mov     [rbp+210h+var_40], rax
0x18000b7f0  mov     r12, r8
0x18000b7f3  mov     r15, rdx
0x18000b7f6  mov     r13, rcx
0x18000b7f9  xor     r14d, r14d
0x18000b7fc  xor     edx, edx; Val
0x18000b7fe  mov     [rsp+310h+var_2E0], r14
0x18000b803  mov     r8d, 1FEh; Size
0x18000b809  lea     rcx, [rbp+210h+var_23E]; void *
0x18000b80d  call    memset_0
0x18000b812  mov     [rbp+210h+var_258], 200h
0x18000b819  lea     rax, [rbp+210h+var_240]
0x18000b81d  mov     [rbp+210h+var_260], rax
0x18000b821  mov     [rbp+210h+var_254], 100h
0x18000b827  mov     [rbp+210h+var_250], r14d
0x18000b82b  mov     [rbp+210h+var_240], r14w
0x18000b830  mov     [rsp+310h+var_2B0], r14
0x18000b835  test    r15, r15
0x18000b838  jz      loc_18000BAC1
0x18000b83e  test    r12, r12
0x18000b841  jz      loc_18000BAC1
0x18000b847  lea     rcx, [r13-8]; this
0x18000b84b  mov     ebx, r14d
0x18000b84e  cmp     [rcx+138h], r14d
0x18000b855  jnz     short loc_18000B866
0x18000b857  call    ?LoadSectionTable@COMMAND_PROCESSOR@@AEAAJXZ; COMMAND_PROCESSOR::LoadSectionTable(void)
0x18000b85c  mov     ebx, eax
0x18000b85e  test    eax, eax
0x18000b860  js      loc_18000BA76
0x18000b866  lea     r14, [r13+0E8h]
0x18000b86d  mov     rdx, r15
0x18000b870  mov     rcx, r14
0x18000b873  lea     r8, [rsp+310h+var_2E0]
0x18000b878  call    ?FindKey@?$CTypedHashTable@VSECTION_TABLE@@VSECTION_TABLE_ENTRY@@PEBGVCLKRHashTable@@VCIterator@3@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVSECTION_TABLE_ENTRY@@@Z; CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,ushort const *,CLKRHashTable,CLKRHashTable::CIterator>::FindKey(ushort const * const,SECTION_TABLE_ENTRY * *)
0x18000b87d  xor     ecx, ecx
0x18000b87f  test    eax, eax
0x18000b881  jnz     short loc_18000B89A
0x18000b883  mov     rcx, [rsp+310h+var_2E0]; this
0x18000b888  mov     rax, [rcx+28h]
0x18000b88c  mov     [r12], rax
0x18000b890  call    ?DereferenceSectionTableEntry@SECTION_TABLE_ENTRY@@QEAAXXZ; SECTION_TABLE_ENTRY::DereferenceSectionTableEntry(void)
0x18000b895  jmp     loc_18000BA76
0x18000b89a  cmp     word ptr [r15], 3Fh ; '?'
0x18000b89f  jnz     loc_18000B9AB
0x18000b8a5  lea     rdx, [rsp+310h+var_2D8]
0x18000b8aa  mov     rcx, r14
0x18000b8ad  call    ?begin@?$CTypedHashTable@VSECTION_TABLE@@VSECTION_TABLE_ENTRY@@PEBGVCLKRHashTable@@VCIterator@3@@@QEAA?AViterator@1@XZ; CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,ushort const *,CLKRHashTable,CLKRHashTable::CIterator>::begin(void)
0x18000b8b2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b8b6  xor     r14d, r14d
0x18000b8b9  lea     rdx, [rsp+310h+var_2A8]
0x18000b8be  call    ?end@?$CTypedHashTable@VSECTION_TABLE@@VSECTION_TABLE_ENTRY@@PEBGVCLKRHashTable@@VCIterator@3@@@QEAA?AViterator@1@XZ; CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,ushort const *,CLKRHashTable,CLKRHashTable::CIterator>::end(void)
0x18000b8c3  mov     rcx, [rax+10h]
0x18000b8c7  cmp     [rsp+310h+var_2C8], rcx
0x18000b8cc  jnz     short loc_18000B8DC
0x18000b8ce  movzx   eax, word ptr [rax+1Ch]
0x18000b8d2  mov     bl, r14b
0x18000b8d5  cmp     [rsp+310h+var_2BC], ax
0x18000b8da  jz      short loc_18000B8DE
0x18000b8dc  mov     bl, 1
0x18000b8de  mov     edx, edi; int
0x18000b8e0  lea     rcx, [rsp+310h+var_2A0]; this
0x18000b8e5  call    ?_AddRef@CLKRLinearHashTable_Iterator@@IEBAXH@Z; CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000b8ea  test    bl, bl
0x18000b8ec  jz      loc_18000B979
0x18000b8f2  mov     rax, [rsp+310h+var_2C8]
0x18000b8f7  lea     r8, asc_1800397FC; "*"
0x18000b8fe  movsx   rcx, [rsp+310h+var_2BC]; this
0x18000b904  lea     r9, [rsp+310h+var_2E0]; int *
0x18000b909  mov     dword ptr [rsp+310h+var_2E0], r14d
0x18000b90e  mov     rsi, [rax+rcx*8+18h]
0x18000b913  lea     rax, [r15+2]
0x18000b917  cmp     [rax], r14w
0x18000b91b  cmovnz  r8, rax; unsigned __int16 *
0x18000b91f  mov     rdx, [rsi+28h]; unsigned __int16 *
0x18000b923  call    ?IsWildcardMatch@COMMAND_PROCESSOR@@AEAAJPEBG0PEAH@Z; COMMAND_PROCESSOR::IsWildcardMatch(ushort const *,ushort const *,int *)
0x18000b928  mov     ebx, eax
0x18000b92a  test    eax, eax
0x18000b92c  js      loc_18000BA6A
0x18000b932  cmp     dword ptr [rsp+310h+var_2E0], r14d
0x18000b937  jz      short loc_18000B96A
0x18000b939  mov     rdx, [rsi+28h]; unsigned __int16 *
0x18000b93d  lea     rcx, [rbp+210h+var_280]; this
0x18000b941  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000b946  mov     ebx, eax
0x18000b948  test    eax, eax
0x18000b94a  js      loc_18000BA6A
0x18000b950  lea     rdx, asc_180039804; "\n"
0x18000b957  lea     rcx, [rbp+210h+var_280]; this
0x18000b95b  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000b960  mov     ebx, eax
0x18000b962  test    eax, eax
0x18000b964  js      loc_18000BA6A
0x18000b96a  lea     rcx, [rsp+310h+var_2D8]; this
0x18000b96f  call    ?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18000b974  jmp     loc_18000B8B9
0x18000b979  mov     edx, edi; int
0x18000b97b  lea     rcx, [rsp+310h+var_2D0]; this
0x18000b980  call    ?_AddRef@CLKRLinearHashTable_Iterator@@IEBAXH@Z; CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000b985  mov     rax, [r13+0]
0x18000b989  mov     ebx, 80070057h
0x18000b98e  mov     r8, [rbp+210h+var_260]
0x18000b992  xor     r9d, r9d
0x18000b995  mov     edx, ebx
0x18000b997  mov     rcx, r13
0x18000b99a  mov     rax, [rax+80h]
0x18000b9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a6  jmp     loc_18000BAC6
0x18000b9ab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b9af  mov     rsi, rdi
0x18000b9b2  inc     rsi
0x18000b9b5  cmp     [r15+rsi*2], cx
0x18000b9ba  jnz     short loc_18000B9B2
0x18000b9bc  test    rsi, rsi
0x18000b9bf  jz      loc_18000BA8D
0x18000b9c5  lea     rdx, [rsp+310h+var_2D8]
0x18000b9ca  mov     rcx, r14
0x18000b9cd  call    ?begin@?$CTypedHashTable@VSECTION_TABLE@@VSECTION_TABLE_ENTRY@@PEBGVCLKRHashTable@@VCIterator@3@@@QEAA?AViterator@1@XZ; CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,ushort const *,CLKRHashTable,CLKRHashTable::CIterator>::begin(void)
0x18000b9d2  lea     rdx, [rsp+310h+var_2A8]
0x18000b9d7  call    ?end@?$CTypedHashTable@VSECTION_TABLE@@VSECTION_TABLE_ENTRY@@PEBGVCLKRHashTable@@VCIterator@3@@@QEAA?AViterator@1@XZ; CTypedHashTable<SECTION_TABLE,SECTION_TABLE_ENTRY,ushort const *,CLKRHashTable,CLKRHashTable::CIterator>::end(void)
0x18000b9dc  mov     rcx, [rax+10h]
0x18000b9e0  cmp     [rsp+310h+var_2C8], rcx
0x18000b9e5  jnz     short loc_18000B9F7
0x18000b9e7  movzx   eax, word ptr [rax+1Ch]
0x18000b9eb  cmp     [rsp+310h+var_2BC], ax
0x18000b9f0  jnz     short loc_18000B9F7
0x18000b9f2  xor     r14b, r14b
0x18000b9f5  jmp     short loc_18000B9FA
0x18000b9f7  mov     r14b, 1
0x18000b9fa  mov     edx, edi; int
0x18000b9fc  lea     rcx, [rsp+310h+var_2A0]; this
0x18000ba01  call    ?_AddRef@CLKRLinearHashTable_Iterator@@IEBAXH@Z; CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000ba06  test    r14b, r14b
0x18000ba09  jz      short loc_18000BA81
0x18000ba0b  movsx   rcx, [rsp+310h+var_2BC]
0x18000ba11  mov     rax, [rsp+310h+var_2C8]
0x18000ba16  mov     r14, [rax+rcx*8+18h]
0x18000ba1b  mov     ecx, [r14+38h]
0x18000ba1f  cmp     rcx, rsi
0x18000ba22  jbe     short loc_18000BA53
0x18000ba24  mov     rax, [r14+28h]
0x18000ba28  sub     rcx, rsi
0x18000ba2b  mov     r8, rsi; MaxCount
0x18000ba2e  lea     rax, [rax+rcx*2]
0x18000ba32  mov     rcx, r15; String1
0x18000ba35  mov     rdx, rax; String2
0x18000ba38  mov     [rsp+310h+var_2E0], rax
0x18000ba3d  call    cs:__imp__wcsnicmp
0x18000ba43  test    eax, eax
0x18000ba45  jnz     short loc_18000BA53
0x18000ba47  mov     rax, [rsp+310h+var_2E0]
0x18000ba4c  cmp     word ptr [rax-2], 2Fh ; '/'
0x18000ba51  jz      short loc_18000BA62
0x18000ba53  lea     rcx, [rsp+310h+var_2D8]; this
0x18000ba58  call    ?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x18000ba5d  jmp     loc_18000B9D2
0x18000ba62  mov     rax, [r14+28h]
0x18000ba66  mov     [r12], rax
0x18000ba6a  mov     edx, edi; int
0x18000ba6c  lea     rcx, [rsp+310h+var_2D0]; this
0x18000ba71  call    ?_AddRef@CLKRLinearHashTable_Iterator@@IEBAXH@Z; CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000ba76  mov     edx, 80070002h
0x18000ba7b  cmp     ebx, edx
0x18000ba7d  jnz     short loc_18000BAC6
0x18000ba7f  jmp     short loc_18000BA94
0x18000ba81  mov     edx, edi; int
0x18000ba83  lea     rcx, [rsp+310h+var_2D0]; this
0x18000ba88  call    ?_AddRef@CLKRLinearHashTable_Iterator@@IEBAXH@Z; CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000ba8d  mov     edx, 80070002h
0x18000ba92  mov     ebx, edx
0x18000ba94  mov     rax, [r13+0]
0x18000ba98  lea     r9, [rsp+310h+var_2B0]
0x18000ba9d  mov     r8d, 0C00003F7h
0x18000baa3  mov     [rsp+310h+var_2B0], r15
0x18000baa8  mov     rcx, r13
0x18000baab  mov     [rsp+310h+var_2F0], 0
0x18000bab3  mov     rax, [rax+90h]
0x18000baba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000babf  jmp     short loc_18000BAC6
0x18000bac1  mov     ebx, 80070057h
0x18000bac6  lea     rcx, [rbp+210h+var_280]; this
0x18000baca  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000bacf  mov     eax, ebx
0x18000bad1  mov     rcx, [rbp+210h+var_40]
0x18000bad8  xor     rcx, rsp; StackCookie
0x18000badb  call    __security_check_cookie
0x18000bae0  mov     rbx, [rsp+310h+arg_18]
0x18000bae8  add     rsp, 2E0h
0x18000baef  pop     r15
0x18000baf1  pop     r14
0x18000baf3  pop     r13
0x18000baf5  pop     r12
0x18000baf7  pop     rdi
0x18000baf8  pop     rsi
0x18000baf9  pop     rbp
0x18000bafa  retn
```
