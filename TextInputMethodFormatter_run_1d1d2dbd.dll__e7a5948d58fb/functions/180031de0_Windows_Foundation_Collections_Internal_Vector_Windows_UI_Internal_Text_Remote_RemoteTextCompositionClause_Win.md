# Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180031de0`
- end: `0x180031dfd`
- name: `?GetRuntimeClassName@?$Vector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180031e10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180031df6`

## string_xrefs

- `0x180031de7`: `Windows.Foundation.Collections.IVector`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IVector`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>",
           0x65u,
           a2);
}

```

## disassembly

```asm
0x180031de0  mov     qword ptr [rdx], 0
0x180031de7  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVector`"...
0x180031dee  mov     r8, rdx
0x180031df1  mov     edx, 65h ; 'e'
0x180031df6  jmp     cs:__imp_WindowsCreateString
```
