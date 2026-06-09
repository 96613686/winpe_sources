# VsmUtils::TrustletProcess::WaitForTrustletStopped(ulong,long *)

- ea: `0x1800253b4`
- end: `0x180025498`
- name: `?WaitForTrustletStopped@TrustletProcess@VsmUtils@@QEAAJKPEAJ@Z`
- size: `228`
- prototype: `__int64 __fastcall(VsmUtils::TrustletProcess *__hidden this, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800250a8`

## callees

- `0x1800232a0`
- `0x1800253b4`
- `0x180029040`
- `0x180037348`
- `0x18005ea14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800253c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800253c9`
- `ntdll!NtQueryInformationProcess` at `0x180025426`
- `ntdll!NtQueryInformationProcess` at `0x180025426`

## string_xrefs

- `0x1800253de`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x18002543b`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x18002545e`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
int __fastcall VsmUtils::TrustletProcess::WaitForTrustletStopped(VsmUtils::TrustletProcess *this, __int64 a2, int *a3)
{
  DWORD v4; // eax
  NTSTATUS InformationProcess; // eax
  int v7; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-48h]
  int ReturnLengtha; // [rsp+20h] [rbp-48h]
  _OWORD ProcessInformation[3]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = WaitForSingleObject(ProcessHandle, 0x1388u);
  if ( v4 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xC8,
             (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
             (const char *)v4,
             ReturnLength);
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  InformationProcess = NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xD0,
             (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
             (const char *)(unsigned int)InformationProcess,
             ReturnLengtha);
  v7 = ProcessInformation[0];
  if ( SLODWORD(ProcessInformation[0]) < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      (const char *)LODWORD(ProcessInformation[0]),
      ReturnLengtha);
    v7 = ProcessInformation[0];
  }
  if ( a3 )
    *a3 = v7 | 0x10000000;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &ProcessHandle,
    0);
  return 0;
}

```

## disassembly

```asm
0x1800253b4  push    rbx
0x1800253b6  sub     rsp, 60h
0x1800253ba  mov     rcx, cs:ProcessHandle; hHandle
0x1800253c1  mov     edx, 1388h; dwMilliseconds
0x1800253c6  mov     rbx, r8
0x1800253c9  call    cs:__imp_WaitForSingleObject
0x1800253d0  nop     dword ptr [rax+rax+00h]
0x1800253d5  test    eax, eax
0x1800253d7  jz      short loc_1800253F7
0x1800253d9  mov     rcx, [rsp+68h]; this
0x1800253de  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x1800253e5  mov     r9d, eax; char *
0x1800253e8  mov     edx, 0C8h; void *
0x1800253ed  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800253f2  jmp     loc_180025491
0x1800253f7  mov     rcx, cs:ProcessHandle; ProcessHandle
0x1800253fe  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x180025403  xorps   xmm0, xmm0
0x180025406  mov     qword ptr [rsp+68h+ReturnLength], 0; int
0x18002540f  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180025415  xor     edx, edx; ProcessInformationClass
0x180025417  movups  [rsp+68h+ProcessInformation], xmm0
0x18002541c  movups  [rsp+68h+var_28], xmm0
0x180025421  movups  [rsp+68h+var_18], xmm0
0x180025426  call    cs:__imp_NtQueryInformationProcess
0x18002542d  nop     dword ptr [rax+rax+00h]
0x180025432  test    eax, eax
0x180025434  jns     short loc_180025451
0x180025436  mov     rcx, [rsp+68h]; this
0x18002543b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x180025442  mov     r9d, eax; char *
0x180025445  mov     edx, 0D0h; void *
0x18002544a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002544f  jmp     short loc_180025491
0x180025451  mov     eax, dword ptr [rsp+68h+ProcessInformation]
0x180025455  test    eax, eax
0x180025457  jns     short loc_180025476
0x180025459  mov     rcx, [rsp+68h]; this
0x18002545e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x180025465  mov     r9d, eax; char *
0x180025468  mov     edx, 0D1h; void *
0x18002546d  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180025472  mov     eax, dword ptr [rsp+68h+ProcessInformation]
0x180025476  test    rbx, rbx
0x180025479  jz      short loc_180025481
0x18002547b  bts     eax, 1Ch
0x18002547f  mov     [rbx], eax
0x180025481  xor     edx, edx
0x180025483  lea     rcx, ProcessHandle
0x18002548a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002548f  xor     eax, eax
0x180025491  add     rsp, 60h
0x180025495  pop     rbx
0x180025496  retn
```
