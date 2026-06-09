# Windows::Networking::UX::Internal::MboLifetimePredicate::Destroy(Windows::Networking::UX::MbOperatorInfo *)

- ea: `0x18003d104`
- end: `0x18003d131`
- name: `?Destroy@MboLifetimePredicate@Internal@UX@Networking@Windows@@SAXPEAUMbOperatorInfo@345@@Z`
- size: `45`
- prototype: `void __fastcall(struct Windows::Networking::UX::MbOperatorInfo *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18001682c`
- `0x180038f94`
- `0x180039054`
- `0x180039230`
- `0x18003ae6c`
- `0x18003d560`
- `0x18003dbe0`
- `0x18003e760`
- `0x1800403e0`
- `0x1800405a0`
- `0x180040870`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d111`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d11b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d12a`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MboLifetimePredicate::Destroy(HSTRING *a1)
{
  WindowsDeleteString(a1[1]);
  WindowsDeleteString(a1[2]);
  WindowsDeleteString(a1[3]);
}

```

## disassembly

```asm
0x18003d104  push    rbx
0x18003d106  sub     rsp, 20h
0x18003d10a  mov     rbx, rcx
0x18003d10d  mov     rcx, [rcx+8]; string
0x18003d111  call    cs:__imp_WindowsDeleteString
0x18003d117  mov     rcx, [rbx+10h]; string
0x18003d11b  call    cs:__imp_WindowsDeleteString
0x18003d121  mov     rcx, [rbx+18h]
0x18003d125  add     rsp, 20h
0x18003d129  pop     rbx
0x18003d12a  jmp     cs:__imp_WindowsDeleteString
```
