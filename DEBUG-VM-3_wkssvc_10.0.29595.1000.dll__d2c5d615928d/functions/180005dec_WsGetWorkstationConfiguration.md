# WsGetWorkstationConfiguration

- ea: `0x180005dec`
- end: `0x18000635a`
- name: `WsGetWorkstationConfiguration`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800068d0`

## callees

- `0x180005a60`
- `0x180005ca8`
- `0x180005dec`
- `0x180006360`
- `0x180007100`
- `0x1800072d8`
- `0x180007400`
- `0x1800082f0`
- `0x180010d90`
- `0x180010e24`
- `0x18001e420`
- `0x18001ed46`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800061ed`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000621b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800061ed`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000621b`
- `ntdll!RtlGetNtProductType` at `0x180006108`
- `ntdll!RtlGetNtProductType` at `0x180006108`
- `ntdll!DbgPrint` at `0x180005e50`
- `ntdll!DbgPrint` at `0x180005eb7`
- `ntdll!DbgPrint` at `0x180005f93`
- `ntdll!DbgPrint` at `0x180006010`
- `ntdll!DbgPrint` at `0x180005e50`
- `ntdll!DbgPrint` at `0x180005eb7`
- `ntdll!DbgPrint` at `0x180005f93`
- `ntdll!DbgPrint` at `0x180006010`
- `ntdll!NtDeviceIoControlFile` at `0x180006169`
- `ntdll!NtDeviceIoControlFile` at `0x180006169`
- `ntdll!NtFsControlFile` at `0x180006279`
- `ntdll!NtFsControlFile` at `0x180006279`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005e3f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005e3f`
- `ntdll!RtlReleaseResource` at `0x180005ea8`
- `ntdll!RtlReleaseResource` at `0x180005f84`
- `ntdll!RtlReleaseResource` at `0x180005fd6`
- `ntdll!RtlReleaseResource` at `0x180006331`
- `ntdll!RtlReleaseResource` at `0x180005ea8`
- `ntdll!RtlReleaseResource` at `0x180005f84`
- `ntdll!RtlReleaseResource` at `0x180005fd6`
- `ntdll!RtlReleaseResource` at `0x180006331`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180005e6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180005e6e`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800062ed`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800062ed`
- `netutils!NetApiBufferFree` at `0x180005f7b`
- `netutils!NetApiBufferFree` at `0x180005fa3`
- `netutils!NetApiBufferFree` at `0x180006084`
- `netutils!NetApiBufferFree` at `0x1800060a7`
- `netutils!NetApiBufferFree` at `0x180005f7b`
- `netutils!NetApiBufferFree` at `0x180005fa3`
- `netutils!NetApiBufferFree` at `0x180006084`
- `netutils!NetApiBufferFree` at `0x1800060a7`
- `netutils!NetpwNameCanonicalize` at `0x180005ee5`
- `netutils!NetpwNameCanonicalize` at `0x180006052`
- `netutils!NetpwNameCanonicalize` at `0x180005ee5`
- `netutils!NetpwNameCanonicalize` at `0x180006052`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180005f08`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180005f08`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180005f69`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180005f69`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180005f72`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180005f72`

## string_xrefs

- `0x180005f8c`: `WKSSVC Invalid computer name failed %lx\n`
- `0x180005e49`: `WKSSVC Acquire ConfigResource failed\n`
- `0x180005eae`: `WKSSVC Get computer name failed %lx\n`
- `0x180005fdc`: `WKSSVC Open config file failed %lx\n`

## pseudocode

