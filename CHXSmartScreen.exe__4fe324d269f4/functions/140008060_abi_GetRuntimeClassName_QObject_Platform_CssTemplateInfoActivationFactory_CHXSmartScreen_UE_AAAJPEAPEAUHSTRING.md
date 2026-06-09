# ?__abi_GetRuntimeClassName@?QObject@Platform@@__CssTemplateInfoActivationFactory@CHXSmartScreen@@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x140008060`
- end: `0x140008074`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@__CssTemplateInfoActivationFactory@CHXSmartScreen@@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008080`

## callees

- `0x140002850`

## string_xrefs

- `0x140008063`: `CHXSmartScreen.__CssTemplateInfoActivationFactory`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform____CssTemplateInfoActivationFactory_CHXSmartScreen__UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(L"CHXSmartScreen.__CssTemplateInfoActivationFactory", 0x31u, a2);
}

```

## disassembly

```asm
0x140008060  mov     r8, rdx; string
0x140008063  lea     rcx, aChxsmartscreen_0; "CHXSmartScreen.__CssTemplateInfoActivat"...
0x14000806a  mov     edx, 31h ; '1'; length
0x14000806f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
