# MdmHttpRequest::SendDelegationRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001b394`
- end: `0x18001b77a`
- name: `?SendDelegationRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `998`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWCH lpWideCharStr, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b780`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002de4`
- `0x180006548`
- `0x18001a39c`
- `0x18001a588`
- `0x18001b394`
- `0x18001b8b0`

## string_xrefs

- `0x18001b48a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b4d5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b520`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b597`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b692`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b6f9`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001b4c1`: `CPR(pwszUrlPath)`
- `0x18001b65d`: `Content-Type: application/json\n`
- `0x18001b67e`: `CHR(SendHttpRequest( pwszMethod, L"Content-Type: application/json\r\n", pwszHost, pwszUrlPath, pwszDeviceTicket, pwszDelegationTicket, 1, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fReadResponse ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::SendDelegationRequest(
        MdmHttpRequest *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        LPCWCH lpWideCharStr,
        unsigned int *a8,
        unsigned __int16 **a9)
{
  const unsigned __int16 *v10; // r11
  MdmHttpRequest *v12; // r10
  const unsigned __int16 *v13; // rsi
  unsigned __int16 *v14; // rbx
  char *v15; // r8
  unsigned int v16; // r9d
  int v17; // ebx
  const WCHAR *v18; // rcx
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  unsigned int v26; // [rsp+80h] [rbp-A8h] BYREF
  unsigned int cbMultiByte; // [rsp+84h] [rbp-A4h] BYREF
  unsigned __int16 *v28; // [rsp+88h] [rbp-A0h] BYREF
  char *v29; // [rsp+90h] [rbp-98h] BYREF
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-90h] BYREF
  MdmHttpRequest *v31; // [rsp+A0h] [rbp-88h]
  unsigned __int16 *v32; // [rsp+A8h] [rbp-80h]
  unsigned __int16 *v33; // [rsp+B0h] [rbp-78h]
  unsigned __int16 *v34; // [rsp+B8h] [rbp-70h]
  _OWORD v35[2]; // [rsp+C0h] [rbp-68h] BYREF

  v10 = a3;
  v32 = a3;
  v12 = this;
  v31 = this;
  v13 = lpWideCharStr;
  v14 = a5;
  v33 = a5;
  v34 = a6;
  v15 = 0;
  v29 = 0;
  v16 = 0;
  v26 = 0;
  cbMultiByte = 0;
  lpMultiByteStr = 0;
  v28 = 0;
  v35[0] = 0;
  v35[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35[0]) = 0;
  if ( !a8 )
  {
    v17 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        211,
        "CPR(pdwHttpStatus)");
LABEL_10:
    std::wstring::~wstring((char **)v35);
    return (unsigned int)v17;
  }
  if ( !a4 )
  {
    v17 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        212,
        "CPR(pwszUrlPath)");
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v17 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        213,
        "CPR(pwszHost)");
    goto LABEL_10;
  }
  *a8 = 0;
  if ( *((_QWORD *)lpWideCharStr + 2) )
  {
    if ( *((_QWORD *)lpWideCharStr + 3) <= 7u )
      v18 = lpWideCharStr;
    else
      v18 = *(const WCHAR **)lpWideCharStr;
    v17 = MdmConverters::ConvertWideCharToMultiByte(v18, *((_DWORD *)lpWideCharStr + 4), &v29, &v26);
    if ( v17 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v20,
          v19,
          v17,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          224,
          "CHR(MdmConverters::ConvertWideCharToMultiByte( wstrBody.c_str(), (DWORD)wstrBody.length(), &pszMultiByteBody, &cbNeededLen))");
      goto LABEL_30;
    }
    v15 = v29;
    v16 = v26;
    v12 = v31;
    v10 = v32;
    v14 = v33;
  }
  if ( *((_QWORD *)lpWideCharStr + 3) > 7u )
    v13 = *(const unsigned __int16 **)lpWideCharStr;
  v17 = MdmHttpRequest::SendHttpRequest(
          v12,
          v10,
          L"Content-Type: application/json\r\n",
          a2,
          a4,
          v14,
          v34,
          1,
          0,
          0,
          v13,
          v15,
          v16,
          a8,
          (unsigned int *)((unsigned __int64)&cbMultiByte & ((unsigned __int128)-(__int128)(unsigned __int64)a9 >> 64)),
          (unsigned __int8 **)((unsigned __int64)&lpMultiByteStr & -(__int64)(a9 != 0)));
  if ( v17 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v22,
        v21,
        v17,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        243,
        "CHR(SendHttpRequest( pwszMethod, L\"Content-Type: application/json\\r\\n\", pwszHost, pwszUrlPath, pwszDeviceTic"
        "ket, pwszDelegationTicket, 1, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fReadR"
        "esponse ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))");
    goto LABEL_30;
  }
  if ( !a9 )
  {
LABEL_30:
    std::wstring::~wstring((char **)v35);
    return (unsigned int)v17;
  }
  v17 = MdmConverters::ConvertMultiByteToWideChar(lpMultiByteStr, cbMultiByte, &v28);
  if ( v17 >= 0 )
  {
    *a9 = v28;
    v28 = 0;
    goto LABEL_30;
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v24,
      v23,
      v17,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      247,
      "CHR(MdmConverters::ConvertMultiByteToWideChar(pbBuffer, cbBuffer, &pwszBuffer))");
  std::wstring::~wstring((char **)v35);
  if ( v28 )
    operator delete(v28);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001b394  push    rbx
