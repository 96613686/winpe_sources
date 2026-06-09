# Windows::Networking::UX::CEthernetAuthConfig::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180009050`
- end: `0x18000906d`
- name: `?GetRuntimeClassName@CEthernetAuthConfig@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CEthernetAuthConfig *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009066`

## string_xrefs

- `0x180009057`: `Windows.Networking.UX.EthernetAuthConfig`

## pseudocode

```c
HRESULT __fastcall Windows::Networking::UX::CEthernetAuthConfig::GetRuntimeClassName(
        Windows::Networking::UX::CEthernetAuthConfig *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Networking.UX.EthernetAuthConfig", 0x28u, a2);
}

```

## disassembly

```asm
0x180009050  mov     qword ptr [rdx], 0
0x180009057  lea     rcx, ?RuntimeClass_Windows_Networking_UX_EthernetAuthConfig@@3QBGB; "Windows.Networking.UX.EthernetAuthConfi"...
0x18000905e  mov     r8, rdx
0x180009061  mov     edx, 28h ; '('
0x180009066  jmp     cs:__imp_WindowsCreateString
```
