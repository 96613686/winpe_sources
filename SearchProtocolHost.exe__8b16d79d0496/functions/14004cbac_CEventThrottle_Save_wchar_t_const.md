# CEventThrottle::Save(wchar_t const *)

- ea: `0x14004cbac`
- end: `0x14004cca5`
- name: `?Save@CEventThrottle@@QEAA_NPEB_W@Z`
- size: `249`
- prototype: `bool __fastcall(BYTE *lpData, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004ccac`

## callees

- `0x140005240`
- `0x140029a8c`
- `0x14004cbac`
- `0x14004ee84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004cc40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004cc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004cc68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004cc68`

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
0x14004cbac  mov     [rsp+arg_8], rbx
0x14004cbb1  mov     [rsp+arg_10], rsi
0x14004cbb6  push    rdi
0x14004cbb7  sub     rsp, 280h
0x14004cbbe  mov     rax, cs:__security_cookie
0x14004cbc5  xor     rax, rsp
0x14004cbc8  mov     [rsp+288h+var_18], rax
0x14004cbd0  mov     r9d, [rcx+14h]
0x14004cbd4  lea     r8, a08x; "%08x"
0x14004cbdb  mov     rdi, rcx
0x14004cbde  mov     edx, 10h; unsigned __int64
0x14004cbe3  lea     rcx, [rsp+288h+ValueName]; unsigned __int16 *
0x14004cbe8  xor     bl, bl
0x14004cbea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004cbef  test    eax, eax
0x14004cbf1  js      loc_14004CC7E
0x14004cbf7  lea     rsi, aSoftwareMicros_0; "Software\\Microsoft\\Windows Search\\Tr"...
0x14004cbfe  mov     [rsp+288h+hKey], 0
0x14004cc07  mov     r8, rsi; wchar_t *
0x14004cc0a  lea     r9, [rsp+288h+var_228]; wchar_t *
0x14004cc0f  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14004cc16  call    ?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z; MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)
0x14004cc1b  test    al, al
0x14004cc1d  lea     rdx, [rsp+288h+var_228]
0x14004cc22  lea     rax, [rsp+288h+hKey]
0x14004cc27  mov     r9d, 2; samDesired
0x14004cc2d  cmovz   rdx, rsi; lpSubKey
0x14004cc31  mov     [rsp+288h+phkResult], rax; phkResult
0x14004cc36  xor     r8d, r8d; ulOptions
0x14004cc39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004cc40  call    cs:__imp_RegOpenKeyExW
0x14004cc46  test    eax, eax
0x14004cc48  jnz     short loc_14004CC7E
0x14004cc4a  mov     rcx, [rsp+288h+hKey]; hKey
0x14004cc4f  lea     r9d, [rax+3]; dwType
0x14004cc53  mov     [rsp+288h+cbData], 14h; cbData
0x14004cc5b  lea     rdx, [rsp+288h+ValueName]; lpValueName
0x14004cc60  xor     r8d, r8d; Reserved
0x14004cc63  mov     [rsp+288h+phkResult], rdi; lpData
0x14004cc68  call    cs:__imp_RegSetValueExW
0x14004cc6e  mov     rcx, [rsp+288h+hKey]; hKey
0x14004cc73  test    eax, eax
0x14004cc75  setz    bl
0x14004cc78  call    cs:__imp_RegCloseKey
0x14004cc7e  mov     al, bl
0x14004cc80  mov     rcx, [rsp+288h+var_18]
0x14004cc88  xor     rcx, rsp; StackCookie
0x14004cc8b  call    __security_check_cookie
0x14004cc90  lea     r11, [rsp+288h+var_8]
0x14004cc98  mov     rbx, [r11+18h]
0x14004cc9c  mov     rsi, [r11+20h]
0x14004cca0  mov     rsp, r11
0x14004cca3  pop     rdi
0x14004cca4  retn
```
