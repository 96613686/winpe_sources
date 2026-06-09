# MdmHttpRequest::SendDelegationRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001b924`
- end: `0x18001bd0b`
- name: `?SendDelegationRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `999`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, LPCWCH lpWideCharStr, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001bd20`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002de8`
- `0x1800065c0`
- `0x18001a8c0`
- `0x18001aac0`
- `0x18001b924`
- `0x18001be50`

## string_xrefs

- `0x18001ba1a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001ba65`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001bab0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001bb27`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001bc22`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001bc89`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001ba51`: `CPR(pwszUrlPath)`
- `0x18001bbed`: `Content-Type: application/json\n`
- `0x18001bc0e`: `CHR(SendHttpRequest( pwszMethod, L"Content-Type: application/json\r\n", pwszHost, pwszUrlPath, pwszDeviceTicket, pwszDelegationTicket, 1, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fReadResponse ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
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
  unsigned __int64 v25; // rdx
  unsigned int v27; // [rsp+80h] [rbp-A8h] BYREF
  unsigned int cbMultiByte; // [rsp+84h] [rbp-A4h] BYREF
  unsigned __int16 *v29; // [rsp+88h] [rbp-A0h] BYREF
  char *v30; // [rsp+90h] [rbp-98h] BYREF
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-90h] BYREF
  MdmHttpRequest *v32; // [rsp+A0h] [rbp-88h]
  unsigned __int16 *v33; // [rsp+A8h] [rbp-80h]
  unsigned __int16 *v34; // [rsp+B0h] [rbp-78h]
  unsigned __int16 *v35; // [rsp+B8h] [rbp-70h]
  _OWORD v36[2]; // [rsp+C0h] [rbp-68h] BYREF

  v10 = a3;
  v33 = a3;
  v12 = this;
  v32 = this;
  v13 = lpWideCharStr;
  v14 = a5;
  v34 = a5;
  v35 = a6;
  v15 = 0;
  v30 = 0;
  v16 = 0;
  v27 = 0;
  cbMultiByte = 0;
  lpMultiByteStr = 0;
  v29 = 0;
  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
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
    std::wstring::~wstring(v36);
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
    v17 = MdmConverters::ConvertWideCharToMultiByte(v18, *((_DWORD *)lpWideCharStr + 4), &v30, &v27);
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
    v15 = v30;
    v16 = v27;
    v12 = v32;
    v10 = v33;
    v14 = v34;
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
          v35,
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
    std::wstring::~wstring(v36);
    return (unsigned int)v17;
  }
  v17 = MdmConverters::ConvertMultiByteToWideChar(lpMultiByteStr, cbMultiByte, &v29);
  if ( v17 >= 0 )
  {
    *a9 = v29;
    v29 = 0;
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
  std::wstring::~wstring(v36);
  if ( v29 )
    operator delete(v29, v25);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001b924  push    rbx
0x18001b926  push    rsi
0x18001b927  push    rdi
0x18001b928  push    r12
0x18001b92a  push    r13
0x18001b92c  push    r14
0x18001b92e  push    r15
0x18001b930  sub     rsp, 0F0h
0x18001b937  mov     rax, cs:__security_cookie
0x18001b93e  xor     rax, rsp
0x18001b941  mov     [rsp+128h+var_48], rax
0x18001b949  mov     r13, r9
0x18001b94c  mov     r11, r8
0x18001b94f  mov     [rsp+128h+var_80], r8
0x18001b957  mov     r12, rdx
0x18001b95a  mov     r10, rcx
0x18001b95d  mov     [rsp+128h+var_88], rcx
0x18001b965  mov     r14, [rsp+128h+arg_40]
0x18001b96d  mov     rsi, [rsp+128h+lpWideCharStr]
0x18001b975  mov     rbx, [rsp+128h+arg_20]
0x18001b97d  mov     [rsp+128h+var_78], rbx
0x18001b985  mov     rax, [rsp+128h+arg_28]
0x18001b98d  mov     [rsp+128h+var_70], rax
0x18001b995  mov     r15, [rsp+128h+arg_38]
0x18001b99d  xor     edi, edi
0x18001b99f  mov     r8d, edi
0x18001b9a2  mov     [rsp+128h+var_98], rdi
0x18001b9aa  mov     r9d, edi
0x18001b9ad  mov     [rsp+128h+var_A8], edi
0x18001b9b4  mov     [rsp+128h+cbMultiByte], edi
0x18001b9bb  mov     [rsp+128h+lpMultiByteStr], rdi
0x18001b9c3  mov     [rsp+128h+var_A0], rdi
0x18001b9cb  xorps   xmm0, xmm0
0x18001b9ce  movups  [rsp+128h+var_68], xmm0
0x18001b9d6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001b9de  movdqu  [rsp+128h+var_58], xmm1
0x18001b9e7  mov     word ptr [rsp+128h+var_68], di
0x18001b9ef  test    r15, r15
0x18001b9f2  jnz     short loc_18001BA3A
0x18001b9f4  mov     r8d, 80070057h
0x18001b9fa  mov     ebx, r8d
0x18001b9fd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ba04  jz      short loc_18001BA27
0x18001ba06  lea     rax, aCprPdwhttpstat; "CPR(pdwHttpStatus)"
0x18001ba0d  mov     [rsp+128h+var_100], rax
0x18001ba12  mov     dword ptr [rsp+128h+var_108], 0D3h
0x18001ba1a  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ba21  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ba26  nop
0x18001ba27  lea     rcx, [rsp+128h+var_68]
0x18001ba2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ba34  nop
0x18001ba35  jmp     loc_18001BCE5
0x18001ba3a  test    r13, r13
0x18001ba3d  jnz     short loc_18001BA85
0x18001ba3f  mov     r8d, 80070057h
0x18001ba45  mov     ebx, r8d
0x18001ba48  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ba4f  jz      short loc_18001BA72
0x18001ba51  lea     rax, aCprPwszurlpath; "CPR(pwszUrlPath)"
0x18001ba58  mov     [rsp+128h+var_100], rax
0x18001ba5d  mov     dword ptr [rsp+128h+var_108], 0D4h
0x18001ba65  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ba6c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ba71  nop
0x18001ba72  lea     rcx, [rsp+128h+var_68]
0x18001ba7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ba7f  nop
0x18001ba80  jmp     loc_18001BCE5
0x18001ba85  test    r12, r12
0x18001ba88  jnz     short loc_18001BAD0
0x18001ba8a  mov     r8d, 80070057h
0x18001ba90  mov     ebx, r8d
0x18001ba93  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ba9a  jz      short loc_18001BABD
0x18001ba9c  lea     rax, aCprPwszhost; "CPR(pwszHost)"
0x18001baa3  mov     [rsp+128h+var_100], rax
0x18001baa8  mov     dword ptr [rsp+128h+var_108], 0D5h
0x18001bab0  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001bab7  call    McTemplateU0dsqs_EventWriteTransfer
0x18001babc  nop
0x18001babd  lea     rcx, [rsp+128h+var_68]
0x18001bac5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001baca  nop
0x18001bacb  jmp     loc_18001BCE5
0x18001bad0  mov     [r15], edi
0x18001bad3  cmp     [rsi+10h], rdi
0x18001bad7  jbe     loc_18001BB72
0x18001badd  cmp     qword ptr [rsi+18h], 7
0x18001bae2  jbe     short loc_18001BAE9
0x18001bae4  mov     rcx, [rsi]
0x18001bae7  jmp     short loc_18001BAEC
0x18001bae9  mov     rcx, rsi; lpWideCharStr
0x18001baec  lea     r9, [rsp+128h+var_A8]; unsigned int *
0x18001baf4  lea     r8, [rsp+128h+var_98]; char **
0x18001bafc  mov     edx, [rsi+10h]; cchWideChar
0x18001baff  call    ?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z; MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)
0x18001bb04  mov     ebx, eax
0x18001bb06  test    eax, eax
0x18001bb08  jns     short loc_18001BB4A
0x18001bb0a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bb11  jz      short loc_18001BB37
0x18001bb13  lea     rax, aChrMdmconverte_3; "CHR(MdmConverters::ConvertWideCharToMul"...
0x18001bb1a  mov     [rsp+128h+var_100], rax
0x18001bb1f  mov     dword ptr [rsp+128h+var_108], 0E0h
0x18001bb27  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001bb2e  mov     r8d, ebx
0x18001bb31  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bb36  nop
0x18001bb37  lea     rcx, [rsp+128h+var_68]
0x18001bb3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bb44  nop
0x18001bb45  jmp     loc_18001BCE5
0x18001bb4a  mov     r8, [rsp+128h+var_98]
0x18001bb52  mov     r9d, [rsp+128h+var_A8]
0x18001bb5a  mov     r10, [rsp+128h+var_88]
0x18001bb62  mov     r11, [rsp+128h+var_80]
0x18001bb6a  mov     rbx, [rsp+128h+var_78]
0x18001bb72  mov     rax, r14
0x18001bb75  neg     rax
0x18001bb78  sbb     rcx, rcx
0x18001bb7b  lea     rax, [rsp+128h+lpMultiByteStr]
0x18001bb83  and     rcx, rax
0x18001bb86  mov     rax, r14
0x18001bb89  neg     rax
0x18001bb8c  sbb     rdx, rdx
0x18001bb8f  lea     rax, [rsp+128h+cbMultiByte]
0x18001bb97  and     rdx, rax
0x18001bb9a  cmp     qword ptr [rsi+18h], 7
0x18001bb9f  jbe     short loc_18001BBA4
0x18001bba1  mov     rsi, [rsi]
0x18001bba4  mov     [rsp+128h+var_B0], rcx; unsigned __int8 **
0x18001bba9  mov     [rsp+128h+var_B8], rdx; unsigned int *
0x18001bbae  mov     [rsp+128h+var_C0], r15; unsigned int *
0x18001bbb3  mov     [rsp+128h+var_C8], r9d; unsigned int
0x18001bbb8  mov     [rsp+128h+var_D0], r8; char *
0x18001bbbd  mov     [rsp+128h+var_D8], rsi; unsigned __int16 *
0x18001bbc2  mov     [rsp+128h+var_E0], edi; unsigned int
0x18001bbc6  mov     [rsp+128h+var_E8], rdi; unsigned __int16 *
0x18001bbcb  mov     [rsp+128h+var_F0], 1; int
0x18001bbd3  mov     rax, [rsp+128h+var_70]
0x18001bbdb  mov     [rsp+128h+var_F8], rax; unsigned __int16 *
0x18001bbe0  mov     [rsp+128h+var_100], rbx; unsigned __int16 *
0x18001bbe5  mov     [rsp+128h+var_108], r13; unsigned __int16 *
0x18001bbea  mov     r9, r12; unsigned __int16 *
0x18001bbed  lea     r8, szHeaders; "Content-Type: application/json\r\n"
0x18001bbf4  mov     rdx, r11; unsigned __int16 *
0x18001bbf7  mov     rcx, r10; this
0x18001bbfa  call    ?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z; MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)
0x18001bbff  mov     ebx, eax
0x18001bc01  test    eax, eax
0x18001bc03  jns     short loc_18001BC45
0x18001bc05  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bc0c  jz      short loc_18001BC32
0x18001bc0e  lea     rax, aChrSendhttpreq_0; "CHR(SendHttpRequest( pwszMethod, L\"Con"...
0x18001bc15  mov     [rsp+128h+var_100], rax
0x18001bc1a  mov     dword ptr [rsp+128h+var_108], 0F3h
0x18001bc22  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001bc29  mov     r8d, ebx
0x18001bc2c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bc31  nop
0x18001bc32  lea     rcx, [rsp+128h+var_68]
0x18001bc3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bc3f  nop
0x18001bc40  jmp     loc_18001BCE5
0x18001bc45  test    r14, r14
0x18001bc48  jz      short loc_18001BCBC
0x18001bc4a  lea     r8, [rsp+128h+var_A0]; unsigned __int16 **
0x18001bc52  mov     edx, [rsp+128h+cbMultiByte]; cbMultiByte
0x18001bc59  mov     rcx, [rsp+128h+lpMultiByteStr]; lpMultiByteStr
0x18001bc61  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18001bc66  mov     ebx, eax
0x18001bc68  test    eax, eax
0x18001bc6a  jns     short loc_18001BCA9
0x18001bc6c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001bc73  jz      short loc_18001BC99
0x18001bc75  lea     rax, aChrMdmconverte_0; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18001bc7c  mov     [rsp+128h+var_100], rax
0x18001bc81  mov     dword ptr [rsp+128h+var_108], 0F7h
0x18001bc89  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001bc90  mov     r8d, ebx
0x18001bc93  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bc98  nop
0x18001bc99  lea     rcx, [rsp+128h+var_68]
0x18001bca1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bca6  nop
0x18001bca7  jmp     short loc_18001BCD3
0x18001bca9  mov     rax, [rsp+128h+var_A0]
0x18001bcb1  mov     [r14], rax
0x18001bcb4  mov     [rsp+128h+var_A0], rdi
0x18001bcbc  lea     rcx, [rsp+128h+var_68]
0x18001bcc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bcc9  nop
0x18001bcca  jmp     short loc_18001BCE5
0x18001bccc  mov     ebx, [rsp+128h+var_A8]
0x18001bcd3  mov     rcx, [rsp+128h+var_A0]; void *
0x18001bcdb  test    rcx, rcx
0x18001bcde  jz      short loc_18001BCE5
0x18001bce0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bce5  mov     eax, ebx
0x18001bce7  mov     rcx, [rsp+128h+var_48]
0x18001bcef  xor     rcx, rsp; StackCookie
0x18001bcf2  call    __security_check_cookie
0x18001bcf7  add     rsp, 0F0h
0x18001bcfe  pop     r15
0x18001bd00  pop     r14
0x18001bd02  pop     r13
0x18001bd04  pop     r12
0x18001bd06  pop     rdi
0x18001bd07  pop     rsi
0x18001bd08  pop     rbx
0x18001bd09  retn
```
