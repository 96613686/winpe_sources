# FwppAllocateDelayedInjectionContext

- ea: `0x1800021f4`
- end: `0x180002277`
- name: `FwppAllocateDelayedInjectionContext`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180001cd0`
- `0x180002280`
- `0x1800025b0`
- `0x180002910`

## callees

- `0x1800021f4`
- `0x180004904`
- `0x18000c9b4`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000220a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000220a`

## string_xrefs

- `0x180002243`: `ExAllocateFromNPagedLookasideList`
- `0x180002257`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppAllocateDelayedInjectionContext(void **a1)
{
  __int64 v2; // rbx
  PVOID v3; // rax
  __int64 v4; // rcx
  __int64 v6; // rax

  v2 = 0;
  v3 = ExAllocateFromNPagedLookasideList(&Lookaside);
  *a1 = v3;
  if ( v3
    || (v6 = WfpReportSysErrorAsNtStatus(v4, (int)"ExAllocateFromNPagedLookasideList", -1073741801), (v2 = v6) == 0) )
  {
    memset(*a1, 0, 0xA0u);
  }
  else
  {
    WfpReportError(v6, (int)"WfpAllocFromNPagedLookasideList");
    WfpReportError(v2, (int)"FwppAllocateDelayedInjectionContext");
  }
  return v2;
}

```

## disassembly

```asm
0x1800021f4  mov     [rsp+arg_0], rbx
0x1800021f9  push    rdi
0x1800021fa  sub     rsp, 20h
0x1800021fe  mov     rdi, rcx
0x180002201  xor     ebx, ebx
0x180002203  lea     rcx, Lookaside; Lookaside
0x18000220a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180002211  nop     dword ptr [rax+rax+00h]
0x180002216  mov     [rdi], rax
0x180002219  test    rax, rax
0x18000221c  jz      short loc_18000223D
0x18000221e  mov     rcx, [rdi]; void *
0x180002221  xor     edx, edx; Val
0x180002223  mov     r8d, 0A0h; Size
0x180002229  call    memset
0x18000222e  mov     rax, rbx
0x180002231  mov     rbx, [rsp+28h+arg_0]
0x180002236  add     rsp, 20h
0x18000223a  pop     rdi
0x18000223b  retn
0x18000223d  mov     r8d, 0C0000017h
0x180002243  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x18000224a  call    WfpReportSysErrorAsNtStatus
0x18000224f  mov     rbx, rax
0x180002252  test    rax, rax
0x180002255  jz      short loc_18000221E
0x180002257  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x18000225e  mov     rcx, rax
0x180002261  call    WfpReportError
0x180002266  lea     rdx, aFwppallocatede_0; "FwppAllocateDelayedInjectionContext"
0x18000226d  mov     rcx, rbx
0x180002270  call    WfpReportError
0x180002275  jmp     short loc_18000222E
```
