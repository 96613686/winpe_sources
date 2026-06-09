# DdcCommandController::UserSessionCommand(void)

- ea: `0x180007838`
- end: `0x1800079bd`
- name: `?UserSessionCommand@DdcCommandController@@SAJXZ`
- size: `389`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
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
- `0x180005a64`
- `0x180005a9c`
- `0x1800073b8`
- `0x180007838`
- `0x18001b530`

## string_xrefs

- `0x180007931`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x1800078ea`: `CHR(QueryCommandState(&prefix, &cmdType, &pwszPin, &pwszCpn, &fRingAfterLock, &fEnableLocation, &vCids))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 DdcCommandController::UserSessionCommand(void)
{
  __int64 v0; // rcx
  __int64 v1; // r8
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // ebx
  const unsigned __int16 *v5; // r8
  int v6; // edx
  int v7; // ecx
  void *v8; // rcx
  int v10; // [rsp+40h] [rbp-19h] BYREF
  int v11; // [rsp+44h] [rbp-15h] BYREF
  int v12; // [rsp+48h] [rbp-11h] BYREF
  void *Block; // [rsp+50h] [rbp-9h] BYREF
  void *v14; // [rsp+58h] [rbp-1h] BYREF
  _QWORD *v15[3]; // [rsp+60h] [rbp+7h] BYREF
  __int128 v16; // [rsp+78h] [rbp+1Fh] BYREF
  int v17; // [rsp+88h] [rbp+2Fh]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+90h] [rbp+37h] BYREF

  v16 = 0;
  v17 = 0;
  v10 = 0;
  Block = 0;
  v14 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(v15);
  v12 = 0;
  v11 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      v0,
      (const EVENT_DESCRIPTOR *)DEVICE_DIRECTORY_CLIENT_USER_SESSION_COMMAND,
      v1,
      1u,
      &v18);
  v4 = DdcCommandController::QueryCommandState((__int64)&v16, &v10, &Block, &v14, (__int64)&v12, &v11, (__int64)v15);
  if ( v4 >= 0 )
  {
    if ( (v10 & 0x3F) == 2 )
    {
      v4 = DdcToastHelper::PostToastNotification(v3, v2, v5);
      if ( v4 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v4,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
          205,
          "CHR(DdcToastHelper::PostToastNotification( 603, 604, 0, 0))");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v4,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      197,
      "CHR(QueryCommandState(&prefix, &cmdType, &pwszPin, &pwszCpn, &fRingAfterLock, &fEnableLocation, &vCids))");
  }
  if ( Block )
    operator delete(Block);
  v8 = v14;
  if ( v14 )
    operator delete(v14);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v8, DEVICE_DIRECTORY_CLIENT_USER_SESSION_COMMAND_RESULT, (unsigned int)v4);
  if ( v15[0] )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v15[0], v15[1]);
    std::_Deallocate<16>(v15[0], ((char *)v15[2] - (char *)v15[0]) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007838  mov     [rsp-8+arg_0], rbx
0x18000783d  push    rbp
0x18000783e  lea     rbp, [rsp-57h]
0x180007843  sub     rsp, 0B0h
0x18000784a  mov     rax, cs:__security_cookie
0x180007851  xor     rax, rsp
0x180007854  mov     [rbp+57h+var_10], rax
0x180007858  xorps   xmm0, xmm0
0x18000785b  xor     eax, eax
0x18000785d  movups  [rbp+57h+var_38], xmm0
0x180007861  mov     [rbp+57h+var_28], eax
0x180007864  mov     [rbp+57h+var_70], eax
0x180007867  mov     [rbp+57h+Block], rax
0x18000786b  mov     [rbp+57h+var_58], rax
0x18000786f  lea     rcx, [rbp+57h+var_50]
0x180007873  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x180007878  nop
0x180007879  mov     [rbp+57h+var_68], 0
0x180007880  mov     [rbp+57h+var_6C], 0
0x180007887  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000788e  jz      short loc_1800078AB
0x180007890  lea     rax, [rbp+57h+var_20]
0x180007894  mov     [rsp+0B0h+var_90], rax
0x180007899  mov     r9d, 1
0x18000789f  lea     rdx, DEVICE_DIRECTORY_CLIENT_USER_SESSION_COMMAND
0x1800078a6  call    McGenEventWrite_EventWriteTransfer
0x1800078ab  lea     rax, [rbp+57h+var_50]
0x1800078af  mov     [rsp+0B0h+var_80], rax
0x1800078b4  lea     rax, [rbp+57h+var_6C]
0x1800078b8  mov     [rsp+0B0h+var_88], rax
0x1800078bd  lea     rax, [rbp+57h+var_68]
0x1800078c1  mov     [rsp+0B0h+var_90], rax
0x1800078c6  lea     r9, [rbp+57h+var_58]
0x1800078ca  lea     r8, [rbp+57h+Block]
0x1800078ce  lea     rdx, [rbp+57h+var_70]
0x1800078d2  lea     rcx, [rbp+57h+var_38]
0x1800078d6  call    ?QueryCommandState@DdcCommandController@@CAJPEAUCommandPrefix@@PEAUMdmCommandAndAcknowledgement@@PEAPEAG2PEAH3PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DdcCommandController::QueryCommandState(CommandPrefix *,MdmCommandAndAcknowledgement *,ushort * *,ushort * *,int *,int *,std::vector<std::wstring> *)
0x1800078db  mov     ebx, eax
0x1800078dd  test    eax, eax
0x1800078df  jns     short loc_180007900
0x1800078e1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800078e8  jz      short loc_180007940
0x1800078ea  lea     rax, aChrQuerycomman; "CHR(QueryCommandState(&prefix, &cmdType"...
0x1800078f1  mov     [rsp+0B0h+var_88], rax
0x1800078f6  mov     dword ptr [rsp+0B0h+var_90], 2C5h
0x1800078fe  jmp     short loc_180007931
0x180007900  mov     eax, [rbp+57h+var_70]
0x180007903  and     al, 3Fh
0x180007905  cmp     al, 2
0x180007907  jnz     short loc_180007940
0x180007909  call    ?PostToastNotification@DdcToastHelper@@SAJIIPEBGK@Z; DdcToastHelper::PostToastNotification(uint,uint,ushort const *,ulong)
0x18000790e  mov     ebx, eax
0x180007910  test    eax, eax
0x180007912  jns     short loc_180007940
0x180007914  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000791b  jz      short loc_180007940
0x18000791d  lea     rax, aChrDdctoasthel; "CHR(DdcToastHelper::PostToastNotificati"...
0x180007924  mov     [rsp+0B0h+var_88], rax
0x180007929  mov     dword ptr [rsp+0B0h+var_90], 2CDh
0x180007931  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180007938  mov     r8d, ebx
0x18000793b  call    McTemplateU0dsqs_EventWriteTransfer
0x180007940  mov     rcx, [rbp+57h+Block]; Block
0x180007944  test    rcx, rcx
0x180007947  jz      short loc_18000794E
0x180007949  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000794e  mov     rcx, [rbp+57h+var_58]; Block
0x180007952  test    rcx, rcx
0x180007955  jz      short loc_18000795C
0x180007957  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000795c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180007963  jz      short loc_180007975
0x180007965  mov     r8d, ebx
0x180007968  lea     rdx, DEVICE_DIRECTORY_CLIENT_USER_SESSION_COMMAND_RESULT
0x18000796f  call    McTemplateU0q_EventWriteTransfer
0x180007974  nop
0x180007975  cmp     [rbp+57h+var_50], 0
0x18000797a  jz      short loc_18000799E
0x18000797c  mov     rdx, [rbp+57h+var_48]
0x180007980  mov     rcx, [rbp+57h+var_50]
0x180007984  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180007989  mov     rdx, [rbp+57h+var_40]
0x18000798d  sub     rdx, [rbp+57h+var_50]
0x180007991  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180007995  mov     rcx, [rbp+57h+var_50]
0x180007999  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000799e  mov     eax, ebx
0x1800079a0  mov     rcx, [rbp+57h+var_10]
0x1800079a4  xor     rcx, rsp; StackCookie
0x1800079a7  call    __security_check_cookie
0x1800079ac  mov     rbx, [rsp+0B0h+arg_0]
0x1800079b4  add     rsp, 0B0h
0x1800079bb  pop     rbp
0x1800079bc  retn
```