```c
__int64 WsGetWorkstationConfiguration()
{
  __int16 Version; // ax
  unsigned int ComputerNameEx2; // ebx
  WCHAR *v3; // rdi
  unsigned int v4; // esi
  HANDLE v5; // rax
  void *v6; // rbx
  __int64 v7; // rdx
  HKEY v8; // r8
  DWORDLONG ullTotalPhys; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int DomainName; // eax
  void *v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  NTSTATUS v20; // eax
  int v21; // eax
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR Strings[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 RawData; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+78h] [rbp-88h] BYREF
  _MEMORYSTATUSEX v27; // [rsp+80h] [rbp-80h] BYREF
  int InputBuffer; // [rsp+C0h] [rbp-40h] BYREF
  int v29; // [rsp+C4h] [rbp-3Ch]
  int v30; // [rsp+D4h] [rbp-2Ch]
  int v31; // [rsp+D8h] [rbp-28h]
  _WORD v32[14]; // [rsp+DCh] [rbp-24h] BYREF
  __int128 v33; // [rsp+F8h] [rbp-8h]
  bool v34; // [rsp+108h] [rbp+8h]
  bool v35; // [rsp+109h] [rbp+9h]

  RawData = 0;
  Strings[0] = 0;
  Buffer = 0;
  ProductType = 0;
  if ( !RtlAcquireResourceExclusive(&WsInfo, 1u) )
  {
    DbgPrint("WKSSVC Acquire ConfigResource failed\n");
    return 2140;
  }
  qword_18004F010 = (__int64)&off_18004D190;
  Version = GetVersion();
  dword_18004EF74 = 500;
  dword_18004EF78 = (unsigned __int8)Version;
  dword_18004EF7C = HIBYTE(Version);
  ComputerNameEx2 = NetpGetComputerNameEx2((LPVOID *)Strings, ComputerNameNetBIOS);
  if ( ComputerNameEx2 )
  {
    RtlReleaseResource(&WsInfo);
    DbgPrint("WKSSVC Get computer name failed %lx\n", ComputerNameEx2);
    return ComputerNameEx2;
  }
  v3 = (WCHAR *)Strings[0];
  v4 = NetpwNameCanonicalize(Strings[0], qword_18004ED40, 522, 4, 0);
  if ( !v4 )
  {
    NetApiBufferFree(v3);
    ullTotalPhys = -1;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)qword_18004ED40 + v10) );
    dword_18004EF4C = v10;
    ComputerNameEx2 = NetpOpenConfigDataEx(&RawData, v7, v8, 1);
    if ( ComputerNameEx2 )
    {
      RtlReleaseResource(&WsInfo);
      DbgPrint("WKSSVC Open config file failed %lx\n", ComputerNameEx2);
      return ComputerNameEx2;
    }
    LOBYTE(v22) = 0;
    DomainName = NetpGetDomainNameExExEx(&Buffer, v11, v12, v13, (bool *)&v22);
    ComputerNameEx2 = DomainName;
    if ( DomainName )
    {
      DbgPrint("WKSSVC Get the primary domain name failed %lx\n", DomainName);
      goto LABEL_46;
    }
    v15 = Buffer;
    if ( *(_WORD *)Buffer )
    {
      v16 = WsInAWorkgroup();
      ComputerNameEx2 = NetpwNameCanonicalize(Buffer, word_18004EF50, 32, v16 != 0 ? 13 : 6, 0);
      if ( ComputerNameEx2 )
      {
        Strings[0] = (LPCWSTR)Buffer;
        WsLogEvent(0xF5Cu, 0);
        NetApiBufferFree(Buffer);
        DbgPrint("WKSSVC Invalid domain name failed %lx\n", ComputerNameEx2);
LABEL_46:
        NetpCloseConfigData(RawData);
        RtlReleaseResource(&WsInfo);
        return ComputerNameEx2;
      }
      v15 = Buffer;
    }
    else
    {
      word_18004EF50[0] = 0;
    }
    NetApiBufferFree(v15);
    v17 = -1;
    do
      ++v17;
    while ( word_18004EF50[v17] );
    dword_18004EF70 = v17;
    WsUpdateWkstaToMatchRegistry(RawData, 1);
    v33 = xmmword_18004EFC0;
    v34 = (_DWORD)xmmword_18004EFD0 != 0;
    v29 = 6;
    RtlGetNtProductType(&ProductType);
    v35 = ProductType == NtProductLanManNt;
    *(_OWORD *)Strings = 0;
    if ( WsDgReceiverDeviceHandle )
    {
      LOWORD(v31) = 0;
      v18 = NtDeviceIoControlFile(
              WsDgReceiverDeviceHandle,
              0,
              0,
              0,
              (PIO_STATUS_BLOCK)Strings,
              0x130007u,
              &InputBuffer,
              0x60u,
              0,
              0);
      if ( v18 == 259 )
        v18 = (unsigned int)Strings[0];
      if ( v18 == 258 )
      {
        ComputerNameEx2 = 1460;
LABEL_35:
        Strings[0] = L"datagram receiver";
        WsLogEvent(0xC29u, ComputerNameEx2);
        DbgPrint("WKSSVC Start Datagram recevier failed %lx\n", ComputerNameEx2);
        goto LABEL_46;
      }
      v19 = WsMapStatus(v18);
      ComputerNameEx2 = v19;
      if ( v19 && v19 != 1056 && v19 != 50 )
        goto LABEL_35;
    }
    InputBuffer = 0;
    v29 = 6;
    _o_wcscpy_s(v32, 277, qword_18004ED40);
    v30 = 2 * dword_18004EF4C;
    v31 = 2 * dword_18004EF70;
    _o_wcscpy_s(&v32[dword_18004EF4C], (unsigned int)(277 - dword_18004EF4C), word_18004EF50);
    *(_OWORD *)Strings = 0;
    v20 = NtFsControlFile(
            WsRedirDeviceHandle,
            0,
            0,
            0,
            (PIO_STATUS_BLOCK)Strings,
            0x140191u,
            &InputBuffer,
            v31 + 36 + v30,
            &xmmword_18004EF80,
            0x8Cu);
    if ( v20 >= 0 )
      v20 = (NTSTATUS)Strings[0];
    v21 = WsMapStatus((unsigned int)v20);
    ComputerNameEx2 = v21;
    if ( !v21 || v21 == 1056 )
    {
      if ( (_DWORD)xmmword_18004EFC0 == -1 )
      {
        memset_0(&v27, 0, sizeof(v27));
        v27.dwLength = 64;
        GlobalMemoryStatusEx(&v27);
        if ( v27.ullTotalPhys != -1 )
          ullTotalPhys = v27.ullTotalPhys;
        LODWORD(xmmword_18004EFC0) = ullTotalPhys / 0x1F4000;
      }
      WsCSCReportStartRedir();
      ComputerNameEx2 = 0;
    }
    else
    {
      Strings[0] = L"redirector";
      WsLogEvent(0xC29u, v21);
      DbgPrint("WKSSVC Start redirector failed %lx\n", ComputerNameEx2);
    }
    goto LABEL_46;
  }
  Strings[0] = v3;
  LODWORD(RawData) = 0;
  v5 = RegisterEventSourceW(0, L"Workstation");
  v6 = v5;
  if ( v5 )
  {
    if ( (_DWORD)RawData )
      ReportEventW(v5, 1u, 0, 0xF1Eu, 0, 1u, 4u, Strings, &RawData);
    else
      ReportEventW(v5, 1u, 0, 0xF1Eu, 0, 1u, 0, Strings, 0);
    DeregisterEventSource(v6);
  }
  NetApiBufferFree(v3);
  RtlReleaseResource(&WsInfo);
  DbgPrint("WKSSVC Invalid computer name failed %lx\n", v4);
  return v4;
}

```

