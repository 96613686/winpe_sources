# AgentAccountHelpers2::RemoveSessionConfigId(wchar_t const *)

- ea: `0x18005ac18`
- end: `0x18005aca3`
- name: `?RemoveSessionConfigId@AgentAccountHelpers2@@SAXPEB_W@Z`
- size: `139`
- prototype: `void __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18005efe0`
- `0x18005f33c`

## callees

- `0x180011e18`
- `0x18005ac18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005ac86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005ac86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ac4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ac97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ac97`

## string_xrefs

- `0x18005ac6b`: `Failed to open registry key to remove config ID, hr: 0x%X`
- `0x18005ac3d`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AgentAccountHelpers2::RemoveSessionConfigId(LPCWSTR lpValueName)
{
  int v2; // eax
  bool v3; // sf
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds",
         0,
         0xF003Fu,
         &hKey);
  v3 = v2 < 0;
  if ( v2 > 0 )
  {
    v2 = (unsigned __int16)v2 | 0x80070000;
    v3 = v2 < 0;
  }
  if ( v3 )
  {
    if ( v2 != -2147024894 )
      Log(3u, L"Failed to open registry key to remove config ID, hr: 0x%X", (unsigned int)v2);
  }
  else
  {
    RegDeleteValueW(hKey, lpValueName);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18005ac18  push    rbx
0x18005ac1a  sub     rsp, 30h
0x18005ac1e  mov     rbx, rcx
0x18005ac21  mov     [rsp+38h+hKey], 0
0x18005ac2a  lea     rax, [rsp+38h+hKey]
0x18005ac2f  mov     [rsp+38h+phkResult], rax; phkResult
0x18005ac34  mov     r9d, 0F003Fh; samDesired
0x18005ac3a  xor     r8d, r8d; ulOptions
0x18005ac3d  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers2@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18005ac44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ac4b  call    cs:__imp_RegOpenKeyExW
0x18005ac51  test    eax, eax
0x18005ac53  jle     short loc_18005AC5F
0x18005ac55  movzx   eax, ax
0x18005ac58  or      eax, 80070000h
0x18005ac5d  test    eax, eax
0x18005ac5f  jns     short loc_18005AC7E
0x18005ac61  cmp     eax, 80070002h
0x18005ac66  jz      short loc_18005AC8D
0x18005ac68  mov     r8d, eax
0x18005ac6b  lea     rdx, aFailedToOpenRe_0; "Failed to open registry key to remove c"...
0x18005ac72  mov     ecx, 3; unsigned __int8
0x18005ac77  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005ac7c  jmp     short loc_18005AC8D
0x18005ac7e  mov     rdx, rbx; lpValueName
0x18005ac81  mov     rcx, [rsp+38h+hKey]; hKey
0x18005ac86  call    cs:__imp_RegDeleteValueW
0x18005ac8c  nop
0x18005ac8d  mov     rcx, [rsp+38h+hKey]; hKey
0x18005ac92  test    rcx, rcx
0x18005ac95  jz      short loc_18005AC9D
0x18005ac97  call    cs:__imp_RegCloseKey
0x18005ac9d  add     rsp, 30h
0x18005aca1  pop     rbx
0x18005aca2  retn
```
