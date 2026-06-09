# CWinApp::GetAppRegistryKey(void)

- ea: `0x1800214f0`
- end: `0x18002160e`
- name: `?GetAppRegistryKey@CWinApp@@QEAAPEAUHKEY__@@XZ`
- size: `286`
- prototype: `HKEY __fastcall(CWinApp *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180021160`
- `0x180021460`

## callees

- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215b2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800215f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021603`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021603`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021538`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021538`

## pseudocode

```c
HKEY __fastcall CWinApp::GetAppRegistryKey(CWinApp *this)
{
  const WCHAR *v3; // rdx
  HKEY v4; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  HKEY v7; // [rsp+88h] [rbp+28h] BYREF

  v4 = 0;
  hKey = 0;
  v7 = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"software", 0, 0x2001Fu, &hKey) )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 30);
    dwDisposition = 0;
    if ( !RegCreateKeyExW(hKey, v3, 0, 0, 0, 0x2001Fu, 0, &v7, &dwDisposition) )
      RegCreateKeyExW(v7, *((LPCWSTR *)this + 35), 0, 0, 0, 0x2001Fu, 0, &v4, &dwDisposition);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    RegCloseKey(v7);
  return v4;
}

```

## disassembly

```asm
0x1800214f0  mov     [rsp-8+arg_0], rbx
0x1800214f5  push    rbp
0x1800214f6  mov     rbp, rsp
0x1800214f9  sub     rsp, 60h
0x1800214fd  mov     rbx, rcx
0x180021500  mov     [rbp+var_10], 0
0x180021508  lea     rax, [rbp+hKey]
0x18002150c  mov     [rbp+hKey], 0
0x180021514  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002151b  mov     [rsp+60h+phkResult], rax; phkResult
0x180021520  mov     r9d, 2001Fh; samDesired
0x180021526  mov     [rbp+arg_18], 0
0x18002152e  xor     r8d, r8d; ulOptions
0x180021531  lea     rdx, SubKey; "software"
0x180021538  call    cs:__imp_RegOpenKeyExW
0x18002153e  test    eax, eax
0x180021540  jz      short loc_18002156F
0x180021542  mov     rcx, [rbp+hKey]; hKey
0x180021546  test    rcx, rcx
0x180021549  jnz     short loc_180021567
0x18002154b  mov     rcx, [rbp+arg_18]; hKey
0x18002154f  test    rcx, rcx
0x180021552  jnz     loc_180021603
0x180021558  mov     rax, [rbp+var_10]
0x18002155c  mov     rbx, [rsp+60h+arg_0]
0x180021561  add     rsp, 60h
0x180021565  pop     rbp
0x180021566  retn
0x180021567  call    cs:__imp_RegCloseKey
0x18002156d  jmp     short loc_18002154B
0x18002156f  mov     rdx, [rbx+0F0h]; lpSubKey
0x180021576  lea     rax, [rbp+dwDisposition]
0x18002157a  mov     rcx, [rbp+hKey]; hKey
0x18002157e  xor     r9d, r9d; lpClass
0x180021581  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180021586  xor     r8d, r8d; Reserved
0x180021589  lea     rax, [rbp+arg_18]
0x18002158d  mov     [rbp+dwDisposition], 0
0x180021594  mov     [rsp+60h+var_28], rax; phkResult
0x180021599  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800215a2  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800215aa  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800215b2  call    cs:__imp_RegCreateKeyExW
0x1800215b8  test    eax, eax
0x1800215ba  jnz     short loc_180021542
0x1800215bc  mov     rdx, [rbx+118h]; lpSubKey
0x1800215c3  lea     rax, [rbp+dwDisposition]
0x1800215c7  mov     rcx, [rbp+arg_18]; hKey
0x1800215cb  xor     r9d, r9d; lpClass
0x1800215ce  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x1800215d3  xor     r8d, r8d; Reserved
0x1800215d6  lea     rax, [rbp+var_10]
0x1800215da  mov     [rsp+60h+var_28], rax; phkResult
0x1800215df  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800215e8  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800215f0  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x1800215f8  call    cs:__imp_RegCreateKeyExW
0x1800215fe  jmp     loc_180021542
0x180021603  call    cs:__imp_RegCloseKey
0x180021609  jmp     loc_180021558
```
