# Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800176e0`
- end: `0x1800176fd`
- name: `?GetRuntimeClassName@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180017710`
- `0x180017720`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800176f6`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Foundation.Collections.IObservableVector`1<Object>", 0x3Au, a2);
}

```

## disassembly

```asm
0x1800176e0  mov     qword ptr [rdx], 0
0x1800176e7  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IObserva"...
0x1800176ee  mov     r8, rdx
0x1800176f1  mov     edx, 3Ah ; ':'
0x1800176f6  jmp     cs:__imp_WindowsCreateString
```
