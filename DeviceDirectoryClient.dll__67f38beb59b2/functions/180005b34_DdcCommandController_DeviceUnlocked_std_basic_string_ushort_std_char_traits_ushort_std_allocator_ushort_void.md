# DdcCommandController::DeviceUnlocked(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,void *)

- ea: `0x180005b34`
- end: `0x180005f54`
- name: `?DeviceUnlocked@DdcCommandController@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `1056`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

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
- `0x1800053b4`
- `0x180005b34`
- `0x18000f600`
- `0x1800118fc`
- `0x180011e74`
- `0x180012178`
- `0x180012538`
- `0x1800128fc`
- `0x18001505c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005c18`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005c18`

## string_xrefs

- `0x180005eb1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x180005d16`: `CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))`
- `0x180005e01`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180005c91`: `CBR(swscanf_s(wstrConfiguration.c_str(), L"%s %s %s", pwszSwitch, c_cchSwitch, pwszEncodedPrefix, c_cchEncodedPrefix, pwszEncodedContext, c_cchEncodedContext) == 3)`
- `0x180005db4`: `CBR(b64coder.DecodedLength() == sizeof(UpdateStatusContext))`
- `0x180005e9a`: `CHR(DdcCommandExecutor::UpdateStatus(&prefix, &context, pdcHandle, &dwHttpStatus))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcCommandController::DeviceUnlocked(__int64 a1, void *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // r15d
  int v6; // r14d
  const wchar_t *v7; // rax
  int v8; // edx
  int v9; // ecx
  int updated; // ebx
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // r8
  int v13; // edx
  int v14; // ecx
  __int64 v15; // rcx
  LPVOID v16; // rcx
  char ppv; // [rsp+20h] [rbp-E0h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h]
  unsigned int v26[4]; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  _OWORD v28[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v32[256]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v33[256]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v30 = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  memset_0(v33, 0, sizeof(v33));
  Block = 0;
  v25 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v5 = 0;
  memset(v28, 0, 28);
  v6 = 0;
  v20 = 0;
  v23 = 0;
  v21 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v3, DEVICE_DIRECTORY_CLIENT_DEVICE_UNLOCKED, v4, 1, v29);
  v22 = 0;
  if ( CoCreateInstance(&CLSID_CommandHandler, 0, 1u, &IID_ICommandHandler, &v22) >= 0 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 48LL))(v22);
  v7 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( swscanf_s(v7, L"%s %s %s", &v30, 16, v32, 256, v33, 256) != 3 )
  {
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        133,
        "CBR(swscanf_s(wstrConfiguration.c_str(), L\"%s %s %s\", pwszSwitch, c_cchSwitch, pwszEncodedPrefix, c_cchEncoded"
        "Prefix, pwszEncodedContext, c_cchEncodedContext) == 3)");
    goto LABEL_35;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v32[v12] );
  updated = DdcBase64Coder::Decode(&Block, v32, v12);
  if ( updated < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_35;
    v19 = "CHR(b64coder.Decode(pwszEncodedPrefix, wcslen(pwszEncodedPrefix)))";
    ppv = -120;
    goto LABEL_34;
  }
  if ( v25 == 20 )
  {
    *(_OWORD *)v26 = *(_OWORD *)Block;
    v27 = *((_DWORD *)Block + 4);
    v5 = 1;
    do
      ++v11;
    while ( v33[v11] );
    updated = DdcBase64Coder::Decode(&Block, v33, v11);
    if ( updated < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_35;
      v19 = "CHR(b64coder.Decode(pwszEncodedContext, wcslen(pwszEncodedContext)))";
      ppv = -114;
      goto LABEL_34;
    }
    if ( v25 == 28 )
    {
      v28[0] = *(_OWORD *)Block;
      *(_OWORD *)((char *)v28 + 12) = *(_OWORD *)((char *)Block + 12);
      v6 = 1;
      updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v23);
      if ( updated >= 0 )
      {
        DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(
          (DdcTaskSchedulerWrapper *)&v23,
          (struct CommandPrefix *)v26);
        DdcTaskSchedulerWrapper::DeleteDeviceUnlockedEventSchedule(
          (DdcTaskSchedulerWrapper *)&v23,
          (struct CommandPrefix *)v26);
        updated = DdcDeviceInfoHelper::FmdDisabledByPolicy(&v20);
        if ( updated >= 0 )
        {
          if ( v20 )
            goto LABEL_35;
          LODWORD(v28[1]) = 6;
          updated = DdcCommandExecutor::UpdateStatus(
                      (struct CommandPrefix *)v26,
                      (struct UpdateStatusContext *)v28,
                      a2,
                      &v21);
          if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_35;
          v19 = "CHR(DdcCommandExecutor::UpdateStatus(&prefix, &context, pdcHandle, &dwHttpStatus))";
          ppv = -89;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_35;
          v19 = "CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fIsFmdDisabledByPolicy))";
          ppv = -97;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_35;
        v19 = "CHR(taskSchedulerWrapper.Initialize())";
        ppv = -108;
      }
LABEL_34:
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        updated,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        ppv,
        v19);
      goto LABEL_35;
    }
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        143,
        "CBR(b64coder.DecodedLength() == sizeof(UpdateStatusContext))");
  }
  else
  {
    updated = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        137,
        "CBR(b64coder.DecodedLength() == sizeof(CommandPrefix))");
  }
