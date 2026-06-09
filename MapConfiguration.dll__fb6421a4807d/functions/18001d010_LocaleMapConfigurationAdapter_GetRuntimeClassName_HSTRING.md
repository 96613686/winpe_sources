# LocaleMapConfigurationAdapter::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001d010`
- end: `0x18001d02d`
- name: `?GetRuntimeClassName@LocaleMapConfigurationAdapter@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(LocaleMapConfigurationAdapter *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001d026`

## string_xrefs

- `0x18001d017`: `LocaleMapConfigurationAdapter`

## pseudocode

```c
HRESULT __fastcall LocaleMapConfigurationAdapter::GetRuntimeClassName(LocaleMapConfigurationAdapter *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"LocaleMapConfigurationAdapter", 0x1Du, a2);
}

```

## disassembly

```asm
0x18001d010  mov     qword ptr [rdx], 0
0x18001d017  lea     rcx, aLocalemapconfi; "LocaleMapConfigurationAdapter"
0x18001d01e  mov     r8, rdx
0x18001d021  mov     edx, 1Dh
0x18001d026  jmp     cs:__imp_WindowsCreateString
```
