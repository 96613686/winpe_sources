# FreeDnsServer(Windows::Networking::UX::DnsServer *)

- ea: `0x18000352c`
- end: `0x18000354f`
- name: `?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z`
- size: `35`
- prototype: `void __fastcall(struct Windows::Networking::UX::DnsServer *)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023d0`
- `0x18000414c`
- `0x1800043f4`
- `0x18001e708`
- `0x18001ec40`
- `0x18001edf0`
- `0x18001eef4`
- `0x1800239cc`
- `0x180025cdc`
- `0x180025ddc`
- `0x18002711c`
- `0x18002a068`
- `0x180052e2c`
- `0x180053008`
- `0x1800535d4`
- `0x180054100`
- `0x180054b50`
- `0x180054d10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003548`

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
0x18000352c  push    rbx
0x18000352e  sub     rsp, 20h
0x180003532  mov     rbx, rcx
0x180003535  mov     rcx, [rcx+8]; string
0x180003539  call    cs:__imp_WindowsDeleteString
0x18000353f  mov     rcx, [rbx+10h]
0x180003543  add     rsp, 20h
0x180003547  pop     rbx
0x180003548  jmp     cs:__imp_WindowsDeleteString
```
