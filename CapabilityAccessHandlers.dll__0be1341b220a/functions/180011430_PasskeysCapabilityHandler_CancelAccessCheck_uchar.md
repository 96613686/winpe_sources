# PasskeysCapabilityHandler::CancelAccessCheck(uchar *)

- ea: `0x180011430`
- end: `0x180011440`
- name: `?CancelAccessCheck@PasskeysCapabilityHandler@@UEAAJPEAE@Z`
- size: `16`
- prototype: `__int64 __fastcall(PasskeysCapabilityHandler *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180011430`

## pseudocode

```c
__int64 __fastcall PasskeysCapabilityHandler::CancelAccessCheck(PasskeysCapabilityHandler *this, unsigned __int8 *a2)
{
  __int64 result; // rax

  result = 0;
  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180011430  xor     eax, eax
0x180011432  test    rdx, rdx
0x180011435  jnz     short loc_18001143D
0x180011437  mov     eax, 80070057h
0x18001143c  retn
0x18001143d  mov     [rdx], al
0x18001143f  retn
```
