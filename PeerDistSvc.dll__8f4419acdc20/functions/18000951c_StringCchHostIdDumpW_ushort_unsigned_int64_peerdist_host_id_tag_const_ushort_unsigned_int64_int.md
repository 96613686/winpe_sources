# StringCchHostIdDumpW(ushort *,unsigned __int64,peerdist_host_id_tag const *,ushort * *,unsigned __int64 *,int)

- ea: `0x18000951c`
- end: `0x18000983d`
- name: `?StringCchHostIdDumpW@@YAJPEAG_KPEBUpeerdist_host_id_tag@@PEAPEAGPEA_KH@Z`
- size: `801`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPWSTR pszDest@<rcx>, unsigned __int64@<rdx>, const struct peerdist_host_id_tag *@<r8>, unsigned __int16 **@<r9>, unsigned __int64 *, int)`
- caller_count: `11`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000a7f4`
- `0x18000ab20`
- `0x18000ae54`
- `0x18000b230`
- `0x18000b3a4`
- `0x18000bd10`
- `0x1800a96a4`
- `0x1800b0e6c`
- `0x1800bbf18`
- `0x1800ce8a0`
- `0x1800e20fc`

## callees

- `0x180009168`
- `0x180009354`
- `0x18000951c`
- `0x1800099e0`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `WS2_32!WSAAddressToStringW` at `0x180009740`
- `WS2_32!WSAAddressToStringW` at `0x180009740`
- `WS2_32!__imp_WSAGetLastError` at `0x180009770`
- `WS2_32!__imp_WSAGetLastError` at `0x180009770`
- `WS2_32!__imp_WSAStartup` at `0x180009707`
- `WS2_32!__imp_WSAStartup` at `0x180009707`
- `WS2_32!__imp_WSACleanup` at `0x180009799`
- `WS2_32!__imp_WSACleanup` at `0x180009799`

## pseudocode

```c

```
