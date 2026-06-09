# DdcCommandController::HandleWnsCommand(void)

- ea: `0x1800071d0`
- end: `0x180007348`
- name: `?HandleWnsCommand@DdcCommandController@@SAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x180005554`
- `0x180006230`
- `0x1800071d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007242`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007242`
- `MdmCommon!MdmHandlePushNotification` at `0x18000726d`
- `MdmCommon!MdmHandlePushNotification` at `0x18000726d`

## string_xrefs

- `0x1800072f4`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x1800072e0`: `CHR(HandleCommandData( dwProfileId, dwRequestId, dwTimestamp, pbCommandData, cbCommandData, MdmCommandChannelType_WNS, ftUtc))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcCommandController::HandleWnsCommand(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  void *v8; // rcx
  unsigned int v10; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned int v12; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v13; // [rsp+4Ch] [rbp-34h] BYREF
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v16[16]; // [rsp+60h] [rbp-20h] BYREF

  v11 = 0;
  v10 = 0;
  v13 = 0;
  Block = 0;
  v12 = 0;
  SystemTimeAsFileTime = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, DEVICE_DIRECTORY_CLIENT_HANDLE_WNS_COMMAND, a3, 1, v16);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = MdmHandlePushNotification(
         (struct _WNF_STATE_NAME)0xD83063EA3BD2875LL,
         &v11,
         &v10,
         &v13,
         (unsigned __int8 **)&Block,
         &v12);
  DdcTraceHelper::TraceHandleWnsCommandResult(v11, v10, v3);
  if ( v3 >= 0 )
  {
    v3 = DdcCommandController::HandleCommandData(v11, v10, v13, Block, v12, 1, *(_QWORD *)&SystemTimeAsFileTime);
    if ( v3 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        v3,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        60,
        "CHR(HandleCommandData( dwProfileId, dwRequestId, dwTimestamp, pbCommandData, cbCommandData, MdmCommandChannelType_WNS, ftUtc))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
      51,
      "CHR(hr)");
  }
  v8 = Block;
  if ( Block )
    operator delete(Block);
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v8, DEVICE_DIRECTORY_CLIENT_HANDLE_WNS_COMMAND_RESULT, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800071d0  mov     [rsp-8+arg_0], rbx
0x1800071d5  push    rbp
0x1800071d6  mov     rbp, rsp
0x1800071d9  sub     rsp, 80h
0x1800071e0  mov     rax, cs:__security_cookie
0x1800071e7  xor     rax, rsp
0x1800071ea  mov     [rbp+var_10], rax
0x1800071ee  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x1800071f5  mov     [rbp+var_3C], 0
0x1800071fc  mov     [rbp+var_40], 0
0x180007203  mov     [rbp+var_34], 0
0x18000720a  mov     [rbp+Block], 0
0x180007212  mov     [rbp+var_38], 0
0x180007219  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180007221  jz      short loc_18000723E
0x180007223  lea     rax, [rbp+var_20]
0x180007227  mov     r9d, 1
0x18000722d  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_WNS_COMMAND
0x180007234  mov     [rsp+80h+var_60], rax
0x180007239  call    McGenEventWrite_EventWriteTransfer
0x18000723e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007242  call    cs:__imp_GetSystemTimeAsFileTime
0x180007248  mov     rcx, cs:qword_180042290
0x18000724f  lea     rax, [rbp+var_38]
0x180007253  mov     [rsp+80h+var_58], rax
0x180007258  lea     r9, [rbp+var_34]
0x18000725c  lea     rax, [rbp+Block]
0x180007260  lea     r8, [rbp+var_40]
0x180007264  mov     [rsp+80h+var_60], rax
0x180007269  lea     rdx, [rbp+var_3C]
0x18000726d  call    cs:__imp_?MdmHandlePushNotification@@YAJU_WNF_STATE_NAME@@PEAK11PEAPEAE1@Z; MdmHandlePushNotification(_WNF_STATE_NAME,ulong *,ulong *,ulong *,uchar * *,ulong *)
0x180007273  mov     edx, [rbp+var_40]; unsigned int
0x180007276  mov     r8d, eax; int
0x180007279  mov     ecx, [rbp+var_3C]; unsigned int
0x18000727c  mov     ebx, eax
0x18000727e  call    ?TraceHandleWnsCommandResult@DdcTraceHelper@@SAXKKJ@Z; DdcTraceHelper::TraceHandleWnsCommandResult(ulong,ulong,long)
0x180007283  test    ebx, ebx
0x180007285  jns     short loc_1800072A6
0x180007287  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000728e  jz      short loc_180007303
0x180007290  lea     rax, aChrHr; "CHR(hr)"
0x180007297  mov     [rsp+80h+var_58], rax
0x18000729c  mov     dword ptr [rsp+80h+var_60], 33h ; '3'
0x1800072a4  jmp     short loc_1800072F4
0x1800072a6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800072aa  mov     r9, [rbp+Block]
0x1800072ae  mov     r8d, [rbp+var_34]
0x1800072b2  mov     edx, [rbp+var_40]
0x1800072b5  mov     ecx, [rbp+var_3C]
0x1800072b8  mov     [rsp+80h+var_50], rax
0x1800072bd  mov     eax, [rbp+var_38]
0x1800072c0  mov     dword ptr [rsp+80h+var_58], 1
0x1800072c8  mov     dword ptr [rsp+80h+var_60], eax
0x1800072cc  call    ?HandleCommandData@DdcCommandController@@CAJKKKPEAEKW4MdmCommandChannelType@@U_FILETIME@@@Z; DdcCommandController::HandleCommandData(ulong,ulong,ulong,uchar *,ulong,MdmCommandChannelType,_FILETIME)
0x1800072d1  mov     ebx, eax
0x1800072d3  test    eax, eax
0x1800072d5  jns     short loc_180007303
0x1800072d7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800072de  jz      short loc_180007303
0x1800072e0  lea     rax, aChrHandlecomma_0; "CHR(HandleCommandData( dwProfileId, dwR"...
0x1800072e7  mov     [rsp+80h+var_58], rax
0x1800072ec  mov     dword ptr [rsp+80h+var_60], 3Ch ; '<'
0x1800072f4  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800072fb  mov     r8d, ebx
0x1800072fe  call    McTemplateU0dsqs_EventWriteTransfer
0x180007303  mov     rcx, [rbp+Block]; Block
0x180007307  test    rcx, rcx
0x18000730a  jz      short loc_180007311
0x18000730c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007311  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x180007318  jz      short loc_180007329
0x18000731a  mov     r8d, ebx
0x18000731d  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_WNS_COMMAND_RESULT
0x180007324  call    McTemplateU0q_EventWriteTransfer
0x180007329  mov     eax, ebx
0x18000732b  mov     rcx, [rbp+var_10]
0x18000732f  xor     rcx, rsp; StackCookie
0x180007332  call    __security_check_cookie
0x180007337  mov     rbx, [rsp+80h+arg_0]
0x18000733f  add     rsp, 80h
0x180007346  pop     rbp
0x180007347  retn
```
