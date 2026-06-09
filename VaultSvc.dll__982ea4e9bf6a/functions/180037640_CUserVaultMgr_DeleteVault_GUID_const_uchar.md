# CUserVaultMgr::DeleteVault(_GUID const *,uchar)

- ea: `0x180037640`
- end: `0x180037861`
- name: `?DeleteVault@CUserVaultMgr@@QEAAKPEBU_GUID@@E@Z`
- size: `545`
- prototype: `__int64 __fastcall(CUserVaultMgr *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001dbe0`

## callees

- `0x180020b10`
- `0x18002e2e0`
- `0x18002ed08`
- `0x180037640`
- `0x180037b0c`
- `0x18003b7b0`
- `0x18003c948`
- `0x18003d780`
- `0x18003d7b8`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18003771b`
- `ntdll!RtlReleaseResource` at `0x18003776e`
- `ntdll!RtlReleaseResource` at `0x1800377b2`
- `ntdll!RtlReleaseResource` at `0x180037802`
- `ntdll!RtlReleaseResource` at `0x180037840`
- `ntdll!RtlReleaseResource` at `0x18003771b`
- `ntdll!RtlReleaseResource` at `0x18003776e`
- `ntdll!RtlReleaseResource` at `0x1800377b2`
- `ntdll!RtlReleaseResource` at `0x180037802`
- `ntdll!RtlReleaseResource` at `0x180037840`

## pseudocode

```c
__int64 __fastcall CUserVaultMgr::DeleteVault(CUserVaultMgr *this, const struct _GUID *a2)
{
  PVOID *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 *v9; // rax
  unsigned __int8 v10; // dl
  __int64 v11; // rbx
  CUserVault *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rax
  PRTL_RESOURCE Resource; // [rsp+30h] [rbp-10h] BYREF
  char v17; // [rsp+38h] [rbp-8h]
  char v18; // [rsp+70h] [rbp+30h] BYREF

  CVaultRtlLock::CVaultRtlLock(&Resource, (char *)this + 72, 1);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *(_QWORD *)&Vault_DefaultVault_ID.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&Vault_DefaultVault_ID.Data1 == *(_QWORD *)&a2->Data1 )
    v5 = *(_QWORD *)Vault_DefaultVault_ID.Data4 - *(_QWORD *)a2->Data4;
  if ( !v5 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      v6 = 57;
LABEL_16:
      WPP_SF_(v4[2], v6, &WPP_f1575cf6446936089985711df8c7b212_Traceguids);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  v7 = Vault_CredmanVault_ID - *(_QWORD *)&a2->Data1;
  if ( (_QWORD)Vault_CredmanVault_ID == *(_QWORD *)&a2->Data1 )
    v7 = *((_QWORD *)&Vault_CredmanVault_ID + 1) - *(_QWORD *)a2->Data4;
  if ( !v7 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    {
      v6 = 58;
      goto LABEL_16;
    }
LABEL_17:
    if ( v17 )
      RtlReleaseResource(Resource);
    return 50;
  }
  v9 = (__int64 *)std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::find(
                    (char *)this + 16,
                    &v18,
                    a2);
  v11 = *v9;
  if ( *v9 == *((_QWORD *)this + 2) )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF__guid_(v4[2], 59, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, a2);
    if ( v17 )
      RtlReleaseResource(Resource);
    return 1168;
  }
  else
  {
    v12 = *(CUserVault **)(v11 + 48);
    if ( *((_DWORD *)v12 + 27) )
    {
      v13 = CUserVault::DeleteUserVault(v12, v10);
      v14 = v13;
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            &WPP_f1575cf6446936089985711df8c7b212_Traceguids,
            a2,
            v13);
        if ( v17 )
          RtlReleaseResource(Resource);
        return v14;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v11 + 48) + 8LL))(*(_QWORD *)(v11 + 48));
        v15 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>::_Extract(
                (char *)this + 16,
                v11);
        std::_Deallocate<16>(v15, 56);
        if ( v17 )
          RtlReleaseResource(Resource);
        return 0;
      }
    }
    else
    {
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        WPP_SF__guid_(v4[2], 60, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, a2);
      if ( v17 )
        RtlReleaseResource(Resource);
      return 212;
    }
  }
}

