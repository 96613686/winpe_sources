# WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)

- ea: `0x140072798`
- end: `0x14007296a`
- name: `?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z`
- size: `466`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140073750`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140072798`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x14007280c`
- `ADVAPI32!QueryServiceStatus` at `0x1400728a9`
- `ADVAPI32!QueryServiceStatus` at `0x14007280c`
- `ADVAPI32!QueryServiceStatus` at `0x1400728a9`
- `KERNEL32!GetTickCount` at `0x14007285c`
- `KERNEL32!GetTickCount` at `0x14007287f`
- `KERNEL32!GetTickCount` at `0x14007285c`
- `KERNEL32!GetTickCount` at `0x14007287f`
- `KERNEL32!GetLastError` at `0x140072816`
- `KERNEL32!GetLastError` at `0x1400728b3`
- `KERNEL32!GetLastError` at `0x140072816`
- `KERNEL32!GetLastError` at `0x1400728b3`
- `KERNEL32!Sleep` at `0x14007289b`
- `KERNEL32!Sleep` at `0x14007289b`

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
0x140072798  mov     [rsp+arg_8], rbx
0x14007279d  mov     [rsp+arg_10], rsi
0x1400727a2  push    rdi
0x1400727a3  push    r14
0x1400727a5  push    r15
0x1400727a7  sub     rsp, 50h
0x1400727ab  mov     rax, cs:__security_cookie
0x1400727b2  xor     rax, rsp
0x1400727b5  mov     [rsp+68h+var_28], rax
0x1400727ba  xorps   xmm0, xmm0
0x1400727bd  mov     esi, r8d
0x1400727c0  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1400727c5  mov     rbx, rcx
0x1400727c8  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400727cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400727d4  lea     r14, WPP_GLOBAL_Control
0x1400727db  lea     r15, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400727e2  cmp     rcx, r14
0x1400727e5  jz      short loc_140072804
0x1400727e7  test    byte ptr [rcx+1Ch], 2
0x1400727eb  jz      short loc_140072804
0x1400727ed  cmp     byte ptr [rcx+19h], 5
0x1400727f1  jb      short loc_140072804
0x1400727f3  mov     rcx, [rcx+10h]
0x1400727f7  mov     edx, 4Ch ; 'L'
0x1400727fc  mov     r8, r15
0x1400727ff  call    WPP_SF_
0x140072804  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x140072809  mov     rcx, rbx; hService
0x14007280c  call    cs:__imp_QueryServiceStatus
0x140072812  test    eax, eax
0x140072814  jnz     short loc_140072851
0x140072816  call    cs:__imp_GetLastError
0x14007281c  mov     ebx, eax
0x14007281e  mov     rcx, cs:WPP_GLOBAL_Control
0x140072825  cmp     rcx, r14
0x140072828  jz      short loc_14007284A
0x14007282a  test    byte ptr [rcx+1Ch], 2
0x14007282e  jz      short loc_14007284A
0x140072830  cmp     byte ptr [rcx+19h], 2
0x140072834  jb      short loc_14007284A
0x140072836  mov     edx, 4Dh ; 'M'
0x14007283b  mov     rcx, [rcx+10h]
0x14007283f  mov     r9d, ebx
0x140072842  mov     r8, r15
0x140072845  call    WPP_SF_d
0x14007284a  mov     eax, ebx
0x14007284c  jmp     loc_140072947
0x140072851  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 1
0x140072856  jz      loc_140072945
0x14007285c  call    cs:__imp_GetTickCount
0x140072862  mov     edi, eax
0x140072864  jmp     short loc_1400728A1
0x140072866  mov     r9d, [rsp+68h+ServiceStatus.dwCurrentState]
0x14007286b  cmp     r9d, 1
0x14007286f  jz      loc_140072945
0x140072875  cmp     r9d, 3
0x140072879  jnz     loc_140072915
0x14007287f  call    cs:__imp_GetTickCount
0x140072885  sub     eax, edi
0x140072887  cmp     eax, esi
0x140072889  ja      short loc_1400728E5
0x14007288b  mov     eax, [rsp+68h+ServiceStatus.dwWaitHint]
0x14007288f  mov     ecx, 1388h
0x140072894  shr     eax, 1
0x140072896  cmp     eax, ecx
0x140072898  cmovb   ecx, eax; dwMilliseconds
0x14007289b  call    cs:__imp_Sleep
0x1400728a1  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1400728a6  mov     rcx, rbx; hService
0x1400728a9  call    cs:__imp_QueryServiceStatus
0x1400728af  test    eax, eax
0x1400728b1  jnz     short loc_140072866
0x1400728b3  call    cs:__imp_GetLastError
0x1400728b9  mov     ebx, eax
0x1400728bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728c2  cmp     rcx, r14
0x1400728c5  jz      short loc_14007284A
0x1400728c7  test    byte ptr [rcx+1Ch], 2
0x1400728cb  jz      loc_14007284A
0x1400728d1  cmp     byte ptr [rcx+19h], 2
0x1400728d5  jb      loc_14007284A
0x1400728db  mov     edx, 4Eh ; 'N'
0x1400728e0  jmp     loc_14007283B
0x1400728e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728ec  cmp     rcx, r14
0x1400728ef  jz      short loc_14007290E
0x1400728f1  test    byte ptr [rcx+1Ch], 2
0x1400728f5  jz      short loc_14007290E
0x1400728f7  cmp     byte ptr [rcx+19h], 2
0x1400728fb  jb      short loc_14007290E
0x1400728fd  mov     rcx, [rcx+10h]
0x140072901  mov     edx, 50h ; 'P'
0x140072906  mov     r8, r15
0x140072909  call    WPP_SF_
0x14007290e  mov     eax, 5B4h
0x140072913  jmp     short loc_140072947
0x140072915  mov     rcx, cs:WPP_GLOBAL_Control
0x14007291c  cmp     rcx, r14
0x14007291f  jz      short loc_14007293E
0x140072921  test    byte ptr [rcx+1Ch], 2
0x140072925  jz      short loc_14007293E
0x140072927  cmp     byte ptr [rcx+19h], 2
0x14007292b  jb      short loc_14007293E
0x14007292d  mov     rcx, [rcx+10h]
0x140072931  mov     edx, 4Fh ; 'O'
0x140072936  mov     r8, r15
0x140072939  call    WPP_SF_d
0x14007293e  mov     eax, 426h
0x140072943  jmp     short loc_140072947
0x140072945  xor     eax, eax
0x140072947  mov     rcx, [rsp+68h+var_28]
0x14007294c  xor     rcx, rsp; StackCookie
0x14007294f  call    __security_check_cookie
0x140072954  lea     r11, [rsp+68h+var_18]
0x140072959  mov     rbx, [r11+28h]
0x14007295d  mov     rsi, [r11+30h]
0x140072961  mov     rsp, r11
0x140072964  pop     r15
0x140072966  pop     r14
0x140072968  pop     rdi
0x140072969  retn
```
