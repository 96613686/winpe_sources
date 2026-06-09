# Windows::Internal::Security::Authentication::TokenBroker::IsDefaultBridgeEnabled(void)

- ea: `0x18001f560`
- end: `0x18001f5bd`
- name: `?IsDefaultBridgeEnabled@TokenBroker@Authentication@Security@Internal@Windows@@YA_NXZ`
- size: `93`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f5aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001f5aa`

## string_xrefs

- `0x18001f58e`: `Software\Microsoft\Windows NT\CurrentVersion\TokenBroker\WAB2WAMBridge`

## pseudocode

```c
bool __fastcall Windows::Internal::Security::Authentication::TokenBroker::IsDefaultBridgeEnabled()
{
  unsigned int dwValue; // [rsp+50h] [rbp+8h] BYREF
  unsigned int size; // [rsp+58h] [rbp+10h] BYREF

  dwValue = 0;
  size = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\TokenBroker\\WAB2WAMBridge",
    L"DefaultBridgeEnabled",
    0x10010u,
    0,
    &dwValue,
    &size);
  return dwValue != 0;
}

```

## disassembly

```asm
0x18001f560  mov     r11, rsp
0x18001f563  sub     rsp, 48h
0x18001f567  lea     rax, [r11+10h]
0x18001f56b  mov     [rsp+48h+dwValue], 0
0x18001f573  mov     [r11-18h], rax
0x18001f577  lea     r8, aDefaultbridgee; "DefaultBridgeEnabled"
0x18001f57e  lea     rax, [r11+8]
0x18001f582  mov     [rsp+48h+size], 4
0x18001f58a  mov     [r11-20h], rax
0x18001f58e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f595  mov     r9d, 10010h; dwFlags
0x18001f59b  mov     qword ptr [r11-28h], 0
0x18001f5a3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001f5aa  call    cs:__imp_RegGetValueW
0x18001f5b0  cmp     [rsp+48h+dwValue], 0
0x18001f5b5  setnz   al
0x18001f5b8  add     rsp, 48h
0x18001f5bc  retn
```
