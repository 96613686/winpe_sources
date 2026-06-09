# WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)

- ea: `0x1400770c0`
- end: `0x1400772c1`
- name: `?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z`
- size: `513`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400781f0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400770c0`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x140077134`
- `ADVAPI32!QueryServiceStatus` at `0x1400771ef`
- `ADVAPI32!QueryServiceStatus` at `0x140077134`
- `ADVAPI32!QueryServiceStatus` at `0x1400771ef`
- `KERNEL32!GetTickCount` at `0x140077190`
- `KERNEL32!GetTickCount` at `0x1400771b9`
- `KERNEL32!GetTickCount` at `0x140077190`
- `KERNEL32!GetTickCount` at `0x1400771b9`
- `KERNEL32!GetLastError` at `0x140077144`
- `KERNEL32!GetLastError` at `0x1400771ff`
- `KERNEL32!GetLastError` at `0x140077144`
- `KERNEL32!GetLastError` at `0x1400771ff`
- `KERNEL32!Sleep` at `0x1400771db`
- `KERNEL32!Sleep` at `0x1400771db`

## pseudocode

```c
__int64 __fastcall WaitForServiceStopOrStart(SC_HANDLE hService, __int64 a2, DWORD a3)
{
  DWORD LastError; // ebx
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  DWORD TickCount; // edi
  DWORD v10; // ecx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-48h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( !QueryServiceStatus(hService, &ServiceStatus) )
  {
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 77;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
    return LastError;
  }
  if ( ServiceStatus.dwCurrentState != 1 )
  {
    TickCount = GetTickCount();
    while ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      if ( ServiceStatus.dwCurrentState == 1 )
        return 0;
      if ( ServiceStatus.dwCurrentState != 3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( GetTickCount() - TickCount > a3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_db036311db36307996a98c23702218b2_Traceguids);
        }
        return 1460;
      }
      v10 = 5000;
      if ( ServiceStatus.dwWaitHint >> 1 < 0x1388 )
        v10 = ServiceStatus.dwWaitHint >> 1;
      Sleep(v10);
    }
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 78;
      goto LABEL_10;
    }
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x1400770c0  mov     [rsp+arg_8], rbx
0x1400770c5  mov     [rsp+arg_10], rsi
0x1400770ca  push    rdi
0x1400770cb  push    r14
0x1400770cd  push    r15
0x1400770cf  sub     rsp, 50h
0x1400770d3  mov     rax, cs:__security_cookie
0x1400770da  xor     rax, rsp
0x1400770dd  mov     [rsp+68h+var_28], rax
0x1400770e2  xorps   xmm0, xmm0
0x1400770e5  mov     esi, r8d
0x1400770e8  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1400770ed  mov     rbx, rcx
0x1400770f0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400770f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400770fc  lea     r14, WPP_GLOBAL_Control
0x140077103  lea     r15, WPP_db036311db36307996a98c23702218b2_Traceguids
0x14007710a  cmp     rcx, r14
0x14007710d  jz      short loc_14007712C
0x14007710f  test    byte ptr [rcx+1Ch], 2
0x140077113  jz      short loc_14007712C
0x140077115  cmp     byte ptr [rcx+19h], 5
0x140077119  jb      short loc_14007712C
0x14007711b  mov     rcx, [rcx+10h]
0x14007711f  mov     edx, 4Ch ; 'L'
0x140077124  mov     r8, r15
0x140077127  call    WPP_SF_
0x14007712c  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x140077131  mov     rcx, rbx; hService
0x140077134  call    cs:__imp_QueryServiceStatus
0x14007713b  nop     dword ptr [rax+rax+00h]
0x140077140  test    eax, eax
0x140077142  jnz     short loc_140077185
0x140077144  call    cs:__imp_GetLastError
0x14007714b  nop     dword ptr [rax+rax+00h]
0x140077150  mov     ebx, eax
0x140077152  mov     rcx, cs:WPP_GLOBAL_Control
0x140077159  cmp     rcx, r14
0x14007715c  jz      short loc_14007717E
0x14007715e  test    byte ptr [rcx+1Ch], 2
0x140077162  jz      short loc_14007717E
0x140077164  cmp     byte ptr [rcx+19h], 2
0x140077168  jb      short loc_14007717E
0x14007716a  mov     edx, 4Dh ; 'M'
0x14007716f  mov     rcx, [rcx+10h]
0x140077173  mov     r9d, ebx
0x140077176  mov     r8, r15
0x140077179  call    WPP_SF_d
0x14007717e  mov     eax, ebx
0x140077180  jmp     loc_14007729D
0x140077185  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x14007718a  jz      loc_14007729B
0x140077190  call    cs:__imp_GetTickCount
0x140077197  nop     dword ptr [rax+rax+00h]
0x14007719c  mov     edi, eax
0x14007719e  jmp     short loc_1400771E7
0x1400771a0  mov     r9d, [rsp+68h+ServiceStatus.dwCurrentState]
0x1400771a5  cmp     r9d, 1
0x1400771a9  jz      loc_14007729B
0x1400771af  cmp     r9d, 3
0x1400771b3  jnz     loc_14007726B
0x1400771b9  call    cs:__imp_GetTickCount
0x1400771c0  nop     dword ptr [rax+rax+00h]
0x1400771c5  sub     eax, edi
0x1400771c7  cmp     eax, esi
0x1400771c9  ja      short loc_14007723B
0x1400771cb  mov     eax, [rsp+68h+ServiceStatus.dwWaitHint]
0x1400771cf  mov     ecx, 1388h
0x1400771d4  shr     eax, 1
0x1400771d6  cmp     eax, ecx
0x1400771d8  cmovb   ecx, eax; dwMilliseconds
0x1400771db  call    cs:__imp_Sleep
0x1400771e2  nop     dword ptr [rax+rax+00h]
0x1400771e7  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1400771ec  mov     rcx, rbx; hService
0x1400771ef  call    cs:__imp_QueryServiceStatus
0x1400771f6  nop     dword ptr [rax+rax+00h]
0x1400771fb  test    eax, eax
0x1400771fd  jnz     short loc_1400771A0
0x1400771ff  call    cs:__imp_GetLastError
0x140077206  nop     dword ptr [rax+rax+00h]
0x14007720b  mov     ebx, eax
0x14007720d  mov     rcx, cs:WPP_GLOBAL_Control
0x140077214  cmp     rcx, r14
0x140077217  jz      loc_14007717E
0x14007721d  test    byte ptr [rcx+1Ch], 2
0x140077221  jz      loc_14007717E
0x140077227  cmp     byte ptr [rcx+19h], 2
0x14007722b  jb      loc_14007717E
0x140077231  mov     edx, 4Eh ; 'N'
0x140077236  jmp     loc_14007716F
0x14007723b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077242  cmp     rcx, r14
0x140077245  jz      short loc_140077264
0x140077247  test    byte ptr [rcx+1Ch], 2
0x14007724b  jz      short loc_140077264
0x14007724d  cmp     byte ptr [rcx+19h], 2
0x140077251  jb      short loc_140077264
0x140077253  mov     rcx, [rcx+10h]
0x140077257  mov     edx, 50h ; 'P'
0x14007725c  mov     r8, r15
0x14007725f  call    WPP_SF_
0x140077264  mov     eax, 5B4h
0x140077269  jmp     short loc_14007729D
0x14007726b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077272  cmp     rcx, r14
0x140077275  jz      short loc_140077294
0x140077277  test    byte ptr [rcx+1Ch], 2
0x14007727b  jz      short loc_140077294
0x14007727d  cmp     byte ptr [rcx+19h], 2
0x140077281  jb      short loc_140077294
0x140077283  mov     rcx, [rcx+10h]
0x140077287  mov     edx, 4Fh ; 'O'
0x14007728c  mov     r8, r15
0x14007728f  call    WPP_SF_d
0x140077294  mov     eax, 426h
0x140077299  jmp     short loc_14007729D
0x14007729b  xor     eax, eax
0x14007729d  mov     rcx, [rsp+68h+var_28]
0x1400772a2  xor     rcx, rsp; StackCookie
0x1400772a5  call    __security_check_cookie
0x1400772aa  lea     r11, [rsp+68h+var_18]
0x1400772af  mov     rbx, [r11+28h]
0x1400772b3  mov     rsi, [r11+30h]
0x1400772b7  mov     rsp, r11
0x1400772ba  pop     r15
0x1400772bc  pop     r14
0x1400772be  pop     rdi
0x1400772bf  retn
```
