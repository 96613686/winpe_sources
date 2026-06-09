# DfsPeriodicDcUpdate

- ea: `0x18002d080`
- end: `0x18002d341`
- name: `DfsPeriodicDcUpdate`
- size: `705`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180005ac0`
- `0x1800071d8`
- `0x1800082f0`
- `0x18000a600`
- `0x18000a6d0`
- `0x18001e420`
- `0x18002d080`
- `0x18002d348`
- `0x18002f42c`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18002d1e1`
- `ntdll!WinSqmSetDWORD` at `0x18002d2a1`
- `ntdll!WinSqmSetDWORD` at `0x18002d1e1`
- `ntdll!WinSqmSetDWORD` at `0x18002d2a1`
- `ntdll!RtlDeregisterWait` at `0x18002d0c7`
- `ntdll!RtlDeregisterWait` at `0x18002d0c7`
- `ntdll!RtlRegisterWait` at `0x18002d303`
- `ntdll!RtlRegisterWait` at `0x18002d303`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d168`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d31f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d168`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d31f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d200`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d240`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d200`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d240`

## pseudocode

```c
void __fastcall DfsPeriodicDcUpdate(PVOID a1, __int64 a2)
{
  char v2; // si
  ULONG ulMilliseconds; // edi
  int v5; // ebx
  unsigned int v6; // edx
  int v7; // ecx
  int DCName; // edi
  int v9; // ebx
  int v10; // eax
  unsigned int DelayInterval; // eax
  BOOL v12; // eax
  int v13; // eax
  _WORD v14[2]; // [rsp+30h] [rbp-29h] BYREF
  BOOL v15; // [rsp+34h] [rbp-25h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v17[3]; // [rsp+48h] [rbp-11h] BYREF

  v2 = a2;
  LOBYTE(v14[0]) = 0;
  if ( (unsigned int)WsIsTerminating(a1, a2) )
    goto LABEL_36;
  ulMilliseconds = -1;
  RtlDeregisterWait(g_WsDomainNameChangeWorkItem);
  v5 = WsInAWorkgroup();
  if ( v2 )
  {
    if ( !v5 )
    {
      v6 = g_ulCount;
LABEL_7:
      v7 = 0;
      if ( v6 > g_ulInitThreshold )
        v7 = 256;
      DCName = DfsGetDCName(v7, v14);
      v9 = 1;
      if ( DCName )
      {
        if ( LOBYTE(v14[0]) || g_ulForce < (unsigned int)g_ulForceThreshold )
          goto LABEL_14;
        DCName = DfsGetDCName(1, v14);
      }
      g_ulForce = 0;
LABEL_14:
      if ( MupEventSignaled )
      {
        v10 = DfsSqmWrapper::gm_IsWinSqmEnabled;
        v14[0] = 0;
        memset(v17, 0, 44);
        if ( DfsSqmWrapper::gm_IsWinSqmEnabled )
        {
          if ( !DfsSqmClient::gm_RegDone )
          {
            if ( !(unsigned int)DfsSqmGetClientDP(393576, 0, 0, (unsigned int)v17, 44) )
            {
              DfsSqmClient::DfsSqmSetClientRegDP((struct DFSC_REGISTRY_SETTINGS *)v17);
              DfsSqmClient::gm_RegDone = 1;
            }
            DelayInterval = DfsGetDelayInterval();
            WinSqmSetDWORD(0, 4540, DelayInterval);
            v10 = DfsSqmWrapper::gm_IsWinSqmEnabled;
          }
          if ( v10 )
          {
            SystemTime = 0;
            GetLocalTime(&SystemTime);
            if ( SystemTime.wHour == 6 * (SystemTime.wHour / 6u) && DfsSqmClient::gm_wHour )
            {
              DfsSqmClient::gm_wHour = SystemTime.wHour % 6u;
              SystemTime = 0;
              GetLocalTime(&SystemTime);
              v12 = 0;
              if ( !SystemTime.wDayOfWeek )
                v12 = DfsSqmClient::gm_wDayOfWeek != 0;
              DfsSqmClient::gm_wDayOfWeek = SystemTime.wDayOfWeek;
              v15 = v12;
              if ( !(unsigned int)DfsSqmGetClientDP(393580, (unsigned int)&v15, 4, (unsigned int)v14, 2)
                && DfsSqmWrapper::gm_IsWinSqmEnabled )
              {
                WinSqmSetDWORD(0, 3924, v14[0]);
              }
            }
            else
            {
              DfsSqmClient::gm_wHour = SystemTime.wHour % 6u;
            }
          }
        }
      }
      else
      {
        SetEvent(hMupEvent);
        MupEventSignaled = 1;
      }
      if ( !DCName || (v13 = g_ulCount, g_ulCount >= (unsigned int)g_ulInitThreshold) )
      {
        v9 = DfsGetDelayInterval();
        v13 = g_ulCount;
      }
      g_ulForce += v9;
      g_ulCount = v9 + v13;
      ulMilliseconds = 60000 * v9;
    }
  }
  else
  {
    WsSetWorkStationDomainName();
    if ( !v5 )
    {
      v6 = 0;
      g_ulCount = 0;
      g_ulForce = g_ulForceThreshold;
      goto LABEL_7;
    }
  }
  if ( RtlRegisterWait(&g_WsDomainNameChangeWorkItem, a1, DfsPeriodicDcUpdate, a1, ulMilliseconds, 0x19u) >= 0 )
    return;
  g_WsDomainNameChangeWorkItem = (HANDLE)-1LL;
LABEL_36:
  SetEvent(WsDfsTearDownDoneEvent);
}

```

