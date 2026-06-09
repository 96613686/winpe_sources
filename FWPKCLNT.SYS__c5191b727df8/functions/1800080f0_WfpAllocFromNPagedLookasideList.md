# WfpAllocFromNPagedLookasideList

- ea: `0x1800080f0`
- end: `0x180008144`
- name: `WfpAllocFromNPagedLookasideList`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001c88c`
- `0x18001ca04`
- `0x18001ce30`

## callees

- `0x180004904`
- `0x1800080f0`
- `0x18000c9b4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800080f9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800080f9`

## string_xrefs

- `0x18000811c`: `ExAllocateFromNPagedLookasideList`
- `0x180008130`: `WfpAllocFromNPagedLookasideList`

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
  result = WfpReportSysErrorAsNtStatus(v4, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
  v6 = result;
  if ( result )
  {
    WfpReportError(result, (int)"WfpAllocFromNPagedLookasideList");
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800080f0  push    rbx
0x1800080f2  sub     rsp, 20h
0x1800080f6  mov     rbx, rdx
0x1800080f9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180008100  nop     dword ptr [rax+rax+00h]
0x180008105  mov     [rbx], rax
0x180008108  test    rax, rax
0x18000810b  jz      short loc_180008116
0x18000810d  xor     eax, eax
0x18000810f  add     rsp, 20h
0x180008113  pop     rbx
0x180008114  retn
0x180008116  mov     r8d, 0C0000017h
0x18000811c  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180008123  call    WfpReportSysErrorAsNtStatus
0x180008128  mov     rbx, rax
0x18000812b  test    rax, rax
0x18000812e  jz      short loc_18000810F
0x180008130  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x180008137  mov     rcx, rax
0x18000813a  call    WfpReportError
0x18000813f  mov     rax, rbx
0x180008142  jmp     short loc_18000810F
```
