# ?__abi_GetRuntimeClassName@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z

- ea: `0x14000e540`
- end: `0x14000e554`
- name: `?__abi_GetRuntimeClassName@?QObject@Platform@@?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@2@UE$AAAJPEAPEAUHSTRING__@@@Z`
- size: `20`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e560`
- `0x14000e570`
- `0x14000e580`
- `0x14000e590`
- `0x14000e5a0`
- `0x14000e5b0`
- `0x14000e5c0`
- `0x14000e5d0`

## callees

- `0x140002850`

## string_xrefs

- `0x14000e543`: `Windows.Foundation.IReferenceArray`1<Windows.UI.Xaml.Markup.XmlnsDefinition>`

## pseudocode

```c
HRESULT __fastcall ___abi_GetRuntimeClassName__QObject_Platform____Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_2_UE_AAAJPEAPEAUHSTRING_____Z(
        __int64 a1,
        HSTRING *a2)
{
  return __winRT::__windowsCreateString(
           L"Windows.Foundation.IReferenceArray`1<Windows.UI.Xaml.Markup.XmlnsDefinition>",
           0x4Cu,
           a2);
}

```

## disassembly

```asm
0x14000e540  mov     r8, rdx; string
0x14000e543  lea     rcx, aWindowsFoundat_14; "Windows.Foundation.IReferenceArray`1<Wi"...
0x14000e54a  mov     edx, 4Ch ; 'L'; length
0x14000e54f  jmp     ?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z; __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)
```
