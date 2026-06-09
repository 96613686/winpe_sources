# DdcCommandController::HandleLocateCommandRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x1800063f4`
- end: `0x18000673f`
- name: `?HandleLocateCommandRetry@DdcCommandController@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `843`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180002fc0`
- `0x18000333c`
- `0x180004d5c`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x18000573c`
- `0x1800063f4`
- `0x18000f600`
- `0x1800101f0`
- `0x180011e74`
- `0x18001227c`
- `0x1800128fc`
- `0x18001505c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800065e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800065e7`

## string_xrefs

- `0x1800066bd`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x1800064f7`: `CBR(swscanf_s(wstrConfiguration.c_str(), L"%s %lu %s", pwszSwitch, c_cchSwitch, &dwRetries, pwszEncodedPrefix, c_cchEncodedPrefix) == 3)`
- `0x180006579`: `CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))`
- `0x180006672`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x1800066a6`: `CHR(taskSchedulerWrapper.DeleteLocateCommandRetrySchedule(&prefix))`
- `0x180006643`: `CHR(DdcCommandExecutor::ProcessLocateCommand(&prefix, pdcHandle, 0, dwRetries))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DdcCommandController::HandleLocateCommandRetry(__int64 a1, void *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // r14d
  BOOL v6; // edi
  const wchar_t *v7; // rax
  int v8; // edx
  int v9; // ecx
  int Command; // ebx
  unsigned __int64 v11; // r8
  int v12; // edx
  int v13; // ecx
  __int64 v14; // rcx
  char v16; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  unsigned int v24[6]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v29[256]; // [rsp+C0h] [rbp-40h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v19 = 0;
  memset(v24, 0, 20);
  v5 = 0;
  Block = 0;
  v23 = 0;
  SystemTimeAsFileTime = 0;
  v6 = 0;
  v18 = 0;
  v20 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v3, DEVICE_DIRECTORY_CLIENT_HANDLE_LOCATE_COMMAND_RETRY, v4, 1, v25);
  v7 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( swscanf_s(v7, L"%s %lu %s", &v26, 20, &v19, v29, 256) != 3 )
  {
    Command = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        215,
        "CBR(swscanf_s(wstrConfiguration.c_str(), L\"%s %lu %s\", pwszSwitch, c_cchSwitch, &dwRetries, pwszEncodedPrefix,"
        " c_cchEncodedPrefix) == 3)");
    goto LABEL_29;
  }
  v11 = -1;
  do
    ++v11;
  while ( v29[v11] );
  Command = DdcBase64Coder::Decode(&Block, v29, v11);
  if ( Command < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_29;
    v17 = "CHR(b64coder.Decode(pwszEncodedPrefix, wcslen(pwszEncodedPrefix)))";
    v16 = -38;
    goto LABEL_28;
  }
  if ( v23 == 20 )
  {
    *(_OWORD *)v24 = *(_OWORD *)Block;
    v24[4] = *((_DWORD *)Block + 4);
    v5 = 1;
    Command = DdcDeviceInfoHelper::FmdDisabledByPolicy(&v18, v12);
    if ( Command >= 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v6 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v24[3] >= 0x58028E44000uLL;
      if ( v18 || *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v24[3] >= 0x58028E44000uLL )
      {
        Command = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v20);
        if ( Command >= 0 )
        {
          Command = DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(
                      (DdcTaskSchedulerWrapper *)&v20,
                      (struct CommandPrefix *)v24);
          if ( Command >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_29;
          v17 = "CHR(taskSchedulerWrapper.DeleteLocateCommandRetrySchedule(&prefix))";
          v16 = -18;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_29;
          v17 = "CHR(taskSchedulerWrapper.Initialize())";
          v16 = -19;
        }
      }
      else
      {
        Command = DdcCommandExecutor::ProcessLocateCommand((struct CommandPrefix *)v24, a2, 0, v19);
        if ( Command >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_29;
        v17 = "CHR(DdcCommandExecutor::ProcessLocateCommand(&prefix, pdcHandle, 0, dwRetries))";
        v16 = -13;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_29;
      v17 = "CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fIsFmdDisabledByPolicy))";
      v16 = -32;
    }
LABEL_28:
    McTemplateU0dsqs_EventWriteTransfer(
      v13,
      v12,
      Command,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      v16,
      v17);
    goto LABEL_29;
  }
  Command = -2147418113;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v13,
      v12,
      -2147418113,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      219,
      "CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))");
LABEL_29:
  DdcTraceHelper::TraceLocateCommandRetryResult(v5, v24[0], v19, v6, v18, Command);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(
      v14,
      DEVICE_DIRECTORY_CLIENT_HANDLE_LOCATE_COMMAND_RETRY_RESULT,
      (unsigned int)Command);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v20);
  operator delete(Block);
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x1800063f4  mov     [rsp-8+arg_10], rbx
0x1800063f9  push    rbp
0x1800063fa  push    rsi
0x1800063fb  push    rdi
0x1800063fc  push    r12
0x1800063fe  push    r14
0x180006400  lea     rbp, [rsp-1D0h]
0x180006408  sub     rsp, 2D0h
0x18000640f  mov     rax, cs:__security_cookie
0x180006416  xor     rax, rsp
0x180006419  mov     [rbp+1F0h+var_30], rax
0x180006420  mov     rsi, rdx
0x180006423  mov     rbx, rcx
0x180006426  xorps   xmm0, xmm0
0x180006429  xor     eax, eax
0x18000642b  movups  [rbp+1F0h+var_260], xmm0
0x18000642f  movups  [rbp+1F0h+var_250], xmm0
0x180006433  mov     [rbp+1F0h+var_240], rax
0x180006437  xor     edx, edx; Val
0x180006439  mov     r8d, 200h; Size
0x18000643f  lea     rcx, [rbp+1F0h+var_230]; void *
0x180006443  call    memset_0
0x180006448  xor     r12d, r12d
0x18000644b  mov     [rsp+2F0h+var_2AC], r12d
0x180006450  xorps   xmm0, xmm0
0x180006453  xor     eax, eax
0x180006455  movups  xmmword ptr [rsp+2F0h+var_288], xmm0
0x18000645a  mov     [rsp+2F0h+var_278], eax
0x18000645e  mov     r14d, r12d
0x180006461  mov     [rsp+2F0h+Block], r12
0x180006466  mov     [rsp+2F0h+var_290], r12d
0x18000646b  mov     qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180006470  mov     edi, r12d
0x180006473  mov     [rsp+2F0h+var_2B0], r12d
0x180006478  mov     [rsp+2F0h+var_2A8], r12
0x18000647d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180006484  jz      short loc_1800064A0
0x180006486  lea     rax, [rbp+1F0h+var_270]
0x18000648a  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18000648f  lea     r9d, [r12+1]
0x180006494  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_LOCATE_COMMAND_RETRY
0x18000649b  call    McGenEventWrite_EventWriteTransfer
0x1800064a0  mov     rcx, rbx
0x1800064a3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800064a8  mov     [rsp+2F0h+var_2C0], 100h
0x1800064b0  lea     rcx, [rbp+1F0h+var_230]
0x1800064b4  mov     qword ptr [rsp+2F0h+var_2C8], rcx
0x1800064b9  lea     rcx, [rsp+2F0h+var_2AC]
0x1800064be  mov     qword ptr [rsp+2F0h+var_2D0], rcx
0x1800064c3  mov     r9d, 14h
0x1800064c9  lea     r8, [rbp+1F0h+var_260]
0x1800064cd  lea     rdx, aSLuS; "%s %lu %s"
0x1800064d4  mov     rcx, rax; Buffer
0x1800064d7  call    swscanf_s
0x1800064dc  cmp     eax, 3
0x1800064df  jz      short loc_180006510
0x1800064e1  mov     r8d, 8000FFFFh
0x1800064e7  mov     ebx, r8d
0x1800064ea  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800064f1  jz      loc_1800066C9
0x1800064f7  lea     rax, aCbrSwscanfSWst_0; "CBR(swscanf_s(wstrConfiguration.c_str()"...
0x1800064fe  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x180006503  mov     [rsp+2F0h+var_2D0], 1D7h
0x18000650b  jmp     loc_1800066BD
0x180006510  lea     rax, [rbp+1F0h+var_230]
0x180006514  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006518  inc     r8; unsigned __int64
0x18000651b  cmp     [rax+r8*2], r12w
0x180006520  jnz     short loc_180006518
0x180006522  lea     rdx, [rbp+1F0h+var_230]; unsigned __int16 *
0x180006526  lea     rcx, [rsp+2F0h+Block]; this
0x18000652b  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x180006530  mov     ebx, eax
0x180006532  test    eax, eax
0x180006534  jns     short loc_18000655C
0x180006536  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000653d  jz      loc_1800066C9
0x180006543  lea     rax, aChrB64coderDec_0; "CHR(b64coder.Decode(pwszEncodedPrefix, "...
0x18000654a  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x18000654f  mov     [rsp+2F0h+var_2D0], 1DAh
0x180006557  jmp     loc_1800066BA
0x18000655c  cmp     [rsp+2F0h+var_290], 14h
0x180006561  jz      short loc_180006592
0x180006563  mov     r8d, 8000FFFFh
0x180006569  mov     ebx, r8d
0x18000656c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006573  jz      loc_1800066C9
0x180006579  lea     rax, aCbrB64coderDec; "CBR(b64coder.DecodedLength() == sizeof("...
0x180006580  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x180006585  mov     [rsp+2F0h+var_2D0], 1DBh
0x18000658d  jmp     loc_1800066BD
0x180006592  mov     rax, [rsp+2F0h+Block]
0x180006597  movups  xmm0, xmmword ptr [rax]
0x18000659a  movups  xmmword ptr [rsp+2F0h+var_288], xmm0
0x18000659f  mov     eax, [rax+10h]
0x1800065a2  mov     [rsp+2F0h+var_278], eax
0x1800065a6  mov     r14d, 1
0x1800065ac  lea     rcx, [rsp+2F0h+var_2B0]; int *
0x1800065b1  call    ?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)
0x1800065b6  mov     ebx, eax
0x1800065b8  test    eax, eax
0x1800065ba  jns     short loc_1800065E2
0x1800065bc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x1800065c3  jz      loc_1800066C9
0x1800065c9  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x1800065d0  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x1800065d5  mov     [rsp+2F0h+var_2D0], 1E0h
0x1800065dd  jmp     loc_1800066BA
0x1800065e2  lea     rcx, [rsp+2F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800065e7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800065ed  mov     rax, qword ptr [rsp+2F0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800065f2  sub     rax, qword ptr [rsp+2F0h+var_288+0Ch]
0x1800065f7  mov     edi, r12d
0x1800065fa  mov     rcx, 58028E44000h
0x180006604  cmp     rax, rcx
0x180006607  setnb   dil
0x18000660b  cmp     [rsp+2F0h+var_2B0], r12d
0x180006610  jnz     short loc_180006659
0x180006612  cmp     rax, rcx
0x180006615  jnb     short loc_180006659
0x180006617  mov     r9d, [rsp+2F0h+var_2AC]; unsigned int
0x18000661c  xor     r8d, r8d; int
0x18000661f  mov     rdx, rsi; void *
0x180006622  lea     rcx, [rsp+2F0h+var_288]; struct CommandPrefix *
0x180006627  call    ?ProcessLocateCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAXHK@Z; DdcCommandExecutor::ProcessLocateCommand(CommandPrefix *,void *,int,ulong)
0x18000662c  mov     ebx, eax
0x18000662e  test    eax, eax
0x180006630  jns     loc_1800066C9
0x180006636  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000663d  jz      loc_1800066C9
0x180006643  lea     rax, aChrDdccommande_4; "CHR(DdcCommandExecutor::ProcessLocateCo"...
0x18000664a  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x18000664f  mov     [rsp+2F0h+var_2D0], 1F3h
0x180006657  jmp     short loc_1800066BA
0x180006659  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18000665e  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180006663  mov     ebx, eax
0x180006665  test    eax, eax
0x180006667  jns     short loc_180006688
0x180006669  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x180006670  jz      short loc_1800066C9
0x180006672  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180006679  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x18000667e  mov     [rsp+2F0h+var_2D0], 1EDh
0x180006686  jmp     short loc_1800066BA
0x180006688  lea     rdx, [rsp+2F0h+var_288]; struct CommandPrefix *
0x18000668d  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180006692  call    ?DeleteLocateCommandRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(CommandPrefix *)
0x180006697  mov     ebx, eax
0x180006699  test    eax, eax
0x18000669b  jns     short loc_1800066C9
0x18000669d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x1800066a4  jz      short loc_1800066C9
0x1800066a6  lea     rax, aChrTaskschedul_4; "CHR(taskSchedulerWrapper.DeleteLocateCo"...
0x1800066ad  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x1800066b2  mov     [rsp+2F0h+var_2D0], 1EEh
0x1800066ba  mov     r8d, ebx
0x1800066bd  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800066c4  call    McTemplateU0dsqs_EventWriteTransfer
0x1800066c9  mov     [rsp+2F0h+var_2C8], ebx; int
0x1800066cd  mov     eax, [rsp+2F0h+var_2B0]
0x1800066d1  mov     [rsp+2F0h+var_2D0], eax; int
0x1800066d5  mov     r9d, edi; int
0x1800066d8  mov     r8d, [rsp+2F0h+var_2AC]; unsigned int
0x1800066dd  mov     edx, [rsp+2F0h+var_288]; unsigned int
0x1800066e1  mov     ecx, r14d; int
0x1800066e4  call    ?TraceLocateCommandRetryResult@DdcTraceHelper@@SAXHKKHHJ@Z; DdcTraceHelper::TraceLocateCommandRetryResult(int,ulong,ulong,int,int,long)
0x1800066e9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x1800066f0  jz      short loc_180006702
0x1800066f2  mov     r8d, ebx
0x1800066f5  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_LOCATE_COMMAND_RETRY_RESULT
0x1800066fc  call    McTemplateU0q_EventWriteTransfer
0x180006701  nop
0x180006702  lea     rcx, [rsp+2F0h+var_2A8]
0x180006707  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x18000670c  nop
0x18000670d  mov     rcx, [rsp+2F0h+Block]; Block
0x180006712  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006717  mov     eax, ebx
0x180006719  mov     rcx, [rbp+1F0h+var_30]
0x180006720  xor     rcx, rsp; StackCookie
0x180006723  call    __security_check_cookie
0x180006728  mov     rbx, [rsp+2F0h+arg_10]
0x180006730  add     rsp, 2D0h
0x180006737  pop     r14
0x180006739  pop     r12
0x18000673b  pop     rdi
0x18000673c  pop     rsi
0x18000673d  pop     rbp
0x18000673e  retn
```
