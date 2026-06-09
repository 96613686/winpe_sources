# CRuleWriter::ProcessRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x18001dd00`
- end: `0x18001de55`
- name: `?ProcessRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000b90c`
- `0x18000c048`
- `0x18000fa14`
- `0x180011f18`
- `0x180012050`
- `0x18001395c`
- `0x18001dc8c`
- `0x18001dd00`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001ddfc`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001ddfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleWriter::ProcessRulePath(
        CRuleWriter *this,
        const struct RULE_PATH_INFO *a2,
        const struct tagPROPVARIANT *a3)
{
  int v6; // esi
  int v7; // r14d
  __int64 v8; // r8
  int v9; // ebp
  unsigned int v10; // ebp
  bool v11; // sf
  __int64 v12; // rax
  _QWORD *v13; // rdx
  int v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v15 = 1;
  v6 = (*(__int64 (__fastcall **)(CRuleWriter *, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *, int *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         a3,
         &v15);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( v15 == 2 )
    return (unsigned int)CRuleWriter::RemovePathAndHandleChecksum(this, a2);
  if ( v15 != 1 )
    return (unsigned int)v6;
  v7 = CRuleWriter::NeedToProcessChecksumForPath(this, a2);
  if ( !v7 || (v6 = CRuleWriter::WriteOtherKeysAffectedByChecksum(this, a2), v6 >= 0) )
  {
    v6 = (*(__int64 (__fastcall **)(CRuleWriter *, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *))(*(_QWORD *)this + 56LL))(
           this,
           a2,
           a3);
    if ( v6 >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v16,
        *((_QWORD *)a2 + 3),
        v8);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
        (char *)this + 56,
        &v16);
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
      if ( v7 )
        CRuleWriter::UpdateChecksum(this, a2);
      return (unsigned int)v6;
    }
  }
  v9 = *((_DWORD *)this + 20);
  if ( v9 != *((_DWORD *)this + 21) )
    goto LABEL_16;
  if ( *((_DWORD *)this + 21) )
  {
    v11 = (v9 & 0x40000000) != 0;
    v10 = 2 * v9;
    if ( v11 )
      return (unsigned int)v6;
  }
  else
  {
    v10 = 1;
  }
  if ( v10 <= 0xFFFFFFFuLL )
  {
    v12 = _o__recalloc(*((_QWORD *)this + 9), v10, 8);
    if ( v12 )
    {
      *((_DWORD *)this + 21) = v10;
      *((_QWORD *)this + 9) = v12;
LABEL_16:
      v13 = (_QWORD *)(*((_QWORD *)this + 9) + 8LL * *((int *)this + 20));
      if ( v13 )
        *v13 = a2;
      ++*((_DWORD *)this + 20);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001dd00  mov     [rsp+arg_8], rbx
0x18001dd05  mov     [rsp+arg_10], rbp
0x18001dd0a  push    rsi
0x18001dd0b  push    rdi
0x18001dd0c  push    r14
0x18001dd0e  sub     rsp, 30h
0x18001dd12  mov     rbp, r8
0x18001dd15  mov     rdi, rdx
0x18001dd18  mov     rbx, rcx
0x18001dd1b  mov     [rsp+48h+arg_0], 1
0x18001dd23  mov     rax, [rcx]
0x18001dd26  lea     r9, [rsp+48h+arg_0]
0x18001dd2b  mov     rax, [rax+28h]
0x18001dd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd34  mov     esi, eax
0x18001dd36  test    eax, eax
0x18001dd38  js      loc_18001DE3F
0x18001dd3e  cmp     [rsp+48h+arg_0], 2
0x18001dd43  jnz     short loc_18001DD57
0x18001dd45  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001dd48  mov     rcx, rbx; this
0x18001dd4b  call    ?RemovePathAndHandleChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::RemovePathAndHandleChecksum(RULE_PATH_INFO const *)
0x18001dd50  mov     esi, eax
0x18001dd52  jmp     loc_18001DE3F
0x18001dd57  cmp     [rsp+48h+arg_0], 1
0x18001dd5c  jnz     loc_18001DE3F
0x18001dd62  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001dd65  mov     rcx, rbx; this
0x18001dd68  call    ?NeedToProcessChecksumForPath@CRuleWriter@@IEAAHPEBURULE_PATH_INFO@@@Z; CRuleWriter::NeedToProcessChecksumForPath(RULE_PATH_INFO const *)
0x18001dd6d  mov     r14d, eax
0x18001dd70  test    eax, eax
0x18001dd72  jz      short loc_18001DD85
0x18001dd74  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001dd77  mov     rcx, rbx; this
0x18001dd7a  call    ?WriteOtherKeysAffectedByChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::WriteOtherKeysAffectedByChecksum(RULE_PATH_INFO const *)
0x18001dd7f  mov     esi, eax
0x18001dd81  test    eax, eax
0x18001dd83  js      short loc_18001DDCE
0x18001dd85  mov     rax, [rbx]
0x18001dd88  mov     r8, rbp
0x18001dd8b  mov     rdx, rdi
0x18001dd8e  mov     rcx, rbx
0x18001dd91  mov     rax, [rax+38h]
0x18001dd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd9a  mov     esi, eax
0x18001dd9c  test    eax, eax
0x18001dd9e  js      short loc_18001DDCE
0x18001dda0  mov     rdx, [rdi+18h]
0x18001dda4  lea     rcx, [rsp+48h+arg_18]
0x18001dda9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001ddae  nop
0x18001ddaf  lea     rcx, [rbx+38h]
0x18001ddb3  lea     rdx, [rsp+48h+arg_18]
0x18001ddb8  call    ?Add@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001ddbd  nop
0x18001ddbe  mov     rcx, [rsp+48h+arg_18]
0x18001ddc3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ddc7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ddcc  jmp     short loc_18001DE2F
0x18001ddce  mov     ebp, [rbx+50h]
0x18001ddd1  cmp     ebp, [rbx+54h]
0x18001ddd4  jnz     short loc_18001DE14
0x18001ddd6  cmp     dword ptr [rbx+54h], 0
0x18001ddda  jnz     short loc_18001DDE3
0x18001dddc  mov     ebp, 1
0x18001dde1  jmp     short loc_18001DDE7
0x18001dde3  add     ebp, ebp
0x18001dde5  js      short loc_18001DE2B
0x18001dde7  mov     edx, ebp
0x18001dde9  cmp     rdx, 0FFFFFFFh
0x18001ddf0  ja      short loc_18001DE2B
0x18001ddf2  mov     r8d, 8
0x18001ddf8  mov     rcx, [rbx+48h]
0x18001ddfc  call    cs:__imp__o__recalloc
0x18001de03  nop     dword ptr [rax+rax+00h]
0x18001de08  test    rax, rax
0x18001de0b  jz      short loc_18001DE2B
0x18001de0d  mov     [rbx+54h], ebp
0x18001de10  mov     [rbx+48h], rax
0x18001de14  movsxd  rcx, dword ptr [rbx+50h]
0x18001de18  mov     rax, [rbx+48h]
0x18001de1c  lea     rdx, [rax+rcx*8]
0x18001de20  test    rdx, rdx
0x18001de23  jz      short loc_18001DE28
0x18001de25  mov     [rdx], rdi
0x18001de28  inc     dword ptr [rbx+50h]
0x18001de2b  test    esi, esi
0x18001de2d  js      short loc_18001DE3F
0x18001de2f  test    r14d, r14d
0x18001de32  jz      short loc_18001DE3F
0x18001de34  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001de37  mov     rcx, rbx; this
0x18001de3a  call    ?UpdateChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::UpdateChecksum(RULE_PATH_INFO const *)
0x18001de3f  mov     eax, esi
0x18001de41  mov     rbx, [rsp+48h+arg_8]
0x18001de46  mov     rbp, [rsp+48h+arg_10]
0x18001de4b  add     rsp, 30h
0x18001de4f  pop     r14
0x18001de51  pop     rdi
0x18001de52  pop     rsi
0x18001de53  retn
```
