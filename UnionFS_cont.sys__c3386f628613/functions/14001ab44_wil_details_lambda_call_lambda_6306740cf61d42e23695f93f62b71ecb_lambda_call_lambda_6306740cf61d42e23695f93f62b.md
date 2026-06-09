# wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___

- ea: `0x14001ab44`
- end: `0x14001ac25`
- name: `wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001aef4`
- `0x140077774`

## callees

- `0x14001ab44`

## import_xrefs

- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14001abad`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14001abad`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001ac0d`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001ac0d`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001ab79`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001ab79`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001abf4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001abf4`
- `FLTMGR!FltObjectDereference` at `0x14001abc4`
- `FLTMGR!FltObjectDereference` at `0x14001abdc`
- `FLTMGR!FltObjectDereference` at `0x14001abc4`
- `FLTMGR!FltObjectDereference` at `0x14001abdc`

## pseudocode

```c
void __fastcall wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___(
        __int64 a1)
{
  PVOID *v2; // rbx
  void *v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v6; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    v2 = (PVOID *)(a1 + 8);
    *(_BYTE *)(a1 + 16) = 0;
    v3 = *(void **)(a1 + 8);
    if ( v3 )
    {
      if ( FltIsEcpAcknowledged(*(PFLT_FILTER *)UnionFs::g_FilterState, v3) )
      {
        FltRemoveExtraCreateParameter(
          *(PFLT_FILTER *)UnionFs::g_FilterState,
          *(PECP_LIST *)a1,
          &GUID_ECP_FLT_CREATEFILE_TARGET,
          v2,
          0);
        v4 = *(void **)*v2;
        if ( v4 )
          FltObjectDereference(v4);
        v5 = (void *)*((_QWORD *)*v2 + 1);
        if ( v5 )
          FltObjectDereference(v5);
        v6 = (struct _FLT_FILE_NAME_INFORMATION *)*((_QWORD *)*v2 + 2);
        if ( v6 )
          FltReleaseFileNameInformation(v6);
        FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, *v2);
      }
    }
  }
}

```

## disassembly

```asm
0x14001ab44  mov     [rsp+arg_0], rbx
0x14001ab49  push    rdi
0x14001ab4a  sub     rsp, 30h
0x14001ab4e  cmp     byte ptr [rcx+10h], 0
0x14001ab52  mov     rdi, rcx
0x14001ab55  jz      loc_14001AC19
0x14001ab5b  lea     rbx, [rcx+8]
0x14001ab5f  mov     byte ptr [rcx+10h], 0
0x14001ab63  mov     rdx, [rbx]; EcpContext
0x14001ab66  test    rdx, rdx
0x14001ab69  jz      loc_14001AC19
0x14001ab6f  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ab76  mov     rcx, [rcx]; Filter
0x14001ab79  call    cs:__imp_FltIsEcpAcknowledged
0x14001ab80  nop     dword ptr [rax+rax+00h]
0x14001ab85  test    al, al
0x14001ab87  jz      loc_14001AC19
0x14001ab8d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ab94  lea     r8, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14001ab9b  mov     rdx, [rdi]; EcpList
0x14001ab9e  mov     r9, rbx; EcpContext
0x14001aba1  mov     [rsp+38h+EcpContextSize], 0; EcpContextSize
0x14001abaa  mov     rcx, [rcx]; Filter
0x14001abad  call    cs:__imp_FltRemoveExtraCreateParameter
0x14001abb4  nop     dword ptr [rax+rax+00h]
0x14001abb9  mov     rax, [rbx]
0x14001abbc  mov     rcx, [rax]; FltObject
0x14001abbf  test    rcx, rcx
0x14001abc2  jz      short loc_14001ABD0
0x14001abc4  call    cs:__imp_FltObjectDereference
0x14001abcb  nop     dword ptr [rax+rax+00h]
0x14001abd0  mov     rax, [rbx]
0x14001abd3  mov     rcx, [rax+8]; FltObject
0x14001abd7  test    rcx, rcx
0x14001abda  jz      short loc_14001ABE8
0x14001abdc  call    cs:__imp_FltObjectDereference
0x14001abe3  nop     dword ptr [rax+rax+00h]
0x14001abe8  mov     rax, [rbx]
0x14001abeb  mov     rcx, [rax+10h]; FileNameInformation
0x14001abef  test    rcx, rcx
0x14001abf2  jz      short loc_14001AC00
0x14001abf4  call    cs:__imp_FltReleaseFileNameInformation
0x14001abfb  nop     dword ptr [rax+rax+00h]
0x14001ac00  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ac07  mov     rdx, [rbx]; EcpContext
0x14001ac0a  mov     rcx, [rcx]; Filter
0x14001ac0d  call    cs:__imp_FltFreeExtraCreateParameter
0x14001ac14  nop     dword ptr [rax+rax+00h]
0x14001ac19  mov     rbx, [rsp+38h+arg_0]
0x14001ac1e  add     rsp, 30h
0x14001ac22  pop     rdi
0x14001ac23  retn
```
