# Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180031da0`
- end: `0x180031dbd`
- name: `?GetRuntimeClassName@?$SimpleVectorView@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@V?$Vector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180031dd0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180031db6`

## string_xrefs

- `0x180031da7`: `Windows.Foundation.Collections.IVectorView`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>",
           0x69u,
           a2);
}

```

## disassembly

```asm
0x180031da0  mov     qword ptr [rdx], 0
0x180031da7  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x180031dae  mov     r8, rdx
0x180031db1  mov     edx, 69h ; 'i'
0x180031db6  jmp     cs:__imp_WindowsCreateString
```
