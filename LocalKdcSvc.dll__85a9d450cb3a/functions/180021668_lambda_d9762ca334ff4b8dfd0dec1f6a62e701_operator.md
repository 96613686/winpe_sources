# _lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()

- ea: `0x180021668`
- end: `0x1800216c3`
- name: `_lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180020d58`
- `0x180028d24`

## callees

- `0x18001e8c8`
- `0x180021668`
- `0x18002b380`
- `0x18005c2a4`

## import_xrefs

- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800216b7`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800216b7`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180021695`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180021695`

## pseudocode

```c
char __fastcall lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(__int64 a1)
{
  _QWORD *v2; // rax

  KdcFreeDmsaKeyList(**(struct KERB_KEY_LIST_REP_s ***)a1);
  KdcFreeDmsaKeyList(**(struct KERB_KEY_LIST_REP_s ***)(a1 + 8));
  FreeTicketInfo(*(struct _KDC_TICKET_INFO **)(a1 + 16));
  SamIFreeSidAndAttributesList(*(_QWORD *)(a1 + 24));
  LOBYTE(v2) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl'::`2'::impl);
  if ( (_BYTE)v2 )
  {
    v2 = *(_QWORD **)(a1 + 32);
    if ( *v2 )
      LOBYTE(v2) = SamIFree_UserInternal6Information(*v2);
  }
  return (char)v2;
}

```

## disassembly

```asm
0x180021668  push    rbx
0x18002166a  sub     rsp, 20h
0x18002166e  mov     rbx, rcx
0x180021671  mov     rcx, [rcx]
0x180021674  mov     rcx, [rcx]; struct KERB_KEY_LIST_REP_s *
0x180021677  call    ?KdcFreeDmsaKeyList@@YAXPEAUKERB_KEY_LIST_REP_s@@@Z; KdcFreeDmsaKeyList(KERB_KEY_LIST_REP_s *)
0x18002167c  mov     rcx, [rbx+8]
0x180021680  mov     rcx, [rcx]; struct KERB_KEY_LIST_REP_s *
0x180021683  call    ?KdcFreeDmsaKeyList@@YAXPEAUKERB_KEY_LIST_REP_s@@@Z; KdcFreeDmsaKeyList(KERB_KEY_LIST_REP_s *)
0x180021688  mov     rcx, [rbx+10h]; struct _KDC_TICKET_INFO *
0x18002168c  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180021691  mov     rcx, [rbx+18h]
0x180021695  call    cs:__imp_SamIFreeSidAndAttributesList
0x18002169b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl(void)'::`2'::impl
0x1800216a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled(void)
0x1800216a7  test    al, al
0x1800216a9  jz      short loc_1800216BD
0x1800216ab  mov     rax, [rbx+20h]
0x1800216af  mov     rcx, [rax]
0x1800216b2  test    rcx, rcx
0x1800216b5  jz      short loc_1800216BD
0x1800216b7  call    cs:__imp_SamIFree_UserInternal6Information
0x1800216bd  add     rsp, 20h
0x1800216c1  pop     rbx
0x1800216c2  retn
```
