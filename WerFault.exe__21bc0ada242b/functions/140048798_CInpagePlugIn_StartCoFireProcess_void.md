# CInpagePlugIn::StartCoFireProcess(void)

- ea: `0x140048798`
- end: `0x140048a6e`
- name: `?StartCoFireProcess@CInpagePlugIn@@AEAAJXZ`
- size: `726`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140048a80`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14000b540`
- `0x14001444c`
- `0x140048798`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a17`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400489df`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1400489df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048973`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048a4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048973`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048a3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048a4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140048827`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140048827`

## string_xrefs

- `0x1400488ba`: `%s\system32\cofire.exe`

## pseudocode

```c
__int64 __fastcall CInpagePlugIn::StartCoFireProcess(CInpagePlugIn *this)
{
  UINT WindowsDirectoryW; // eax
  signed int v3; // eax
  signed int v4; // ebx
  CUserModeHangReport *v5; // rcx
  __int64 v6; // rdx
  signed int LastError; // eax
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW v11; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[264]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR ApplicationName[264]; // [rsp+360h] [rbp+260h] BYREF

  memset(&hObject, 0, sizeof(hObject));
  memset_0(&v11, 0, sizeof(v11));
  StartupInfo = v11;
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( WindowsDirectoryW )
  {
    if ( WindowsDirectoryW < 0x104 )
    {
      v4 = StringCchPrintfW(ApplicationName, 0x104u, L"%s\\system32\\cofire.exe", Buffer);
      if ( v4 >= 0 )
      {
        v4 = StringCchPrintfW(
               Buffer,
               0x104u,
               L"\"%s\" \"%s\" \"%s\"",
               ApplicationName,
               (char *)this + 568,
               (char *)this + 1088);
        if ( v4 >= 0 )
        {
          StartupInfo.cb = 104;
          if ( hObject.hProcess )
            CloseHandle(hObject.hProcess);
          if ( hObject.hThread )
            CloseHandle(hObject.hThread);
          memset(&hObject, 0, sizeof(hObject));
          if ( CreateProcessW(ApplicationName, Buffer, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &hObject) )
          {
            v4 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
            }
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 19;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 18;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v4 = -2147024774;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 17;
        goto LABEL_7;
      }
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 16;
LABEL_7:
      WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids);
    }
  }
  if ( hObject.hProcess )
    CloseHandle(hObject.hProcess);
  if ( hObject.hThread )
    CloseHandle(hObject.hThread);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140048798  push    rbp
0x14004879a  push    rbx
0x14004879b  push    rdi
0x14004879c  push    r14
0x14004879e  lea     rbp, [rsp-488h]
0x1400487a6  sub     rsp, 588h
0x1400487ad  mov     rax, cs:__security_cookie
0x1400487b4  xor     rax, rsp
0x1400487b7  mov     [rbp+4A0h+var_30], rax
0x1400487be  xor     eax, eax
0x1400487c0  mov     rdi, rcx
0x1400487c3  xorps   xmm0, xmm0
0x1400487c6  mov     [rsp+5A0h+var_540], rax
0x1400487cb  xor     edx, edx; Val
0x1400487cd  lea     rcx, [rbp+4A0h+var_4C0]; void *
0x1400487d1  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x1400487d6  lea     r8d, [rax+68h]; Size
0x1400487da  call    memset_0
0x1400487df  movups  xmm0, [rbp+4A0h+var_4C0]
0x1400487e3  mov     r14d, 104h
0x1400487e9  lea     rcx, [rbp+4A0h+Buffer]; lpBuffer
0x1400487ed  movups  xmm1, [rbp+4A0h+var_4B0]
0x1400487f1  mov     edx, r14d; uSize
0x1400487f4  movaps  xmmword ptr [rsp+5A0h+StartupInfo.cb], xmm0
0x1400487f9  movups  xmm0, [rbp+4A0h+var_4A0]
0x1400487fd  movaps  xmmword ptr [rbp+4A0h+StartupInfo.lpDesktop], xmm1
0x140048801  movups  xmm1, [rbp+4A0h+var_490]
0x140048805  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwX], xmm0
0x140048809  movups  xmm0, [rbp+4A0h+var_480]
0x14004880d  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwXCountChars], xmm1
0x140048811  movups  xmm1, [rbp+4A0h+var_470]
0x140048815  movaps  xmmword ptr [rbp+4A0h+StartupInfo.wShowWindow], xmm0
0x140048819  movsd   xmm0, [rbp+4A0h+var_460]
0x14004881e  movsd   [rbp+4A0h+StartupInfo.hStdError], xmm0
0x140048823  movaps  xmmword ptr [rbp+4A0h+StartupInfo.hStdInput], xmm1
0x140048827  call    cs:__imp_GetWindowsDirectoryW
0x14004882d  test    eax, eax
0x14004882f  jnz     short loc_140048881
0x140048831  call    cs:__imp_GetLastError
0x140048837  mov     ebx, eax
0x140048839  test    eax, eax
0x14004883b  jle     short loc_140048846
0x14004883d  movzx   ebx, ax
0x140048840  or      ebx, 80070000h
0x140048846  mov     rcx, cs:WPP_GLOBAL_Control
0x14004884d  lea     rax, WPP_GLOBAL_Control
0x140048854  cmp     rcx, rax
0x140048857  jz      loc_140048A30
0x14004885d  test    byte ptr [rcx+1Ch], 1
0x140048861  jz      loc_140048A30
0x140048867  mov     edx, 10h
0x14004886c  mov     rcx, [rcx+10h]
0x140048870  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x140048877  call    WPP_SF_
0x14004887c  jmp     loc_140048A30
0x140048881  cmp     eax, r14d
0x140048884  jb      short loc_1400488B3
0x140048886  mov     ebx, 8007007Ah
0x14004888b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048892  lea     rax, WPP_GLOBAL_Control
0x140048899  cmp     rcx, rax
0x14004889c  jz      loc_140048A30
0x1400488a2  test    byte ptr [rcx+1Ch], 1
0x1400488a6  jz      loc_140048A30
0x1400488ac  mov     edx, 11h
0x1400488b1  jmp     short loc_14004886C
0x1400488b3  lea     r9, [rbp+4A0h+Buffer]
0x1400488b7  mov     rdx, r14; unsigned __int64
0x1400488ba  lea     r8, aSSystem32Cofir; "%s\\system32\\cofire.exe"
0x1400488c1  lea     rcx, [rbp+4A0h+ApplicationName]; wchar_t *
0x1400488c8  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400488cd  mov     ebx, eax
0x1400488cf  test    eax, eax
0x1400488d1  jns     short loc_1400488FE
0x1400488d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488da  lea     rax, WPP_GLOBAL_Control
0x1400488e1  cmp     rcx, rax
0x1400488e4  jz      loc_140048A30
0x1400488ea  test    byte ptr [rcx+1Ch], 1
0x1400488ee  jz      loc_140048A30
0x1400488f4  mov     edx, 12h
0x1400488f9  jmp     loc_14004886C
0x1400488fe  lea     rax, [rdi+440h]
0x140048905  mov     rdx, r14; unsigned __int64
0x140048908  lea     rcx, [rdi+238h]
0x14004890f  mov     qword ptr [rsp+5A0h+dwCreationFlags], rax
0x140048914  mov     qword ptr [rsp+5A0h+bInheritHandles], rcx
0x140048919  lea     r9, [rbp+4A0h+ApplicationName]
0x140048920  lea     rcx, [rbp+4A0h+Buffer]; wchar_t *
0x140048924  lea     r8, aSSS; "\"%s\" \"%s\" \"%s\""
0x14004892b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140048930  mov     ebx, eax
0x140048932  test    eax, eax
0x140048934  jns     short loc_140048961
0x140048936  mov     rcx, cs:WPP_GLOBAL_Control
0x14004893d  lea     rax, WPP_GLOBAL_Control
0x140048944  cmp     rcx, rax
0x140048947  jz      loc_140048A30
0x14004894d  test    byte ptr [rcx+1Ch], 1
0x140048951  jz      loc_140048A30
0x140048957  mov     edx, 13h
0x14004895c  jmp     loc_14004886C
0x140048961  mov     rcx, [rsp+5A0h+hObject]; hObject
0x140048966  mov     [rsp+5A0h+StartupInfo.cb], 68h ; 'h'
0x14004896e  test    rcx, rcx
0x140048971  jz      short loc_140048979
0x140048973  call    cs:__imp_CloseHandle
0x140048979  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x14004897e  test    rcx, rcx
0x140048981  jz      short loc_140048989
0x140048983  call    cs:__imp_CloseHandle
0x140048989  xor     eax, eax
0x14004898b  lea     rdx, [rbp+4A0h+Buffer]; lpCommandLine
0x14004898f  mov     [rsp+5A0h+var_540], rax
0x140048994  lea     rcx, [rbp+4A0h+ApplicationName]; lpApplicationName
0x14004899b  lea     rax, [rsp+5A0h+hObject]
0x1400489a0  xorps   xmm0, xmm0
0x1400489a3  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x1400489a8  xor     r9d, r9d; lpThreadAttributes
0x1400489ab  lea     rax, [rsp+5A0h+StartupInfo]
0x1400489b0  xor     r8d, r8d; lpProcessAttributes
0x1400489b3  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x1400489b8  mov     [rsp+5A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1400489c1  mov     [rsp+5A0h+lpEnvironment], 0; lpEnvironment
0x1400489ca  mov     [rsp+5A0h+dwCreationFlags], 8000000h; dwCreationFlags
0x1400489d2  mov     [rsp+5A0h+bInheritHandles], 0; bInheritHandles
0x1400489da  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x1400489df  call    cs:__imp_CreateProcessW
0x1400489e5  test    eax, eax
0x1400489e7  jnz     short loc_140048A2E
0x1400489e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400489f0  lea     rax, WPP_GLOBAL_Control
0x1400489f7  cmp     rcx, rax
0x1400489fa  jz      short loc_140048A17
0x1400489fc  test    byte ptr [rcx+1Ch], 1
0x140048a00  jz      short loc_140048A17
0x140048a02  mov     rcx, [rcx+10h]
0x140048a06  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x140048a0d  mov     edx, 14h
0x140048a12  call    WPP_SF_
0x140048a17  call    cs:__imp_GetLastError
0x140048a1d  mov     ebx, eax
0x140048a1f  test    eax, eax
0x140048a21  jle     short loc_140048A30
0x140048a23  movzx   ebx, ax
0x140048a26  or      ebx, 80070000h
0x140048a2c  jmp     short loc_140048A30
0x140048a2e  xor     ebx, ebx
0x140048a30  mov     rcx, [rsp+5A0h+hObject]; hObject
0x140048a35  test    rcx, rcx
0x140048a38  jz      short loc_140048A40
0x140048a3a  call    cs:__imp_CloseHandle
0x140048a40  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x140048a45  test    rcx, rcx
0x140048a48  jz      short loc_140048A50
0x140048a4a  call    cs:__imp_CloseHandle
0x140048a50  mov     eax, ebx
0x140048a52  mov     rcx, [rbp+4A0h+var_30]
0x140048a59  xor     rcx, rsp; StackCookie
0x140048a5c  call    __security_check_cookie
0x140048a61  add     rsp, 588h
0x140048a68  pop     r14
0x140048a6a  pop     rdi
0x140048a6b  pop     rbx
0x140048a6c  pop     rbp
0x140048a6d  retn
```
