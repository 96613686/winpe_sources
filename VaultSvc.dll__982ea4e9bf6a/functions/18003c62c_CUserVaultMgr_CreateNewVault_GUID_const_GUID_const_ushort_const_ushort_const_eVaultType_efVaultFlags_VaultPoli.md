# CUserVaultMgr::CreateNewVault(_GUID const *,_GUID const *,ushort const *,ushort const *,eVaultType,efVaultFlags,VaultPolicy *,IVaultCall *,CUserVault * *)

- ea: `0x18003c62c`
- end: `0x18003c77c`
- name: `?CreateNewVault@CUserVaultMgr@@QEAAKPEBU_GUID@@0PEBG1W4eVaultType@@W4efVaultFlags@@PEAUVaultPolicy@@PEAUIVaultCall@@PEAPEAVCUserVault@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(CUserVaultMgr *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, struct CUserVault **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18003c4e0`

## callees

- `0x180006610`
- `0x18000d5c4`
- `0x180020a24`
- `0x180034058`
- `0x180037f5c`
- `0x18003b7d8`
- `0x18003c62c`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUserVaultMgr::CreateNewVault(
        CUserVaultMgr *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        struct CUserVault **a10)
{
  CUserVaultMgr *v12; // rcx
  const unsigned __int16 *v13; // rbx
  __int64 v14; // r8
  unsigned int NewVaultInternal; // ebx
  struct CUserVault *v16; // rbx
  unsigned int inserted; // edi
  __int64 (__fastcall *v18)(__int64); // [rsp+60h] [rbp-48h] BYREF
  struct CUserVault *v19; // [rsp+68h] [rbp-40h] BYREF
  int v20; // [rsp+70h] [rbp-38h]

  v18 = AutoDereference<IVaultKeyManager>;
  v19 = 0;
  v20 = 0;
  if ( CUserVaultMgr::GetVault(a1, &Vault_DefaultVault_ID, &v19) )
  {
    v12 = *(_BYTE *)(a8 + 8) != 0 ? (CUserVaultMgr *)8 : 0LL;
    v13 = *(const unsigned __int16 **)((char *)a1 + (_QWORD)v12 + 48);
    LOBYTE(v14) = CUserVaultMgr::IsRoamingProfilePath(v12, v13);
    NewVaultInternal = CreateNewVaultInternal(a1, v13, v14, &Vault_DefaultVault_ID);
    if ( NewVaultInternal )
    {
      CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v18);
      return NewVaultInternal;
    }
    else
    {
      v16 = v19;
      inserted = CUserVaultMgr::InsertVaultToStore(a1, v19);
      if ( inserted )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_f1575cf6446936089985711df8c7b212_Traceguids, inserted);
        CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v18);
        return inserted;
      }
      else
      {
        if ( a10 )
        {
          (**(void (__fastcall ***)(struct CUserVault *))v16)(v16);
          *a10 = v16;
        }
        CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v18);
        return 0;
      }
    }
  }
  else
  {
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v18);
    return 183;
  }
}

