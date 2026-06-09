# Windows::Networking::UX::CStaticIpConfig::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180009080`
- end: `0x18000909d`
- name: `?GetRuntimeClassName@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CStaticIpConfig *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009096`

## string_xrefs

- `0x180009087`: `Windows.Networking.UX.StaticIpConfig`

## pseudocode

```c
HRESULT __fastcall Windows::Networking::UX::CStaticIpConfig::GetRuntimeClassName(
        Windows::Networking::UX::CStaticIpConfig *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Networking.UX.StaticIpConfig", 0x24u, a2);
}

```

## disassembly

```asm
0x180009080  mov     qword ptr [rdx], 0
0x180009087  lea     rcx, ?RuntimeClass_Windows_Networking_UX_StaticIpConfig@@3QBGB; "Windows.Networking.UX.StaticIpConfig"
0x18000908e  mov     r8, rdx
0x180009091  mov     edx, 24h ; '$'
0x180009096  jmp     cs:__imp_WindowsCreateString
```
