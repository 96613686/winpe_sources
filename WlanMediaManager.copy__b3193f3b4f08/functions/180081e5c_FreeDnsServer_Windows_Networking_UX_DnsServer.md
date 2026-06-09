# FreeDnsServer(Windows::Networking::UX::DnsServer *)

- ea: `0x180081e5c`
- end: `0x180081e7f`
- name: `?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z`
- size: `35`
- prototype: `void __fastcall(struct Windows::Networking::UX::DnsServer *)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18005bad4`
- `0x18005d290`
- `0x18007d734`
- `0x180080390`
- `0x1800805cc`
- `0x180081388`
- `0x1800825b0`
- `0x180083010`
- `0x180083af4`
- `0x1800845e0`
- `0x1800847a0`
- `0x180084c40`
- `0x180084ea8`
- `0x180085118`
- `0x180085368`
- `0x180086d30`
- `0x1800871f0`
- `0x1800876d8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081e78`

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
0x180081e5c  push    rbx
0x180081e5e  sub     rsp, 20h
0x180081e62  mov     rbx, rcx
0x180081e65  mov     rcx, [rcx+8]; string
0x180081e69  call    cs:__imp_WindowsDeleteString
0x180081e6f  mov     rcx, [rbx+10h]
0x180081e73  add     rsp, 20h
0x180081e77  pop     rbx
0x180081e78  jmp     cs:__imp_WindowsDeleteString
```
