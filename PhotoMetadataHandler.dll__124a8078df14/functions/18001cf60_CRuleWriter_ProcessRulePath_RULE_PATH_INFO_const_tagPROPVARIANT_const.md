# CRuleWriter::ProcessRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x18001cf60`
- end: `0x18001d0ae`
- name: `?ProcessRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000b3bc`
- `0x18000bac0`
- `0x18000f2d0`
- `0x180011704`
- `0x180011838`
- `0x180013030`
- `0x18001cee4`
- `0x18001cf60`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001d05c`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001d05c`

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
  int v8; // ebp
  unsigned int v9; // ebp
  bool v10; // sf
  __int64 v11; // rax
  _QWORD *v12; // rdx
  int v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 1;
  v6 = (*(__int64 (__fastcall **)(CRuleWriter *, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *, int *))(*(_QWORD *)this + 40LL))(
         this,
         a2,
         a3,
         &v14);
  if ( v6 < 0 )
    return (unsigned int)v6;
  if ( v14 == 2 )
    return (unsigned int)CRuleWriter::RemovePathAndHandleChecksum(this, a2);
  if ( v14 != 1 )
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
        &v15,
        *((_QWORD *)a2 + 3));
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
        (char *)this + 56,
        &v15);
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      if ( v7 )
        CRuleWriter::UpdateChecksum(this, a2);
      return (unsigned int)v6;
    }
  }
  v8 = *((_DWORD *)this + 20);
  if ( v8 != *((_DWORD *)this + 21) )
    goto LABEL_16;
  if ( *((_DWORD *)this + 21) )
  {
    v10 = (v8 & 0x40000000) != 0;
    v9 = 2 * v8;
    if ( v10 )
      return (unsigned int)v6;
  }
  else
  {
    v9 = 1;
  }
  if ( v9 <= 0xFFFFFFFuLL )
  {
    v11 = _o__recalloc(*((_QWORD *)this + 9), v9, 8);
    if ( v11 )
    {
      *((_DWORD *)this + 21) = v9;
      *((_QWORD *)this + 9) = v11;
LABEL_16:
      v12 = (_QWORD *)(*((_QWORD *)this + 9) + 8LL * *((int *)this + 20));
      if ( v12 )
        *v12 = a2;
      ++*((_DWORD *)this + 20);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001cf60  mov     [rsp+arg_8], rbx
0x18001cf65  mov     [rsp+arg_10], rbp
0x18001cf6a  push    rsi
0x18001cf6b  push    rdi
0x18001cf6c  push    r14
0x18001cf6e  sub     rsp, 30h
0x18001cf72  mov     rbp, r8
0x18001cf75  mov     rdi, rdx
0x18001cf78  mov     rbx, rcx
0x18001cf7b  mov     [rsp+48h+arg_0], 1
0x18001cf83  mov     rax, [rcx]
0x18001cf86  lea     r9, [rsp+48h+arg_0]
0x18001cf8b  mov     rax, [rax+28h]
0x18001cf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf94  mov     esi, eax
0x18001cf96  test    eax, eax
0x18001cf98  js      loc_18001D099
0x18001cf9e  cmp     [rsp+48h+arg_0], 2
0x18001cfa3  jnz     short loc_18001CFB7
0x18001cfa5  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001cfa8  mov     rcx, rbx; this
0x18001cfab  call    ?RemovePathAndHandleChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::RemovePathAndHandleChecksum(RULE_PATH_INFO const *)
0x18001cfb0  mov     esi, eax
0x18001cfb2  jmp     loc_18001D099
0x18001cfb7  cmp     [rsp+48h+arg_0], 1
0x18001cfbc  jnz     loc_18001D099
0x18001cfc2  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001cfc5  mov     rcx, rbx; this
0x18001cfc8  call    ?NeedToProcessChecksumForPath@CRuleWriter@@IEAAHPEBURULE_PATH_INFO@@@Z; CRuleWriter::NeedToProcessChecksumForPath(RULE_PATH_INFO const *)
0x18001cfcd  mov     r14d, eax
0x18001cfd0  test    eax, eax
0x18001cfd2  jz      short loc_18001CFE5
0x18001cfd4  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001cfd7  mov     rcx, rbx; this
0x18001cfda  call    ?WriteOtherKeysAffectedByChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::WriteOtherKeysAffectedByChecksum(RULE_PATH_INFO const *)
0x18001cfdf  mov     esi, eax
0x18001cfe1  test    eax, eax
0x18001cfe3  js      short loc_18001D02E
0x18001cfe5  mov     rax, [rbx]
0x18001cfe8  mov     r8, rbp
0x18001cfeb  mov     rdx, rdi
0x18001cfee  mov     rcx, rbx
0x18001cff1  mov     rax, [rax+38h]
0x18001cff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cffa  mov     esi, eax
0x18001cffc  test    eax, eax
0x18001cffe  js      short loc_18001D02E
0x18001d000  mov     rdx, [rdi+18h]
0x18001d004  lea     rcx, [rsp+48h+arg_18]
0x18001d009  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d00e  nop
0x18001d00f  lea     rcx, [rbx+38h]
0x18001d013  lea     rdx, [rsp+48h+arg_18]
0x18001d018  call    ?Add@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001d01d  nop
0x18001d01e  mov     rcx, [rsp+48h+arg_18]
0x18001d023  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d027  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d02c  jmp     short loc_18001D089
0x18001d02e  mov     ebp, [rbx+50h]
0x18001d031  cmp     ebp, [rbx+54h]
0x18001d034  jnz     short loc_18001D06E
0x18001d036  cmp     dword ptr [rbx+54h], 0
0x18001d03a  jnz     short loc_18001D043
0x18001d03c  mov     ebp, 1
0x18001d041  jmp     short loc_18001D047
0x18001d043  add     ebp, ebp
0x18001d045  js      short loc_18001D085
0x18001d047  mov     edx, ebp
0x18001d049  cmp     rdx, 0FFFFFFFh
0x18001d050  ja      short loc_18001D085
0x18001d052  mov     r8d, 8
0x18001d058  mov     rcx, [rbx+48h]
0x18001d05c  call    cs:__imp__o__recalloc
0x18001d062  test    rax, rax
0x18001d065  jz      short loc_18001D085
0x18001d067  mov     [rbx+54h], ebp
0x18001d06a  mov     [rbx+48h], rax
0x18001d06e  movsxd  rcx, dword ptr [rbx+50h]
0x18001d072  mov     rax, [rbx+48h]
0x18001d076  lea     rdx, [rax+rcx*8]
0x18001d07a  test    rdx, rdx
0x18001d07d  jz      short loc_18001D082
0x18001d07f  mov     [rdx], rdi
0x18001d082  inc     dword ptr [rbx+50h]
0x18001d085  test    esi, esi
0x18001d087  js      short loc_18001D099
0x18001d089  test    r14d, r14d
0x18001d08c  jz      short loc_18001D099
0x18001d08e  mov     rdx, rdi; struct RULE_PATH_INFO *
0x18001d091  mov     rcx, rbx; this
0x18001d094  call    ?UpdateChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z; CRuleWriter::UpdateChecksum(RULE_PATH_INFO const *)
0x18001d099  mov     eax, esi
0x18001d09b  mov     rbx, [rsp+48h+arg_8]
0x18001d0a0  mov     rbp, [rsp+48h+arg_10]
0x18001d0a5  add     rsp, 30h
0x18001d0a9  pop     r14
0x18001d0ab  pop     rdi
0x18001d0ac  pop     rsi
0x18001d0ad  retn
```