LABEL_35:
  DdcTraceHelper::TraceDeviceUnlockedResult(v5, v6, v26[0], v20, v21, updated);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v15, DEVICE_DIRECTORY_CLIENT_DEVICE_UNLOCKED_RESULT, (unsigned int)updated);
  v16 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  }
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v23);
  operator delete(Block);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005b34  mov     [rsp-8+arg_10], rbx
0x180005b39  push    rbp
0x180005b3a  push    rsi
0x180005b3b  push    rdi
0x180005b3c  push    r12
0x180005b3e  push    r13
0x180005b40  push    r14
0x180005b42  push    r15
0x180005b44  lea     rbp, [rsp-3E0h]
0x180005b4c  sub     rsp, 4E0h
0x180005b53  mov     rax, cs:__security_cookie
0x180005b5a  xor     rax, rsp
0x180005b5d  mov     [rbp+410h+var_40], rax
0x180005b64  mov     rsi, rdx
0x180005b67  mov     rbx, rcx
0x180005b6a  xorps   xmm0, xmm0
0x180005b6d  movups  [rbp+410h+var_460], xmm0
0x180005b71  movups  [rbp+410h+var_450], xmm0
0x180005b75  mov     edi, 200h
0x180005b7a  mov     r8d, edi; Size
0x180005b7d  xor     edx, edx; Val
0x180005b7f  lea     rcx, [rbp+410h+var_440]; void *
0x180005b83  call    memset_0
0x180005b88  mov     r8d, edi; Size
0x180005b8b  xor     edx, edx; Val
0x180005b8d  lea     rcx, [rbp+410h+var_240]; void *
0x180005b94  call    memset_0
0x180005b99  xor     r13d, r13d
0x180005b9c  mov     [rsp+510h+Block], r13
0x180005ba1  mov     [rsp+510h+var_4B0], r13d
0x180005ba6  xorps   xmm0, xmm0
0x180005ba9  xor     eax, eax
0x180005bab  movups  xmmword ptr [rsp+510h+var_4A8], xmm0
0x180005bb0  mov     [rsp+510h+var_498], eax
0x180005bb4  mov     r15d, r13d
0x180005bb7  movups  [rbp+410h+var_490], xmm0
0x180005bbb  movups  [rbp+410h+var_490+0Ch], xmm0
0x180005bbf  mov     r14d, r13d
0x180005bc2  mov     [rsp+510h+var_4D0], r13d
0x180005bc7  mov     [rsp+510h+var_4C0], r13
0x180005bcc  mov     [rsp+510h+var_4CC], r13d
0x180005bd1  lea     r12d, [r13+1]
0x180005bd5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180005bdc  jz      short loc_180005BF6
0x180005bde  lea     rax, [rbp+410h+var_470]
0x180005be2  mov     [rsp+510h+ppv], rax
0x180005be7  mov     r9d, r12d
0x180005bea  lea     rdx, DEVICE_DIRECTORY_CLIENT_DEVICE_UNLOCKED
0x180005bf1  call    McGenEventWrite_EventWriteTransfer
0x180005bf6  mov     [rsp+510h+var_4C8], r13
0x180005bfb  lea     rax, [rsp+510h+var_4C8]
0x180005c00  mov     [rsp+510h+ppv], rax; ppv
0x180005c05  lea     r9, IID_ICommandHandler; riid
0x180005c0c  mov     r8d, r12d; dwClsContext
0x180005c0f  xor     edx, edx; pUnkOuter
0x180005c11  lea     rcx, CLSID_CommandHandler; rclsid
0x180005c18  call    cs:__imp_CoCreateInstance
0x180005c1e  test    eax, eax
0x180005c20  js      short loc_180005C33
0x180005c22  mov     rcx, [rsp+510h+var_4C8]
0x180005c27  mov     rax, [rcx]
0x180005c2a  mov     rax, [rax+30h]
0x180005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c33  mov     rcx, rbx
0x180005c36  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180005c3b  mov     edx, 100h
0x180005c40  mov     [rsp+510h+var_4D8], edx
0x180005c44  lea     rcx, [rbp+410h+var_240]
0x180005c4b  mov     [rsp+510h+var_4E0], rcx
0x180005c50  mov     [rsp+510h+var_4E8], edx
0x180005c54  lea     rcx, [rbp+410h+var_440]
0x180005c58  mov     [rsp+510h+ppv], rcx
0x180005c5d  mov     r9d, 10h
0x180005c63  lea     r8, [rbp+410h+var_460]
0x180005c67  lea     rdx, aSSS; "%s %s %s"
0x180005c6e  mov     rcx, rax; Buffer
0x180005c71  call    swscanf_s
0x180005c76  cmp     eax, 3
0x180005c79  jz      short loc_180005CAA
0x180005c7b  mov     r8d, 8000FFFFh
0x180005c81  mov     ebx, r8d
0x180005c84  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005c8b  jz      loc_180005EBD
0x180005c91  lea     rax, aCbrSwscanfSWst; "CBR(swscanf_s(wstrConfiguration.c_str()"...
0x180005c98  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005c9d  mov     dword ptr [rsp+510h+ppv], 285h
0x180005ca5  jmp     loc_180005EB1
0x180005caa  lea     rax, [rbp+410h+var_440]
0x180005cae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180005cb2  mov     r8, rdi
0x180005cb5  inc     r8; unsigned __int64
0x180005cb8  cmp     [rax+r8*2], r13w
0x180005cbd  jnz     short loc_180005CB5
0x180005cbf  lea     rdx, [rbp+410h+var_440]; unsigned __int16 *
0x180005cc3  lea     rcx, [rsp+510h+Block]; this
0x180005cc8  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x180005ccd  mov     ebx, eax
0x180005ccf  test    eax, eax
0x180005cd1  jns     short loc_180005CF9
0x180005cd3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005cda  jz      loc_180005EBD
0x180005ce0  lea     rax, aChrB64coderDec_0; "CHR(b64coder.Decode(pwszEncodedPrefix, "...
0x180005ce7  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005cec  mov     dword ptr [rsp+510h+ppv], 288h
0x180005cf4  jmp     loc_180005EAE
0x180005cf9  cmp     [rsp+510h+var_4B0], 14h
0x180005cfe  jz      short loc_180005D2F
0x180005d00  mov     r8d, 8000FFFFh
0x180005d06  mov     ebx, r8d
0x180005d09  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005d10  jz      loc_180005EBD
0x180005d16  lea     rax, aCbrB64coderDec; "CBR(b64coder.DecodedLength() == sizeof("...
0x180005d1d  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005d22  mov     dword ptr [rsp+510h+ppv], 289h
0x180005d2a  jmp     loc_180005EB1
0x180005d2f  mov     rax, [rsp+510h+Block]
0x180005d34  movups  xmm0, xmmword ptr [rax]
0x180005d37  movups  xmmword ptr [rsp+510h+var_4A8], xmm0
0x180005d3c  mov     eax, [rax+10h]
0x180005d3f  mov     [rsp+510h+var_498], eax
0x180005d43  mov     r15d, r12d
0x180005d46  lea     rax, [rbp+410h+var_240]
0x180005d4d  inc     rdi
0x180005d50  cmp     [rax+rdi*2], r13w
0x180005d55  jnz     short loc_180005D4D
0x180005d57  mov     r8, rdi; unsigned __int64
0x180005d5a  lea     rdx, [rbp+410h+var_240]; unsigned __int16 *
0x180005d61  lea     rcx, [rsp+510h+Block]; this
0x180005d66  call    ?Decode@DdcBase64Coder@@QEAAJPEBG_K@Z; DdcBase64Coder::Decode(ushort const *,unsigned __int64)
0x180005d6b  mov     ebx, eax
0x180005d6d  test    eax, eax
0x180005d6f  jns     short loc_180005D97
0x180005d71  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005d78  jz      loc_180005EBD
0x180005d7e  lea     rax, aChrB64coderDec_1; "CHR(b64coder.Decode(pwszEncodedContext,"...
0x180005d85  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005d8a  mov     dword ptr [rsp+510h+ppv], 28Eh
0x180005d92  jmp     loc_180005EAE
0x180005d97  cmp     [rsp+510h+var_4B0], 1Ch
0x180005d9c  jz      short loc_180005DCD
0x180005d9e  mov     r8d, 8000FFFFh
0x180005da4  mov     ebx, r8d
0x180005da7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005dae  jz      loc_180005EBD
0x180005db4  lea     rax, aCbrB64coderDec_0; "CBR(b64coder.DecodedLength() == sizeof("...
0x180005dbb  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005dc0  mov     dword ptr [rsp+510h+ppv], 28Fh
0x180005dc8  jmp     loc_180005EB1
0x180005dcd  mov     rax, [rsp+510h+Block]
0x180005dd2  movups  xmm0, xmmword ptr [rax]
0x180005dd5  movups  [rbp+410h+var_490], xmm0
0x180005dd9  movups  xmm1, xmmword ptr [rax+0Ch]
0x180005ddd  movups  [rbp+410h+var_490+0Ch], xmm1
0x180005de1  mov     r14d, r12d
0x180005de4  lea     rcx, [rsp+510h+var_4C0]; this
0x180005de9  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180005dee  mov     ebx, eax
0x180005df0  test    eax, eax
0x180005df2  jns     short loc_180005E1A
0x180005df4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005dfb  jz      loc_180005EBD
0x180005e01  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180005e08  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005e0d  mov     dword ptr [rsp+510h+ppv], 294h
0x180005e15  jmp     loc_180005EAE
0x180005e1a  lea     rdx, [rsp+510h+var_4A8]; struct CommandPrefix *
0x180005e1f  lea     rcx, [rsp+510h+var_4C0]; this
0x180005e24  call    ?DeleteUpdateStatusRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(CommandPrefix *)
0x180005e29  lea     rdx, [rsp+510h+var_4A8]; struct CommandPrefix *
0x180005e2e  lea     rcx, [rsp+510h+var_4C0]; this
0x180005e33  call    ?DeleteDeviceUnlockedEventSchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteDeviceUnlockedEventSchedule(CommandPrefix *)
0x180005e38  lea     rcx, [rsp+510h+var_4D0]; int *
0x180005e3d  call    ?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)
0x180005e42  mov     ebx, eax
0x180005e44  test    eax, eax
0x180005e46  jns     short loc_180005E67
0x180005e48  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005e4f  jz      short loc_180005EBD
0x180005e51  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x180005e58  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005e5d  mov     dword ptr [rsp+510h+ppv], 29Fh
0x180005e65  jmp     short loc_180005EAE
0x180005e67  cmp     [rsp+510h+var_4D0], r13d
0x180005e6c  jnz     short loc_180005EBD
0x180005e6e  mov     [rbp+410h+var_480], 6
0x180005e75  lea     r9, [rsp+510h+var_4CC]; unsigned int *
0x180005e7a  mov     r8, rsi; void *
0x180005e7d  lea     rdx, [rbp+410h+var_490]; struct UpdateStatusContext *
0x180005e81  lea     rcx, [rsp+510h+var_4A8]; struct CommandPrefix *
0x180005e86  call    ?UpdateStatus@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@PEAXPEAK@Z; DdcCommandExecutor::UpdateStatus(CommandPrefix *,UpdateStatusContext *,void *,ulong *)
0x180005e8b  mov     ebx, eax
0x180005e8d  test    eax, eax
0x180005e8f  jns     short loc_180005EBD
0x180005e91  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r12b
0x180005e98  jz      short loc_180005EBD
0x180005e9a  lea     rax, aChrDdccommande_2; "CHR(DdcCommandExecutor::UpdateStatus(&p"...
0x180005ea1  mov     qword ptr [rsp+510h+var_4E8], rax
0x180005ea6  mov     dword ptr [rsp+510h+ppv], 2A7h
0x180005eae  mov     r8d, ebx
0x180005eb1  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180005eb8  call    McTemplateU0dsqs_EventWriteTransfer
0x180005ebd  mov     [rsp+510h+var_4E8], ebx; int
0x180005ec1  mov     eax, [rsp+510h+var_4CC]
0x180005ec5  mov     dword ptr [rsp+510h+ppv], eax; unsigned int
0x180005ec9  mov     r9d, [rsp+510h+var_4D0]; int
0x180005ece  mov     r8d, [rsp+510h+var_4A8]; unsigned int
0x180005ed3  mov     edx, r14d; int
0x180005ed6  mov     ecx, r15d; int
0x180005ed9  call    ?TraceDeviceUnlockedResult@DdcTraceHelper@@SAXHHKHKJ@Z; DdcTraceHelper::TraceDeviceUnlockedResult(int,int,ulong,int,ulong,long)
0x180005ede  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180005ee5  jz      short loc_180005EF7
0x180005ee7  mov     r8d, ebx
0x180005eea  lea     rdx, DEVICE_DIRECTORY_CLIENT_DEVICE_UNLOCKED_RESULT
0x180005ef1  call    McTemplateU0q_EventWriteTransfer
0x180005ef6  nop
0x180005ef7  mov     rcx, [rsp+510h+var_4C8]
0x180005efc  test    rcx, rcx
0x180005eff  jz      short loc_180005F13
0x180005f01  mov     [rsp+510h+var_4C8], r13
0x180005f06  mov     rax, [rcx]
0x180005f09  mov     rax, [rax+10h]
0x180005f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f12  nop
0x180005f13  lea     rcx, [rsp+510h+var_4C0]
0x180005f18  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180005f1d  nop
0x180005f1e  mov     rcx, [rsp+510h+Block]; Block
0x180005f23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005f28  mov     eax, ebx
0x180005f2a  mov     rcx, [rbp+410h+var_40]
0x180005f31  xor     rcx, rsp; StackCookie
0x180005f34  call    __security_check_cookie
0x180005f39  mov     rbx, [rsp+510h+arg_10]
0x180005f41  add     rsp, 4E0h
0x180005f48  pop     r15
0x180005f4a  pop     r14
0x180005f4c  pop     r13
0x180005f4e  pop     r12
0x180005f50  pop     rdi
0x180005f51  pop     rsi
0x180005f52  pop     rbp
0x180005f53  retn
```
