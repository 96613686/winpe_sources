# InvokeTiffImageDocumentHandlerForPrinting

- ea: `0x1800366d0`
- end: `0x180036a7b`
- name: `InvokeTiffImageDocumentHandlerForPrinting`
- size: `939`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036f80`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002bb58`
- `0x18002d224`
- `0x18002d854`
- `0x1800366d0`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800368b2`
- `msvcrt!wcsstr` at `0x1800368b2`
- `KERNEL32!CloseHandle` at `0x180036a14`
- `KERNEL32!CloseHandle` at `0x180036a25`
- `KERNEL32!CloseHandle` at `0x180036a14`
- `KERNEL32!CloseHandle` at `0x180036a25`
- `KERNEL32!GetLastError` at `0x180036798`
- `KERNEL32!GetLastError` at `0x18003680b`
- `KERNEL32!GetLastError` at `0x180036867`
- `KERNEL32!GetLastError` at `0x1800369d8`
- `KERNEL32!GetLastError` at `0x180036798`
- `KERNEL32!GetLastError` at `0x18003680b`
- `KERNEL32!GetLastError` at `0x180036867`
- `KERNEL32!GetLastError` at `0x1800369d8`
- `KERNEL32!CreateProcessW` at `0x1800369c8`
- `KERNEL32!CreateProcessW` at `0x1800369c8`
- `ADVAPI32!RegCloseKey` at `0x180036a41`
- `ADVAPI32!RegCloseKey` at `0x180036a41`

## string_xrefs

- `0x180036778`: `TIFImage.Document\shell\printto\command`

## pseudocode

```c
__int64 __fastcall InvokeTiffImageDocumentHandlerForPrinting(__int64 a1, __int64 a2)
{
  HKEY v4; // rax
  HKEY v5; // rsi
  wchar_t *RegistryStringValue; // rdi
  DWORD LastError; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  int v11; // eax
  DWORD bInheritHandles; // [rsp+20h] [rbp-E0h]
  DWORD bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-90h] BYREF
  WCHAR CommandLine[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(CommandLine, 0, 0x208u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
  }
  v4 = (HKEY)OpenRegistryKey(0xFFFFFFFF80000000uLL, L"TIFImage.Document\\shell\\printto\\command", 0, 131097);
  v5 = v4;
  if ( v4 )
  {
    LastError = 0;
    RegistryStringValue = GetRegistryStringValue(v4, 1u, 0, 0, bInheritHandles);
    if ( RegistryStringValue )
      goto LABEL_21;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
    }
    RegistryStringValue = GetRegistryStringValue(v5, 2u, 0, 0, bInheritHandlesa);
    if ( RegistryStringValue )
    {
LABEL_21:
      v10 = wcsstr(RegistryStringValue, L"\"%1\"");
      if ( v10 )
      {
        *v10 = 0;
        v11 = StringCchPrintfW(CommandLine, 0x104u, L"%s\"%s\" \"%s\"", RegistryStringValue, a2, a1);
        if ( v11 >= 0 )
        {
          StartupInfo.cb = 104;
          StartupInfo.wShowWindow = 9;
          if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            CloseHandle(ProcessInformation.hThread);
            CloseHandle(ProcessInformation.hProcess);
          }
          else
          {
            LastError = GetLastError();
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v9 = 83;
              goto LABEL_10;
            }
          }
        }
        else
        {
          LastError = (unsigned __int16)v11;
          if ( (v11 & 0x1FFF0000) != 0x70000 )
            LastError = v11;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v9 = 82;
            goto LABEL_10;
          }
        }
      }
      else
      {
        LastError = 1627;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 81;
          goto LABEL_10;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 80;
        goto LABEL_10;
      }
    }
  }
  else
  {
    RegistryStringValue = 0;
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 78;
LABEL_10:
      WPP_SF_d(v8[2], v9, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
    }
  }
  pMemFree(RegistryStringValue);
  if ( v5 )
    RegCloseKey(v5);
  return LastError;
}

