# BfeSidValidate

- ea: `0x1800565d0`
- end: `0x180056614`
- name: `BfeSidValidate`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180023300`
- `0x180076eb0`

## callees

- `0x180012b54`
- `0x180018b74`
- `0x1800565d0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800565d8`
- `ntdll!RtlValidSid` at `0x1800565d8`

## string_xrefs

- `0x1800565e8`: `BfeSidValidate`
- `0x1800565fc`: `BfeSidValidate`

## pseudocode

```c
__int64 __fastcall BfeSidValidate(void *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rax

  v1 = 0;
  if ( !RtlValidSid(a1) )
  {
    v3 = WfpReportSysErrorAsNtStatus(v2, "BfeSidValidate", 3221225592LL);
    v1 = v3;
    if ( v3 )
      WfpReportError(v3, "BfeSidValidate");
  }
  return v1;
}

```

## disassembly

```asm
0x1800565d0  push    rbx
0x1800565d2  sub     rsp, 20h
0x1800565d6  xor     ebx, ebx
0x1800565d8  call    cs:__imp_RtlValidSid
0x1800565de  test    al, al
0x1800565e0  jnz     short loc_18005660B
0x1800565e2  mov     r8d, 0C0000078h
0x1800565e8  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1800565ef  call    WfpReportSysErrorAsNtStatus
0x1800565f4  mov     rbx, rax
0x1800565f7  test    rax, rax
0x1800565fa  jz      short loc_18005660B
0x1800565fc  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x180056603  mov     rcx, rax
0x180056606  call    WfpReportError
0x18005660b  mov     rax, rbx
0x18005660e  add     rsp, 20h
0x180056612  pop     rbx
0x180056613  retn
```
