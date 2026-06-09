# StartDsmUserTaskExe(ushort const *,ulong)

- ea: `0x180035ba8`
- end: `0x180035dd0`
- name: `?StartDsmUserTaskExe@@YAJPEBGK@Z`
- size: `552`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fe9c`

## callees

- `0x180007800`
- `0x180018240`
- `0x18001ba48`
- `0x180022070`
- `0x180027ba8`
- `0x180035ba8`
- `0x180035dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180035d2d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180035d2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035da6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035db4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180035bd1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180035bd1`
- `USERENV!CreateEnvironmentBlock` at `0x180035c66`
- `USERENV!CreateEnvironmentBlock` at `0x180035c66`
- `USERENV!DestroyEnvironmentBlock` at `0x180035d96`
- `USERENV!DestroyEnvironmentBlock` at `0x180035d96`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180035bf0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180035bf0`

## string_xrefs

- `0x180035c17`: `DsmUserTask.Exe `

## pseudocode

```c
__int64 __fastcall StartDsmUserTaskExe(WCHAR *a1)
{
  signed int v1; // edi
  DWORD active; // eax
  signed int LastError; // eax
  const unsigned __int16 *v4; // r8
  const unsigned __int16 *v5; // r9
  signed int v6; // eax
  WCHAR *v7; // rbx
  signed int v8; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-49h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-29h] BYREF
  LPWSTR lpCommandLine; // [rsp+110h] [rbp+67h] BYREF
  void *phToken; // [rsp+120h] [rbp+77h] BYREF
  LPVOID Environment; // [rsp+128h] [rbp+7Fh] BYREF

  lpCommandLine = a1;
  v1 = 0;
  if ( _IsUserTaskPresent() )
  {
    active = WTSGetActiveConsoleSessionId();
    if ( active == -1 )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      phToken = 0;
      if ( WTSQueryUserToken(active, &phToken) )
        goto LABEL_8;
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 >= 0 )
      {
LABEL_8:
        lpCommandLine = 0;
        v1 = CCoMemString::Assign((CCoMemString *)&lpCommandLine, L"DsmUserTask.Exe ");
        if ( v1 < 0 )
          goto LABEL_27;
        v1 = CCoMemString::Append((CCoMemString *)&lpCommandLine, L"?800F0248", v4, v5);
        if ( v1 < 0 )
          goto LABEL_27;
        Environment = 0;
        if ( CreateEnvironmentBlock(&Environment, phToken, 0) )
          goto LABEL_14;
        v6 = GetLastError();
        v1 = v6;
        if ( v6 > 0 )
          v1 = (unsigned __int16)v6 | 0x80070000;
        if ( v1 >= 0 )
        {
LABEL_14:
          *(_QWORD *)&StartupInfo.cb = 104;
          memset_0(&StartupInfo.lpReserved, 0, 0x60u);
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          v7 = lpCommandLine;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              &WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids,
              lpCommandLine);
          if ( CreateProcessAsUserW(phToken, 0, v7, 0, 0, 0, 0x400u, Environment, 0, &StartupInfo, &ProcessInformation) )
          {
            v1 = 0;
          }
          else
          {
            v8 = GetLastError();
            v1 = v8;
            if ( v8 > 0 )
              v1 = (unsigned __int16)v8 | 0x80070000;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              &WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids,
              (unsigned int)v1);
          if ( v1 >= 0 )
          {
            CloseHandle(ProcessInformation.hThread);
            CloseHandle(ProcessInformation.hProcess);
          }
          DestroyEnvironmentBlock(Environment);
        }
        else
        {
LABEL_27:
          v7 = lpCommandLine;
        }
        CloseHandle(phToken);
        if ( v7 )
          CoTaskMemFree(v7);
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180035ba8  mov     [rsp-8+arg_8], rbx
0x180035bad  mov     [rsp-8+lpCommandLine], rcx
0x180035bb2  push    rbp
0x180035bb3  push    rdi
0x180035bb4  push    r15
0x180035bb6  lea     rbp, [rsp-47h]
0x180035bbb  sub     rsp, 0F0h
0x180035bc2  xor     edi, edi
0x180035bc4  call    ?_IsUserTaskPresent@@YA_NXZ; _IsUserTaskPresent(void)
0x180035bc9  test    al, al
0x180035bcb  jz      loc_180035DBA
0x180035bd1  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180035bd7  cmp     eax, 0FFFFFFFFh
0x180035bda  jnz     short loc_180035BE6
0x180035bdc  mov     edi, 80004005h
0x180035be1  jmp     loc_180035DBA
0x180035be6  lea     rdx, [rbp+57h+phToken]; phToken
0x180035bea  mov     [rbp+57h+phToken], rdi
0x180035bee  mov     ecx, eax; SessionId
0x180035bf0  call    cs:__imp_WTSQueryUserToken
0x180035bf6  test    eax, eax
0x180035bf8  jnz     short loc_180035C17
0x180035bfa  call    cs:__imp_GetLastError
0x180035c00  mov     edi, eax
0x180035c02  test    eax, eax
0x180035c04  jle     short loc_180035C0F
0x180035c06  movzx   edi, ax
0x180035c09  or      edi, 80070000h
0x180035c0f  test    edi, edi
0x180035c11  js      loc_180035DBA
0x180035c17  lea     rdx, aDsmusertaskExe; "DsmUserTask.Exe "
0x180035c1e  mov     [rbp+57h+lpCommandLine], 0
0x180035c26  lea     rcx, [rbp+57h+lpCommandLine]; this
0x180035c2a  call    ?Assign@CCoMemString@@QEAAJPEBG@Z; CCoMemString::Assign(ushort const *)
0x180035c2f  mov     edi, eax
0x180035c31  test    eax, eax
0x180035c33  js      loc_180035D9E
0x180035c39  lea     rdx, a800f0248; "?800F0248"
0x180035c40  lea     rcx, [rbp+57h+lpCommandLine]; this
0x180035c44  call    ?Append@CCoMemString@@QEAAJPEBG00@Z; CCoMemString::Append(ushort const *,ushort const *,ushort const *)
0x180035c49  mov     edi, eax
0x180035c4b  test    eax, eax
0x180035c4d  js      loc_180035D9E
0x180035c53  mov     rdx, [rbp+57h+phToken]; hToken
0x180035c57  lea     rcx, [rbp+57h+Environment]; lpEnvironment
0x180035c5b  xor     r8d, r8d; bInherit
0x180035c5e  mov     [rbp+57h+Environment], 0
0x180035c66  call    cs:__imp_CreateEnvironmentBlock
0x180035c6c  test    eax, eax
0x180035c6e  jnz     short loc_180035C8D
0x180035c70  call    cs:__imp_GetLastError
0x180035c76  mov     edi, eax
0x180035c78  test    eax, eax
0x180035c7a  jle     short loc_180035C85
0x180035c7c  movzx   edi, ax
0x180035c7f  or      edi, 80070000h
0x180035c85  test    edi, edi
0x180035c87  js      loc_180035D9E
0x180035c8d  xor     edx, edx; Val
0x180035c8f  mov     qword ptr [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180035c97  lea     rcx, [rbp+57h+StartupInfo.lpReserved]; void *
0x180035c9b  lea     r8d, [rdx+60h]; Size
0x180035c9f  call    memset_0
0x180035ca4  xorps   xmm0, xmm0
0x180035ca7  xor     eax, eax
0x180035ca9  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180035cad  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180035cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180035cb8  lea     r15, WPP_GLOBAL_Control
0x180035cbf  mov     rbx, [rbp+57h+lpCommandLine]
0x180035cc3  cmp     rcx, r15
0x180035cc6  jz      short loc_180035CE4
0x180035cc8  test    byte ptr [rcx+1Ch], 1
0x180035ccc  jz      short loc_180035CE4
0x180035cce  mov     rcx, [rcx+10h]
0x180035cd2  lea     edx, [rax+0Ch]
0x180035cd5  mov     r9, rbx
0x180035cd8  lea     r8, WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids
0x180035cdf  call    WPP_SF_S
0x180035ce4  mov     rax, [rbp+57h+Environment]
0x180035ce8  lea     rcx, [rbp+57h+ProcessInformation]
0x180035cec  mov     [rsp+100h+lpProcessInformation], rcx; lpProcessInformation
0x180035cf1  xor     r9d, r9d; lpProcessAttributes
0x180035cf4  lea     rcx, [rbp+57h+StartupInfo]
0x180035cf8  mov     r8, rbx; lpCommandLine
0x180035cfb  mov     [rsp+100h+lpStartupInfo], rcx; lpStartupInfo
0x180035d00  xor     edx, edx; lpApplicationName
0x180035d02  mov     rcx, [rbp+57h+phToken]; hToken
0x180035d06  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180035d0f  mov     [rsp+100h+lpEnvironment], rax; lpEnvironment
0x180035d14  mov     [rsp+100h+dwCreationFlags], 400h; dwCreationFlags
0x180035d1c  mov     [rsp+100h+bInheritHandles], 0; bInheritHandles
0x180035d24  mov     [rsp+100h+lpThreadAttributes], 0; lpThreadAttributes
0x180035d2d  call    cs:__imp_CreateProcessAsUserW
0x180035d33  test    eax, eax
0x180035d35  jz      short loc_180035D3B
0x180035d37  xor     edi, edi
0x180035d39  jmp     short loc_180035D50
0x180035d3b  call    cs:__imp_GetLastError
0x180035d41  mov     edi, eax
0x180035d43  test    eax, eax
0x180035d45  jle     short loc_180035D50
0x180035d47  movzx   edi, ax
0x180035d4a  or      edi, 80070000h
0x180035d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d57  cmp     rcx, r15
0x180035d5a  jz      short loc_180035D7A
0x180035d5c  test    byte ptr [rcx+1Ch], 1
0x180035d60  jz      short loc_180035D7A
0x180035d62  mov     rcx, [rcx+10h]
0x180035d66  lea     r8, WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids
0x180035d6d  mov     edx, 0Dh
0x180035d72  mov     r9d, edi
0x180035d75  call    WPP_SF_d
0x180035d7a  test    edi, edi
0x180035d7c  js      short loc_180035D92
0x180035d7e  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180035d82  call    cs:__imp_CloseHandle
0x180035d88  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180035d8c  call    cs:__imp_CloseHandle
0x180035d92  mov     rcx, [rbp+57h+Environment]; lpEnvironment
0x180035d96  call    cs:__imp_DestroyEnvironmentBlock
0x180035d9c  jmp     short loc_180035DA2
0x180035d9e  mov     rbx, [rbp+57h+lpCommandLine]
0x180035da2  mov     rcx, [rbp+57h+phToken]; hObject
0x180035da6  call    cs:__imp_CloseHandle
0x180035dac  test    rbx, rbx
0x180035daf  jz      short loc_180035DBA
0x180035db1  mov     rcx, rbx; pv
0x180035db4  call    cs:__imp_CoTaskMemFree
0x180035dba  mov     rbx, [rsp+100h+arg_8]
0x180035dc2  mov     eax, edi
0x180035dc4  add     rsp, 0F0h
0x180035dcb  pop     r15
0x180035dcd  pop     rdi
0x180035dce  pop     rbp
0x180035dcf  retn
```
