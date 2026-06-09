# LogRemainingPrintJobs(ushort const *)

- ea: `0x1400354c0`
- end: `0x140035819`
- name: `?LogRemainingPrintJobs@@YAJPEBG@Z`
- size: `857`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140035b6c`

## callees

- `0x140005f30`
- `0x14001f3b4`
- `0x14001f3d4`
- `0x140034038`
- `0x14003411c`
- `0x140034390`
- `0x1400354c0`
- `0x14003684c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140035764`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140035764`
- `KERNEL32!GetLastError` at `0x140035674`
- `KERNEL32!GetLastError` at `0x140035674`
- `KERNEL32!SystemTimeToFileTime` at `0x140035754`
- `KERNEL32!SystemTimeToFileTime` at `0x140035754`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x140035560`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x140035560`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035591`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035613`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035717`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1400357e1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035591`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035613`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x140035717`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1400357e1`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1400355dc`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x1400355dc`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x14003565b`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x1400356d5`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x14003565b`
- `ext-ms-win-printer-winspool-l1-1-4!EnumJobsW` at `0x1400356d5`

## string_xrefs

- `0x140035577`: `pcshell\shell\systemsettings\adminflows\removedevice\removedeviceflyout.cpp`
- `0x1400355ee`: `pcshell\shell\systemsettings\adminflows\removedevice\removedeviceflyout.cpp`
- `0x1400356e7`: `pcshell\shell\systemsettings\adminflows\removedevice\removedeviceflyout.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall LogRemainingPrintJobs(const unsigned __int16 *a1)
{
  DWORD v1; // ebx
  int ObjectProperties; // eax
  unsigned int v3; // edi
  WCHAR *v5; // rcx
  const char *v6; // r9
  unsigned int LastError; // ebx
  unsigned int v8; // esi
  const char *v9; // r9
  unsigned int v10; // ebx
  unsigned __int64 v11; // rdi
  LPBYTE v12; // r14
  DWORD v13; // eax
  unsigned int v14; // [rsp+40h] [rbp-A8h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-A4h] BYREF
  DWORD pcbNeeded; // [rsp+48h] [rbp-A0h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-9Ch] BYREF
  __int64 v18; // [rsp+50h] [rbp-98h] BYREF
  HANDLE phPrinter; // [rsp+58h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-88h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-80h] BYREF
  LPBYTE pJob[2]; // [rsp+70h] [rbp-78h] BYREF
  __int64 v23; // [rsp+80h] [rbp-68h]
  unsigned int *v24; // [rsp+88h] [rbp-60h]
  __int64 *v25; // [rsp+90h] [rbp-58h]
  char v26; // [rsp+98h] [rbp-50h]
  DEVPROPKEY v27; // [rsp+A0h] [rbp-48h] BYREF
  int v28; // [rsp+B4h] [rbp-34h]
  __int64 v29; // [rsp+B8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v1 = 0;
  v17 = 0;
  v27 = DEVPKEY_NAME;
  v28 = 0;
  v29 = 0;
  v14 = 0;
  v18 = 0;
  v24 = &v14;
  v25 = &v18;
  v26 = 1;
  ObjectProperties = DevGetObjectProperties(2, a1, 0, 1);
  v3 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\removedevice\\removedeviceflyout.cpp",
      (const char *)(unsigned int)ObjectProperties,
      (int)&v27);
    DevFreeObjectProperties(v14, v18);
    return v3;
  }
  if ( !v14 )
    goto LABEL_20;
  if ( *(_DWORD *)(v18 + 32) != 18 )
    goto LABEL_20;
  v5 = *(WCHAR **)(v18 + 40);
  if ( !v5 || !*(_DWORD *)(v18 + 36) )
    goto LABEL_20;
  phPrinter = 0;
  if ( !OpenPrinterW(v5, &phPrinter, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x50,
                  (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\removedevice\\removedeviceflyout.cpp",
                  v6);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
    DevFreeObjectProperties(v14, v18);
    return LastError;
  }
  v8 = 0;
  pcbNeeded = 0;
  pcReturned = 0;
  if ( !EnumJobsW(phPrinter, 0, 0xFFFFFFFF, 2u, 0, 0, &pcbNeeded, &pcReturned) && pcbNeeded && GetLastError() == 122 )
  {
    *(_OWORD *)pJob = 0;
    v23 = 0;
    std::vector<unsigned char>::_Construct_n<>(pJob, pcbNeeded);
    if ( !EnumJobsW(phPrinter, 0, 0xFFFFFFFF, 2u, pJob[0], pcbNeeded, &pcbNeeded, &pcReturned) )
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x5C,
              (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\removedevice\\removedeviceflyout.cpp",
              v9);
      std::vector<unsigned char>::_Tidy(pJob);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
      DevFreeObjectProperties(v14, v18);
      return v10;
    }
    v1 = pcReturned;
    v17 = pcReturned;
    v11 = 0;
    if ( pcReturned )
    {
      v12 = pJob[0] + 132;
      do
      {
        FileTime = 0;
        SystemTimeToFileTime((const SYSTEMTIME *)&v12[160 * v11], &FileTime);
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v8 += (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime) / 10000000LL;
        ++v11;
      }
      while ( v11 < pcReturned );
    }
    std::vector<unsigned char>::_Tidy(pJob);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
  if ( v1 )
    v13 = v8 / v1;
  else
LABEL_20:
    v13 = 0;
  pcReturned = v13;
  RemoveDeviceAdminFlowTelemetry::RemainingJobsAtPrinterDeletion<int &,unsigned int>(&v17, &pcReturned);
  DevFreeObjectProperties(v14, v18);
  return 0;
}

```

