# StopService

- ea: `0x1400781f0`
- end: `0x140078568`
- name: `StopService`
- size: `888`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x14003b300`
- `0x1400781f0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x1400698ec`
- `0x14006998c`
- `0x140076e04`
- `0x140076f08`
- `0x1400770c0`
- `0x1400781f0`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!ControlService` at `0x1400784a3`
- `ADVAPI32!ControlService` at `0x1400784a3`
- `ADVAPI32!EnumDependentServicesW` at `0x14007830a`
- `ADVAPI32!EnumDependentServicesW` at `0x140078411`
- `ADVAPI32!EnumDependentServicesW` at `0x14007830a`
- `ADVAPI32!EnumDependentServicesW` at `0x140078411`
- `KERNEL32!GetLastError` at `0x14007831e`
- `KERNEL32!GetLastError` at `0x1400783be`
- `KERNEL32!GetLastError` at `0x14007844c`
- `KERNEL32!GetLastError` at `0x1400784d2`
- `KERNEL32!GetLastError` at `0x14007831e`
- `KERNEL32!GetLastError` at `0x1400783be`
- `KERNEL32!GetLastError` at `0x14007844c`
- `KERNEL32!GetLastError` at `0x1400784d2`
- `KERNEL32!SetLastError` at `0x14007851d`
- `KERNEL32!SetLastError` at `0x14007851d`

## pseudocode

```c
__int64 __fastcall StopService(__int64 a1, const unsigned __int16 *a2, int a3, unsigned int a4)
{
  unsigned int v4; // edi
  struct _ENUM_SERVICE_STATUSW *v8; // r15
  const unsigned __int16 *v9; // rcx
  DWORD v10; // eax
  SC_HANDLE v11; // rsi
  DWORD v12; // eax
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // edx
  DWORD LastError; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-60h]
  DWORD cbBufSize; // [rsp+40h] [rbp-40h] BYREF
  SC_HANDLE hService; // [rsp+48h] [rbp-38h] BYREF
  SC_HANDLE hSCObject; // [rsp+50h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-28h] BYREF

  v4 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  hSCObject = 0;
  hService = 0;
  v8 = 0;
  v9 = (const unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v10 = FaxOpenService(v9, a2, &hSCObject, &hService, pcbBytesNeeded, 0x2Cu, &ServiceStatus.dwCurrentState);
  v11 = hService;
  if ( v10 )
    goto LABEL_41;
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_db036311db36307996a98c23702218b2_Traceguids);
    }
    goto LABEL_11;
  }
  if ( !a3 )
  {
LABEL_34:
    if ( !ControlService(v11, 1u, &ServiceStatus) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
      goto LABEL_42;
    }
    if ( !a4 || (v10 = WaitForServiceStopOrStart(v11, v16, a4)) == 0 )
    {
LABEL_11:
      v4 = 1;
      goto LABEL_42;
    }
LABEL_41:
    SetLastError(v10);
    goto LABEL_42;
  }
  LODWORD(hService) = 0;
  cbBufSize = 0;
  if ( !EnumDependentServicesW(v11, 1u, 0, 0, &cbBufSize, (LPDWORD)&hService) )
  {
    v12 = GetLastError();
    if ( v12 != 234 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v14 = 34;
LABEL_19:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_db036311db36307996a98c23702218b2_Traceguids, v12);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
    if ( !cbBufSize )
      goto LABEL_34;
    v8 = (struct _ENUM_SERVICE_STATUSW *)pMemAlloc(cbBufSize);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        GetLastError();
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_db036311db36307996a98c23702218b2_Traceguids);
      }
      goto LABEL_42;
    }
  }
  if ( EnumDependentServicesW(v11, 1u, v8, cbBufSize, &cbBufSize, (LPDWORD)&hService) )
  {
    v15 = 0;
    if ( (_DWORD)hService )
    {
      while ( (unsigned int)StopService(0, v8[v15].lpServiceName, 0, 0xFFFFFFFFLL) )
      {
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= (unsigned int)hService )
          goto LABEL_34;
      }
      goto LABEL_42;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = GetLastError();
    v13 = WPP_GLOBAL_Control;
    v14 = 36;
    goto LABEL_19;
  }
LABEL_42:
  pMemFree(v8);
  FaxCloseService(hSCObject, v11);
  return v4;
}

```

## disassembly

