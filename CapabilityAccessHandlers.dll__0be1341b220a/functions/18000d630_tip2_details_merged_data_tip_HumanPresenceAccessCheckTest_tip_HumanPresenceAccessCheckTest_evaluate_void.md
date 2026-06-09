# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::evaluate(void)

- ea: `0x18000d630`
- end: `0x18000d63c`
- name: `?evaluate@?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@EEAAXXZ`
- size: `12`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000d8b0`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::evaluate(
        __int64 a1)
{
  _tip_HumanPresenceAccessCheckTest::evaluate((_tip_HumanPresenceAccessCheckTest *)(a1 + 256));
}

```

## disassembly

```asm
0x18000d630  add     rcx, 100h; this
0x18000d637  jmp     ?evaluate@_tip_HumanPresenceAccessCheckTest@@QEAAXXZ; _tip_HumanPresenceAccessCheckTest::evaluate(void)
```
