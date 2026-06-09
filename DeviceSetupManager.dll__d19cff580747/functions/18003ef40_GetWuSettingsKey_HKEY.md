# GetWuSettingsKey(HKEY__ * *)

- ea: `0x18003ef40`
- end: `0x18003f08f`
- name: `?GetWuSettingsKey@@YAJPEAPEAUHKEY__@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024814`
- `0x18003f098`

## callees

- `0x180010a7c`
- `0x180010eb8`
- `0x1800112a4`
- `0x18001af70`
- `0x18001ba48`
- `0x18003ef40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f058`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003f058`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003ef95`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18003ef95`

## string_xrefs

- `0x18003ef8e`: `WindowsUpdateUXRoot`
- `0x18003ef87`: `SOFTWARE\Microsoft\WindowsUpdate\UX`

## pseudocode

```c
__int64 __fastcall GetWuSettingsKey(PHKEY phkResult)
{
  unsigned int PersistedRegistryLocationW; // eax
  __int64 v3; // rdx
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int dwOptions; // [rsp+20h] [rbp-258h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(SubKey, 0, 0x208u);
  dwOptions = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdateUXRoot",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX",
                                 SubKey,
                                 520);
  if ( PersistedRegistryLocationW )
  {
    v3 = 752;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v3,
             (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
             (const char *)PersistedRegistryLocationW,
             dwOptions);
  }
  v5 = StringCchCatW(SubKey, 0x104u, L"\\");
  if ( v5 < 0 )
  {
    v6 = 754;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\lib\\utils\\dsmutils.cpp",
      (const char *)(unsigned int)v5,
      0);
    return (unsigned int)v5;
  }
  v5 = StringCchCatW(SubKey, 0x104u, L"Settings");
  if ( v5 < 0 )
  {
    v6 = 755;
    goto LABEL_6;
  }
  PersistedRegistryLocationW = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20019u, 0, phkResult, 0);
  if ( PersistedRegistryLocationW )
  {
    v3 = 765;
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
0x18003ef40  mov     [rsp+arg_8], rbx
0x18003ef45  push    rdi
0x18003ef46  sub     rsp, 270h
0x18003ef4d  mov     rax, cs:__security_cookie
0x18003ef54  xor     rax, rsp
0x18003ef57  mov     [rsp+278h+var_18], rax
0x18003ef5f  mov     rdi, rcx
0x18003ef62  mov     ebx, 208h
0x18003ef67  mov     r8d, ebx; Size
0x18003ef6a  lea     rcx, [rsp+278h+SubKey]; void *
0x18003ef6f  xor     edx, edx; Val
0x18003ef71  call    memset_0
0x18003ef76  mov     r9d, ebx
0x18003ef79  mov     qword ptr [rsp+278h+dwOptions], 0; int
0x18003ef82  lea     r8, [rsp+278h+SubKey]
0x18003ef87  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"
0x18003ef8e  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x18003ef95  call    cs:__imp_GetPersistedRegistryLocationW
0x18003ef9b  test    eax, eax
0x18003ef9d  jz      short loc_18003EFC0
0x18003ef9f  mov     edx, 2F0h; void *
0x18003efa4  mov     rcx, [rsp+278h]; this
0x18003efac  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003efb3  mov     r9d, eax; char *
0x18003efb6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003efbb  jmp     loc_18003F06E
0x18003efc0  lea     r8, asc_18004C1D8; "\\"
0x18003efc7  mov     edx, 104h; unsigned __int64
0x18003efcc  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18003efd1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003efd6  mov     ebx, eax
0x18003efd8  test    eax, eax
0x18003efda  jns     short loc_18003EFFC
0x18003efdc  mov     edx, 2F2h; void *
0x18003efe1  mov     rcx, [rsp+278h]; this
0x18003efe9  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\devices\\setup\\lib\\"...
0x18003eff0  mov     r9d, ebx; char *
0x18003eff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eff8  mov     eax, ebx
0x18003effa  jmp     short loc_18003F06E
0x18003effc  lea     r8, aSettings; "Settings"
0x18003f003  mov     edx, 104h; unsigned __int64
0x18003f008  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18003f00d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f012  mov     ebx, eax
0x18003f014  test    eax, eax
0x18003f016  jns     short loc_18003F01F
0x18003f018  mov     edx, 2F3h
0x18003f01d  jmp     short loc_18003EFE1
0x18003f01f  mov     [rsp+278h+lpdwDisposition], 0; lpdwDisposition
0x18003f028  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18003f02d  mov     [rsp+278h+phkResult], rdi; phkResult
0x18003f032  xor     r9d, r9d; lpClass
0x18003f035  mov     [rsp+278h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003f03e  xor     r8d, r8d; Reserved
0x18003f041  mov     [rsp+278h+samDesired], 20019h; samDesired
0x18003f049  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f050  mov     [rsp+278h+dwOptions], 0; dwOptions
0x18003f058  call    cs:__imp_RegCreateKeyExW
0x18003f05e  test    eax, eax
0x18003f060  jz      short loc_18003F06C
0x18003f062  mov     edx, 2FDh
0x18003f067  jmp     loc_18003EFA4
0x18003f06c  xor     eax, eax
0x18003f06e  mov     rcx, [rsp+278h+var_18]
0x18003f076  xor     rcx, rsp; StackCookie
0x18003f079  call    __security_check_cookie
0x18003f07e  mov     rbx, [rsp+278h+arg_8]
0x18003f086  add     rsp, 270h
0x18003f08d  pop     rdi
0x18003f08e  retn
```
