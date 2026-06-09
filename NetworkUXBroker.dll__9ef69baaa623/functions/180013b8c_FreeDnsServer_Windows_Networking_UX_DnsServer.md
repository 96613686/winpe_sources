# FreeDnsServer(Windows::Networking::UX::DnsServer *)

- ea: `0x180013b8c`
- end: `0x180013baf`
- name: `?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z`
- size: `35`
- prototype: `void __fastcall(struct Windows::Networking::UX::DnsServer *)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x180010030`
- `0x18001026c`
- `0x180011c78`
- `0x180011f94`
- `0x180012680`
- `0x18001281c`
- `0x180012c10`
- `0x180012f00`
- `0x180014df0`
- `0x180015400`
- `0x180016d54`
- `0x180017be0`
- `0x180018de0`
- `0x180018fa0`
- `0x1800192f0`
- `0x180019df8`
- `0x18001a27c`
- `0x180039ec0`
- `0x18003a438`
- `0x18003a920`
- `0x18003e424`
- `0x180043730`
- `0x1800439a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013ba8`

## pseudocode

```c
void __fastcall FreeDnsServer(HSTRING *a1)
{
  WindowsDeleteString(a1[1]);
  WindowsDeleteString(a1[2]);
}

```

## disassembly

```asm
0x180013b8c  push    rbx
0x180013b8e  sub     rsp, 20h
0x180013b92  mov     rbx, rcx
0x180013b95  mov     rcx, [rcx+8]; string
0x180013b99  call    cs:__imp_WindowsDeleteString
0x180013b9f  mov     rcx, [rbx+10h]
0x180013ba3  add     rsp, 20h
0x180013ba7  pop     rbx
0x180013ba8  jmp     cs:__imp_WindowsDeleteString
```
