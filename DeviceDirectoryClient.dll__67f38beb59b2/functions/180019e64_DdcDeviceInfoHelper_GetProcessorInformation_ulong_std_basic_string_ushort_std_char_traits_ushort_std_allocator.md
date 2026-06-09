# DdcDeviceInfoHelper::GetProcessorInformation(ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180019e64`
- end: `0x180019f62`
- name: `?GetProcessorInformation@DdcDeviceInfoHelper@@CAJPEAKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `254`
- prototype: `__int64 __fastcall(unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019400`

## callees

- `0x1800024c0`
- `0x180004e10`
- `0x1800050b8`
- `0x180019874`
- `0x180019e64`
- `0x180019f68`
- `0x18001a074`
- `0x180028ad0`

## string_xrefs

- `0x180019ec3`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetProcessorInformation(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edx
  int v6; // ecx
  unsigned int ProcessorSpeed; // ebx
  __int64 v8; // r8
  unsigned int v9; // edx
  int v10; // ecx
  __int64 v11; // r8
  int v12; // ecx
  _BYTE v14[32]; // [rsp+0h] [rbp-1058h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-1028h]
  unsigned __int16 pvData[1024]; // [rsp+40h] [rbp-1018h] BYREF
  unsigned __int16 v17[1024]; // [rsp+840h] [rbp-818h] BYREF

  GetNumProcessorsFromWMI(a1);
  if ( !a2 )
  {
    ProcessorSpeed = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        -2147024809,
        (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        159,
        "CPR(pwstrProcessorName)");
    return ProcessorSpeed;
  }
  if ( !a3 )
  {
    ProcessorSpeed = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        v5,
        -2147024809,
        (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        160,
        "CPR(pwstrProcessorSpeed)");
    return ProcessorSpeed;
  }
  GetProcessorName(pvData, v5);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    std::wstring::assign(a2, (__int64)pvData, v8);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          (unsigned int)v14,
          -2147024882,
          (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          171,
          "CHR(((HRESULT)0x8007000EL))");
      ProcessorSpeed = v15;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180019F3B);
      return ProcessorSpeed;
    }
  }
  ProcessorSpeed = GetProcessorSpeed(v17, v9);
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    std::wstring::assign(a3, (__int64)v17, v11);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          (unsigned int)v14,
          -2147024882,
          (const char *)(unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          183,
          "CHR(((HRESULT)0x8007000EL))");
      ProcessorSpeed = v15;
      __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180019F39);
    }
  }
  return ProcessorSpeed;
}

```

## disassembly

```asm
0x180019e64  mov     [rsp+arg_18], rbx
0x180019e69  push    rdi
0x180019e6a  mov     eax, 1050h
0x180019e6f  call    _alloca_probe
0x180019e74  sub     rsp, rax
0x180019e77  mov     rax, cs:__security_cookie
0x180019e7e  xor     rax, rsp
0x180019e81  mov     [rsp+1058h+var_18], rax
0x180019e89  mov     rdi, r8
0x180019e8c  mov     rbx, rdx
0x180019e8f  call    ?GetNumProcessorsFromWMI@@YAJPEAK@Z; GetNumProcessorsFromWMI(ulong *)
0x180019e94  test    rbx, rbx
0x180019e97  jnz     short loc_180019ED1
0x180019e99  mov     r8d, 80070057h
0x180019e9f  mov     ebx, r8d
0x180019ea2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019ea9  jz      loc_180019F3F
0x180019eaf  lea     rax, aCprPwstrproces_0; "CPR(pwstrProcessorName)"
0x180019eb6  mov     [rsp+1058h+var_1030], rax
0x180019ebb  mov     [rsp+1058h+var_1038], 59Fh
0x180019ec3  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019eca  call    McTemplateU0dsqs_EventWriteTransfer
0x180019ecf  jmp     short loc_180019F3F
0x180019ed1  test    rdi, rdi
0x180019ed4  jnz     short loc_180019EFE
0x180019ed6  mov     r8d, 80070057h
0x180019edc  mov     ebx, r8d
0x180019edf  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019ee6  jz      short loc_180019F3F
0x180019ee8  lea     rax, aCprPwstrproces; "CPR(pwstrProcessorSpeed)"
0x180019eef  mov     [rsp+1058h+var_1030], rax
0x180019ef4  mov     [rsp+1058h+var_1038], 5A0h
0x180019efc  jmp     short loc_180019EC3
0x180019efe  lea     rcx, [rsp+1058h+pvData]; pvData
0x180019f03  call    ?GetProcessorName@@YAJPEAGI@Z; GetProcessorName(ushort *,uint)
0x180019f08  nop
0x180019f09  lea     rdx, [rsp+1058h+pvData]
0x180019f0e  mov     rcx, rbx
0x180019f11  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180019f16  nop
0x180019f17  lea     rcx, [rsp+1058h+var_818]; unsigned __int16 *
0x180019f1f  call    ?GetProcessorSpeed@@YAJPEAGI@Z; GetProcessorSpeed(ushort *,uint)
0x180019f24  mov     ebx, eax
0x180019f26  lea     rdx, [rsp+1058h+var_818]
0x180019f2e  mov     rcx, rdi
0x180019f31  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180019f36  nop
0x180019f37  jmp     short loc_180019F3F
0x180019f39  jmp     short $+2
0x180019f3b  mov     ebx, [rsp+1058h+var_1028]
0x180019f3f  mov     eax, ebx
0x180019f41  mov     rcx, [rsp+1058h+var_18]
0x180019f49  xor     rcx, rsp; StackCookie
0x180019f4c  call    __security_check_cookie
0x180019f51  mov     rbx, [rsp+1058h+arg_18]
0x180019f59  add     rsp, 1050h
0x180019f60  pop     rdi
0x180019f61  retn
```
