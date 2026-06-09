# DeriveConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,int,tWAVEFORMATEX * *)

- ea: `0x18001fa40`
- end: `0x1800200e0`
- name: `?DeriveConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@33HPEAPEAU3@@Z`
- size: `1696`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<edx>, struct tWAVEFORMATEX *Src@<r8>, struct _GUID *__struct_ptr@<r9>, struct _GUID *, struct _GUID *, int, struct tWAVEFORMATEX **)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001eb4c`
- `0x180083c90`
- `0x1800842f0`
- `0x180123220`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001f258`
- `0x18001f6b0`
- `0x18001fa40`
- `0x1800214d0`
- `0x18003cee0`
- `0x18003f11c`
- `0x180040938`
- `0x1800d074c`
- `0x1800d2588`
- `0x180118500`
- `0x180118ae0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fa89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fa89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fce5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fbcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fce5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200bc`

## string_xrefs

- `0x18001faa8`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fbba`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fbf5`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fc91`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fccf`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fed0`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001feef`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001ff7a`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1800200ca`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DeriveConnectorFormatFromStreamFormat(
        EffectPack **a1,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        IAudioMediaType *Src,
        struct _GUID *a4,
        struct _GUID *a5,
        struct _GUID *a6,
        int a7,
        struct tWAVEFORMATEX **pAudioFormat)
{
  struct tWAVEFORMATEX **v12; // r12
  __int64 lpVtbl_low; // rsi
  struct tWAVEFORMATEX *v14; // rax
  struct tWAVEFORMATEX *v15; // rbx
  unsigned int v16; // r14d
  struct tWAVEFORMATEX *v17; // rcx
  struct tWAVEFORMATEX *v18; // rsi
  struct _GUID *v19; // rdi
  void *v20; // rcx
  __int64 v22; // rdx
  struct _GUID *v23; // rbx
  int v24; // eax
  struct tWAVEFORMATEX **v25; // rbx
  __int64 v26; // rdx
  struct tWAVEFORMATEX **v27; // rcx
  IAudioMediaType *v28; // rcx
  const struct tWAVEFORMATEX *v29; // rax
  const struct tWAVEFORMATEX *v30; // rax
  struct tWAVEFORMATEX **v31; // rcx
  IAudioMediaType *v32; // rbx
  _DWORD *v33; // rdi
  struct tWAVEFORMATEX *v34; // rcx
  int v35; // ecx
  struct tWAVEFORMATEX *v36; // rdi
  __int64 v37; // rdx
  const struct tWAVEFORMATEX *v38; // rax
  const struct tWAVEFORMATEX *v39; // rax
  int v40; // [rsp+20h] [rbp-81h]
  int v41; // [rsp+20h] [rbp-81h]
  struct IAudioMediaType *v42; // [rsp+40h] [rbp-61h] BYREF
  IAudioMediaType *ppIAudioMediaType; // [rsp+48h] [rbp-59h] BYREF
  struct _GUID v44; // [rsp+50h] [rbp-51h] BYREF
  struct _GUID v45; // [rsp+60h] [rbp-41h] BYREF
  struct tWAVEFORMATEX *v46; // [rsp+70h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-29h]
  struct _GUID v48; // [rsp+80h] [rbp-21h] BYREF
  struct tWAVEFORMATEX *v49; // [rsp+90h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]
  IAudioMediaType *v51; // [rsp+100h] [rbp+5Fh] BYREF

