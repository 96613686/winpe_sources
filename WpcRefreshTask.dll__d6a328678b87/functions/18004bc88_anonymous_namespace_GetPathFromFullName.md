# _anonymous_namespace_::GetPathFromFullName

- ea: `0x18004bc88`
- end: `0x18004c233`
- name: `_anonymous_namespace_::GetPathFromFullName`
- size: `1451`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18004c4b0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180009a80`
- `0x18000e93c`
- `0x18000ecc0`
- `0x1800173e4`
- `0x180034548`
- `0x180035084`
- `0x180035af4`
- `0x180035e0c`
- `0x180037820`
- `0x180048df8`
- `0x180048eac`
- `0x18004b938`
- `0x18004bc88`
- `0x1800591d4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004be92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004be92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004be7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004be7a`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x18004bd67`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x18004bdce`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x18004bd67`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x18004bdce`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x18004bcea`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x18004bd2e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x18004bcea`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x18004bd2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall anonymous_namespace_::GetPathFromFullName(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r14
  const WCHAR *v5; // rcx
  LONG v6; // eax
  unsigned int v7; // edi
  const WCHAR *v8; // rcx
  LONG v9; // eax
  signed int v10; // edi
  const PACKAGE_ID *v11; // r12
  LONG PackagePath; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  WCHAR *v15; // r9
  int v16; // edi
  bool v17; // sf
  __int64 result; // rax
  int v19; // edi
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // r14
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rdi
  _QWORD *v24; // rax
  int v25; // esi
  __int64 FullNameAndPath; // rax
  _OWORD *v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // r10
  int v32; // eax
  __int64 v33; // r10
  int v34; // eax
  __int64 v35; // r10
  int v36; // eax
  __int64 v37; // r10
  int v38; // eax
  __int64 v39; // r10
  UINT32 bufferLength; // [rsp+30h] [rbp-1E8h] BYREF
  UINT32 pathLength; // [rsp+34h] [rbp-1E4h] BYREF
  __int64 v42; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v43; // [rsp+40h] [rbp-1D8h] BYREF
  const WCHAR *v44; // [rsp+48h] [rbp-1D0h] BYREF
  const WCHAR *v45; // [rsp+50h] [rbp-1C8h]
  _QWORD *v46; // [rsp+60h] [rbp-1B8h]
  _OWORD *v47; // [rsp+68h] [rbp-1B0h]
  _OWORD v48[2]; // [rsp+70h] [rbp-1A8h] BYREF
  BYTE *buffer[3]; // [rsp+90h] [rbp-188h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+A8h] [rbp-170h] BYREF
  _BYTE v51[40]; // [rsp+D0h] [rbp-148h] BYREF
  _BYTE v52[40]; // [rsp+F8h] [rbp-120h] BYREF
  _BYTE v53[40]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v54[40]; // [rsp+148h] [rbp-D0h] BYREF
  _BYTE v55[48]; // [rsp+170h] [rbp-A8h] BYREF
  _OWORD hstringHeader[2]; // [rsp+1A0h] [rbp-78h] BYREF
  char *v57; // [rsp+1C0h] [rbp-58h] BYREF

  v44 = (const WCHAR *)a2;
  v47 = (_OWORD *)a1;
  v45 = (const WCHAR *)a2;
  bufferLength = 0;
  v4 = (_QWORD *)(a2 + 24);
  v46 = (_QWORD *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  v6 = PackageIdFromFullName(v5, 0, &bufferLength, 0);
  try
  {
    v7 = v6;
    if ( v6 && v6 != 122 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v30 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v31 + 16), 17, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v30, v7);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::vector<unsigned char>::vector<unsigned char>(buffer, bufferLength);
    if ( *v4 <= 7u )
      v8 = (const WCHAR *)a2;
    else
      v8 = *(const WCHAR **)a2;
    v9 = PackageIdFromFullName(v8, 0, &bufferLength, buffer[0]);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v32 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v33 + 16), 18, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v32, v10);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v51, v10);
      throw (ErrorCodeException *)v51;
    }
    v11 = (const PACKAGE_ID *)buffer[0];
    pathLength = 0;
    PackagePath = GetPackagePath((const PACKAGE_ID *)buffer[0], 0, &pathLength, 0);
    v13 = PackagePath;
    if ( PackagePath && PackagePath != 122 )
    {
      if ( PackagePath > 0 )
        v13 = (unsigned __int16)PackagePath | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v34 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v35 + 16), 19, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v34, v13);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v52, v13);
      throw (ErrorCodeException *)v52;
    }
    hstringHeader[0] = 0;
    hstringHeader[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(hstringHeader[0]) = 0;
    v14 = StringAlgo::GetBuffer<unsigned short>(v48, hstringHeader, pathLength);
    v15 = *(WCHAR **)v14;
    if ( *(_QWORD *)(*(_QWORD *)v14 + 24LL) > 7u )
      v15 = *(WCHAR **)v15;
    v16 = GetPackagePath(v11, 0, &pathLength, v15);
    Private::Buffer<unsigned short>::~Buffer<unsigned short>(v48);
    v17 = v16 < 0;
    if ( v16 > 0 )
    {
      v16 = (unsigned __int16)v16 | 0x80070000;
      v17 = v16 < 0;
    }
    if ( v17 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v36 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v37 + 16), 20, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v36, v16);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v53, v16);
      throw (ErrorCodeException *)v53;
    }
    v48[0] = hstringHeader[0];
    v48[1] = hstringHeader[1];
    hstringHeader[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(hstringHeader[0]) = 0;
    IO::Path::Path(a1, (__int64)v48);
    std::wstring::~wstring((char **)hstringHeader);
    std::vector<char>::~vector<char>((char **)buffer);
    result = a1;
  }
  catch ( std::exception )
  {
    v43 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Management.Deployment.PackageManager",
           0x2Cu,
           (HSTRING_HEADER *)((char *)hstringHeader + 8),
           (HSTRING *)hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v19 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
            *(__int64 *)&hstringHeader[0],
            &v43);
    if ( v19 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          21,
          WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
          (unsigned int)v19);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v54, v19);
      throw (ErrorCodeException *)v54;
    }
    v42 = 0;
    v20 = v43;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 136LL);
    if ( *v46 <= 7u )
    {
      v23 = v45;
      v22 = v45;
    }
    else
    {
      v22 = *(const WCHAR **)v44;
      v23 = v44;
    }
    v44 = v22;
    v24 = (_QWORD *)Windows::Internal::StringReference::StringReference((__int64)hstringHeader, &v44);
    v25 = v21(v20, *v24, &v42);
    if ( v25 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v38 = std::wstring::c_str(v23);
        WPP_SF_Sd(*(_QWORD *)(v39 + 16), 22, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v38, v25);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v55, v25);
      throw (ErrorCodeException *)v55;
    }
    FullNameAndPath = anonymous_namespace_::GetFullNameAndPath(hstringHeader, v42);
    v27 = v47;
    *v47 = 0;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 3) = 0;
    *v27 = *(_OWORD *)(FullNameAndPath + 32);
    v27[1] = *(_OWORD *)(FullNameAndPath + 48);
    *(_QWORD *)(FullNameAndPath + 48) = 0;
    *(_QWORD *)(FullNameAndPath + 56) = 7;
    *(_WORD *)(FullNameAndPath + 32) = 0;
    std::wstring::~wstring(&v57);
    std::wstring::~wstring((char **)hstringHeader);
    v28 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    return (__int64)v27;
  }
  return result;
}

```

