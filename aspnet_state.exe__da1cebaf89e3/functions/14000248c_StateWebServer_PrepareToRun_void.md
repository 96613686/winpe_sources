# StateWebServer::PrepareToRun(void)

- ea: `0x14000248c`
- end: `0x14000264a`
- name: `?PrepareToRun@StateWebServer@@AEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140001a20`
- `0x140002678`

## callees

- `0x1400011ac`
- `0x14000248c`
- `0x140004e5c`
- `0x140004f1e`
- `0x140004f2c`
- `0x140005b20`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x1400024dd`
- `WS2_32!__imp_WSAStartup` at `0x1400024dd`
- `ADVAPI32!RegQueryValueExW` at `0x14000258e`
- `ADVAPI32!RegQueryValueExW` at `0x1400025d6`
- `ADVAPI32!RegQueryValueExW` at `0x14000258e`
- `ADVAPI32!RegQueryValueExW` at `0x1400025d6`
- `ADVAPI32!RegOpenKeyExW` at `0x14000254d`
- `ADVAPI32!RegOpenKeyExW` at `0x14000254d`
- `ADVAPI32!RegCloseKey` at `0x14000261e`
- `ADVAPI32!RegCloseKey` at `0x14000261e`
- `KERNEL32!CreateEventW` at `0x140002508`
- `KERNEL32!CreateEventW` at `0x140002508`
- `KERNEL32!CreateWaitableTimerW` at `0x1400025fc`
- `KERNEL32!CreateWaitableTimerW` at `0x1400025fc`

## string_xrefs

- `0x140002523`: `SYSTEM\CurrentControlSet\Services\aspnet_state\Parameters`

## pseudocode

```c
__int64 __fastcall StateWebServer::PrepareToRun(StateWebServer *this)
{
  unsigned int LastWin32Error; // ebx
  int v3; // eax
  HANDLE EventW; // rax
  HANDLE WaitableTimerW; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v11[12]; // [rsp+44h] [rbp-BCh] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  *((_BYTE *)this + 75) = 0;
  LastWin32Error = BlockMem::Init();
  if ( LastWin32Error )
    goto LABEL_18;
  v3 = WSAStartup(0x202u, &WSAData);
  if ( v3 )
  {
    LastWin32Error = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      LastWin32Error = v3;
    goto LABEL_18;
  }
  *((_BYTE *)this + 4) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
LABEL_7:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_18;
  }
  *((_QWORD *)this + 8) = EventW;
  *((_WORD *)this + 24) = -23112;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, StateWebServer::s_serviceKeyNameParameters, 0, 0x20019u, &hKey) )
  {
    Type = 4;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, StateWebServer::s_serviceValueNamePort, 0, &Type, Data, &cbData)
      && (unsigned int)(*(_DWORD *)Data - 1) <= 0xFFFE )
    {
      *((_WORD *)this + 24) = *(_WORD *)Data;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, StateWebServer::s_serviceValueNameUseIPv6, 0, &Type, v11, &cbData) && *(_DWORD *)v11 )
      *((_BYTE *)this + 75) = 1;
  }
  LastWin32Error = Tracker::staticInit();
  if ( !LastWin32Error )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
    *((_QWORD *)this + 3) = WaitableTimerW;
    if ( WaitableTimerW )
    {
      PerfCounterInitialize();
      goto LABEL_18;
    }
    goto LABEL_7;
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return LastWin32Error;
}

