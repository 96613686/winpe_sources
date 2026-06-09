# WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)

- ea: `0x18002de00`
- end: `0x18002dfec`
- name: `?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z`
- size: `492`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002ebe4`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002de00`
- `0x18003d510`

## import_xrefs

- `KERNEL32!Sleep` at `0x18002df12`
- `KERNEL32!Sleep` at `0x18002df12`
- `KERNEL32!GetTickCount` at `0x18002dec4`
- `KERNEL32!GetTickCount` at `0x18002deed`
- `KERNEL32!GetTickCount` at `0x18002dec4`
- `KERNEL32!GetTickCount` at `0x18002deed`
- `KERNEL32!GetLastError` at `0x18002de78`
- `KERNEL32!GetLastError` at `0x18002df36`
- `KERNEL32!GetLastError` at `0x18002de78`
- `KERNEL32!GetLastError` at `0x18002df36`
- `ADVAPI32!QueryServiceStatus` at `0x18002de68`
- `ADVAPI32!QueryServiceStatus` at `0x18002df26`
- `ADVAPI32!QueryServiceStatus` at `0x18002de68`
- `ADVAPI32!QueryServiceStatus` at `0x18002df26`

## pseudocode

```c
__int64 __fastcall WaitForServiceStopOrStart(SC_HANDLE hService)
{
  DWORD LastError; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  DWORD TickCount; // edi
  DWORD v7; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( !QueryServiceStatus(hService, &ServiceStatus) )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 77;
LABEL_10:
      WPP_SF_d(v3[2], v4, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
    return LastError;
  }
  if ( ServiceStatus.dwCurrentState != 4 )
  {
    TickCount = GetTickCount();
    while ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 4 )
        return 0;
      if ( ServiceStatus.dwCurrentState != 2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            79,
            WPP_db036311db36307996a98c23702218b2_Traceguids,
            ServiceStatus.dwCurrentState);
        }
        return 1062;
      }
      if ( GetTickCount() - TickCount > 0x927C0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_db036311db36307996a98c23702218b2_Traceguids);
        }
        return 1460;
      }
      v7 = 5000;
      if ( ServiceStatus.dwWaitHint >> 1 < 0x1388 )
        v7 = ServiceStatus.dwWaitHint >> 1;
      Sleep(v7);
    }
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 78;
      goto LABEL_10;
    }
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x18002de00  push    rbx
0x18002de02  push    rbp
0x18002de03  push    rdi
0x18002de04  push    r14
0x18002de06  sub     rsp, 58h
0x18002de0a  mov     rax, cs:__security_cookie
0x18002de11  xor     rax, rsp
0x18002de14  mov     [rsp+78h+var_38], rax
0x18002de19  xorps   xmm0, xmm0
0x18002de1c  mov     rbx, rcx
0x18002de1f  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18002de24  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002de29  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de30  lea     rbp, WPP_GLOBAL_Control
0x18002de37  lea     r14, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002de3e  cmp     rcx, rbp
0x18002de41  jz      short loc_18002DE60
0x18002de43  test    byte ptr [rcx+1Ch], 2
0x18002de47  jz      short loc_18002DE60
0x18002de49  cmp     byte ptr [rcx+19h], 5
0x18002de4d  jb      short loc_18002DE60
0x18002de4f  mov     rcx, [rcx+10h]
0x18002de53  mov     edx, 4Ch ; 'L'
0x18002de58  mov     r8, r14
0x18002de5b  call    WPP_SF_
0x18002de60  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18002de65  mov     rcx, rbx; hService
0x18002de68  call    cs:__imp_QueryServiceStatus
0x18002de6f  nop     dword ptr [rax+rax+00h]
0x18002de74  test    eax, eax
0x18002de76  jnz     short loc_18002DEB9
0x18002de78  call    cs:__imp_GetLastError
0x18002de7f  nop     dword ptr [rax+rax+00h]
0x18002de84  mov     ebx, eax
0x18002de86  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de8d  cmp     rcx, rbp
0x18002de90  jz      short loc_18002DEB2
0x18002de92  test    byte ptr [rcx+1Ch], 2
0x18002de96  jz      short loc_18002DEB2
0x18002de98  cmp     byte ptr [rcx+19h], 2
0x18002de9c  jb      short loc_18002DEB2
0x18002de9e  mov     edx, 4Dh ; 'M'
0x18002dea3  mov     rcx, [rcx+10h]
0x18002dea7  mov     r9d, ebx
0x18002deaa  mov     r8, r14
0x18002dead  call    WPP_SF_d
0x18002deb2  mov     eax, ebx
0x18002deb4  jmp     loc_18002DFD4
0x18002deb9  cmp     [rsp+78h+ServiceStatus.dwCurrentState], 4
0x18002debe  jz      loc_18002DFD2
0x18002dec4  call    cs:__imp_GetTickCount
0x18002decb  nop     dword ptr [rax+rax+00h]
0x18002ded0  mov     edi, eax
0x18002ded2  jmp     short loc_18002DF1E
0x18002ded4  mov     r9d, [rsp+78h+ServiceStatus.dwCurrentState]
0x18002ded9  cmp     r9d, 4
0x18002dedd  jz      loc_18002DFD2
0x18002dee3  cmp     r9d, 2
0x18002dee7  jnz     loc_18002DFA2
0x18002deed  call    cs:__imp_GetTickCount
0x18002def4  nop     dword ptr [rax+rax+00h]
0x18002def9  sub     eax, edi
0x18002defb  cmp     eax, 927C0h
0x18002df00  ja      short loc_18002DF72
0x18002df02  mov     eax, [rsp+78h+ServiceStatus.dwWaitHint]
0x18002df06  mov     ecx, 1388h
0x18002df0b  shr     eax, 1
0x18002df0d  cmp     eax, ecx
0x18002df0f  cmovb   ecx, eax; dwMilliseconds
0x18002df12  call    cs:__imp_Sleep
0x18002df19  nop     dword ptr [rax+rax+00h]
0x18002df1e  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18002df23  mov     rcx, rbx; hService
0x18002df26  call    cs:__imp_QueryServiceStatus
0x18002df2d  nop     dword ptr [rax+rax+00h]
0x18002df32  test    eax, eax
0x18002df34  jnz     short loc_18002DED4
0x18002df36  call    cs:__imp_GetLastError
0x18002df3d  nop     dword ptr [rax+rax+00h]
0x18002df42  mov     ebx, eax
0x18002df44  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df4b  cmp     rcx, rbp
0x18002df4e  jz      loc_18002DEB2
0x18002df54  test    byte ptr [rcx+1Ch], 2
0x18002df58  jz      loc_18002DEB2
0x18002df5e  cmp     byte ptr [rcx+19h], 2
0x18002df62  jb      loc_18002DEB2
0x18002df68  mov     edx, 4Eh ; 'N'
0x18002df6d  jmp     loc_18002DEA3
0x18002df72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df79  cmp     rcx, rbp
0x18002df7c  jz      short loc_18002DF9B
0x18002df7e  test    byte ptr [rcx+1Ch], 2
0x18002df82  jz      short loc_18002DF9B
0x18002df84  cmp     byte ptr [rcx+19h], 2
0x18002df88  jb      short loc_18002DF9B
0x18002df8a  mov     rcx, [rcx+10h]
0x18002df8e  mov     edx, 50h ; 'P'
0x18002df93  mov     r8, r14
0x18002df96  call    WPP_SF_
0x18002df9b  mov     eax, 5B4h
0x18002dfa0  jmp     short loc_18002DFD4
0x18002dfa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfa9  cmp     rcx, rbp
0x18002dfac  jz      short loc_18002DFCB
0x18002dfae  test    byte ptr [rcx+1Ch], 2
0x18002dfb2  jz      short loc_18002DFCB
0x18002dfb4  cmp     byte ptr [rcx+19h], 2
0x18002dfb8  jb      short loc_18002DFCB
0x18002dfba  mov     rcx, [rcx+10h]
0x18002dfbe  mov     edx, 4Fh ; 'O'
0x18002dfc3  mov     r8, r14
0x18002dfc6  call    WPP_SF_d
0x18002dfcb  mov     eax, 426h
0x18002dfd0  jmp     short loc_18002DFD4
0x18002dfd2  xor     eax, eax
0x18002dfd4  mov     rcx, [rsp+78h+var_38]
0x18002dfd9  xor     rcx, rsp; StackCookie
0x18002dfdc  call    __security_check_cookie
0x18002dfe1  add     rsp, 58h
0x18002dfe5  pop     r14
0x18002dfe7  pop     rdi
0x18002dfe8  pop     rbp
0x18002dfe9  pop     rbx
0x18002dfea  retn
```