```

## disassembly

```asm
0x1800366d0  mov     [rsp-8+arg_10], rbx
0x1800366d5  mov     [rsp-8+arg_18], rsi
0x1800366da  push    rbp
0x1800366db  push    rdi
0x1800366dc  push    r12
0x1800366de  push    r14
0x1800366e0  push    r15
0x1800366e2  lea     rbp, [rsp-200h]
0x1800366ea  sub     rsp, 300h
0x1800366f1  mov     rax, cs:__security_cookie
0x1800366f8  xor     rax, rsp
0x1800366fb  mov     [rbp+220h+var_30], rax
0x180036702  mov     r15, rdx
0x180036705  mov     r14, rcx
0x180036708  xor     edx, edx; Val
0x18003670a  lea     rcx, [rbp+220h+CommandLine]; void *
0x18003670e  mov     r8d, 208h; Size
0x180036714  call    memset_0
0x180036719  xor     edx, edx; Val
0x18003671b  lea     rcx, [rsp+320h+StartupInfo]; void *
0x180036720  lea     r8d, [rdx+68h]; Size
0x180036724  call    memset_0
0x180036729  xorps   xmm0, xmm0
0x18003672c  xor     eax, eax
0x18003672e  movups  xmmword ptr [rsp+320h+ProcessInformation.hProcess], xmm0
0x180036733  mov     qword ptr [rsp+320h+ProcessInformation.dwProcessId], rax
0x180036738  mov     rcx, cs:WPP_GLOBAL_Control
0x18003673f  lea     rax, WPP_GLOBAL_Control
0x180036746  mov     r12d, 2
0x18003674c  cmp     rcx, rax
0x18003674f  jz      short loc_180036772
0x180036751  test    [rcx+1Ch], r12b
0x180036755  jz      short loc_180036772
0x180036757  cmp     byte ptr [rcx+19h], 5
0x18003675b  jb      short loc_180036772
0x18003675d  mov     rcx, [rcx+10h]
0x180036761  lea     edx, [r12+4Bh]
0x180036766  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x18003676d  call    WPP_SF_
0x180036772  mov     r9d, 20019h
0x180036778  lea     rdx, aTifimageDocume; "TIFImage.Document\\shell\\printto\\comm"...
0x18003677f  xor     r8d, r8d
0x180036782  mov     rcx, 0FFFFFFFF80000000h
0x180036789  call    OpenRegistryKey
0x18003678e  mov     rsi, rax
0x180036791  test    rax, rax
0x180036794  jnz     short loc_1800367EC
0x180036796  xor     edi, edi
0x180036798  call    cs:__imp_GetLastError
0x18003679f  nop     dword ptr [rax+rax+00h]
0x1800367a4  mov     ebx, eax
0x1800367a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367ad  lea     rax, WPP_GLOBAL_Control
0x1800367b4  cmp     rcx, rax
0x1800367b7  jz      loc_180036A31
0x1800367bd  test    [rcx+1Ch], r12b
0x1800367c1  jz      loc_180036A31
0x1800367c7  cmp     [rcx+19h], r12b
0x1800367cb  jb      loc_180036A31
0x1800367d1  lea     edx, [rsi+4Eh]
0x1800367d4  mov     rcx, [rcx+10h]
0x1800367d8  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x1800367df  mov     r9d, ebx
0x1800367e2  call    WPP_SF_d
0x1800367e7  jmp     loc_180036A31
0x1800367ec  xor     ebx, ebx
0x1800367ee  xor     r9d, r9d; unsigned __int16 *
0x1800367f1  xor     r8d, r8d; lpValueName
0x1800367f4  mov     rcx, rsi; hKey
0x1800367f7  lea     edx, [rbx+1]; dwType
0x1800367fa  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x1800367ff  mov     rdi, rax
0x180036802  test    rax, rax
0x180036805  jnz     loc_1800368A8
0x18003680b  call    cs:__imp_GetLastError
0x180036812  nop     dword ptr [rax+rax+00h]
0x180036817  mov     ebx, eax
0x180036819  mov     rcx, cs:WPP_GLOBAL_Control
0x180036820  lea     rax, WPP_GLOBAL_Control
0x180036827  cmp     rcx, rax
0x18003682a  jz      short loc_18003684E
0x18003682c  test    [rcx+1Ch], r12b
0x180036830  jz      short loc_18003684E
0x180036832  cmp     [rcx+19h], r12b
0x180036836  jb      short loc_18003684E
0x180036838  mov     rcx, [rcx+10h]
0x18003683c  lea     edx, [rdi+4Fh]
0x18003683f  mov     r9d, ebx
0x180036842  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180036849  call    WPP_SF_d
0x18003684e  xor     r9d, r9d; unsigned __int16 *
0x180036851  xor     r8d, r8d; lpValueName
0x180036854  mov     edx, r12d; dwType
0x180036857  mov     rcx, rsi; hKey
0x18003685a  call    ?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z; GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)
0x18003685f  mov     rdi, rax
0x180036862  test    rax, rax
0x180036865  jnz     short loc_1800368A8
0x180036867  call    cs:__imp_GetLastError
0x18003686e  nop     dword ptr [rax+rax+00h]
0x180036873  mov     ebx, eax
0x180036875  mov     rcx, cs:WPP_GLOBAL_Control
0x18003687c  lea     rax, WPP_GLOBAL_Control
0x180036883  cmp     rcx, rax
0x180036886  jz      loc_180036A31
0x18003688c  test    [rcx+1Ch], r12b
0x180036890  jz      loc_180036A31
0x180036896  cmp     [rcx+19h], r12b
0x18003689a  jb      loc_180036A31
0x1800368a0  lea     edx, [rdi+50h]
0x1800368a3  jmp     loc_1800367D4
0x1800368a8  lea     rdx, a1_0; "\"%1\""
0x1800368af  mov     rcx, rdi; Str
0x1800368b2  call    cs:__imp_wcsstr
0x1800368b9  nop     dword ptr [rax+rax+00h]
0x1800368be  mov     rcx, rax
0x1800368c1  test    rax, rax
0x1800368c4  jnz     short loc_180036900
0x1800368c6  mov     ebx, 65Bh
0x1800368cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800368d2  lea     rax, WPP_GLOBAL_Control
0x1800368d9  cmp     rcx, rax
0x1800368dc  jz      loc_180036A31
0x1800368e2  test    [rcx+1Ch], r12b
0x1800368e6  jz      loc_180036A31
0x1800368ec  cmp     [rcx+19h], r12b
0x1800368f0  jb      loc_180036A31
0x1800368f6  mov     edx, 51h ; 'Q'
0x1800368fb  jmp     loc_1800367D4
0x180036900  xor     eax, eax
0x180036902  mov     qword ptr [rsp+320h+dwCreationFlags], r14
0x180036907  mov     [rcx], ax
0x18003690a  lea     r8, aSSS_0; "%s\"%s\" \"%s\""
0x180036911  lea     rcx, [rbp+220h+CommandLine]; unsigned __int16 *
0x180036915  mov     qword ptr [rsp+320h+bInheritHandles], r15
0x18003691a  mov     r9, rdi
0x18003691d  mov     edx, 104h; unsigned __int64
0x180036922  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036927  test    eax, eax
0x180036929  jns     short loc_180036975
0x18003692b  mov     ecx, eax
0x18003692d  movzx   ebx, ax
0x180036930  and     ecx, 1FFF0000h
0x180036936  cmp     ecx, 70000h
0x18003693c  jz      short loc_180036940
0x18003693e  mov     ebx, eax
0x180036940  mov     rcx, cs:WPP_GLOBAL_Control
0x180036947  lea     rax, WPP_GLOBAL_Control
0x18003694e  cmp     rcx, rax
0x180036951  jz      loc_180036A31
0x180036957  test    [rcx+1Ch], r12b
0x18003695b  jz      loc_180036A31
0x180036961  cmp     [rcx+19h], r12b
0x180036965  jb      loc_180036A31
0x18003696b  mov     edx, 52h ; 'R'
0x180036970  jmp     loc_1800367D4
0x180036975  mov     eax, 9
0x18003697a  mov     [rsp+320h+StartupInfo.cb], 68h ; 'h'
0x180036982  mov     [rbp+220h+StartupInfo.wShowWindow], ax
0x180036986  lea     rdx, [rbp+220h+CommandLine]; lpCommandLine
0x18003698a  lea     rax, [rsp+320h+ProcessInformation]
0x18003698f  xor     r9d, r9d; lpThreadAttributes
0x180036992  mov     [rsp+320h+lpProcessInformation], rax; lpProcessInformation
0x180036997  xor     r8d, r8d; lpProcessAttributes
0x18003699a  lea     rax, [rsp+320h+StartupInfo]
0x18003699f  xor     ecx, ecx; lpApplicationName
0x1800369a1  mov     [rsp+320h+lpStartupInfo], rax; lpStartupInfo
0x1800369a6  mov     [rsp+320h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800369af  mov     [rsp+320h+lpEnvironment], 0; lpEnvironment
0x1800369b8  mov     [rsp+320h+dwCreationFlags], 0; dwCreationFlags
0x1800369c0  mov     [rsp+320h+bInheritHandles], 0; bInheritHandles
0x1800369c8  call    cs:__imp_CreateProcessW
0x1800369cf  nop     dword ptr [rax+rax+00h]
0x1800369d4  test    eax, eax
0x1800369d6  jnz     short loc_180036A0F
0x1800369d8  call    cs:__imp_GetLastError
0x1800369df  nop     dword ptr [rax+rax+00h]
0x1800369e4  mov     ebx, eax
0x1800369e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369ed  lea     rax, WPP_GLOBAL_Control
0x1800369f4  cmp     rcx, rax
0x1800369f7  jz      short loc_180036A31
0x1800369f9  test    [rcx+1Ch], r12b
0x1800369fd  jz      short loc_180036A31
0x1800369ff  cmp     [rcx+19h], r12b
0x180036a03  jb      short loc_180036A31
0x180036a05  mov     edx, 53h ; 'S'
0x180036a0a  jmp     loc_1800367D4
0x180036a0f  mov     rcx, [rsp+320h+ProcessInformation.hThread]; hObject
0x180036a14  call    cs:__imp_CloseHandle
0x180036a1b  nop     dword ptr [rax+rax+00h]
0x180036a20  mov     rcx, [rsp+320h+ProcessInformation.hProcess]; hObject
0x180036a25  call    cs:__imp_CloseHandle
0x180036a2c  nop     dword ptr [rax+rax+00h]
0x180036a31  mov     rcx, rdi; lpMem
0x180036a34  call    pMemFree
0x180036a39  test    rsi, rsi
0x180036a3c  jz      short loc_180036A4D
0x180036a3e  mov     rcx, rsi; hKey
0x180036a41  call    cs:__imp_RegCloseKey
0x180036a48  nop     dword ptr [rax+rax+00h]
0x180036a4d  mov     eax, ebx
0x180036a4f  mov     rcx, [rbp+220h+var_30]
0x180036a56  xor     rcx, rsp; StackCookie
0x180036a59  call    __security_check_cookie
0x180036a5e  lea     r11, [rsp+320h+var_20]
0x180036a66  mov     rbx, [r11+40h]
0x180036a6a  mov     rsi, [r11+48h]
0x180036a6e  mov     rsp, r11
0x180036a71  pop     r15
0x180036a73  pop     r14
0x180036a75  pop     r12
0x180036a77  pop     rdi
0x180036a78  pop     rbp
0x180036a79  retn
```
