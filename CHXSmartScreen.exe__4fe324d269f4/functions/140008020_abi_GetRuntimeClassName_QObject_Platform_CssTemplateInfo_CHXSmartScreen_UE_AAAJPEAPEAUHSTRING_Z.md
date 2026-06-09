# ?__abi_GetRuntimeClassName@?QObject@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x140008020`
- end: `0x140008034`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@CssTemplateInfo@CHXSmartScreen@@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008040`
- `0x140008050`

## callees

- `0x140002850`

## string_xrefs

- `0x140008023`: `CHXSmartScreen.CssTemplateInfo`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform__CssTemplateInfo_CHXSmartScreen__UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(L"CHXSmartScreen.CssTemplateInfo", 0x1Eu, a2);
}

```

## disassembly

```asm
0x140008020  mov     r8, rdx; string
0x140008023  lea     rcx, sourceString; "CHXSmartScreen.CssTemplateInfo"
0x14000802a  mov     edx, 1Eh; length
0x14000802f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