```

## disassembly

```asm
0x18003c62c  push    rbx
0x18003c62e  push    rbp
0x18003c62f  push    rsi
0x18003c630  push    rdi
0x18003c631  sub     rsp, 88h
0x18003c638  mov     rbp, r9
0x18003c63b  mov     rsi, rcx
0x18003c63e  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18003c645  mov     [rsp+0A8h+var_48], rax
0x18003c64a  mov     [rsp+0A8h+var_40], 0
0x18003c653  mov     [rsp+0A8h+var_38], 0
0x18003c65b  lea     r8, [rsp+0A8h+var_40]; struct CUserVault **
0x18003c660  lea     rdx, Vault_DefaultVault_ID; struct _GUID *
0x18003c667  call    ?GetVault@CUserVaultMgr@@QEAAKPEBU_GUID@@PEAPEAVCUserVault@@@Z; CUserVaultMgr::GetVault(_GUID const *,CUserVault * *)
0x18003c66c  test    eax, eax
0x18003c66e  jnz     short loc_18003C685
0x18003c670  lea     rcx, [rsp+0A8h+var_48]
0x18003c675  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18003c67a  nop
0x18003c67b  mov     eax, 0B7h
0x18003c680  jmp     loc_18003C770
0x18003c685  mov     rdi, [rsp+0A8h+arg_38]
0x18003c68d  mov     al, [rdi+8]
0x18003c690  neg     al
0x18003c692  sbb     rcx, rcx
0x18003c695  and     ecx, 8; this
0x18003c698  mov     rbx, [rcx+rsi+30h]
0x18003c69d  mov     rdx, rbx; unsigned __int16 *
0x18003c6a0  call    ?IsRoamingProfilePath@CUserVaultMgr@@AEAAEPEBG@Z; CUserVaultMgr::IsRoamingProfilePath(ushort const *)
0x18003c6a5  lea     rcx, [rsp+0A8h+var_40]
0x18003c6aa  mov     [rsp+0A8h+var_58], rcx
0x18003c6af  mov     [rsp+0A8h+var_68], rdi
0x18003c6b4  mov     [rsp+0A8h+var_78], 1
0x18003c6bc  mov     [rsp+0A8h+var_80], rbp
0x18003c6c1  lea     r9, Vault_DefaultVault_ID
0x18003c6c8  mov     r8b, al
0x18003c6cb  mov     rdx, rbx
0x18003c6ce  mov     rcx, rsi
0x18003c6d1  call    ?CreateNewVaultInternal@@YAKPEAVCUserVaultMgr@@PEBGEPEBU_GUID@@21W4eVaultType@@W4efVaultFlags@@PEAUVaultPolicy@@PEAUIVaultCall@@PEAPEAVCUserVault@@@Z; CreateNewVaultInternal(CUserVaultMgr *,ushort const *,uchar,_GUID const *,_GUID const *,ushort const *,eVaultType,efVaultFlags,VaultPolicy *,IVaultCall *,CUserVault * *)
0x18003c6d6  mov     ebx, eax
0x18003c6d8  test    eax, eax
0x18003c6da  jz      short loc_18003C6EE
0x18003c6dc  lea     rcx, [rsp+0A8h+var_48]
0x18003c6e1  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18003c6e6  nop
0x18003c6e7  mov     eax, ebx
0x18003c6e9  jmp     loc_18003C770
0x18003c6ee  mov     rbx, [rsp+0A8h+var_40]
0x18003c6f3  mov     rdx, rbx; struct CUserVault *
0x18003c6f6  mov     rcx, rsi; this
0x18003c6f9  call    ?InsertVaultToStore@CUserVaultMgr@@AEAAKPEAVCUserVault@@@Z; CUserVaultMgr::InsertVaultToStore(CUserVault *)
0x18003c6fe  mov     edi, eax
0x18003c700  test    eax, eax
0x18003c702  jz      short loc_18003C745
0x18003c704  lea     rax, WPP_GLOBAL_Control
0x18003c70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c712  cmp     rcx, rax
0x18003c715  jz      short loc_18003C736
0x18003c717  test    byte ptr [rcx+1Ch], 2
0x18003c71b  jz      short loc_18003C736
0x18003c71d  mov     edx, 3Eh ; '>'
0x18003c722  mov     r9d, edi
0x18003c725  lea     r8, WPP_f1575cf6446936089985711df8c7b212_Traceguids
0x18003c72c  mov     rcx, [rcx+10h]
0x18003c730  call    WPP_SF_d
0x18003c735  nop
0x18003c736  lea     rcx, [rsp+0A8h+var_48]
0x18003c73b  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18003c740  nop
0x18003c741  mov     eax, edi
0x18003c743  jmp     short loc_18003C770
0x18003c745  mov     rdi, [rsp+0A8h+arg_48]
0x18003c74d  test    rdi, rdi
0x18003c750  jz      short loc_18003C763
0x18003c752  mov     rax, [rbx]
0x18003c755  mov     rcx, rbx
0x18003c758  mov     rax, [rax]
0x18003c75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c760  mov     [rdi], rbx
0x18003c763  lea     rcx, [rsp+0A8h+var_48]
0x18003c768  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18003c76d  nop
0x18003c76e  xor     eax, eax
0x18003c770  add     rsp, 88h
0x18003c777  pop     rdi
0x18003c778  pop     rsi
0x18003c779  pop     rbp
0x18003c77a  pop     rbx
0x18003c77b  retn
```
