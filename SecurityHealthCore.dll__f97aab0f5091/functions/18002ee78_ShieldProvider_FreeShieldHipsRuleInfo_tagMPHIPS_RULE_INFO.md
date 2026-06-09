# ShieldProvider::FreeShieldHipsRuleInfo(tagMPHIPS_RULE_INFO *)

- ea: `0x18002ee78`
- end: `0x18002eea8`
- name: `?FreeShieldHipsRuleInfo@ShieldProvider@@YAXPEAUtagMPHIPS_RULE_INFO@@@Z`
- size: `48`
- prototype: `void __fastcall(ShieldProvider *__hidden this, struct tagMPHIPS_RULE_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002ee18`
- `0x180034df0`

## callees

- `0x18002ee78`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ee89`
- `ole32!CoTaskMemFree` at `0x18002ee93`
- `ole32!CoTaskMemFree` at `0x18002ee9c`
- `ole32!CoTaskMemFree` at `0x18002ee89`
- `ole32!CoTaskMemFree` at `0x18002ee93`
- `ole32!CoTaskMemFree` at `0x18002ee9c`

## pseudocode

```c
void __fastcall ShieldProvider::FreeShieldHipsRuleInfo(LPVOID *this, struct tagMPHIPS_RULE_INFO *a2)
{
  if ( this )
  {
    CoTaskMemFree(this[2]);
    CoTaskMemFree(this[3]);
    CoTaskMemFree(this);
  }
}

```

## disassembly

```asm
0x18002ee78  test    rcx, rcx
0x18002ee7b  jz      short locret_18002EEA7
0x18002ee7d  push    rbx
0x18002ee7e  sub     rsp, 20h
0x18002ee82  mov     rbx, rcx
0x18002ee85  mov     rcx, [rcx+10h]; pv
0x18002ee89  call    cs:__imp_CoTaskMemFree
0x18002ee8f  mov     rcx, [rbx+18h]; pv
0x18002ee93  call    cs:__imp_CoTaskMemFree
0x18002ee99  mov     rcx, rbx; pv
0x18002ee9c  call    cs:__imp_CoTaskMemFree
0x18002eea2  add     rsp, 20h
0x18002eea6  pop     rbx
0x18002eea7  retn
```
