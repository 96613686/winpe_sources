# Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180029e20`
- end: `0x180029e3d`
- name: `?GetRuntimeClassName@ColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029e50`
- `0x180029e60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029e36`

## string_xrefs

- `0x180029e27`: `Microsoft.Internal.UI.Composition.Effects.ColorSourceEffect`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect::GetRuntimeClassName(
        Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Microsoft.Internal.UI.Composition.Effects.ColorSourceEffect", 0x3Bu, a2);
}

```

## disassembly

```asm
0x180029e20  mov     qword ptr [rdx], 0
0x180029e27  lea     rcx, ?RuntimeClass_Microsoft_Internal_UI_Composition_Effects_ColorSourceEffect@@3QBGB; "Microsoft.Internal.UI.Composition.Effec"...
0x180029e2e  mov     r8, rdx
0x180029e31  mov     edx, 3Bh ; ';'
0x180029e36  jmp     cs:__imp_WindowsCreateString
```
