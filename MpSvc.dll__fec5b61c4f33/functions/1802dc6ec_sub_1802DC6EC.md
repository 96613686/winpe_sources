# sub_1802DC6EC

- ea: `0x1802dc6ec`
- end: `0x1802dcc48`
- name: `sub_1802DC6EC`
- size: `1372`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180126388`

## callees

- `0x180034fa8`
- `0x1800452b8`
- `0x18004533c`
- `0x180067aec`
- `0x1800a8590`
- `0x1800a9720`
- `0x1800a9750`
- `0x1800e9078`
- `0x1800fe15c`
- `0x180168808`
- `0x1801747cc`
- `0x1802d5cfc`
- `0x1802dc6ec`
- `0x1804731a0`

## import_xrefs

- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc853`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc862`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc871`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc880`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc853`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc862`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc871`
- `MpClient!MpConfigUnregisterNotifications` at `0x1802dc880`
- `MpClient!MpFreeMemory` at `0x1802dc818`
- `MpClient!MpFreeMemory` at `0x1802dc835`
- `MpClient!MpFreeMemory` at `0x1802dc844`
- `MpClient!MpFreeMemory` at `0x1802dc818`
- `MpClient!MpFreeMemory` at `0x1802dc835`
- `MpClient!MpFreeMemory` at `0x1802dc844`
- `KERNEL32!DebugBreak` at `0x1802dc761`
- `KERNEL32!DebugBreak` at `0x1802dc761`
- `KERNEL32!CloseHandle` at `0x1802dc90d`
- `KERNEL32!CloseHandle` at `0x1802dc979`
- `KERNEL32!CloseHandle` at `0x1802dc9db`
- `KERNEL32!CloseHandle` at `0x1802dca40`
- `KERNEL32!CloseHandle` at `0x1802dcaa5`
- `KERNEL32!CloseHandle` at `0x1802dcb0c`
- `KERNEL32!CloseHandle` at `0x1802dcb73`
- `KERNEL32!CloseHandle` at `0x1802dc90d`
- `KERNEL32!CloseHandle` at `0x1802dc979`
- `KERNEL32!CloseHandle` at `0x1802dc9db`
- `KERNEL32!CloseHandle` at `0x1802dca40`
- `KERNEL32!CloseHandle` at `0x1802dcaa5`
- `KERNEL32!CloseHandle` at `0x1802dcb0c`
- `KERNEL32!CloseHandle` at `0x1802dcb73`

## string_xrefs

- `0x1802dc957`: `[DC] UtilCreateEvent(m_hNetworkRefreshNotify) failed with hr=%#lx`
- `0x1802dcbbd`: `[DC] UtilCreateEvent(m_hDeviceEncryptionStateRefreshNotify) failed with hr=%#lx`
- `0x1802dcb58`: `[DC] UtilCreateEvent(m_hEnableDisableTransitionInProgress) failed with hr=%#lx`
- `0x1802dcaf1`: `[DC] UtilCreateEvent(m_hShutdownInProgress) failed with hr=%#lx`
- `0x1802dca8a`: `[DC] UtilCreateEvent(m_hDriverConnectNotify) failed with hr=%#lx`
- `0x1802dca25`: `[DC] UtilCreateEvent(m_hSessionChangeNotify) failed with hr=%#lx`
- `0x1802dc9c3`: `[DC] UtilCreateEvent(m_hVPNConnectionsRefreshNotify) failed with hr=%#lx`

## pseudocode

