# MdmShouldRegisterDevice(int *,MdmRegistrationParameters *)

- ea: `0x1800058b0`
- end: `0x180005a5a`
- name: `?MdmShouldRegisterDevice@@YAJPEAHPEAUMdmRegistrationParameters@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(int *, struct MdmRegistrationParameters *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de8`
- `0x1800058b0`
- `0x180006560`
- `0x1800065c0`
- `0x18000c6e8`

## string_xrefs

- `0x180005954`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800059c7`: `CHR(MdmHttpWrapper::CreateRegisterDeviceRequestBody( pParameters, wstrBody, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, &fNotUsed))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmShouldRegisterDevice(int *a1, struct MdmRegistrationParameters *a2, __int64 a3)
{
  int v5; // ebx
  int v6; // edx
  int v8; // [rsp+50h] [rbp-29h] BYREF
  int v9; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v10[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v11; // [rsp+80h] [rbp+7h] BYREF
  __m128i si128; // [rsp+90h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+A0h] [rbp+27h] BYREF
  int *v14; // [rsp+B0h] [rbp+37h]
  __int64 v15; // [rsp+B8h] [rbp+3Fh]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_SHOULD_REGISTER_DEVICE,
      a3,
      1u,
      &v13);
  v11 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11) = 0;
  v10[0] = 0;
  v10[1] = si128;
  LOWORD(v10[0]) = 0;
  v8 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v5 = MdmHttpWrapper::CreateRegisterDeviceRequestBody(
           (__int64)a2,
           (unsigned __int64 *)&v11,
           v10,
           v10,
           (__int64)v10,
           (__int64)v10,
           (__int64)v10,
           (__int64)v10,
           (__int64)v10,
           &v8);
    if ( v5 >= 0 )
    {
      *a1 = si128.m128i_i64[0] != 0;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        v6,
        v5,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        133,
        "CHR(MdmHttpWrapper::CreateRegisterDeviceRequestBody( pParameters, wstrBody, wstrNotUsed, wstrNotUsed, wstrNotUse"
        "d, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, &fNotUsed))");
    }
  }
  else
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
        120,
        "CPR(pfShouldRegister)");
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    v9 = v5;
    v14 = &v9;
    v15 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_SHOULD_REGISTER_DEVICE_RESULT,
      a3,
      2u,
      &v13);
  }
  std::wstring::~wstring(v10);
  std::wstring::~wstring(&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800058b0  mov     [rsp-8+arg_10], rbx
0x1800058b5  mov     [rsp-8+arg_18], rdi
0x1800058ba  push    rbp
0x1800058bb  lea     rbp, [rsp-57h]
0x1800058c0  sub     rsp, 0D0h
0x1800058c7  mov     rax, cs:__security_cookie
0x1800058ce  xor     rax, rsp
0x1800058d1  mov     [rbp+57h+var_10], rax
0x1800058d5  mov     rbx, rdx
0x1800058d8  mov     rdi, rcx
0x1800058db  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800058e2  jz      short loc_1800058FF
0x1800058e4  lea     rax, [rbp+57h+var_30]
0x1800058e8  mov     [rsp+0D0h+var_B0], rax
0x1800058ed  mov     r9d, 1
0x1800058f3  lea     rdx, MDMCOMMON_SHOULD_REGISTER_DEVICE
0x1800058fa  call    McGenEventWrite_EventWriteTransfer
0x1800058ff  xorps   xmm0, xmm0
0x180005902  movups  [rbp+57h+var_50], xmm0
0x180005906  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000590e  movdqu  [rbp+57h+var_40], xmm1
0x180005913  xor     eax, eax
0x180005915  mov     word ptr [rbp+57h+var_50], ax
0x180005919  movups  [rbp+57h+var_70], xmm0
0x18000591d  movdqu  [rbp+57h+var_60], xmm1
0x180005922  mov     word ptr [rbp+57h+var_70], ax
0x180005926  mov     [rbp+57h+var_80], eax
0x180005929  test    rdi, rdi
0x18000592c  jnz     short loc_180005968
0x18000592e  mov     ebx, 80070057h
0x180005933  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000593a  jz      loc_1800059EB
0x180005940  lea     rax, aCprPfshouldreg; "CPR(pfShouldRegister)"
0x180005947  mov     [rsp+0D0h+var_A8], rax
0x18000594c  mov     dword ptr [rsp+0D0h+var_B0], 178h
0x180005954  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000595b  mov     r8d, ebx
0x18000595e  call    McTemplateU0dsqs_EventWriteTransfer
0x180005963  jmp     loc_1800059EB
0x180005968  mov     dword ptr [rdi], 0
0x18000596e  lea     rax, [rbp+57h+var_80]
0x180005972  mov     [rsp+0D0h+var_88], rax
0x180005977  lea     rax, [rbp+57h+var_70]
0x18000597b  mov     [rsp+0D0h+var_90], rax
0x180005980  lea     rax, [rbp+57h+var_70]
0x180005984  mov     [rsp+0D0h+var_98], rax
0x180005989  lea     rax, [rbp+57h+var_70]
0x18000598d  mov     [rsp+0D0h+var_A0], rax
0x180005992  lea     rax, [rbp+57h+var_70]
0x180005996  mov     [rsp+0D0h+var_A8], rax
0x18000599b  lea     rax, [rbp+57h+var_70]
0x18000599f  mov     [rsp+0D0h+var_B0], rax
0x1800059a4  lea     r9, [rbp+57h+var_70]
0x1800059a8  lea     r8, [rbp+57h+var_70]
0x1800059ac  lea     rdx, [rbp+57h+var_50]
0x1800059b0  mov     rcx, rbx
0x1800059b3  call    ?CreateRegisterDeviceRequestBody@MdmHttpWrapper@@SAJPEAUMdmRegistrationParameters@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1111111PEAH@Z; MdmHttpWrapper::CreateRegisterDeviceRequestBody(MdmRegistrationParameters *,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,int *)
0x1800059b8  mov     ebx, eax
0x1800059ba  test    eax, eax
0x1800059bc  jns     short loc_1800059E0
0x1800059be  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800059c5  jz      short loc_1800059EB
0x1800059c7  lea     rax, aChrMdmhttpwrap_1; "CHR(MdmHttpWrapper::CreateRegisterDevic"...
0x1800059ce  mov     [rsp+0D0h+var_A8], rax
0x1800059d3  mov     dword ptr [rsp+0D0h+var_B0], 185h
0x1800059db  jmp     loc_180005954
0x1800059e0  xor     eax, eax
0x1800059e2  cmp     qword ptr [rbp+57h+var_40], rax
0x1800059e6  setnbe  al
0x1800059e9  mov     [rdi], eax
0x1800059eb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800059f2  jz      short loc_180005A23
0x1800059f4  mov     [rbp+57h+var_78], ebx
0x1800059f7  lea     rax, [rbp+57h+var_78]
0x1800059fb  mov     [rbp+57h+var_20], rax
0x1800059ff  mov     [rbp+57h+var_18], 4
0x180005a07  lea     rax, [rbp+57h+var_30]
0x180005a0b  mov     [rsp+0D0h+var_B0], rax
0x180005a10  mov     r9d, 2
0x180005a16  lea     rdx, MDMCOMMON_SHOULD_REGISTER_DEVICE_RESULT
0x180005a1d  call    McGenEventWrite_EventWriteTransfer
0x180005a22  nop
0x180005a23  lea     rcx, [rbp+57h+var_70]
0x180005a27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005a2c  nop
0x180005a2d  lea     rcx, [rbp+57h+var_50]
0x180005a31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005a36  mov     eax, ebx
0x180005a38  mov     rcx, [rbp+57h+var_10]
0x180005a3c  xor     rcx, rsp; StackCookie
0x180005a3f  call    __security_check_cookie
0x180005a44  lea     r11, [rsp+0D0h+var_s0]
0x180005a4c  mov     rbx, [r11+20h]
0x180005a50  mov     rdi, [r11+28h]
0x180005a54  mov     rsp, r11
0x180005a57  pop     rbp
0x180005a58  retn
```