  v51 = Src;
  v46 = 0;
  v12 = pAudioFormat;
  *pAudioFormat = 0;
  lpVtbl_low = LOWORD(Src[2].lpVtbl);
  v14 = (struct tWAVEFORMATEX *)CoTaskMemAlloc(lpVtbl_low + 18);
  v15 = v14;
  pv = v14;
  if ( v14 )
  {
    memcpy_0(v14, Src, lpVtbl_low + 18);
    v49 = v15;
    v45 = *a4;
    v16 = -2004287480;
    if ( EffectPack::GetMixFormat(a1[1], a2, &v45, &v46) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28F,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
        (const char *)0x88890008LL,
        v40);
      CoTaskMemFree(v15);
      v17 = v46;
      goto LABEL_11;
    }
    v18 = v46;
    if ( a7 && g_PerformStrictConnectorMatchOnMatchFormat )
    {
      v19 = a5;
    }
    else
    {
      v19 = a5;
      v45 = *a5;
      if ( !IsStreamFormatSupportedForMixFormat((struct EndpointCharacteristicsDescriptor *)a1, &v45, a2, v46, v15, 0) )
      {
        v45 = *a6;
        if ( GetDeviceDefaults((struct EndpointCharacteristicsDescriptor *)a1, a2, &v45, v12, 0, 0, 0) < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
            (const char *)0x88890008LL,
            v41);
          v20 = v15;
          goto LABEL_10;
        }
        if ( *v12 )
          goto LABEL_8;
        v22 = 664;
LABEL_64:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)0x88890008LL,
          v41);
        goto LABEL_9;
      }
      if ( !a7 )
      {
LABEL_63:
        v22 = 745;
        goto LABEL_64;
      }
    }
    pAudioFormat = 0;
    v23 = a6;
    v45 = *a6;
    v24 = DeriveConnectorFormatWithHighestBitDepthFromStreamFormat(
            (struct EndpointCharacteristicsDescriptor *)a1,
            a2,
            (struct tWAVEFORMATEX *)v51,
            &v45,
            (struct tWAVEFORMATEX **)&pAudioFormat);
    if ( v24 >= 0 )
    {
      ppIAudioMediaType = 0;
      *(_QWORD *)&v44.Data1 = 0;
      v42 = 0;
      v25 = pAudioFormat;
      if ( CreateAudioMediaType(
             (const WAVEFORMATEX *)pAudioFormat,
             *((unsigned __int16 *)pAudioFormat + 8) + 18,
             &ppIAudioMediaType) < 0 )
      {
        v26 = 681;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)0x88890008LL,
          v41);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
        v27 = v25;
