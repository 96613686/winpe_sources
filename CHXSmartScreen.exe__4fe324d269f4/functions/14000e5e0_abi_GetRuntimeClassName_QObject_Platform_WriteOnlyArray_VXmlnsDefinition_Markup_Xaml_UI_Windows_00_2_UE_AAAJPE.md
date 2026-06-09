# ?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x14000e5e0`
- end: `0x14000e5f4`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e600`
- `0x14000e610`
- `0x14000e620`

## callees

- `0x140002850`

## string_xrefs

- `0x14000e5e3`: `Platform.?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform____WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Platform.?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00",
           0x46u,
           a2);
}

```

## disassembly

```asm
0x14000e5e0  mov     r8, rdx; string
0x14000e5e3  lea     rcx, aPlatformWriteo; "Platform.?$WriteOnlyArray@VXmlnsDefinit"...
0x14000e5ea  mov     edx, 46h ; 'F'; length
0x14000e5ef  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
