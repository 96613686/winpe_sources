# Windows::Services::Cortana::CortanaSettings::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180011000`
- end: `0x18001101d`
- name: `?GetRuntimeClassName@CortanaSettings@Cortana@Services@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Services::Cortana::CortanaSettings *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011016`

## string_xrefs

- `0x180011007`: `Windows.Services.Cortana.CortanaSettings`

## pseudocode

```c
HRESULT __fastcall Windows::Services::Cortana::CortanaSettings::GetRuntimeClassName(
        Windows::Services::Cortana::CortanaSettings *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Services.Cortana.CortanaSettings", 0x28u, a2);
}

```

## disassembly

```asm
0x180011000  mov     qword ptr [rdx], 0
0x180011007  lea     rcx, ?RuntimeClass_Windows_Services_Cortana_CortanaSettings@@3QBGB; "Windows.Services.Cortana.CortanaSetting"...
0x18001100e  mov     r8, rdx
0x180011011  mov     edx, 28h ; '('
0x180011016  jmp     cs:__imp_WindowsCreateString
```
