# DdcCommandController::HandleCommand(void *)

- ea: `0x180005f5c`
- end: `0x180006229`
- name: `?HandleCommand@DdcCommandController@@SAJPEAX@Z`
- size: `717`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x1800035b0`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x180005444`
- `0x180005a64`
- `0x180005a9c`
- `0x180005f5c`
- `0x1800073b8`
- `0x1800101f0`
- `0x1800107e0`
- `0x180010dd4`
- `0x180011158`
- `0x18001122c`

## string_xrefs

- `0x180006198`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x180006056`: `CHR(DdcCommandExecutor::ProcessLocateCommand(&prefix, pdcHandle, fEnableLocation))`
- `0x180006097`: `CHR(DdcCommandExecutor::ProcessRingCommand(&prefix, pdcHandle))`
- `0x1800060f0`: `CHR(DdcCommandExecutor::ProcessLockCommand(&prefix, pdcHandle, pwszPin, pwszCpn, fRingAfterLock, vCids))`
- `0x18000612d`: `CHR(DdcCommandExecutor::ProcessWipeCommand(&prefix, pdcHandle))`
- `0x180006160`: `CHR(DdcCommandExecutor::ProcessStartFamilySafetyCommand(&prefix))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DdcCommandController::HandleCommand(void *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int CommandState; // eax
  unsigned int v5; // ebx
  int v6; // edx
  __int64 v7; // rcx
  int v8; // edx
  int Command; // ebx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v15; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+44h] [rbp-15h] BYREF
  int v17; // [rsp+48h] [rbp-11h] BYREF
  void *Block; // [rsp+50h] [rbp-9h] BYREF
  void *v19; // [rsp+58h] [rbp-1h] BYREF
  __int64 v20[3]; // [rsp+60h] [rbp+7h] BYREF
  unsigned int v21[4]; // [rsp+78h] [rbp+1Fh] BYREF
  int v22; // [rsp+88h] [rbp+2Fh]
  _BYTE v23[16]; // [rsp+90h] [rbp+37h] BYREF

  *(_OWORD *)v21 = 0;
  v22 = 0;
  v15 = 0;
  Block = 0;
  v19 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(v20);
  v17 = 0;
  v16 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v2, DEVICE_DIRECTORY_CLIENT_HANDLE_COMMAND, v3, 1, v23);
  CommandState = DdcCommandController::QueryCommandState(
                   (unsigned int)v21,
                   (unsigned int)&v15,
                   (unsigned int)&Block,
                   (unsigned int)&v19,
                   (__int64)&v17,
                   (__int64)&v16,
                   (__int64)v20);
  v5 = v15 & 0x3F;
  DdcTraceHelper::TraceHandleCommand(CommandState >= 0, v21[0], v5, v21[2], CommandState);
  switch ( v5 )
  {
    case 2u:
      Command = DdcCommandExecutor::ProcessLocateCommand((struct CommandPrefix *)v21, a1, v16, 0);
      if ( Command < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v8,
          Command,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          147,
          "CHR(DdcCommandExecutor::ProcessLocateCommand(&prefix, pdcHandle, fEnableLocation))");
      break;
    case 1u:
      Command = DdcCommandExecutor::ProcessRingCommand((struct CommandPrefix *)v21, a1);
      if ( Command < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v10,
          Command,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          151,
          "CHR(DdcCommandExecutor::ProcessRingCommand(&prefix, pdcHandle))");
      break;
    case 3u:
      Command = DdcCommandExecutor::ProcessLockCommand(
                  (struct CommandPrefix *)v21,
                  (__int64)a1,
                  (__int64)Block,
                  (__int64)v19,
                  v17,
                  (__int64)v20);
      if ( Command < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v11,
          Command,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          155,
          "CHR(DdcCommandExecutor::ProcessLockCommand(&prefix, pdcHandle, pwszPin, pwszCpn, fRingAfterLock, vCids))");
      break;
    case 4u:
      Command = DdcCommandExecutor::ProcessWipeCommand((struct CommandPrefix *)v21, a1);
      if ( Command < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v12,
          Command,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          159,
          "CHR(DdcCommandExecutor::ProcessWipeCommand(&prefix, pdcHandle))");
      break;
    case 8u:
      Command = DdcCommandExecutor::ProcessStartFamilySafetyCommand((struct CommandPrefix *)v21);
      if ( Command < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v13,
          Command,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          163,
          "CHR(DdcCommandExecutor::ProcessStartFamilySafetyCommand(&prefix))");
      break;
    default:
      Command = -2147418113;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          -2147418113,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          167,
          "CHR(((HRESULT)0x8000FFFFL))");
      break;
  }
  if ( Block )
    operator delete(Block);
  if ( v19 )
    operator delete(v19);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v7, DEVICE_DIRECTORY_CLIENT_HANDLE_COMMAND_RESULT, (unsigned int)Command);
  if ( v20[0] )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v20[0], v20[1]);
    std::_Deallocate<16>((_QWORD *)v20[0], (v20[2] - v20[0]) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x180005f5c  mov     [rsp-8+arg_8], rbx
0x180005f61  mov     [rsp-8+arg_10], rdi
0x180005f66  push    rbp
0x180005f67  lea     rbp, [rsp-57h]
0x180005f6c  sub     rsp, 0B0h
0x180005f73  mov     rax, cs:__security_cookie
0x180005f7a  xor     rax, rsp
0x180005f7d  mov     [rbp+57h+var_10], rax
0x180005f81  mov     rdi, rcx
0x180005f84  xorps   xmm0, xmm0
0x180005f87  xor     eax, eax
0x180005f89  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x180005f8d  mov     [rbp+57h+var_28], eax
0x180005f90  mov     [rbp+57h+var_70], eax
0x180005f93  mov     [rbp+57h+Block], rax
0x180005f97  mov     [rbp+57h+var_58], rax
0x180005f9b  lea     rcx, [rbp+57h+var_50]
0x180005f9f  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x180005fa4  nop
0x180005fa5  mov     [rbp+57h+var_68], 0
0x180005fac  mov     [rbp+57h+var_6C], 0
0x180005fb3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180005fba  jz      short loc_180005FD7
0x180005fbc  lea     rax, [rbp+57h+var_20]
0x180005fc0  mov     qword ptr [rsp+0B0h+var_90], rax
0x180005fc5  mov     r9d, 1
0x180005fcb  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_COMMAND
0x180005fd2  call    McGenEventWrite_EventWriteTransfer
0x180005fd7  lea     rax, [rbp+57h+var_50]
0x180005fdb  mov     [rsp+0B0h+var_80], rax
0x180005fe0  lea     rax, [rbp+57h+var_6C]
0x180005fe4  mov     [rsp+0B0h+var_88], rax
0x180005fe9  lea     rax, [rbp+57h+var_68]
0x180005fed  mov     qword ptr [rsp+0B0h+var_90], rax
0x180005ff2  lea     r9, [rbp+57h+var_58]
0x180005ff6  lea     r8, [rbp+57h+Block]
0x180005ffa  lea     rdx, [rbp+57h+var_70]
0x180005ffe  lea     rcx, [rbp+57h+var_38]
0x180006002  call    ?QueryCommandState@DdcCommandController@@CAJPEAUCommandPrefix@@PEAUMdmCommandAndAcknowledgement@@PEAPEAG2PEAH3PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DdcCommandController::QueryCommandState(CommandPrefix *,MdmCommandAndAcknowledgement *,ushort * *,ushort * *,int *,int *,std::vector<std::wstring> *)
0x180006007  mov     ebx, [rbp+57h+var_70]
0x18000600a  and     ebx, 3Fh
0x18000600d  mov     ecx, eax
0x18000600f  not     ecx
0x180006011  shr     ecx, 1Fh; int
0x180006014  mov     [rsp+0B0h+var_90], eax; int
0x180006018  mov     r9d, [rbp+57h+var_38+8]; unsigned int
0x18000601c  mov     r8d, ebx; unsigned int
0x18000601f  mov     edx, [rbp+57h+var_38]; unsigned int
0x180006022  call    ?TraceHandleCommand@DdcTraceHelper@@SAXHKKKJ@Z; DdcTraceHelper::TraceHandleCommand(int,ulong,ulong,ulong,long)
0x180006027  cmp     ebx, 2
0x18000602a  jnz     short loc_18000606F
0x18000602c  xor     r9d, r9d; unsigned int
0x18000602f  mov     r8d, [rbp+57h+var_6C]; int
0x180006033  mov     rdx, rdi; void *
0x180006036  lea     rcx, [rbp+57h+var_38]; struct CommandPrefix *
0x18000603a  call    ?ProcessLocateCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAXHK@Z; DdcCommandExecutor::ProcessLocateCommand(CommandPrefix *,void *,int,ulong)
0x18000603f  mov     ebx, eax
0x180006041  test    eax, eax
0x180006043  jns     loc_1800061A7
0x180006049  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006050  jz      loc_1800061A7
0x180006056  lea     rax, aChrDdccommande_0; "CHR(DdcCommandExecutor::ProcessLocateCo"...
0x18000605d  mov     [rsp+0B0h+var_88], rax
0x180006062  mov     [rsp+0B0h+var_90], 193h
0x18000606a  jmp     loc_180006198
0x18000606f  cmp     ebx, 1
0x180006072  jnz     short loc_1800060B0
0x180006074  mov     rdx, rdi; void *
0x180006077  lea     rcx, [rbp+57h+var_38]; struct CommandPrefix *
0x18000607b  call    ?ProcessRingCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAX@Z; DdcCommandExecutor::ProcessRingCommand(CommandPrefix *,void *)
0x180006080  mov     ebx, eax
0x180006082  test    eax, eax
0x180006084  jns     loc_1800061A7
0x18000608a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006091  jz      loc_1800061A7
0x180006097  lea     rax, aChrDdccommande_5; "CHR(DdcCommandExecutor::ProcessRingComm"...
0x18000609e  mov     [rsp+0B0h+var_88], rax
0x1800060a3  mov     [rsp+0B0h+var_90], 197h
0x1800060ab  jmp     loc_180006198
0x1800060b0  cmp     ebx, 3
0x1800060b3  jnz     short loc_180006109
0x1800060b5  lea     rax, [rbp+57h+var_50]
0x1800060b9  mov     [rsp+0B0h+var_88], rax; __int64
0x1800060be  mov     eax, [rbp+57h+var_68]
0x1800060c1  mov     [rsp+0B0h+var_90], eax; int
0x1800060c5  mov     r9, [rbp+57h+var_58]
0x1800060c9  mov     r8, [rbp+57h+Block]
0x1800060cd  mov     rdx, rdi
0x1800060d0  lea     rcx, [rbp+57h+var_38]; struct CommandPrefix *
0x1800060d4  call    ?ProcessLockCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAXPEAG2HAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DdcCommandExecutor::ProcessLockCommand(CommandPrefix *,void *,ushort *,ushort *,int,std::vector<std::wstring> &)
0x1800060d9  mov     ebx, eax
0x1800060db  test    eax, eax
0x1800060dd  jns     loc_1800061A7
0x1800060e3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800060ea  jz      loc_1800061A7
0x1800060f0  lea     rax, aChrDdccommande; "CHR(DdcCommandExecutor::ProcessLockComm"...
0x1800060f7  mov     [rsp+0B0h+var_88], rax
0x1800060fc  mov     [rsp+0B0h+var_90], 19Bh
0x180006104  jmp     loc_180006198
0x180006109  cmp     ebx, 4
0x18000610c  jnz     short loc_180006143
0x18000610e  mov     rdx, rdi; void *
0x180006111  lea     rcx, [rbp+57h+var_38]; struct CommandPrefix *
0x180006115  call    ?ProcessWipeCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAX@Z; DdcCommandExecutor::ProcessWipeCommand(CommandPrefix *,void *)
0x18000611a  mov     ebx, eax
0x18000611c  test    eax, eax
0x18000611e  jns     loc_1800061A7
0x180006124  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000612b  jz      short loc_1800061A7
0x18000612d  lea     rax, aChrDdccommande_1; "CHR(DdcCommandExecutor::ProcessWipeComm"...
0x180006134  mov     [rsp+0B0h+var_88], rax
0x180006139  mov     [rsp+0B0h+var_90], 19Fh
0x180006141  jmp     short loc_180006198
0x180006143  cmp     ebx, 8
0x180006146  jnz     short loc_180006176
0x180006148  lea     rcx, [rbp+57h+var_38]; struct CommandPrefix *
0x18000614c  call    ?ProcessStartFamilySafetyCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@@Z; DdcCommandExecutor::ProcessStartFamilySafetyCommand(CommandPrefix *)
0x180006151  mov     ebx, eax
0x180006153  test    eax, eax
0x180006155  jns     short loc_1800061A7
0x180006157  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000615e  jz      short loc_1800061A7
0x180006160  lea     rax, aChrDdccommande_3; "CHR(DdcCommandExecutor::ProcessStartFam"...
0x180006167  mov     [rsp+0B0h+var_88], rax
0x18000616c  mov     [rsp+0B0h+var_90], 1A3h
0x180006174  jmp     short loc_180006198
0x180006176  mov     ebx, 8000FFFFh
0x18000617b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006182  jz      short loc_1800061A7
0x180006184  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8000FFFFL))"
0x18000618b  mov     [rsp+0B0h+var_88], rax
0x180006190  mov     [rsp+0B0h+var_90], 1A7h
0x180006198  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000619f  mov     r8d, ebx
0x1800061a2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800061a7  cmp     [rbp+57h+Block], 0
0x1800061ac  jz      short loc_1800061B7
0x1800061ae  mov     rcx, [rbp+57h+Block]; Block
0x1800061b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800061b7  cmp     [rbp+57h+var_58], 0
0x1800061bc  jz      short loc_1800061C7
0x1800061be  mov     rcx, [rbp+57h+var_58]; Block
0x1800061c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800061c7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x1800061ce  jz      short loc_1800061E0
0x1800061d0  mov     r8d, ebx
0x1800061d3  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_COMMAND_RESULT
0x1800061da  call    McTemplateU0q_EventWriteTransfer
0x1800061df  nop
0x1800061e0  mov     rcx, [rbp+57h+var_50]
0x1800061e4  test    rcx, rcx
0x1800061e7  jz      short loc_180006206
0x1800061e9  mov     rdx, [rbp+57h+var_48]
0x1800061ed  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800061f2  mov     rcx, [rbp+57h+var_50]
0x1800061f6  mov     rdx, [rbp+57h+var_40]
0x1800061fa  sub     rdx, rcx
0x1800061fd  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180006201  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180006206  mov     eax, ebx
0x180006208  mov     rcx, [rbp+57h+var_10]
0x18000620c  xor     rcx, rsp; StackCookie
0x18000620f  call    __security_check_cookie
0x180006214  lea     r11, [rsp+0B0h+var_s0]
0x18000621c  mov     rbx, [r11+18h]
0x180006220  mov     rdi, [r11+20h]
0x180006224  mov     rsp, r11
0x180006227  pop     rbp
0x180006228  retn
```