0x18001b396  push    rsi
0x18001b397  push    rdi
0x18001b398  push    r12
0x18001b39a  push    r13
0x18001b39c  push    r14
0x18001b39e  push    r15
0x18001b3a0  sub     rsp, 0F0h
0x18001b3a7  mov     rax, cs:__security_cookie
0x18001b3ae  xor     rax, rsp
0x18001b3b1  mov     [rsp+128h+var_48], rax
0x18001b3b9  mov     r13, r9
0x18001b3bc  mov     r11, r8
0x18001b3bf  mov     [rsp+128h+var_80], r8
0x18001b3c7  mov     r12, rdx
0x18001b3ca  mov     r10, rcx
0x18001b3cd  mov     [rsp+128h+var_88], rcx
0x18001b3d5  mov     r14, [rsp+128h+arg_40]
0x18001b3dd  mov     rsi, [rsp+128h+lpWideCharStr]
0x18001b3e5  mov     rbx, [rsp+128h+arg_20]
0x18001b3ed  mov     [rsp+128h+var_78], rbx
0x18001b3f5  mov     rax, [rsp+128h+arg_28]
0x18001b3fd  mov     [rsp+128h+var_70], rax
0x18001b405  mov     r15, [rsp+128h+arg_38]
0x18001b40d  xor     edi, edi
0x18001b40f  mov     r8d, edi
0x18001b412  mov     [rsp+128h+var_98], rdi
0x18001b41a  mov     r9d, edi
0x18001b41d  mov     [rsp+128h+var_A8], edi
0x18001b424  mov     [rsp+128h+cbMultiByte], edi
0x18001b42b  mov     [rsp+128h+lpMultiByteStr], rdi
0x18001b433  mov     [rsp+128h+var_A0], rdi
0x18001b43b  xorps   xmm0, xmm0
0x18001b43e  movups  [rsp+128h+var_68], xmm0
0x18001b446  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b44e  movdqu  [rsp+128h+var_58], xmm1
0x18001b457  mov     word ptr [rsp+128h+var_68], di
0x18001b45f  test    r15, r15
0x18001b462  jnz     short loc_18001B4AA
0x18001b464  mov     r8d, 80070057h
0x18001b46a  mov     ebx, r8d
0x18001b46d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b474  jz      short loc_18001B497
0x18001b476  lea     rax, aCprPdwhttpstat; "CPR(pdwHttpStatus)"
0x18001b47d  mov     [rsp+128h+var_100], rax
0x18001b482  mov     dword ptr [rsp+128h+var_108], 0D3h
0x18001b48a  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b491  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b496  nop
0x18001b497  lea     rcx, [rsp+128h+var_68]
0x18001b49f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b4a4  nop
0x18001b4a5  jmp     loc_18001B755
0x18001b4aa  test    r13, r13
0x18001b4ad  jnz     short loc_18001B4F5
0x18001b4af  mov     r8d, 80070057h
0x18001b4b5  mov     ebx, r8d
0x18001b4b8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b4bf  jz      short loc_18001B4E2
0x18001b4c1  lea     rax, aCprPwszurlpath; "CPR(pwszUrlPath)"
0x18001b4c8  mov     [rsp+128h+var_100], rax
0x18001b4cd  mov     dword ptr [rsp+128h+var_108], 0D4h
0x18001b4d5  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b4dc  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b4e1  nop
0x18001b4e2  lea     rcx, [rsp+128h+var_68]
0x18001b4ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b4ef  nop
0x18001b4f0  jmp     loc_18001B755
0x18001b4f5  test    r12, r12
0x18001b4f8  jnz     short loc_18001B540
0x18001b4fa  mov     r8d, 80070057h
0x18001b500  mov     ebx, r8d
0x18001b503  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b50a  jz      short loc_18001B52D
0x18001b50c  lea     rax, aCprPwszhost; "CPR(pwszHost)"
0x18001b513  mov     [rsp+128h+var_100], rax
0x18001b518  mov     dword ptr [rsp+128h+var_108], 0D5h
0x18001b520  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b527  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b52c  nop
0x18001b52d  lea     rcx, [rsp+128h+var_68]
0x18001b535  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b53a  nop
0x18001b53b  jmp     loc_18001B755
0x18001b540  mov     [r15], edi
0x18001b543  cmp     [rsi+10h], rdi
0x18001b547  jbe     loc_18001B5E2
0x18001b54d  cmp     qword ptr [rsi+18h], 7
0x18001b552  jbe     short loc_18001B559
0x18001b554  mov     rcx, [rsi]
0x18001b557  jmp     short loc_18001B55C
0x18001b559  mov     rcx, rsi; lpWideCharStr
0x18001b55c  lea     r9, [rsp+128h+var_A8]; unsigned int *
0x18001b564  lea     r8, [rsp+128h+var_98]; char **
0x18001b56c  mov     edx, [rsi+10h]; cchWideChar
0x18001b56f  call    ?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z; MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)
0x18001b574  mov     ebx, eax
0x18001b576  test    eax, eax
0x18001b578  jns     short loc_18001B5BA
0x18001b57a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b581  jz      short loc_18001B5A7
0x18001b583  lea     rax, aChrMdmconverte_3; "CHR(MdmConverters::ConvertWideCharToMul"...
0x18001b58a  mov     [rsp+128h+var_100], rax
0x18001b58f  mov     dword ptr [rsp+128h+var_108], 0E0h
0x18001b597  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b59e  mov     r8d, ebx
0x18001b5a1  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b5a6  nop
0x18001b5a7  lea     rcx, [rsp+128h+var_68]
0x18001b5af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b5b4  nop
0x18001b5b5  jmp     loc_18001B755
0x18001b5ba  mov     r8, [rsp+128h+var_98]
0x18001b5c2  mov     r9d, [rsp+128h+var_A8]
0x18001b5ca  mov     r10, [rsp+128h+var_88]
0x18001b5d2  mov     r11, [rsp+128h+var_80]
0x18001b5da  mov     rbx, [rsp+128h+var_78]
0x18001b5e2  mov     rax, r14
0x18001b5e5  neg     rax
0x18001b5e8  sbb     rcx, rcx
0x18001b5eb  lea     rax, [rsp+128h+lpMultiByteStr]
0x18001b5f3  and     rcx, rax
0x18001b5f6  mov     rax, r14
0x18001b5f9  neg     rax
0x18001b5fc  sbb     rdx, rdx
0x18001b5ff  lea     rax, [rsp+128h+cbMultiByte]
0x18001b607  and     rdx, rax
0x18001b60a  cmp     qword ptr [rsi+18h], 7
0x18001b60f  jbe     short loc_18001B614
0x18001b611  mov     rsi, [rsi]
0x18001b614  mov     [rsp+128h+var_B0], rcx; unsigned __int8 **
0x18001b619  mov     [rsp+128h+var_B8], rdx; unsigned int *
0x18001b61e  mov     [rsp+128h+var_C0], r15; unsigned int *
0x18001b623  mov     [rsp+128h+var_C8], r9d; unsigned int
0x18001b628  mov     [rsp+128h+var_D0], r8; char *
0x18001b62d  mov     [rsp+128h+var_D8], rsi; unsigned __int16 *
0x18001b632  mov     [rsp+128h+var_E0], edi; unsigned int
0x18001b636  mov     [rsp+128h+var_E8], rdi; unsigned __int16 *
0x18001b63b  mov     [rsp+128h+var_F0], 1; int
0x18001b643  mov     rax, [rsp+128h+var_70]
0x18001b64b  mov     [rsp+128h+var_F8], rax; unsigned __int16 *
0x18001b650  mov     [rsp+128h+var_100], rbx; unsigned __int16 *
0x18001b655  mov     [rsp+128h+var_108], r13; unsigned __int16 *
0x18001b65a  mov     r9, r12; unsigned __int16 *
0x18001b65d  lea     r8, szHeaders; "Content-Type: application/json\r\n"
0x18001b664  mov     rdx, r11; unsigned __int16 *
0x18001b667  mov     rcx, r10; this
0x18001b66a  call    ?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z; MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)
0x18001b66f  mov     ebx, eax
0x18001b671  test    eax, eax
0x18001b673  jns     short loc_18001B6B5
0x18001b675  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b67c  jz      short loc_18001B6A2
0x18001b67e  lea     rax, aChrSendhttpreq_0; "CHR(SendHttpRequest( pwszMethod, L\"Con"...
0x18001b685  mov     [rsp+128h+var_100], rax
0x18001b68a  mov     dword ptr [rsp+128h+var_108], 0F3h
0x18001b692  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b699  mov     r8d, ebx
0x18001b69c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b6a1  nop
0x18001b6a2  lea     rcx, [rsp+128h+var_68]
0x18001b6aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b6af  nop
0x18001b6b0  jmp     loc_18001B755
0x18001b6b5  test    r14, r14
0x18001b6b8  jz      short loc_18001B72C
0x18001b6ba  lea     r8, [rsp+128h+var_A0]; unsigned __int16 **
0x18001b6c2  mov     edx, [rsp+128h+cbMultiByte]; cbMultiByte
0x18001b6c9  mov     rcx, [rsp+128h+lpMultiByteStr]; lpMultiByteStr
0x18001b6d1  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18001b6d6  mov     ebx, eax
0x18001b6d8  test    eax, eax
0x18001b6da  jns     short loc_18001B719
0x18001b6dc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001b6e3  jz      short loc_18001B709
0x18001b6e5  lea     rax, aChrMdmconverte_0; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18001b6ec  mov     [rsp+128h+var_100], rax
0x18001b6f1  mov     dword ptr [rsp+128h+var_108], 0F7h
0x18001b6f9  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001b700  mov     r8d, ebx
0x18001b703  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b708  nop
0x18001b709  lea     rcx, [rsp+128h+var_68]
0x18001b711  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b716  nop
0x18001b717  jmp     short loc_18001B743
0x18001b719  mov     rax, [rsp+128h+var_A0]
0x18001b721  mov     [r14], rax
0x18001b724  mov     [rsp+128h+var_A0], rdi
0x18001b72c  lea     rcx, [rsp+128h+var_68]
0x18001b734  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b739  nop
0x18001b73a  jmp     short loc_18001B755
0x18001b73c  mov     ebx, [rsp+128h+var_A8]
0x18001b743  mov     rcx, [rsp+128h+var_A0]; void *
0x18001b74b  test    rcx, rcx
0x18001b74e  jz      short loc_18001B755
0x18001b750  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b755  mov     eax, ebx
0x18001b757  mov     rcx, [rsp+128h+var_48]
0x18001b75f  xor     rcx, rsp; StackCookie
0x18001b762  call    __security_check_cookie
0x18001b767  add     rsp, 0F0h
0x18001b76e  pop     r15
0x18001b770  pop     r14
0x18001b772  pop     r13
0x18001b774  pop     r12
0x18001b776  pop     rdi
0x18001b777  pop     rsi
0x18001b778  pop     rbx
0x18001b779  retn
```
