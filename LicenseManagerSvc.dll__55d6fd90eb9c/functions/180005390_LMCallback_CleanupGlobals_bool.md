# LMCallback::CleanupGlobals(bool)

- ea: `0x180005390`
- end: `0x1800053a2`
- name: `?CleanupGlobals@LMCallback@@UEAAX_N@Z`
- size: `18`
- prototype: `void __fastcall(LMCallback *__hidden this, bool)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005390`

## import_xrefs

- `LicenseManager!ServiceCleanup` at `0x180005394`
- `LicenseManager!ServiceCleanup` at `0x180005394`

## pseudocode

```c
void __fastcall LMCallback::CleanupGlobals(LMCallback *this)
{
  ServiceCleanup(this);
}

```

## disassembly

```asm
0x180005390  sub     rsp, 28h
0x180005394  call    cs:__imp_ServiceCleanup
0x18000539a  nop
0x18000539b  jmp     short $+2
0x18000539d  add     rsp, 28h
0x1800053a1  retn
```
