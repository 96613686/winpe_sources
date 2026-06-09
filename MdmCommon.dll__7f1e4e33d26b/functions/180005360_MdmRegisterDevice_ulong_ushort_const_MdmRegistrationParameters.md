# MdmRegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)

- ea: `0x180005360`
- end: `0x18000543c`
- name: `?MdmRegisterDevice@@YAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(unsigned int *, const unsigned __int16 *, struct MdmRegistrationParameters *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180005360`
- `0x1800064f0`
- `0x180006548`
- `0x18001142c`

## string_xrefs

- `0x1800053d3`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

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
  _BYTE v12[16]; // [rsp+38h] [rbp-40h] BYREF
  int *v13; // [rsp+48h] [rbp-30h]
  __int64 v14; // [rsp+50h] [rbp-28h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_REGISTER_DEVICE, a3, 1, v12);
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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
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
    McGenEventWrite_EventWriteTransfer(v9, MDMCOMMON_TRACE_REGISTER_DEVICE_RESULT, v8, 2, v12);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005360  push    rbx
0x180005362  push    rsi
0x180005363  push    rdi
0x180005364  sub     rsp, 60h
0x180005368  mov     rax, cs:__security_cookie
0x18000536f  xor     rax, rsp
0x180005372  mov     [rsp+78h+var_20], rax
0x180005377  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x18000537e  mov     rsi, r8
0x180005381  mov     rdi, rdx
0x180005384  mov     rbx, rcx
0x180005387  jz      short loc_1800053A5
0x180005389  lea     rax, [rsp+78h+var_40]
0x18000538e  mov     r9d, 1
0x180005394  lea     rdx, MDMCOMMON_TRACE_REGISTER_DEVICE
0x18000539b  mov     [rsp+78h+var_58], rax
0x1800053a0  call    McGenEventWrite_EventWriteTransfer
0x1800053a5  mov     r8, rsi; struct MdmRegistrationParameters *
0x1800053a8  mov     rdx, rdi; unsigned __int16 *
0x1800053ab  mov     rcx, rbx; unsigned int *
0x1800053ae  call    ?RegisterDevice@MdmHttpWrapper@@SAJPEAKPEBGPEAUMdmRegistrationParameters@@@Z; MdmHttpWrapper::RegisterDevice(ulong *,ushort const *,MdmRegistrationParameters *)
0x1800053b3  mov     ebx, eax
0x1800053b5  test    eax, eax
0x1800053b7  jns     short loc_1800053E7
0x1800053b9  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800053bf  test    cl, 1
0x1800053c2  jz      short loc_1800053ED
0x1800053c4  lea     rax, aChrMdmhttpwrap_2; "CHR(MdmHttpWrapper::RegisterDevice(pdwH"...
0x1800053cb  mov     r8d, ebx
0x1800053ce  mov     [rsp+78h+var_50], rax
0x1800053d3  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800053da  mov     dword ptr [rsp+78h+var_58], 166h
0x1800053e2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800053e7  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800053ed  test    cl, 2
0x1800053f0  jz      short loc_180005425
0x1800053f2  lea     rax, [rsp+78h+var_48]
0x1800053f7  mov     [rsp+78h+var_48], ebx
0x1800053fb  mov     [rsp+78h+var_30], rax
0x180005400  lea     rdx, MDMCOMMON_TRACE_REGISTER_DEVICE_RESULT
0x180005407  lea     rax, [rsp+78h+var_40]
0x18000540c  mov     [rsp+78h+var_28], 4
0x180005415  mov     r9d, 2
0x18000541b  mov     [rsp+78h+var_58], rax
0x180005420  call    McGenEventWrite_EventWriteTransfer
0x180005425  mov     eax, ebx
0x180005427  mov     rcx, [rsp+78h+var_20]
0x18000542c  xor     rcx, rsp; StackCookie
0x18000542f  call    __security_check_cookie
0x180005434  add     rsp, 60h
0x180005438  pop     rdi
0x180005439  pop     rsi
0x18000543a  pop     rbx
0x18000543b  retn
```
