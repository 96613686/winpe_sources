# CEventThrottle::Save(wchar_t const *)

- ea: `0x14002a538`
- end: `0x14002a631`
- name: `?Save@CEventThrottle@@QEAA_NPEB_W@Z`
- size: `249`
- prototype: `bool __fastcall(BYTE *lpData, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a638`

## callees

- `0x1400030a0`
- `0x14000a684`
- `0x14002a538`
- `0x14002aac4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002a5f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002a5f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a604`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002a5cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002a5cc`

## pseudocode

```c
bool __fastcall CEventThrottle::Save(BYTE *lpData, const wchar_t *a2)
{
  bool v3; // bl
  const wchar_t *v4; // rcx
  bool v5; // al
  wchar_t *v6; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-268h]
  HKEY hKey; // [rsp+30h] [rbp-258h] BYREF
  WCHAR ValueName[20]; // [rsp+38h] [rbp-250h] BYREF
  wchar_t v11[264]; // [rsp+60h] [rbp-228h] BYREF

  v3 = 0;
  if ( StringCchPrintfW(ValueName, 0x10u, L"%08x", *((unsigned int *)lpData + 5)) >= 0 )
  {
    hKey = 0;
    v5 = MapRegistryKeyPath(
           v4,
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows Search\\Tracing\\EventThrottleState",
           v11,
           phkResult);
    v6 = v11;
    if ( !v5 )
      v6 = (wchar_t *)L"Software\\Microsoft\\Windows Search\\Tracing\\EventThrottleState";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 2u, &hKey) )
    {
      v3 = RegSetValueExW(hKey, ValueName, 0, 3u, lpData, 0x14u) == 0;
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14002a538  mov     [rsp+arg_8], rbx
0x14002a53d  mov     [rsp+arg_10], rsi
0x14002a542  push    rdi
0x14002a543  sub     rsp, 280h
0x14002a54a  mov     rax, cs:__security_cookie
0x14002a551  xor     rax, rsp
0x14002a554  mov     [rsp+288h+var_18], rax
0x14002a55c  mov     r9d, [rcx+14h]
0x14002a560  lea     r8, a08x; "%08x"
0x14002a567  mov     rdi, rcx
0x14002a56a  mov     edx, 10h; unsigned __int64
0x14002a56f  lea     rcx, [rsp+288h+ValueName]; unsigned __int16 *
0x14002a574  xor     bl, bl
0x14002a576  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002a57b  test    eax, eax
0x14002a57d  js      loc_14002A60A
0x14002a583  lea     rsi, aSoftwareMicros_0; "Software\\Microsoft\\Windows Search\\Tr"...
0x14002a58a  mov     [rsp+288h+hKey], 0
0x14002a593  mov     r8, rsi; wchar_t *
0x14002a596  lea     r9, [rsp+288h+var_228]; wchar_t *
0x14002a59b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14002a5a2  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x14002a5a7  test    al, al
0x14002a5a9  lea     rdx, [rsp+288h+var_228]
0x14002a5ae  lea     rax, [rsp+288h+hKey]
0x14002a5b3  mov     r9d, 2; samDesired
0x14002a5b9  cmovz   rdx, rsi; lpSubKey
0x14002a5bd  mov     [rsp+288h+phkResult], rax; phkResult
0x14002a5c2  xor     r8d, r8d; ulOptions
0x14002a5c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002a5cc  call    cs:__imp_RegOpenKeyExW
0x14002a5d2  test    eax, eax
0x14002a5d4  jnz     short loc_14002A60A
0x14002a5d6  mov     rcx, [rsp+288h+hKey]; hKey
0x14002a5db  lea     r9d, [rax+3]; dwType
0x14002a5df  mov     [rsp+288h+cbData], 14h; cbData
0x14002a5e7  lea     rdx, [rsp+288h+ValueName]; lpValueName
0x14002a5ec  xor     r8d, r8d; Reserved
0x14002a5ef  mov     [rsp+288h+phkResult], rdi; lpData
0x14002a5f4  call    cs:__imp_RegSetValueExW
0x14002a5fa  mov     rcx, [rsp+288h+hKey]; hKey
0x14002a5ff  test    eax, eax
0x14002a601  setz    bl
0x14002a604  call    cs:__imp_RegCloseKey
0x14002a60a  mov     al, bl
0x14002a60c  mov     rcx, [rsp+288h+var_18]
0x14002a614  xor     rcx, rsp; StackCookie
0x14002a617  call    __security_check_cookie
0x14002a61c  lea     r11, [rsp+288h+var_8]
0x14002a624  mov     rbx, [r11+18h]
0x14002a628  mov     rsi, [r11+20h]
0x14002a62c  mov     rsp, r11
0x14002a62f  pop     rdi
0x14002a630  retn
```
