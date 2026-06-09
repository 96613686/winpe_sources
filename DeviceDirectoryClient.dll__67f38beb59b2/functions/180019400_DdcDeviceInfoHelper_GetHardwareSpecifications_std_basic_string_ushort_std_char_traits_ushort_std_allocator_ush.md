# DdcDeviceInfoHelper::GetHardwareSpecifications(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180019400`
- end: `0x180019641`
- name: `?GetHardwareSpecifications@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAK0000@Z`
- size: `577`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180015fbc`

## callees

- `0x1800024c0`
- `0x180004d5c`
- `0x180004db8`
- `0x180004e10`
- `0x1800050b8`
- `0x180014410`
- `0x180019400`
- `0x180019e64`
- `0x18001a418`
- `0x18001a514`

## string_xrefs

- `0x180019460`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001944c`: `CPR(pwstrRandomAccessMemory)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcDeviceInfoHelper::GetHardwareSpecifications(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v10; // r8d
  int SystemMemory; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // ecx
  __int64 v16; // [rsp+0h] [rbp-98h] BYREF
  int v17; // [rsp+20h] [rbp-78h]
  const char *v18; // [rsp+28h] [rbp-70h]
  unsigned __int64 v19; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v20[32]; // [rsp+38h] [rbp-60h] BYREF

  if ( a1 )
  {
    if ( !a3 )
    {
      SystemMemory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          201,
          "CPR(pwstrProcessorName)");
      return (unsigned int)SystemMemory;
    }
    if ( !a4 )
    {
      SystemMemory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          202,
          "CPR(pwstrProcessorSpeed)");
      return (unsigned int)SystemMemory;
    }
    if ( !a5 )
    {
      SystemMemory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          203,
          "CPR(pwstrSystemType)");
      return (unsigned int)SystemMemory;
    }
    if ( !a6 )
    {
      SystemMemory = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          204,
          "CPR(pwstrDeviceAge)");
      return (unsigned int)SystemMemory;
    }
    v19 = 0;
    SystemMemory = GetSystemMemory(&v19);
    if ( SystemMemory >= 0 )
    {
      if ( !v19 )
        return (unsigned int)SystemMemory;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        std::_Integral_to_string<unsigned short,unsigned __int64>(v20, v19);
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        std::wstring::assign(a1, v12, v13);
        std::wstring::_Tidy_deallocate((__int64)v20);
        v14 = a5;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          LODWORD(v19) = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v14,
              (unsigned int)&v16,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              220,
              "CHR(((HRESULT)0x8007000EL))");
          SystemMemory = v19;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180019620);
          return (unsigned int)SystemMemory;
        }
      }
      SystemMemory = ((__int64 (*)(void))DdcDeviceInfoHelper::GetSystemType)();
      if ( SystemMemory >= 0 )
      {
        SystemMemory = DdcDeviceInfoHelper::GetProcessorInformation(a2, a3, a4);
        if ( SystemMemory >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          return (unsigned int)SystemMemory;
        v18 = "CHR(GetProcessorInformation(pdwNumProcessors, pwstrProcessorName, pwstrProcessorSpeed))";
        v17 = 1504;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          return (unsigned int)SystemMemory;
        v18 = "CHR(GetSystemType(pwstrSystemType))";
        v17 = 1503;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return (unsigned int)SystemMemory;
      v18 = "CHR(GetSystemMemory(&ullRam))";
      v17 = 1487;
    }
    v10 = SystemMemory;
    goto LABEL_4;
  }
  v10 = -2147024809;
  SystemMemory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v18 = "CPR(pwstrRandomAccessMemory)";
    v17 = 1480;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      (_DWORD)a2,
      v10,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v17,
      v18);
  }
  return (unsigned int)SystemMemory;
}

```

## disassembly

