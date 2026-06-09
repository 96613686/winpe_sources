# DdcCommandController::HandleUpdateStatusRetry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x180006da4`
- end: `0x1800071c7`
- name: `?HandleUpdateStatusRetry@DdcCommandController@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `1059`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

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
- `0x1800059a0`
- `0x180006da4`
- `0x18000f600`
- `0x1800118fc`
- `0x180011e74`
- `0x180012538`
- `0x1800128fc`
- `0x18001505c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007060`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007060`

## string_xrefs

- `0x180007135`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x180006f56`: `CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))`
- `0x1800070ea`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180006ecd`: `CBR(swscanf_s(wstrConfiguration.c_str(), L"%s %s %s", pwszSwitch, c_cchSwitch, pwszEncodedPrefix, c_cchEncodedPrefix, pwszEncodedContext, c_cchEncodedContext) == 3)`
- `0x180006ff5`: `CBR(b64coder.DecodedLength() == sizeof(UpdateStatusContext))`
- `0x18000711e`: `CHR(taskSchedulerWrapper.DeleteUpdateStatusRetrySchedule(&prefix))`
- `0x1800070b2`: `CHR(DdcCommandExecutor::UpdateStatus(&prefix, &context, pdcHandle, &dwHttpStatus))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcCommandController::HandleUpdateStatusRetry(__int64 a1, void *a2)
{
  __int64 v3; // r8
  int v4; // r12d
  int v5; // r15d
  BOOL v6; // edi
  const wchar_t *v7; // rax
  int v8; // edx
  int v9; // ecx
  int updated; // ebx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // r8
  int v13; // edx
  int v14; // ecx
  __int64 v15; // rcx
  char v17; // [rsp+20h] [rbp-E0h]
  const char *v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-BCh] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v25[6]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[22]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v30[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v31[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v28 = 0;
  memset(v29, 0, sizeof(v29));
  memset_0(v30, 0, sizeof(v30));
  memset_0(v31, 0, sizeof(v31));
  Block = 0;
  v22 = 0;
  memset(v25, 0, 20);
  v4 = 0;
  memset(v26, 0, 28);
  v5 = 0;
  SystemTimeAsFileTime = 0;
  v6 = 0;
  v19 = 0;
  v23 = 0;
  v20 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(0, DEVICE_DIRECTORY_CLIENT_HANDLE_UPDATE_STATUS_RETRY, v3, 1, v27);
  v7 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( swscanf_s(v7, L"%s %s %s", &v28, 19, v30, 256, v31, 256) != 3 )
  {
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        40,
        "CBR(swscanf_s(wstrConfiguration.c_str(), L\"%s %s %s\", pwszSwitch, c_cchSwitch, pwszEncodedPrefix, c_cchEncoded"
        "Prefix, pwszEncodedContext, c_cchEncodedContext) == 3)");
    goto LABEL_37;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v30[v12] );
  updated = DdcBase64Coder::Decode(&Block, v30, v12);
  v14 = 0;
  if ( updated < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_37;
    v18 = "CHR(b64coder.Decode(pwszEncodedPrefix, wcslen(pwszEncodedPrefix)))";
    v17 = 43;
    goto LABEL_36;
  }
  if ( v22 == 20 )
  {
    *(_OWORD *)v25 = *(_OWORD *)Block;
    v25[4] = *((_DWORD *)Block + 4);
    v4 = 1;
    do
      ++v11;
    while ( v31[v11] );
    updated = DdcBase64Coder::Decode(&Block, v31, v11);
    if ( updated < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_37;
      v18 = "CHR(b64coder.Decode(pwszEncodedContext, wcslen(pwszEncodedContext)))";
      v17 = 49;
      goto LABEL_36;
    }
    if ( v22 == 28 )
    {
      v26[0] = *(_OWORD *)Block;
      *(_OWORD *)((char *)v26 + 12) = *(_OWORD *)((char *)Block + 12);
      v5 = 1;
      updated = DdcDeviceInfoHelper::FmdDisabledByPolicy(&v19, v13);
      if ( updated >= 0 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v25[3] >= 0x58028E44000uLL || v19 )
        {
          v6 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v25[3] >= 0x58028E44000uLL;
          updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v23);
          if ( updated >= 0 )
          {
            updated = DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(
                        (DdcTaskSchedulerWrapper *)&v23,
                        (struct CommandPrefix *)v25);
            if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_37;
            v18 = "CHR(taskSchedulerWrapper.DeleteUpdateStatusRetrySchedule(&prefix))";
            v17 = 69;
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_37;
            v18 = "CHR(taskSchedulerWrapper.Initialize())";
            v17 = 68;
          }
        }
        else
        {
          updated = DdcCommandExecutor::UpdateStatus(
                      (struct CommandPrefix *)v25,
                      (struct UpdateStatusContext *)v26,
                      a2,
                      &v20);
          if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_37;
          v18 = "CHR(DdcCommandExecutor::UpdateStatus(&prefix, &context, pdcHandle, &dwHttpStatus))";
          v17 = 74;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_37;
        v18 = "CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fIsFmdDisabledByPolicy))";
        v17 = 55;
      }
LABEL_36:
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        updated,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        v17,
        v18);
      goto LABEL_37;
    }
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        50,
        "CBR(b64coder.DecodedLength() == sizeof(UpdateStatusContext))");
  }
  else
  {
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        v13,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        44,
        "CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))");
  }
LABEL_37:
  DdcTraceHelper::TraceUpdateStatusRetryResult(v4, v5, v25[0], DWORD2(v26[1]), v6, v19, v20, updated);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(
      v15,
      DEVICE_DIRECTORY_CLIENT_HANDLE_UPDATE_STATUS_RETRY_RESULT,
      (unsigned int)updated);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v23);
  operator delete(Block);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180006da4  mov     [rsp-8+arg_10], rbx
0x180006da9  push    rbp
0x180006daa  push    rsi
0x180006dab  push    rdi
0x180006dac  push    r12
0x180006dae  push    r13
0x180006db0  push    r14
0x180006db2  push    r15
0x180006db4  lea     rbp, [rsp-3F0h]
0x180006dbc  sub     rsp, 4F0h
0x180006dc3  mov     rax, cs:__security_cookie
0x180006dca  xor     rax, rsp
0x180006dcd  mov     [rbp+420h+var_40], rax
0x180006dd4  mov     r14, rdx
0x180006dd7  mov     rbx, rcx
0x180006dda  xorps   xmm0, xmm0
0x180006ddd  xor     eax, eax
0x180006ddf  movups  [rbp+420h+var_470], xmm0
0x180006de3  movups  xmmword ptr [rbp+420h+var_460], xmm0
0x180006de7  mov     qword ptr [rbp+420h+var_460+0Eh], rax
0x180006deb  mov     edi, 200h
0x180006df0  mov     r8d, edi; Size
0x180006df3  xor     edx, edx; Val
0x180006df5  lea     rcx, [rbp+420h+var_440]; void *
0x180006df9  call    memset_0
0x180006dfe  mov     r8d, edi; Size
0x180006e01  xor     edx, edx; Val
0x180006e03  lea     rcx, [rbp+420h+var_240]; void *
0x180006e0a  call    memset_0
0x180006e0f  xor     ecx, ecx
0x180006e11  mov     [rsp+520h+Block], rcx
0x180006e16  mov     [rsp+520h+var_4D0], ecx
0x180006e1a  xorps   xmm0, xmm0
0x180006e1d  xor     eax, eax
0x180006e1f  movups  xmmword ptr [rsp+520h+var_4B8], xmm0
0x180006e24  mov     [rsp+520h+var_4A8], eax
0x180006e28  mov     r12d, ecx
0x180006e2b  movups  [rbp+420h+var_4A0], xmm0
0x180006e2f  movups  [rbp+420h+var_4A0+0Ch], xmm0
0x180006e33  mov     r15d, ecx
0x180006e36  mov     qword ptr [rsp+520h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180006e3b  mov     edi, ecx
0x180006e3d  mov     [rsp+520h+var_4E0], ecx
0x180006e41  mov     [rsp+520h+var_4C8], rcx
0x180006e46  mov     [rsp+520h+var_4DC], ecx
0x180006e4a  lea     r13d, [rcx+1]
0x180006e4e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180006e55  jz      short loc_180006E6F
0x180006e57  lea     rax, [rbp+420h+var_480]
0x180006e5b  mov     qword ptr [rsp+520h+var_500], rax
0x180006e60  mov     r9d, r13d
0x180006e63  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_UPDATE_STATUS_RETRY
0x180006e6a  call    McGenEventWrite_EventWriteTransfer
0x180006e6f  mov     rcx, rbx
0x180006e72  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180006e77  mov     edx, 100h
0x180006e7c  mov     [rsp+520h+var_4E8], edx
0x180006e80  lea     rcx, [rbp+420h+var_240]
0x180006e87  mov     qword ptr [rsp+520h+var_4F0], rcx
0x180006e8c  mov     [rsp+520h+var_4F8], edx
0x180006e90  lea     rcx, [rbp+420h+var_440]
0x180006e94  mov     qword ptr [rsp+520h+var_500], rcx
0x180006e99  mov     r9d, 13h
0x180006e9f  lea     r8, [rbp+420h+var_470]
0x180006ea3  lea     rdx, aSSS; "%s %s %s"
0x180006eaa  mov     rcx, rax; Buffer
0x180006ead  call    swscanf_s
0x180006eb2  cmp     eax, 3
0x180006eb5  jz      short loc_180006EE6
0x180006eb7  mov     r8d, 8000FFFFh
0x180006ebd  mov     ebx, r8d
0x180006ec0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x180006ec7  jz      loc_180007141
0x180006ecd  lea     rax, aCbrSwscanfSWst; "CBR(swscanf_s(wstrConfiguration.c_str()"...
0x180006ed4  mov     qword ptr [rsp+520h+var_4F8], rax
0x180006ed9  mov     [rsp+520h+var_500], 228h
0x180006ee1  jmp     loc_180007135
0x180006ee6  lea     rcx, [rbp+420h+var_440]
0x180006eea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006eee  mov     r8, rsi
0x180006ef1  xor     eax, eax
0x180006ef3  inc     r8; unsigned __int64
0x180006ef6  cmp     [rcx+r8*2], ax
0x180006efb  jnz     short loc_180006EF3
0x180006efd  lea     rdx, [rbp+420h+var_440]; unsigned __int16 *
0x180006f01  lea     rcx, [rsp+520h+Block]; this
0x180006f06  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x180006f0b  mov     ebx, eax
0x180006f0d  xor     ecx, ecx
0x180006f0f  test    eax, eax
0x180006f11  jns     short loc_180006F39
0x180006f13  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x180006f1a  jz      loc_180007141
0x180006f20  lea     rax, aChrB64coderDec_0; "CHR(b64coder.Decode(pwszEncodedPrefix, "...
0x180006f27  mov     qword ptr [rsp+520h+var_4F8], rax
0x180006f2c  mov     [rsp+520h+var_500], 22Bh
0x180006f34  jmp     loc_180007132
0x180006f39  cmp     [rsp+520h+var_4D0], 14h
0x180006f3e  jz      short loc_180006F6F
0x180006f40  mov     r8d, 8000FFFFh
0x180006f46  mov     ebx, r8d
0x180006f49  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x180006f50  jz      loc_180007141
0x180006f56  lea     rax, aCbrB64coderDec; "CBR(b64coder.DecodedLength() == sizeof("...
0x180006f5d  mov     qword ptr [rsp+520h+var_4F8], rax
0x180006f62  mov     [rsp+520h+var_500], 22Ch
0x180006f6a  jmp     loc_180007135
0x180006f6f  mov     rax, [rsp+520h+Block]
0x180006f74  movups  xmm0, xmmword ptr [rax]
0x180006f77  movups  xmmword ptr [rsp+520h+var_4B8], xmm0
0x180006f7c  mov     eax, [rax+10h]
0x180006f7f  mov     [rsp+520h+var_4A8], eax
0x180006f83  mov     r12d, r13d
0x180006f86  lea     rax, [rbp+420h+var_240]
0x180006f8d  inc     rsi
0x180006f90  cmp     [rax+rsi*2], cx
0x180006f94  jnz     short loc_180006F8D
0x180006f96  mov     r8, rsi; unsigned __int64
0x180006f99  lea     rdx, [rbp+420h+var_240]; unsigned __int16 *
0x180006fa0  lea     rcx, [rsp+520h+Block]; this
0x180006fa5  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x180006faa  mov     ebx, eax
0x180006fac  xor     esi, esi
0x180006fae  test    eax, eax
0x180006fb0  jns     short loc_180006FD8
0x180006fb2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x180006fb9  jz      loc_180007141
0x180006fbf  lea     rax, aChrB64coderDec_1; "CHR(b64coder.Decode(pwszEncodedContext,"...
0x180006fc6  mov     qword ptr [rsp+520h+var_4F8], rax
0x180006fcb  mov     [rsp+520h+var_500], 231h
0x180006fd3  jmp     loc_180007132
0x180006fd8  cmp     [rsp+520h+var_4D0], 1Ch
0x180006fdd  jz      short loc_18000700E
0x180006fdf  mov     r8d, 8000FFFFh
0x180006fe5  mov     ebx, r8d
0x180006fe8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x180006fef  jz      loc_180007141
0x180006ff5  lea     rax, aCbrB64coderDec_0; "CBR(b64coder.DecodedLength() == sizeof("...
0x180006ffc  mov     qword ptr [rsp+520h+var_4F8], rax
0x180007001  mov     [rsp+520h+var_500], 232h
0x180007009  jmp     loc_180007135
0x18000700e  mov     rax, [rsp+520h+Block]
0x180007013  movups  xmm0, xmmword ptr [rax]
0x180007016  movups  [rbp+420h+var_4A0], xmm0
0x18000701a  movups  xmm1, xmmword ptr [rax+0Ch]
0x18000701e  movups  [rbp+420h+var_4A0+0Ch], xmm1
0x180007022  mov     r15d, r13d
0x180007025  lea     rcx, [rsp+520h+var_4E0]; int *
0x18000702a  call    ?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)
0x18000702f  mov     ebx, eax
0x180007031  test    eax, eax
0x180007033  jns     short loc_18000705B
0x180007035  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x18000703c  jz      loc_180007141
0x180007042  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x180007049  mov     qword ptr [rsp+520h+var_4F8], rax
0x18000704e  mov     [rsp+520h+var_500], 237h
0x180007056  jmp     loc_180007132
0x18000705b  lea     rcx, [rsp+520h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007060  call    cs:__imp_GetSystemTimeAsFileTime
0x180007066  mov     rax, qword ptr [rsp+520h+SystemTimeAsFileTime.dwLowDateTime]
0x18000706b  sub     rax, qword ptr [rsp+520h+var_4B8+0Ch]
0x180007070  mov     rcx, 58028E44000h
0x18000707a  cmp     rax, rcx
0x18000707d  jnb     short loc_1800070C8
0x18000707f  cmp     [rsp+520h+var_4E0], esi
0x180007083  jnz     short loc_1800070C8
0x180007085  lea     r9, [rsp+520h+var_4DC]; unsigned int *
0x18000708a  mov     r8, r14; void *
0x18000708d  lea     rdx, [rbp+420h+var_4A0]; struct UpdateStatusContext *
0x180007091  lea     rcx, [rsp+520h+var_4B8]; struct CommandPrefix *
0x180007096  call    ?UpdateStatus@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@PEAXPEAK@Z; DdcCommandExecutor::UpdateStatus(CommandPrefix *,UpdateStatusContext *,void *,ulong *)
0x18000709b  mov     ebx, eax
0x18000709d  test    eax, eax
0x18000709f  jns     loc_180007141
0x1800070a5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x1800070ac  jz      loc_180007141
0x1800070b2  lea     rax, aChrDdccommande_2; "CHR(DdcCommandExecutor::UpdateStatus(&p"...
0x1800070b9  mov     qword ptr [rsp+520h+var_4F8], rax
0x1800070be  mov     [rsp+520h+var_500], 24Ah
0x1800070c6  jmp     short loc_180007132
0x1800070c8  mov     edi, esi
0x1800070ca  cmp     rax, rcx
0x1800070cd  setnb   dil
0x1800070d1  lea     rcx, [rsp+520h+var_4C8]; this
0x1800070d6  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x1800070db  mov     ebx, eax
0x1800070dd  test    eax, eax
0x1800070df  jns     short loc_180007100
0x1800070e1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x1800070e8  jz      short loc_180007141
0x1800070ea  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x1800070f1  mov     qword ptr [rsp+520h+var_4F8], rax
0x1800070f6  mov     [rsp+520h+var_500], 244h
0x1800070fe  jmp     short loc_180007132
0x180007100  lea     rdx, [rsp+520h+var_4B8]; struct CommandPrefix *
0x180007105  lea     rcx, [rsp+520h+var_4C8]; this
0x18000710a  call    ?DeleteUpdateStatusRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(CommandPrefix *)
0x18000710f  mov     ebx, eax
0x180007111  test    eax, eax
0x180007113  jns     short loc_180007141
0x180007115  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r13b
0x18000711c  jz      short loc_180007141
0x18000711e  lea     rax, aChrTaskschedul_5; "CHR(taskSchedulerWrapper.DeleteUpdateSt"...
0x180007125  mov     qword ptr [rsp+520h+var_4F8], rax
0x18000712a  mov     [rsp+520h+var_500], 245h
0x180007132  mov     r8d, ebx
0x180007135  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000713c  call    McTemplateU0dsqs_EventWriteTransfer
0x180007141  mov     [rsp+520h+var_4E8], ebx; int
0x180007145  mov     eax, [rsp+520h+var_4DC]
0x180007149  mov     [rsp+520h+var_4F0], eax; unsigned int
0x18000714d  mov     eax, [rsp+520h+var_4E0]
0x180007151  mov     [rsp+520h+var_4F8], eax; int
0x180007155  mov     [rsp+520h+var_500], edi; int
0x180007159  mov     r9d, [rbp+420h+var_488]; unsigned int
0x18000715d  mov     r8d, [rsp+520h+var_4B8]; unsigned int
0x180007162  mov     edx, r15d; int
0x180007165  mov     ecx, r12d; int
0x180007168  call    ?TraceUpdateStatusRetryResult@DdcTraceHelper@@SAXHHKKHHKJ@Z; DdcTraceHelper::TraceUpdateStatusRetryResult(int,int,ulong,ulong,int,int,ulong,long)
0x18000716d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180007174  jz      short loc_180007186
0x180007176  mov     r8d, ebx
0x180007179  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_UPDATE_STATUS_RETRY_RESULT
0x180007180  call    McTemplateU0q_EventWriteTransfer
0x180007185  nop
0x180007186  lea     rcx, [rsp+520h+var_4C8]
0x18000718b  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180007190  nop
0x180007191  mov     rcx, [rsp+520h+Block]; Block
0x180007196  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000719b  mov     eax, ebx
0x18000719d  mov     rcx, [rbp+420h+var_40]
0x1800071a4  xor     rcx, rsp; StackCookie
0x1800071a7  call    __security_check_cookie
0x1800071ac  mov     rbx, [rsp+520h+arg_10]
0x1800071b4  add     rsp, 4F0h
0x1800071bb  pop     r15
0x1800071bd  pop     r14
0x1800071bf  pop     r13
0x1800071c1  pop     r12
0x1800071c3  pop     rdi
0x1800071c4  pop     rsi
0x1800071c5  pop     rbp
0x1800071c6  retn
```
