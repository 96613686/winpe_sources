# MdmHttpRequest::SendRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong *,ushort * *)

- ea: `0x18001c298`
- end: `0x18001c5e3`
- name: `?SendRequest@MdmHttpRequest@@QEAAJPEBG0000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAKPEAPEAG@Z`
- size: `843`
- prototype: `__int64 __fastcall(MdmHttpRequest *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPCWCH lpWideCharStr, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001c5f0`

## callees

- `0x180001520`
- `0x180001544`
- `0x180002de4`
- `0x180006548`
- `0x18001a39c`
- `0x18001a588`
- `0x18001b8b0`
- `0x18001c298`

## string_xrefs

- `0x18001c38a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001c577`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`
- `0x18001c3b6`: `CPR(pwszUrlPath)`
- `0x18001c4f5`: `Content-Type: application/json\n`
- `0x18001c51a`: `CHR(SendHttpRequest( pwszMethod, L"Content-Type: application/json\r\n", pwszHost, pwszUrlPath, pwszMainTicket, pwszSecondaryTicket, 0, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fReadResponse ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))`

## pseudocode

```c
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
  const unsigned __int16 *v14; // r11
  const unsigned __int16 *v15; // rbx
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
      v19 = -2147024809;
      v20 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_33;
      v27 = "CPR(pwszUrlPath)";
      v26 = -119;
      goto LABEL_4;
    }
    if ( !a2 )
    {
      v19 = -2147024809;
      v20 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_33;
      v27 = "CPR(pwszHost)";
      v26 = -118;
      goto LABEL_4;
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
          goto LABEL_33;
        v27 = "CHR(MdmConverters::ConvertWideCharToMultiByte( wstrBody.c_str(), (DWORD)wstrBody.length(), &pszMultiByteBo"
              "dy, &cbNeededLen))";
        v26 = -107;
        goto LABEL_18;
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
              (__int64)"CHR(MdmConverters::ConvertMultiByteToWideChar(pbBuffer, cbBuffer, &pwszBuffer))");
          v24 = v30;
        }
        if ( v24 )
          operator delete(v24, v22);
      }
      goto LABEL_33;
    }
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_33;
    v27 = "CHR(SendHttpRequest( pwszMethod, L\"Content-Type: application/json\\r\\n\", pwszHost, pwszUrlPath, pwszMainTic"
          "ket, pwszSecondaryTicket, 0, nullptr, 0, wstrBody.c_str(), pszMultiByteBody, cbNeededLen, pdwHttpStatus, fRead"
          "Response ? &cbBuffer : nullptr, fReadResponse ? &pbBuffer : nullptr ))";
    v26 = -88;
LABEL_18:
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
      (__int64)v27);
  }
LABEL_33:
  std::wstring::~wstring(v36);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001c298  push    rbx
