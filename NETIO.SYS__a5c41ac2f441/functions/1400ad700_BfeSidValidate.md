# BfeSidValidate

- ea: `0x1400ad700`
- end: `0x1400ad74d`
- name: `BfeSidValidate`
- size: `77`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14006a970`
- `0x1400ad330`

## callees

- `0x140009520`
- `0x14003c580`
- `0x1400ad700`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x1400ad708`
- `ntoskrnl!RtlValidSid` at `0x1400ad708`

## string_xrefs

- `0x1400ad728`: `BfeSidValidate`
- `0x1400ad73c`: `BfeSidValidate`

## pseudocode

```c
__int64 __fastcall BfeSidValidate(void *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v4; // rax

  v1 = 0;
  if ( !RtlValidSid(a1) )
  {
    v4 = WfpReportAppErrorAsNtStatus(v2, "BfeSidValidate", 3221225592LL);
    v1 = v4;
    if ( v4 )
      WfpReportError(v4, "BfeSidValidate");
  }
  return v1;
}

```

## disassembly

```asm
0x1400ad700  push    rbx
0x1400ad702  sub     rsp, 30h
0x1400ad706  xor     ebx, ebx
0x1400ad708  call    cs:__imp_RtlValidSid
0x1400ad70f  nop     dword ptr [rax+rax+00h]
0x1400ad714  test    al, al
0x1400ad716  jz      short loc_1400AD722
0x1400ad718  mov     rax, rbx
0x1400ad71b  add     rsp, 30h
0x1400ad71f  pop     rbx
0x1400ad720  retn
0x1400ad722  mov     r8d, 0C0000078h
0x1400ad728  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1400ad72f  call    WfpReportAppErrorAsNtStatus
0x1400ad734  mov     rbx, rax
0x1400ad737  test    rax, rax
0x1400ad73a  jz      short loc_1400AD718
0x1400ad73c  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1400ad743  mov     rcx, rax
0x1400ad746  call    WfpReportError
0x1400ad74b  jmp     short loc_1400AD718
```
