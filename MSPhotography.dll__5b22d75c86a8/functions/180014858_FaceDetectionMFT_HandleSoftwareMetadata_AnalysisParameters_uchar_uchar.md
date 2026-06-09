# FaceDetectionMFT::HandleSoftwareMetadata(AnalysisParameters *,uchar * *,uchar * *)

- ea: `0x180014858`
- end: `0x180014c44`
- name: `?HandleSoftwareMetadata@FaceDetectionMFT@@AEAAJPEAUAnalysisParameters@@PEAPEAE1@Z`
- size: `1004`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct AnalysisParameters *, unsigned __int8 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800180ec`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0f8`
- `0x18000d53c`
- `0x18000f338`
- `0x180014858`
- `0x18001605c`
- `0x1800197e0`
- `0x18001cb74`
- `0x1800292a8`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014c1c`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::HandleSoftwareMetadata(
        FaceDetectionMFT *this,
        struct AnalysisParameters *a2,
        unsigned __int8 **a3,
        unsigned __int8 **a4)
{
  _DWORD *v6; // r14
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  unsigned int v11; // edi
  __int64 unique_cotaskmem; // rax
  void *v13; // rcx
  _DWORD *v14; // r13
  unsigned int i; // r12d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, void **); // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  void *v20; // rcx
  _DWORD *v21; // rdi
  unsigned __int8 *v22; // rax
  int v23; // ecx
  int v24; // ecx
  void *v26; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-71h] BYREF
  __int64 v28; // [rsp+40h] [rbp-69h] BYREF
  LPVOID v29; // [rsp+48h] [rbp-61h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-59h] BYREF
  _DWORD *v31; // [rsp+60h] [rbp-49h] BYREF
  __int128 v32; // [rsp+68h] [rbp-41h]
  unsigned __int8 **v33; // [rsp+78h] [rbp-31h]
  unsigned __int8 **v34; // [rsp+80h] [rbp-29h]
  __int128 v35; // [rsp+90h] [rbp-19h] BYREF
  __int128 v36; // [rsp+A0h] [rbp-9h] BYREF

  v34 = a4;
  v33 = a3;
  v6 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  v27 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)a2 + 56LL))(*(_QWORD *)a2, &v27);
  if ( v7 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_42;
    v8 = 148;
    goto LABEL_4;
  }
  v7 = FaceDetectionMFT::SetDominantFaceToFirst(this, a2);
  if ( v7 >= 0 )
  {
    v9 = *(_QWORD *)a2;
    v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)a2 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v7 = v10(v9, &v28);
    if ( v7 >= 0 )
    {
      v7 = FaceDetectionMFT::NotifyDetectedFaces(this, v28, a2);
      if ( v7 >= 0 )
      {
        v11 = 20 * v27 + 8;
        unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(pv, v11);
        wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
          &v29,
          unique_cotaskmem);
        v13 = pv[0];
        pv[0] = 0;
        if ( v13 )
          CoTaskMemFree(v13);
        v6 = v29;
        if ( v29 )
        {
          *(_DWORD *)v29 = v11;
          v6[1] = v27;
          v14 = v6 + 2;
          v26 = 0;
          v36 = 0;
          v32 = 0;
          for ( i = 0; i < v27; ++i )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v16 = v28;
            v17 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v28 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v7 = v17(v16, i, &v26);
            if ( v7 < 0 )
            {
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_30;
              v18 = 153;
              goto LABEL_29;
            }
            *(_OWORD *)pv = 0;
            v7 = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)v26 + 48LL))(v26, &v36);
            if ( v7 < 0 )
            {
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_30;
              v18 = 154;
LABEL_29:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v18,
                &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                this,
                v7);
              goto LABEL_30;
            }
            *(float *)&v32 = (float)(int)v36;
            *((float *)&v32 + 1) = (float)SDWORD1(v36);
            *((float *)&v32 + 2) = (float)SDWORD2(v36);
            *((float *)&v32 + 3) = (float)SHIDWORD(v36);
            v35 = v32;
            v7 = ConvertBoundsToQ31Rect(&v35, *((unsigned int *)a2 + 12), *((unsigned int *)a2 + 13), pv);
            if ( v7 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v18 = 155;
                goto LABEL_29;
              }
LABEL_30:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              goto LABEL_42;
            }
            *(_OWORD *)v14 = *(_OWORD *)pv;
            pv[0] = v26;
            v14[4] = (int)(float)(*(float *)utl::unordered_map<Windows::Media::FaceAnalysis::IDetectedFace *,float,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>>::at(
                                              (char *)a2 + 8,
                                              pv)
                                * 100.0);
            v14 += 5;
          }
          v19 = wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&v29, 24);
          wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
            &v31,
            v19);
          v20 = v29;
          v29 = 0;
          if ( v20 )
            CoTaskMemFree(v20);
          v21 = v31;
          if ( !v31 )
          {
            v7 = -2147024882;
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                156,
                &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
                this,
                v23);
            goto LABEL_30;
          }
          if ( *((_BYTE *)a2 + 112) )
          {
            *v31 = 3;
            *((_QWORD *)v21 + 1) = *((_QWORD *)a2 + 12);
          }
          else
          {
            *v31 = 2;
          }
          *((_QWORD *)v21 + 2) = *((_QWORD *)a2 + 13);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
          v22 = (unsigned __int8 *)v6;
          v6 = 0;
          *v33 = v22;
          *v34 = (unsigned __int8 *)v21;
        }
        else
        {
          v7 = -2147024882;
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              152,
              &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
              this,
              v24);
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v8 = 151;
        goto LABEL_4;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 150;
      goto LABEL_4;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = 149;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v7);
  }
LABEL_42:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014858  push    rbp
0x18001485a  push    rbx
0x18001485b  push    rsi
0x18001485c  push    rdi
0x18001485d  push    r12
0x18001485f  push    r13
0x180014861  push    r14
0x180014863  push    r15
0x180014865  lea     rbp, [rsp-1Fh]
0x18001486a  sub     rsp, 0C8h
0x180014871  mov     rax, cs:__security_cookie
0x180014878  xor     rax, rsp
0x18001487b  mov     [rbp+57h+var_50], rax
0x18001487f  mov     [rbp+57h+var_80], r9
0x180014883  mov     [rbp+57h+var_88], r8
0x180014887  mov     r15, rdx
0x18001488a  mov     rsi, rcx
0x18001488d  xor     r14d, r14d
0x180014890  mov     [rbp+57h+var_B8], r14
0x180014894  mov     [rbp+57h+var_A0], r14
0x180014898  mov     [rbp+57h+var_C0], r14
0x18001489c  mov     [rbp+57h+var_C8], r14d
0x1800148a0  mov     rcx, [rdx]
0x1800148a3  mov     rax, [rcx]
0x1800148a6  lea     rdx, [rbp+57h+var_C8]
0x1800148aa  mov     rax, [rax+38h]
0x1800148ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b3  mov     ebx, eax
0x1800148b5  test    eax, eax
0x1800148b7  jns     short loc_1800148D4
0x1800148b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800148be  cmp     al, 1
0x1800148c0  jb      loc_180014C0A
0x1800148c6  mov     edx, 94h
0x1800148cb  mov     [rsp+100h+var_E0], ebx
0x1800148cf  jmp     loc_180014BEF
0x1800148d4  mov     rdx, r15; struct AnalysisParameters *
0x1800148d7  mov     rcx, rsi; this
0x1800148da  call    ?SetDominantFaceToFirst@FaceDetectionMFT@@AEAAJPEAUAnalysisParameters@@@Z; FaceDetectionMFT::SetDominantFaceToFirst(AnalysisParameters *)
0x1800148df  mov     ebx, eax
0x1800148e1  test    eax, eax
0x1800148e3  jns     short loc_1800148F9
0x1800148e5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800148ea  cmp     al, 1
0x1800148ec  jb      loc_180014C0A
0x1800148f2  mov     edx, 95h
0x1800148f7  jmp     short loc_1800148CB
0x1800148f9  mov     rdi, [r15]
0x1800148fc  mov     rax, [rdi]
0x1800148ff  mov     rbx, [rax+40h]
0x180014903  lea     rcx, [rbp+57h+var_C0]
0x180014907  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001490c  lea     rdx, [rbp+57h+var_C0]
0x180014910  mov     rcx, rdi
0x180014913  mov     rax, rbx
0x180014916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001491b  mov     ebx, eax
0x18001491d  test    eax, eax
0x18001491f  jns     short loc_180014935
0x180014921  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014926  cmp     al, 1
0x180014928  jb      loc_180014C0A
0x18001492e  mov     edx, 96h
0x180014933  jmp     short loc_1800148CB
0x180014935  mov     r8, r15
0x180014938  mov     rdx, [rbp+57h+var_C0]
0x18001493c  mov     rcx, rsi
0x18001493f  call    ?NotifyDetectedFaces@FaceDetectionMFT@@AEAAJPEAU?$IVectorView@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Collections@Foundation@Windows@@PEAUAnalysisParameters@@@Z; FaceDetectionMFT::NotifyDetectedFaces(Windows::Foundation::Collections::IVectorView<Windows::Media::FaceAnalysis::DetectedFace *> *,AnalysisParameters *)
0x180014944  mov     ebx, eax
0x180014946  test    eax, eax
0x180014948  jns     short loc_180014961
0x18001494a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001494f  cmp     al, 1
0x180014951  jb      loc_180014C0A
0x180014957  mov     edx, 97h
0x18001495c  jmp     loc_1800148CB
0x180014961  mov     eax, [rbp+57h+var_C8]
0x180014964  lea     ecx, [rax+rax*4]
0x180014967  lea     edi, ds:8[rcx*4]
0x18001496e  mov     edx, edi
0x180014970  lea     rcx, [rbp+57h+pv]
0x180014974  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180014979  mov     rdx, rax
0x18001497c  lea     rcx, [rbp+57h+var_B8]
0x180014980  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180014985  mov     rcx, [rbp+57h+pv]; pv
0x180014989  mov     [rbp+57h+pv], 0
0x180014991  test    rcx, rcx
0x180014994  jz      short loc_18001499C
0x180014996  call    cs:__imp_CoTaskMemFree
0x18001499c  mov     r14, [rbp+57h+var_B8]
0x1800149a0  test    r14, r14
0x1800149a3  jz      loc_180014BD6
0x1800149a9  mov     [r14], edi
0x1800149ac  mov     eax, [rbp+57h+var_C8]
0x1800149af  mov     [r14+4], eax
0x1800149b3  lea     r13, [r14+8]
0x1800149b7  mov     [rbp+57h+var_D0], 0
0x1800149bf  xorps   xmm0, xmm0
0x1800149c2  movups  [rbp+57h+var_60], xmm0
0x1800149c6  xorps   xmm1, xmm1
0x1800149c9  movups  [rbp+57h+var_98], xmm1
0x1800149cd  xor     r12d, r12d
0x1800149d0  cmp     r12d, [rbp+57h+var_C8]
0x1800149d4  jnb     loc_180014B36
0x1800149da  lea     rcx, [rbp+57h+var_D0]
0x1800149de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149e3  mov     rdi, [rbp+57h+var_C0]
0x1800149e7  mov     rax, [rdi]
0x1800149ea  mov     rbx, [rax+30h]
0x1800149ee  lea     rcx, [rbp+57h+var_D0]
0x1800149f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149f7  lea     r8, [rbp+57h+var_D0]
0x1800149fb  mov     edx, r12d
0x1800149fe  mov     rcx, rdi
0x180014a01  mov     rax, rbx
0x180014a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a09  mov     ebx, eax
0x180014a0b  test    eax, eax
0x180014a0d  js      loc_180014AFB
0x180014a13  xorps   xmm0, xmm0
0x180014a16  movdqa  xmmword ptr [rbp+57h+pv], xmm0
0x180014a1b  mov     rcx, [rbp+57h+var_D0]
0x180014a1f  mov     rax, [rcx]
0x180014a22  lea     rdx, [rbp+57h+var_60]
0x180014a26  mov     rax, [rax+30h]
0x180014a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a2f  mov     ebx, eax
0x180014a31  test    eax, eax
0x180014a33  js      loc_180014AEB
0x180014a39  mov     eax, dword ptr [rbp+57h+var_60]
0x180014a3c  xorps   xmm0, xmm0
0x180014a3f  cvtsi2ss xmm0, rax
0x180014a44  movss   dword ptr [rbp+57h+var_98], xmm0
0x180014a49  mov     eax, dword ptr [rbp+57h+var_60+4]
0x180014a4c  xorps   xmm1, xmm1
0x180014a4f  cvtsi2ss xmm1, rax
0x180014a54  movss   dword ptr [rbp+57h+var_98+4], xmm1
0x180014a59  mov     eax, dword ptr [rbp+57h+var_60+8]
0x180014a5c  xorps   xmm0, xmm0
0x180014a5f  cvtsi2ss xmm0, rax
0x180014a64  movss   dword ptr [rbp+57h+var_98+8], xmm0
0x180014a69  mov     eax, dword ptr [rbp+57h+var_60+0Ch]
0x180014a6c  xorps   xmm1, xmm1
0x180014a6f  cvtsi2ss xmm1, rax
0x180014a74  movss   dword ptr [rbp+57h+var_98+0Ch], xmm1
0x180014a79  movups  xmm0, [rbp+57h+var_98]
0x180014a7d  movups  [rbp+57h+var_70], xmm0
0x180014a81  lea     r9, [rbp+57h+pv]
0x180014a85  mov     r8d, [r15+34h]
0x180014a89  mov     edx, [r15+30h]
0x180014a8d  lea     rcx, [rbp+57h+var_70]
0x180014a91  call    ?ConvertBoundsToQ31Rect@@YAJURect@Foundation@Windows@@IIPEAUtagRECT@@@Z; ConvertBoundsToQ31Rect(Windows::Foundation::Rect,uint,uint,tagRECT *)
0x180014a96  mov     ebx, eax
0x180014a98  test    eax, eax
0x180014a9a  js      short loc_180014ADB
0x180014a9c  movaps  xmm0, xmmword ptr [rbp+57h+pv]
0x180014aa0  movdqu  xmmword ptr [r13+0], xmm0
0x180014aa6  mov     rax, [rbp+57h+var_D0]
0x180014aaa  mov     [rbp+57h+pv], rax
0x180014aae  lea     rcx, [r15+8]
0x180014ab2  lea     rdx, [rbp+57h+pv]
0x180014ab6  call    ?at@?$unordered_map@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@MU?$hash@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@utl@@U?$equal_to@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@V?$allocator@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@6@@utl@@QEAAAEAMAEBQEAUIDetectedFace@FaceAnalysis@Media@Windows@@@Z; utl::unordered_map<Windows::Media::FaceAnalysis::IDetectedFace *,float,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>>::at(Windows::Media::FaceAnalysis::IDetectedFace * const &)
0x180014abb  movss   xmm0, dword ptr [rax]
0x180014abf  mulss   xmm0, cs:__real@42c80000
0x180014ac7  cvttss2si eax, xmm0
0x180014acb  mov     [r13+10h], eax
0x180014acf  add     r13, 14h
0x180014ad3  inc     r12d
0x180014ad6  jmp     loc_1800149D0
0x180014adb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014ae0  cmp     al, 1
0x180014ae2  jb      short loc_180014B28
0x180014ae4  mov     edx, 9Bh
0x180014ae9  jmp     short loc_180014B09
0x180014aeb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014af0  cmp     al, 1
0x180014af2  jb      short loc_180014B28
0x180014af4  mov     edx, 9Ah
0x180014af9  jmp     short loc_180014B09
0x180014afb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014b00  cmp     al, 1
0x180014b02  jb      short loc_180014B28
0x180014b04  mov     edx, 99h
0x180014b09  mov     [rsp+100h+var_E0], ebx
0x180014b0d  mov     r9, rsi
0x180014b10  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b1e  mov     rcx, [rcx+10h]
0x180014b22  call    WPP_SF_qD
0x180014b27  nop
0x180014b28  lea     rcx, [rbp+57h+var_D0]
0x180014b2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014b31  jmp     loc_180014C0A
0x180014b36  mov     edx, 18h
0x180014b3b  lea     rcx, [rbp+57h+var_B8]
0x180014b3f  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180014b44  mov     rdx, rax
0x180014b47  lea     rcx, [rbp+57h+var_A0]
0x180014b4b  call    ??4?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180014b50  mov     rcx, [rbp+57h+var_B8]; pv
0x180014b54  mov     [rbp+57h+var_B8], 0
0x180014b5c  test    rcx, rcx
0x180014b5f  jz      short loc_180014B67
0x180014b61  call    cs:__imp_CoTaskMemFree
0x180014b67  mov     rdi, [rbp+57h+var_A0]
0x180014b6b  test    rdi, rdi
0x180014b6e  jz      short loc_180014BB4
0x180014b70  cmp     byte ptr [r15+70h], 0
0x180014b75  jz      short loc_180014B87
0x180014b77  mov     dword ptr [rdi], 3
0x180014b7d  mov     rax, [r15+60h]
0x180014b81  mov     [rdi+8], rax
0x180014b85  jmp     short loc_180014B8D
0x180014b87  mov     dword ptr [rdi], 2
0x180014b8d  mov     rax, [r15+68h]
0x180014b91  mov     [rdi+10h], rax
0x180014b95  lea     rcx, [rbp+57h+var_D0]
0x180014b99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014b9e  mov     rax, r14
0x180014ba1  xor     r14d, r14d
0x180014ba4  mov     rcx, [rbp+57h+var_88]
0x180014ba8  mov     [rcx], rax
0x180014bab  mov     rax, [rbp+57h+var_80]
0x180014baf  mov     [rax], rdi
0x180014bb2  jmp     short loc_180014C0A
0x180014bb4  mov     ecx, 8007000Eh
0x180014bb9  mov     ebx, ecx
0x180014bbb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014bc0  cmp     al, 1
0x180014bc2  jb      loc_180014B28
0x180014bc8  mov     edx, 9Ch
0x180014bcd  mov     [rsp+100h+var_E0], ecx
0x180014bd1  jmp     loc_180014B0D
0x180014bd6  mov     ecx, 8007000Eh
0x180014bdb  mov     ebx, ecx
0x180014bdd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014be2  cmp     al, 1
0x180014be4  jb      short loc_180014C0A
0x180014be6  mov     edx, 98h
0x180014beb  mov     [rsp+100h+var_E0], ecx
0x180014bef  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bf6  mov     r9, rsi
0x180014bf9  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014c00  mov     rcx, [rcx+10h]
0x180014c04  call    WPP_SF_qD
0x180014c09  nop
0x180014c0a  lea     rcx, [rbp+57h+var_C0]
0x180014c0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014c13  nop
0x180014c14  test    r14, r14
0x180014c17  jz      short loc_180014C22
0x180014c19  mov     rcx, r14; pv
0x180014c1c  call    cs:__imp_CoTaskMemFree
0x180014c22  mov     eax, ebx
0x180014c24  mov     rcx, [rbp+57h+var_50]
0x180014c28  xor     rcx, rsp; StackCookie
0x180014c2b  call    __security_check_cookie
0x180014c30  add     rsp, 0C8h
0x180014c37  pop     r15
0x180014c39  pop     r14
0x180014c3b  pop     r13
0x180014c3d  pop     r12
0x180014c3f  pop     rdi
0x180014c40  pop     rsi
0x180014c41  pop     rbx
0x180014c42  pop     rbp
0x180014c43  retn
```