```c
__int64 __fastcall sub_1802DC6EC(__int64 a1)
{
  unsigned int v2; // ebx
  int v4; // eax
  unsigned int v5; // edi
  HANDLE *v6; // rdi
  int v7; // eax
  unsigned int v8; // edi
  HANDLE *v9; // rdi
  int v10; // eax
  HANDLE *v11; // rdi
  int v12; // eax
  HANDLE *v13; // rdi
  int v14; // eax
  HANDLE *v15; // rdi
  int v16; // eax
  HANDLE *v17; // rdi
  int v18; // eax
  HANDLE *v19; // rdi
  int v20; // eax
  __int64 v21; // [rsp+38h] [rbp-79h] BYREF
  __int64 v22; // [rsp+40h] [rbp-71h]
  __int128 v23; // [rsp+48h] [rbp-69h]
  __int64 v24; // [rsp+58h] [rbp-59h]
  _BYTE v25[68]; // [rsp+60h] [rbp-51h] BYREF
  int v26; // [rsp+A4h] [rbp-Dh]
  __int64 v27; // [rsp+A8h] [rbp-9h]
  __int64 v28; // [rsp+B0h] [rbp-1h]
  LPVOID lpMem[2]; // [rsp+B8h] [rbp+7h]
  __int64 v30; // [rsp+C8h] [rbp+17h]
  __int64 v31; // [rsp+D0h] [rbp+1Fh]
  __int128 v32; // [rsp+D8h] [rbp+27h]
  __int64 v33; // [rsp+E8h] [rbp+37h]

  if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    sub_1800A9720(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 36, &stru_18050FE88);
  sub_1800E9078(L"[DC] Entering CDeviceControlEngine::Initialize.");
  v2 = 0;
  if ( (unsigned int)sub_1800A8590(L"MpDc_Debug") )
    DebugBreak();
  sub_1800FE15C(qword_18050FFC0, sub_1800FDEF0, qword_1805DDFB0, qword_1805DDFB0);
  sub_1800452B8(a1 + 16);
  if ( *(_DWORD *)(a1 + 8) == 4 )
  {
    v2 = -2147467259;
LABEL_9:
    sub_18004533C((LPCRITICAL_SECTION)(a1 + 16));
    return v2;
  }
  if ( *(_DWORD *)(a1 + 8) )
    goto LABEL_9;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v26 = 0;
  sub_1804731A0(v25, 0, 72);
  v27 = 0;
  v28 = 0;
  *(_OWORD *)lpMem = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  sub_1802D5CFC(a1 + 1336, &v21);
  if ( (_QWORD)v32 )
    MpFreeMemory(v32);
  if ( lpMem[1] )
    sub_180067AEC(lpMem[1]);
  if ( lpMem[0] )
    MpFreeMemory(lpMem[0]);
  if ( v27 )
    MpFreeMemory(v27);
  if ( v24 )
    MpConfigUnregisterNotifications();
  if ( *((_QWORD *)&v23 + 1) )
    MpConfigUnregisterNotifications();
  if ( (_QWORD)v23 )
    MpConfigUnregisterNotifications();
  if ( v22 )
    MpConfigUnregisterNotifications();
  *(_QWORD *)(a1 + 1336) = a1;
  *(_OWORD *)(a1 + 1544) = 0;
  *(_BYTE *)(a1 + 1008) = 0;
  *(_BYTE *)(a1 + 1560) = sub_180168808();
  *(_BYTE *)(a1 + 1561) = _InterlockedCompareExchange(&dword_1806078E8, 0, 0) != 0;
  v4 = sub_1801747CC(a1 + 1564);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 2) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 37, &stru_18050FE88, (unsigned int)v4);
    sub_1800E9078(L"[DC] SvcGetRunningMode failed with hr=%#lx", v5);
  }
  v6 = (HANDLE *)(a1 + 1024);
  if ( *(_QWORD *)(a1 + 1024) )
  {
    CloseHandle(*v6);
    *v6 = 0;
  }
  v7 = sub_180034FA8((_QWORD *)(a1 + 1024), 0, 0, 0, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = (HANDLE *)(a1 + 1032);
    if ( *(_QWORD *)(a1 + 1032) )
    {
      CloseHandle(*v9);
      *v9 = 0;
    }
    v10 = sub_180034FA8((_QWORD *)(a1 + 1032), 0, 0, 0, 0);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v11 = (HANDLE *)(a1 + 1040);
      if ( *(_QWORD *)(a1 + 1040) )
      {
        CloseHandle(*v11);
        *v11 = 0;
      }
      v12 = sub_180034FA8((_QWORD *)(a1 + 1040), 0, 0, 0, 0);
      v8 = v12;
      if ( v12 >= 0 )
      {
        v13 = (HANDLE *)(a1 + 1048);
        if ( *(_QWORD *)(a1 + 1048) )
        {
          CloseHandle(*v13);
          *v13 = 0;
        }
        v14 = sub_180034FA8((_QWORD *)(a1 + 1048), 0, 0, 0, 0);
        v8 = v14;
        if ( v14 >= 0 )
        {
          v15 = (HANDLE *)(a1 + 1056);
          if ( *(_QWORD *)(a1 + 1056) )
          {
            CloseHandle(*v15);
            *v15 = 0;
          }
          v16 = sub_180034FA8((_QWORD *)(a1 + 1056), 1, 0, 0, 0);
          v8 = v16;
          if ( v16 >= 0 )
          {
            v17 = (HANDLE *)(a1 + 1064);
            if ( *(_QWORD *)(a1 + 1064) )
            {
              CloseHandle(*v17);
              *v17 = 0;
            }
            v18 = sub_180034FA8((_QWORD *)(a1 + 1064), 1, 1, 0, 0);
            v8 = v18;
            if ( v18 >= 0 )
            {
              v19 = (HANDLE *)(a1 + 2896);
              if ( *(_QWORD *)(a1 + 2896) )
              {
                CloseHandle(*v19);
                *v19 = 0;
              }
              v20 = sub_180034FA8((_QWORD *)(a1 + 2896), 0, 0, 0, 0);
              v8 = v20;
              if ( v20 >= 0 )
              {
                xmmword_1805DDF9C = xmmword_18050FF60;
                *(_DWORD *)(a1 + 8) = 1;
                *(_DWORD *)(a1 + 1568) = 1;
              }
              else
              {
                if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType
                  && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
                {
                  sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 44, &stru_18050FE88, (unsigned int)v20);
                }
                sub_1800E9078(L"[DC] UtilCreateEvent(m_hDeviceEncryptionStateRefreshNotify) failed with hr=%#lx", v8);
              }
            }
            else
            {
              if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType
                && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
              {
                sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 43, &stru_18050FE88, (unsigned int)v18);
              }
              sub_1800E9078(L"[DC] UtilCreateEvent(m_hEnableDisableTransitionInProgress) failed with hr=%#lx", v8);
            }
          }
          else
          {
            if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
              sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 42, &stru_18050FE88, (unsigned int)v16);
            sub_1800E9078(L"[DC] UtilCreateEvent(m_hShutdownInProgress) failed with hr=%#lx", v8);
          }
        }
        else
        {
          if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
            sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 41, &stru_18050FE88, (unsigned int)v14);
          sub_1800E9078(L"[DC] UtilCreateEvent(m_hDriverConnectNotify) failed with hr=%#lx", v8);
        }
      }
      else
      {
        if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
          sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 40, &stru_18050FE88, (unsigned int)v12);
        sub_1800E9078(L"[DC] UtilCreateEvent(m_hSessionChangeNotify) failed with hr=%#lx", v8);
      }
    }
    else
    {
      if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
        sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 39, &stru_18050FE88, (unsigned int)v10);
      sub_1800E9078(L"[DC] UtilCreateEvent(m_hVPNConnectionsRefreshNotify) failed with hr=%#lx", v8);
    }
  }
  else
  {
    if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 1) != 0 )
      sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 38, &stru_18050FE88, (unsigned int)v7);
    sub_1800E9078(L"[DC] UtilCreateEvent(m_hNetworkRefreshNotify) failed with hr=%#lx", v8);
  }
  sub_18004533C((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(COMPUTER_NAME_FORMAT **)&NameType != &NameType && (*(_BYTE *)(*(_QWORD *)&NameType + 28LL) & 4) != 0 )
    sub_1800A9750(*(_QWORD *)(*(_QWORD *)&NameType + 16LL), 45, &stru_18050FE88, v8);
  sub_1800E9078(L"[DC] Leaving CDeviceControlEngine::Initialize(%#lx).", v8);
  return v8;
}

```

