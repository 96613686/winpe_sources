# BfeSidValidate

- ea: `0x1800583b0`
- end: `0x1800583fb`
- name: `BfeSidValidate`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025a10`
- `0x180079970`

## callees

- `0x1800135ac`
- `0x1800197d0`
- `0x1800583b0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800583b8`
- `ntdll!RtlValidSid` at `0x1800583b8`

## string_xrefs

- `0x1800583ce`: `BfeSidValidate`
- `0x1800583e2`: `BfeSidValidate`

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
0x1800583b0  push    rbx
0x1800583b2  sub     rsp, 20h
0x1800583b6  xor     ebx, ebx
0x1800583b8  call    cs:__imp_RtlValidSid
0x1800583bf  nop     dword ptr [rax+rax+00h]
0x1800583c4  test    al, al
0x1800583c6  jnz     short loc_1800583F1
0x1800583c8  mov     r8d, 0C0000078h
0x1800583ce  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1800583d5  call    WfpReportSysErrorAsNtStatus
0x1800583da  mov     rbx, rax
0x1800583dd  test    rax, rax
0x1800583e0  jz      short loc_1800583F1
0x1800583e2  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1800583e9  mov     rcx, rax
0x1800583ec  call    WfpReportError
0x1800583f1  mov     rax, rbx
0x1800583f4  add     rsp, 20h
0x1800583f8  pop     rbx
0x1800583f9  retn
```
