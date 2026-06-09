# ScHelperInitializeEventLogHandle(void)

- ea: `0x18006e0c8`
- end: `0x18006e1e2`
- name: `?ScHelperInitializeEventLogHandle@@YAJXZ`
- size: `282`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d778`

## callees

- `0x18006e0c8`
- `0x1800719c8`
- `0x180071a3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e127`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e127`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e16b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e19d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e16b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e19d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e1a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e1a8`

## string_xrefs

- `0x18006e0ee`: `System\CurrentControlSet\Services\EventLog\Application\Smart Card Logon`
- `0x18006e147`: `%SystemRoot%\System32\kerberos.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ScHelperInitializeEventLogHandle(void)
{
  struct _RTL_CRITICAL_SECTION *v1; // rax
  DWORD Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  if ( ScHelperGlobalEventLogHandle )
    return 0;
  hKey = 0;
  Data = 0;
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\EventLog\\Application\\Smart Card Logon",
         0,
         (LPWSTR)&Class,
         0,
         0x20006u,
         0,
         &hKey,
         &Data) )
  {
    return 3221225473LL;
  }
  if ( Data == 1 )
  {
    RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, L"%SystemRoot%\\System32\\kerberos.dll", 0x46u);
    Data = 7;
    RegSetValueExW(hKey, L"TypesSupported", 0, 4u, (const BYTE *)&Data, 4u);
  }
  RegCloseKey(hKey);
  v1 = (struct _RTL_CRITICAL_SECTION *)NetpEventlogOpen((wchar_t *)L"Smart Card Logon");
  if ( v1 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&ScHelperGlobalEventLogHandle, (signed __int64)v1, 0) )
      NetpEventlogClose(v1);
    return 0;
  }
  return 3221225871LL;
}

```

## disassembly

```asm
0x18006e0c8  mov     r11, rsp
0x18006e0cb  sub     rsp, 58h
0x18006e0cf  mov     rax, cs:?ScHelperGlobalEventLogHandle@@3REAXEA; void * ScHelperGlobalEventLogHandle
0x18006e0d6  test    rax, rax
0x18006e0d9  jnz     loc_18006E1D4
0x18006e0df  mov     [r11+10h], rax
0x18006e0e3  lea     r9, Class; lpClass
0x18006e0ea  mov     [rsp+58h+Data], eax
0x18006e0ee  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ev"...
0x18006e0f5  lea     rax, [r11+8]
0x18006e0f9  xor     r8d, r8d; Reserved
0x18006e0fc  mov     [r11-18h], rax
0x18006e100  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e107  lea     rax, [r11+10h]
0x18006e10b  mov     [r11-20h], rax
0x18006e10f  mov     qword ptr [r11-28h], 0
0x18006e117  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18006e11f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18006e127  call    cs:__imp_RegCreateKeyExW
0x18006e12d  test    eax, eax
0x18006e12f  jz      short loc_18006E13B
0x18006e131  mov     eax, 0C0000001h
0x18006e136  jmp     loc_18006E1D6
0x18006e13b  cmp     [rsp+58h+Data], 1
0x18006e140  jnz     short loc_18006E1A3
0x18006e142  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e147  lea     rax, Data; "%SystemRoot%\\System32\\kerberos.dll"
0x18006e14e  mov     [rsp+58h+samDesired], 46h ; 'F'; cbData
0x18006e156  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18006e15d  mov     r9d, 2; dwType
0x18006e163  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18006e168  xor     r8d, r8d; Reserved
0x18006e16b  call    cs:__imp_RegSetValueExW
0x18006e171  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e176  lea     rax, [rsp+58h+Data]
0x18006e17b  mov     r9d, 4; dwType
0x18006e181  mov     [rsp+58h+Data], 7
0x18006e189  mov     [rsp+58h+samDesired], r9d; cbData
0x18006e18e  lea     rdx, aTypessupported; "TypesSupported"
0x18006e195  xor     r8d, r8d; Reserved
0x18006e198  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18006e19d  call    cs:__imp_RegSetValueExW
0x18006e1a3  mov     rcx, [rsp+58h+hKey]; hKey
0x18006e1a8  call    cs:__imp_RegCloseKey
0x18006e1ae  lea     rcx, aSmartCardLogon; "Smart Card Logon"
0x18006e1b5  call    NetpEventlogOpen
0x18006e1ba  mov     rcx, rax; lpCriticalSection
0x18006e1bd  test    rax, rax
0x18006e1c0  jz      short loc_18006E1DB
0x18006e1c2  xor     eax, eax
0x18006e1c4  lock cmpxchg cs:?ScHelperGlobalEventLogHandle@@3REAXEA, rcx; void * ScHelperGlobalEventLogHandle
0x18006e1cd  jz      short loc_18006E1D4
0x18006e1cf  call    NetpEventlogClose
0x18006e1d4  xor     eax, eax
0x18006e1d6  add     rsp, 58h
0x18006e1da  retn
0x18006e1db  mov     eax, 0C000018Fh
0x18006e1e0  jmp     short loc_18006E1D6
```
