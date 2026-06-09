# FaceDetectionMFT::RuntimeClassInitialize(void)

- ea: `0x18001937c`
- end: `0x1800195b4`
- name: `?RuntimeClassInitialize@FaceDetectionMFT@@QEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007df4`
- `0x180007eac`

## callees

- `0x180002420`
- `0x18000b480`
- `0x18000b490`
- `0x18000c0f8`
- `0x18000c1d8`
- `0x18000c414`
- `0x18000c838`
- `0x18001937c`
- `0x1801332b4`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019409`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019409`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800193f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800193f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019541`
- `MFPlat!MFTEnum2` at `0x1800194db`
- `MFPlat!MFTEnum2` at `0x1800194db`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::RuntimeClassInitialize(FaceDetectionMFT *this)
{
  int v2; // edi
  __int64 v3; // rdx
  const unsigned __int16 *v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  unsigned int v7; // eax
  __int64 i; // rsi
  __int64 v9; // rdx
  unsigned __int8 v10; // cl
  _BYTE v12[4]; // [rsp+40h] [rbp-9h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-5h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-1h] BYREF
  GUID v15; // [rsp+50h] [rbp+7h] BYREF
  _OWORD hstringHeader[2]; // [rsp+60h] [rbp+17h] BYREF

  v12[0] = 0;
  v2 = CCoreMFT::InitializeBase(this);
  if ( v2 >= 0 )
  {
    if ( WindowsCreateStringReference(
           L"Windows.Media.FaceAnalysis.Internal.DetectedFaceFactory",
           0x37u,
           (HSTRING_HEADER *)((char *)hstringHeader + 8),
           (HSTRING *)hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::Internal::IDetectedFaceFactory>>(
           *(_QWORD *)&hstringHeader[0],
           (char *)this + 648);
    if ( v2 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return (unsigned int)v2;
      v3 = 15;
      goto LABEL_4;
    }
    v5 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                     (HSTRING *)hstringHeader,
                     (const unsigned __int16 (*)[39])v4);
    if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTrackerStatics>>(
                *v5,
                (char *)this + 17440) < 0
      || (*(int (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 2180) + 72LL))(*((_QWORD *)this + 2180), v12) < 0
      || !v12[0] )
    {
      *((_BYTE *)this + 544) = 0;
    }
    pv = 0;
    v13 = 0;
    hstringHeader[0] = MFMediaType_Video;
    hstringHeader[1] = MFVideoFormat_MJPG;
    v15 = MFT_CATEGORY_VIDEO_DECODER;
    v2 = MFTEnum2(&v15, 268435527, hstringHeader, 0, 0, &pv, &v13);
    if ( v2 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return (unsigned int)v2;
      v3 = 16;
      goto LABEL_4;
    }
    v6 = pv;
    if ( pv )
    {
      v7 = v13;
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        v9 = v6[i];
        if ( v9 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 16LL))(v6[i]);
          *((_QWORD *)pv + i) = 0;
          v6 = pv;
          v7 = v13;
        }
      }
      CoTaskMemFree(v6);
      pv = 0;
    }
    *((_BYTE *)this + 568) = v13 != 0;
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v10);
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v3 = 14;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001937c  mov     [rsp-8+arg_8], rbx
0x180019381  mov     [rsp-8+arg_10], rsi
0x180019386  push    rbp
0x180019387  push    rdi
0x180019388  push    r14
0x18001938a  lea     rbp, [rsp-47h]
0x18001938f  sub     rsp, 90h
0x180019396  mov     rax, cs:__security_cookie
0x18001939d  xor     rax, rsp
0x1800193a0  mov     [rbp+57h+var_20], rax
0x1800193a4  mov     rbx, rcx
0x1800193a7  mov     [rbp+57h+var_60], 0
0x1800193ab  call    ?InitializeBase@CCoreMFT@@IEAAJXZ; CCoreMFT::InitializeBase(void)
0x1800193b0  mov     edi, eax
0x1800193b2  test    eax, eax
0x1800193b4  jns     short loc_1800193DC
0x1800193b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800193bb  cmp     al, 1
0x1800193bd  jb      loc_18001958E
0x1800193c3  mov     edx, 0Eh
0x1800193c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193cf  mov     dword ptr [rsp+0A0h+var_80], edi
0x1800193d3  mov     rcx, [rcx+10h]
0x1800193d7  jmp     loc_18001957F
0x1800193dc  lea     r9, [rbp+57h+hstringHeader]; string
0x1800193e0  mov     edx, 37h ; '7'; length
0x1800193e5  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x1800193e9  lea     rcx, ?RuntimeClass_Windows_Media_FaceAnalysis_Internal_DetectedFaceFactory@@3QBGB; "Windows.Media.FaceAnalysis.Internal.Det"...
0x1800193f0  call    cs:__imp_WindowsCreateStringReference
0x1800193f6  test    eax, eax
0x1800193f8  jns     short loc_18001940F
0x1800193fa  xor     r9d, r9d; lpArguments
0x1800193fd  xor     r8d, r8d; nNumberOfArguments
0x180019400  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019405  lea     edx, [r9+1]; dwExceptionFlags
0x180019409  call    cs:__imp_RaiseException
0x18001940f  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180019413  lea     rdx, [rbx+288h]
0x18001941a  call    ??$ActivateInstance@V?$ComPtr@UIDetectedFaceFactory@Internal@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDetectedFaceFactory@Internal@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::Internal::IDetectedFaceFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::Internal::IDetectedFaceFactory>>)
0x18001941f  mov     edi, eax
0x180019421  test    eax, eax
0x180019423  jns     short loc_180019439
0x180019425  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001942a  cmp     al, 1
0x18001942c  jb      loc_18001958E
0x180019432  mov     edx, 0Fh
0x180019437  jmp     short loc_1800193C8
0x180019439  lea     rcx, [rbp+57h+hstringHeader]; string
0x18001943d  lea     rdi, [rbx+4420h]
0x180019444  call    ??$?0$0CH@@StringReference@Internal@Windows@@QEAA@AEAY0CH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[39])
0x180019449  mov     rdx, rdi
0x18001944c  mov     rcx, [rax]
0x18001944f  call    ??$GetActivationFactory@V?$ComPtr@UIFaceTrackerStatics@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIFaceTrackerStatics@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTrackerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTrackerStatics>>)
0x180019454  test    eax, eax
0x180019456  js      short loc_180019475
0x180019458  mov     rcx, [rdi]
0x18001945b  lea     rdx, [rbp+57h+var_60]
0x18001945f  mov     rax, [rcx]
0x180019462  mov     rax, [rax+48h]
0x180019466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946b  test    eax, eax
0x18001946d  js      short loc_180019475
0x18001946f  cmp     [rbp+57h+var_60], 0
0x180019473  jnz     short loc_18001947C
0x180019475  mov     byte ptr [rbx+220h], 0
0x18001947c  movups  xmm1, xmmword ptr cs:MFVideoFormat_MJPG.Data1
0x180019483  xor     eax, eax
0x180019485  lea     r8, [rbp+57h+hstringHeader]
0x180019489  xorps   xmm0, xmm0
0x18001948c  mov     [rbp+57h+pv], rax
0x180019490  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved+4], xmm0
0x180019494  mov     [rbp+57h+var_5C], eax
0x180019497  lea     rax, [rbp+57h+var_5C]
0x18001949b  movups  xmm0, xmmword ptr cs:MFMediaType_Video.Data1
0x1800194a2  mov     [rsp+0A0h+var_70], rax
0x1800194a7  lea     rcx, [rbp+57h+var_50]
0x1800194ab  lea     rax, [rbp+57h+pv]
0x1800194af  xor     r9d, r9d
0x1800194b2  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800194b7  mov     [rsp+0A0h+var_78], rax
0x1800194bc  mov     edx, 10000047h
0x1800194c1  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800194c8  mov     [rsp+0A0h+var_80], 0
0x1800194d1  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved+10h], xmm1
0x1800194d6  movdqu  [rbp+57h+var_50], xmm0
0x1800194db  call    cs:__imp_MFTEnum2
0x1800194e1  mov     edi, eax
0x1800194e3  test    eax, eax
0x1800194e5  jns     short loc_1800194FE
0x1800194e7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800194ec  cmp     al, 1
0x1800194ee  jb      loc_18001958E
0x1800194f4  mov     edx, 10h
0x1800194f9  jmp     loc_1800193C8
0x1800194fe  mov     rcx, [rbp+57h+pv]
0x180019502  test    rcx, rcx
0x180019505  jz      short loc_18001954F
0x180019507  mov     eax, [rbp+57h+var_5C]
0x18001950a  xor     esi, esi
0x18001950c  test    eax, eax
0x18001950e  jz      short loc_180019541
0x180019510  mov     rdx, [rcx+rsi*8]
0x180019514  test    rdx, rdx
0x180019517  jz      short loc_18001953B
0x180019519  mov     rax, [rdx]
0x18001951c  mov     rcx, rdx
0x18001951f  mov     rax, [rax+10h]
0x180019523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019528  mov     rax, [rbp+57h+pv]
0x18001952c  mov     qword ptr [rax+rsi*8], 0
0x180019534  mov     rcx, [rbp+57h+pv]; pv
0x180019538  mov     eax, [rbp+57h+var_5C]
0x18001953b  inc     esi
0x18001953d  cmp     esi, eax
0x18001953f  jb      short loc_180019510
0x180019541  call    cs:__imp_CoTaskMemFree
0x180019547  mov     [rbp+57h+pv], 0
0x18001954f  cmp     [rbp+57h+var_5C], 0
0x180019553  setnbe  cl
0x180019556  mov     [rbx+238h], cl
0x18001955c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180019561  cmp     al, 20h ; ' '
0x180019563  jb      short loc_18001958E
0x180019565  movzx   eax, cl
0x180019568  mov     edx, 11h
0x18001956d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019574  mov     dword ptr [rsp+0A0h+var_80], eax
0x180019578  mov     rcx, [rcx+0D8h]
0x18001957f  mov     r9, rbx
0x180019582  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180019589  call    WPP_SF_qD
0x18001958e  mov     eax, edi
0x180019590  mov     rcx, [rbp+57h+var_20]
0x180019594  xor     rcx, rsp; StackCookie
0x180019597  call    __security_check_cookie
0x18001959c  lea     r11, [rsp+0A0h+var_10]
0x1800195a4  mov     rbx, [r11+28h]
0x1800195a8  mov     rsi, [r11+30h]
0x1800195ac  mov     rsp, r11
0x1800195af  pop     r14
0x1800195b1  pop     rdi
0x1800195b2  pop     rbp
0x1800195b3  retn
```