## disassembly

```asm
0x18002d080  push    rbp
0x18002d082  push    rbx
0x18002d083  push    rsi
0x18002d084  push    rdi
0x18002d085  push    r14
0x18002d087  push    r15
0x18002d089  lea     rbp, [rsp-2Fh]
0x18002d08e  sub     rsp, 88h
0x18002d095  mov     rax, cs:__security_cookie
0x18002d09c  xor     rax, rsp
0x18002d09f  mov     [rbp+57h+var_38], rax
0x18002d0a3  xor     r15d, r15d
0x18002d0a6  mov     sil, dl
0x18002d0a9  mov     byte ptr [rbp+57h+var_80], r15b
0x18002d0ad  mov     r14, rcx
0x18002d0b0  call    WsIsTerminating
0x18002d0b5  test    eax, eax
0x18002d0b7  jnz     loc_18002D318
0x18002d0bd  mov     rcx, cs:g_WsDomainNameChangeWorkItem; hWaitHandle
0x18002d0c4  or      edi, 0FFFFFFFFh
0x18002d0c7  call    cs:__imp_RtlDeregisterWait
0x18002d0cd  call    WsInAWorkgroup
0x18002d0d2  mov     ebx, eax
0x18002d0d4  test    sil, sil
0x18002d0d7  jnz     short loc_18002D0FD
0x18002d0d9  call    WsSetWorkStationDomainName
0x18002d0de  test    ebx, ebx
0x18002d0e0  jnz     loc_18002D2E3
0x18002d0e6  mov     eax, cs:g_ulForceThreshold
0x18002d0ec  mov     edx, r15d
0x18002d0ef  mov     cs:g_ulCount, edx
0x18002d0f5  mov     cs:g_ulForce, eax
0x18002d0fb  jmp     short loc_18002D10B
0x18002d0fd  test    ebx, ebx
0x18002d0ff  jnz     loc_18002D2E3
0x18002d105  mov     edx, cs:g_ulCount
0x18002d10b  cmp     edx, cs:g_ulInitThreshold
0x18002d111  mov     ecx, r15d
0x18002d114  mov     eax, 100h
0x18002d119  lea     rdx, [rbp+57h+var_80]
0x18002d11d  cmova   ecx, eax
0x18002d120  call    DfsGetDCName
0x18002d125  mov     edi, eax
0x18002d127  mov     ebx, 1
0x18002d12c  test    eax, eax
0x18002d12e  jz      short loc_18002D151
0x18002d130  cmp     byte ptr [rbp+57h+var_80], r15b
0x18002d134  jnz     short loc_18002D158
0x18002d136  mov     ecx, cs:g_ulForceThreshold
0x18002d13c  cmp     cs:g_ulForce, ecx
0x18002d142  jb      short loc_18002D158
0x18002d144  lea     rdx, [rbp+57h+var_80]
0x18002d148  mov     ecx, ebx
0x18002d14a  call    DfsGetDCName
0x18002d14f  mov     edi, eax
0x18002d151  mov     cs:g_ulForce, r15d
0x18002d158  cmp     cs:MupEventSignaled, r15b
0x18002d15f  jnz     short loc_18002D179
0x18002d161  mov     rcx, cs:hMupEvent; hEvent
0x18002d168  call    cs:__imp_SetEvent
0x18002d16e  mov     cs:MupEventSignaled, bl
0x18002d174  jmp     loc_18002D2B0
0x18002d179  mov     eax, cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002d17f  xorps   xmm0, xmm0
0x18002d182  mov     [rbp+57h+var_80], r15w
0x18002d187  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18002d18b  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x18002d18f  movups  [rbp+57h+var_68], xmm0
0x18002d193  test    eax, eax
0x18002d195  jz      loc_18002D2B0
0x18002d19b  cmp     cs:?gm_RegDone@DfsSqmClient@@2EA, r15b; uchar DfsSqmClient::gm_RegDone
0x18002d1a2  jnz     short loc_18002D1ED
0x18002d1a4  lea     r9, [rbp+57h+var_68]
0x18002d1a8  mov     [rsp+0B0h+ulMilliseconds], 2Ch ; ','
0x18002d1b0  xor     r8d, r8d
0x18002d1b3  xor     edx, edx
0x18002d1b5  mov     ecx, 60168h
0x18002d1ba  call    DfsSqmGetClientDP
0x18002d1bf  test    eax, eax
0x18002d1c1  jnz     short loc_18002D1D2
0x18002d1c3  lea     rcx, [rbp+57h+var_68]; struct DFSC_REGISTRY_SETTINGS *
0x18002d1c7  call    ?DfsSqmSetClientRegDP@DfsSqmClient@@SAXPEAUDFSC_REGISTRY_SETTINGS@@@Z; DfsSqmClient::DfsSqmSetClientRegDP(DFSC_REGISTRY_SETTINGS *)
0x18002d1cc  mov     cs:?gm_RegDone@DfsSqmClient@@2EA, bl; uchar DfsSqmClient::gm_RegDone
0x18002d1d2  call    DfsGetDelayInterval
0x18002d1d7  mov     r8d, eax
0x18002d1da  mov     edx, 11BCh
0x18002d1df  xor     ecx, ecx
0x18002d1e1  call    cs:__imp_WinSqmSetDWORD
0x18002d1e7  mov     eax, cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002d1ed  test    eax, eax
0x18002d1ef  jz      loc_18002D2B0
0x18002d1f5  xorps   xmm0, xmm0
0x18002d1f8  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002d1fc  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002d200  call    cs:__imp_GetLocalTime
0x18002d206  movzx   ecx, [rbp+57h+SystemTime.wHour]
0x18002d20a  mov     eax, 0AAAAAAABh
0x18002d20f  mul     ecx
0x18002d211  shr     edx, 2
0x18002d214  lea     eax, [rdx+rdx*2]
0x18002d217  add     eax, eax
0x18002d219  sub     ecx, eax
0x18002d21b  test    cx, cx
0x18002d21e  jnz     loc_18002D2A9
0x18002d224  cmp     r15w, cs:?gm_wHour@DfsSqmClient@@2GA; ushort DfsSqmClient::gm_wHour
0x18002d22c  jz      short loc_18002D2A9
0x18002d22e  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x18002d235  xorps   xmm0, xmm0
0x18002d238  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18002d23c  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18002d240  call    cs:__imp_GetLocalTime
0x18002d246  movzx   ecx, [rbp+57h+SystemTime.wDayOfWeek]
0x18002d24a  mov     eax, r15d
0x18002d24d  test    cx, cx
0x18002d250  jnz     short loc_18002D25E
0x18002d252  xor     edx, edx
0x18002d254  cmp     dx, cs:?gm_wDayOfWeek@DfsSqmClient@@2GA; ushort DfsSqmClient::gm_wDayOfWeek
0x18002d25b  cmovnz  eax, ebx
0x18002d25e  mov     cs:?gm_wDayOfWeek@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wDayOfWeek
0x18002d265  lea     r9, [rbp+57h+var_80]
0x18002d269  mov     ecx, 6016Ch
0x18002d26e  mov     [rbp+57h+var_7C], eax
0x18002d271  mov     r8d, 4
0x18002d277  mov     [rsp+0B0h+ulMilliseconds], 2
0x18002d27f  lea     rdx, [rbp+57h+var_7C]
0x18002d283  call    DfsSqmGetClientDP
0x18002d288  test    eax, eax
0x18002d28a  jnz     short loc_18002D2B0
0x18002d28c  cmp     cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA, r15d; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x18002d293  jz      short loc_18002D2B0
0x18002d295  movzx   r8d, [rbp+57h+var_80]
0x18002d29a  mov     edx, 0F54h
0x18002d29f  xor     ecx, ecx
0x18002d2a1  call    cs:__imp_WinSqmSetDWORD
0x18002d2a7  jmp     short loc_18002D2B0
0x18002d2a9  mov     cs:?gm_wHour@DfsSqmClient@@2GA, cx; ushort DfsSqmClient::gm_wHour
0x18002d2b0  test    edi, edi
0x18002d2b2  jz      short loc_18002D2C2
0x18002d2b4  mov     eax, cs:g_ulCount
0x18002d2ba  cmp     eax, cs:g_ulInitThreshold
0x18002d2c0  jb      short loc_18002D2CF
0x18002d2c2  call    DfsGetDelayInterval
0x18002d2c7  mov     ebx, eax
0x18002d2c9  mov     eax, cs:g_ulCount
0x18002d2cf  add     cs:g_ulForce, ebx
0x18002d2d5  add     eax, ebx
0x18002d2d7  mov     cs:g_ulCount, eax
0x18002d2dd  imul    edi, ebx, 0EA60h
0x18002d2e3  mov     [rsp+0B0h+ulFlags], 19h; ulFlags
0x18002d2eb  lea     r8, DfsPeriodicDcUpdate; Callback
0x18002d2f2  mov     r9, r14; pvContext
0x18002d2f5  mov     [rsp+0B0h+ulMilliseconds], edi; ulMilliseconds
0x18002d2f9  mov     rdx, r14; hObject
0x18002d2fc  lea     rcx, g_WsDomainNameChangeWorkItem; phNewWaitObject
0x18002d303  call    cs:__imp_RtlRegisterWait
0x18002d309  test    eax, eax
0x18002d30b  jns     short loc_18002D325
0x18002d30d  mov     cs:g_WsDomainNameChangeWorkItem, 0FFFFFFFFFFFFFFFFh
0x18002d318  mov     rcx, cs:WsDfsTearDownDoneEvent; hEvent
0x18002d31f  call    cs:__imp_SetEvent
0x18002d325  mov     rcx, [rbp+57h+var_38]
0x18002d329  xor     rcx, rsp; StackCookie
0x18002d32c  call    __security_check_cookie
0x18002d331  add     rsp, 88h
0x18002d338  pop     r15
0x18002d33a  pop     r14
0x18002d33c  pop     rdi
0x18002d33d  pop     rsi
0x18002d33e  pop     rbx
0x18002d33f  pop     rbp
0x18002d340  retn
```
