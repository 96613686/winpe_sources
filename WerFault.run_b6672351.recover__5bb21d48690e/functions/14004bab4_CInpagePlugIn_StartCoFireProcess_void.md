# CInpagePlugIn::StartCoFireProcess(void)

- ea: `0x14004bab4`
- end: `0x14004bdbb`
- name: `?StartCoFireProcess@CInpagePlugIn@@AEAAJXZ`
- size: `775`
- prototype: `__int64 __fastcall(CInpagePlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14004bdd0`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000b580`
- `0x140014ee4`
- `0x14004bab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bd51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bb53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004bd51`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14004bd13`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14004bd13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bc9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bcb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bd7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bd90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bc9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bcb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bd7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004bd90`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14004bb43`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14004bb43`

## string_xrefs

- `0x14004bbe2`: `%s\system32\cofire.exe`

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
0x14004bab4  push    rbp
0x14004bab6  push    rbx
0x14004bab7  push    rdi
0x14004bab8  push    r14
0x14004baba  lea     rbp, [rsp-488h]
0x14004bac2  sub     rsp, 588h
0x14004bac9  mov     rax, cs:__security_cookie
0x14004bad0  xor     rax, rsp
0x14004bad3  mov     [rbp+4A0h+var_30], rax
0x14004bada  xor     eax, eax
0x14004badc  mov     rdi, rcx
0x14004badf  xorps   xmm0, xmm0
0x14004bae2  mov     [rsp+5A0h+var_540], rax
0x14004bae7  xor     edx, edx; Val
0x14004bae9  lea     rcx, [rbp+4A0h+var_4C0]; void *
0x14004baed  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x14004baf2  lea     r8d, [rax+68h]; Size
0x14004baf6  call    memset_0
0x14004bafb  movups  xmm0, [rbp+4A0h+var_4C0]
0x14004baff  mov     r14d, 104h
0x14004bb05  lea     rcx, [rbp+4A0h+Buffer]; lpBuffer
0x14004bb09  movups  xmm1, [rbp+4A0h+var_4B0]
0x14004bb0d  mov     edx, r14d; uSize
0x14004bb10  movaps  xmmword ptr [rsp+5A0h+StartupInfo.cb], xmm0
0x14004bb15  movups  xmm0, [rbp+4A0h+var_4A0]
0x14004bb19  movaps  xmmword ptr [rbp+4A0h+StartupInfo.lpDesktop], xmm1
0x14004bb1d  movups  xmm1, [rbp+4A0h+var_490]
0x14004bb21  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwX], xmm0
0x14004bb25  movups  xmm0, [rbp+4A0h+var_480]
0x14004bb29  movaps  xmmword ptr [rbp+4A0h+StartupInfo.dwXCountChars], xmm1
0x14004bb2d  movups  xmm1, [rbp+4A0h+var_470]
0x14004bb31  movaps  xmmword ptr [rbp+4A0h+StartupInfo.wShowWindow], xmm0
0x14004bb35  movsd   xmm0, [rbp+4A0h+var_460]
0x14004bb3a  movsd   [rbp+4A0h+StartupInfo.hStdError], xmm0
0x14004bb3f  movaps  xmmword ptr [rbp+4A0h+StartupInfo.hStdInput], xmm1
0x14004bb43  call    cs:__imp_GetWindowsDirectoryW
0x14004bb4a  nop     dword ptr [rax+rax+00h]
0x14004bb4f  test    eax, eax
0x14004bb51  jnz     short loc_14004BBA9
0x14004bb53  call    cs:__imp_GetLastError
0x14004bb5a  nop     dword ptr [rax+rax+00h]
0x14004bb5f  mov     ebx, eax
0x14004bb61  test    eax, eax
0x14004bb63  jle     short loc_14004BB6E
0x14004bb65  movzx   ebx, ax
0x14004bb68  or      ebx, 80070000h
0x14004bb6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bb75  lea     rax, WPP_GLOBAL_Control
0x14004bb7c  cmp     rcx, rax
0x14004bb7f  jz      loc_14004BD70
0x14004bb85  test    byte ptr [rcx+1Ch], 1
0x14004bb89  jz      loc_14004BD70
0x14004bb8f  mov     edx, 10h
0x14004bb94  mov     rcx, [rcx+10h]
0x14004bb98  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004bb9f  call    WPP_SF_
0x14004bba4  jmp     loc_14004BD70
0x14004bba9  cmp     eax, r14d
0x14004bbac  jb      short loc_14004BBDB
0x14004bbae  mov     ebx, 8007007Ah
0x14004bbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bbba  lea     rax, WPP_GLOBAL_Control
0x14004bbc1  cmp     rcx, rax
0x14004bbc4  jz      loc_14004BD70
0x14004bbca  test    byte ptr [rcx+1Ch], 1
0x14004bbce  jz      loc_14004BD70
0x14004bbd4  mov     edx, 11h
0x14004bbd9  jmp     short loc_14004BB94
0x14004bbdb  lea     r9, [rbp+4A0h+Buffer]
0x14004bbdf  mov     rdx, r14; unsigned __int64
0x14004bbe2  lea     r8, aSSystem32Cofir; "%s\\system32\\cofire.exe"
0x14004bbe9  lea     rcx, [rbp+4A0h+ApplicationName]; wchar_t *
0x14004bbf0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14004bbf5  mov     ebx, eax
0x14004bbf7  test    eax, eax
0x14004bbf9  jns     short loc_14004BC26
0x14004bbfb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc02  lea     rax, WPP_GLOBAL_Control
0x14004bc09  cmp     rcx, rax
0x14004bc0c  jz      loc_14004BD70
0x14004bc12  test    byte ptr [rcx+1Ch], 1
0x14004bc16  jz      loc_14004BD70
0x14004bc1c  mov     edx, 12h
0x14004bc21  jmp     loc_14004BB94
0x14004bc26  lea     rax, [rdi+440h]
0x14004bc2d  mov     rdx, r14; unsigned __int64
0x14004bc30  lea     rcx, [rdi+238h]
0x14004bc37  mov     qword ptr [rsp+5A0h+dwCreationFlags], rax
0x14004bc3c  mov     qword ptr [rsp+5A0h+bInheritHandles], rcx
0x14004bc41  lea     r9, [rbp+4A0h+ApplicationName]
0x14004bc48  lea     rcx, [rbp+4A0h+Buffer]; wchar_t *
0x14004bc4c  lea     r8, aSSS; "\"%s\" \"%s\" \"%s\""
0x14004bc53  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14004bc58  mov     ebx, eax
0x14004bc5a  test    eax, eax
0x14004bc5c  jns     short loc_14004BC89
0x14004bc5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc65  lea     rax, WPP_GLOBAL_Control
0x14004bc6c  cmp     rcx, rax
0x14004bc6f  jz      loc_14004BD70
0x14004bc75  test    byte ptr [rcx+1Ch], 1
0x14004bc79  jz      loc_14004BD70
0x14004bc7f  mov     edx, 13h
0x14004bc84  jmp     loc_14004BB94
0x14004bc89  mov     rcx, [rsp+5A0h+hObject]; hObject
0x14004bc8e  mov     [rsp+5A0h+StartupInfo.cb], 68h ; 'h'
0x14004bc96  test    rcx, rcx
0x14004bc99  jz      short loc_14004BCA7
0x14004bc9b  call    cs:__imp_CloseHandle
0x14004bca2  nop     dword ptr [rax+rax+00h]
0x14004bca7  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x14004bcac  test    rcx, rcx
0x14004bcaf  jz      short loc_14004BCBD
0x14004bcb1  call    cs:__imp_CloseHandle
0x14004bcb8  nop     dword ptr [rax+rax+00h]
0x14004bcbd  xor     eax, eax
0x14004bcbf  lea     rdx, [rbp+4A0h+Buffer]; lpCommandLine
0x14004bcc3  mov     [rsp+5A0h+var_540], rax
0x14004bcc8  lea     rcx, [rbp+4A0h+ApplicationName]; lpApplicationName
0x14004bccf  lea     rax, [rsp+5A0h+hObject]
0x14004bcd4  xorps   xmm0, xmm0
0x14004bcd7  mov     [rsp+5A0h+lpProcessInformation], rax; lpProcessInformation
0x14004bcdc  xor     r9d, r9d; lpThreadAttributes
0x14004bcdf  lea     rax, [rsp+5A0h+StartupInfo]
0x14004bce4  xor     r8d, r8d; lpProcessAttributes
0x14004bce7  mov     [rsp+5A0h+lpStartupInfo], rax; lpStartupInfo
0x14004bcec  mov     [rsp+5A0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14004bcf5  mov     [rsp+5A0h+lpEnvironment], 0; lpEnvironment
0x14004bcfe  mov     [rsp+5A0h+dwCreationFlags], 8000000h; dwCreationFlags
0x14004bd06  mov     [rsp+5A0h+bInheritHandles], 0; bInheritHandles
0x14004bd0e  movups  xmmword ptr [rsp+5A0h+hObject], xmm0
0x14004bd13  call    cs:__imp_CreateProcessW
0x14004bd1a  nop     dword ptr [rax+rax+00h]
0x14004bd1f  test    eax, eax
0x14004bd21  jnz     short loc_14004BD6E
0x14004bd23  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bd2a  lea     rax, WPP_GLOBAL_Control
0x14004bd31  cmp     rcx, rax
0x14004bd34  jz      short loc_14004BD51
0x14004bd36  test    byte ptr [rcx+1Ch], 1
0x14004bd3a  jz      short loc_14004BD51
0x14004bd3c  mov     rcx, [rcx+10h]
0x14004bd40  lea     r8, WPP_1a5416ce094a32ffbfa11198aa918cdd_Traceguids
0x14004bd47  mov     edx, 14h
0x14004bd4c  call    WPP_SF_
0x14004bd51  call    cs:__imp_GetLastError
0x14004bd58  nop     dword ptr [rax+rax+00h]
0x14004bd5d  mov     ebx, eax
0x14004bd5f  test    eax, eax
0x14004bd61  jle     short loc_14004BD70
0x14004bd63  movzx   ebx, ax
0x14004bd66  or      ebx, 80070000h
0x14004bd6c  jmp     short loc_14004BD70
0x14004bd6e  xor     ebx, ebx
0x14004bd70  mov     rcx, [rsp+5A0h+hObject]; hObject
0x14004bd75  test    rcx, rcx
0x14004bd78  jz      short loc_14004BD86
0x14004bd7a  call    cs:__imp_CloseHandle
0x14004bd81  nop     dword ptr [rax+rax+00h]
0x14004bd86  mov     rcx, [rsp+5A0h+hObject+8]; hObject
0x14004bd8b  test    rcx, rcx
0x14004bd8e  jz      short loc_14004BD9C
0x14004bd90  call    cs:__imp_CloseHandle
0x14004bd97  nop     dword ptr [rax+rax+00h]
0x14004bd9c  mov     eax, ebx
0x14004bd9e  mov     rcx, [rbp+4A0h+var_30]
0x14004bda5  xor     rcx, rsp; StackCookie
0x14004bda8  call    __security_check_cookie
0x14004bdad  add     rsp, 588h
0x14004bdb4  pop     r14
0x14004bdb6  pop     rdi
0x14004bdb7  pop     rbx
0x14004bdb8  pop     rbp
0x14004bdb9  retn
```