## disassembly

```asm
0x18004bc88  mov     [rsp+arg_10], rbx
0x18004bc8d  push    rsi
0x18004bc8e  push    rdi
0x18004bc8f  push    r12
0x18004bc91  push    r14
0x18004bc93  push    r15
0x18004bc95  sub     rsp, 1F0h
0x18004bc9c  mov     rax, cs:__security_cookie
0x18004bca3  xor     rax, rsp
0x18004bca6  mov     [rsp+218h+var_38], rax
0x18004bcae  mov     rsi, rdx
0x18004bcb1  mov     r15, rcx
0x18004bcb4  mov     [rsp+218h+var_1D0], rdx
0x18004bcb9  mov     [rsp+218h+var_1B0], rcx
0x18004bcbe  mov     [rsp+218h+var_1C8], rdx
0x18004bcc3  xor     ebx, ebx
0x18004bcc5  mov     [rsp+218h+bufferLength], ebx
0x18004bcc9  lea     r14, [rdx+18h]
0x18004bccd  mov     [rsp+218h+var_1B8], r14
0x18004bcd2  cmp     qword ptr [r14], 7
0x18004bcd6  jbe     short loc_18004BCDD
0x18004bcd8  mov     rcx, [rdx]
0x18004bcdb  jmp     short loc_18004BCE0
0x18004bcdd  mov     rcx, rsi; packageFullName
0x18004bce0  xor     r9d, r9d; buffer
0x18004bce3  lea     r8, [rsp+218h+bufferLength]; bufferLength
0x18004bce8  xor     edx, edx; flags
0x18004bcea  call    cs:__imp_PackageIdFromFullName
0x18004bcf0  mov     edi, eax
0x18004bcf2  test    eax, eax
0x18004bcf4  jz      short loc_18004BCFF
0x18004bcf6  cmp     eax, 7Ah ; 'z'
0x18004bcf9  jnz     loc_18004BFDE
0x18004bcff  mov     edx, [rsp+218h+bufferLength]
0x18004bd03  lea     rcx, [rsp+218h+buffer]
0x18004bd0b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18004bd10  nop
0x18004bd11  cmp     qword ptr [r14], 7
0x18004bd15  jbe     short loc_18004BD1C
0x18004bd17  mov     rcx, [rsi]
0x18004bd1a  jmp     short loc_18004BD1F
0x18004bd1c  mov     rcx, rsi; packageFullName
0x18004bd1f  mov     r9, [rsp+218h+buffer]; buffer
0x18004bd27  lea     r8, [rsp+218h+bufferLength]; bufferLength
0x18004bd2c  xor     edx, edx; flags
0x18004bd2e  call    cs:__imp_PackageIdFromFullName
0x18004bd34  mov     edi, eax
0x18004bd36  mov     r14d, 80070000h
0x18004bd3c  test    eax, eax
0x18004bd3e  jle     short loc_18004BD46
0x18004bd40  movzx   edi, ax
0x18004bd43  or      edi, r14d
0x18004bd46  test    edi, edi
0x18004bd48  js      loc_18004C04D
0x18004bd4e  mov     r12, [rsp+218h+buffer]
0x18004bd56  mov     [rsp+218h+pathLength], ebx
0x18004bd5a  xor     r9d, r9d; path
0x18004bd5d  lea     r8, [rsp+218h+pathLength]; pathLength
0x18004bd62  xor     edx, edx; reserved
0x18004bd64  mov     rcx, r12; packageId
0x18004bd67  call    cs:__imp_GetPackagePath
0x18004bd6d  mov     edi, eax
0x18004bd6f  test    eax, eax
0x18004bd71  jz      short loc_18004BD7C
0x18004bd73  cmp     eax, 7Ah ; 'z'
0x18004bd76  jnz     loc_18004C0AE
0x18004bd7c  xorps   xmm0, xmm0
0x18004bd7f  movups  xmmword ptr [rsp+218h+hstringHeader], xmm0
0x18004bd87  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004bd8f  movdqu  xmmword ptr [rsp+218h+hstringHeader+10h], xmm1
0x18004bd98  mov     word ptr [rsp+218h+hstringHeader], bx
0x18004bda0  mov     r8d, [rsp+218h+pathLength]
0x18004bda5  lea     rdx, [rsp+218h+hstringHeader]
0x18004bdad  lea     rcx, [rsp+218h+var_1A8]
0x18004bdb2  call    ??$GetBuffer@G@StringAlgo@@YA?AV?$Buffer@G@Private@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K_N@Z; StringAlgo::GetBuffer<ushort>(std::wstring &,unsigned __int64,bool)
0x18004bdb7  mov     r9, [rax]
0x18004bdba  cmp     qword ptr [r9+18h], 7
0x18004bdbf  jbe     short loc_18004BDC4
0x18004bdc1  mov     r9, [r9]; path
0x18004bdc4  lea     r8, [rsp+218h+pathLength]; pathLength
0x18004bdc9  xor     edx, edx; reserved
0x18004bdcb  mov     rcx, r12; packageId
0x18004bdce  call    cs:__imp_GetPackagePath
0x18004bdd4  mov     edi, eax
0x18004bdd6  lea     rcx, [rsp+218h+var_1A8]
0x18004bddb  call    ??1?$Buffer@G@Private@@QEAA@XZ; Private::Buffer<ushort>::~Buffer<ushort>(void)
0x18004bde0  test    edi, edi
0x18004bde2  jle     short loc_18004BDEC
0x18004bde4  movzx   edi, di
0x18004bde7  or      edi, r14d
0x18004bdea  test    edi, edi
0x18004bdec  js      loc_18004C11A
0x18004bdf2  movups  xmm0, xmmword ptr [rsp+218h+hstringHeader]
0x18004bdfa  movups  [rsp+218h+var_1A8], xmm0
0x18004bdff  movups  xmm1, xmmword ptr [rsp+218h+hstringHeader+10h]
0x18004be07  movups  [rsp+218h+var_198], xmm1
0x18004be0f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18004be17  movdqu  xmmword ptr [rsp+218h+hstringHeader+10h], xmm0
0x18004be20  mov     word ptr [rsp+218h+hstringHeader], bx
0x18004be28  lea     rdx, [rsp+218h+var_1A8]
0x18004be2d  mov     rcx, r15
0x18004be30  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x18004be35  nop
0x18004be36  lea     rcx, [rsp+218h+hstringHeader]
0x18004be3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004be43  nop
0x18004be44  lea     rcx, [rsp+218h+buffer]
0x18004be4c  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18004be51  mov     rax, r15
0x18004be54  jmp     loc_18004BFB6
0x18004be59  xor     ebx, ebx
0x18004be5b  mov     [rsp+218h+var_1D8], rbx
0x18004be60  lea     r9, [rsp+218h+hstringHeader]; string
0x18004be68  lea     r8, [rsp+218h+hstringHeader+8]; hstringHeader
0x18004be70  lea     edx, [rbx+2Ch]; length
0x18004be73  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18004be7a  call    cs:__imp_WindowsCreateStringReference
0x18004be80  test    eax, eax
0x18004be82  jns     short loc_18004BE98
0x18004be84  xor     r9d, r9d; lpArguments
0x18004be87  xor     r8d, r8d; nNumberOfArguments
0x18004be8a  lea     edx, [rbx+1]; dwExceptionFlags
0x18004be8d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004be92  call    cs:__imp_RaiseException
0x18004be98  lea     rdx, [rsp+218h+var_1D8]
0x18004be9d  mov     rcx, qword ptr [rsp+218h+hstringHeader]
0x18004bea5  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x18004beaa  mov     edi, eax
0x18004beac  test    eax, eax
0x18004beae  js      loc_18004C17C
0x18004beb4  mov     [rsp+218h+var_1E0], rbx
0x18004beb9  mov     rsi, [rsp+218h+var_1D8]
0x18004bebe  mov     rax, [rsi]
0x18004bec1  mov     r14, [rax+88h]
0x18004bec8  mov     rax, [rsp+218h+var_1B8]
0x18004becd  cmp     qword ptr [rax], 7
0x18004bed1  jbe     short loc_18004BEE0
0x18004bed3  mov     rax, [rsp+218h+var_1D0]
0x18004bed8  mov     rcx, [rax]
0x18004bedb  mov     rdi, rax
0x18004bede  jmp     short loc_18004BEE8
0x18004bee0  mov     rdi, [rsp+218h+var_1C8]
0x18004bee5  mov     rcx, rdi
0x18004bee8  mov     [rsp+218h+var_1D0], rcx
0x18004beed  lea     rdx, [rsp+218h+var_1D0]
0x18004bef2  lea     rcx, [rsp+218h+hstringHeader]
0x18004befa  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18004beff  lea     r8, [rsp+218h+var_1E0]
0x18004bf04  mov     rdx, [rax]
0x18004bf07  mov     rcx, rsi
0x18004bf0a  mov     rax, r14
0x18004bf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf12  mov     esi, eax
0x18004bf14  test    eax, eax
0x18004bf16  js      loc_18004C1D1
0x18004bf1c  mov     rdx, [rsp+218h+var_1E0]
0x18004bf21  lea     rcx, [rsp+218h+hstringHeader]
0x18004bf29  call    _anonymous_namespace___GetFullNameAndPath
0x18004bf2e  xorps   xmm0, xmm0
0x18004bf31  mov     rdi, [rsp+218h+var_1B0]
0x18004bf36  movups  xmmword ptr [rdi], xmm0
0x18004bf39  mov     [rdi+10h], rbx
0x18004bf3d  mov     [rdi+18h], rbx
0x18004bf41  movups  xmm0, xmmword ptr [rax+20h]
0x18004bf45  movups  xmmword ptr [rdi], xmm0
0x18004bf48  movups  xmm1, xmmword ptr [rax+30h]
0x18004bf4c  movups  xmmword ptr [rdi+10h], xmm1
0x18004bf50  mov     [rax+30h], rbx
0x18004bf54  mov     qword ptr [rax+38h], 7
0x18004bf5c  mov     [rax+20h], bx
0x18004bf60  lea     rcx, [rsp+218h+var_58]
0x18004bf68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004bf6d  lea     rcx, [rsp+218h+hstringHeader]
0x18004bf75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004bf7a  nop
0x18004bf7b  mov     rcx, [rsp+218h+var_1E0]
0x18004bf80  test    rcx, rcx
0x18004bf83  jz      short loc_18004BF97
0x18004bf85  mov     [rsp+218h+var_1E0], rbx
0x18004bf8a  mov     rax, [rcx]
0x18004bf8d  mov     rax, [rax+10h]
0x18004bf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf96  nop
0x18004bf97  mov     rcx, [rsp+218h+var_1D8]
0x18004bf9c  test    rcx, rcx
0x18004bf9f  jz      short loc_18004BFB3
0x18004bfa1  mov     [rsp+218h+var_1D8], rbx
0x18004bfa6  mov     rdx, [rcx]
0x18004bfa9  mov     rax, [rdx+10h]
0x18004bfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfb2  nop
0x18004bfb3  mov     rax, rdi
0x18004bfb6  mov     rcx, [rsp+218h+var_38]
0x18004bfbe  xor     rcx, rsp; StackCookie
0x18004bfc1  call    __security_check_cookie
0x18004bfc6  mov     rbx, [rsp+218h+arg_10]
0x18004bfce  add     rsp, 1F0h
0x18004bfd5  pop     r15
0x18004bfd7  pop     r14
0x18004bfd9  pop     r12
0x18004bfdb  pop     rdi
0x18004bfdc  pop     rsi
0x18004bfdd  retn
0x18004bfde  test    eax, eax
0x18004bfe0  jle     short loc_18004BFEB
0x18004bfe2  movzx   edi, ax
0x18004bfe5  or      edi, 80070000h
0x18004bfeb  lea     rax, WPP_GLOBAL_Control
0x18004bff2  mov     r10, cs:WPP_GLOBAL_Control
0x18004bff9  cmp     r10, rax
0x18004bffc  jz      short loc_18004C029
0x18004bffe  test    byte ptr [r10+1Ch], 1
0x18004c003  jz      short loc_18004C029
0x18004c005  mov     rcx, rsi
0x18004c008  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004c00d  mov     edx, 11h
0x18004c012  mov     [rsp+218h+var_1F8], edi
0x18004c016  mov     r9, rax
0x18004c019  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004c020  mov     rcx, [r10+10h]
0x18004c024  call    WPP_SF_Sd
0x18004c029  mov     edx, edi; int
0x18004c02b  lea     rcx, [rsp+218h+pExceptionObject]; this
0x18004c033  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004c038  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004c03f  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x18004c047  call    _CxxThrowException_0
0x18004c04d  lea     rax, WPP_GLOBAL_Control
0x18004c054  mov     r10, cs:WPP_GLOBAL_Control
0x18004c05b  cmp     r10, rax
0x18004c05e  jz      short loc_18004C08B
0x18004c060  test    byte ptr [r10+1Ch], 1
0x18004c065  jz      short loc_18004C08B
0x18004c067  mov     rcx, rsi
0x18004c06a  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004c06f  mov     edx, 12h
0x18004c074  mov     [rsp+218h+var_1F8], edi
0x18004c078  mov     r9, rax
0x18004c07b  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004c082  mov     rcx, [r10+10h]
0x18004c086  call    WPP_SF_Sd
0x18004c08b  mov     edx, edi; int
0x18004c08d  lea     rcx, [rsp+218h+var_148]; this
0x18004c095  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004c09a  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004c0a1  lea     rcx, [rsp+218h+var_148]; pExceptionObject
0x18004c0a9  call    _CxxThrowException_0
0x18004c0ae  test    eax, eax
0x18004c0b0  jle     short loc_18004C0B8
0x18004c0b2  movzx   edi, ax
0x18004c0b5  or      edi, r14d
0x18004c0b8  lea     rax, WPP_GLOBAL_Control
0x18004c0bf  mov     r10, cs:WPP_GLOBAL_Control
0x18004c0c6  cmp     r10, rax
0x18004c0c9  jz      short loc_18004C0F6
0x18004c0cb  test    byte ptr [r10+1Ch], 1
0x18004c0d0  jz      short loc_18004C0F6
0x18004c0d2  mov     rcx, rsi
0x18004c0d5  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004c0da  mov     edx, 13h
0x18004c0df  mov     [rsp+218h+var_1F8], edi
0x18004c0e3  mov     r9, rax
0x18004c0e6  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004c0ed  mov     rcx, [r10+10h]
0x18004c0f1  call    WPP_SF_Sd
0x18004c0f6  mov     edx, edi; int
0x18004c0f8  lea     rcx, [rsp+218h+var_120]; this
0x18004c100  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004c105  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004c10c  lea     rcx, [rsp+218h+var_120]; pExceptionObject
0x18004c114  call    _CxxThrowException_0
0x18004c11a  lea     rax, WPP_GLOBAL_Control
0x18004c121  mov     r10, cs:WPP_GLOBAL_Control
0x18004c128  cmp     r10, rax
0x18004c12b  jz      short loc_18004C158
0x18004c12d  test    byte ptr [r10+1Ch], 1
0x18004c132  jz      short loc_18004C158
0x18004c134  mov     rcx, rsi
0x18004c137  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004c13c  mov     edx, 14h
0x18004c141  mov     [rsp+218h+var_1F8], edi
0x18004c145  mov     r9, rax
0x18004c148  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x18004c14f  mov     rcx, [r10+10h]
0x18004c153  call    WPP_SF_Sd
0x18004c158  mov     edx, edi; int
0x18004c15a  lea     rcx, [rsp+218h+var_F8]; this
0x18004c162  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18004c167  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18004c16e  lea     rcx, [rsp+218h+var_F8]; pExceptionObject
0x18004c176  call    _CxxThrowException_0
0x18004c17c  lea     rax, WPP_GLOBAL_Control
0x18004c183  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c18a  cmp     rcx, rax
0x18004c18d  jz      short loc_18004C1AD
0x18004c18f  test    byte ptr [rcx+1Ch], 1
0x18004c193  jz      short loc_18004C1AD
0x18004c195  mov     edx, 15h
0x18004c19a  mov     r9d, edi
0x18004c19d  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
  ... truncated ...
```