```asm
0x180019400  push    rbx
0x180019402  push    rsi
0x180019403  push    rdi
0x180019404  push    r12
0x180019406  push    r14
0x180019408  push    r15
0x18001940a  sub     rsp, 68h
0x18001940e  mov     rax, cs:__security_cookie
0x180019415  xor     rax, rsp
0x180019418  mov     [rsp+98h+var_40], rax
0x18001941d  mov     r14, r9
0x180019420  mov     rsi, r8
0x180019423  mov     r12, rdx
0x180019426  mov     r15, rcx
0x180019429  mov     rdi, [rsp+98h+arg_20]
0x180019431  test    rcx, rcx
0x180019434  jnz     short loc_180019471
0x180019436  mov     r8d, 80070057h
0x18001943c  mov     ebx, r8d
0x18001943f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019446  jz      loc_180019624
0x18001944c  lea     rax, aCprPwstrrandom; "CPR(pwstrRandomAccessMemory)"
0x180019453  mov     [rsp+98h+var_70], rax
0x180019458  mov     [rsp+98h+var_78], 5C8h
0x180019460  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019467  call    McTemplateU0dsqs_EventWriteTransfer
0x18001946c  jmp     loc_180019624
0x180019471  test    rsi, rsi
0x180019474  jnz     short loc_1800194A2
0x180019476  mov     r8d, 80070057h
0x18001947c  mov     ebx, r8d
0x18001947f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019486  jz      loc_180019624
0x18001948c  lea     rax, aCprPwstrproces_0; "CPR(pwstrProcessorName)"
0x180019493  mov     [rsp+98h+var_70], rax
0x180019498  mov     [rsp+98h+var_78], 5C9h
0x1800194a0  jmp     short loc_180019460
0x1800194a2  test    r14, r14
0x1800194a5  jnz     short loc_1800194D3
0x1800194a7  mov     r8d, 80070057h
0x1800194ad  mov     ebx, r8d
0x1800194b0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800194b7  jz      loc_180019624
0x1800194bd  lea     rax, aCprPwstrproces; "CPR(pwstrProcessorSpeed)"
0x1800194c4  mov     [rsp+98h+var_70], rax
0x1800194c9  mov     [rsp+98h+var_78], 5CAh
0x1800194d1  jmp     short loc_180019460
0x1800194d3  test    rdi, rdi
0x1800194d6  jnz     short loc_180019507
0x1800194d8  mov     r8d, 80070057h
0x1800194de  mov     ebx, r8d
0x1800194e1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800194e8  jz      loc_180019624
0x1800194ee  lea     rax, aCprPwstrsystem; "CPR(pwstrSystemType)"
0x1800194f5  mov     [rsp+98h+var_70], rax
0x1800194fa  mov     [rsp+98h+var_78], 5CBh
0x180019502  jmp     loc_180019460
0x180019507  cmp     [rsp+98h+arg_28], 0
0x180019510  jnz     short loc_180019541
0x180019512  mov     r8d, 80070057h
0x180019518  mov     ebx, r8d
0x18001951b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019522  jz      loc_180019624
0x180019528  lea     rax, aCprPwstrdevice; "CPR(pwstrDeviceAge)"
0x18001952f  mov     [rsp+98h+var_70], rax
0x180019534  mov     [rsp+98h+var_78], 5CCh
0x18001953c  jmp     loc_180019460
0x180019541  mov     [rsp+98h+var_68], 0
0x18001954a  lea     rcx, [rsp+98h+var_68]; unsigned __int64 *
0x18001954f  call    ?GetSystemMemory@@YAJPEA_K@Z; GetSystemMemory(unsigned __int64 *)
0x180019554  mov     ebx, eax
0x180019556  test    eax, eax
0x180019558  jns     short loc_180019583
0x18001955a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019561  jz      loc_180019624
0x180019567  lea     rax, aChrGetsystemme; "CHR(GetSystemMemory(&ullRam))"
0x18001956e  mov     [rsp+98h+var_70], rax
0x180019573  mov     [rsp+98h+var_78], 5CFh
0x18001957b  mov     r8d, ebx
0x18001957e  jmp     loc_180019460
0x180019583  mov     rdx, [rsp+98h+var_68]
0x180019588  test    rdx, rdx
0x18001958b  jz      loc_180019624
0x180019591  lea     rcx, [rsp+98h+var_60]
0x180019596  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18001959b  nop
0x18001959c  lea     rcx, [rsp+98h+var_60]
0x1800195a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800195a6  mov     rdx, rax
0x1800195a9  mov     rcx, r15
0x1800195ac  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800195b1  nop
0x1800195b2  lea     rcx, [rsp+98h+var_60]
0x1800195b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800195bc  nop
0x1800195bd  mov     rcx, rdi
0x1800195c0  call    ?GetSystemType@DdcDeviceInfoHelper@@CAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcDeviceInfoHelper::GetSystemType(std::wstring *)
0x1800195c5  mov     ebx, eax
0x1800195c7  test    eax, eax
0x1800195c9  jns     short loc_1800195EA
0x1800195cb  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800195d2  jz      short loc_180019624
0x1800195d4  lea     rax, aChrGetsystemty; "CHR(GetSystemType(pwstrSystemType))"
0x1800195db  mov     [rsp+98h+var_70], rax
0x1800195e0  mov     [rsp+98h+var_78], 5DFh
0x1800195e8  jmp     short loc_18001957B
0x1800195ea  mov     r8, r14
0x1800195ed  mov     rdx, rsi
0x1800195f0  mov     rcx, r12
0x1800195f3  call    ?GetProcessorInformation@DdcDeviceInfoHelper@@CAJPEAKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; DdcDeviceInfoHelper::GetProcessorInformation(ulong *,std::wstring *,std::wstring *)
0x1800195f8  mov     ebx, eax
0x1800195fa  test    eax, eax
0x1800195fc  jns     short loc_180019624
0x1800195fe  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019605  jz      short loc_180019624
0x180019607  lea     rax, aChrGetprocesso; "CHR(GetProcessorInformation(pdwNumProce"...
0x18001960e  mov     [rsp+98h+var_70], rax
0x180019613  mov     [rsp+98h+var_78], 5E0h
0x18001961b  jmp     loc_18001957B
0x180019620  mov     ebx, dword ptr [rsp+98h+var_68]
0x180019624  mov     eax, ebx
0x180019626  mov     rcx, [rsp+98h+var_40]
0x18001962b  xor     rcx, rsp; StackCookie
0x18001962e  call    __security_check_cookie
0x180019633  add     rsp, 68h
0x180019637  pop     r15
0x180019639  pop     r14
0x18001963b  pop     r12
0x18001963d  pop     rdi
0x18001963e  pop     rsi
0x18001963f  pop     rbx
0x180019640  retn
```