```

## disassembly

```asm
0x180037640  mov     [rsp-28h+arg_8], rbx
0x180037645  mov     [rsp-28h+arg_10], rsi
0x18003764a  push    rbp
0x18003764b  push    rdi
0x18003764c  push    r12
0x18003764e  push    r13
0x180037650  push    r14
0x180037652  mov     rbp, rsp
0x180037655  sub     rsp, 40h
0x180037659  mov     rsi, rdx
0x18003765c  mov     r14, rcx
0x18003765f  lea     rdx, [rcx+48h]
0x180037663  mov     r8d, 1
0x180037669  lea     rcx, [rbp+Resource]
0x18003766d  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x180037672  nop
0x180037673  lea     r12, WPP_GLOBAL_Control
0x18003767a  lea     r13, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x180037681  mov     rdi, cs:WPP_GLOBAL_Control
0x180037688  cmp     rdi, r12
0x18003768b  jz      short loc_1800376AE
0x18003768d  test    byte ptr [rdi+1Ch], 8
0x180037691  jz      short loc_1800376AE
0x180037693  mov     edx, 38h ; '8'
0x180037698  mov     r9, rsi
0x18003769b  mov     r8, r13
0x18003769e  mov     rcx, [rdi+10h]
0x1800376a2  call    WPP_SF__guid_
0x1800376a7  mov     rdi, cs:WPP_GLOBAL_Control
0x1800376ae  mov     rax, qword ptr cs:Vault_DefaultVault_ID.Data1
0x1800376b5  sub     rax, [rsi]
0x1800376b8  jnz     short loc_1800376C5
0x1800376ba  mov     rax, qword ptr cs:Vault_DefaultVault_ID.Data4
0x1800376c1  sub     rax, [rsi+8]
0x1800376c5  test    rax, rax
0x1800376c8  jnz     short loc_1800376DA
0x1800376ca  cmp     rdi, r12
0x1800376cd  jz      short loc_180037711
0x1800376cf  test    byte ptr [rdi+1Ch], 2
0x1800376d3  jz      short loc_180037711
0x1800376d5  lea     edx, [rax+39h]
0x1800376d8  jmp     short loc_180037704
0x1800376da  mov     rax, qword ptr cs:Vault_CredmanVault_ID
0x1800376e1  sub     rax, [rsi]
0x1800376e4  jnz     short loc_1800376F1
0x1800376e6  mov     rax, qword ptr cs:Vault_CredmanVault_ID+8
0x1800376ed  sub     rax, [rsi+8]
0x1800376f1  test    rax, rax
0x1800376f4  jnz     short loc_18003772B
0x1800376f6  cmp     rdi, r12
0x1800376f9  jz      short loc_180037711
0x1800376fb  test    byte ptr [rdi+1Ch], 2
0x1800376ff  jz      short loc_180037711
0x180037701  lea     edx, [rax+3Ah]
0x180037704  mov     r8, r13
0x180037707  mov     rcx, [rdi+10h]
0x18003770b  call    WPP_SF_
0x180037710  nop
0x180037711  cmp     [rbp+var_8], 0
0x180037715  jz      short loc_180037721
0x180037717  mov     rcx, [rbp+Resource]; Resource
0x18003771b  call    cs:__imp_RtlReleaseResource
0x180037721  mov     eax, 32h ; '2'
0x180037726  jmp     loc_180037848
0x18003772b  mov     r8, rsi
0x18003772e  lea     rdx, [rbp+arg_0]
0x180037732  lea     rcx, [r14+10h]
0x180037736  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCUserVault@@UGuidCmp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::find(_GUID const &)
0x18003773b  mov     rbx, [rax]
0x18003773e  cmp     rbx, [r14+10h]
0x180037742  jnz     short loc_18003777E
0x180037744  cmp     rdi, r12
0x180037747  jz      short loc_180037764
0x180037749  test    byte ptr [rdi+1Ch], 2
0x18003774d  jz      short loc_180037764
0x18003774f  mov     edx, 3Bh ; ';'
0x180037754  mov     r9, rsi
0x180037757  mov     r8, r13
0x18003775a  mov     rcx, [rdi+10h]
0x18003775e  call    WPP_SF__guid_
0x180037763  nop
0x180037764  cmp     [rbp+var_8], 0
0x180037768  jz      short loc_180037774
0x18003776a  mov     rcx, [rbp+Resource]; Resource
0x18003776e  call    cs:__imp_RtlReleaseResource
0x180037774  mov     eax, 490h
0x180037779  jmp     loc_180037848
0x18003777e  mov     rcx, [rbx+30h]; this
0x180037782  cmp     dword ptr [rcx+6Ch], 0
0x180037786  jnz     short loc_1800377C2
0x180037788  cmp     rdi, r12
0x18003778b  jz      short loc_1800377A8
0x18003778d  test    byte ptr [rdi+1Ch], 2
0x180037791  jz      short loc_1800377A8
0x180037793  mov     edx, 3Ch ; '<'
0x180037798  mov     r9, rsi
0x18003779b  mov     r8, r13
0x18003779e  mov     rcx, [rdi+10h]
0x1800377a2  call    WPP_SF__guid_
0x1800377a7  nop
0x1800377a8  cmp     [rbp+var_8], 0
0x1800377ac  jz      short loc_1800377B8
0x1800377ae  mov     rcx, [rbp+Resource]; Resource
0x1800377b2  call    cs:__imp_RtlReleaseResource
0x1800377b8  mov     eax, 0D4h
0x1800377bd  jmp     loc_180037848
0x1800377c2  call    ?DeleteUserVault@CUserVault@@QEAAKE@Z; CUserVault::DeleteUserVault(uchar)
0x1800377c7  mov     edi, eax
0x1800377c9  test    eax, eax
0x1800377cb  jz      short loc_18003780C
0x1800377cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377d4  cmp     rcx, r12
0x1800377d7  jz      short loc_1800377F8
0x1800377d9  test    byte ptr [rcx+1Ch], 2
0x1800377dd  jz      short loc_1800377F8
0x1800377df  mov     edx, 3Dh ; '='
0x1800377e4  mov     [rsp+40h+var_20], eax
0x1800377e8  mov     r9, rsi
0x1800377eb  mov     r8, r13
0x1800377ee  mov     rcx, [rcx+10h]
0x1800377f2  call    WPP_SF__guid_D
0x1800377f7  nop
0x1800377f8  cmp     [rbp+var_8], 0
0x1800377fc  jz      short loc_180037808
0x1800377fe  mov     rcx, [rbp+Resource]; Resource
0x180037802  call    cs:__imp_RtlReleaseResource
0x180037808  mov     eax, edi
0x18003780a  jmp     short loc_180037848
0x18003780c  mov     rcx, [rbx+30h]
0x180037810  mov     rax, [rcx]
0x180037813  mov     rax, [rax+8]
0x180037817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003781c  mov     rdx, rbx
0x18003781f  lea     rcx, [r14+10h]
0x180037823  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>,std::_Iterator_base0>)
0x180037828  mov     edx, 38h ; '8'
0x18003782d  mov     rcx, rax
0x180037830  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180037835  nop
0x180037836  cmp     [rbp+var_8], 0
0x18003783a  jz      short loc_180037846
0x18003783c  mov     rcx, [rbp+Resource]; Resource
0x180037840  call    cs:__imp_RtlReleaseResource
0x180037846  xor     eax, eax
0x180037848  lea     r11, [rsp+40h+var_s0]
0x18003784d  mov     rbx, [r11+38h]
0x180037851  mov     rsi, [r11+40h]
0x180037855  mov     rsp, r11
0x180037858  pop     r14
0x18003785a  pop     r13
0x18003785c  pop     r12
0x18003785e  pop     rdi
0x18003785f  pop     rbp
0x180037860  retn
```