LABEL_25:
        CoTaskMemFree(v27);
        goto LABEL_9;
      }
      v45 = *v19;
      if ( (int)EffectPack::DeriveDevicePipeFormatFromConnectorFormat(
                  a1[1],
                  &v45,
                  a2,
                  ppIAudioMediaType,
                  (struct IAudioMediaType **)&v44) < 0 )
      {
        v26 = 684;
        goto LABEL_22;
      }
      v45 = *v19;
      if ( (int)EffectPack::DeriveMixFormatFromDevicePipeFormat(
                  a1[1],
                  &v45,
                  a2,
                  *(struct IAudioMediaType **)&v44.Data1,
                  &v42,
                  0) < 0 )
      {
        v26 = 687;
        goto LABEL_22;
      }
      v29 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(struct IAudioMediaType *))v42->lpVtbl->GetAudioFormat)(v42);
      v45 = *v19;
      if ( IsStreamFormatSupportedForMixFormat(
             (struct EndpointCharacteristicsDescriptor *)a1,
             &v45,
             a2,
             v29,
             (const struct tWAVEFORMATEX *)v51,
             0) )
      {
        v26 = 690;
        goto LABEL_22;
      }
      v30 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))ppIAudioMediaType->lpVtbl->GetAudioFormat)(ppIAudioMediaType);
      if ( (int)CloneWaveFormat(v30, v12) < 0 )
      {
        v26 = 693;
        goto LABEL_22;
      }
      if ( !*v12 )
      {
        v26 = 694;
        goto LABEL_22;
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&ppIAudioMediaType);
      v31 = v25;
      goto LABEL_37;
    }
    if ( !g_PerformStrictConnectorMatchOnMatchFormat && v24 == -2004287480 )
    {
      ppIAudioMediaType = 0;
      v45 = *v23;
      if ( GetDeviceDefaults(
             (struct EndpointCharacteristicsDescriptor *)a1,
             a2,
             &v45,
             (struct tWAVEFORMATEX **)&ppIAudioMediaType,
             0,
             0,
             0) < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C1,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
          (const char *)0x88890008LL,
          v41);
        v28 = ppIAudioMediaType;
        goto LABEL_24;
      }
      v32 = ppIAudioMediaType;
      v33 = pv;
      if ( *((_DWORD *)pv + 1) != HIDWORD(ppIAudioMediaType->lpVtbl) )
      {
        *(_QWORD *)&v45.Data1 = 0;
        if ( (int)CloneWaveFormat((const struct tWAVEFORMATEX *)ppIAudioMediaType, (struct tWAVEFORMATEX **)&v45) >= 0 )
        {
          v35 = v33[1];
          v36 = *(struct tWAVEFORMATEX **)&v45.Data1;
          *(_DWORD *)(*(_QWORD *)&v45.Data1 + 4LL) = v35;
          v36->nAvgBytesPerSec = v35 * v36->nBlockAlign;
          v44 = *a6;
          if ( ConnectorSupportsFormat((struct EndpointCharacteristicsDescriptor *)a1, a2, v36, &v44) < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CC,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
              (const char *)0x88890008LL,
              v41);
          }
          else
          {
            v51 = 0;
            v42 = 0;
            *(_QWORD *)&v44.Data1 = 0;
            if ( CreateAudioMediaType(v36, v36->cbSize + 18, &v51) >= 0 )
            {
              v48 = *a5;
              if ( (int)EffectPack::DeriveDevicePipeFormatFromConnectorFormat(a1[1], &v48, a2, v51, &v42) >= 0 )
              {
                v48 = *a5;
                if ( (int)EffectPack::DeriveMixFormatFromDevicePipeFormat(
                            a1[1],
                            &v48,
                            a2,
                            v42,
                            (struct IAudioMediaType **)&v44,
                            0) >= 0 )
                {
                  v38 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v44.Data1 + 40LL))(*(_QWORD *)&v44.Data1);
                  v48 = *a5;
                  if ( IsStreamFormatSupportedForMixFormat(
                         (struct EndpointCharacteristicsDescriptor *)a1,
                         &v48,
                         a2,
                         v38,
                         (const struct tWAVEFORMATEX *)pv,
                         0) )
                  {
                    v37 = 733;
                  }
                  else
                  {
                    v39 = (const struct tWAVEFORMATEX *)((__int64 (__fastcall *)(IAudioMediaType *))v51->lpVtbl->GetAudioFormat)(v51);
                    if ( (int)CloneWaveFormat(v39, v12) >= 0 )
                    {
                      if ( *v12 )
                      {
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
                        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
                        CoTaskMemFree(v36);
                        CoTaskMemFree(v32);
                        v31 = pAudioFormat;
LABEL_37:
                        CoTaskMemFree(v31);
LABEL_8:
                        v16 = 0;
LABEL_9:
                        v20 = pv;
LABEL_10:
                        CoTaskMemFree(v20);
                        v17 = v18;
                        goto LABEL_11;
                      }
                      v37 = 737;
                    }
                    else
                    {
                      v37 = 736;
                    }
                  }
                }
                else
                {
                  v37 = 729;
                }
              }
              else
              {
                v37 = 725;
              }
            }
            else
            {
              v37 = 721;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v37,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
              (const char *)0x88890008LL,
              v41);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v51);
          }
          v34 = v36;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C6,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
            (const char *)0x88890008LL,
            v41);
          v34 = *(struct tWAVEFORMATEX **)&v45.Data1;
        }
        CoTaskMemFree(v34);
        v28 = v32;
LABEL_24:
        CoTaskMemFree(v28);
        v27 = pAudioFormat;
        goto LABEL_25;
      }
      CoTaskMemFree(ppIAudioMediaType);
    }
    CoTaskMemFree(pAudioFormat);
    goto LABEL_63;
  }
  v16 = -2004287480;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x27A,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\policyconfig.cpp",
    (const char *)0x88890008LL,
    v40);
  CoTaskMemFree(0);
  v17 = 0;
LABEL_11:
  CoTaskMemFree(v17);
  return v16;
}