0x18001c29a  push    rsi
0x18001c29b  push    rdi
0x18001c29c  push    r12
0x18001c29e  push    r13
0x18001c2a0  push    r14
0x18001c2a2  push    r15
0x18001c2a4  sub     rsp, 0E0h
0x18001c2ab  mov     rax, cs:__security_cookie
0x18001c2b2  xor     rax, rsp
0x18001c2b5  mov     [rsp+118h+var_40], rax
0x18001c2bd  mov     r12, r9
0x18001c2c0  mov     r10, r8
0x18001c2c3  mov     [rsp+118h+var_78], r8
0x18001c2cb  mov     r15, rdx
0x18001c2ce  mov     r13, rcx
0x18001c2d1  mov     rsi, [rsp+118h+arg_40]
0x18001c2d9  mov     rdi, [rsp+118h+lpWideCharStr]
0x18001c2e1  mov     r11, [rsp+118h+arg_20]
0x18001c2e9  mov     [rsp+118h+var_70], r11
0x18001c2f1  mov     rbx, [rsp+118h+arg_28]
0x18001c2f9  mov     [rsp+118h+var_68], rbx
0x18001c301  mov     r14, [rsp+118h+arg_38]
0x18001c309  xor     ecx, ecx
0x18001c30b  mov     r8d, ecx
0x18001c30e  mov     [rsp+118h+var_88], rcx
0x18001c316  mov     r9d, ecx
0x18001c319  mov     [rsp+118h+var_98], ecx
0x18001c320  mov     [rsp+118h+cbMultiByte], ecx
0x18001c327  mov     [rsp+118h+lpMultiByteStr], rcx
0x18001c32f  mov     [rsp+118h+var_90], rcx
0x18001c337  xorps   xmm0, xmm0
0x18001c33a  movups  [rsp+118h+var_60], xmm0
0x18001c342  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c34a  movdqu  [rsp+118h+var_50], xmm1
0x18001c353  mov     word ptr [rsp+118h+var_60], cx
0x18001c35b  test    r14, r14
0x18001c35e  jnz     short loc_18001C39B
0x18001c360  mov     r8d, 80070057h
0x18001c366  mov     ebx, r8d
0x18001c369  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c370  jz      loc_18001C5A9
0x18001c376  lea     rax, aCprPdwhttpstat; "CPR(pdwHttpStatus)"
0x18001c37d  mov     [rsp+118h+var_F0], rax
0x18001c382  mov     dword ptr [rsp+118h+var_F8], 88h
0x18001c38a  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001c391  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c396  jmp     loc_18001C5A9
0x18001c39b  test    r12, r12
0x18001c39e  jnz     short loc_18001C3CC
0x18001c3a0  mov     r8d, 80070057h
0x18001c3a6  mov     ebx, r8d
0x18001c3a9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c3b0  jz      loc_18001C5A9
0x18001c3b6  lea     rax, aCprPwszurlpath; "CPR(pwszUrlPath)"
0x18001c3bd  mov     [rsp+118h+var_F0], rax
0x18001c3c2  mov     dword ptr [rsp+118h+var_F8], 89h
0x18001c3ca  jmp     short loc_18001C38A
0x18001c3cc  test    r15, r15
0x18001c3cf  jnz     short loc_18001C3FD
0x18001c3d1  mov     r8d, 80070057h
0x18001c3d7  mov     ebx, r8d
0x18001c3da  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c3e1  jz      loc_18001C5A9
0x18001c3e7  lea     rax, aCprPwszhost; "CPR(pwszHost)"
0x18001c3ee  mov     [rsp+118h+var_F0], rax
0x18001c3f3  mov     dword ptr [rsp+118h+var_F8], 8Ah
0x18001c3fb  jmp     short loc_18001C38A
0x18001c3fd  mov     [r14], ecx
0x18001c400  cmp     [rdi+10h], rcx
0x18001c404  jbe     short loc_18001C484
0x18001c406  cmp     qword ptr [rdi+18h], 7
0x18001c40b  jbe     short loc_18001C412
0x18001c40d  mov     rcx, [rdi]
0x18001c410  jmp     short loc_18001C415
0x18001c412  mov     rcx, rdi; lpWideCharStr
0x18001c415  lea     r9, [rsp+118h+var_98]; unsigned int *
0x18001c41d  lea     r8, [rsp+118h+var_88]; char **
0x18001c425  mov     edx, [rdi+10h]; cchWideChar
0x18001c428  call    ?ConvertWideCharToMultiByte@MdmConverters@@SAJPEBGKPEAPEADPEAK@Z; MdmConverters::ConvertWideCharToMultiByte(ushort const *,ulong,char * *,ulong *)
0x18001c42d  mov     ebx, eax
0x18001c42f  test    eax, eax
0x18001c431  jns     short loc_18001C45C
0x18001c433  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c43a  jz      loc_18001C5A9
0x18001c440  lea     rax, aChrMdmconverte_3; "CHR(MdmConverters::ConvertWideCharToMul"...
0x18001c447  mov     [rsp+118h+var_F0], rax
0x18001c44c  mov     dword ptr [rsp+118h+var_F8], 95h
0x18001c454  mov     r8d, ebx
0x18001c457  jmp     loc_18001C38A
0x18001c45c  mov     r8, [rsp+118h+var_88]
0x18001c464  mov     r9d, [rsp+118h+var_98]
0x18001c46c  mov     r10, [rsp+118h+var_78]
0x18001c474  mov     r11, [rsp+118h+var_70]
0x18001c47c  mov     rbx, [rsp+118h+var_68]
0x18001c484  mov     rax, rsi
0x18001c487  neg     rax
0x18001c48a  sbb     rcx, rcx
0x18001c48d  lea     rax, [rsp+118h+lpMultiByteStr]
0x18001c495  and     rcx, rax
0x18001c498  mov     rax, rsi
0x18001c49b  neg     rax
0x18001c49e  sbb     rdx, rdx
0x18001c4a1  lea     rax, [rsp+118h+cbMultiByte]
0x18001c4a9  and     rdx, rax
0x18001c4ac  cmp     qword ptr [rdi+18h], 7
0x18001c4b1  jbe     short loc_18001C4B6
0x18001c4b3  mov     rdi, [rdi]
0x18001c4b6  mov     [rsp+118h+var_A0], rcx; unsigned __int8 **
0x18001c4bb  mov     [rsp+118h+var_A8], rdx; unsigned int *
0x18001c4c0  mov     [rsp+118h+var_B0], r14; unsigned int *
0x18001c4c5  mov     [rsp+118h+var_B8], r9d; unsigned int
0x18001c4ca  mov     [rsp+118h+var_C0], r8; char *
0x18001c4cf  mov     [rsp+118h+var_C8], rdi; unsigned __int16 *
0x18001c4d4  xor     edi, edi
0x18001c4d6  mov     [rsp+118h+var_D0], edi; unsigned int
0x18001c4da  mov     [rsp+118h+var_D8], rdi; unsigned __int16 *
0x18001c4df  mov     [rsp+118h+var_E0], edi; int
0x18001c4e3  mov     [rsp+118h+var_E8], rbx; unsigned __int16 *
0x18001c4e8  mov     [rsp+118h+var_F0], r11; unsigned __int16 *
0x18001c4ed  mov     [rsp+118h+var_F8], r12; unsigned __int16 *
0x18001c4f2  mov     r9, r15; unsigned __int16 *
0x18001c4f5  lea     r8, szHeaders; "Content-Type: application/json\r\n"
0x18001c4fc  mov     rdx, r10; unsigned __int16 *
0x18001c4ff  mov     rcx, r13; this
0x18001c502  call    ?SendHttpRequest@MdmHttpRequest@@AEAAJPEBGQEBG0000H0K0PEADKPEAK3PEAPEAE@Z; MdmHttpRequest::SendHttpRequest(ushort const *,ushort const * const,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ushort const *,char *,ulong,ulong *,ulong *,uchar * *)
0x18001c507  mov     ebx, eax
0x18001c509  test    eax, eax
0x18001c50b  jns     short loc_18001C533
0x18001c50d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c514  jz      loc_18001C5A9
0x18001c51a  lea     rax, aChrSendhttpreq; "CHR(SendHttpRequest( pwszMethod, L\"Con"...
0x18001c521  mov     [rsp+118h+var_F0], rax
0x18001c526  mov     dword ptr [rsp+118h+var_F8], 0A8h
0x18001c52e  jmp     loc_18001C454
0x18001c533  test    rsi, rsi
0x18001c536  jz      short loc_18001C5A9
0x18001c538  lea     r8, [rsp+118h+var_90]; unsigned __int16 **
0x18001c540  mov     edx, [rsp+118h+cbMultiByte]; cbMultiByte
0x18001c547  mov     rcx, [rsp+118h+lpMultiByteStr]; lpMultiByteStr
0x18001c54f  call    ?ConvertMultiByteToWideChar@MdmConverters@@SAJPEAEKPEAPEAG@Z; MdmConverters::ConvertMultiByteToWideChar(uchar *,ulong,ushort * *)
0x18001c554  mov     ebx, eax
0x18001c556  test    eax, eax
0x18001c558  jns     short loc_18001C590
0x18001c55a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001c561  jz      short loc_18001C586
0x18001c563  lea     rax, aChrMdmconverte_0; "CHR(MdmConverters::ConvertMultiByteToWi"...
0x18001c56a  mov     [rsp+118h+var_F0], rax
0x18001c56f  mov     dword ptr [rsp+118h+var_F8], 0ACh
0x18001c577  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001c57e  mov     r8d, ebx
0x18001c581  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c586  mov     rcx, [rsp+118h+var_90]
0x18001c58e  jmp     short loc_18001C59E
0x18001c590  mov     rax, [rsp+118h+var_90]
0x18001c598  mov     [rsi], rax
0x18001c59b  mov     rcx, rdi; void *
0x18001c59e  test    rcx, rcx
0x18001c5a1  jz      short loc_18001C5A9
0x18001c5a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c5a8  nop
0x18001c5a9  lea     rcx, [rsp+118h+var_60]
0x18001c5b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c5b6  mov     eax, ebx
0x18001c5b8  jmp     short loc_18001C5BF
0x18001c5ba  mov     eax, 8000FFFFh
0x18001c5bf  mov     rcx, [rsp+118h+var_40]
0x18001c5c7  xor     rcx, rsp; StackCookie
0x18001c5ca  call    __security_check_cookie
0x18001c5cf  add     rsp, 0E0h
0x18001c5d6  pop     r15
0x18001c5d8  pop     r14
0x18001c5da  pop     r13
0x18001c5dc  pop     r12
0x18001c5de  pop     rdi
0x18001c5df  pop     rsi
0x18001c5e0  pop     rbx
0x18001c5e1  retn
```
