# Microsoft::CoreUI::HvSockets::HvSocket::UninitializeWinSockets(void)

- ea: `0x1800b5408`
- end: `0x1800b5421`
- name: `?UninitializeWinSockets@HvSocket@HvSockets@CoreUI@Microsoft@@SAXXZ`
- size: `25`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ada00`
- `0x1800b7ea4`

## callees

- `0x18008f584`
- `0x1800b5408`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1800b540c`
- `WS2_32!__imp_WSACleanup` at `0x1800b540c`

## pseudocode

```c
void Microsoft::CoreUI::HvSockets::HvSocket::UninitializeWinSockets(void)
{
  if ( WSACleanup() )
    Cn::FailFast::ForWin32();
}

```

## disassembly

```asm
0x1800b5408  sub     rsp, 28h
0x1800b540c  call    cs:__imp_WSACleanup
0x1800b5412  test    eax, eax
0x1800b5414  jz      short loc_1800B541C
0x1800b5416  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
0x1800b541c  add     rsp, 28h
0x1800b5420  retn
```
