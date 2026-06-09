# Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose(void)

- ea: `0x18000be60`
- end: `0x18000be75`
- name: `?InternalClose@?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `21`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006c00`
- `0x18000762c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000be68`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000be68`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose(__int64 a1)
{
  FreeSid(*(PSID *)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x18000be60  sub     rsp, 28h
0x18000be64  mov     rcx, [rcx+8]; pSid
0x18000be68  call    cs:__imp_FreeSid
0x18000be6e  mov     al, 1
0x18000be70  add     rsp, 28h
0x18000be74  retn
```
