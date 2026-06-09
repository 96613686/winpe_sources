# Windows::Power::IsSleepOnACEnabled(void)

- ea: `0x180066a60`
- end: `0x180066b77`
- name: `?IsSleepOnACEnabled@Power@Windows@@UEAA_NXZ`
- size: `279`
- prototype: `bool __fastcall(Windows::Power *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180025cd0`
- `0x180066a60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066ac5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066b3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066ac5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066b3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066ab7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066b2e`
- `POWRPROF!PowerGetActiveScheme` at `0x180066a8d`
- `POWRPROF!PowerGetActiveScheme` at `0x180066a8d`
- `POWRPROF!PowerReadACValue` at `0x180066b08`
- `POWRPROF!PowerReadACValue` at `0x180066b08`

## string_xrefs

- `0x180066b50`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`
- `0x180066b65`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Windows::Power::IsSleepOnACEnabled(Windows::Power *this)
{
  DWORD ActiveScheme; // eax
  GUID *v2; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v4; // eax
  bool v5; // di
  GUID *v6; // rbx
  HANDLE v7; // rax
  unsigned int Type; // [rsp+20h] [rbp-40h]
  unsigned int Typea; // [rsp+20h] [rbp-40h]
  GUID *ActivePolicyGuid; // [rsp+48h] [rbp-18h] BYREF
  char v12; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int Buffer; // [rsp+88h] [rbp+28h] BYREF
  DWORD BufferSize; // [rsp+90h] [rbp+30h] BYREF
  GUID *SchemeGuid; // [rsp+98h] [rbp+38h]

  SchemeGuid = 0;
  ActivePolicyGuid = 0;
  v12 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  if ( ActiveScheme )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
      (const char *)ActiveScheme,
      Type);
  if ( v12 )
  {
    v2 = SchemeGuid;
    SchemeGuid = ActivePolicyGuid;
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
  }
  Buffer = 0;
  BufferSize = 4;
  v4 = PowerReadACValue(0, SchemeGuid, &GUID_SLEEP_SUBGROUP, &GUID_STANDBY_TIMEOUT, 0, (LPBYTE)&Buffer, &BufferSize);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
      (const char *)v4,
      Typea);
  v5 = Buffer != 0;
  v6 = SchemeGuid;
  SchemeGuid = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180066a60  push    rbp
0x180066a62  push    rbx
0x180066a63  push    rdi
0x180066a64  mov     rbp, rsp
0x180066a67  sub     rsp, 60h
0x180066a6b  mov     [rbp+SchemeGuid], 0
0x180066a73  lea     rax, [rbp+SchemeGuid]
0x180066a77  mov     [rbp+var_20], rax
0x180066a7b  mov     [rbp+ActivePolicyGuid], 0
0x180066a83  mov     [rbp+var_10], 1
0x180066a87  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x180066a8b  xor     ecx, ecx; UserRootPowerKey
0x180066a8d  call    cs:__imp_PowerGetActiveScheme
0x180066a93  mov     rcx, [rbp+18h]; this
0x180066a97  test    eax, eax
0x180066a99  jnz     loc_180066B62
0x180066a9f  cmp     [rbp+var_10], al
0x180066aa2  jz      short loc_180066ACB
0x180066aa4  mov     rcx, [rbp+var_20]
0x180066aa8  mov     rbx, [rcx]
0x180066aab  mov     rax, [rbp+ActivePolicyGuid]
0x180066aaf  mov     [rcx], rax
0x180066ab2  test    rbx, rbx
0x180066ab5  jz      short loc_180066ACB
0x180066ab7  call    cs:__imp_GetProcessHeap
0x180066abd  mov     rcx, rax; hHeap
0x180066ac0  mov     r8, rbx; lpMem
0x180066ac3  xor     edx, edx; dwFlags
0x180066ac5  call    cs:__imp_HeapFree
0x180066acb  mov     [rbp+arg_8], 0
0x180066ad2  mov     [rbp+arg_10], 4
0x180066ad9  lea     rax, [rbp+arg_10]
0x180066add  mov     [rsp+60h+BufferSize], rax; BufferSize
0x180066ae2  lea     rax, [rbp+arg_8]
0x180066ae6  mov     [rsp+60h+Buffer], rax; Buffer
0x180066aeb  mov     [rsp+60h+Type], 0; unsigned int
0x180066af4  lea     r9, GUID_STANDBY_TIMEOUT; PowerSettingGuid
0x180066afb  lea     r8, GUID_SLEEP_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180066b02  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x180066b06  xor     ecx, ecx; RootPowerKey
0x180066b08  call    cs:__imp_PowerReadACValue
0x180066b0e  mov     rcx, [rbp+18h]; this
0x180066b12  test    eax, eax
0x180066b14  jnz     short loc_180066B4D
0x180066b16  cmp     [rbp+arg_8], eax
0x180066b19  setnz   dil
0x180066b1d  mov     rbx, [rbp+SchemeGuid]
0x180066b21  mov     [rbp+SchemeGuid], 0
0x180066b29  test    rbx, rbx
0x180066b2c  jz      short loc_180066B42
0x180066b2e  call    cs:__imp_GetProcessHeap
0x180066b34  mov     rcx, rax; hHeap
0x180066b37  mov     r8, rbx; lpMem
0x180066b3a  xor     edx, edx; dwFlags
0x180066b3c  call    cs:__imp_HeapFree
0x180066b42  mov     al, dil
0x180066b45  add     rsp, 60h
0x180066b49  pop     rdi
0x180066b4a  pop     rbx
0x180066b4b  pop     rbp
0x180066b4c  retn
0x180066b4d  mov     r9d, eax; char *
0x180066b50  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180066b57  mov     edx, 0D2h; void *
0x180066b5c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180066b62  mov     r9d, eax; char *
0x180066b65  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180066b6c  mov     edx, 0C7h; void *
0x180066b71  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
