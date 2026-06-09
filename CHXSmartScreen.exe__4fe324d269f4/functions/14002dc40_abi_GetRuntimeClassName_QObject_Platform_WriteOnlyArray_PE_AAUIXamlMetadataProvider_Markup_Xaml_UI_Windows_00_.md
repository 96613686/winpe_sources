# ?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x14002dc40`
- end: `0x14002dc54`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14002dc60`
- `0x14002dc70`
- `0x14002dc80`

## callees

- `0x140002850`

## string_xrefs

- `0x14002dc43`: `Platform.?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform____WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_2_UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Platform.?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00",
           0x51u,
           a2);
}

```

## disassembly

```asm
0x14002dc40  mov     r8, rdx; string
0x14002dc43  lea     rcx, aPlatformWriteo_1; "Platform.?$WriteOnlyArray@PE$AAUIXamlMe"...
0x14002dc4a  mov     edx, 51h ; 'Q'; length
0x14002dc4f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
