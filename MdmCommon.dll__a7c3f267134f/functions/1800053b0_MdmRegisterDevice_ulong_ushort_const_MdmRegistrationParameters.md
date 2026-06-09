# MdmRegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)

- ea: `0x1800053b0`
- end: `0x18000548d`
- name: `?MdmRegisterDevice@@YAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *, struct MdmRegistrationParameters *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800053b0`
- `0x180006560`
- `0x1800065c0`
- `0x180011800`

## string_xrefs

- `0x180005423`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegisterDevice(
        unsigned int *a1,
        const unsigned __int16 *a2,
        struct MdmRegistrationParameters *a3)
{
  int v6; // edx
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rcx
  int v11; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-40h] BYREF
  int *v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+50h] [rbp-28h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_REGISTER_DEVICE,
      (__int64)a3,
      1u,
      &v12);
  v7 = MdmHttpWrapper::RegisterDevice(a1, a2, a3);
  if ( v7 < 0 )
  {
    v9 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v6,
      v7,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      102,
      "CHR(MdmHttpWrapper::RegisterDevice(pdwHttpStatus, pwszTicket, pParameters))");
  }
  v9 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v9 & 2) != 0 )
  {
    v11 = v7;
    v13 = &v11;
    v14 = 4;
    McGenEventWrite_EventWriteTransfer(
      v9,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_REGISTER_DEVICE_RESULT,
      v8,
      2u,
      &v12);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800053b0  push    rbx
0x1800053b2  push    rsi
0x1800053b3  push    rdi
0x1800053b4  sub     rsp, 60h
0x1800053b8  mov     rax, cs:__security_cookie
0x1800053bf  xor     rax, rsp
0x1800053c2  mov     [rsp+78h+var_20], rax
0x1800053c7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800053ce  mov     rsi, r8
0x1800053d1  mov     rdi, rdx
0x1800053d4  mov     rbx, rcx
0x1800053d7  jz      short loc_1800053F5
0x1800053d9  lea     rax, [rsp+78h+var_40]
0x1800053de  mov     r9d, 1
0x1800053e4  lea     rdx, MDMCOMMON_TRACE_REGISTER_DEVICE
0x1800053eb  mov     [rsp+78h+var_58], rax
0x1800053f0  call    McGenEventWrite_EventWriteTransfer
0x1800053f5  mov     r8, rsi; struct MdmRegistrationParameters *
0x1800053f8  mov     rdx, rdi; unsigned __int16 *
0x1800053fb  mov     rcx, rbx; unsigned int *
0x1800053fe  call    ?RegisterDevice@MdmHttpWrapper@@SAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z; MdmHttpWrapper::RegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)
0x180005403  mov     ebx, eax
0x180005405  test    eax, eax
0x180005407  jns     short loc_180005437
0x180005409  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18000540f  test    cl, 1
0x180005412  jz      short loc_18000543D
0x180005414  lea     rax, aChrMdmhttpwrap_2; "CHR(MdmHttpWrapper::RegisterDevice(pdwH"...
0x18000541b  mov     r8d, ebx
0x18000541e  mov     [rsp+78h+var_50], rax
0x180005423  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000542a  mov     dword ptr [rsp+78h+var_58], 166h
0x180005432  call    McTemplateU0dsqs_EventWriteTransfer
0x180005437  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18000543d  test    cl, 2
0x180005440  jz      short loc_180005475
0x180005442  lea     rax, [rsp+78h+var_48]
0x180005447  mov     [rsp+78h+var_48], ebx
0x18000544b  mov     [rsp+78h+var_30], rax
0x180005450  lea     rdx, MDMCOMMON_TRACE_REGISTER_DEVICE_RESULT
0x180005457  lea     rax, [rsp+78h+var_40]
0x18000545c  mov     [rsp+78h+var_28], 4
0x180005465  mov     r9d, 2
0x18000546b  mov     [rsp+78h+var_58], rax
0x180005470  call    McGenEventWrite_EventWriteTransfer
0x180005475  mov     eax, ebx
0x180005477  mov     rcx, [rsp+78h+var_20]
0x18000547c  xor     rcx, rsp; StackCookie
0x18000547f  call    __security_check_cookie
0x180005484  add     rsp, 60h
0x180005488  pop     rdi
0x180005489  pop     rsi
0x18000548a  pop     rbx
0x18000548b  retn
```
