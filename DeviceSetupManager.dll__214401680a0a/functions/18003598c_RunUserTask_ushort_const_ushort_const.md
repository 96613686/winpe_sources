# RunUserTask(ushort const *,ushort const *)

- ea: `0x18003598c`
- end: `0x180035b9f`
- name: `?RunUserTask@@YAJPEBG0@Z`
- size: `531`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003120c`

## callees

- `0x180007800`
- `0x180018240`
- `0x180019d74`
- `0x18001ba48`
- `0x180021790`
- `0x18002541c`
- `0x18003598c`
- `0x180035dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ada`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180035acc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180035acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b54`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800359c2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800359c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800359e1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800359e1`

## string_xrefs

- `0x180035a08`: `DsmUserTask.Exe `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RunUserTask(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v4; // edi
  DWORD active; // eax
  signed int LastError; // eax
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  LPWSTR v9; // rbx
  signed int v10; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-49h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-29h] BYREF
  LPWSTR lpCommandLine; // [rsp+120h] [rbp+77h] BYREF
  void *phToken; // [rsp+128h] [rbp+7Fh] BYREF

  v4 = 0;
  if ( _IsSetupUIDisabledByPolicy() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids);
  }
  else if ( _IsUserTaskPresent() )
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
        goto LABEL_9;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_9:
        lpCommandLine = 0;
        v4 = CCoMemString::Assign((CCoMemString *)&lpCommandLine, L"DsmUserTask.Exe ");
        if ( v4 < 0
          || a2 && (v4 = CCoMemString::Append((CCoMemString *)&lpCommandLine, a2, v7, v8), v4 < 0)
          || (v4 = CCoMemString::Append((CCoMemString *)&lpCommandLine, a1, v7, v8), v4 < 0) )
        {
          v9 = lpCommandLine;
        }
        else
        {
          *(_QWORD *)&StartupInfo.cb = 104;
          memset_0(&StartupInfo.lpReserved, 0, 0x60u);
          v9 = lpCommandLine;
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          if ( CreateProcessAsUserW(phToken, 0, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            v4 = 0;
          }
          else
          {
            v10 = GetLastError();
            v4 = v10;
            if ( v10 > 0 )
              v4 = (unsigned __int16)v10 | 0x80070000;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              (unsigned int)WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids,
              (_DWORD)v9,
              v4);
          if ( v4 >= 0 )
          {
            CloseHandle(ProcessInformation.hThread);
            CloseHandle(ProcessInformation.hProcess);
          }
        }
        CloseHandle(phToken);
        if ( v9 )
          CoTaskMemFree(v9);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003598c  mov     [rsp-8+arg_0], rbx
0x180035991  push    rbp
0x180035992  push    rsi
0x180035993  push    rdi
0x180035994  lea     rbp, [rsp-47h]
0x180035999  sub     rsp, 0F0h
0x1800359a0  mov     rbx, rdx
0x1800359a3  mov     rsi, rcx
0x1800359a6  xor     edi, edi
0x1800359a8  call    ?_IsSetupUIDisabledByPolicy@@YA_NXZ; _IsSetupUIDisabledByPolicy(void)
0x1800359ad  test    al, al
0x1800359af  jnz     loc_180035B5C
0x1800359b5  call    ?_IsUserTaskPresent@@YA_NXZ; _IsUserTaskPresent(void)
0x1800359ba  test    al, al
0x1800359bc  jz      loc_180035B8A
0x1800359c2  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800359c8  cmp     eax, 0FFFFFFFFh
0x1800359cb  jnz     short loc_1800359D7
0x1800359cd  mov     edi, 80004005h
0x1800359d2  jmp     loc_180035B8A
0x1800359d7  lea     rdx, [rbp+57h+phToken]; phToken
0x1800359db  mov     [rbp+57h+phToken], rdi
0x1800359df  mov     ecx, eax; SessionId
0x1800359e1  call    cs:__imp_WTSQueryUserToken
0x1800359e7  test    eax, eax
0x1800359e9  jnz     short loc_180035A08
0x1800359eb  call    cs:__imp_GetLastError
0x1800359f1  mov     edi, eax
0x1800359f3  test    eax, eax
0x1800359f5  jle     short loc_180035A00
0x1800359f7  movzx   edi, ax
0x1800359fa  or      edi, 80070000h
0x180035a00  test    edi, edi
0x180035a02  js      loc_180035B8A
0x180035a08  lea     rdx, aDsmusertaskExe; "DsmUserTask.Exe "
0x180035a0f  mov     [rbp+57h+lpCommandLine], 0
0x180035a17  lea     rcx, [rbp+57h+lpCommandLine]; this
0x180035a1b  call    ?Assign@CCoMemString@@QEAAJPEBG@Z; CCoMemString::Assign(ushort const *)
0x180035a20  mov     edi, eax
0x180035a22  test    eax, eax
0x180035a24  js      loc_180035B3E
0x180035a2a  test    rbx, rbx
0x180035a2d  jz      short loc_180035A45
0x180035a2f  mov     rdx, rbx; unsigned __int16 *
0x180035a32  lea     rcx, [rbp+57h+lpCommandLine]; this
0x180035a36  call    ?Append@CCoMemString@@QEAAJPEBG00@Z; CCoMemString::Append(ushort const *,ushort const *,ushort const *)
0x180035a3b  mov     edi, eax
0x180035a3d  test    eax, eax
0x180035a3f  js      loc_180035B3E
0x180035a45  mov     rdx, rsi; unsigned __int16 *
0x180035a48  lea     rcx, [rbp+57h+lpCommandLine]; this
0x180035a4c  call    ?Append@CCoMemString@@QEAAJPEBG00@Z; CCoMemString::Append(ushort const *,ushort const *,ushort const *)
0x180035a51  mov     edi, eax
0x180035a53  test    eax, eax
0x180035a55  js      loc_180035B3E
0x180035a5b  xor     edx, edx; Val
0x180035a5d  mov     qword ptr [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180035a65  lea     rcx, [rbp+57h+StartupInfo.lpReserved]; void *
0x180035a69  lea     r8d, [rdx+60h]; Size
0x180035a6d  call    memset_0
0x180035a72  mov     rbx, [rbp+57h+lpCommandLine]
0x180035a76  xor     eax, eax
0x180035a78  mov     rcx, [rbp+57h+phToken]; hToken
0x180035a7c  xorps   xmm0, xmm0
0x180035a7f  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180035a83  xor     r9d, r9d; lpProcessAttributes
0x180035a86  lea     rax, [rbp+57h+ProcessInformation]
0x180035a8a  mov     r8, rbx; lpCommandLine
0x180035a8d  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x180035a92  xor     edx, edx; lpApplicationName
0x180035a94  lea     rax, [rbp+57h+StartupInfo]
0x180035a98  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x180035a9d  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180035aa6  mov     [rsp+100h+lpEnvironment], 0; lpEnvironment
0x180035aaf  mov     [rsp+100h+dwCreationFlags], 0; dwCreationFlags
0x180035ab7  mov     [rsp+100h+bInheritHandles], 0; bInheritHandles
0x180035abf  mov     [rsp+100h+lpThreadAttributes], 0; lpThreadAttributes
0x180035ac8  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180035acc  call    cs:__imp_CreateProcessAsUserW
0x180035ad2  test    eax, eax
0x180035ad4  jz      short loc_180035ADA
0x180035ad6  xor     edi, edi
0x180035ad8  jmp     short loc_180035AEF
0x180035ada  call    cs:__imp_GetLastError
0x180035ae0  mov     edi, eax
0x180035ae2  test    eax, eax
0x180035ae4  jle     short loc_180035AEF
0x180035ae6  movzx   edi, ax
0x180035ae9  or      edi, 80070000h
0x180035aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180035af6  lea     rax, WPP_GLOBAL_Control
0x180035afd  cmp     rcx, rax
0x180035b00  jz      short loc_180035B24
0x180035b02  test    byte ptr [rcx+1Ch], 10h
0x180035b06  jz      short loc_180035B24
0x180035b08  mov     rcx, [rcx+10h]
0x180035b0c  lea     r8, WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids
0x180035b13  mov     edx, 0Ah
0x180035b18  mov     dword ptr [rsp+100h+lpThreadAttributes], edi
0x180035b1c  mov     r9, rbx
0x180035b1f  call    WPP_SF_Sd
0x180035b24  test    edi, edi
0x180035b26  js      short loc_180035B42
0x180035b28  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180035b2c  call    cs:__imp_CloseHandle
0x180035b32  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180035b36  call    cs:__imp_CloseHandle
0x180035b3c  jmp     short loc_180035B42
0x180035b3e  mov     rbx, [rbp+57h+lpCommandLine]
0x180035b42  mov     rcx, [rbp+57h+phToken]; hObject
0x180035b46  call    cs:__imp_CloseHandle
0x180035b4c  test    rbx, rbx
0x180035b4f  jz      short loc_180035B8A
0x180035b51  mov     rcx, rbx; pv
0x180035b54  call    cs:__imp_CoTaskMemFree
0x180035b5a  jmp     short loc_180035B8A
0x180035b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b63  lea     rax, WPP_GLOBAL_Control
0x180035b6a  cmp     rcx, rax
0x180035b6d  jz      short loc_180035B8A
0x180035b6f  test    byte ptr [rcx+1Ch], 1
0x180035b73  jz      short loc_180035B8A
0x180035b75  mov     rcx, [rcx+10h]
0x180035b79  lea     r8, WPP_bd88bed05aa13fd5bc097d4a303fcdaa_Traceguids
0x180035b80  mov     edx, 0Bh
0x180035b85  call    WPP_SF_
0x180035b8a  mov     rbx, [rsp+100h+arg_0]
0x180035b92  mov     eax, edi
0x180035b94  add     rsp, 0F0h
0x180035b9b  pop     rdi
0x180035b9c  pop     rsi
0x180035b9d  pop     rbp
0x180035b9e  retn
```
