# Windows::UI::Input::Preview::Injection::InputInjector::GetTrustLevel(TrustLevel *)

- ea: `0x180006860`
- end: `0x180006869`
- name: `?GetTrustLevel@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAJPEAW4TrustLevel@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this, enum TrustLevel *)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008670`
- `0x180008680`
- `0x18000aab0`
- `0x18000aac0`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::GetTrustLevel(
        Windows::UI::Input::Preview::Injection::InputInjector *this,
        enum TrustLevel *a2)
{
  *a2 = PartialTrust;
  return 0;
}

```

## disassembly

```asm
0x180006860  mov     dword ptr [rdx], 1
0x180006866  xor     eax, eax
0x180006868  retn
```
