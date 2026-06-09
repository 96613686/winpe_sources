# GetDeviceSetupKey(HKEY__ * *)

- ea: `0x18000bfc0`
- end: `0x18000c0b4`
- name: `?GetDeviceSetupKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `244`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000bda0`
- `0x180023e70`
- `0x18002e3d0`
- `0x18003ea48`

## callees

- `0x18000bfc0`
- `0x180010eb8`
- `0x18001af70`
- `0x18001ba48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c069`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c069`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c014`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000c014`

## pseudocode

```c
__int64 __fastcall GetDeviceSetupKey(PHKEY phkResult)
{
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int Key; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-258h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(SubKey, 0, 0x208u);
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"DeviceSetup",
                                 L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceSetup",
                                 SubKey,
                                 520);
  if ( PersistedRegistryLocationW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x378,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)PersistedRegistryLocationW,
             0);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x382,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)Key,
             dwOptions);
  else
    return 0;
}

```

## disassembly

```asm
0x18000bfc0  mov     [rsp+arg_8], rbx
0x18000bfc5  push    rdi
0x18000bfc6  sub     rsp, 270h
0x18000bfcd  mov     rax, cs:__security_cookie
0x18000bfd4  xor     rax, rsp
0x18000bfd7  mov     [rsp+278h+var_18], rax
0x18000bfdf  mov     rbx, rcx
0x18000bfe2  xor     edx, edx; Val
0x18000bfe4  lea     rcx, [rsp+278h+SubKey]; void *
0x18000bfe9  mov     r8d, 208h; Size
0x18000bfef  call    memset_0
0x18000bff4  xor     edi, edi
0x18000bff6  lea     r8, [rsp+278h+SubKey]
0x18000bffb  mov     r9d, 208h
0x18000c001  mov     qword ptr [rsp+278h+dwOptions], rdi; unsigned int
0x18000c006  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c00d  lea     rcx, aDevicesetup; "DeviceSetup"
0x18000c014  call    cs:__imp_GetPersistedRegistryLocationW
0x18000c01a  test    eax, eax
0x18000c01c  jz      short loc_18000C03C
0x18000c01e  mov     rcx, [rsp+278h]; this
0x18000c026  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000c02d  mov     r9d, eax; char *
0x18000c030  mov     edx, 378h; void *
0x18000c035  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c03a  jmp     short loc_18000C093
0x18000c03c  mov     [rsp+278h+lpdwDisposition], rdi; lpdwDisposition
0x18000c041  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18000c046  mov     [rsp+278h+phkResult], rbx; phkResult
0x18000c04b  xor     r9d, r9d; lpClass
0x18000c04e  mov     [rsp+278h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000c053  xor     r8d, r8d; Reserved
0x18000c056  mov     [rsp+278h+samDesired], 0F003Fh; samDesired
0x18000c05e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c065  mov     [rsp+278h+dwOptions], edi; unsigned int
0x18000c069  call    cs:__imp_RegCreateKeyExW
0x18000c06f  test    eax, eax
0x18000c071  jz      short loc_18000C091
0x18000c073  mov     rcx, [rsp+278h]; this
0x18000c07b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18000c082  mov     r9d, eax; char *
0x18000c085  mov     edx, 382h; void *
0x18000c08a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c08f  jmp     short loc_18000C093
0x18000c091  xor     eax, eax
0x18000c093  mov     rcx, [rsp+278h+var_18]
0x18000c09b  xor     rcx, rsp; StackCookie
0x18000c09e  call    __security_check_cookie
0x18000c0a3  mov     rbx, [rsp+278h+arg_8]
0x18000c0ab  add     rsp, 270h
0x18000c0b2  pop     rdi
0x18000c0b3  retn
```
