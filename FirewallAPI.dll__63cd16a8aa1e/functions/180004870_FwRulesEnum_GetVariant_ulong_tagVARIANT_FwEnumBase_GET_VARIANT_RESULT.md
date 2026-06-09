# FwRulesEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x180004870`
- end: `0x180004cc8`
- name: `?GetVariant@FwRulesEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `1112`
- prototype: `__int64 __fastcall(FwRulesEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004870`
- `0x180004e50`
- `0x18003104c`
- `0x18005e010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180004a00`
- `fwbase!FwReportReturnError` at `0x180004a28`
- `fwbase!FwReportReturnError` at `0x180004b83`
- `fwbase!FwReportReturnError` at `0x180004ba0`
- `fwbase!FwReportReturnError` at `0x180004bb9`
- `fwbase!FwReportReturnError` at `0x180004cae`
- `fwbase!FwReportReturnError` at `0x180004cbd`
- `fwbase!FwReportReturnError` at `0x180004a00`
- `fwbase!FwReportReturnError` at `0x180004a28`
- `fwbase!FwReportReturnError` at `0x180004b83`
- `fwbase!FwReportReturnError` at `0x180004ba0`
- `fwbase!FwReportReturnError` at `0x180004bb9`
- `fwbase!FwReportReturnError` at `0x180004cae`
- `fwbase!FwReportReturnError` at `0x180004cbd`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004b8d`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004b8d`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800049db`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800049db`

## string_xrefs

- `0x1800049f9`: `FwRule::CreateInstance`
- `0x180004a21`: `FwRule::CreateInstance`
- `0x180004bb2`: `FwRule::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwRulesEnum::GetVariant(
        FwRulesEnum *this,
        int a2,
        struct tagVARIANT *a3,
        enum FwEnumBase::GET_VARIANT_RESULT *a4)
{
  FwPolicy2 *v8; // r10
  unsigned int v9; // esi
  int v10; // r12d
  __int64 v11; // rbp
  _WORD *v12; // rax
  __int16 v13; // ax
  unsigned int i; // r9d
  int v15; // ecx
  __int64 *v16; // r12
  int v17; // esi
  __int64 v18; // rcx
  LONGLONG v19; // rbp
  int v20; // eax
  unsigned int v21; // ebx
  LONGLONG v22; // rdi
  int v23; // eax
  __int64 v25; // rcx
  _WORD *v26; // rdx
  __int64 v27; // rdx
  _WORD *v28; // rcx
  _WORD *v29; // rax
  int v30; // eax
  _WORD *v31; // rcx
  LONGLONG v32; // [rsp+50h] [rbp+8h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_098d31ae94223bbae5defc232583cd37_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    *((_QWORD *)this + 14) = *((_QWORD *)this + 12);
    *((_QWORD *)this + 15) = 0;
    v8 = WPP_GLOBAL_Control;
  }
  v9 = *((_DWORD *)this + 30);
  if ( v9 >= *((_DWORD *)this + 26) )
  {
LABEL_41:
    *(_DWORD *)a4 = 2;
    return 0;
  }
  while ( 1 )
  {
    v10 = *((_DWORD *)this + 18);
    v11 = *((_QWORD *)this + 14);
    if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 95, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v12 = *(_WORD **)(v11 + 24);
    if ( v12 )
    {
      if ( *v12 && (unsigned int)(*(_DWORD *)(v11 + 288) - 2) <= 1 )
        break;
    }
LABEL_40:
    ++v9;
    v25 = **((_QWORD **)this + 14);
    ++*((_DWORD *)this + 30);
    *((_QWORD *)this + 14) = v25;
    if ( v9 >= *((_DWORD *)this + 26) )
      goto LABEL_41;
    v8 = WPP_GLOBAL_Control;
  }
  v13 = *(_WORD *)(v11 + 48);
  if ( v13 == 1 || v13 == 58 )
    goto LABEL_19;
  if ( v11 == -56 )
  {
    if ( v8 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_40;
    v27 = 10;
LABEL_47:
    WPP_SF_(*((_QWORD *)v8 + 2), v27, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids);
    goto LABEL_40;
  }
  if ( (*(_WORD *)(v11 + 56) & 0xFC20) != 0 )
  {
    if ( v8 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_40;
    v27 = 11;
    goto LABEL_47;
  }
  for ( i = 0; i < *(_DWORD *)(v11 + 64); ++i )
  {
    v26 = (_WORD *)(*(_QWORD *)(v11 + 72) + 4LL * i);
    if ( *v26 > v26[1] )
    {
      if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      {
        v27 = 12;
        goto LABEL_47;
      }
      goto LABEL_40;
    }
  }
LABEL_19:
  if ( (v10 & 1) != 0 )
  {
    v28 = *(_WORD **)(v11 + 376);
    if ( v28 || *(_QWORD *)(v11 + 384) )
    {
      if ( (v10 & 4) == 0 )
        goto LABEL_40;
      if ( !v28 )
        goto LABEL_40;
      if ( !*v28 )
        goto LABEL_40;
      v31 = *(_WORD **)(v11 + 384);
      if ( !v31 || !*v31 )
        goto LABEL_40;
    }
    v29 = *(_WORD **)(v11 + 280);
    if ( v29 )
    {
      if ( (v10 & 2) == 0 || !*v29 )
        goto LABEL_40;
    }
  }
  v15 = *((_DWORD *)this + 31);
  *((_DWORD *)this + 31) = v15 + 1;
  if ( a2 != v15 )
    goto LABEL_40;
  v16 = (__int64 *)*((_QWORD *)this + 14);
  v17 = *((_DWORD *)this + 18);
  v18 = *v16;
  ++*((_DWORD *)this + 30);
  *((_QWORD *)this + 14) = v18;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v32 = 0;
  v19 = 0;
  v20 = ATL::CComObject<FwRule>::CreateInstance(&v32);
  v21 = v20;
  if ( v20 < 0 )
  {
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v20);
    v22 = v32;
    goto LABEL_32;
  }
  v22 = v32;
  (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v32 + 8LL))(v32);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  *(_DWORD *)(v22 + 64) = v17;
  v23 = FwCopyRule(v16, v22 + 80);
  v21 = v23;
  if ( v23 >= 0 )
  {
    *(_DWORD *)(v22 + 88) = 1;
    goto LABEL_30;
  }
  FwReportReturnError("FwRule::Initialize", (unsigned int)v23);
  FwFreeWFRule(*(_QWORD *)(v22 + 80));
  *(_QWORD *)(v22 + 80) = 0;
  v30 = FwReportReturnError("FwRule::Initialize", v21);
  v21 = v30;
  if ( v30 >= 0 )
  {
LABEL_30:
    v19 = v22;
    goto LABEL_35;
  }
  FwReportReturnError("FwRule::CreateInstance", (unsigned int)v30);
LABEL_32:
  if ( v22 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v22 + 16LL))(v22);
  v21 = FwReportReturnError("FwRule::CreateInstance", v21);
  if ( v21 == -2147024883 )
    goto LABEL_54;