## disassembly

```asm
0x180005dec  push    rbp
0x180005dee  push    rbx
0x180005def  push    rsi
0x180005df0  push    rdi
0x180005df1  push    r12
0x180005df3  push    r14
0x180005df5  push    r15
0x180005df7  lea     rbp, [rsp-220h]
0x180005dff  sub     rsp, 320h
0x180005e06  mov     rax, cs:__security_cookie
0x180005e0d  xor     rax, rsp
0x180005e10  mov     [rbp+250h+var_40], rax
0x180005e17  xor     r14d, r14d
0x180005e1a  lea     r12, WsInfo
0x180005e21  mov     rcx, r12; Resource
0x180005e24  mov     [rsp+350h+RawData], r14
0x180005e29  mov     [rsp+350h+Strings], r14
0x180005e2e  mov     [rsp+350h+Buffer], r14
0x180005e33  lea     r15d, [r14+1]
0x180005e37  mov     [rsp+350h+ProductType], r14d
0x180005e3c  mov     dl, r15b; Wait
0x180005e3f  call    cs:__imp_RtlAcquireResourceExclusive
0x180005e45  test    al, al
0x180005e47  jnz     short loc_180005E60
0x180005e49  lea     rcx, aWkssvcAcquireC; "WKSSVC Acquire ConfigResource failed\n"
0x180005e50  call    cs:__imp_DbgPrint
0x180005e56  mov     eax, 85Ch
0x180005e5b  jmp     loc_180006339
0x180005e60  lea     rax, off_18004D190; "CharWait"
0x180005e67  mov     cs:qword_18004F010, rax
0x180005e6e  call    cs:__imp_GetVersion
0x180005e74  lea     rcx, [rsp+350h+Strings]
0x180005e79  mov     cs:dword_18004EF74, 1F4h
0x180005e83  movzx   edx, al
0x180005e86  shr     eax, 8
0x180005e89  movzx   eax, al
0x180005e8c  mov     cs:dword_18004EF78, edx
0x180005e92  xor     edx, edx
0x180005e94  mov     cs:dword_18004EF7C, eax
0x180005e9a  call    NetpGetComputerNameEx2
0x180005e9f  mov     ebx, eax
0x180005ea1  test    eax, eax
0x180005ea3  jz      short loc_180005EC2
0x180005ea5  mov     rcx, r12; Resource
0x180005ea8  call    cs:__imp_RtlReleaseResource
0x180005eae  lea     rcx, aWkssvcGetCompu; "WKSSVC Get computer name failed %lx\n"
0x180005eb5  mov     edx, ebx
0x180005eb7  call    cs:__imp_DbgPrint
0x180005ebd  jmp     loc_180006337
0x180005ec2  mov     rdi, [rsp+350h+Strings]
0x180005ec7  lea     rbx, qword_18004ED40
0x180005ece  mov     rdx, rbx
0x180005ed1  mov     dword ptr [rsp+350h+lpUserSid], r14d
0x180005ed6  mov     rcx, rdi
0x180005ed9  mov     r9d, 4
0x180005edf  mov     r8d, 20Ah
0x180005ee5  call    cs:__imp_NetpwNameCanonicalize
0x180005eeb  mov     esi, eax
0x180005eed  test    eax, eax
0x180005eef  jz      loc_180005FA0
0x180005ef5  lea     rdx, SourceName; "Workstation"
0x180005efc  mov     [rsp+350h+Strings], rdi
0x180005f01  xor     ecx, ecx; lpUNCServerName
0x180005f03  mov     dword ptr [rsp+350h+RawData], r14d
0x180005f08  call    cs:__imp_RegisterEventSourceW
0x180005f0e  mov     rbx, rax
0x180005f11  test    rax, rax
0x180005f14  jz      short loc_180005F78
0x180005f16  xor     r8d, r8d; wCategory
0x180005f19  mov     edx, r15d; wType
0x180005f1c  mov     r9d, 0F1Eh; dwEventID
0x180005f22  mov     rcx, rax; hEventLog
0x180005f25  cmp     dword ptr [rsp+350h+RawData], r14d
0x180005f2a  jnz     short loc_180005F42
0x180005f2c  mov     [rsp+350h+lpRawData], r14
0x180005f31  lea     rax, [rsp+350h+Strings]
0x180005f36  mov     [rsp+350h+lpStrings], rax
0x180005f3b  mov     [rsp+350h+dwDataSize], r14d
0x180005f40  jmp     short loc_180005F5E
0x180005f42  lea     rax, [rsp+350h+RawData]
0x180005f47  mov     [rsp+350h+lpRawData], rax; lpRawData
0x180005f4c  lea     rax, [rsp+350h+Strings]
0x180005f51  mov     [rsp+350h+lpStrings], rax; lpStrings
0x180005f56  mov     [rsp+350h+dwDataSize], 4; dwDataSize
0x180005f5e  mov     [rsp+350h+wNumStrings], r15w; wNumStrings
0x180005f64  mov     [rsp+350h+lpUserSid], r14; lpUserSid
0x180005f69  call    cs:__imp_ReportEventW
0x180005f6f  mov     rcx, rbx; hEventLog
0x180005f72  call    cs:__imp_DeregisterEventSource
0x180005f78  mov     rcx, rdi; Buffer
0x180005f7b  call    cs:__imp_NetApiBufferFree
0x180005f81  mov     rcx, r12; Resource
0x180005f84  call    cs:__imp_RtlReleaseResource
0x180005f8a  mov     edx, esi
0x180005f8c  lea     rcx, aWkssvcInvalidC; "WKSSVC Invalid computer name failed %lx"...
0x180005f93  call    cs:__imp_DbgPrint
0x180005f99  mov     eax, esi
0x180005f9b  jmp     loc_180006339
0x180005fa0  mov     rcx, rdi; Buffer
0x180005fa3  call    cs:__imp_NetApiBufferFree
0x180005fa9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005fad  mov     rax, rdi
0x180005fb0  inc     rax
0x180005fb3  cmp     [rbx+rax*2], r14w
0x180005fb8  jnz     short loc_180005FB0
0x180005fba  mov     r9d, r15d
0x180005fbd  mov     cs:dword_18004EF4C, eax
0x180005fc3  lea     rcx, [rsp+350h+RawData]
0x180005fc8  call    NetpOpenConfigDataEx
0x180005fcd  mov     ebx, eax
0x180005fcf  test    eax, eax
0x180005fd1  jz      short loc_180005FE8
0x180005fd3  mov     rcx, r12; Resource
0x180005fd6  call    cs:__imp_RtlReleaseResource
0x180005fdc  lea     rcx, aWkssvcOpenConf; "WKSSVC Open config file failed %lx\n"
0x180005fe3  jmp     loc_180005EB5
0x180005fe8  lea     rax, [rsp+350h+var_300]
0x180005fed  mov     byte ptr [rsp+350h+var_300], r14b
0x180005ff2  lea     rcx, [rsp+350h+Buffer]; Buffer
0x180005ff7  mov     [rsp+350h+lpUserSid], rax; __int64
0x180005ffc  call    NetpGetDomainNameExExEx
0x180006001  mov     ebx, eax
0x180006003  test    eax, eax
0x180006005  jz      short loc_18000601B
0x180006007  mov     edx, eax
0x180006009  lea     rcx, aWkssvcGetThePr; "WKSSVC Get the primary domain name fail"...
0x180006010  call    cs:__imp_DbgPrint
0x180006016  jmp     loc_180006324
0x18000601b  mov     rcx, [rsp+350h+Buffer]; Buffer
0x180006020  lea     rsi, word_18004EF50
0x180006027  cmp     [rcx], r14w
0x18000602b  jz      short loc_18000609F
0x18000602d  call    WsInAWorkgroup
0x180006032  mov     rcx, [rsp+350h+Buffer]
0x180006037  neg     eax
0x180006039  mov     r8d, 20h ; ' '
0x18000603f  mov     dword ptr [rsp+350h+lpUserSid], r14d
0x180006044  sbb     r9d, r9d
0x180006047  mov     rdx, rsi
0x18000604a  and     r9d, 7
0x18000604e  add     r9d, 6
0x180006052  call    cs:__imp_NetpwNameCanonicalize
0x180006058  mov     ebx, eax
0x18000605a  test    eax, eax
0x18000605c  jz      short loc_180006098
0x18000605e  mov     rax, [rsp+350h+Buffer]
0x180006063  lea     r9, [rsp+350h+Strings]
0x180006068  mov     edx, r15d
0x18000606b  mov     [rsp+350h+Strings], rax
0x180006070  mov     ecx, 0F5Ch; dwEventID
0x180006075  mov     dword ptr [rsp+350h+lpUserSid], r14d; RawData
0x18000607a  call    WsLogEvent
0x18000607f  mov     rcx, [rsp+350h+Buffer]; Buffer
0x180006084  call    cs:__imp_NetApiBufferFree
0x18000608a  mov     edx, ebx
0x18000608c  lea     rcx, aWkssvcInvalidD; "WKSSVC Invalid domain name failed %lx\n"
0x180006093  jmp     loc_180006010
0x180006098  mov     rcx, [rsp+350h+Buffer]
0x18000609d  jmp     short loc_1800060A7
0x18000609f  mov     cs:word_18004EF50, r14w
0x1800060a7  call    cs:__imp_NetApiBufferFree
0x1800060ad  mov     rax, rdi
0x1800060b0  inc     rax
0x1800060b3  cmp     [rsi+rax*2], r14w
0x1800060b8  jnz     short loc_1800060B0
0x1800060ba  mov     rcx, [rsp+350h+RawData]
0x1800060bf  mov     edx, r15d
0x1800060c2  mov     cs:dword_18004EF70, eax
0x1800060c8  call    WsUpdateWkstaToMatchRegistry
0x1800060cd  mov     eax, dword ptr cs:xmmword_18004EFC0
0x1800060d3  lea     rcx, [rsp+350h+ProductType]; ProductType
0x1800060d8  cmp     dword ptr cs:xmmword_18004EFD0, r14d
0x1800060df  mov     dword ptr [rbp+250h+var_258], eax
0x1800060e2  mov     eax, dword ptr cs:xmmword_18004EFC0+4
0x1800060e8  setnz   [rbp+250h+var_248]
0x1800060ec  mov     dword ptr [rbp+250h+var_258+4], eax
0x1800060ef  mov     eax, dword ptr cs:xmmword_18004EFC0+8
0x1800060f5  mov     dword ptr [rbp+250h+var_258+8], eax
0x1800060f8  mov     eax, dword ptr cs:xmmword_18004EFC0+0Ch
0x1800060fe  mov     dword ptr [rbp+250h+var_258+0Ch], eax
0x180006101  mov     [rbp+250h+var_28C], 6
0x180006108  call    cs:__imp_RtlGetNtProductType
0x18000610e  cmp     [rsp+350h+ProductType], 2
0x180006113  xorps   xmm0, xmm0
0x180006116  mov     rcx, cs:WsDgReceiverDeviceHandle; FileHandle
0x18000611d  setz    [rbp+250h+var_247]
0x180006121  movups  xmmword ptr [rsp+350h+Strings], xmm0
0x180006126  test    rcx, rcx
0x180006129  jz      loc_1800061D0
0x18000612f  mov     [rsp+350h+OutputBufferLength], r14d; OutputBufferLength
0x180006134  lea     rax, [rbp+250h+InputBuffer]
0x180006138  mov     [rsp+350h+lpRawData], r14; OutputBuffer
0x18000613d  xor     r9d, r9d; ApcContext
0x180006140  mov     dword ptr [rsp+350h+lpStrings], 60h ; '`'; InputBufferLength
0x180006148  xor     r8d, r8d; ApcRoutine
0x18000614b  mov     qword ptr [rsp+350h+dwDataSize], rax; InputBuffer
0x180006150  xor     edx, edx; Event
0x180006152  lea     rax, [rsp+350h+Strings]
0x180006157  mov     dword ptr [rsp+350h+wNumStrings], 130007h; IoControlCode
0x18000615f  mov     [rsp+350h+lpUserSid], rax; IoStatusBlock
0x180006164  mov     word ptr [rbp+250h+var_278], r14w
0x180006169  call    cs:__imp_NtDeviceIoControlFile
0x18000616f  cmp     eax, 103h
0x180006174  cmovz   eax, dword ptr [rsp+350h+Strings]
0x180006179  cmp     eax, 102h
0x18000617e  jnz     short loc_180006187
0x180006180  mov     ebx, 5B4h
0x180006185  jmp     short loc_1800061A0
0x180006187  mov     ecx, eax
0x180006189  call    WsMapStatus
0x18000618e  mov     ebx, eax
0x180006190  test    eax, eax
0x180006192  jz      short loc_1800061D0
0x180006194  cmp     eax, 420h
0x180006199  jz      short loc_1800061D0
0x18000619b  cmp     eax, 32h ; '2'
0x18000619e  jz      short loc_1800061D0
0x1800061a0  lea     rax, aDatagramReceiv; "datagram receiver"
0x1800061a7  mov     dword ptr [rsp+350h+lpUserSid], ebx; RawData
0x1800061ab  mov     edx, r15d
0x1800061ae  mov     [rsp+350h+Strings], rax
0x1800061b3  lea     r9, [rsp+350h+Strings]
0x1800061b8  mov     ecx, 0C29h; dwEventID
0x1800061bd  call    WsLogEvent
0x1800061c2  mov     edx, ebx
0x1800061c4  lea     rcx, aWkssvcStartDat; "WKSSVC Start Datagram recevier failed %"...
0x1800061cb  jmp     loc_180006010
0x1800061d0  mov     ebx, 115h
0x1800061d5  mov     [rbp+250h+InputBuffer], r14d
0x1800061d9  mov     edx, ebx
0x1800061db  mov     [rbp+250h+var_28C], 6
0x1800061e2  lea     r8, qword_18004ED40
0x1800061e9  lea     rcx, [rbp+250h+var_274]
0x1800061ed  call    cs:__imp__o_wcscpy_s
0x1800061f3  mov     ecx, cs:dword_18004EF4C
0x1800061f9  mov     r8, rsi
0x1800061fc  sub     ebx, ecx
0x1800061fe  mov     edx, ebx
0x180006200  lea     eax, [rcx+rcx]
0x180006203  mov     [rbp+250h+var_27C], eax
0x180006206  mov     eax, cs:dword_18004EF70
0x18000620c  add     eax, eax
0x18000620e  mov     [rbp+250h+var_278], eax
0x180006211  mov     eax, ecx
0x180006213  lea     rcx, [rbp+250h+var_274]
0x180006217  lea     rcx, [rcx+rax*2]
0x18000621b  call    cs:__imp__o_wcscpy_s
0x180006221  mov     eax, [rbp+250h+var_278]
0x180006224  xorps   xmm0, xmm0
0x180006227  mov     r8d, [rbp+250h+var_27C]
0x18000622b  add     eax, 24h ; '$'
0x18000622e  mov     rcx, cs:WsRedirDeviceHandle; FileHandle
0x180006235  add     r8d, eax
0x180006238  mov     [rsp+350h+OutputBufferLength], 8Ch; OutputBufferLength
0x180006240  lea     rax, xmmword_18004EF80
0x180006247  mov     [rsp+350h+lpRawData], rax; OutputBuffer
0x18000624c  xor     r9d, r9d; ApcContext
0x18000624f  mov     dword ptr [rsp+350h+lpStrings], r8d; InputBufferLength
0x180006254  lea     rax, [rbp+250h+InputBuffer]
0x180006258  mov     qword ptr [rsp+350h+dwDataSize], rax; InputBuffer
0x18000625d  xor     r8d, r8d; ApcRoutine
0x180006260  lea     rax, [rsp+350h+Strings]
0x180006265  mov     dword ptr [rsp+350h+wNumStrings], 140191h; FsControlCode
0x18000626d  xor     edx, edx; Event
0x18000626f  mov     [rsp+350h+lpUserSid], rax; IoStatusBlock
0x180006274  movups  xmmword ptr [rsp+350h+Strings], xmm0
0x180006279  call    cs:__imp_NtFsControlFile
0x18000627f  test    eax, eax
0x180006281  cmovns  eax, dword ptr [rsp+350h+Strings]
0x180006286  mov     ecx, eax
0x180006288  call    WsMapStatus
0x18000628d  mov     ebx, eax
0x18000628f  test    eax, eax
0x180006291  jz      short loc_1800062CA
0x180006293  cmp     eax, 420h
0x180006298  jz      short loc_1800062CA
0x18000629a  lea     rax, aRedirector; "redirector"
0x1800062a1  mov     dword ptr [rsp+350h+lpUserSid], ebx; RawData
0x1800062a5  mov     edx, r15d
0x1800062a8  mov     [rsp+350h+Strings], rax
0x1800062ad  lea     r9, [rsp+350h+Strings]
0x1800062b2  mov     ecx, 0C29h; dwEventID
0x1800062b7  call    WsLogEvent
0x1800062bc  mov     edx, ebx
0x1800062be  lea     rcx, aWkssvcStartRed; "WKSSVC Start redirector failed %lx\n"
0x1800062c5  jmp     loc_180006010
0x1800062ca  cmp     dword ptr cs:xmmword_18004EFC0, 0FFFFFFFFh
0x1800062d1  jnz     short loc_18000631C
0x1800062d3  mov     ebx, 40h ; '@'
0x1800062d8  lea     rcx, [rbp+250h+var_2D0]; void *
0x1800062dc  mov     r8d, ebx; Size
0x1800062df  xor     edx, edx; Val
0x1800062e1  call    memset_0
0x1800062e6  lea     rcx, [rbp+250h+var_2D0]; lpBuffer
0x1800062ea  mov     [rbp+250h+var_2D0.dwLength], ebx
0x1800062ed  call    cs:__imp_GlobalMemoryStatusEx
0x1800062f3  cmp     [rbp+250h+var_2D0.ullTotalPhys], rdi
0x1800062f7  mov     rax, 624DD2F1A9FBE77h
0x180006301  cmovb   rdi, [rbp+250h+var_2D0.ullTotalPhys]
0x180006306  mul     rdi
  ... truncated ...
```