## disassembly

```asm
0x1400354c0  mov     r11, rsp
0x1400354c3  mov     [r11+10h], rbx
0x1400354c7  mov     [r11+18h], rsi
0x1400354cb  push    rdi
0x1400354cc  push    r14
0x1400354ce  push    r15
0x1400354d0  sub     rsp, 0D0h
0x1400354d7  mov     rax, cs:__security_cookie
0x1400354de  xor     rax, rsp
0x1400354e1  mov     [rsp+0E8h+var_28], rax
0x1400354e9  xor     r15d, r15d
0x1400354ec  mov     ebx, r15d
0x1400354ef  mov     [rsp+0E8h+var_9C], ebx
0x1400354f3  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x1400354fa  movups  xmmword ptr [r11-48h], xmm0
0x1400354ff  mov     eax, cs:DEVPKEY_NAME.pid
0x140035505  mov     [r11-38h], eax
0x140035509  mov     [r11-34h], r15d
0x14003550d  mov     [r11-30h], r15
0x140035511  mov     [rsp+0E8h+var_A8], r15d
0x140035516  mov     [rsp+0E8h+var_98], r15
0x14003551b  lea     rax, [rsp+0E8h+var_A8]
0x140035520  mov     [r11-60h], rax
0x140035524  lea     rax, [rsp+0E8h+var_98]
0x140035529  mov     [r11-58h], rax
0x14003552d  mov     byte ptr [r11-50h], 1
0x140035532  lea     rax, [rsp+0E8h+var_98]
0x140035537  mov     [rsp+0E8h+pcbNeeded], rax
0x14003553c  lea     rax, [rsp+0E8h+var_A8]
0x140035541  mov     qword ptr [rsp+0E8h+cbBuf], rax
0x140035546  lea     rax, [r11-48h]
0x14003554a  mov     [rsp+0E8h+pJob], rax; int
0x14003554f  lea     r9d, [r15+1]
0x140035553  xor     r8d, r8d
0x140035556  mov     rdx, rcx
0x140035559  lea     r14d, [r15+2]
0x14003555d  mov     ecx, r14d
0x140035560  call    cs:__imp_DevGetObjectProperties
0x140035566  mov     edi, eax
0x140035568  test    eax, eax
0x14003556a  jns     short loc_14003559E
0x14003556c  mov     rcx, [rsp+0E8h]; this
0x140035574  mov     r9d, eax; char *
0x140035577  lea     r8, aPcshellShellSy_34; "pcshell\\shell\\systemsettings\\adminfl"...
0x14003557e  lea     edx, [r15+46h]; void *
0x140035582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140035587  nop
0x140035588  mov     rdx, [rsp+0E8h+var_98]
0x14003558d  mov     ecx, [rsp+0E8h+var_A8]
0x140035591  call    cs:__imp_DevFreeObjectProperties
0x140035597  mov     eax, edi
0x140035599  jmp     loc_1400357EF
0x14003559e  cmp     [rsp+0E8h+var_A8], r15d
0x1400355a3  jbe     loc_1400357C1
0x1400355a9  mov     rax, [rsp+0E8h+var_98]
0x1400355ae  cmp     dword ptr [rax+20h], 12h
0x1400355b2  jnz     loc_1400357C1
0x1400355b8  mov     rcx, [rax+28h]; pPrinterName
0x1400355bc  test    rcx, rcx
0x1400355bf  jz      loc_1400357C1
0x1400355c5  cmp     [rax+24h], r15d
0x1400355c9  jbe     loc_1400357C1
0x1400355cf  mov     [rsp+0E8h+phPrinter], r15
0x1400355d4  xor     r8d, r8d; pDefault
0x1400355d7  lea     rdx, [rsp+0E8h+phPrinter]; phPrinter
0x1400355dc  call    cs:__imp_OpenPrinterW
0x1400355e2  test    eax, eax
0x1400355e4  jnz     short loc_140035620
0x1400355e6  mov     rcx, [rsp+0E8h]; this
0x1400355ee  lea     r8, aPcshellShellSy_34; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400355f5  lea     edx, [rax+50h]; void *
0x1400355f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400355fd  mov     ebx, eax
0x1400355ff  lea     rcx, [rsp+0E8h+phPrinter]
0x140035604  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140035609  nop
0x14003560a  mov     rdx, [rsp+0E8h+var_98]
0x14003560f  mov     ecx, [rsp+0E8h+var_A8]
0x140035613  call    cs:__imp_DevFreeObjectProperties
0x140035619  mov     eax, ebx
0x14003561b  jmp     loc_1400357EF
0x140035620  mov     esi, r15d
0x140035623  mov     [rsp+0E8h+var_A0], r15d
0x140035628  mov     [rsp+0E8h+var_A4], r15d
0x14003562d  lea     rax, [rsp+0E8h+var_A4]
0x140035632  mov     [rsp+0E8h+pcReturned], rax; pcReturned
0x140035637  lea     rax, [rsp+0E8h+var_A0]
0x14003563c  mov     [rsp+0E8h+pcbNeeded], rax; pcbNeeded
0x140035641  mov     [rsp+0E8h+cbBuf], r15d; cbBuf
0x140035646  mov     [rsp+0E8h+pJob], r15; pJob
0x14003564b  mov     r9d, r14d; Level
0x14003564e  or      edi, 0FFFFFFFFh
0x140035651  mov     r8d, edi; NoJobs
0x140035654  xor     edx, edx; FirstJob
0x140035656  mov     rcx, [rsp+0E8h+phPrinter]; hPrinter
0x14003565b  call    cs:__imp_EnumJobsW
0x140035661  test    eax, eax
0x140035663  jnz     loc_1400357AB
0x140035669  cmp     [rsp+0E8h+var_A0], r15d
0x14003566e  jbe     loc_1400357AB
0x140035674  call    cs:__imp_GetLastError
0x14003567a  cmp     eax, 7Ah ; 'z'
0x14003567d  jnz     loc_1400357AB
0x140035683  xorps   xmm0, xmm0
0x140035686  movdqu  xmmword ptr [rsp+0E8h+var_78], xmm0
0x14003568c  mov     [rsp+0E8h+var_68], r15
0x140035694  mov     edx, [rsp+0E8h+var_A0]
0x140035698  lea     rcx, [rsp+0E8h+var_78]
0x14003569d  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x1400356a2  mov     eax, [rsp+0E8h+var_A0]
0x1400356a6  mov     rdx, [rsp+0E8h+var_78]
0x1400356ab  lea     rcx, [rsp+0E8h+var_A4]
0x1400356b0  mov     [rsp+0E8h+pcReturned], rcx; pcReturned
0x1400356b5  lea     rcx, [rsp+0E8h+var_A0]
0x1400356ba  mov     [rsp+0E8h+pcbNeeded], rcx; pcbNeeded
0x1400356bf  mov     [rsp+0E8h+cbBuf], eax; cbBuf
0x1400356c3  mov     [rsp+0E8h+pJob], rdx; pJob
0x1400356c8  mov     r9d, r14d; Level
0x1400356cb  mov     r8d, edi; NoJobs
0x1400356ce  xor     edx, edx; FirstJob
0x1400356d0  mov     rcx, [rsp+0E8h+phPrinter]; hPrinter
0x1400356d5  call    cs:__imp_EnumJobsW
0x1400356db  test    eax, eax
0x1400356dd  jnz     short loc_140035724
0x1400356df  mov     rcx, [rsp+0E8h]; this
0x1400356e7  lea     r8, aPcshellShellSy_34; "pcshell\\shell\\systemsettings\\adminfl"...
0x1400356ee  lea     edx, [rax+5Ch]; void *
0x1400356f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400356f6  mov     ebx, eax
0x1400356f8  lea     rcx, [rsp+0E8h+var_78]
0x1400356fd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140035702  nop
0x140035703  lea     rcx, [rsp+0E8h+phPrinter]
0x140035708  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14003570d  nop
0x14003570e  mov     rdx, [rsp+0E8h+var_98]
0x140035713  mov     ecx, [rsp+0E8h+var_A8]
0x140035717  call    cs:__imp_DevFreeObjectProperties
0x14003571d  mov     eax, ebx
0x14003571f  jmp     loc_1400357EF
0x140035724  mov     ebx, [rsp+0E8h+var_A4]
0x140035728  mov     [rsp+0E8h+var_9C], ebx
0x14003572c  mov     rax, [rsp+0E8h+var_78]
0x140035731  mov     rdi, r15
0x140035734  test    ebx, ebx
0x140035736  jz      short loc_1400357A0
0x140035738  lea     r14, [rax+84h]
0x14003573f  mov     qword ptr [rsp+0E8h+FileTime.dwLowDateTime], r15
0x140035744  lea     rcx, [rdi+rdi*4]
0x140035748  shl     rcx, 5
0x14003574c  add     rcx, r14; lpSystemTime
0x14003574f  lea     rdx, [rsp+0E8h+FileTime]; lpFileTime
0x140035754  call    cs:__imp_SystemTimeToFileTime
0x14003575a  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x14003575f  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140035764  call    cs:__imp_GetSystemTimeAsFileTime
0x14003576a  mov     rcx, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x14003576f  sub     rcx, qword ptr [rsp+0E8h+FileTime.dwLowDateTime]
0x140035774  mov     rax, 0D6BF94D5E57A42BDh
0x14003577e  imul    rcx
0x140035781  add     rdx, rcx
0x140035784  sar     rdx, 17h
0x140035788  mov     rax, rdx
0x14003578b  shr     rax, 3Fh
0x14003578f  add     rdx, rax
0x140035792  add     esi, edx
0x140035794  inc     rdi
0x140035797  mov     eax, [rsp+0E8h+var_A4]
0x14003579b  cmp     rdi, rax
0x14003579e  jb      short loc_14003573F
0x1400357a0  lea     rcx, [rsp+0E8h+var_78]
0x1400357a5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400357aa  nop
0x1400357ab  lea     rcx, [rsp+0E8h+phPrinter]
0x1400357b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400357b5  test    ebx, ebx
0x1400357b7  jz      short loc_1400357C1
0x1400357b9  xor     edx, edx
0x1400357bb  mov     eax, esi
0x1400357bd  div     ebx
0x1400357bf  jmp     short loc_1400357C4
0x1400357c1  mov     eax, r15d
0x1400357c4  mov     [rsp+0E8h+var_A4], eax
0x1400357c8  lea     rdx, [rsp+0E8h+var_A4]
0x1400357cd  lea     rcx, [rsp+0E8h+var_9C]
0x1400357d2  call    ??$RemainingJobsAtPrinterDeletion@AEAHI@RemoveDeviceAdminFlowTelemetry@@SAXAEAH$$QEAI@Z; RemoveDeviceAdminFlowTelemetry::RemainingJobsAtPrinterDeletion<int &,uint>(int &,uint &&)
0x1400357d7  nop
0x1400357d8  mov     rdx, [rsp+0E8h+var_98]
0x1400357dd  mov     ecx, [rsp+0E8h+var_A8]
0x1400357e1  call    cs:__imp_DevFreeObjectProperties
0x1400357e7  xor     eax, eax
0x1400357e9  jmp     short loc_1400357EF
0x1400357eb  mov     eax, [rsp+0E8h+var_9C]
0x1400357ef  mov     rcx, [rsp+0E8h+var_28]
0x1400357f7  xor     rcx, rsp; StackCookie
0x1400357fa  call    __security_check_cookie
0x1400357ff  lea     r11, [rsp+0E8h+var_18]
0x140035807  mov     rbx, [r11+28h]
0x14003580b  mov     rsi, [r11+30h]
0x14003580f  mov     rsp, r11
0x140035812  pop     r15
0x140035814  pop     r14
0x140035816  pop     rdi
0x140035817  retn
```
