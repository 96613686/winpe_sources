# DoDebugBreak

- ea: `0x140020f3c`
- end: `0x140021026`
- name: `DoDebugBreak`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009820`
- `0x140012258`
- `0x1400161bc`
- `0x14001c4c8`
- `0x14001c538`

## callees

- `0x140020f3c`
- `0x140024650`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140021003`
- `ntdll!NtQuerySystemInformation` at `0x140021003`
- `ntdll!DbgPrintEx` at `0x140020f87`
- `ntdll!DbgPrintEx` at `0x140020fa7`
- `ntdll!DbgPrintEx` at `0x140020fb6`
- `ntdll!DbgPrintEx` at `0x140020fdd`
- `ntdll!DbgPrintEx` at `0x140020f87`
- `ntdll!DbgPrintEx` at `0x140020fa7`
- `ntdll!DbgPrintEx` at `0x140020fb6`
- `ntdll!DbgPrintEx` at `0x140020fdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140020f92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140020f92`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140020fc7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140020fe5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140020fc7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140020fe5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140020fc1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140020fc1`

## string_xrefs

- `0x140020f52`: `Software\Microsoft\Windows\CurrentVersion\Device Installer`
- `0x140020f7b`: `\nDRVINST.EXE: Unknown DebugInstall options, NOT breaking to debugger.\n\n`

## pseudocode

```c
__int64 __fastcall DoDebugBreak(__int64 a1)
{
  unsigned int v1; // ebx
  int PolicyValue; // eax
  int v3; // eax
  DWORD CurrentProcessId; // eax
  __int16 SystemInformation; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  PolicyValue = pSetupGetPolicyValue(
                  -2147483646,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Device Installer",
                  &qword_14004E980,
                  a1,
                  0,
                  0);
  if ( PolicyValue )
  {
    v3 = PolicyValue - 1;
    if ( v3 )
    {
      if ( v3 != 1 )
      {
        DbgPrintEx(0x23u, 0, "\nDRVINST.EXE: Unknown DebugInstall options, NOT breaking to debugger.\n\n");
        return v1;
      }
      CurrentProcessId = GetCurrentProcessId();
      DbgPrintEx(0x23u, 0, "\nDRVINST.EXE: Waiting for debugger on Process ID = %d ...", CurrentProcessId);
      while ( !IsDebuggerPresent() )
      {
        DbgPrintEx(0x23u, 0, ".");
        Sleep(0x3E8u);
      }
      DbgPrintEx(0x23u, 0, "Debugger detected!");
      return 1;
    }
    if ( IsDebuggerPresent() )
      return 1;
    SystemInformation = 0;
    if ( NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0) >= 0
      && (_BYTE)SystemInformation
      && !HIBYTE(SystemInformation) )
    {
      return 1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140020f3c  push    rbx
0x140020f3e  sub     rsp, 30h
0x140020f42  xor     ebx, ebx
0x140020f44  lea     r8, qword_14004E980
0x140020f4b  mov     r9, rcx
0x140020f4e  mov     [rsp+38h+var_10], ebx
0x140020f52  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140020f59  mov     [rsp+38h+var_18], ebx
0x140020f5d  mov     rcx, 0FFFFFFFF80000002h
0x140020f64  call    pSetupGetPolicyValue
0x140020f69  test    eax, eax
0x140020f6b  jz      loc_14002101E
0x140020f71  sub     eax, 1
0x140020f74  jz      short loc_140020FE5
0x140020f76  cmp     eax, 1
0x140020f79  jz      short loc_140020F92
0x140020f7b  lea     r8, aDrvinstExeUnkn; "\nDRVINST.EXE: Unknown DebugInstall opt"...
0x140020f82  xor     edx, edx; Level
0x140020f84  lea     ecx, [rbx+23h]; ComponentId
0x140020f87  call    cs:__imp_DbgPrintEx
0x140020f8d  jmp     loc_14002101E
0x140020f92  call    cs:__imp_GetCurrentProcessId
0x140020f98  xor     edx, edx; Level
0x140020f9a  lea     r8, aDrvinstExeWait; "\nDRVINST.EXE: Waiting for debugger on "...
0x140020fa1  mov     r9d, eax
0x140020fa4  lea     ecx, [rdx+23h]; ComponentId
0x140020fa7  call    cs:__imp_DbgPrintEx
0x140020fad  jmp     short loc_140020FC7
0x140020faf  lea     r8, asc_1400516FC; "."
0x140020fb6  call    cs:__imp_DbgPrintEx
0x140020fbc  mov     ecx, 3E8h; dwMilliseconds
0x140020fc1  call    cs:__imp_Sleep
0x140020fc7  call    cs:__imp_IsDebuggerPresent
0x140020fcd  xor     edx, edx; Level
0x140020fcf  lea     ecx, [rdx+23h]; ComponentId
0x140020fd2  test    eax, eax
0x140020fd4  jz      short loc_140020FAF
0x140020fd6  lea     r8, aDebuggerDetect; "Debugger detected!"
0x140020fdd  call    cs:__imp_DbgPrintEx
0x140020fe3  jmp     short loc_140021019
0x140020fe5  call    cs:__imp_IsDebuggerPresent
0x140020feb  test    eax, eax
0x140020fed  jnz     short loc_140021019
0x140020fef  xor     r9d, r9d; ReturnLength
0x140020ff2  mov     [rsp+38h+SystemInformation], ax
0x140020ff7  lea     r8d, [rax+2]; SystemInformationLength
0x140020ffb  lea     rdx, [rsp+38h+SystemInformation]; SystemInformation
0x140021000  lea     ecx, [rax+23h]; SystemInformationClass
0x140021003  call    cs:__imp_NtQuerySystemInformation
0x140021009  test    eax, eax
0x14002100b  js      short loc_14002101E
0x14002100d  cmp     byte ptr [rsp+38h+SystemInformation], bl
0x140021011  jz      short loc_14002101E
0x140021013  cmp     byte ptr [rsp+38h+SystemInformation+1], bl
0x140021017  jnz     short loc_14002101E
0x140021019  mov     ebx, 1
0x14002101e  mov     eax, ebx
0x140021020  add     rsp, 30h
0x140021024  pop     rbx
0x140021025  retn
```
