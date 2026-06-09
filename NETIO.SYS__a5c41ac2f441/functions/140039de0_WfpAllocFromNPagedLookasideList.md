# WfpAllocFromNPagedLookasideList

- ea: `0x140039de0`
- end: `0x140039e3a`
- name: `WfpAllocFromNPagedLookasideList`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14006c4e8`

## callees

- `0x140009520`
- `0x140009e00`
- `0x140039de0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140039de9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140039de9`

## string_xrefs

- `0x140039e0c`: `ExAllocateFromNPagedLookasideList`
- `0x140039e26`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall WfpAllocFromNPagedLookasideList(struct _NPAGED_LOOKASIDE_LIST *a1, _QWORD *a2)
{
  PVOID v3; // rax
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // rbx

  v3 = ExAllocateFromNPagedLookasideList(a1);
  *a2 = v3;
  if ( v3 )
    return 0;
  result = WfpReportSysErrorAsNtStatus(v4, "ExAllocateFromNPagedLookasideList", 3221225495LL, 1);
  v6 = result;
  if ( result )
  {
    WfpReportError(result, "WfpAllocFromNPagedLookasideList");
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140039de0  push    rbx
0x140039de2  sub     rsp, 20h
0x140039de6  mov     rbx, rdx
0x140039de9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140039df0  nop     dword ptr [rax+rax+00h]
0x140039df5  mov     [rbx], rax
0x140039df8  test    rax, rax
0x140039dfb  jz      short loc_140039E06
0x140039dfd  xor     eax, eax
0x140039dff  add     rsp, 20h
0x140039e03  pop     rbx
0x140039e04  retn
0x140039e06  mov     r9d, 1
0x140039e0c  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x140039e13  mov     r8d, 0C0000017h
0x140039e19  call    WfpReportSysErrorAsNtStatus
0x140039e1e  mov     rbx, rax
0x140039e21  test    rax, rax
0x140039e24  jz      short loc_140039DFF
0x140039e26  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x140039e2d  mov     rcx, rax
0x140039e30  call    WfpReportError
0x140039e35  mov     rax, rbx
0x140039e38  jmp     short loc_140039DFF
```
