# Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180031d70`
- end: `0x180031d8d`
- name: `?GetRuntimeClassName@?$SimpleVectorIterator@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@V?$Vector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180031d86`

## string_xrefs

- `0x180031d77`: `Windows.Foundation.Collections.IIterator`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IIterator`1<Windows.UI.Internal.Text.Remote.RemoteTextCompositionClause>",
           0x67u,
           a2);
}

```

## disassembly

```asm
0x180031d70  mov     qword ptr [rdx], 0
0x180031d77  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.Collections.IIterato"...
0x180031d7e  mov     r8, rdx
0x180031d81  mov     edx, 67h ; 'g'
0x180031d86  jmp     cs:__imp_WindowsCreateString
```
