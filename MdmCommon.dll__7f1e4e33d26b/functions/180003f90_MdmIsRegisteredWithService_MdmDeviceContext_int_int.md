# MdmIsRegisteredWithService(MdmDeviceContext,int *,int *)

- ea: `0x180003f90`
- end: `0x1800040b7`
- name: `?MdmIsRegisteredWithService@@YAJW4MdmDeviceContext@@PEAH1@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, _DWORD *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180003f90`
- `0x1800064f0`
- `0x180006548`
- `0x180013004`

## string_xrefs

- `0x18000400e`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x18000403d`: `CHR(MdmSettings::HasRegisteredWithService(eDeviceType, &fRegistered, &fCurrentVersionRegistered))`

## pseudocode

```c
__int64 __fastcall MdmIsRegisteredWithService(__int64 a1, _DWORD *a2, int *a3)
{
  int v5; // ebx
  int HasRegisteredWithService; // ebx
  int v7; // edx
  int v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+40h] [rbp-30h] BYREF
  int *v12; // [rsp+50h] [rbp-20h]
  __int64 v13; // [rsp+58h] [rbp-18h]

  v10 = 0;
  v5 = a1;
  v9 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_IS_REGISTERED_WITH_SERVICE, a3, 1, v11);
  if ( a2 )
  {
    HasRegisteredWithService = MdmSettings::HasRegisteredWithService(v5, &v10, &v9);
    if ( HasRegisteredWithService >= 0 )
    {
      *a2 = v10;
      if ( a3 )
        *a3 = v9;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        v7,
        HasRegisteredWithService,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        68,
        "CHR(MdmSettings::HasRegisteredWithService(eDeviceType, &fRegistered, &fCurrentVersionRegistered))");
    }
  }
  else
  {
    HasRegisteredWithService = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        66,
        "CPR(pfRegistered)");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v9 = HasRegisteredWithService;
    v12 = &v9;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_IS_REGISTERED_WITH_SERVICE_RESULT, a3, 2, v11);
  }
  return (unsigned int)HasRegisteredWithService;
}

```

## disassembly

```asm
0x180003f90  mov     [rsp-18h+arg_18], rbx
0x180003f95  push    rbp
0x180003f96  push    rsi
0x180003f97  push    rdi
0x180003f98  mov     rbp, rsp
0x180003f9b  sub     rsp, 70h
0x180003f9f  mov     rax, cs:__security_cookie
0x180003fa6  xor     rax, rsp
0x180003fa9  mov     [rbp+var_10], rax
0x180003fad  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003fb4  mov     rdi, r8
0x180003fb7  mov     rsi, rdx
0x180003fba  mov     [rbp+var_38], 0
0x180003fc1  mov     ebx, ecx
0x180003fc3  mov     [rbp+var_40], 0
0x180003fca  jz      short loc_180003FE7
0x180003fcc  lea     rax, [rbp+var_30]
0x180003fd0  mov     r9d, 1
0x180003fd6  lea     rdx, MDMCOMMON_IS_REGISTERED_WITH_SERVICE
0x180003fdd  mov     [rsp+70h+var_50], rax
0x180003fe2  call    McGenEventWrite_EventWriteTransfer
0x180003fe7  test    rsi, rsi
0x180003fea  jnz     short loc_18000401F
0x180003fec  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180003ff3  mov     ebx, 80070057h
0x180003ff8  jz      short loc_180004062
0x180003ffa  lea     rax, aCprPfregistere; "CPR(pfRegistered)"
0x180004001  mov     [rsp+70h+var_48], rax
0x180004006  mov     dword ptr [rsp+70h+var_50], 242h
0x18000400e  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004015  mov     r8d, ebx
0x180004018  call    McTemplateU0dsqs_EventWriteTransfer
0x18000401d  jmp     short loc_180004062
0x18000401f  lea     r8, [rbp+var_40]
0x180004023  mov     ecx, ebx
0x180004025  lea     rdx, [rbp+var_38]
0x180004029  call    ?HasRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@PEAH1@Z; MdmSettings::HasRegisteredWithService(MdmDeviceContext,int *,int *)
0x18000402e  mov     ebx, eax
0x180004030  test    eax, eax
0x180004032  jns     short loc_180004053
0x180004034  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000403b  jz      short loc_180004062
0x18000403d  lea     rax, aChrMdmsettings_17; "CHR(MdmSettings::HasRegisteredWithServi"...
0x180004044  mov     [rsp+70h+var_48], rax
0x180004049  mov     dword ptr [rsp+70h+var_50], 244h
0x180004051  jmp     short loc_18000400E
0x180004053  mov     eax, [rbp+var_38]
0x180004056  mov     [rsi], eax
0x180004058  test    rdi, rdi
0x18000405b  jz      short loc_180004062
0x18000405d  mov     eax, [rbp+var_40]
0x180004060  mov     [rdi], eax
0x180004062  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004069  jz      short loc_180004099
0x18000406b  lea     rax, [rbp+var_40]
0x18000406f  mov     [rbp+var_40], ebx
0x180004072  mov     [rbp+var_20], rax
0x180004076  lea     rdx, MDMCOMMON_IS_REGISTERED_WITH_SERVICE_RESULT
0x18000407d  lea     rax, [rbp+var_30]
0x180004081  mov     [rbp+var_18], 4
0x180004089  mov     r9d, 2
0x18000408f  mov     [rsp+70h+var_50], rax
0x180004094  call    McGenEventWrite_EventWriteTransfer
0x180004099  mov     eax, ebx
0x18000409b  mov     rcx, [rbp+var_10]
0x18000409f  xor     rcx, rsp; StackCookie
0x1800040a2  call    __security_check_cookie
0x1800040a7  mov     rbx, [rsp+70h+arg_18]
0x1800040af  add     rsp, 70h
0x1800040b3  pop     rdi
0x1800040b4  pop     rsi
0x1800040b5  pop     rbp
0x1800040b6  retn
```
