# UnhandledExceptionFilter

- ea: `0x180117b10`
- end: `0x1801180a9`
- name: `UnhandledExceptionFilter`
- size: `1433`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1800fe5c0`

## callees

- `0x1800145c0`
- `0x1800147a0`
- `0x18007dd40`
- `0x18007de08`
- `0x18007e804`
- `0x1800ae1a0`
- `0x1800b7130`
- `0x1800e5a34`
- `0x1800fac80`
- `0x180104c70`
- `0x180117b10`
- `0x180126f38`
- `0x18012d080`
- `0x18012d119`
- `0x18012feb0`
- `0x180182c0c`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180117cdc`
- `ntdll!RtlEqualUnicodeString` at `0x180117cdc`
- `ntdll!NtSetInformationProcess` at `0x180117c34`
- `ntdll!NtSetInformationProcess` at `0x180117d7c`
- `ntdll!NtSetInformationProcess` at `0x180117c34`
- `ntdll!NtSetInformationProcess` at `0x180117d7c`
- `ntdll!NtTerminateProcess` at `0x18011807b`
- `ntdll!NtTerminateProcess` at `0x18011807b`
- `ntdll!RtlDecodePointer` at `0x180117c5d`
- `ntdll!RtlDecodePointer` at `0x180117c5d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180117c44`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180117c44`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180117ce9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180117d49`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180117ce9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180117d49`
- `ntdll!RtlGetThreadErrorMode` at `0x180117d97`
- `ntdll!RtlGetThreadErrorMode` at `0x180117d97`
- `ntdll!NtRaiseHardError` at `0x180117ff2`
- `ntdll!NtRaiseHardError` at `0x180117ff2`
- `ntdll!RtlKnownExceptionFilter` at `0x180117c0c`
- `ntdll!RtlKnownExceptionFilter` at `0x180117d52`
- `ntdll!RtlKnownExceptionFilter` at `0x180117c0c`
- `ntdll!RtlKnownExceptionFilter` at `0x180117d52`
- `ntdll!NtQueryInformationJobObject` at `0x180117dbb`
- `ntdll!NtQueryInformationJobObject` at `0x180117dbb`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!BasepReportFault` at `0x180117e2d`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!BasepReportFault` at `0x180117e2d`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!CheckForReadOnlyResourceFilter` at `0x180117be5`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!CheckForReadOnlyResourceFilter` at `0x180117be5`

## string_xrefs

- `0x180117df4`: `ext-ms-win-kernel32-errorhandling-l1-1-0.dll`

## pseudocode

```c
LONG __stdcall UnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  struct _EXCEPTION_POINTERS *v3; // r12
  int v4; // eax
  __int64 (__fastcall *v5)(struct _EXCEPTION_POINTERS *); // rax
  __int64 (__fastcall *v6)(struct _EXCEPTION_POINTERS *); // rdi
  int v7; // eax
  LONG v8; // esi
  LONG result; // eax
  int v10; // r14d
  int v11; // edi
  HMODULE Library; // r12
  ULONG LastErrorValue; // ecx
  _WORD *v14; // rdi
  _DWORD *v15; // rax
  __int64 v16; // rcx
  NTSTATUS *ExceptionRecord; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  ULONG v20; // eax
  int v21; // r14d
  ULONG Response; // [rsp+38h] [rbp-D0h] BYREF
  __int64 ProcessInformation; // [rsp+40h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-C0h]
  int v26; // [rsp+4Ch] [rbp-BCh]
  struct _EXCEPTION_POINTERS *v27; // [rsp+50h] [rbp-B8h]
  ULONG v28; // [rsp+60h] [rbp-A8h]
  ULONG v29; // [rsp+64h] [rbp-A4h]
  HMODULE v30; // [rsp+68h] [rbp-A0h]
  _BYTE JobInformation[16]; // [rsp+70h] [rbp-98h] BYREF
  int v32; // [rsp+80h] [rbp-88h]
  unsigned __int64 Parameters[4]; // [rsp+B0h] [rbp-58h] BYREF

  v27 = ExceptionInfo;
  v26 = 4;
  Response = 6;
  memset_0(JobInformation, 0, 0x40u);
  ProcessInformation = 0;
  if ( (ExceptionInfo->ExceptionRecord->ExceptionFlags & 0x10) != 0 )
    return 0;
  if ( ExceptionInfo->ExceptionRecord->ExceptionCode == -1073740791
    && ((unsigned int)BasepIsKernelDebuggerPresent() || (unsigned int)BasepIsDebugPortPresent()) )
  {
    DbgPrint_0("\r\nSTATUS_STACK_BUFFER_OVERRUN encountered\r\n");
    __debugbreak();
  }
  v3 = ExceptionInfo;
  if ( !(unsigned __int8)IsBasepReportFaultPresent() || BasepIsSecureProcess )
    v4 = 0;
  else
    v4 = CheckForReadOnlyResourceFilter(ExceptionInfo);
  if ( v4 == -1 )
    return -1;
  if ( (unsigned int)BasepIsDebugPortPresent() )
    return 0;
  if ( (unsigned int)RtlKnownExceptionFilter(ExceptionInfo) != -1 )
  {
    ProcessInformation = 8;
    NtSetInformationProcess(
      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
      MaxProcessInfoClass|ProcessUserModeIOPL,
      &ProcessInformation,
      8u);
  }
  RtlAcquireSRWLockExclusive(&BasepUEFLock);
  if ( BasepIsSecureProcess
    || (v5 = (__int64 (__fastcall *)(struct _EXCEPTION_POINTERS *))RtlDecodePointer(BasepCurrentTopLevelFilter),
        (v6 = v5) == 0)
    || !(unsigned int)BasepFillUEFInfo(v5)
    || *(_QWORD *)BasepFilterInfo != *((_QWORD *)BasepFilterInfo + 71)
    || *((_QWORD *)BasepFilterInfo + 1) != *((_QWORD *)BasepFilterInfo + 72)
    || (v7 = *((_DWORD *)BasepFilterInfo + 4), v7 != *((_DWORD *)BasepFilterInfo + 146)) )
  {
    v8 = 1;
LABEL_28:
    RtlReleaseSRWLockExclusive(&BasepUEFLock);
    goto LABEL_29;
  }
  v8 = 1;
  if ( (v7 & 0x1040000) != 0
    && !RtlEqualUnicodeString(
          (PCUNICODE_STRING)((char *)BasepFilterInfo + 24),
          (PCUNICODE_STRING)BasepFilterInfo + 37,
          1u) )
  {
    goto LABEL_28;
  }
  RtlReleaseSRWLockExclusive(&BasepUEFLock);
  result = v6(ExceptionInfo);
  if ( ((result + 1) & 0xFFFFFFFD) == 0 )
    return result;
  if ( result || !(unsigned int)BasepIsDebugPortPresent() )
  {
LABEL_29:
    if ( (unsigned int)RtlKnownExceptionFilter(ExceptionInfo) != -1 )
    {
      ProcessInformation = 1;
      NtSetInformationProcess(
        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
        MaxProcessInfoClass|ProcessUserModeIOPL,
        &ProcessInformation,
        8u);
      if ( BasepIsSecureProcess )
        return 0;
      if ( (GetErrorMode() & 2) != 0
        || (RtlGetThreadErrorMode() & 0x20) != 0
        || NtQueryInformationJobObject(0, JobObjectBasicLimitInformation, JobInformation, 0x40u, 0) >= 0
        && (v32 & 0x400) != 0 )
      {
        return v8;
      }
      v10 = 4;
      if ( (unsigned __int8)IsBasepReportFaultPresent() )
      {
        v11 = 0;
        v25 = 0;
        Library = LoadLibraryExW(L"ext-ms-win-kernel32-errorhandling-l1-1-0.dll", 0, 0);
        v30 = Library;
        LastErrorValue = 0;
        if ( !Library )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v28 = LastErrorValue;
          v29 = LastErrorValue;
        }
        if ( !LastErrorValue || LastErrorValue == 126 )
        {
          v10 = BasepReportFault(ExceptionInfo, 1);
          v26 = v10;
          v11 = 1;
          v25 = 1;
        }
        if ( Library )
          FreeLibrary(Library);
        if ( (unsigned int)(v10 - 9) <= 1 || v10 == 3 || !v11 )
          RaiseFailFastException(ExceptionInfo->ExceptionRecord, ExceptionInfo->ContextRecord, 0);
        v3 = ExceptionInfo;
      }
      if ( v10 == 8 || v10 == 6 && (unsigned int)BasepIsDebugPortPresent() )
        return 0;
      v14 = 0;
      if ( v10 != 4 )
        goto LABEL_84;
      v15 = VirtualAllocExNuma((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x250u, 0x1000u, 4u, 0xFFFFFFFF);
      v14 = v15;
      if ( !v15 )
        return 0;
      *v15 &= ~1u;
      if ( (unsigned __int8)IsBasepReportFaultPresent() && ((int)WerpGetDebugger(v16, v14) < 0 || !v14[2]) )
        *(_DWORD *)v14 &= ~1u;
      if ( (*(_BYTE *)v14 & 2) != 0 )
      {
LABEL_74:
        if ( (*(_BYTE *)v14 & 1) != 0 && (Response == 3 || (*(_BYTE *)v14 & 2) != 0) )
        {
          if ( BasepAlreadyHadHardError )
          {
LABEL_85:
            NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3->ExceptionRecord->ExceptionCode);
LABEL_86:
            if ( v14 )
              VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v14, 0, 0x8000u);
            return v8;
          }
          if ( !byte_1803A2DC4 )
          {
            v21 = -2147467259;
            if ( (unsigned __int8)IsBasepReportFaultPresent() )
              v21 = WerpLaunchAeDebug(
                      -1,
                      -2,
                      (__int64)v3->ExceptionRecord,
                      &ExceptionInfo->ContextRecord->P1Home,
                      (ULONG_PTR)v14);
            if ( v21 < 0 )
              BasepAlreadyHadHardError = 1;
            v8 = 0;
            goto LABEL_86;
          }
        }
LABEL_84:
        if ( !BasepAlreadyHadHardError )
          goto LABEL_86;
        goto LABEL_85;
      }
      ExceptionRecord = (NTSTATUS *)v3->ExceptionRecord;
      Parameters[0] = v3->ExceptionRecord->ExceptionCode;
      Parameters[1] = *((_QWORD *)ExceptionRecord + 2);
      if ( *ExceptionRecord == -1073741818 )
      {
        if ( (unsigned int)ExceptionRecord[6] >= 3 )
        {
          v18 = *((_QWORD *)ExceptionRecord + 6);
LABEL_64:
          Parameters[2] = v18;
          if ( (unsigned int)ExceptionRecord[6] < 2 )
            v19 = 0;
          else
            v19 = *((_QWORD *)ExceptionRecord + 5);
          Parameters[3] = v19;
          if ( (NtCurrentPeb()->NtGlobalFlag & 0x20000000) != 0 )
          {
            DbgPrint_0("\r\nUnhandled exception encountered\r\n");
            __debugbreak();
          }
          if ( (*(_BYTE *)v14 & 1) == 0 || (v20 = 2, BasepAlreadyHadHardError) )
            v20 = 1;
          if ( (NtRaiseHardError(-805306044, 4u, 0, Parameters, v20, &Response) & 0xC0000000) == 0xC0000000 )
            Response = 6;
          goto LABEL_74;
        }
      }
      else if ( ExceptionRecord[6] )
      {
        v18 = *((_QWORD *)ExceptionRecord + 4);
        goto LABEL_64;
      }
      v18 = 0;
      goto LABEL_64;
    }
    return -1;
  }
  return 0;
}

