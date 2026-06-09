# ShieldProvider::FreeShieldAsrHistoryBlockedAction(tagMP_ASR_HISTORY_BLOCKED_ACTION *)

- ea: `0x18002ede0`
- end: `0x18002ee0f`
- name: `?FreeShieldAsrHistoryBlockedAction@ShieldProvider@@YAXPEAUtagMP_ASR_HISTORY_BLOCKED_ACTION@@@Z`
- size: `47`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMP_ASR_HISTORY_BLOCKED_ACTION *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ee18`
- `0x18002f1a4`
- `0x180034a4c`

## callees

- `0x18002ede0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002edf0`
- `ole32!CoTaskMemFree` at `0x18002edfa`
- `ole32!CoTaskMemFree` at `0x18002ee03`
- `ole32!CoTaskMemFree` at `0x18002edf0`
- `ole32!CoTaskMemFree` at `0x18002edfa`
- `ole32!CoTaskMemFree` at `0x18002ee03`

## pseudocode

```c
void __fastcall ShieldProvider::FreeShieldAsrHistoryBlockedAction(
        LPVOID *this,
        struct tagMP_ASR_HISTORY_BLOCKED_ACTION *a2)
{
  if ( this )
  {
    CoTaskMemFree(*this);
    CoTaskMemFree(this[3]);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x18002ede0  test    rcx, rcx
0x18002ede3  jz      short locret_18002EE0E
0x18002ede5  push    rbx
0x18002ede6  sub     rsp, 20h
0x18002edea  mov     rbx, rcx
0x18002eded  mov     rcx, [rcx]; pv
0x18002edf0  call    cs:__imp_CoTaskMemFree
0x18002edf6  mov     rcx, [rbx+18h]; pv
0x18002edfa  call    cs:__imp_CoTaskMemFree
0x18002ee00  mov     rcx, rbx; pv
0x18002ee03  call    cs:__imp_CoTaskMemFree
0x18002ee09  add     rsp, 20h
0x18002ee0d  pop     rbx
0x18002ee0e  retn
```