```asm
0x1400781f0  mov     [rsp-28h+arg_0], rbx
0x1400781f5  mov     [rsp-28h+arg_10], rsi
0x1400781fa  push    rbp
0x1400781fb  push    rdi
0x1400781fc  push    r13
0x1400781fe  push    r14
0x140078200  push    r15
0x140078202  mov     rbp, rsp
0x140078205  sub     rsp, 80h
0x14007820c  mov     rax, cs:__security_cookie
0x140078213  xor     rax, rsp
0x140078216  mov     [rbp+var_8], rax
0x14007821a  xor     edi, edi
0x14007821c  xorps   xmm0, xmm0
0x14007821f  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x140078223  mov     r14d, r9d
0x140078226  mov     ebx, r8d
0x140078229  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x14007822d  mov     rsi, rdx
0x140078230  mov     [rbp+hSCObject], rdi
0x140078234  mov     [rbp+hService], rdi
0x140078238  xor     r15d, r15d
0x14007823b  mov     rcx, cs:WPP_GLOBAL_Control
0x140078242  lea     rax, WPP_GLOBAL_Control
0x140078249  cmp     rcx, rax
0x14007824c  jz      short loc_14007826D
0x14007824e  test    byte ptr [rcx+1Ch], 2
0x140078252  jz      short loc_14007826D
0x140078254  cmp     byte ptr [rcx+19h], 5
0x140078258  jb      short loc_14007826D
0x14007825a  mov     rcx, [rcx+10h]
0x14007825e  lea     edx, [rdi+20h]
0x140078261  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140078268  call    WPP_SF_
0x14007826d  lea     rax, [rbp+ServiceStatus.dwCurrentState]
0x140078271  mov     rdx, rsi; unsigned __int16 *
0x140078274  mov     [rsp+80h+var_50], rax; unsigned int *
0x140078279  lea     r9, [rbp+hService]; struct SC_HANDLE__ **
0x14007827d  lea     r8, [rbp+hSCObject]; struct SC_HANDLE__ **
0x140078281  mov     dword ptr [rsp+80h+lpServicesReturned], 2Ch ; ','; unsigned int
0x140078289  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x14007828e  mov     rsi, [rbp+hService]
0x140078292  test    eax, eax
0x140078294  jnz     loc_14007851B
0x14007829a  lea     r13d, [rax+1]
0x14007829e  cmp     [rbp+ServiceStatus.dwCurrentState], r13d
0x1400782a2  jnz     short loc_1400782DE
0x1400782a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400782ab  lea     rdx, WPP_GLOBAL_Control
0x1400782b2  cmp     rcx, rdx
0x1400782b5  jz      short loc_1400782D6
0x1400782b7  test    byte ptr [rcx+1Ch], 2
0x1400782bb  jz      short loc_1400782D6
0x1400782bd  cmp     byte ptr [rcx+19h], 5
0x1400782c1  jb      short loc_1400782D6
0x1400782c3  mov     rcx, [rcx+10h]
0x1400782c7  lea     edx, [rax+21h]
0x1400782ca  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400782d1  call    WPP_SF_
0x1400782d6  mov     edi, r13d
0x1400782d9  jmp     loc_140078529
0x1400782de  test    ebx, ebx
0x1400782e0  jz      loc_140078499
0x1400782e6  lea     rax, [rbp+hService]
0x1400782ea  mov     dword ptr [rbp+hService], edi
0x1400782ed  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x1400782f2  xor     r9d, r9d; cbBufSize
0x1400782f5  lea     rax, [rbp+cbBufSize]
0x1400782f9  mov     [rbp+cbBufSize], edi
0x1400782fc  xor     r8d, r8d; lpServices
0x1400782ff  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140078304  mov     edx, r13d; dwServiceState
0x140078307  mov     rcx, rsi; hService
0x14007830a  call    cs:__imp_EnumDependentServicesW
0x140078311  nop     dword ptr [rax+rax+00h]
0x140078316  test    eax, eax
0x140078318  jnz     loc_1400783F2
0x14007831e  call    cs:__imp_GetLastError
0x140078325  nop     dword ptr [rax+rax+00h]
0x14007832a  cmp     eax, 0EAh
0x14007832f  jz      short loc_140078379
0x140078331  mov     rcx, cs:WPP_GLOBAL_Control
0x140078338  lea     rdx, WPP_GLOBAL_Control
0x14007833f  cmp     rcx, rdx
0x140078342  jz      loc_140078529
0x140078348  test    byte ptr [rcx+1Ch], 2
0x14007834c  jz      loc_140078529
0x140078352  cmp     byte ptr [rcx+19h], 5
0x140078356  jb      loc_140078529
0x14007835c  mov     edx, 22h ; '"'
0x140078361  mov     rcx, [rcx+10h]
0x140078365  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x14007836c  mov     r9d, eax
0x14007836f  call    WPP_SF_d
0x140078374  jmp     loc_140078529
0x140078379  mov     eax, [rbp+cbBufSize]
0x14007837c  test    eax, eax
0x14007837e  jz      loc_140078499
0x140078384  mov     ecx, eax; dwBytes
0x140078386  call    pMemAlloc
0x14007838b  mov     r15, rax
0x14007838e  test    rax, rax
0x140078391  jnz     short loc_1400783F2
0x140078393  mov     rax, cs:WPP_GLOBAL_Control
0x14007839a  lea     rdx, WPP_GLOBAL_Control
0x1400783a1  cmp     rax, rdx
0x1400783a4  jz      loc_140078529
0x1400783aa  test    byte ptr [rax+1Ch], 2
0x1400783ae  jz      loc_140078529
0x1400783b4  cmp     byte ptr [rax+19h], 5
0x1400783b8  jb      loc_140078529
0x1400783be  call    cs:__imp_GetLastError
0x1400783c5  nop     dword ptr [rax+rax+00h]
0x1400783ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400783d1  lea     edx, [r15+23h]
0x1400783d5  mov     r9d, [rbp+cbBufSize]
0x1400783d9  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400783e0  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x1400783e4  mov     rcx, [rcx+10h]
0x1400783e8  call    WPP_SF_dd
0x1400783ed  jmp     loc_140078529
0x1400783f2  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x1400783f6  lea     rax, [rbp+hService]
0x1400783fa  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x1400783ff  mov     r8, r15; lpServices
0x140078402  lea     rax, [rbp+cbBufSize]
0x140078406  mov     edx, r13d; dwServiceState
0x140078409  mov     rcx, rsi; hService
0x14007840c  mov     [rsp+80h+pcbBytesNeeded], rax; unsigned int
0x140078411  call    cs:__imp_EnumDependentServicesW
0x140078418  nop     dword ptr [rax+rax+00h]
0x14007841d  test    eax, eax
0x14007841f  jnz     short loc_140078469
0x140078421  mov     rax, cs:WPP_GLOBAL_Control
0x140078428  lea     rdx, WPP_GLOBAL_Control
0x14007842f  cmp     rax, rdx
0x140078432  jz      loc_140078529
0x140078438  test    byte ptr [rax+1Ch], 2
0x14007843c  jz      loc_140078529
0x140078442  cmp     byte ptr [rax+19h], 5
0x140078446  jb      loc_140078529
0x14007844c  call    cs:__imp_GetLastError
0x140078453  nop     dword ptr [rax+rax+00h]
0x140078458  mov     rcx, cs:WPP_GLOBAL_Control
0x14007845f  mov     edx, 24h ; '$'
0x140078464  jmp     loc_140078361
0x140078469  xor     ebx, ebx
0x14007846b  cmp     dword ptr [rbp+hService], ebx
0x14007846e  jbe     short loc_140078499
0x140078470  lea     rdx, [rbx+rbx*2]
0x140078474  or      r9d, 0FFFFFFFFh
0x140078478  add     rdx, rdx
0x14007847b  xor     r8d, r8d
0x14007847e  xor     ecx, ecx
0x140078480  mov     rdx, [r15+rdx*8]
0x140078484  call    StopService
0x140078489  test    eax, eax
0x14007848b  jz      loc_140078529
0x140078491  add     ebx, r13d
0x140078494  cmp     ebx, dword ptr [rbp+hService]
0x140078497  jb      short loc_140078470
0x140078499  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x14007849d  mov     edx, r13d; dwControl
0x1400784a0  mov     rcx, rsi; hService
0x1400784a3  call    cs:__imp_ControlService
0x1400784aa  nop     dword ptr [rax+rax+00h]
0x1400784af  test    eax, eax
0x1400784b1  jnz     short loc_1400784FF
0x1400784b3  mov     rax, cs:WPP_GLOBAL_Control
0x1400784ba  lea     rdx, WPP_GLOBAL_Control
0x1400784c1  cmp     rax, rdx
0x1400784c4  jz      short loc_140078529
0x1400784c6  test    byte ptr [rax+1Ch], 2
0x1400784ca  jz      short loc_140078529
0x1400784cc  cmp     byte ptr [rax+19h], 2
0x1400784d0  jb      short loc_140078529
0x1400784d2  call    cs:__imp_GetLastError
0x1400784d9  nop     dword ptr [rax+rax+00h]
0x1400784de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400784e5  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400784ec  mov     edx, 25h ; '%'
0x1400784f1  mov     r9d, eax
0x1400784f4  mov     rcx, [rcx+10h]
0x1400784f8  call    WPP_SF_d
0x1400784fd  jmp     short loc_140078529
0x1400784ff  test    r14d, r14d
0x140078502  jz      loc_1400782D6
0x140078508  mov     r8d, r14d; unsigned int
0x14007850b  mov     rcx, rsi; hService
0x14007850e  call    ?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z; WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)
0x140078513  test    eax, eax
0x140078515  jz      loc_1400782D6
0x14007851b  mov     ecx, eax; dwErrCode
0x14007851d  call    cs:__imp_SetLastError
0x140078524  nop     dword ptr [rax+rax+00h]
0x140078529  mov     rcx, r15; lpMem
0x14007852c  call    pMemFree
0x140078531  mov     rcx, [rbp+hSCObject]; hSCObject
0x140078535  mov     rdx, rsi; SC_HANDLE
0x140078538  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x14007853d  mov     eax, edi
0x14007853f  mov     rcx, [rbp+var_8]
0x140078543  xor     rcx, rsp; StackCookie
0x140078546  call    __security_check_cookie
0x14007854b  lea     r11, [rsp+80h+var_s0]
0x140078553  mov     rbx, [r11+30h]
0x140078557  mov     rsi, [r11+40h]
0x14007855b  mov     rsp, r11
0x14007855e  pop     r15
0x140078560  pop     r14
0x140078562  pop     r13
0x140078564  pop     rdi
0x140078565  pop     rbp
0x140078566  retn
```
