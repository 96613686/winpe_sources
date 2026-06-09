# ConfigurationManagerAdapter::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000bec0`
- end: `0x18000bedd`
- name: `?GetRuntimeClassName@ConfigurationManagerAdapter@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(ConfigurationManagerAdapter *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000bed6`

## string_xrefs

- `0x18000bec7`: `ConfigurationManagerAdapter`

## pseudocode

```c
HRESULT __fastcall ConfigurationManagerAdapter::GetRuntimeClassName(ConfigurationManagerAdapter *this, HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"ConfigurationManagerAdapter", 0x1Bu, a2);
}

```

## disassembly

```asm
0x18000bec0  mov     qword ptr [rdx], 0
0x18000bec7  lea     rcx, aConfigurationm_4; "ConfigurationManagerAdapter"
0x18000bece  mov     r8, rdx
0x18000bed1  mov     edx, 1Bh
0x18000bed6  jmp     cs:__imp_WindowsCreateString
```
