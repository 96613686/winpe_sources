# lrGetSetMaxEndPoints

- ea: `0x180098bb0`
- end: `0x180098c5b`
- name: `lrGetSetMaxEndPoints`
- size: `171`
- prototype: `__int64 __fastcall(BYTE *lpData, BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b6a0`

## callees

- `0x180098bb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098be9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180098be9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098c48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098c48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098c13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098c3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098c13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098c3d`

## string_xrefs

- `0x180098c04`: `LimitSimultaneousIncomingCalls`
- `0x180098bce`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
__int64 __fastcall lrGetSetMaxEndPoints(BYTE *lpData, BYTE *a2)
{
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Rasman\\Parameters",
          0,
          0x20007u,
          &hKey) )
  {
    if ( !RegSetValueExW(hKey, L"LimitSimultaneousIncomingCalls", 0, 4u, a2, 4u) )
      RegSetValueExW(hKey, L"LimitSimultaneousOutgoingCalls", 0, 4u, lpData, 4u);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180098bb0  mov     r11, rsp
0x180098bb3  mov     [r11+8], rbx
0x180098bb7  push    rdi
0x180098bb8  sub     rsp, 30h
0x180098bbc  mov     rdi, rdx
0x180098bbf  mov     qword ptr [r11+20h], 0
0x180098bc7  mov     rbx, rcx
0x180098bca  lea     rax, [r11+20h]
0x180098bce  lea     rdx, aSystemCurrentc_31; "System\\CurrentControlSet\\Services\\Ra"...
0x180098bd5  mov     [r11-18h], rax
0x180098bd9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180098be0  mov     r9d, 20007h; samDesired
0x180098be6  xor     r8d, r8d; ulOptions
0x180098be9  call    cs:__imp_RegOpenKeyExW
0x180098bef  test    eax, eax
0x180098bf1  jnz     short loc_180098C4E
0x180098bf3  mov     rcx, [rsp+38h+hKey]; hKey
0x180098bf8  lea     r9d, [rax+4]; dwType
0x180098bfc  mov     [rsp+38h+cbData], 4; cbData
0x180098c04  lea     rdx, aLimitsimultane; "LimitSimultaneousIncomingCalls"
0x180098c0b  xor     r8d, r8d; Reserved
0x180098c0e  mov     [rsp+38h+lpData], rdi; lpData
0x180098c13  call    cs:__imp_RegSetValueExW
0x180098c19  test    eax, eax
0x180098c1b  jnz     short loc_180098C43
0x180098c1d  mov     rcx, [rsp+38h+hKey]; hKey
0x180098c22  lea     r9d, [rax+4]; dwType
0x180098c26  mov     [rsp+38h+cbData], 4; cbData
0x180098c2e  lea     rdx, aLimitsimultane_0; "LimitSimultaneousOutgoingCalls"
0x180098c35  xor     r8d, r8d; Reserved
0x180098c38  mov     [rsp+38h+lpData], rbx; lpData
0x180098c3d  call    cs:__imp_RegSetValueExW
0x180098c43  mov     rcx, [rsp+38h+hKey]; hKey
0x180098c48  call    cs:__imp_RegCloseKey
0x180098c4e  mov     rbx, [rsp+38h+arg_0]
0x180098c53  xor     eax, eax
0x180098c55  add     rsp, 30h
0x180098c59  pop     rdi
0x180098c5a  retn
```
