# _CreateAuthHostProcess

- ea: `0x18001009c`
- end: `0x1800103f9`
- name: `_CreateAuthHostProcess`
- size: `861`
- prototype: `__int64 __fastcall(const wchar_t *applicationName, const wchar_t *commandLineArg, void *appContainerSid, _SID_AND_ATTRIBUTES *capabilities, unsigned int capabilityCount, DWORD clientProcessId, void **processHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ed84`
- `0x180010494`

## callees

- `0x180003f40`
- `0x1800053f8`
- `0x18000737c`
- `0x18001009c`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001022c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001035a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001022c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001035a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180010350`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180010350`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800101e2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800102ac`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800101e2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800102ac`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001012b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001017b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001012b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001017b`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800103b5`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800103b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800103ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010154`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010154`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001021c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001021c`

## pseudocode

```c
__int64 __fastcall CreateAuthHostProcess(
        const wchar_t *applicationName,
        const wchar_t *commandLineArg,
        void *appContainerSid,
        _SID_AND_ATTRIBUTES *capabilities,
        unsigned int capabilityCount,
        DWORD clientProcessId,
        void **processHandle)
{
  int v11; // ebx
  _PROC_THREAD_ATTRIBUTE_LIST *v12; // rax
  _PROC_THREAD_ATTRIBUTE_LIST *v13; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  signed int v16; // eax
  WPP_PROJECT_CONTROL_BLOCK *v17; // rcx
  unsigned __int16 v18; // dx
  signed int v19; // eax
  void *hThread; // rcx
  unsigned __int64 attributesLength; // [rsp+50h] [rbp-B0h] BYREF
  void *clientProcessHandle; // [rsp+58h] [rbp-A8h] BYREF
  _SECURITY_CAPABILITIES securityCapabilities; // [rsp+60h] [rbp-A0h] BYREF
  _PROCESS_INFORMATION pi; // [rsp+78h] [rbp-88h] BYREF
  _STARTUPINFOEXW lpStartupInfo; // [rsp+90h] [rbp-70h] BYREF
  wchar_t commandLine[520]; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&lpStartupInfo.StartupInfo.cb = 0;
  memset_0(&lpStartupInfo.StartupInfo.lpReserved, 0, 0x68u);
  attributesLength = 0;
  *(_QWORD *)&securityCapabilities.CapabilityCount = 0;
  clientProcessHandle = 0;
  memset(&pi, 0, sizeof(pi));
  *processHandle = 0;
  *(_OWORD *)&securityCapabilities.AppContainerSid = 0;
  if ( !InitializeProcThreadAttributeList(0, 2u, 0, &attributesLength) && GetLastError() != 122 )
  {
    v11 = -2147467259;
    goto LABEL_37;
  }
  v12 = (_PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0x40u, attributesLength);
  v13 = v12;
  if ( !v12 )
  {
    v11 = -2147024882;
    goto LABEL_37;
  }
  if ( !InitializeProcThreadAttributeList(v12, 2u, 0, &attributesLength) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_36;
  }
  securityCapabilities.AppContainerSid = appContainerSid;
  securityCapabilities.CapabilityCount = capabilityCount;
  securityCapabilities.Capabilities = capabilities;
  securityCapabilities.Reserved = 0;
  if ( !UpdateProcThreadAttribute(v13, 0, 0x20009u, &securityCapabilities, 0x18u, 0, 0) )
    goto LABEL_10;
  if ( clientProcessId )
  {
    clientProcessHandle = OpenProcess(0x1004C0u, 0, clientProcessId);
    if ( !clientProcessHandle )
    {
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_35;
      }
      v18 = 70;
      goto LABEL_20;
    }
    if ( !UpdateProcThreadAttribute(v13, 0, 0x20000u, &clientProcessHandle, 8u, 0, 0) )
    {
LABEL_10:
      v15 = GetLastError();
      v11 = v15;
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_35;
    }
  }
  lpStartupInfo.StartupInfo.cb = 112;
  lpStartupInfo.lpAttributeList = v13;
  v11 = StringCchCopyW(commandLine, 0x208u, applicationName);
  if ( v11 >= 0 )
  {
    v11 = StringCchCatW(commandLine, 0x208u, L" ");
    if ( v11 >= 0 )
    {
      v11 = StringCchCatW(commandLine, 0x208u, commandLineArg);
      if ( v11 >= 0 )
      {
        if ( CreateProcessW(0, commandLine, 0, 0, 0, 0x80000u, 0, 0, &lpStartupInfo.StartupInfo, &pi) )
        {
          hThread = pi.hThread;
          *processHandle = pi.hProcess;
          if ( hThread )
            CloseHandle(hThread);
          v11 = 0;
          goto LABEL_35;
        }
        v19 = GetLastError();
        v11 = v19;
        if ( v19 > 0 )
          v11 = (unsigned __int16)v19 | 0x80070000;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          v18 = 71;
LABEL_20:
          WPP_SF_d(v17[1].Control.Logger, v18, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v11);
        }
      }
    }
  }