## disassembly

```asm
0x1802dc6ec  mov     rax, rsp
0x1802dc6ef  mov     [rax+8], rbx
0x1802dc6f3  mov     [rax+10h], rsi
0x1802dc6f7  mov     [rax+18h], rdi
0x1802dc6fb  mov     [rax+20h], r12
0x1802dc6ff  push    rbp
0x1802dc700  push    r14
0x1802dc702  push    r15
0x1802dc704  lea     rbp, [rax-5Fh]
0x1802dc708  sub     rsp, 0F0h
0x1802dc70f  mov     rsi, rcx
0x1802dc712  mov     rcx, cs:NameType
0x1802dc719  lea     r15, NameType
0x1802dc720  lea     r12, stru_18050FE88
0x1802dc727  cmp     rcx, r15
0x1802dc72a  jz      short loc_1802DC743
0x1802dc72c  test    byte ptr [rcx+1Ch], 4
0x1802dc730  jz      short loc_1802DC743
0x1802dc732  mov     rcx, [rcx+10h]
0x1802dc736  mov     edx, 24h ; '$'
0x1802dc73b  mov     r8, r12
0x1802dc73e  call    sub_1800A9720
0x1802dc743  lea     rcx, aDcEnteringCdev_2; "[DC] Entering CDeviceControlEngine::Ini"...
0x1802dc74a  call    sub_1800E9078
0x1802dc74f  lea     rcx, aMpdcDebug; "MpDc_Debug"
0x1802dc756  call    sub_1800A8590
0x1802dc75b  xor     ebx, ebx
0x1802dc75d  test    eax, eax
0x1802dc75f  jz      short loc_1802DC767
0x1802dc761  call    cs:__imp_DebugBreak
0x1802dc767  lea     r8, qword_1805DDFB0
0x1802dc76e  mov     r9, r8
0x1802dc771  lea     rdx, sub_1800FDEF0
0x1802dc778  lea     rcx, qword_18050FFC0
0x1802dc77f  call    sub_1800FE15C
0x1802dc784  lea     r14, [rsi+10h]
0x1802dc788  mov     rcx, r14
0x1802dc78b  call    sub_1800452B8
0x1802dc790  cmp     dword ptr [rsi+8], 4
0x1802dc794  jnz     short loc_1802DC79D
0x1802dc796  mov     ebx, 80004005h
0x1802dc79b  jmp     short loc_1802DC7A2
0x1802dc79d  cmp     [rsi+8], ebx
0x1802dc7a0  jz      short loc_1802DC7B1
0x1802dc7a2  mov     rcx, r14; lpCriticalSection
0x1802dc7a5  call    sub_18004533C
0x1802dc7aa  mov     eax, ebx
0x1802dc7ac  jmp     loc_1802DCC27
0x1802dc7b1  xor     eax, eax
0x1802dc7b3  mov     [rbp+57h+var_C8], rbx
0x1802dc7b7  xorps   xmm0, xmm0
0x1802dc7ba  mov     [rbp+57h+var_D0], rax
0x1802dc7be  xor     edx, edx
0x1802dc7c0  movdqa  [rbp+57h+var_C0], xmm0
0x1802dc7c5  lea     rcx, [rbp+57h+var_A8]
0x1802dc7c9  mov     [rbp+57h+var_B0], rbx
0x1802dc7cd  lea     r8d, [rax+48h]
0x1802dc7d1  mov     [rbp+57h+var_64], eax
0x1802dc7d4  call    sub_1804731A0
0x1802dc7d9  xor     eax, eax
0x1802dc7db  mov     [rbp+57h+var_60], rbx
0x1802dc7df  xorps   xmm0, xmm0
0x1802dc7e2  mov     [rbp+57h+var_58], rax
0x1802dc7e6  lea     rdi, [rsi+538h]
0x1802dc7ed  movdqa  xmmword ptr [rbp+57h+lpMem], xmm0
0x1802dc7f2  mov     rcx, rdi
0x1802dc7f5  mov     [rbp+57h+var_40], rax
0x1802dc7f9  lea     rdx, [rbp+57h+var_D0]
0x1802dc7fd  mov     [rbp+57h+var_38], rax
0x1802dc801  movdqa  [rbp+57h+var_30], xmm0
0x1802dc806  mov     [rbp+57h+var_20], rbx
0x1802dc80a  call    sub_1802D5CFC
0x1802dc80f  mov     rcx, qword ptr [rbp+57h+var_30]
0x1802dc813  test    rcx, rcx
0x1802dc816  jz      short loc_1802DC81E
0x1802dc818  call    cs:__imp_MpFreeMemory
0x1802dc81e  mov     rcx, [rbp+57h+lpMem+8]; lpMem
0x1802dc822  test    rcx, rcx
0x1802dc825  jz      short loc_1802DC82C
0x1802dc827  call    sub_180067AEC
0x1802dc82c  mov     rcx, [rbp+57h+lpMem]
0x1802dc830  test    rcx, rcx
0x1802dc833  jz      short loc_1802DC83B
0x1802dc835  call    cs:__imp_MpFreeMemory
0x1802dc83b  mov     rcx, [rbp+57h+var_60]
0x1802dc83f  test    rcx, rcx
0x1802dc842  jz      short loc_1802DC84A
0x1802dc844  call    cs:__imp_MpFreeMemory
0x1802dc84a  mov     rcx, [rbp+57h+var_B0]
0x1802dc84e  test    rcx, rcx
0x1802dc851  jz      short loc_1802DC859
0x1802dc853  call    cs:MpConfigUnregisterNotifications
0x1802dc859  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x1802dc85d  test    rcx, rcx
0x1802dc860  jz      short loc_1802DC868
0x1802dc862  call    cs:MpConfigUnregisterNotifications
0x1802dc868  mov     rcx, qword ptr [rbp+57h+var_C0]
0x1802dc86c  test    rcx, rcx
0x1802dc86f  jz      short loc_1802DC877
0x1802dc871  call    cs:MpConfigUnregisterNotifications
0x1802dc877  mov     rcx, [rbp+57h+var_C8]
0x1802dc87b  test    rcx, rcx
0x1802dc87e  jz      short loc_1802DC886
0x1802dc880  call    cs:MpConfigUnregisterNotifications
0x1802dc886  xorps   xmm0, xmm0
0x1802dc889  mov     [rdi], rsi
0x1802dc88c  movdqu  xmmword ptr [rsi+608h], xmm0
0x1802dc894  mov     [rsi+3F0h], bl
0x1802dc89a  call    sub_180168808
0x1802dc89f  mov     [rsi+618h], al
0x1802dc8a5  xor     eax, eax
0x1802dc8a7  lock cmpxchg cs:dword_1806078E8, ebx
0x1802dc8af  setnz   cl
0x1802dc8b2  mov     [rsi+619h], cl
0x1802dc8b8  lea     rcx, [rsi+61Ch]
0x1802dc8bf  call    sub_1801747CC
0x1802dc8c4  mov     edi, eax
0x1802dc8c6  test    eax, eax
0x1802dc8c8  jns     short loc_1802DC8FE
0x1802dc8ca  mov     rcx, cs:NameType
0x1802dc8d1  cmp     rcx, r15
0x1802dc8d4  jz      short loc_1802DC8F0
0x1802dc8d6  test    byte ptr [rcx+1Ch], 2
0x1802dc8da  jz      short loc_1802DC8F0
0x1802dc8dc  mov     rcx, [rcx+10h]
0x1802dc8e0  mov     edx, 25h ; '%'
0x1802dc8e5  mov     r9d, eax
0x1802dc8e8  mov     r8, r12
0x1802dc8eb  call    sub_1800A9750
0x1802dc8f0  mov     edx, edi
0x1802dc8f2  lea     rcx, aDcSvcgetrunnin; "[DC] SvcGetRunningMode failed with hr=%"...
0x1802dc8f9  call    sub_1800E9078
0x1802dc8fe  lea     rdi, [rsi+400h]
0x1802dc905  cmp     [rdi], rbx
0x1802dc908  jz      short loc_1802DC916
0x1802dc90a  mov     rcx, [rdi]; hObject
0x1802dc90d  call    cs:CloseHandle
0x1802dc913  mov     [rdi], rbx
0x1802dc916  xor     r9d, r9d; int
0x1802dc919  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dc91e  xor     r8d, r8d; int
0x1802dc921  xor     edx, edx; int
0x1802dc923  mov     rcx, rdi; int
0x1802dc926  call    sub_180034FA8
0x1802dc92b  mov     edi, eax
0x1802dc92d  test    eax, eax
0x1802dc92f  jns     short loc_1802DC96A
0x1802dc931  mov     rcx, cs:NameType
0x1802dc938  cmp     rcx, r15
0x1802dc93b  jz      short loc_1802DC957
0x1802dc93d  test    byte ptr [rcx+1Ch], 1
0x1802dc941  jz      short loc_1802DC957
0x1802dc943  mov     rcx, [rcx+10h]
0x1802dc947  mov     edx, 26h ; '&'
0x1802dc94c  mov     r9d, eax
0x1802dc94f  mov     r8, r12
0x1802dc952  call    sub_1800A9750
0x1802dc957  lea     rcx, aDcUtilcreateev; "[DC] UtilCreateEvent(m_hNetworkRefreshN"...
0x1802dc95e  mov     edx, edi
0x1802dc960  call    sub_1800E9078
0x1802dc965  jmp     loc_1802DCBE9
0x1802dc96a  lea     rdi, [rsi+408h]
0x1802dc971  cmp     [rdi], rbx
0x1802dc974  jz      short loc_1802DC982
0x1802dc976  mov     rcx, [rdi]; hObject
0x1802dc979  call    cs:CloseHandle
0x1802dc97f  mov     [rdi], rbx
0x1802dc982  xor     r9d, r9d; int
0x1802dc985  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dc98a  xor     r8d, r8d; int
0x1802dc98d  xor     edx, edx; int
0x1802dc98f  mov     rcx, rdi; int
0x1802dc992  call    sub_180034FA8
0x1802dc997  mov     edi, eax
0x1802dc999  test    eax, eax
0x1802dc99b  jns     short loc_1802DC9CC
0x1802dc99d  mov     rcx, cs:NameType
0x1802dc9a4  cmp     rcx, r15
0x1802dc9a7  jz      short loc_1802DC9C3
0x1802dc9a9  test    byte ptr [rcx+1Ch], 1
0x1802dc9ad  jz      short loc_1802DC9C3
0x1802dc9af  mov     rcx, [rcx+10h]
0x1802dc9b3  mov     edx, 27h ; '''
0x1802dc9b8  mov     r9d, eax
0x1802dc9bb  mov     r8, r12
0x1802dc9be  call    sub_1800A9750
0x1802dc9c3  lea     rcx, aDcUtilcreateev_0; "[DC] UtilCreateEvent(m_hVPNConnectionsR"...
0x1802dc9ca  jmp     short loc_1802DC95E
0x1802dc9cc  lea     rdi, [rsi+410h]
0x1802dc9d3  cmp     [rdi], rbx
0x1802dc9d6  jz      short loc_1802DC9E4
0x1802dc9d8  mov     rcx, [rdi]; hObject
0x1802dc9db  call    cs:CloseHandle
0x1802dc9e1  mov     [rdi], rbx
0x1802dc9e4  xor     r9d, r9d; int
0x1802dc9e7  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dc9ec  xor     r8d, r8d; int
0x1802dc9ef  xor     edx, edx; int
0x1802dc9f1  mov     rcx, rdi; int
0x1802dc9f4  call    sub_180034FA8
0x1802dc9f9  mov     edi, eax
0x1802dc9fb  test    eax, eax
0x1802dc9fd  jns     short loc_1802DCA31
0x1802dc9ff  mov     rcx, cs:NameType
0x1802dca06  cmp     rcx, r15
0x1802dca09  jz      short loc_1802DCA25
0x1802dca0b  test    byte ptr [rcx+1Ch], 1
0x1802dca0f  jz      short loc_1802DCA25
0x1802dca11  mov     rcx, [rcx+10h]
0x1802dca15  mov     edx, 28h ; '('
0x1802dca1a  mov     r9d, eax
0x1802dca1d  mov     r8, r12
0x1802dca20  call    sub_1800A9750
0x1802dca25  lea     rcx, aDcUtilcreateev_1; "[DC] UtilCreateEvent(m_hSessionChangeNo"...
0x1802dca2c  jmp     loc_1802DC95E
0x1802dca31  lea     rdi, [rsi+418h]
0x1802dca38  cmp     [rdi], rbx
0x1802dca3b  jz      short loc_1802DCA49
0x1802dca3d  mov     rcx, [rdi]; hObject
0x1802dca40  call    cs:CloseHandle
0x1802dca46  mov     [rdi], rbx
0x1802dca49  xor     r9d, r9d; int
0x1802dca4c  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dca51  xor     r8d, r8d; int
0x1802dca54  xor     edx, edx; int
0x1802dca56  mov     rcx, rdi; int
0x1802dca59  call    sub_180034FA8
0x1802dca5e  mov     edi, eax
0x1802dca60  test    eax, eax
0x1802dca62  jns     short loc_1802DCA96
0x1802dca64  mov     rcx, cs:NameType
0x1802dca6b  cmp     rcx, r15
0x1802dca6e  jz      short loc_1802DCA8A
0x1802dca70  test    byte ptr [rcx+1Ch], 1
0x1802dca74  jz      short loc_1802DCA8A
0x1802dca76  mov     rcx, [rcx+10h]
0x1802dca7a  mov     edx, 29h ; ')'
0x1802dca7f  mov     r9d, eax
0x1802dca82  mov     r8, r12
0x1802dca85  call    sub_1800A9750
0x1802dca8a  lea     rcx, aDcUtilcreateev_2; "[DC] UtilCreateEvent(m_hDriverConnectNo"...
0x1802dca91  jmp     loc_1802DC95E
0x1802dca96  lea     rdi, [rsi+420h]
0x1802dca9d  cmp     [rdi], rbx
0x1802dcaa0  jz      short loc_1802DCAAE
0x1802dcaa2  mov     rcx, [rdi]; hObject
0x1802dcaa5  call    cs:CloseHandle
0x1802dcaab  mov     [rdi], rbx
0x1802dcaae  xor     r9d, r9d; int
0x1802dcab1  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dcab6  xor     r8d, r8d; int
0x1802dcab9  mov     rcx, rdi; int
0x1802dcabc  lea     edx, [r9+1]; int
0x1802dcac0  call    sub_180034FA8
0x1802dcac5  mov     edi, eax
0x1802dcac7  test    eax, eax
0x1802dcac9  jns     short loc_1802DCAFD
0x1802dcacb  mov     rcx, cs:NameType
0x1802dcad2  cmp     rcx, r15
0x1802dcad5  jz      short loc_1802DCAF1
0x1802dcad7  test    byte ptr [rcx+1Ch], 1
0x1802dcadb  jz      short loc_1802DCAF1
0x1802dcadd  mov     rcx, [rcx+10h]
0x1802dcae1  mov     edx, 2Ah ; '*'
0x1802dcae6  mov     r9d, eax
0x1802dcae9  mov     r8, r12
0x1802dcaec  call    sub_1800A9750
0x1802dcaf1  lea     rcx, aDcUtilcreateev_3; "[DC] UtilCreateEvent(m_hShutdownInProgr"...
0x1802dcaf8  jmp     loc_1802DC95E
0x1802dcafd  lea     rdi, [rsi+428h]
0x1802dcb04  cmp     [rdi], rbx
0x1802dcb07  jz      short loc_1802DCB15
0x1802dcb09  mov     rcx, [rdi]; hObject
0x1802dcb0c  call    cs:CloseHandle
0x1802dcb12  mov     [rdi], rbx
0x1802dcb15  xor     r9d, r9d; int
0x1802dcb18  mov     [rsp+100h+lpEventAttributes], rbx; lpEventAttributes
0x1802dcb1d  mov     rcx, rdi; int
0x1802dcb20  lea     edx, [r9+1]; int
0x1802dcb24  mov     r8d, edx; int
0x1802dcb27  call    sub_180034FA8
0x1802dcb2c  mov     edi, eax
0x1802dcb2e  test    eax, eax
0x1802dcb30  jns     short loc_1802DCB64
0x1802dcb32  mov     rcx, cs:NameType
0x1802dcb39  cmp     rcx, r15
0x1802dcb3c  jz      short loc_1802DCB58
0x1802dcb3e  test    byte ptr [rcx+1Ch], 1
0x1802dcb42  jz      short loc_1802DCB58
0x1802dcb44  mov     rcx, [rcx+10h]
0x1802dcb48  mov     edx, 2Bh ; '+'
0x1802dcb4d  mov     r9d, eax
0x1802dcb50  mov     r8, r12
0x1802dcb53  call    sub_1800A9750
0x1802dcb58  lea     rcx, aDcUtilcreateev_4; "[DC] UtilCreateEvent(m_hEnableDisableTr"...
0x1802dcb5f  jmp     loc_1802DC95E
0x1802dcb64  lea     rdi, [rsi+0B50h]
0x1802dcb6b  cmp     [rdi], rbx
0x1802dcb6e  jz      short loc_1802DCB7C
0x1802dcb70  mov     rcx, [rdi]; hObject
  ... truncated ...
```
