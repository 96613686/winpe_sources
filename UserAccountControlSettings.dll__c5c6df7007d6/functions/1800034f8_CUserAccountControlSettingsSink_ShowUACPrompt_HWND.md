# CUserAccountControlSettingsSink::_ShowUACPrompt(HWND__ *)

- ea: `0x1800034f8`
- end: `0x180003620`
- name: `?_ShowUACPrompt@CUserAccountControlSettingsSink@@AEAAJPEAUHWND__@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(CUserAccountControlSettingsSink *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180003400`

## callees

- `0x1800034cc`
- `0x1800034f8`
- `0x18000b6de`
- `0x18000b710`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18000359b`
- `SHELL32!ShellExecuteExW` at `0x18000359b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003537`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800035eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800035b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800035b7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800035c9`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800035c9`

## string_xrefs

- `0x180003526`: `%systemroot%\system32\UserAccountControlSettings.exe`

## pseudocode

```c
__int64 __fastcall CUserAccountControlSettingsSink::_ShowUACPrompt(CUserAccountControlSettingsSink *this, HWND a2)
{
  signed int Error; // ebx
  HANDLE hProcess; // rbx
  DWORD ExitCode[4]; // [rsp+20h] [rbp-E0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Dst[264]; // [rsp+A0h] [rbp-60h] BYREF

  if ( ExpandEnvironmentStringsW(L"%systemroot%\\system32\\UserAccountControlSettings.exe", Dst, 0x104u)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pExecInfo.cbSize = 112;
    memset_0(&pExecInfo.fMask, 0, 0x6Cu);
    pExecInfo.fMask = 64;
    pExecInfo.lpFile = Dst;
    pExecInfo.hwnd = a2;
    pExecInfo.lpParameters = L"/applySettings";
    pExecInfo.lpVerb = L"runas";
    if ( ShellExecuteExW(&pExecInfo) )
    {
      hProcess = pExecInfo.hProcess;
      ExitCode[0] = 0;
      if ( WaitForSingleObject(pExecInfo.hProcess, 0xFFFFFFFF) )
      {
        Error = -2147467259;
      }
      else if ( GetExitCodeProcess(hProcess, ExitCode) )
      {
        Error = ExitCode[0];
      }
      else
      {
        Error = ResultFromKnownLastError();
      }
      CloseHandle(pExecInfo.hProcess);
    }
    else
    {
      return (unsigned int)ResultFromKnownLastError();
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800034f8  mov     [rsp-8+arg_0], rbx
0x1800034fd  mov     [rsp-8+arg_10], rdi
0x180003502  push    rbp
0x180003503  lea     rbp, [rsp-1C0h]
0x18000350b  sub     rsp, 2C0h
0x180003512  mov     rax, cs:__security_cookie
0x180003519  xor     rax, rsp
0x18000351c  mov     [rbp+1C0h+var_10], rax
0x180003523  mov     rdi, rdx
0x180003526  lea     rcx, Src; "%systemroot%\\system32\\UserAccountCont"...
0x18000352d  lea     rdx, [rbp+1C0h+Dst]; lpDst
0x180003531  mov     r8d, 104h; nSize
0x180003537  call    cs:__imp_ExpandEnvironmentStringsW
0x18000353d  test    eax, eax
0x18000353f  jnz     short loc_180003550
0x180003541  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003546  mov     ebx, eax
0x180003548  test    eax, eax
0x18000354a  js      loc_1800035FA
0x180003550  xor     edx, edx; Val
0x180003552  mov     [rsp+2C0h+pExecInfo.cbSize], 70h ; 'p'
0x18000355a  lea     rcx, [rsp+2C0h+pExecInfo.fMask]; void *
0x18000355f  lea     r8d, [rdx+6Ch]; Size
0x180003563  call    memset_0
0x180003568  lea     rax, [rbp+1C0h+Dst]
0x18000356c  mov     [rsp+2C0h+pExecInfo.fMask], 40h ; '@'
0x180003574  mov     [rsp+2C0h+pExecInfo.lpFile], rax
0x180003579  lea     rcx, [rsp+2C0h+pExecInfo]; pExecInfo
0x18000357e  lea     rax, aApplysettings; "/applySettings"
0x180003585  mov     [rsp+2C0h+pExecInfo.hwnd], rdi
0x18000358a  mov     [rsp+2C0h+pExecInfo.lpParameters], rax
0x18000358f  lea     rax, aRunas; "runas"
0x180003596  mov     [rsp+2C0h+pExecInfo.lpVerb], rax
0x18000359b  call    cs:__imp_ShellExecuteExW
0x1800035a1  test    eax, eax
0x1800035a3  jz      short loc_1800035F3
0x1800035a5  mov     rbx, [rbp+1C0h+pExecInfo.hProcess]
0x1800035a9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800035ac  mov     rcx, rbx; hHandle
0x1800035af  mov     [rsp+2C0h+ExitCode], 0
0x1800035b7  call    cs:__imp_WaitForSingleObject
0x1800035bd  test    eax, eax
0x1800035bf  jnz     short loc_1800035E2
0x1800035c1  lea     rdx, [rsp+2C0h+ExitCode]; lpExitCode
0x1800035c6  mov     rcx, rbx; hProcess
0x1800035c9  call    cs:__imp_GetExitCodeProcess
0x1800035cf  test    eax, eax
0x1800035d1  jnz     short loc_1800035DC
0x1800035d3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800035d8  mov     ebx, eax
0x1800035da  jmp     short loc_1800035E7
0x1800035dc  mov     ebx, [rsp+2C0h+ExitCode]
0x1800035e0  jmp     short loc_1800035E7
0x1800035e2  mov     ebx, 80004005h
0x1800035e7  mov     rcx, [rbp+1C0h+pExecInfo.hProcess]; hObject
0x1800035eb  call    cs:__imp_CloseHandle
0x1800035f1  jmp     short loc_1800035FA
0x1800035f3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800035f8  mov     ebx, eax
0x1800035fa  mov     eax, ebx
0x1800035fc  mov     rcx, [rbp+1C0h+var_10]
0x180003603  xor     rcx, rsp; StackCookie
0x180003606  call    __security_check_cookie
0x18000360b  lea     r11, [rsp+2C0h+var_s0]
0x180003613  mov     rbx, [r11+10h]
0x180003617  mov     rdi, [r11+20h]
0x18000361b  mov     rsp, r11
0x18000361e  pop     rbp
0x18000361f  retn
```