```

## disassembly

```asm
0x180117b10  mov     [rsp+arg_8], rbx
0x180117b15  mov     [rsp+arg_10], rsi
0x180117b1a  push    rdi
0x180117b1b  push    r12
0x180117b1d  push    r13
0x180117b1f  push    r14
0x180117b21  push    r15
0x180117b23  sub     rsp, 0E0h
0x180117b2a  mov     rax, cs:__security_cookie
0x180117b31  xor     rax, rsp
0x180117b34  mov     [rsp+108h+var_38], rax
0x180117b3c  mov     rdi, rcx
0x180117b3f  mov     [rsp+108h+var_D8], rcx
0x180117b44  mov     r13, rcx
0x180117b47  mov     [rsp+108h+var_B8], rcx
0x180117b4c  mov     [rsp+108h+var_BC], 4
0x180117b54  mov     [rsp+108h+Response], 6
0x180117b5c  xor     edx, edx; Val
0x180117b5e  lea     r8d, [rdx+40h]; Size
0x180117b62  lea     rcx, [rsp+108h+JobInformation]; void *
0x180117b67  call    memset_0
0x180117b6c  xor     ebx, ebx
0x180117b6e  mov     [rsp+108h+ProcessInformation], rbx
0x180117b73  mov     rax, [r13+0]
0x180117b77  test    byte ptr [rax+4], 10h
0x180117b7b  jnz     loc_180117D12
0x180117b81  cmp     dword ptr [rax], 0C0000409h
0x180117b87  jnz     short loc_180117BCE
0x180117b89  call    BasepIsKernelDebuggerPresent
0x180117b8e  test    eax, eax
0x180117b90  jnz     short loc_180117B9B
0x180117b92  call    BasepIsDebugPortPresent
0x180117b97  test    eax, eax
0x180117b99  jz      short loc_180117BCE
0x180117b9b  lea     rcx, aStatusStackBuf; "\r\nSTATUS_STACK_BUFFER_OVERRUN encount"...
0x180117ba2  call    DbgPrint_0
0x180117ba7  int     3; Trap to Debugger
0x180117ba8  mov     r12, [rsp+108h+var_D8]
0x180117bad  jmp     short loc_180117BD1
0x180117baf  mov     edx, 0C0000409h; uExitCode
0x180117bb4  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x180117bb8  call    TerminateProcess
0x180117bbd  xor     ebx, ebx
0x180117bbf  mov     r13, [rsp+108h+var_B8]
0x180117bc4  mov     r12, r13
0x180117bc7  mov     [rsp+108h+var_D8], r13
0x180117bcc  jmp     short loc_180117BD1
0x180117bce  mov     r12, rdi
0x180117bd1  call    IsBasepReportFaultPresent
0x180117bd6  test    al, al
0x180117bd8  jz      short loc_180117BED
0x180117bda  cmp     cs:BasepIsSecureProcess, bl
0x180117be0  jnz     short loc_180117BED
0x180117be2  mov     rcx, r13
0x180117be5  call    cs:__imp_CheckForReadOnlyResourceFilter
0x180117beb  jmp     short loc_180117BEF
0x180117bed  mov     eax, ebx
0x180117bef  or      r15, 0FFFFFFFFFFFFFFFFh
0x180117bf3  cmp     eax, r15d
0x180117bf6  jz      loc_1801180A1
0x180117bfc  call    BasepIsDebugPortPresent
0x180117c01  test    eax, eax
0x180117c03  jnz     loc_180117D12
0x180117c09  mov     rcx, r13
0x180117c0c  call    cs:__imp_RtlKnownExceptionFilter
0x180117c12  cmp     eax, r15d
0x180117c15  jz      short loc_180117C3A
0x180117c17  mov     [rsp+108h+ProcessInformation], rbx
0x180117c1c  mov     dword ptr [rsp+108h+ProcessInformation], 8
0x180117c24  lea     r9d, [r15+9]; ProcessInformationLength
0x180117c28  lea     r8, [rsp+108h+ProcessInformation]; ProcessInformation
0x180117c2d  lea     edx, [r15+40h]; ProcessInformationClass
0x180117c31  mov     rcx, r15; ProcessHandle
0x180117c34  call    cs:__imp_NtSetInformationProcess
0x180117c3a  lea     r14, BasepUEFLock
0x180117c41  mov     rcx, r14
0x180117c44  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180117c4a  cmp     cs:BasepIsSecureProcess, bl
0x180117c50  jnz     loc_180117D41
0x180117c56  mov     rcx, cs:BasepCurrentTopLevelFilter; Pointer
0x180117c5d  call    cs:__imp_RtlDecodePointer
0x180117c63  mov     rdi, rax
0x180117c66  test    rax, rax
0x180117c69  jz      loc_180117D41
0x180117c6f  mov     rdx, cs:BasepFilterInfo
0x180117c76  add     rdx, 238h
0x180117c7d  mov     rcx, rax; Address
0x180117c80  call    BasepFillUEFInfo
0x180117c85  test    eax, eax
0x180117c87  jz      loc_180117D41
0x180117c8d  mov     r8, cs:BasepFilterInfo
0x180117c94  mov     rcx, [r8+238h]
0x180117c9b  cmp     [r8], rcx
0x180117c9e  jnz     loc_180117D41
0x180117ca4  mov     rax, [r8+240h]
0x180117cab  cmp     [r8+8], rax
0x180117caf  jnz     loc_180117D41
0x180117cb5  mov     eax, [r8+10h]
0x180117cb9  cmp     eax, [r8+248h]
0x180117cc0  jnz     short loc_180117D41
0x180117cc2  mov     esi, 1
0x180117cc7  test    eax, 1040000h
0x180117ccc  jz      short loc_180117CE6
0x180117cce  lea     rdx, [r8+250h]; String2
0x180117cd5  lea     rcx, [r8+18h]; String1
0x180117cd9  mov     r8b, sil; CaseInsensitive
0x180117cdc  call    cs:__imp_RtlEqualUnicodeString
0x180117ce2  test    al, al
0x180117ce4  jz      short loc_180117D46
0x180117ce6  mov     rcx, r14
0x180117ce9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180117cef  mov     rcx, r13
0x180117cf2  mov     rax, rdi
0x180117cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117cfa  lea     ecx, [rax+1]
0x180117cfd  test    ecx, 0FFFFFFFDh
0x180117d03  jz      short loc_180117D14
0x180117d05  test    eax, eax
0x180117d07  jnz     short loc_180117D4F
0x180117d09  call    BasepIsDebugPortPresent
0x180117d0e  test    eax, eax
0x180117d10  jz      short loc_180117D4F
0x180117d12  xor     eax, eax
0x180117d14  mov     rcx, [rsp+108h+var_38]
0x180117d1c  xor     rcx, rsp; StackCookie
0x180117d1f  call    __security_check_cookie
0x180117d24  lea     r11, [rsp+108h+var_28]
0x180117d2c  mov     rbx, [r11+38h]
0x180117d30  mov     rsi, [r11+40h]
0x180117d34  mov     rsp, r11
0x180117d37  pop     r15
0x180117d39  pop     r14
0x180117d3b  pop     r13
0x180117d3d  pop     r12
0x180117d3f  pop     rdi
0x180117d40  retn
0x180117d41  mov     esi, 1
0x180117d46  mov     rcx, r14
0x180117d49  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180117d4f  mov     rcx, r13
0x180117d52  call    cs:__imp_RtlKnownExceptionFilter
0x180117d58  cmp     eax, r15d
0x180117d5b  jz      loc_1801180A1
0x180117d61  mov     [rsp+108h+ProcessInformation], rbx
0x180117d66  mov     dword ptr [rsp+108h+ProcessInformation], esi
0x180117d6a  mov     r9d, 8; ProcessInformationLength
0x180117d70  lea     r8, [rsp+108h+ProcessInformation]; ProcessInformation
0x180117d75  lea     edx, [r9+37h]; ProcessInformationClass
0x180117d79  mov     rcx, r15; ProcessHandle
0x180117d7c  call    cs:__imp_NtSetInformationProcess
0x180117d82  cmp     cs:BasepIsSecureProcess, bl
0x180117d88  jnz     short loc_180117D12
0x180117d8a  call    GetErrorMode
0x180117d8f  test    al, 2
0x180117d91  jnz     loc_18011809A
0x180117d97  call    cs:__imp_RtlGetThreadErrorMode
0x180117d9d  test    al, 20h
0x180117d9f  jnz     loc_18011809A
0x180117da5  mov     [rsp+108h+ReturnLength], rbx; ReturnLength
0x180117daa  mov     r9d, 40h ; '@'; JobInformationLength
0x180117db0  lea     r8, [rsp+108h+JobInformation]; JobInformation
0x180117db5  lea     edx, [r9-3Eh]; JobInformationClass
0x180117db9  xor     ecx, ecx; JobHandle
0x180117dbb  call    cs:__imp_NtQueryInformationJobObject
0x180117dc1  test    eax, eax
0x180117dc3  js      short loc_180117DD6
0x180117dc5  test    [rsp+108h+var_88], 400h
0x180117dd0  jnz     loc_18011809A
0x180117dd6  mov     r14d, 4
0x180117ddc  call    IsBasepReportFaultPresent
0x180117de1  test    al, al
0x180117de3  jz      loc_180117E98
0x180117de9  mov     edi, ebx
0x180117deb  mov     [rsp+108h+var_C0], ebx
0x180117def  xor     r8d, r8d; dwFlags
0x180117df2  xor     edx, edx; hFile
0x180117df4  lea     rcx, aExtMsWinKernel_21; "ext-ms-win-kernel32-errorhandling-l1-1-"...
0x180117dfb  call    LoadLibraryExW
0x180117e00  mov     r12, rax
0x180117e03  mov     [rsp+108h+var_A0], rax
0x180117e08  mov     ecx, ebx
0x180117e0a  test    rax, rax
0x180117e0d  jnz     short loc_180117E1F
0x180117e0f  mov     ecx, gs:68h
0x180117e17  mov     [rsp+108h+var_A8], ecx
0x180117e1b  mov     [rsp+108h+var_A4], ecx
0x180117e1f  test    ecx, ecx
0x180117e21  jz      short loc_180117E28
0x180117e23  cmp     ecx, 7Eh ; '~'
0x180117e26  jnz     short loc_180117E40
0x180117e28  mov     edx, esi
0x180117e2a  mov     rcx, r13
0x180117e2d  call    cs:__imp_BasepReportFault
0x180117e33  mov     r14d, eax
0x180117e36  mov     [rsp+108h+var_BC], eax
0x180117e3a  mov     edi, esi
0x180117e3c  mov     [rsp+108h+var_C0], esi
0x180117e40  test    r12, r12
0x180117e43  jz      short loc_180117E4D
0x180117e45  mov     rcx, r12; hLibModule
0x180117e48  call    FreeLibrary
0x180117e4d  mov     rcx, [rsp+108h+var_D8]
0x180117e52  jmp     short loc_180117E72
0x180117e54  xor     ebx, ebx
0x180117e56  lea     r14d, [rbx+0Ah]
0x180117e5a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180117e5e  lea     esi, [rbx+1]
0x180117e61  mov     edi, [rsp+108h+var_C0]
0x180117e65  mov     r13, [rsp+108h+var_B8]
0x180117e6a  mov     rcx, r13
0x180117e6d  mov     [rsp+108h+var_D8], rcx
0x180117e72  lea     eax, [r14-9]
0x180117e76  cmp     eax, esi
0x180117e78  jbe     short loc_180117E84
0x180117e7a  cmp     r14d, 3
0x180117e7e  jz      short loc_180117E84
0x180117e80  test    edi, edi
0x180117e82  jnz     short loc_180117E93
0x180117e84  xor     r8d, r8d; dwFlags
0x180117e87  mov     rdx, [r13+8]; pContextRecord
0x180117e8b  mov     rcx, [rcx]; pExceptionRecord
0x180117e8e  call    RaiseFailFastException
0x180117e93  mov     r12, [rsp+108h+var_D8]
0x180117e98  cmp     r14d, 8
0x180117e9c  jz      loc_180117D12
0x180117ea2  cmp     r14d, 6
0x180117ea6  jnz     short loc_180117EB5
0x180117ea8  call    BasepIsDebugPortPresent
0x180117ead  test    eax, eax
0x180117eaf  jnz     loc_180117D12
0x180117eb5  mov     rdi, rbx
0x180117eb8  cmp     r14d, 4
0x180117ebc  jnz     loc_18011806A
0x180117ec2  mov     [rsp+108h+nndPreferred], 0FFFFFFFFh; nndPreferred
0x180117eca  mov     dword ptr [rsp+108h+ReturnLength], r14d; flProtect
0x180117ecf  xor     edx, edx; lpAddress
0x180117ed1  mov     r9d, 1000h; flAllocationType
0x180117ed7  mov     r8d, 250h; dwSize
0x180117edd  mov     rcx, r15; hProcess
0x180117ee0  call    VirtualAllocExNuma
0x180117ee5  mov     rdi, rax
0x180117ee8  mov     [rsp+108h+var_D8], rax
0x180117eed  test    rax, rax
0x180117ef0  jz      loc_180117D12
0x180117ef6  mov     r14d, 0FFFFFFFEh
0x180117efc  and     [rax], r14d
0x180117eff  call    IsBasepReportFaultPresent
0x180117f04  test    al, al
0x180117f06  jz      short loc_180117F1D
0x180117f08  mov     rdx, rdi
0x180117f0b  call    WerpGetDebugger
0x180117f10  test    eax, eax
0x180117f12  js      short loc_180117F1A
0x180117f14  cmp     [rdi+4], bx
0x180117f18  jnz     short loc_180117F1D
0x180117f1a  and     [rdi], r14d
0x180117f1d  test    byte ptr [rdi], 2
0x180117f20  jnz     loc_18011800B
0x180117f26  mov     rcx, [r12]
0x180117f2a  movsxd  rax, dword ptr [rcx]
0x180117f2d  mov     [rsp+108h+Parameters], rax
0x180117f35  mov     rax, [rcx+10h]
0x180117f39  mov     [rsp+108h+var_50], rax
0x180117f41  cmp     dword ptr [rcx], 0C0000006h
0x180117f47  jnz     short loc_180117F55
0x180117f49  cmp     dword ptr [rcx+18h], 3
0x180117f4d  jb      short loc_180117F60
0x180117f4f  mov     rax, [rcx+30h]
0x180117f53  jmp     short loc_180117F63
0x180117f55  cmp     [rcx+18h], esi
0x180117f58  jb      short loc_180117F60
0x180117f5a  mov     rax, [rcx+20h]
0x180117f5e  jmp     short loc_180117F63
0x180117f60  mov     rax, rbx
0x180117f63  mov     [rsp+108h+var_48], rax
0x180117f6b  cmp     dword ptr [rcx+18h], 2
0x180117f6f  jb      short loc_180117F77
0x180117f71  mov     rax, [rcx+28h]
0x180117f75  jmp     short loc_180117F7A
0x180117f77  mov     rax, rbx
0x180117f7a  mov     [rsp+108h+var_40], rax
0x180117f82  mov     rax, gs:60h
0x180117f8b  test    dword ptr [rax+0BCh], 20000000h
0x180117f95  jz      short loc_180117FBC
0x180117f97  lea     rcx, aUnhandledExcep; "\r\nUnhandled exception encountered\r\n"
0x180117f9e  call    DbgPrint_0
0x180117fa3  int     3; Trap to Debugger
0x180117fa4  jmp     short loc_180117FBC
0x180117fa6  xor     ebx, ebx
0x180117fa8  or      r15, 0FFFFFFFFFFFFFFFFh
0x180117fac  lea     esi, [rbx+1]
0x180117faf  mov     r13, [rsp+108h+var_B8]
0x180117fb4  mov     rdi, [rsp+108h+var_D8]
0x180117fb9  mov     r12, r13
0x180117fbc  test    [rdi], sil
0x180117fbf  jz      short loc_180117FCE
0x180117fc1  cmp     cs:BasepAlreadyHadHardError, bl
0x180117fc7  mov     eax, 2
0x180117fcc  jz      short loc_180117FD0
0x180117fce  mov     eax, esi
  ... truncated ...
```
