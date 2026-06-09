# DealWithDeviceEvent

- ea: `0x180008df0`
- end: `0x180008e38`
- name: `DealWithDeviceEvent`
- size: `72`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006758`
- `0x180006a10`

## callees

- `0x180005370`
- `0x180008570`
- `0x180008df0`
- `0x18000a980`

## import_xrefs

- `ntdll!NtSetUuidSeed` at `0x180008e20`
- `ntdll!NtSetUuidSeed` at `0x180008e20`

## pseudocode

```c
NTSTATUS DealWithDeviceEvent()
{
  UCHAR UuidSeed[8]; // [rsp+20h] [rbp-18h] BYREF

  if ( !getMacAddress(UuidSeed) )
    CookupNodeId(UuidSeed);
  return NtSetUuidSeed(UuidSeed);
}

```

## disassembly

```asm
0x180008df0  sub     rsp, 38h
0x180008df4  mov     rax, cs:__security_cookie
0x180008dfb  xor     rax, rsp
0x180008dfe  mov     [rsp+38h+var_10], rax
0x180008e03  lea     rcx, [rsp+38h+UuidSeed]; unsigned __int8 *
0x180008e08  call    ?getMacAddress@@YAEPEAE@Z; getMacAddress(uchar *)
0x180008e0d  lea     rcx, [rsp+38h+UuidSeed]; unsigned __int8 *
0x180008e12  test    al, al
0x180008e14  jnz     short loc_180008E20
0x180008e16  call    ?CookupNodeId@@YAXPEAE@Z; CookupNodeId(uchar *)
0x180008e1b  lea     rcx, [rsp+38h+UuidSeed]; UuidSeed
0x180008e20  call    cs:__imp_NtSetUuidSeed
0x180008e26  mov     rcx, [rsp+38h+var_10]
0x180008e2b  xor     rcx, rsp; StackCookie
0x180008e2e  call    __security_check_cookie
0x180008e33  add     rsp, 38h
0x180008e37  retn
```
