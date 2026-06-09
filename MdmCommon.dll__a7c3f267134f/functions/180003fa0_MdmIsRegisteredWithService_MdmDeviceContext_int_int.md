# MdmIsRegisteredWithService(MdmDeviceContext,int *,int *)

- ea: `0x180003fa0`
- end: `0x1800040c8`
- name: `?MdmIsRegisteredWithService@@YAJW4MdmDeviceContext@@PEAH1@Z`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001520`
- `0x180003fa0`
- `0x180006560`
- `0x1800065c0`
- `0x1800133e8`

## string_xrefs

- `0x18000401e`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x18000404d`: `CHR(MdmSettings::HasRegisteredWithService(eDeviceType, &fRegistered, &fCurrentVersionRegistered))`

## pseudocode

```c
__int64 __fastcall MdmIsRegisteredWithService(__int64 a1, _DWORD *a2, int *a3)
{
  int v5; // ebx
  int HasRegisteredWithService; // ebx
  int v7; // edx
  int v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-30h] BYREF
  int *v12; // [rsp+50h] [rbp-20h]
  __int64 v13; // [rsp+58h] [rbp-18h]

  v10 = 0;
  v5 = a1;
  v9 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_IS_REGISTERED_WITH_SERVICE,
      (__int64)a3,
      1u,
      &v11);
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
    McGenEventWrite_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_IS_REGISTERED_WITH_SERVICE_RESULT,
      (__int64)a3,
      2u,
      &v11);
  }
  return (unsigned int)HasRegisteredWithService;
}

```

## disassembly

```asm
0x180003fa0  mov     [rsp-18h+arg_18], rbx
0x180003fa5  push    rbp
0x180003fa6  push    rsi
0x180003fa7  push    rdi
0x180003fa8  mov     rbp, rsp
0x180003fab  sub     rsp, 70h
0x180003faf  mov     rax, cs:__security_cookie
0x180003fb6  xor     rax, rsp
0x180003fb9  mov     [rbp+var_10], rax
0x180003fbd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003fc4  mov     rdi, r8
0x180003fc7  mov     rsi, rdx
0x180003fca  mov     [rbp+var_38], 0
0x180003fd1  mov     ebx, ecx
0x180003fd3  mov     [rbp+var_40], 0
0x180003fda  jz      short loc_180003FF7
0x180003fdc  lea     rax, [rbp+var_30]
0x180003fe0  mov     r9d, 1
0x180003fe6  lea     rdx, MDMCOMMON_IS_REGISTERED_WITH_SERVICE
0x180003fed  mov     [rsp+70h+var_50], rax
0x180003ff2  call    McGenEventWrite_EventWriteTransfer
0x180003ff7  test    rsi, rsi
0x180003ffa  jnz     short loc_18000402F
0x180003ffc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180004003  mov     ebx, 80070057h
0x180004008  jz      short loc_180004072
0x18000400a  lea     rax, aCprPfregistere; "CPR(pfRegistered)"
0x180004011  mov     [rsp+70h+var_48], rax
0x180004016  mov     dword ptr [rsp+70h+var_50], 242h
0x18000401e  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180004025  mov     r8d, ebx
0x180004028  call    McTemplateU0dsqs_EventWriteTransfer
0x18000402d  jmp     short loc_180004072
0x18000402f  lea     r8, [rbp+var_40]
0x180004033  mov     ecx, ebx
0x180004035  lea     rdx, [rbp+var_38]
0x180004039  call    ?HasRegisteredWithService@MdmSettings@@SAJW4MdmDeviceContext@@PEAH1@Z; MdmSettings::HasRegisteredWithService(MdmDeviceContext,int *,int *)
0x18000403e  mov     ebx, eax
0x180004040  test    eax, eax
0x180004042  jns     short loc_180004063
0x180004044  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000404b  jz      short loc_180004072
0x18000404d  lea     rax, aChrMdmsettings_17; "CHR(MdmSettings::HasRegisteredWithServi"...
0x180004054  mov     [rsp+70h+var_48], rax
0x180004059  mov     dword ptr [rsp+70h+var_50], 244h
0x180004061  jmp     short loc_18000401E
0x180004063  mov     eax, [rbp+var_38]
0x180004066  mov     [rsi], eax
0x180004068  test    rdi, rdi
0x18000406b  jz      short loc_180004072
0x18000406d  mov     eax, [rbp+var_40]
0x180004070  mov     [rdi], eax
0x180004072  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180004079  jz      short loc_1800040A9
0x18000407b  lea     rax, [rbp+var_40]
0x18000407f  mov     [rbp+var_40], ebx
0x180004082  mov     [rbp+var_20], rax
0x180004086  lea     rdx, MDMCOMMON_IS_REGISTERED_WITH_SERVICE_RESULT
0x18000408d  lea     rax, [rbp+var_30]
0x180004091  mov     [rbp+var_18], 4
0x180004099  mov     r9d, 2
0x18000409f  mov     [rsp+70h+var_50], rax
0x1800040a4  call    McGenEventWrite_EventWriteTransfer
0x1800040a9  mov     eax, ebx
0x1800040ab  mov     rcx, [rbp+var_10]
0x1800040af  xor     rcx, rsp; StackCookie
0x1800040b2  call    __security_check_cookie
0x1800040b7  mov     rbx, [rsp+70h+arg_18]
0x1800040bf  add     rsp, 70h
0x1800040c3  pop     rdi
0x1800040c4  pop     rsi
0x1800040c5  pop     rbp
0x1800040c6  retn
```
