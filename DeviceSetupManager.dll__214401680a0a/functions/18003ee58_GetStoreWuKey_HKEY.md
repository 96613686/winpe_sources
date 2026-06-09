# GetStoreWuKey(HKEY__ * *)

- ea: `0x18003ee58`
- end: `0x18003ef37`
- name: `?GetStoreWuKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024814`
- `0x18003f098`

## callees

- `0x180010eb8`
- `0x18001af70`
- `0x18001ba48`
- `0x18003ee58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ef0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ef0b`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003eeaa`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003eeaa`

## string_xrefs

- `0x18003eea3`: `WindowsStoreWindowsUpdate`
- `0x18003ee9c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsStore\WindowsUpdate`

## pseudocode

```c
__int64 __fastcall GetStoreWuKey(PHKEY phkResult)
{
  unsigned int PersistedRegistryLocationW; // eax
  __int64 v3; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-258h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(SubKey, 0, 0x208u);
  dwOptions = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsStoreWindowsUpdate",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate",
                                 SubKey,
                                 520);
  if ( PersistedRegistryLocationW )
  {
    v3 = 728;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v3,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)PersistedRegistryLocationW,
             dwOptions);
  }
  PersistedRegistryLocationW = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, phkResult, 0);
  if ( PersistedRegistryLocationW )
  {
    v3 = 738;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v3,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)PersistedRegistryLocationW,
             dwOptions);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ee58  push    rbx
0x18003ee5a  sub     rsp, 270h
0x18003ee61  mov     rax, cs:__security_cookie
0x18003ee68  xor     rax, rsp
0x18003ee6b  mov     [rsp+278h+var_18], rax
0x18003ee73  mov     rbx, rcx
0x18003ee76  xor     edx, edx; Val
0x18003ee78  lea     rcx, [rsp+278h+SubKey]; void *
0x18003ee7d  mov     r8d, 208h; Size
0x18003ee83  call    memset_0
0x18003ee88  mov     r9d, 208h
0x18003ee8e  mov     qword ptr [rsp+278h+dwOptions], 0; unsigned int
0x18003ee97  lea     r8, [rsp+278h+SubKey]
0x18003ee9c  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003eea3  lea     rcx, aWindowsstorewi; "WindowsStoreWindowsUpdate"
0x18003eeaa  call    cs:__imp_GetPersistedRegistryLocationW
0x18003eeb0  test    eax, eax
0x18003eeb2  jz      short loc_18003EED2
0x18003eeb4  mov     edx, 2D8h; void *
0x18003eeb9  mov     rcx, [rsp+278h]; this
0x18003eec1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003eec8  mov     r9d, eax; char *
0x18003eecb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003eed0  jmp     short loc_18003EF1E
0x18003eed2  mov     [rsp+278h+lpdwDisposition], 0; lpdwDisposition
0x18003eedb  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18003eee0  mov     [rsp+278h+phkResult], rbx; phkResult
0x18003eee5  xor     r9d, r9d; lpClass
0x18003eee8  mov     [rsp+278h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003eef1  xor     r8d, r8d; Reserved
0x18003eef4  mov     [rsp+278h+samDesired], 20019h; samDesired
0x18003eefc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ef03  mov     [rsp+278h+dwOptions], 0; dwOptions
0x18003ef0b  call    cs:__imp_RegCreateKeyExW
0x18003ef11  test    eax, eax
0x18003ef13  jz      short loc_18003EF1C
0x18003ef15  mov     edx, 2E2h
0x18003ef1a  jmp     short loc_18003EEB9
0x18003ef1c  xor     eax, eax
0x18003ef1e  mov     rcx, [rsp+278h+var_18]
0x18003ef26  xor     rcx, rsp; StackCookie
0x18003ef29  call    __security_check_cookie
0x18003ef2e  add     rsp, 270h
0x18003ef35  pop     rbx
0x18003ef36  retn
```
