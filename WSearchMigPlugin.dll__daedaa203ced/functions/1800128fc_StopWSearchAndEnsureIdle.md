# StopWSearchAndEnsureIdle

- ea: `0x1800128fc`
- end: `0x1800129ce`
- name: `StopWSearchAndEnsureIdle`
- size: `210`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014bf0`

## callees

- `0x1800026f0`
- `0x180011220`
- `0x1800127e0`
- `0x1800128fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012964`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012964`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800129a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800129a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001294e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001294e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129ab`

## string_xrefs

- `0x180012957`: `Global\WSearchMigPluginActive`
- `0x180012999`: `MigPluginHandle`

## pseudocode

```c
__int64 __fastcall StopWSearchAndEnsureIdle(struct IUnknown *a1)
{
  HANDLE EventW; // rax
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  hKey = 0;
  MapRegKeyPathIfNeeded(a1, (OLECHAR *)L"SOFTWARE\\Microsoft\\Windows Search", SubKey);
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 3u, &hKey);
  EventW = CreateEventW(0, 1, 0, L"Global\\WSearchMigPluginActive");
  *(_QWORD *)Data = EventW;
  if ( hKey && EventW )
  {
    RegSetValueExW(hKey, L"MigPluginHandle", 0, 3u, Data, 8u);
    RegCloseKey(hKey);
  }
  return StopWSearch();
}

```

## disassembly

```asm
0x1800128fc  sub     rsp, 268h
0x180012903  mov     rax, cs:__security_cookie
0x18001290a  xor     rax, rsp
0x18001290d  mov     [rsp+268h+var_18], rax
0x180012915  lea     r8, [rsp+268h+SubKey]
0x18001291a  mov     [rsp+268h+hKey], 0
0x180012923  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x18001292a  call    MapRegKeyPathIfNeeded
0x18001292f  lea     rax, [rsp+268h+hKey]
0x180012934  mov     r9d, 3; samDesired
0x18001293a  xor     r8d, r8d; ulOptions
0x18001293d  mov     [rsp+268h+phkResult], rax; phkResult
0x180012942  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x180012947  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001294e  call    cs:__imp_RegOpenKeyExW
0x180012954  xor     r8d, r8d; bInitialState
0x180012957  lea     r9, Name; "Global\\WSearchMigPluginActive"
0x18001295e  xor     ecx, ecx; lpEventAttributes
0x180012960  lea     edx, [r8+1]; bManualReset
0x180012964  call    cs:__imp_CreateEventW
0x18001296a  mov     rcx, [rsp+268h+hKey]; hKey
0x18001296f  mov     qword ptr [rsp+268h+Data], rax
0x180012974  test    rcx, rcx
0x180012977  jz      short loc_1800129B1
0x180012979  test    rax, rax
0x18001297c  jz      short loc_1800129B1
0x18001297e  lea     rax, [rsp+268h+Data]
0x180012983  mov     [rsp+268h+cbData], 8; cbData
0x18001298b  mov     r9d, 3; dwType
0x180012991  mov     [rsp+268h+phkResult], rax; lpData
0x180012996  xor     r8d, r8d; Reserved
0x180012999  lea     rdx, pszValue; "MigPluginHandle"
0x1800129a0  call    cs:__imp_RegSetValueExW
0x1800129a6  mov     rcx, [rsp+268h+hKey]; hKey
0x1800129ab  call    cs:__imp_RegCloseKey
0x1800129b1  call    StopWSearch
0x1800129b6  mov     rcx, [rsp+268h+var_18]
0x1800129be  xor     rcx, rsp; StackCookie
0x1800129c1  call    __security_check_cookie
0x1800129c6  add     rsp, 268h
0x1800129cd  retn
```
