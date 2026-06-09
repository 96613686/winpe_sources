# Windows::UI::Composition::CSingleInputCompositeEffect::get_Name(HSTRING__ * *)

- ea: `0x18001b6d0`
- end: `0x18001b6e3`
- name: `?get_Name@CSingleInputCompositeEffect@Composition@UI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `19`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CSingleInputCompositeEffect *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001b6dc`

## pseudocode

```c
HRESULT __fastcall Windows::UI::Composition::CSingleInputCompositeEffect::get_Name(
        Windows::UI::Composition::CSingleInputCompositeEffect *this,
        HSTRING *a2)
{
  return WindowsCreateString(&S1, 0, a2);
}

```

## disassembly

```asm
0x18001b6d0  mov     r8, rdx
0x18001b6d3  lea     rcx, S1
0x18001b6da  xor     edx, edx
0x18001b6dc  jmp     cs:__imp_WindowsCreateString
```
