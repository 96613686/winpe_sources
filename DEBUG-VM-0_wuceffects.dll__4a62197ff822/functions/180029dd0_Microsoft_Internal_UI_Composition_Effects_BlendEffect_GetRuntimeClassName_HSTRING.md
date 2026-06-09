# Microsoft::Internal::UI::Composition::Effects::BlendEffect::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180029dd0`
- end: `0x180029ded`
- name: `?GetRuntimeClassName@BlendEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::BlendEffect *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029e00`
- `0x180029e10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029de6`

## string_xrefs

- `0x180029dd7`: `Microsoft.Internal.UI.Composition.Effects.BlendEffect`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::BlendEffect::GetRuntimeClassName(
        Microsoft::Internal::UI::Composition::Effects::BlendEffect *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Microsoft.Internal.UI.Composition.Effects.BlendEffect", 0x35u, a2);
}

```

## disassembly

```asm
0x180029dd0  mov     qword ptr [rdx], 0
0x180029dd7  lea     rcx, ?RuntimeClass_Microsoft_Internal_UI_Composition_Effects_BlendEffect@@3QBGB; "Microsoft.Internal.UI.Composition.Effec"...
0x180029dde  mov     r8, rdx
0x180029de1  mov     edx, 35h ; '5'
0x180029de6  jmp     cs:__imp_WindowsCreateString
```
