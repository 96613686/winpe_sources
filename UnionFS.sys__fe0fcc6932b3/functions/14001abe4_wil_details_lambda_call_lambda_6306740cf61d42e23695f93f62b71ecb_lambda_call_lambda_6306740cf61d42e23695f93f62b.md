# wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___

- ea: `0x14001abe4`
- end: `0x14001acc5`
- name: `wil::details::lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___::_lambda_call__lambda_6306740cf61d42e23695f93f62b71ecb___`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001af94`
- `0x140077a60`

## callees

- `0x14001abe4`

## import_xrefs

- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14001ac4d`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x14001ac4d`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001acad`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001acad`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001ac19`
- `FLTMGR!FltIsEcpAcknowledged` at `0x14001ac19`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ac94`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ac94`
- `FLTMGR!FltObjectDereference` at `0x14001ac64`
- `FLTMGR!FltObjectDereference` at `0x14001ac7c`
- `FLTMGR!FltObjectDereference` at `0x14001ac64`
- `FLTMGR!FltObjectDereference` at `0x14001ac7c`

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
0x14001abe4  mov     [rsp+arg_0], rbx
0x14001abe9  push    rdi
0x14001abea  sub     rsp, 30h
0x14001abee  cmp     byte ptr [rcx+10h], 0
0x14001abf2  mov     rdi, rcx
0x14001abf5  jz      loc_14001ACB9
0x14001abfb  lea     rbx, [rcx+8]
0x14001abff  mov     byte ptr [rcx+10h], 0
0x14001ac03  mov     rdx, [rbx]; EcpContext
0x14001ac06  test    rdx, rdx
0x14001ac09  jz      loc_14001ACB9
0x14001ac0f  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ac16  mov     rcx, [rcx]; Filter
0x14001ac19  call    cs:__imp_FltIsEcpAcknowledged
0x14001ac20  nop     dword ptr [rax+rax+00h]
0x14001ac25  test    al, al
0x14001ac27  jz      loc_14001ACB9
0x14001ac2d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ac34  lea     r8, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x14001ac3b  mov     rdx, [rdi]; EcpList
0x14001ac3e  mov     r9, rbx; EcpContext
0x14001ac41  mov     [rsp+38h+EcpContextSize], 0; EcpContextSize
0x14001ac4a  mov     rcx, [rcx]; Filter
0x14001ac4d  call    cs:__imp_FltRemoveExtraCreateParameter
0x14001ac54  nop     dword ptr [rax+rax+00h]
0x14001ac59  mov     rax, [rbx]
0x14001ac5c  mov     rcx, [rax]; FltObject
0x14001ac5f  test    rcx, rcx
0x14001ac62  jz      short loc_14001AC70
0x14001ac64  call    cs:__imp_FltObjectDereference
0x14001ac6b  nop     dword ptr [rax+rax+00h]
0x14001ac70  mov     rax, [rbx]
0x14001ac73  mov     rcx, [rax+8]; FltObject
0x14001ac77  test    rcx, rcx
0x14001ac7a  jz      short loc_14001AC88
0x14001ac7c  call    cs:__imp_FltObjectDereference
0x14001ac83  nop     dword ptr [rax+rax+00h]
0x14001ac88  mov     rax, [rbx]
0x14001ac8b  mov     rcx, [rax+10h]; FileNameInformation
0x14001ac8f  test    rcx, rcx
0x14001ac92  jz      short loc_14001ACA0
0x14001ac94  call    cs:__imp_FltReleaseFileNameInformation
0x14001ac9b  nop     dword ptr [rax+rax+00h]
0x14001aca0  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001aca7  mov     rdx, [rbx]; EcpContext
0x14001acaa  mov     rcx, [rcx]; Filter
0x14001acad  call    cs:__imp_FltFreeExtraCreateParameter
0x14001acb4  nop     dword ptr [rax+rax+00h]
0x14001acb9  mov     rbx, [rsp+38h+arg_0]
0x14001acbe  add     rsp, 30h
0x14001acc2  pop     rdi
0x14001acc3  retn
```