LABEL_35:
  if ( v21 == -2147024894 )
  {
LABEL_54:
    *(_DWORD *)a4 = 1;
    return 0;
  }
  if ( (v21 & 0x80000000) == 0 )
  {
    a3->vt = 9;
    a3->llVal = v19;
    *(_DWORD *)a4 = 0;
    return v21;
  }
  FwReportReturnError("FwRulesEnum::GetVariant", v21);
  return FwReportReturnError("FwRulesEnum::GetVariant", v21);
}

```

## disassembly

```asm
0x180004870  mov     [rsp+arg_18], rbx
0x180004875  push    rsi
0x180004876  push    rdi
0x180004877  push    r13
0x180004879  push    r14
0x18000487b  push    r15
0x18000487d  sub     rsp, 20h
0x180004881  mov     r14, r9
0x180004884  mov     r15, r8
0x180004887  mov     edi, edx
0x180004889  mov     rbx, rcx
0x18000488c  mov     r10, cs:WPP_GLOBAL_Control
0x180004893  lea     r11, WPP_GLOBAL_Control
0x18000489a  cmp     r10, r11
0x18000489d  jz      short loc_1800048AA
0x18000489f  test    byte ptr [r10+1Ch], 8
0x1800048a4  jnz     loc_180004BC4
0x1800048aa  xor     r13d, r13d
0x1800048ad  test    edi, edi
0x1800048af  jz      loc_180004A7A
0x1800048b5  mov     esi, [rbx+78h]
0x1800048b8  mov     [rsp+48h+arg_8], rbp
0x1800048bd  mov     [rsp+48h+arg_10], r12
0x1800048c2  cmp     esi, [rbx+68h]
0x1800048c5  jnb     loc_180004AB4
0x1800048cb  mov     r12d, [rbx+48h]
0x1800048cf  mov     rbp, [rbx+70h]
0x1800048d3  cmp     r10, r11
0x1800048d6  jz      short loc_1800048E3
0x1800048d8  test    byte ptr [r10+1Ch], 8
0x1800048dd  jnz     loc_180004BEC
0x1800048e3  mov     rax, [rbp+18h]
0x1800048e7  test    rax, rax
0x1800048ea  jz      loc_180004A9B
0x1800048f0  cmp     [rax], r13w
0x1800048f4  jz      loc_180004A9B
0x1800048fa  mov     eax, [rbp+120h]
0x180004900  sub     eax, 2
0x180004903  cmp     eax, 1
0x180004906  ja      loc_180004A9B
0x18000490c  movzx   eax, word ptr [rbp+30h]
0x180004910  cmp     ax, 1
0x180004914  jz      short loc_180004945
0x180004916  cmp     ax, 3Ah ; ':'
0x18000491a  jz      short loc_180004945
0x18000491c  lea     r8, [rbp+38h]
0x180004920  test    r8, r8
0x180004923  jz      loc_180004B5C
0x180004929  movzx   eax, word ptr [r8]
0x18000492d  test    eax, 0FFFFFC20h
0x180004932  jnz     loc_180004A92
0x180004938  mov     r9d, r13d
0x18000493b  cmp     r9d, [r8+8]
0x18000493f  jb      loc_180004AC0
0x180004945  test    r12b, 1
0x180004949  jnz     loc_180004B07
0x18000494f  mov     ecx, [rbx+7Ch]
0x180004952  lea     eax, [rcx+1]
0x180004955  mov     [rbx+7Ch], eax
0x180004958  cmp     edi, ecx
0x18000495a  jnz     loc_180004A9B
0x180004960  mov     r12, [rbx+70h]
0x180004964  mov     esi, [rbx+48h]
0x180004967  mov     rcx, [r12]
0x18000496b  inc     dword ptr [rbx+78h]
0x18000496e  mov     [rbx+70h], rcx
0x180004972  mov     rcx, cs:WPP_GLOBAL_Control
0x180004979  cmp     rcx, r11
0x18000497c  jz      short loc_180004988
0x18000497e  test    byte ptr [rcx+1Ch], 8
0x180004982  jnz     loc_180004C71
0x180004988  lea     rcx, [rsp+48h+arg_0]
0x18000498d  mov     [rsp+48h+arg_0], r13
0x180004992  mov     rbp, r13
0x180004995  call    ?CreateInstance@?$CComObject@VFwRule@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRule>::CreateInstance(ATL::CComObject<FwRule> * *)
0x18000499a  mov     ebx, eax
0x18000499c  test    eax, eax
0x18000499e  js      short loc_1800049F7
0x1800049a0  mov     rdi, [rsp+48h+arg_0]
0x1800049a5  mov     rcx, rdi
0x1800049a8  mov     rax, [rdi]
0x1800049ab  mov     rax, [rax+8]
0x1800049af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049bb  lea     rax, WPP_GLOBAL_Control
0x1800049c2  cmp     rcx, rax
0x1800049c5  jz      short loc_1800049D1
0x1800049c7  test    byte ptr [rcx+1Ch], 8
0x1800049cb  jnz     loc_180004C8B
0x1800049d1  lea     rdx, [rdi+50h]
0x1800049d5  mov     [rdi+40h], esi
0x1800049d8  mov     rcx, r12
0x1800049db  call    cs:__imp_FwCopyRule
0x1800049e1  mov     ebx, eax
0x1800049e3  test    eax, eax
0x1800049e5  js      loc_180004B7A
0x1800049eb  mov     dword ptr [rdi+58h], 1
0x1800049f2  mov     rbp, rdi
0x1800049f5  jmp     short loc_180004A3B
0x1800049f7  mov     edx, eax
0x1800049f9  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004a00  call    cs:__imp_FwReportReturnError
0x180004a06  mov     rdi, [rsp+48h+arg_0]
0x180004a0b  test    rdi, rdi
0x180004a0e  jz      short loc_180004A1F
0x180004a10  mov     rax, [rdi]
0x180004a13  mov     rcx, rdi
0x180004a16  mov     rax, [rax+10h]
0x180004a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a1f  mov     edx, ebx
0x180004a21  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004a28  call    cs:__imp_FwReportReturnError
0x180004a2e  mov     ebx, eax
0x180004a30  cmp     eax, 8007000Dh
0x180004a35  jz      loc_180004B4D
0x180004a3b  cmp     ebx, 80070002h
0x180004a41  jz      loc_180004B4D
0x180004a47  test    ebx, ebx
0x180004a49  js      loc_180004CA5
0x180004a4f  mov     word ptr [r15], 9
0x180004a55  mov     [r15+8], rbp
0x180004a59  mov     [r14], r13d
0x180004a5c  mov     eax, ebx
0x180004a5e  mov     r12, [rsp+48h+arg_10]
0x180004a63  mov     rbp, [rsp+48h+arg_8]
0x180004a68  mov     rbx, [rsp+48h+arg_18]
0x180004a6d  add     rsp, 20h
0x180004a71  pop     r15
0x180004a73  pop     r14
0x180004a75  pop     r13
0x180004a77  pop     rdi
0x180004a78  pop     rsi
0x180004a79  retn
0x180004a7a  mov     rax, [rbx+60h]
0x180004a7e  mov     [rbx+70h], rax
0x180004a82  mov     [rbx+78h], r13
0x180004a86  mov     r10, cs:WPP_GLOBAL_Control
0x180004a8d  jmp     loc_1800048B5
0x180004a92  cmp     r10, r11
0x180004a95  jnz     loc_180004C14
0x180004a9b  mov     rax, [rbx+70h]
0x180004a9f  inc     esi
0x180004aa1  mov     rcx, [rax]
0x180004aa4  inc     dword ptr [rbx+78h]
0x180004aa7  mov     [rbx+70h], rcx
0x180004aab  cmp     esi, [rbx+68h]
0x180004aae  jb      loc_180004C65
0x180004ab4  mov     dword ptr [r14], 2
0x180004abb  mov     ebx, r13d
0x180004abe  jmp     short loc_180004A5C
0x180004ac0  mov     rax, [r8+10h]
0x180004ac4  mov     ecx, r9d
0x180004ac7  lea     rdx, [rax+rcx*4]
0x180004acb  movzx   eax, word ptr [rax+rcx*4+2]
0x180004ad0  cmp     [rdx], ax
0x180004ad3  ja      short loc_180004ADD
0x180004ad5  inc     r9d
0x180004ad8  jmp     loc_18000493B
0x180004add  cmp     r10, r11
0x180004ae0  jz      short loc_180004A9B
0x180004ae2  test    byte ptr [r10+1Ch], 1
0x180004ae7  jz      short loc_180004A9B
0x180004ae9  mov     edx, 0Ch
0x180004aee  mov     rcx, [r10+10h]
0x180004af2  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x180004af9  call    WPP_SF_
0x180004afe  lea     r11, WPP_GLOBAL_Control
0x180004b05  jmp     short loc_180004A9B
0x180004b07  mov     rcx, [rbp+178h]
0x180004b0e  test    rcx, rcx
0x180004b11  jnz     loc_180004C29
0x180004b17  cmp     [rbp+180h], r13
0x180004b1e  jnz     loc_180004C29
0x180004b24  mov     rax, [rbp+118h]
0x180004b2b  test    rax, rax
0x180004b2e  jz      loc_18000494F
0x180004b34  test    r12b, 2
0x180004b38  jz      loc_180004A9B
0x180004b3e  cmp     [rax], r13w
0x180004b42  jnz     loc_18000494F
0x180004b48  jmp     loc_180004A9B
0x180004b4d  mov     dword ptr [r14], 1
0x180004b54  mov     ebx, r13d
0x180004b57  jmp     loc_180004A5C
0x180004b5c  cmp     r10, r11
0x180004b5f  jz      loc_180004A9B
0x180004b65  test    byte ptr [r10+1Ch], 1
0x180004b6a  jz      loc_180004A9B
0x180004b70  mov     edx, 0Ah
0x180004b75  jmp     loc_180004AEE
0x180004b7a  mov     edx, ebx
0x180004b7c  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004b83  call    cs:__imp_FwReportReturnError
0x180004b89  mov     rcx, [rdi+50h]
0x180004b8d  call    cs:__imp_FwFreeWFRule
0x180004b93  mov     edx, ebx
0x180004b95  mov     [rdi+50h], r13
0x180004b99  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004ba0  call    cs:__imp_FwReportReturnError
0x180004ba6  mov     ebx, eax
0x180004ba8  test    eax, eax
0x180004baa  jns     loc_1800049F2
0x180004bb0  mov     edx, eax
0x180004bb2  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004bb9  call    cs:__imp_FwReportReturnError
0x180004bbf  jmp     loc_180004A0B
0x180004bc4  mov     rcx, [r10+10h]
0x180004bc8  lea     r8, WPP_098d31ae94223bbae5defc232583cd37_Traceguids
0x180004bcf  mov     edx, 0Dh
0x180004bd4  call    WPP_SF_
0x180004bd9  mov     r10, cs:WPP_GLOBAL_Control
0x180004be0  lea     r11, WPP_GLOBAL_Control
0x180004be7  jmp     loc_1800048AA
0x180004bec  mov     rcx, [r10+10h]
0x180004bf0  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180004bf7  mov     edx, 5Fh ; '_'
0x180004bfc  call    WPP_SF_
0x180004c01  mov     r10, cs:WPP_GLOBAL_Control
0x180004c08  lea     r11, WPP_GLOBAL_Control
0x180004c0f  jmp     loc_1800048E3
0x180004c14  test    byte ptr [r10+1Ch], 1
0x180004c19  jz      loc_180004A9B
0x180004c1f  mov     edx, 0Bh
0x180004c24  jmp     loc_180004AEE
0x180004c29  test    r12b, 4
0x180004c2d  jz      loc_180004A9B
0x180004c33  test    rcx, rcx
0x180004c36  jz      loc_180004A9B
0x180004c3c  cmp     [rcx], r13w
0x180004c40  jz      loc_180004A9B
0x180004c46  mov     rcx, [rbp+180h]
0x180004c4d  test    rcx, rcx
0x180004c50  jz      loc_180004A9B
0x180004c56  cmp     [rcx], r13w
0x180004c5a  jz      loc_180004A9B
0x180004c60  jmp     loc_180004B24
0x180004c65  mov     r10, cs:WPP_GLOBAL_Control
0x180004c6c  jmp     loc_1800048CB
0x180004c71  mov     rcx, [rcx+10h]
0x180004c75  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180004c7c  mov     edx, 55h ; 'U'
0x180004c81  call    WPP_SF_
0x180004c86  jmp     loc_180004988
0x180004c8b  mov     rcx, [rcx+10h]
0x180004c8f  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180004c96  mov     edx, 5Ah ; 'Z'
0x180004c9b  call    WPP_SF_
0x180004ca0  jmp     loc_1800049D1
0x180004ca5  mov     edx, ebx
0x180004ca7  lea     rcx, aFwrulesenumGet; "FwRulesEnum::GetVariant"
0x180004cae  call    cs:__imp_FwReportReturnError
0x180004cb4  mov     edx, ebx
0x180004cb6  lea     rcx, aFwrulesenumGet; "FwRulesEnum::GetVariant"
0x180004cbd  call    cs:__imp_FwReportReturnError
0x180004cc3  jmp     loc_180004A5E
```
