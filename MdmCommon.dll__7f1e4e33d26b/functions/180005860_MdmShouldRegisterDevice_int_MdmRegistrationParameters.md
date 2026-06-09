# MdmShouldRegisterDevice(int *,MdmRegistrationParameters *)

- ea: `0x180005860`
- end: `0x180005a09`
- name: `?MdmShouldRegisterDevice@@YAJPEAHPEAUMdmRegistrationParameters@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(int *, struct MdmRegistrationParameters *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180002de4`
- `0x180005860`
- `0x1800064f0`
- `0x180006548`
- `0x18000c38c`

## string_xrefs

- `0x180005904`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005977`: `CHR(MdmHttpWrapper::CreateRegisterDeviceRequestBody( pParameters, wstrBody, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, wstrNotUsed, &fNotUsed))`

## pseudocode

```c
__int64 __fastcall MdmShouldRegisterDevice(int *a1, struct MdmRegistrationParameters *a2, __int64 a3)
{
  int v5; // ebx
  int v6; // edx
  int v8; // [rsp+50h] [rbp-29h] BYREF
  int v9; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v10[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v11; // [rsp+80h] [rbp+7h] BYREF
  __m128i si128; // [rsp+90h] [rbp+17h]
  _BYTE v13[16]; // [rsp+A0h] [rbp+27h] BYREF
  int *v14; // [rsp+B0h] [rbp+37h]
  __int64 v15; // [rsp+B8h] [rbp+3Fh]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_SHOULD_REGISTER_DEVICE, a3, 1, v13);
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
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_SHOULD_REGISTER_DEVICE_RESULT, a3, 2, v13);
  }
  std::wstring::~wstring((char **)v10);
  std::wstring::~wstring((char **)&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005860  mov     [rsp-8+arg_10], rbx
0x180005865  mov     [rsp-8+arg_18], rdi
0x18000586a  push    rbp
0x18000586b  lea     rbp, [rsp-57h]
0x180005870  sub     rsp, 0D0h
0x180005877  mov     rax, cs:__security_cookie
0x18000587e  xor     rax, rsp
0x180005881  mov     [rbp+57h+var_10], rax
0x180005885  mov     rbx, rdx
0x180005888  mov     rdi, rcx
0x18000588b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005892  jz      short loc_1800058AF
0x180005894  lea     rax, [rbp+57h+var_30]
0x180005898  mov     [rsp+0D0h+var_B0], rax
0x18000589d  mov     r9d, 1
0x1800058a3  lea     rdx, MDMCOMMON_SHOULD_REGISTER_DEVICE
0x1800058aa  call    McGenEventWrite_EventWriteTransfer
0x1800058af  xorps   xmm0, xmm0
0x1800058b2  movups  [rbp+57h+var_50], xmm0
0x1800058b6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800058be  movdqu  [rbp+57h+var_40], xmm1
0x1800058c3  xor     eax, eax
0x1800058c5  mov     word ptr [rbp+57h+var_50], ax
0x1800058c9  movups  [rbp+57h+var_70], xmm0
0x1800058cd  movdqu  [rbp+57h+var_60], xmm1
0x1800058d2  mov     word ptr [rbp+57h+var_70], ax
0x1800058d6  mov     [rbp+57h+var_80], eax
0x1800058d9  test    rdi, rdi
0x1800058dc  jnz     short loc_180005918
0x1800058de  mov     ebx, 80070057h
0x1800058e3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800058ea  jz      loc_18000599B
0x1800058f0  lea     rax, aCprPfshouldreg; "CPR(pfShouldRegister)"
0x1800058f7  mov     [rsp+0D0h+var_A8], rax
0x1800058fc  mov     dword ptr [rsp+0D0h+var_B0], 178h
0x180005904  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000590b  mov     r8d, ebx
0x18000590e  call    McTemplateU0dsqs_EventWriteTransfer
0x180005913  jmp     loc_18000599B
0x180005918  mov     dword ptr [rdi], 0
0x18000591e  lea     rax, [rbp+57h+var_80]
0x180005922  mov     [rsp+0D0h+var_88], rax
0x180005927  lea     rax, [rbp+57h+var_70]
0x18000592b  mov     [rsp+0D0h+var_90], rax
0x180005930  lea     rax, [rbp+57h+var_70]
0x180005934  mov     [rsp+0D0h+var_98], rax
0x180005939  lea     rax, [rbp+57h+var_70]
0x18000593d  mov     [rsp+0D0h+var_A0], rax
0x180005942  lea     rax, [rbp+57h+var_70]
0x180005946  mov     [rsp+0D0h+var_A8], rax
0x18000594b  lea     rax, [rbp+57h+var_70]
0x18000594f  mov     [rsp+0D0h+var_B0], rax
0x180005954  lea     r9, [rbp+57h+var_70]
0x180005958  lea     r8, [rbp+57h+var_70]
0x18000595c  lea     rdx, [rbp+57h+var_50]
0x180005960  mov     rcx, rbx
0x180005963  call    ?CreateRegisterDeviceRequestBody@MdmHttpWrapper@@SAJPEAUMdmRegistrationParameters@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1111111PEAH@Z; MdmHttpWrapper::CreateRegisterDeviceRequestBody(MdmRegistrationParameters *,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,int *)
0x180005968  mov     ebx, eax
0x18000596a  test    eax, eax
0x18000596c  jns     short loc_180005990
0x18000596e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180005975  jz      short loc_18000599B
0x180005977  lea     rax, aChrMdmhttpwrap_1; "CHR(MdmHttpWrapper::CreateRegisterDevic"...
0x18000597e  mov     [rsp+0D0h+var_A8], rax
0x180005983  mov     dword ptr [rsp+0D0h+var_B0], 185h
0x18000598b  jmp     loc_180005904
0x180005990  xor     eax, eax
0x180005992  cmp     qword ptr [rbp+57h+var_40], rax
0x180005996  setnbe  al
0x180005999  mov     [rdi], eax
0x18000599b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800059a2  jz      short loc_1800059D3
0x1800059a4  mov     [rbp+57h+var_78], ebx
0x1800059a7  lea     rax, [rbp+57h+var_78]
0x1800059ab  mov     [rbp+57h+var_20], rax
0x1800059af  mov     [rbp+57h+var_18], 4
0x1800059b7  lea     rax, [rbp+57h+var_30]
0x1800059bb  mov     [rsp+0D0h+var_B0], rax
0x1800059c0  mov     r9d, 2
0x1800059c6  lea     rdx, MDMCOMMON_SHOULD_REGISTER_DEVICE_RESULT
0x1800059cd  call    McGenEventWrite_EventWriteTransfer
0x1800059d2  nop
0x1800059d3  lea     rcx, [rbp+57h+var_70]
0x1800059d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800059dc  nop
0x1800059dd  lea     rcx, [rbp+57h+var_50]
0x1800059e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800059e6  mov     eax, ebx
0x1800059e8  mov     rcx, [rbp+57h+var_10]
0x1800059ec  xor     rcx, rsp; StackCookie
0x1800059ef  call    __security_check_cookie
0x1800059f4  lea     r11, [rsp+0D0h+var_s0]
0x1800059fc  mov     rbx, [r11+20h]
0x180005a00  mov     rdi, [r11+28h]
0x180005a04  mov     rsp, r11
0x180005a07  pop     rbp
0x180005a08  retn
```