```

## disassembly

```asm
0x14000248c  mov     [rsp-8+arg_8], rbx
0x140002491  mov     [rsp-8+arg_10], rdi
0x140002496  push    rbp
0x140002497  lea     rbp, [rsp-100h]
0x14000249f  sub     rsp, 200h
0x1400024a6  mov     rax, cs:__security_cookie
0x1400024ad  xor     rax, rsp
0x1400024b0  mov     [rbp+100h+var_10], rax
0x1400024b7  and     [rsp+200h+hKey], 0
0x1400024bd  mov     rdi, rcx
0x1400024c0  mov     byte ptr [rcx+4Bh], 0
0x1400024c4  call    ?Init@BlockMem@@SAJXZ; BlockMem::Init(void)
0x1400024c9  mov     ebx, eax
0x1400024cb  test    eax, eax
0x1400024cd  jnz     loc_140002614
0x1400024d3  mov     ecx, 202h; wVersionRequested
0x1400024d8  lea     rdx, [rsp+200h+WSAData]; lpWSAData
0x1400024dd  call    cs:__imp_WSAStartup
0x1400024e3  test    eax, eax
0x1400024e5  jz      short loc_1400024FA
0x1400024e7  movzx   ebx, ax
0x1400024ea  or      ebx, 80070000h
0x1400024f0  test    eax, eax
0x1400024f2  cmovle  ebx, eax
0x1400024f5  jmp     loc_140002614
0x1400024fa  xor     r9d, r9d; lpName
0x1400024fd  mov     byte ptr [rdi+4], 1
0x140002501  xor     r8d, r8d; bInitialState
0x140002504  xor     edx, edx; bManualReset
0x140002506  xor     ecx, ecx; lpEventAttributes
0x140002508  call    cs:__imp_CreateEventW
0x14000250e  test    rax, rax
0x140002511  jnz     short loc_14000251F
0x140002513  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x140002518  mov     ebx, eax
0x14000251a  jmp     loc_140002614
0x14000251f  mov     [rdi+40h], rax
0x140002523  lea     rdx, ?s_serviceKeyNameParameters@StateWebServer@@0PAGA; "SYSTEM\\CurrentControlSet\\Services\\as"...
0x14000252a  mov     eax, 0A5B8h
0x14000252f  mov     r9d, 20019h; samDesired
0x140002535  mov     [rdi+30h], ax
0x140002539  xor     r8d, r8d; ulOptions
0x14000253c  lea     rax, [rsp+200h+hKey]
0x140002541  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002548  mov     [rsp+200h+phkResult], rax; phkResult
0x14000254d  call    cs:__imp_RegOpenKeyExW
0x140002553  test    eax, eax
0x140002555  jnz     loc_1400025EA
0x14000255b  mov     rcx, [rsp+200h+hKey]; hKey
0x140002560  lea     ebx, [rax+4]
0x140002563  lea     rax, [rsp+200h+cbData]
0x140002568  mov     [rsp+200h+Type], ebx
0x14000256c  mov     [rsp+200h+lpcbData], rax; lpcbData
0x140002571  lea     r9, [rsp+200h+Type]; lpType
0x140002576  lea     rax, [rsp+200h+Data]
0x14000257b  mov     [rsp+200h+cbData], ebx
0x14000257f  xor     r8d, r8d; lpReserved
0x140002582  mov     [rsp+200h+phkResult], rax; lpData
0x140002587  lea     rdx, ?s_serviceValueNamePort@StateWebServer@@0PAGA; "Port"
0x14000258e  call    cs:__imp_RegQueryValueExW
0x140002594  test    eax, eax
0x140002596  jnz     short loc_1400025AA
0x140002598  mov     ecx, dword ptr [rsp+200h+Data]
0x14000259c  lea     eax, [rcx-1]
0x14000259f  cmp     eax, 0FFFEh
0x1400025a4  ja      short loc_1400025AA
0x1400025a6  mov     [rdi+30h], cx
0x1400025aa  mov     rcx, [rsp+200h+hKey]; hKey
0x1400025af  lea     rax, [rsp+200h+cbData]
0x1400025b4  mov     [rsp+200h+lpcbData], rax; lpcbData
0x1400025b9  lea     r9, [rsp+200h+Type]; lpType
0x1400025be  lea     rax, [rsp+200h+var_1BC]
0x1400025c3  mov     [rsp+200h+cbData], ebx
0x1400025c7  xor     r8d, r8d; lpReserved
0x1400025ca  mov     [rsp+200h+phkResult], rax; lpData
0x1400025cf  lea     rdx, ?s_serviceValueNameUseIPv6@StateWebServer@@0PAGA; "UseIPV6"
0x1400025d6  call    cs:__imp_RegQueryValueExW
0x1400025dc  test    eax, eax
0x1400025de  jnz     short loc_1400025EA
0x1400025e0  cmp     dword ptr [rsp+200h+var_1BC], eax
0x1400025e4  jz      short loc_1400025EA
0x1400025e6  mov     byte ptr [rdi+4Bh], 1
0x1400025ea  call    ?staticInit@Tracker@@SAJXZ; Tracker::staticInit(void)
0x1400025ef  mov     ebx, eax
0x1400025f1  test    eax, eax
0x1400025f3  jnz     short loc_140002614
0x1400025f5  xor     r8d, r8d; lpTimerName
0x1400025f8  xor     edx, edx; bManualReset
0x1400025fa  xor     ecx, ecx; lpTimerAttributes
0x1400025fc  call    cs:__imp_CreateWaitableTimerW
0x140002602  mov     [rdi+18h], rax
0x140002606  test    rax, rax
0x140002609  jz      loc_140002513
0x14000260f  call    ?PerfCounterInitialize@@YAJXZ; PerfCounterInitialize(void)
0x140002614  mov     rcx, [rsp+200h+hKey]; hKey
0x140002619  test    rcx, rcx
0x14000261c  jz      short loc_140002624
0x14000261e  call    cs:__imp_RegCloseKey
0x140002624  mov     eax, ebx
0x140002626  mov     rcx, [rbp+100h+var_10]
0x14000262d  xor     rcx, rsp; StackCookie
0x140002630  call    __security_check_cookie
0x140002635  lea     r11, [rsp+200h+var_s0]
0x14000263d  mov     rbx, [r11+18h]
0x140002641  mov     rdi, [r11+20h]
0x140002645  mov     rsp, r11
0x140002648  pop     rbp
0x140002649  retn
```
