# Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener(void)

- ea: `0x1800487ec`
- end: `0x1800489cb`
- name: `?CreateParentListener@TelemetryAppraiser@Appraiser@Compat@Windows@@SAPEAXXZ`
- size: `479`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014090`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800487ec`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180048826`
- `ntdll!NtQueryInformationProcess` at `0x180048826`
- `KERNEL32!OpenProcess` at `0x1800488a5`
- `KERNEL32!OpenProcess` at `0x1800488a5`
- `KERNEL32!CreateThread` at `0x180048963`
- `KERNEL32!CreateThread` at `0x180048963`
- `KERNEL32!GetCurrentProcess` at `0x180048807`
- `KERNEL32!GetCurrentProcess` at `0x180048807`
- `KERNEL32!GetLastError` at `0x1800488b3`
- `KERNEL32!GetLastError` at `0x180048971`
- `KERNEL32!GetLastError` at `0x1800488b3`
- `KERNEL32!GetLastError` at `0x180048971`

## string_xrefs

- `0x180048846`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x18004888d`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x1800488ea`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180048938`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x1800489ae`: `onecore\base\appcompat\appraiser\heads\telemetry\telemetryappraiser.cpp`
- `0x180048992`: `CreateThread failed`
- `0x180048931`: `Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener`
- `0x1800489a2`: `Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener`
- `0x18004884d`: `Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle`
- `0x180048881`: `Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle`
- `0x1800488db`: `Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle`
- `0x1800488cd`: `OpenProcess failed`

## pseudocode

```c
HANDLE Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener(void)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS InformationProcess; // eax
  int v2; // ebx
  HANDLE v3; // rbx
  signed int LastError; // eax
  HANDLE Thread; // rbp
  signed int v6; // eax
  const char *ReturnLength; // [rsp+20h] [rbp-58h]
  const char *ReturnLengtha; // [rsp+20h] [rbp-58h]
  const char *ReturnLengthb; // [rsp+20h] [rbp-58h]
  char *v11; // [rsp+30h] [rbp-48h]
  char *v12; // [rsp+30h] [rbp-48h]
  _BYTE ProcessInformation[32]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v14; // [rsp+60h] [rbp-18h]

  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v14 = 0;
  CurrentProcess = GetCurrentProcess();
  InformationProcess = NtQueryInformationProcess(CurrentProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  v2 = InformationProcess | 0x10000000;
  if ( InformationProcess < 0 )
  {
    LODWORD(v11) = InformationProcess | 0x10000000;
    LODWORD(ReturnLength) = InformationProcess | 0x10000000;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      69,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle",
      ReturnLength,
      (int)"NtQueryInformationProcess failed: [0x%x].",
      v11);
LABEL_11:
    Thread = 0;
    LODWORD(ReturnLengtha) = v2;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      35,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener",
      ReturnLengtha,
      (int)"Couldn't get parent process handle",
      v12);
    return Thread;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x445u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle",
      "NtQueryInformationProcess failed: [0x%x].",
      v2);
  v3 = OpenProcess(0x100400u, 0, DWORD2(v14));
  if ( !v3 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
      v2 = -2147467259;
    LODWORD(ReturnLength) = v2;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      78,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::GetParentProcessHandle",
      ReturnLength,
      (int)"OpenProcess failed",
      v11);
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x423u,
      "onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener",
      "Couldn't get parent process handle");
  Thread = CreateThread(0, 0, Windows::Compat::Appraiser::TelemetryAppraiser::ParentProcessMonitorThread, v3, 0, 0);
  if ( !Thread )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LODWORD(ReturnLengthb) = v6;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      45,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\telemetry\\telemetryappraiser.cpp",
      "Windows::Compat::Appraiser::TelemetryAppraiser::CreateParentListener",
      ReturnLengthb,
      (int)"CreateThread failed",
      v11);
  }
  return Thread;
}

