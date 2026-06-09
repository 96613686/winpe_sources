# CommonBuffer_RebalanceResources

- ea: `0x140023eac`
- end: `0x140023f60`
- name: `CommonBuffer_RebalanceResources`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140022f00`

## callees

- `0x14001bb78`
- `0x140023eac`
- `0x1400241b0`
- `0x140035e4c`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140023ec5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023ef5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023f30`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023ec5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023ef5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023f30`

## string_xrefs

- `0x140023f4f`: `Code Path Requires Passive Level`
- `0x140023f46`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\commonbuffer.c`

## pseudocode

```c
KIRQL __fastcall CommonBuffer_RebalanceResources(_QWORD *a1)
{
  KIRQL result; // al

  if ( *(_BYTE *)(*a1 + 1041LL) && KeGetCurrentIrql() )
    Debug_FreAssertMsg(
      "Code Path Requires Passive Level",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\commonbuffer.c",
      700);
  result = KeGetCurrentIrql();
  if ( !result || a1[9] )
  {
    result = XilCoreCommonBuffer_RebalanceResources(a1 + 11);
    if ( result )
    {
      if ( KeGetCurrentIrql() )
        return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3040))(
                 WdfDriverGlobals,
                 a1[9]);
      else
        return XilCoreCommonBuffer_FreeUnusedResources(a1 + 11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140023eac  mov     [rsp+arg_0], rbx
0x140023eb1  push    rdi
0x140023eb2  sub     rsp, 20h
0x140023eb6  mov     rax, [rcx]
0x140023eb9  mov     rbx, rcx
0x140023ebc  cmp     byte ptr [rax+411h], 0
0x140023ec3  jnz     short loc_140023F30
0x140023ec5  call    cs:__imp_KeGetCurrentIrql
0x140023ecc  nop     dword ptr [rax+rax+00h]
0x140023ed1  test    al, al
0x140023ed3  jz      short loc_140023EE8
0x140023ed5  cmp     qword ptr [rbx+48h], 0
0x140023eda  jnz     short loc_140023EE8
0x140023edc  mov     rbx, [rsp+28h+arg_0]
0x140023ee1  add     rsp, 20h
0x140023ee5  pop     rdi
0x140023ee6  retn
0x140023ee8  lea     rcx, [rbx+58h]
0x140023eec  call    XilCoreCommonBuffer_RebalanceResources
0x140023ef1  test    al, al
0x140023ef3  jz      short loc_140023EDC
0x140023ef5  call    cs:__imp_KeGetCurrentIrql
0x140023efc  nop     dword ptr [rax+rax+00h]
0x140023f01  test    al, al
0x140023f03  jnz     short loc_140023F10
0x140023f05  lea     rcx, [rbx+58h]
0x140023f09  call    XilCoreCommonBuffer_FreeUnusedResources
0x140023f0e  jmp     short loc_140023EDC
0x140023f10  mov     rax, cs:WdfFunctions_01033
0x140023f17  mov     rdx, [rbx+48h]
0x140023f1b  mov     rcx, cs:WdfDriverGlobals
0x140023f22  mov     rax, [rax+0BE0h]
0x140023f29  call    _guard_dispatch_icall
0x140023f2e  jmp     short loc_140023EDC
0x140023f30  call    cs:__imp_KeGetCurrentIrql
0x140023f37  nop     dword ptr [rax+rax+00h]
0x140023f3c  test    al, al
0x140023f3e  jz      short loc_140023EC5
0x140023f40  mov     r9d, 2BCh
0x140023f46  lea     r8, aOnecoreDrivers_13; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140023f4d  xor     edx, edx
0x140023f4f  lea     rcx, aCodePathRequir; "Code Path Requires Passive Level"
0x140023f56  call    Debug_FreAssertMsg
0x140023f5b  jmp     loc_140023EC5
```
