# MdmHttpRequest::SendRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001c8d0`
- end: `0x18001cc1b`
- name: `?SendRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `843`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWCH lpWideCharStr, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001cc30`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002de8`
- `0x1800065c0`
- `0x18001a8c0`
- `0x18001aac0`
- `0x18001be50`
- `0x18001c8d0`

## string_xrefs

- `0x18001c9c2`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001cbaf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001c9ee`: `CPR(pwszUrlPath)`
- `0x18001cb2d`: `Content-Type: application/json\n`
- `0x18001cb52`: `CHR(SendHttpRequest( pwszMethod, L"Content-Type: application/json\r\n", pwszHost, pwszUrlPath, pwszMainTicket, pwszSecondaryTicket, 0, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fReadResponse ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall MdmHttpRequest::SendRequest(
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
  const unsigned __int16 *v10; // r10
  const unsigned __int16 *v13; // rdi
  unsigned __int16 *v14; // r11
  unsigned __int16 *v15; // rbx
  int v16; // ecx
  char *v17; // r8
  unsigned int v18; // r9d
  int v19; // r8d
  int v20; // ebx
  const WCHAR *v21; // rcx
  unsigned __int64 v22; // rdx
  int v23; // ecx
  unsigned __int16 *v24; // rcx
  char v26; // [rsp+20h] [rbp-F8h]
  const char *v27; // [rsp+28h] [rbp-F0h]
  unsigned int v28; // [rsp+80h] [rbp-98h] BYREF
  unsigned int cbMultiByte; // [rsp+84h] [rbp-94h] BYREF
  unsigned __int16 *v30; // [rsp+88h] [rbp-90h] BYREF
  char *v31; // [rsp+90h] [rbp-88h] BYREF
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int16 *v33; // [rsp+A0h] [rbp-78h]
  unsigned __int16 *v34; // [rsp+A8h] [rbp-70h]
  unsigned __int16 *v35; // [rsp+B0h] [rbp-68h]
  _OWORD v36[2]; // [rsp+B8h] [rbp-60h] BYREF

  v10 = a3;
  v33 = a3;
  v13 = lpWideCharStr;
  v14 = a5;
  v34 = a5;
  v15 = a6;
  v35 = a6;
  v16 = 0;
  v17 = 0;
  v31 = 0;
  v18 = 0;
  v28 = 0;
  cbMultiByte = 0;
  lpMultiByteStr = 0;
  v30 = 0;
  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  if ( a8 )
  {
    if ( !a4 )
    {
      v20 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          137,
          "CPR(pwszUrlPath)");
      goto LABEL_34;
    }
    if ( !a2 )
    {
      v20 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          0,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
          138,
          "CPR(pwszHost)");
      goto LABEL_34;
    }
    *a8 = 0;
    if ( *((_QWORD *)lpWideCharStr + 2) )
    {
      if ( *((_QWORD *)lpWideCharStr + 3) <= 7u )
        v21 = lpWideCharStr;
      else
        v21 = *(const WCHAR **)lpWideCharStr;
      v20 = MdmConverters::ConvertWideCharToMultiByte(v21, *((_DWORD *)lpWideCharStr + 4), &v31, &v28);
      if ( v20 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_34;
        v27 = "CHR(MdmConverters::ConvertWideCharToMultiByte( wstrBody.c_str(), (DWORD)wstrBody.length(), &pszMultiByteBo"
              "dy, &cbNeededLen))";
        v26 = -107;
        goto LABEL_19;
      }
      v17 = v31;
      v18 = v28;
      v10 = v33;
      v14 = v34;
      v15 = v35;
    }
    if ( *((_QWORD *)lpWideCharStr + 3) > 7u )
      v13 = *(const unsigned __int16 **)lpWideCharStr;
    v20 = MdmHttpRequest::SendHttpRequest(
            this,
            v10,
            L"Content-Type: application/json\r\n",
            a2,
            a4,
            v14,
            v15,
            0,
            0,
            0,
            v13,
            v17,
            v18,
            a8,
            (unsigned int *)((unsigned __int64)&cbMultiByte & ((unsigned __int128)-(__int128)(unsigned __int64)a9 >> 64)),
            (unsigned __int8 **)((unsigned __int64)&lpMultiByteStr & -(__int64)(a9 != 0)));
    if ( v20 >= 0 )
    {
      if ( a9 )
      {
        v20 = MdmConverters::ConvertMultiByteToWideChar(lpMultiByteStr, cbMultiByte, &v30);
        if ( v20 >= 0 )
        {
          *a9 = v30;
          v24 = 0;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v23,
              v22,
              v20,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
              172,
              "CHR(MdmConverters::ConvertMultiByteToWideChar(pbBuffer, cbBuffer, &pwszBuffer))");
          v24 = v30;
        }
        if ( v24 )
          operator delete(v24, v22);
      }
      goto LABEL_34;
    }
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_34;
    v27 = "CHR(SendHttpRequest( pwszMethod, L\"Content-Type: application/json\\r\\n\", pwszHost, pwszUrlPath, pwszMainTic"
          "ket, pwszSecondaryTicket, 0, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fRead"
          "Response ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))";
    v26 = -88;
LABEL_19:
    v19 = v20;
    goto LABEL_4;
  }
  v19 = -2147024809;
  v20 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    v27 = "CPR(pdwHttpStatus)";
    v26 = -120;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v16,
      (_DWORD)a2,
      v19,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      v26,
      v27);
  }
LABEL_34:
  std::wstring::~wstring(v36);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001c8d0  push    rbx
0x18001c8d2  push    rsi
0x18001c8d3  push    rdi
0x18001c8d4  push    r12
0x18001c8d6  push    r13
0x18001c8d8  push    r14
0x18001c8da  push    r15
0x18001c8dc  sub     rsp, 0E0h
0x18001c8e3  mov     rax, cs:__security_cookie
0x18001c8ea  xor     rax, rsp
0x18001c8ed  mov     [rsp+118h+var_40], rax
0x18001c8f5  mov     r12, r9
0x18001c8f8  mov     r10, r8
0x18001c8fb  mov     [rsp+118h+var_78], r8
0x18001c903  mov     r15, rdx
0x18001c906  mov     r13, rcx
0x18001c909  mov     rsi, [rsp+118h+arg_40]
0x18001c911  mov     rdi, [rsp+118h+lpWideCharStr]
0x18001c919  mov     r11, [rsp+118h+arg_20]
0x18001c921  mov     [rsp+118h+var_70], r11
0x18001c929  mov     rbx, [rsp+118h+arg_28]
0x18001c931  mov     [rsp+118h+var_68], rbx
0x18001c939  mov     r14, [rsp+118h+arg_38]
0x18001c941  xor     ecx, ecx
0x18001c943  mov     r8d, ecx
0x18001c946  mov     [rsp+118h+var_88], rcx
0x18001c94e  mov     r9d, ecx
0x18001c951  mov     [rsp+118h+var_98], ecx
0x18001c958  mov     [rsp+118h+cbMultiByte], ecx
0x18001c95f  mov     [rsp+118h+lpMultiByteStr], rcx
0x18001c967  mov     [rsp+118h+var_90], rcx
0x18001c96f  xorps   xmm0, xmm0
0x18001c972  movups  [rsp+118h+var_60], xmm0
0x18001c97a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c982  movdqu  [rsp+118h+var_50], xmm1
0x18001c98b  mov     word ptr [rsp+118h+var_60], cx
0x18001c993  test    r14, r14
0x18001c996  jnz     short loc_18001C9D3
0x18001c998  mov     r8d, 80070057h
0x18001c99e  mov     ebx, r8d
0x18001c9a1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c9a8  jz      loc_18001CBE1
0x18001c9ae  lea     rax, aCprPdwhttpstat; "CPR(pdwHttpStatus)"
0x18001c9b5  mov     [rsp+118h+var_F0], rax
0x18001c9ba  mov     dword ptr [rsp+118h+var_F8], 88h
0x18001c9c2  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001c9c9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c9ce  jmp     loc_18001CBE1
0x18001c9d3  test    r12, r12
0x18001c9d6  jnz     short loc_18001CA04
0x18001c9d8  mov     r8d, 80070057h
0x18001c9de  mov     ebx, r8d
0x18001c9e1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c9e8  jz      loc_18001CBE1
0x18001c9ee  lea     rax, aCprPwszurlpath; "CPR(pwszUrlPath)"
0x18001c9f5  mov     [rsp+118h+var_F0], rax
0x18001c9fa  mov     dword ptr [rsp+118h+var_F8], 89h
0x18001ca02  jmp     short loc_18001C9C2
0x18001ca04  test    r15, r15
0x18001ca07  jnz     short loc_18001CA35
0x18001ca09  mov     r8d, 80070057h
0x18001ca0f  mov     ebx, r8d
0x18001ca12  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ca19  jz      loc_18001CBE1
0x18001ca1f  lea     rax, aCprPwszhost; "CPR(pwszHost)"
0x18001ca26  mov     [rsp+118h+var_F0], rax
0x18001ca2b  mov     dword ptr [rsp+118h+var_F8], 8Ah
0x18001ca33  jmp     short loc_18001C9C2
0x18001ca35  mov     [r14], ecx
0x18001ca38  cmp     [rdi+10h], rcx
0x18001ca3c  jbe     short loc_18001CABC
0x18001ca3e  cmp     qword ptr [rdi+18h], 7
0x18001ca43  jbe     short loc_18001CA4A
0x18001ca45  mov     rcx, [rdi]
0x18001ca48  jmp     short loc_18001CA4D
0x18001ca4a  mov     rcx, rdi; lpWideCharStr
0x18001ca4d  lea     r9, [rsp+118h+var_98]; unsigned int *
0x18001ca55  lea     r8, [rsp+118h+var_88]; char **
0x18001ca5d  mov     edx, [rdi+10h]; cchWideChar
0x18001ca60  call    ?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z; MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)
0x18001ca65  mov     ebx, eax
0x18001ca67  test    eax, eax
0x18001ca69  jns     short loc_18001CA94
0x18001ca6b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ca72  jz      loc_18001CBE1
0x18001ca78  lea     rax, aChrMdmconverte_3; "CHR(MdmConverters::ConvertWideCharToMul"...
0x18001ca7f  mov     [rsp+118h+var_F0], rax
0x18001ca84  mov     dword ptr [rsp+118h+var_F8], 95h
0x18001ca8c  mov     r8d, ebx
0x18001ca8f  jmp     loc_18001C9C2
0x18001ca94  mov     r8, [rsp+118h+var_88]
0x18001ca9c  mov     r9d, [rsp+118h+var_98]
0x18001caa4  mov     r10, [rsp+118h+var_78]
0x18001caac  mov     r11, [rsp+118h+var_70]
0x18001cab4  mov     rbx, [rsp+118h+var_68]
0x18001cabc  mov     rax, rsi
0x18001cabf  neg     rax
0x18001cac2  sbb     rcx, rcx
0x18001cac5  lea     rax, [rsp+118h+lpMultiByteStr]
0x18001cacd  and     rcx, rax
0x18001cad0  mov     rax, rsi
0x18001cad3  neg     rax
0x18001cad6  sbb     rdx, rdx
0x18001cad9  lea     rax, [rsp+118h+cbMultiByte]
0x18001cae1  and     rdx, rax
0x18001cae4  cmp     qword ptr [rdi+18h], 7
0x18001cae9  jbe     short loc_18001CAEE
0x18001caeb  mov     rdi, [rdi]
0x18001caee  mov     [rsp+118h+var_A0], rcx; unsigned __int8 **
0x18001caf3  mov     [rsp+118h+var_A8], rdx; unsigned int *
0x18001caf8  mov     [rsp+118h+var_B0], r14; unsigned int *
0x18001cafd  mov     [rsp+118h+var_B8], r9d; unsigned int
0x18001cb02  mov     [rsp+118h+var_C0], r8; char *
0x18001cb07  mov     [rsp+118h+var_C8], rdi; unsigned __int16 *
0x18001cb0c  xor     edi, edi
0x18001cb0e  mov     [rsp+118h+var_D0], edi; unsigned int
0x18001cb12  mov     [rsp+118h+var_D8], rdi; unsigned __int16 *
0x18001cb17  mov     [rsp+118h+var_E0], edi; int
0x18001cb1b  mov     [rsp+118h+var_E8], rbx; unsigned __int16 *
0x18001cb20  mov     [rsp+118h+var_F0], r11; unsigned __int16 *
0x18001cb25  mov     [rsp+118h+var_F8], r12; unsigned __int16 *
0x18001cb2a  mov     r9, r15; unsigned __int16 *
0x18001cb2d  lea     r8, szHeaders; "Content-Type: application/json\r\n"
0x18001cb34  mov     rdx, r10; unsigned __int16 *
0x18001cb37  mov     rcx, r13; this
0x18001cb3a  call    ?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z; MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)
0x18001cb3f  mov     ebx, eax
0x18001cb41  test    eax, eax
0x18001cb43  jns     short loc_18001CB6B
0x18001cb45  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cb4c  jz      loc_18001CBE1
0x18001cb52  lea     rax, aChrSendhttpreq; "CHR(SendHttpRequest( pwszMethod, L\"Con"...
0x18001cb59  mov     [rsp+118h+var_F0], rax
0x18001cb5e  mov     dword ptr [rsp+118h+var_F8], 0A8h
0x18001cb66  jmp     loc_18001CA8C
0x18001cb6b  test    rsi, rsi
0x18001cb6e  jz      short loc_18001CBE1
0x18001cb70  lea     r8, [rsp+118h+var_90]; unsigned __int16 **
0x18001cb78  mov     edx, [rsp+118h+cbMultiByte]; cbMultiByte
0x18001cb7f  mov     rcx, [rsp+118h+lpMultiByteStr]; lpMultiByteStr
0x18001cb87  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18001cb8c  mov     ebx, eax
0x18001cb8e  test    eax, eax
0x18001cb90  jns     short loc_18001CBC8
0x18001cb92  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cb99  jz      short loc_18001CBBE
0x18001cb9b  lea     rax, aChrMdmconverte_0; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18001cba2  mov     [rsp+118h+var_F0], rax
0x18001cba7  mov     dword ptr [rsp+118h+var_F8], 0ACh
0x18001cbaf  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cbb6  mov     r8d, ebx
0x18001cbb9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cbbe  mov     rcx, [rsp+118h+var_90]
0x18001cbc6  jmp     short loc_18001CBD6
0x18001cbc8  mov     rax, [rsp+118h+var_90]
0x18001cbd0  mov     [rsi], rax
0x18001cbd3  mov     rcx, rdi; void *
0x18001cbd6  test    rcx, rcx
0x18001cbd9  jz      short loc_18001CBE1
0x18001cbdb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cbe0  nop
0x18001cbe1  lea     rcx, [rsp+118h+var_60]
0x18001cbe9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cbee  mov     eax, ebx
0x18001cbf0  jmp     short loc_18001CBF7
0x18001cbf2  mov     eax, 8000FFFFh
0x18001cbf7  mov     rcx, [rsp+118h+var_40]
0x18001cbff  xor     rcx, rsp; StackCookie
0x18001cc02  call    __security_check_cookie
0x18001cc07  add     rsp, 0E0h
0x18001cc0e  pop     r15
0x18001cc10  pop     r14
0x18001cc12  pop     r13
0x18001cc14  pop     r12
0x18001cc16  pop     rdi
0x18001cc17  pop     rsi
0x18001cc18  pop     rbx
0x18001cc19  retn
```
