# BfeSidValidate

- ea: `0x18006550c`
- end: `0x180065557`
- name: `BfeSidValidate`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001b698`

## callees

- `0x1800050cc`
- `0x18000c9b4`
- `0x18006550c`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x180065514`
- `ntoskrnl!RtlValidSid` at `0x180065514`

## string_xrefs

- `0x18006552a`: `BfeSidValidate`
- `0x18006553e`: `BfeSidValidate`

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
    v3 = WfpReportAppErrorAsNtStatus(v2, (__int64)"BfeSidValidate", 3221225592LL);
    v1 = v3;
    if ( v3 )
      WfpReportError(v3, (int)"BfeSidValidate");
  }
  return v1;
}

```

## disassembly

```asm
0x18006550c  push    rbx
0x18006550e  sub     rsp, 30h
0x180065512  xor     ebx, ebx
0x180065514  call    cs:__imp_RtlValidSid
0x18006551b  nop     dword ptr [rax+rax+00h]
0x180065520  test    al, al
0x180065522  jnz     short loc_18006554D
0x180065524  mov     r8d, 0C0000078h
0x18006552a  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x180065531  call    WfpReportAppErrorAsNtStatus
0x180065536  mov     rbx, rax
0x180065539  test    rax, rax
0x18006553c  jz      short loc_18006554D
0x18006553e  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x180065545  mov     rcx, rax
0x180065548  call    WfpReportError
0x18006554d  mov     rax, rbx
0x180065550  add     rsp, 30h
0x180065554  pop     rbx
0x180065555  retn
```