```

## disassembly

```asm
0x18001fa40  mov     [rsp-8+arg_10], r8
0x18001fa45  push    rbp
0x18001fa46  push    rbx
0x18001fa47  push    rsi
0x18001fa48  push    rdi
0x18001fa49  push    r12
0x18001fa4b  push    r13
0x18001fa4d  push    r14
0x18001fa4f  push    r15
0x18001fa51  lea     rbp, [rsp-7]
0x18001fa56  sub     rsp, 0A8h
0x18001fa5d  mov     r14, r9
0x18001fa60  mov     rdi, r8
0x18001fa63  mov     r15d, edx
0x18001fa66  mov     r13, rcx
0x18001fa69  mov     [rbp+3Fh+var_70], 0
0x18001fa71  mov     r12, [rbp+3Fh+pAudioFormat]
0x18001fa78  mov     qword ptr [r12], 0
0x18001fa80  movzx   esi, word ptr [r8+10h]
0x18001fa85  lea     rcx, [rsi+12h]; cb
0x18001fa89  call    cs:__imp_CoTaskMemAlloc
0x18001fa8f  mov     rbx, rax
0x18001fa92  mov     [rbp+3Fh+pv], rax
0x18001fa96  test    rax, rax
0x18001fa99  jnz     short loc_18001FACA
0x18001fa9b  mov     rcx, [rbp+47h]; this
0x18001fa9f  mov     r14d, 88890008h
0x18001faa5  mov     r9d, r14d; char *
0x18001faa8  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001faaf  mov     edx, 27Ah; void *
0x18001fab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fab9  nop
0x18001faba  xor     ecx, ecx; pv
0x18001fabc  call    cs:__imp_CoTaskMemFree
0x18001fac2  nop
0x18001fac3  xor     ecx, ecx
0x18001fac5  jmp     loc_18001FB96
0x18001faca  lea     r8, [rsi+12h]; Size
0x18001face  mov     rdx, rdi; Src
0x18001fad1  mov     rcx, rbx; void *
0x18001fad4  call    memcpy_0
0x18001fad9  mov     [rbp+3Fh+var_50], rbx
0x18001fadd  movaps  xmm0, xmmword ptr [r14]
0x18001fae1  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fae6  lea     r9, [rbp+3Fh+var_70]; struct tWAVEFORMATEX **
0x18001faea  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001faee  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001faf1  mov     rcx, [r13+8]; this
0x18001faf5  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001fafa  xor     ecx, ecx
0x18001fafc  mov     r14d, 88890008h
0x18001fb02  test    eax, eax
0x18001fb04  js      loc_18001FBB3
0x18001fb0a  mov     rsi, [rbp+3Fh+var_70]
0x18001fb0e  cmp     [rbp+3Fh+arg_30], ecx
0x18001fb11  jnz     loc_18001FBDC
0x18001fb17  mov     rdi, [rbp+3Fh+arg_20]
0x18001fb1b  movaps  xmm0, xmmword ptr [rdi]
0x18001fb1e  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fb23  mov     [rsp+0E0h+var_B8], rcx; struct tWAVEFORMATEX **
0x18001fb28  mov     [rsp+0E0h+var_C0], rbx; struct tWAVEFORMATEX *
0x18001fb2d  mov     r9, rsi; struct tWAVEFORMATEX *
0x18001fb30  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fb33  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fb37  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fb3a  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fb3f  xor     ecx, ecx
0x18001fb41  test    eax, eax
0x18001fb43  jnz     loc_18001FC16
0x18001fb49  mov     rax, [rbp+3Fh+arg_28]
0x18001fb4d  movaps  xmm0, xmmword ptr [rax]
0x18001fb50  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fb55  mov     [rsp+0E0h+var_B0], rcx; __int64 *
0x18001fb5a  mov     [rsp+0E0h+var_B8], rcx; __int64 *
0x18001fb5f  mov     [rsp+0E0h+var_C0], rcx; int
0x18001fb64  mov     r9, r12; struct tWAVEFORMATEX **
0x18001fb67  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001fb6b  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fb6e  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fb71  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001fb76  test    eax, eax
0x18001fb78  js      short loc_18001FBEE
0x18001fb7a  cmp     qword ptr [r12], 0
0x18001fb7f  jz      loc_18001FC0C
0x18001fb85  xor     r14d, r14d
0x18001fb88  mov     rcx, [rbp+3Fh+pv]; pv
0x18001fb8c  call    cs:__imp_CoTaskMemFree
0x18001fb92  nop
0x18001fb93  mov     rcx, rsi; pv
0x18001fb96  call    cs:__imp_CoTaskMemFree
0x18001fb9c  mov     eax, r14d
0x18001fb9f  add     rsp, 0A8h
0x18001fba6  pop     r15
0x18001fba8  pop     r14
0x18001fbaa  pop     r13
0x18001fbac  pop     r12
0x18001fbae  pop     rdi
0x18001fbaf  pop     rsi
0x18001fbb0  pop     rbx
0x18001fbb1  pop     rbp
0x18001fbb2  retn
0x18001fbb3  mov     rcx, [rbp+47h]; this
0x18001fbb7  mov     r9d, r14d; char *
0x18001fbba  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fbc1  mov     edx, 28Fh; void *
0x18001fbc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbcb  nop
0x18001fbcc  mov     rcx, rbx; pv
0x18001fbcf  call    cs:__imp_CoTaskMemFree
0x18001fbd5  nop
0x18001fbd6  mov     rcx, [rbp+3Fh+var_70]
0x18001fbda  jmp     short loc_18001FB96
0x18001fbdc  cmp     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, ecx; int g_PerformStrictConnectorMatchOnMatchFormat
0x18001fbe2  jz      loc_18001FB17
0x18001fbe8  mov     rdi, [rbp+3Fh+arg_20]
0x18001fbec  jmp     short loc_18001FC1F
0x18001fbee  mov     rcx, [rbp+47h]; this
0x18001fbf2  mov     r9d, r14d; char *
0x18001fbf5  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fbfc  mov     edx, 297h; void *
0x18001fc01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc06  nop
0x18001fc07  mov     rcx, rbx
0x18001fc0a  jmp     short loc_18001FB8C
0x18001fc0c  mov     edx, 298h
0x18001fc11  jmp     loc_1800200C7
0x18001fc16  cmp     [rbp+3Fh+arg_30], ecx
0x18001fc19  jz      loc_1800200C2
0x18001fc1f  mov     [rbp+3Fh+pAudioFormat], rcx
0x18001fc26  mov     rbx, [rbp+3Fh+arg_28]
0x18001fc2a  movaps  xmm0, xmmword ptr [rbx]
0x18001fc2d  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fc32  lea     rax, [rbp+3Fh+pAudioFormat]
0x18001fc39  mov     [rsp+0E0h+var_C0], rax; struct tWAVEFORMATEX **
0x18001fc3e  lea     r9, [rbp+3Fh+var_80]; struct _GUID
0x18001fc42  mov     r8, [rbp+3Fh+arg_10]; struct tWAVEFORMATEX *
0x18001fc46  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fc49  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fc4c  call    ?DeriveConnectorFormatWithHighestBitDepthFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@PEAPEAU3@@Z; DeriveConnectorFormatWithHighestBitDepthFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,tWAVEFORMATEX * *)
0x18001fc51  xor     ecx, ecx
0x18001fc53  test    eax, eax
0x18001fc55  js      loc_18001FE52
0x18001fc5b  mov     [rbp+3Fh+ppIAudioMediaType], rcx
0x18001fc5f  mov     qword ptr [rbp+3Fh+var_90.Data1], rcx
0x18001fc63  mov     [rbp+3Fh+var_A0], rcx
0x18001fc67  mov     rbx, [rbp+3Fh+pAudioFormat]
0x18001fc6e  movzx   edx, word ptr [rbx+10h]
0x18001fc72  add     edx, 12h; cbAudioFormatSize
0x18001fc75  lea     r8, [rbp+3Fh+ppIAudioMediaType]; ppIAudioMediaType
0x18001fc79  mov     rcx, rbx; pAudioFormat
0x18001fc7c  call    CreateAudioMediaType
0x18001fc81  test    eax, eax
0x18001fc83  jns     short loc_18001FCFE
0x18001fc85  mov     edx, 2A9h
0x18001fc8a  jmp     short loc_18001FC91
0x18001fc8c  mov     edx, 2B6h; void *
0x18001fc91  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fc98  mov     r9d, r14d; char *
0x18001fc9b  mov     rcx, [rbp+47h]; this
0x18001fc9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fca4  nop
0x18001fca5  lea     rcx, [rbp+3Fh+var_A0]
0x18001fca9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fcae  nop
0x18001fcaf  lea     rcx, [rbp+3Fh+var_90]
0x18001fcb3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fcb8  nop
0x18001fcb9  lea     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001fcbd  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fcc2  nop
0x18001fcc3  mov     rcx, rbx
0x18001fcc6  jmp     short loc_18001FCF3
0x18001fcc8  mov     rcx, [rbp+47h]; this
0x18001fccc  mov     r9d, r14d; char *
0x18001fccf  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fcd6  mov     edx, 2C1h; void *
0x18001fcdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fce0  nop
0x18001fce1  mov     rcx, [rbp+3Fh+ppIAudioMediaType]; pv
0x18001fce5  call    cs:__imp_CoTaskMemFree
0x18001fceb  nop
0x18001fcec  mov     rcx, [rbp+3Fh+pAudioFormat]; pv
0x18001fcf3  call    cs:__imp_CoTaskMemFree
0x18001fcf9  jmp     loc_18001FB88
0x18001fcfe  movaps  xmm0, xmmword ptr [rdi]
0x18001fd01  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fd06  lea     rax, [rbp+3Fh+var_90]
0x18001fd0a  mov     [rsp+0E0h+var_C0], rax; struct IAudioMediaType **
0x18001fd0f  mov     r9, [rbp+3Fh+ppIAudioMediaType]; struct IAudioMediaType *
0x18001fd13  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fd16  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fd1a  mov     rcx, [r13+8]; this
0x18001fd1e  call    ?DeriveDevicePipeFormatFromConnectorFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z; EffectPack::DeriveDevicePipeFormatFromConnectorFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)
0x18001fd23  test    eax, eax
0x18001fd25  jns     short loc_18001FD31
0x18001fd27  mov     edx, 2ACh
0x18001fd2c  jmp     loc_18001FC91
0x18001fd31  movaps  xmm0, xmmword ptr [rdi]
0x18001fd34  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fd39  mov     [rsp+0E0h+var_B8], 0; struct IAudioMediaType **
0x18001fd42  lea     rax, [rbp+3Fh+var_A0]
0x18001fd46  mov     [rsp+0E0h+var_C0], rax; struct IAudioMediaType **
0x18001fd4b  mov     r9, qword ptr [rbp+3Fh+var_90.Data1]; struct IAudioMediaType *
0x18001fd4f  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fd52  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fd56  mov     rcx, [r13+8]; this
0x18001fd5a  call    ?DeriveMixFormatFromDevicePipeFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@3@Z; EffectPack::DeriveMixFormatFromDevicePipeFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *,IAudioMediaType * *)
0x18001fd5f  test    eax, eax
0x18001fd61  jns     short loc_18001FD6D
0x18001fd63  mov     edx, 2AFh
0x18001fd68  jmp     loc_18001FC91
0x18001fd6d  mov     rcx, [rbp+3Fh+var_A0]
0x18001fd71  mov     rax, [rcx]
0x18001fd74  mov     rax, [rax+28h]
0x18001fd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd7d  movaps  xmm0, xmmword ptr [rdi]
0x18001fd80  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fd85  mov     [rsp+0E0h+var_B8], 0; struct tWAVEFORMATEX **
0x18001fd8e  mov     rcx, [rbp+3Fh+arg_10]
0x18001fd92  mov     [rsp+0E0h+var_C0], rcx; struct tWAVEFORMATEX *
0x18001fd97  mov     r9, rax; struct tWAVEFORMATEX *
0x18001fd9a  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fd9d  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fda1  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fda4  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fda9  test    eax, eax
0x18001fdab  jz      short loc_18001FDB7
0x18001fdad  mov     edx, 2B2h
0x18001fdb2  jmp     loc_18001FC91
0x18001fdb7  mov     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001fdbb  mov     rax, [rcx]
0x18001fdbe  mov     rax, [rax+28h]
0x18001fdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdc7  mov     rcx, rax; Src
0x18001fdca  mov     rdx, r12; struct tWAVEFORMATEX **
0x18001fdcd  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fdd2  test    eax, eax
0x18001fdd4  jns     short loc_18001FDE0
0x18001fdd6  mov     edx, 2B5h
0x18001fddb  jmp     loc_18001FC91
0x18001fde0  cmp     qword ptr [r12], 0
0x18001fde5  jz      loc_18001FC8C
0x18001fdeb  lea     rcx, [rbp+3Fh+var_A0]
0x18001fdef  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fdf4  nop
0x18001fdf5  lea     rcx, [rbp+3Fh+var_90]
0x18001fdf9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fdfe  nop
0x18001fdff  lea     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001fe03  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe08  nop
0x18001fe09  mov     rcx, rbx
0x18001fe0c  jmp     short loc_18001FE47
0x18001fe0e  lea     rcx, [rbp+3Fh+var_90]
0x18001fe12  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe17  nop
0x18001fe18  lea     rcx, [rbp+3Fh+var_A0]
0x18001fe1c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe21  nop
0x18001fe22  lea     rcx, [rbp+3Fh+arg_10]
0x18001fe26  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe2b  nop
0x18001fe2c  mov     rcx, rdi; pv
0x18001fe2f  call    cs:__imp_CoTaskMemFree
0x18001fe35  nop
0x18001fe36  mov     rcx, rbx; pv
0x18001fe39  call    cs:__imp_CoTaskMemFree
0x18001fe3f  nop
0x18001fe40  mov     rcx, [rbp+3Fh+pAudioFormat]; pv
0x18001fe47  call    cs:__imp_CoTaskMemFree
0x18001fe4d  jmp     loc_18001FB85
0x18001fe52  cmp     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, ecx; int g_PerformStrictConnectorMatchOnMatchFormat
0x18001fe58  jnz     loc_1800200B5
0x18001fe5e  cmp     eax, r14d
0x18001fe61  jnz     loc_1800200B5
0x18001fe67  mov     [rbp+3Fh+ppIAudioMediaType], rcx
0x18001fe6b  movaps  xmm0, xmmword ptr [rbx]
0x18001fe6e  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fe73  mov     [rsp+0E0h+var_B0], rcx; __int64 *
0x18001fe78  mov     [rsp+0E0h+var_B8], rcx; __int64 *
0x18001fe7d  mov     [rsp+0E0h+var_C0], rcx; int
0x18001fe82  lea     r9, [rbp+3Fh+ppIAudioMediaType]; struct tWAVEFORMATEX **
0x18001fe86  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001fe8a  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fe8d  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fe90  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001fe95  test    eax, eax
0x18001fe97  js      loc_18001FCC8
0x18001fe9d  mov     rbx, [rbp+3Fh+ppIAudioMediaType]
0x18001fea1  mov     eax, [rbx+4]
0x18001fea4  mov     rdi, [rbp+3Fh+pv]
0x18001fea8  cmp     [rdi+4], eax
0x18001feab  jz      loc_1800200AB
0x18001feb1  mov     qword ptr [rbp+3Fh+var_80.Data1], 0
0x18001feb9  lea     rdx, [rbp+3Fh+var_80]; struct tWAVEFORMATEX **
0x18001febd  mov     rcx, rbx; Src
0x18001fec0  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fec5  test    eax, eax
0x18001fec7  jns     short loc_18001FF13
0x18001fec9  mov     rcx, [rbp+47h]; this
  ... truncated ...
```