```

## disassembly

```asm
0x1800487ec  mov     rax, rsp
0x1800487ef  mov     [rax+8], rbx
0x1800487f3  push    rbp
0x1800487f4  sub     rsp, 70h
0x1800487f8  xorps   xmm0, xmm0
0x1800487fb  movups  xmmword ptr [rax-38h], xmm0
0x1800487ff  movups  xmmword ptr [rax-28h], xmm0
0x180048803  movups  xmmword ptr [rax-18h], xmm0
0x180048807  call    cs:__imp_GetCurrentProcess
0x18004880d  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180048813  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x18004881c  mov     rcx, rax; ProcessHandle
0x18004881f  lea     r8, [rsp+78h+ProcessInformation]; ProcessInformation
0x180048824  xor     edx, edx; ProcessInformationClass
0x180048826  call    cs:__imp_NtQueryInformationProcess
0x18004882c  mov     ebx, eax
0x18004882e  or      ebx, 10000000h
0x180048834  jge     short loc_18004886C
0x180048836  lea     r9, aNtqueryinforma; "NtQueryInformationProcess failed: [0x%x"...
0x18004883d  mov     dword ptr [rsp+78h+var_48], ebx; char *
0x180048841  mov     [rsp+78h+lpThreadId], r9; int
0x180048846  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004884d  lea     r9, aWindowsCompatA_167; "Windows::Compat::Appraiser::TelemetryAp"...
0x180048854  mov     dword ptr [rsp+78h+ReturnLength], ebx; char *
0x180048858  mov     edx, 445h; bool
0x18004885d  mov     ecx, 1; this
0x180048862  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180048867  jmp     loc_1800488FF
0x18004886c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048872  test    al, 1
0x180048874  jz      short loc_180048899
0x180048876  lea     r9, aNtqueryinforma; "NtQueryInformationProcess failed: [0x%x"...
0x18004887d  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x180048881  lea     r8, aWindowsCompatA_167; "Windows::Compat::Appraiser::TelemetryAp"...
0x180048888  mov     ecx, 445h; unsigned int
0x18004888d  lea     rdx, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x180048894  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048899  mov     r8d, [rsp+78h+dwProcessId]; dwProcessId
0x18004889e  xor     edx, edx; bInheritHandle
0x1800488a0  mov     ecx, 100400h; dwDesiredAccess
0x1800488a5  call    cs:__imp_OpenProcess
0x1800488ab  mov     rbx, rax
0x1800488ae  test    rax, rax
0x1800488b1  jnz     short loc_18004891B
0x1800488b3  call    cs:__imp_GetLastError
0x1800488b9  mov     ebx, eax
0x1800488bb  test    eax, eax
0x1800488bd  jle     short loc_1800488C8
0x1800488bf  movzx   ebx, ax
0x1800488c2  or      ebx, 80070000h
0x1800488c8  mov     ecx, 80004005h
0x1800488cd  lea     rax, aOpenprocessFai; "OpenProcess failed"
0x1800488d4  test    ebx, ebx
0x1800488d6  mov     [rsp+78h+lpThreadId], rax; int
0x1800488db  lea     r9, aWindowsCompatA_167; "Windows::Compat::Appraiser::TelemetryAp"...
0x1800488e2  mov     edx, 44Eh; bool
0x1800488e7  cmovns  ebx, ecx
0x1800488ea  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800488f1  mov     ecx, 1; this
0x1800488f6  mov     dword ptr [rsp+78h+ReturnLength], ebx; char *
0x1800488fa  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800488ff  lea     r9, aCouldnTGetPare; "Couldn't get parent process handle"
0x180048906  xor     ebp, ebp
0x180048908  mov     [rsp+78h+lpThreadId], r9
0x18004890d  mov     edx, 423h
0x180048912  mov     dword ptr [rsp+78h+ReturnLength], ebx
0x180048916  jmp     loc_1800489A2
0x18004891b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180048921  test    al, 1
0x180048923  jz      short loc_180048944
0x180048925  lea     r9, aCouldnTGetPare; "Couldn't get parent process handle"
0x18004892c  mov     ecx, 423h; unsigned int
0x180048931  lea     r8, aWindowsCompatA_644; "Windows::Compat::Appraiser::TelemetryAp"...
0x180048938  lea     rdx, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004893f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180048944  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18004894d  lea     r8, ?ParentProcessMonitorThread@TelemetryAppraiser@Appraiser@Compat@Windows@@CAKPEAX@Z; lpStartAddress
0x180048954  mov     r9, rbx; lpParameter
0x180048957  mov     dword ptr [rsp+78h+ReturnLength], 0; dwCreationFlags
0x18004895f  xor     edx, edx; dwStackSize
0x180048961  xor     ecx, ecx; lpThreadAttributes
0x180048963  call    cs:__imp_CreateThread
0x180048969  mov     rbp, rax
0x18004896c  test    rax, rax
0x18004896f  jnz     short loc_1800489BA
0x180048971  call    cs:__imp_GetLastError
0x180048977  test    eax, eax
0x180048979  jle     short loc_180048983
0x18004897b  movzx   eax, ax
0x18004897e  or      eax, 80070000h
0x180048983  mov     ecx, 80004005h
0x180048988  test    eax, eax
0x18004898a  mov     edx, 42Dh; bool
0x18004898f  cmovns  eax, ecx
0x180048992  lea     rcx, aCreatethreadFa; "CreateThread failed"
0x180048999  mov     [rsp+78h+lpThreadId], rcx; int
0x18004899e  mov     dword ptr [rsp+78h+ReturnLength], eax; char *
0x1800489a2  lea     r9, aWindowsCompatA_644; "Windows::Compat::Appraiser::TelemetryAp"...
0x1800489a9  mov     ecx, 1; this
0x1800489ae  lea     r8, aOnecoreBaseApp_75; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800489b5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800489ba  mov     rbx, [rsp+78h+arg_0]
0x1800489c2  mov     rax, rbp
0x1800489c5  add     rsp, 70h
0x1800489c9  pop     rbp
0x1800489ca  retn
```
