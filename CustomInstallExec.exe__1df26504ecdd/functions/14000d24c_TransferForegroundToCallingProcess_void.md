# TransferForegroundToCallingProcess(void)

- ea: `0x14000d24c`
- end: `0x14000d2ea`
- name: `?TransferForegroundToCallingProcess@@YAXXZ`
- size: `158`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14000d884`

## callees

- `0x140007d78`
- `0x14000d24c`
- `0x14000d534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000d262`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000d262`
- `ntdll!NtQueryInformationProcess` at `0x14000d281`
- `ntdll!NtQueryInformationProcess` at `0x14000d281`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14000d2b4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14000d2b4`

## string_xrefs

- `0x14000d290`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`
- `0x14000d2d2`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\main.cpp`

## pseudocode

```c
void TransferForegroundToCallingProcess(void)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS InformationProcess; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  int ReturnLength; // [rsp+20h] [rbp-48h]
  _OWORD ProcessInformation[2]; // [rsp+30h] [rbp-38h] BYREF
  DWORD dwProcessId[4]; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)dwProcessId = 0;
  CurrentProcess = GetCurrentProcess();
  InformationProcess = NtQueryInformationProcess(CurrentProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x215,
      (int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
      (const char *)(unsigned int)InformationProcess,
      ReturnLength);
  if ( *(_QWORD *)&dwProcessId[2] > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x216,
      (int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\main.cpp",
      (const char *)0x80070216LL,
      ReturnLength);
  if ( !AllowSetForegroundWindow(dwProcessId[2]) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v2, v3, v4);
}

```

## disassembly

```asm
0x14000d24c  sub     rsp, 68h
0x14000d250  xorps   xmm0, xmm0
0x14000d253  movups  [rsp+68h+ProcessInformation], xmm0
0x14000d258  movups  [rsp+68h+var_28], xmm0
0x14000d25d  movups  xmmword ptr [rsp+68h+dwProcessId], xmm0
0x14000d262  call    cs:__imp_GetCurrentProcess
0x14000d268  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14000d26e  mov     qword ptr [rsp+68h+ReturnLength], 0; int
0x14000d277  mov     rcx, rax; ProcessHandle
0x14000d27a  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x14000d27f  xor     edx, edx; ProcessInformationClass
0x14000d281  call    cs:__imp_NtQueryInformationProcess
0x14000d287  test    eax, eax
0x14000d289  jns     short loc_14000D2A5
0x14000d28b  mov     rcx, [rsp+68h]; this
0x14000d290  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000d297  mov     r9d, eax; char *
0x14000d29a  mov     edx, 215h; void *
0x14000d29f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000d2a5  mov     rcx, qword ptr [rsp+68h+dwProcessId+8]; dwProcessId
0x14000d2aa  mov     eax, 0FFFFFFFFh
0x14000d2af  cmp     rcx, rax
0x14000d2b2  ja      short loc_14000D2CD
0x14000d2b4  call    cs:__imp_AllowSetForegroundWindow
0x14000d2ba  test    eax, eax
0x14000d2bc  jnz     short loc_14000D2C8
0x14000d2be  mov     rcx, [rsp+68h]; this
0x14000d2c3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14000d2c8  add     rsp, 68h
0x14000d2cc  retn
0x14000d2cd  mov     rcx, [rsp+68h]; this
0x14000d2d2  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000d2d9  mov     r9d, 80070216h; char *
0x14000d2df  mov     edx, 216h; void *
0x14000d2e4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