LABEL_35:
  DeleteProcThreadAttributeList(v13);
LABEL_36:
  LocalFree(v13);
LABEL_37:
  if ( clientProcessHandle )
    CloseHandle(clientProcessHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001009c  push    rbp
0x18001009e  push    rbx
0x18001009f  push    rsi
0x1800100a0  push    rdi
0x1800100a1  push    r12
0x1800100a3  push    r13
0x1800100a5  push    r14
0x1800100a7  push    r15
0x1800100a9  lea     rbp, [rsp-428h]
0x1800100b1  sub     rsp, 528h
0x1800100b8  mov     rax, cs:__security_cookie
0x1800100bf  xor     rax, rsp
0x1800100c2  mov     [rbp+460h+var_50], rax
0x1800100c9  mov     ebx, [rbp+460h+dwProcessId]
0x1800100cf  mov     r13, commandLineArg
0x1800100d2  mov     rsi, [rbp+460h+arg_30]
0x1800100d9  xor     edx, edx; Val
0x1800100db  mov     r14, appContainerSid
0x1800100de  mov     qword ptr [rbp+460h+var_4D0.StartupInfo.cb], 0
0x1800100e6  mov     r12, applicationName
0x1800100e9  mov     r15, capabilities
0x1800100ec  lea     applicationName, [rbp+460h+var_4D0.StartupInfo.lpReserved]; void *
0x1800100f0  lea     r8d, [commandLineArg+68h]; Size
0x1800100f4  call    memset_0
0x1800100f9  xor     eax, eax
0x1800100fb  lea     capabilities, [rsp+560h+attributesLength]; lpSize
0x180010100  xorps   xmm0, xmm0
0x180010103  mov     qword ptr [rbp+460h+pi.dwProcessId], rax
0x180010107  xor     r8d, r8d; dwFlags
0x18001010a  mov     [rsp+560h+attributesLength], rax
0x18001010f  xor     ecx, ecx; lpAttributeList
0x180010111  mov     qword ptr [rsp+560h+securityCapabilities.CapabilityCount], rax
0x180010116  lea     edx, [rax+2]; dwAttributeCount
0x180010119  mov     [rsp+560h+clientProcessHandle], rax
0x18001011e  movups  xmmword ptr [rsp+560h+pi.hProcess], xmm0
0x180010123  mov     [rsi], rax
0x180010126  movups  xmmword ptr [rsp+560h+securityCapabilities.AppContainerSid], xmm0
0x18001012b  call    cs:__imp_InitializeProcThreadAttributeList
0x180010131  test    eax, eax
0x180010133  jnz     short loc_18001014A
0x180010135  call    cs:__imp_GetLastError
0x18001013b  cmp     eax, 7Ah ; 'z'
0x18001013e  jz      short loc_18001014A
0x180010140  mov     ebx, 80004005h
0x180010145  jmp     loc_1800103C4
0x18001014a  mov     commandLineArg, [rsp+560h+attributesLength]; uBytes
0x18001014f  mov     ecx, 40h ; '@'; uFlags
0x180010154  call    cs:__imp_LocalAlloc
0x18001015a  mov     rdi, rax
0x18001015d  test    rax, rax
0x180010160  jnz     short loc_18001016C
0x180010162  mov     ebx, 8007000Eh
0x180010167  jmp     loc_1800103C4
0x18001016c  xor     r8d, r8d; dwFlags
0x18001016f  lea     capabilities, [rsp+560h+attributesLength]; lpSize
0x180010174  mov     applicationName, rdi; lpAttributeList
0x180010177  lea     edx, [appContainerSid+2]; dwAttributeCount
0x18001017b  call    cs:__imp_InitializeProcThreadAttributeList
0x180010181  test    eax, eax
0x180010183  jnz     short loc_1800101A3
0x180010185  call    cs:__imp_GetLastError
0x18001018b  mov     ebx, eax
0x18001018d  test    eax, eax
0x18001018f  jle     loc_1800103BB
0x180010195  movzx   ebx, ax
0x180010198  or      ebx, 80070000h
0x18001019e  jmp     loc_1800103BB
0x1800101a3  mov     eax, [rbp+460h+arg_20]
0x1800101a9  lea     capabilities, [rsp+560h+securityCapabilities]; lpValue
0x1800101ae  mov     [rsp+560h+securityCapabilities.AppContainerSid], r14
0x1800101b3  xor     edx, edx; dwFlags
0x1800101b5  xor     r14d, r14d
0x1800101b8  mov     [rsp+560h+securityCapabilities.CapabilityCount], eax
0x1800101bc  mov     [rsp+560h+lpReturnSize], r14; lpReturnSize
0x1800101c1  mov     r8d, 20009h; Attribute
0x1800101c7  mov     [rsp+560h+lpPreviousValue], r14; lpPreviousValue
0x1800101cc  mov     applicationName, rdi; lpAttributeList
0x1800101cf  mov     [rsp+560h+cbSize], 18h; cbSize
0x1800101d8  mov     [rsp+560h+securityCapabilities.Capabilities], r15
0x1800101dd  mov     [rsp+560h+securityCapabilities.Reserved], r14d
0x1800101e2  call    cs:__imp_UpdateProcThreadAttribute
0x1800101e8  test    eax, eax
0x1800101ea  jnz     short loc_18001020A
0x1800101ec  call    cs:__imp_GetLastError
0x1800101f2  mov     ebx, eax
0x1800101f4  test    eax, eax
0x1800101f6  jle     loc_1800103B2
0x1800101fc  movzx   ebx, ax
0x1800101ff  or      ebx, 80070000h
0x180010205  jmp     loc_1800103B2
0x18001020a  test    ebx, ebx
0x18001020c  jz      loc_1800102BA
0x180010212  mov     r8d, ebx; dwProcessId
0x180010215  xor     edx, edx; bInheritHandle
0x180010217  mov     ecx, 1004C0h; dwDesiredAccess
0x18001021c  call    cs:__imp_OpenProcess
0x180010222  mov     [rsp+560h+clientProcessHandle], rax
0x180010227  test    rax, rax
0x18001022a  jnz     short loc_180010289
0x18001022c  call    cs:__imp_GetLastError
0x180010232  mov     ebx, eax
0x180010234  test    eax, eax
0x180010236  jle     short loc_180010241
0x180010238  movzx   ebx, ax
0x18001023b  or      ebx, 80070000h
0x180010241  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010248  lea     rax, WPP_GLOBAL_Control
0x18001024f  cmp     applicationName, rax
0x180010252  jz      loc_1800103B2
0x180010258  test    byte ptr [applicationName+44h], 10h
0x18001025c  jz      loc_1800103B2
0x180010262  cmp     byte ptr [applicationName+41h], 2
0x180010266  jb      loc_1800103B2
0x18001026c  mov     edx, 46h ; 'F'; id
0x180010271  mov     applicationName, [applicationName+38h]; Logger
0x180010275  lea     appContainerSid, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18001027c  mov     r9d, ebx; _a1
0x18001027f  call    WPP_SF_d
0x180010284  jmp     loc_1800103B2
0x180010289  mov     [rsp+560h+lpReturnSize], r14; lpReturnSize
0x18001028e  lea     capabilities, [rsp+560h+clientProcessHandle]; lpValue
0x180010293  mov     [rsp+560h+lpPreviousValue], r14; lpPreviousValue
0x180010298  xor     edx, edx; dwFlags
0x18001029a  mov     r8d, 20000h; Attribute
0x1800102a0  mov     [rsp+560h+cbSize], 8; cbSize
0x1800102a9  mov     applicationName, rdi; lpAttributeList
0x1800102ac  call    cs:__imp_UpdateProcThreadAttribute
0x1800102b2  test    eax, eax
0x1800102b4  jz      loc_1800101EC
0x1800102ba  mov     r15d, 208h
0x1800102c0  mov     [rbp+460h+var_4D0.StartupInfo.cb], 70h ; 'p'
0x1800102c7  mov     edx, r15d; cchDest
0x1800102ca  mov     [rbp+460h+var_4D0.lpAttributeList], rdi
0x1800102ce  mov     appContainerSid, r12; pszSrc
0x1800102d1  lea     applicationName, [rbp+460h+commandLine]; pszDest
0x1800102d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800102da  mov     ebx, eax
0x1800102dc  test    eax, eax
0x1800102de  js      loc_1800103B2
0x1800102e4  lea     appContainerSid, asc_180028D00; " "
0x1800102eb  mov     edx, r15d; cchDest
0x1800102ee  lea     applicationName, [rbp+460h+commandLine]; pszDest
0x1800102f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800102f7  mov     ebx, eax
0x1800102f9  test    eax, eax
0x1800102fb  js      loc_1800103B2
0x180010301  mov     appContainerSid, r13; pszSrc
0x180010304  lea     applicationName, [rbp+460h+commandLine]; pszDest
0x180010308  mov     edx, r15d; cchDest
0x18001030b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010310  mov     ebx, eax
0x180010312  test    eax, eax
0x180010314  js      loc_1800103B2
0x18001031a  lea     rax, [rsp+560h+pi]
0x18001031f  xor     r9d, r9d; lpThreadAttributes
0x180010322  mov     [rsp+560h+lpProcessInformation], rax; lpProcessInformation
0x180010327  lea     commandLineArg, [rbp+460h+commandLine]; lpCommandLine
0x18001032b  lea     rax, [rbp+460h+var_4D0]
0x18001032f  xor     r8d, r8d; lpProcessAttributes
0x180010332  mov     [rsp+560h+lpStartupInfo], rax; lpStartupInfo
0x180010337  xor     ecx, ecx; lpApplicationName
0x180010339  mov     [rsp+560h+lpCurrentDirectory], r14; lpCurrentDirectory
0x18001033e  mov     [rsp+560h+lpReturnSize], r14; lpEnvironment
0x180010343  mov     dword ptr [rsp+560h+lpPreviousValue], 80000h; dwCreationFlags
0x18001034b  mov     dword ptr [rsp+560h+cbSize], r14d; bInheritHandles
0x180010350  call    cs:__imp_CreateProcessW
0x180010356  test    eax, eax
0x180010358  jnz     short loc_180010398
0x18001035a  call    cs:__imp_GetLastError
0x180010360  mov     ebx, eax
0x180010362  test    eax, eax
0x180010364  jle     short loc_18001036F
0x180010366  movzx   ebx, ax
0x180010369  or      ebx, 80070000h
0x18001036f  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180010376  lea     rax, WPP_GLOBAL_Control
0x18001037d  cmp     applicationName, rax
0x180010380  jz      short loc_1800103B2
0x180010382  test    byte ptr [applicationName+44h], 10h
0x180010386  jz      short loc_1800103B2
0x180010388  cmp     byte ptr [applicationName+41h], 2
0x18001038c  jb      short loc_1800103B2
0x18001038e  mov     edx, 47h ; 'G'
0x180010393  jmp     loc_180010271
0x180010398  mov     applicationName, [rbp+460h+pi.hThread]; hObject
0x18001039c  mov     rax, [rsp+560h+pi.hProcess]
0x1800103a1  mov     [rsi], rax
0x1800103a4  test    applicationName, applicationName
0x1800103a7  jz      short loc_1800103AF
0x1800103a9  call    cs:__imp_CloseHandle
0x1800103af  mov     ebx, r14d
0x1800103b2  mov     applicationName, rdi; lpAttributeList
0x1800103b5  call    cs:__imp_DeleteProcThreadAttributeList
0x1800103bb  mov     applicationName, rdi; hMem
0x1800103be  call    cs:__imp_LocalFree
0x1800103c4  mov     applicationName, [rsp+560h+clientProcessHandle]; hObject
0x1800103c9  test    applicationName, applicationName
0x1800103cc  jz      short loc_1800103D4
0x1800103ce  call    cs:__imp_CloseHandle
0x1800103d4  mov     eax, ebx
0x1800103d6  mov     applicationName, [rbp+460h+var_50]
0x1800103dd  xor     applicationName, rsp; StackCookie
0x1800103e0  call    __security_check_cookie
0x1800103e5  add     rsp, 528h
0x1800103ec  pop     r15
0x1800103ee  pop     r14
0x1800103f0  pop     r13
0x1800103f2  pop     r12
0x1800103f4  pop     rdi
0x1800103f5  pop     rsi
0x1800103f6  pop     rbx
0x1800103f7  pop     rbp
0x1800103f8  retn
```
