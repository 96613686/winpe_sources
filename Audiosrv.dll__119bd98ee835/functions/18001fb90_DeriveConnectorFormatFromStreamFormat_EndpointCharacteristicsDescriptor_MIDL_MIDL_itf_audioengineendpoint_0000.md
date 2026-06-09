# DeriveConnectorFormatFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,_GUID,_GUID,int,tWAVEFORMATEX * *)

- ea: `0x18001fb90`
- end: `0x180020230`
- name: `?DeriveConnectorFormatFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@33HPEAPEAU3@@Z`
- size: `1696`
- prototype: `__int64 __usercall@<rax>(struct EndpointCharacteristicsDescriptor *@<rcx>, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@<edx>, struct tWAVEFORMATEX *Src@<r8>, struct _GUID *__struct_ptr@<r9>, struct _GUID *, struct _GUID *, int, struct tWAVEFORMATEX **)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ec9c`
- `0x180083790`
- `0x180083df0`
- `0x180123470`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001f3a8`
- `0x18001f800`
- `0x18001fb90`
- `0x180021620`
- `0x18003d040`
- `0x18003f28c`
- `0x180040aa8`
- `0x1800ce75c`
- `0x1800d0598`
- `0x180118750`
- `0x180118d30`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001fbd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fd1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800201fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002020c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fc0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fd1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fe43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ff97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800201fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002020c`

## string_xrefs

- `0x18001fbf8`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fd0a`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fd45`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fde1`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18001fe1f`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x180020020`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18002003f`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x1800200ca`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18002021a`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

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
0x18001fb90  mov     [rsp-8+arg_10], r8
0x18001fb95  push    rbp
0x18001fb96  push    rbx
0x18001fb97  push    rsi
0x18001fb98  push    rdi
0x18001fb99  push    r12
0x18001fb9b  push    r13
0x18001fb9d  push    r14
0x18001fb9f  push    r15
0x18001fba1  lea     rbp, [rsp-7]
0x18001fba6  sub     rsp, 0A8h
0x18001fbad  mov     r14, r9
0x18001fbb0  mov     rdi, r8
0x18001fbb3  mov     r15d, edx
0x18001fbb6  mov     r13, rcx
0x18001fbb9  mov     [rbp+3Fh+var_70], 0
0x18001fbc1  mov     r12, [rbp+3Fh+pAudioFormat]
0x18001fbc8  mov     qword ptr [r12], 0
0x18001fbd0  movzx   esi, word ptr [r8+10h]
0x18001fbd5  lea     rcx, [rsi+12h]; cb
0x18001fbd9  call    cs:__imp_CoTaskMemAlloc
0x18001fbdf  mov     rbx, rax
0x18001fbe2  mov     [rbp+3Fh+pv], rax
0x18001fbe6  test    rax, rax
0x18001fbe9  jnz     short loc_18001FC1A
0x18001fbeb  mov     rcx, [rbp+47h]; this
0x18001fbef  mov     r14d, 88890008h
0x18001fbf5  mov     r9d, r14d; char *
0x18001fbf8  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fbff  mov     edx, 27Ah; void *
0x18001fc04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc09  nop
0x18001fc0a  xor     ecx, ecx; pv
0x18001fc0c  call    cs:__imp_CoTaskMemFree
0x18001fc12  nop
0x18001fc13  xor     ecx, ecx
0x18001fc15  jmp     loc_18001FCE6
0x18001fc1a  lea     r8, [rsi+12h]; Size
0x18001fc1e  mov     rdx, rdi; Src
0x18001fc21  mov     rcx, rbx; void *
0x18001fc24  call    memcpy_0
0x18001fc29  mov     [rbp+3Fh+var_50], rbx
0x18001fc2d  movaps  xmm0, xmmword ptr [r14]
0x18001fc31  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fc36  lea     r9, [rbp+3Fh+var_70]; struct tWAVEFORMATEX **
0x18001fc3a  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001fc3e  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fc41  mov     rcx, [r13+8]; this
0x18001fc45  call    ?GetMixFormat@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetMixFormat(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18001fc4a  xor     ecx, ecx
0x18001fc4c  mov     r14d, 88890008h
0x18001fc52  test    eax, eax
0x18001fc54  js      loc_18001FD03
0x18001fc5a  mov     rsi, [rbp+3Fh+var_70]
0x18001fc5e  cmp     [rbp+3Fh+arg_30], ecx
0x18001fc61  jnz     loc_18001FD2C
0x18001fc67  mov     rdi, [rbp+3Fh+arg_20]
0x18001fc6b  movaps  xmm0, xmmword ptr [rdi]
0x18001fc6e  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fc73  mov     [rsp+0E0h+var_B8], rcx; struct tWAVEFORMATEX **
0x18001fc78  mov     [rsp+0E0h+var_C0], rbx; struct tWAVEFORMATEX *
0x18001fc7d  mov     r9, rsi; struct tWAVEFORMATEX *
0x18001fc80  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fc83  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fc87  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fc8a  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fc8f  xor     ecx, ecx
0x18001fc91  test    eax, eax
0x18001fc93  jnz     loc_18001FD66
0x18001fc99  mov     rax, [rbp+3Fh+arg_28]
0x18001fc9d  movaps  xmm0, xmmword ptr [rax]
0x18001fca0  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fca5  mov     [rsp+0E0h+var_B0], rcx; __int64 *
0x18001fcaa  mov     [rsp+0E0h+var_B8], rcx; __int64 *
0x18001fcaf  mov     [rsp+0E0h+var_C0], rcx; int
0x18001fcb4  mov     r9, r12; struct tWAVEFORMATEX **
0x18001fcb7  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001fcbb  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fcbe  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fcc1  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001fcc6  test    eax, eax
0x18001fcc8  js      short loc_18001FD3E
0x18001fcca  cmp     qword ptr [r12], 0
0x18001fccf  jz      loc_18001FD5C
0x18001fcd5  xor     r14d, r14d
0x18001fcd8  mov     rcx, [rbp+3Fh+pv]; pv
0x18001fcdc  call    cs:__imp_CoTaskMemFree
0x18001fce2  nop
0x18001fce3  mov     rcx, rsi; pv
0x18001fce6  call    cs:__imp_CoTaskMemFree
0x18001fcec  mov     eax, r14d
0x18001fcef  add     rsp, 0A8h
0x18001fcf6  pop     r15
0x18001fcf8  pop     r14
0x18001fcfa  pop     r13
0x18001fcfc  pop     r12
0x18001fcfe  pop     rdi
0x18001fcff  pop     rsi
0x18001fd00  pop     rbx
0x18001fd01  pop     rbp
0x18001fd02  retn
0x18001fd03  mov     rcx, [rbp+47h]; this
0x18001fd07  mov     r9d, r14d; char *
0x18001fd0a  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fd11  mov     edx, 28Fh; void *
0x18001fd16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd1b  nop
0x18001fd1c  mov     rcx, rbx; pv
0x18001fd1f  call    cs:__imp_CoTaskMemFree
0x18001fd25  nop
0x18001fd26  mov     rcx, [rbp+3Fh+var_70]
0x18001fd2a  jmp     short loc_18001FCE6
0x18001fd2c  cmp     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, ecx; int g_PerformStrictConnectorMatchOnMatchFormat
0x18001fd32  jz      loc_18001FC67
0x18001fd38  mov     rdi, [rbp+3Fh+arg_20]
0x18001fd3c  jmp     short loc_18001FD6F
0x18001fd3e  mov     rcx, [rbp+47h]; this
0x18001fd42  mov     r9d, r14d; char *
0x18001fd45  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fd4c  mov     edx, 297h; void *
0x18001fd51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd56  nop
0x18001fd57  mov     rcx, rbx
0x18001fd5a  jmp     short loc_18001FCDC
0x18001fd5c  mov     edx, 298h
0x18001fd61  jmp     loc_180020217
0x18001fd66  cmp     [rbp+3Fh+arg_30], ecx
0x18001fd69  jz      loc_180020212
0x18001fd6f  mov     [rbp+3Fh+pAudioFormat], rcx
0x18001fd76  mov     rbx, [rbp+3Fh+arg_28]
0x18001fd7a  movaps  xmm0, xmmword ptr [rbx]
0x18001fd7d  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fd82  lea     rax, [rbp+3Fh+pAudioFormat]
0x18001fd89  mov     [rsp+0E0h+var_C0], rax; struct tWAVEFORMATEX **
0x18001fd8e  lea     r9, [rbp+3Fh+var_80]; struct _GUID
0x18001fd92  mov     r8, [rbp+3Fh+arg_10]; struct tWAVEFORMATEX *
0x18001fd96  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fd99  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fd9c  call    ?DeriveConnectorFormatWithHighestBitDepthFromStreamFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUtWAVEFORMATEX@@U_GUID@@PEAPEAU3@@Z; DeriveConnectorFormatWithHighestBitDepthFromStreamFormat(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX *,_GUID,tWAVEFORMATEX * *)
0x18001fda1  xor     ecx, ecx
0x18001fda3  test    eax, eax
0x18001fda5  js      loc_18001FFA2
0x18001fdab  mov     [rbp+3Fh+ppIAudioMediaType], rcx
0x18001fdaf  mov     qword ptr [rbp+3Fh+var_90.Data1], rcx
0x18001fdb3  mov     [rbp+3Fh+var_A0], rcx
0x18001fdb7  mov     rbx, [rbp+3Fh+pAudioFormat]
0x18001fdbe  movzx   edx, word ptr [rbx+10h]
0x18001fdc2  add     edx, 12h; cbAudioFormatSize
0x18001fdc5  lea     r8, [rbp+3Fh+ppIAudioMediaType]; ppIAudioMediaType
0x18001fdc9  mov     rcx, rbx; pAudioFormat
0x18001fdcc  call    CreateAudioMediaType
0x18001fdd1  test    eax, eax
0x18001fdd3  jns     short loc_18001FE4E
0x18001fdd5  mov     edx, 2A9h
0x18001fdda  jmp     short loc_18001FDE1
0x18001fddc  mov     edx, 2B6h; void *
0x18001fde1  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fde8  mov     r9d, r14d; char *
0x18001fdeb  mov     rcx, [rbp+47h]; this
0x18001fdef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdf4  nop
0x18001fdf5  lea     rcx, [rbp+3Fh+var_A0]
0x18001fdf9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fdfe  nop
0x18001fdff  lea     rcx, [rbp+3Fh+var_90]
0x18001fe03  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe08  nop
0x18001fe09  lea     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001fe0d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001fe12  nop
0x18001fe13  mov     rcx, rbx
0x18001fe16  jmp     short loc_18001FE43
0x18001fe18  mov     rcx, [rbp+47h]; this
0x18001fe1c  mov     r9d, r14d; char *
0x18001fe1f  lea     r8, aAvcoreAudiocor_11; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18001fe26  mov     edx, 2C1h; void *
0x18001fe2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe30  nop
0x18001fe31  mov     rcx, [rbp+3Fh+ppIAudioMediaType]; pv
0x18001fe35  call    cs:__imp_CoTaskMemFree
0x18001fe3b  nop
0x18001fe3c  mov     rcx, [rbp+3Fh+pAudioFormat]; pv
0x18001fe43  call    cs:__imp_CoTaskMemFree
0x18001fe49  jmp     loc_18001FCD8
0x18001fe4e  movaps  xmm0, xmmword ptr [rdi]
0x18001fe51  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fe56  lea     rax, [rbp+3Fh+var_90]
0x18001fe5a  mov     [rsp+0E0h+var_C0], rax; struct IAudioMediaType **
0x18001fe5f  mov     r9, [rbp+3Fh+ppIAudioMediaType]; struct IAudioMediaType *
0x18001fe63  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fe66  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fe6a  mov     rcx, [r13+8]; this
0x18001fe6e  call    ?DeriveDevicePipeFormatFromConnectorFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@@Z; EffectPack::DeriveDevicePipeFormatFromConnectorFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *)
0x18001fe73  test    eax, eax
0x18001fe75  jns     short loc_18001FE81
0x18001fe77  mov     edx, 2ACh
0x18001fe7c  jmp     loc_18001FDE1
0x18001fe81  movaps  xmm0, xmmword ptr [rdi]
0x18001fe84  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fe89  mov     [rsp+0E0h+var_B8], 0; struct IAudioMediaType **
0x18001fe92  lea     rax, [rbp+3Fh+var_A0]
0x18001fe96  mov     [rsp+0E0h+var_C0], rax; struct IAudioMediaType **
0x18001fe9b  mov     r9, qword ptr [rbp+3Fh+var_90.Data1]; struct IAudioMediaType *
0x18001fe9f  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001fea2  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fea6  mov     rcx, [r13+8]; this
0x18001feaa  call    ?DeriveMixFormatFromDevicePipeFormat@EffectPack@@QEAAJU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIAudioMediaType@@PEAPEAU4@3@Z; EffectPack::DeriveMixFormatFromDevicePipeFormat(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IAudioMediaType *,IAudioMediaType * *,IAudioMediaType * *)
0x18001feaf  test    eax, eax
0x18001feb1  jns     short loc_18001FEBD
0x18001feb3  mov     edx, 2AFh
0x18001feb8  jmp     loc_18001FDE1
0x18001febd  mov     rcx, [rbp+3Fh+var_A0]
0x18001fec1  mov     rax, [rcx]
0x18001fec4  mov     rax, [rax+28h]
0x18001fec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fecd  movaps  xmm0, xmmword ptr [rdi]
0x18001fed0  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001fed5  mov     [rsp+0E0h+var_B8], 0; struct tWAVEFORMATEX **
0x18001fede  mov     rcx, [rbp+3Fh+arg_10]
0x18001fee2  mov     [rsp+0E0h+var_C0], rcx; struct tWAVEFORMATEX *
0x18001fee7  mov     r9, rax; struct tWAVEFORMATEX *
0x18001feea  mov     r8d, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001feed  lea     rdx, [rbp+3Fh+var_80]; struct _GUID
0x18001fef1  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001fef4  call    ?IsStreamFormatSupportedForMixFormat@@YAJPEAUEndpointCharacteristicsDescriptor@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@3PEAPEAU4@@Z; IsStreamFormatSupportedForMixFormat(EndpointCharacteristicsDescriptor *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001fef9  test    eax, eax
0x18001fefb  jz      short loc_18001FF07
0x18001fefd  mov     edx, 2B2h
0x18001ff02  jmp     loc_18001FDE1
0x18001ff07  mov     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001ff0b  mov     rax, [rcx]
0x18001ff0e  mov     rax, [rax+28h]
0x18001ff12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff17  mov     rcx, rax; Src
0x18001ff1a  mov     rdx, r12; struct tWAVEFORMATEX **
0x18001ff1d  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001ff22  test    eax, eax
0x18001ff24  jns     short loc_18001FF30
0x18001ff26  mov     edx, 2B5h
0x18001ff2b  jmp     loc_18001FDE1
0x18001ff30  cmp     qword ptr [r12], 0
0x18001ff35  jz      loc_18001FDDC
0x18001ff3b  lea     rcx, [rbp+3Fh+var_A0]
0x18001ff3f  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff44  nop
0x18001ff45  lea     rcx, [rbp+3Fh+var_90]
0x18001ff49  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff4e  nop
0x18001ff4f  lea     rcx, [rbp+3Fh+ppIAudioMediaType]
0x18001ff53  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff58  nop
0x18001ff59  mov     rcx, rbx
0x18001ff5c  jmp     short loc_18001FF97
0x18001ff5e  lea     rcx, [rbp+3Fh+var_90]
0x18001ff62  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff67  nop
0x18001ff68  lea     rcx, [rbp+3Fh+var_A0]
0x18001ff6c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff71  nop
0x18001ff72  lea     rcx, [rbp+3Fh+arg_10]
0x18001ff76  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18001ff7b  nop
0x18001ff7c  mov     rcx, rdi; pv
0x18001ff7f  call    cs:__imp_CoTaskMemFree
0x18001ff85  nop
0x18001ff86  mov     rcx, rbx; pv
0x18001ff89  call    cs:__imp_CoTaskMemFree
0x18001ff8f  nop
0x18001ff90  mov     rcx, [rbp+3Fh+pAudioFormat]; pv
0x18001ff97  call    cs:__imp_CoTaskMemFree
0x18001ff9d  jmp     loc_18001FCD5
0x18001ffa2  cmp     cs:?g_PerformStrictConnectorMatchOnMatchFormat@@3HA, ecx; int g_PerformStrictConnectorMatchOnMatchFormat
0x18001ffa8  jnz     loc_180020205
0x18001ffae  cmp     eax, r14d
0x18001ffb1  jnz     loc_180020205
0x18001ffb7  mov     [rbp+3Fh+ppIAudioMediaType], rcx
0x18001ffbb  movaps  xmm0, xmmword ptr [rbx]
0x18001ffbe  movdqa  xmmword ptr [rbp+3Fh+var_80.Data1], xmm0
0x18001ffc3  mov     [rsp+0E0h+var_B0], rcx; __int64 *
0x18001ffc8  mov     [rsp+0E0h+var_B8], rcx; __int64 *
0x18001ffcd  mov     [rsp+0E0h+var_C0], rcx; int
0x18001ffd2  lea     r9, [rbp+3Fh+ppIAudioMediaType]; struct tWAVEFORMATEX **
0x18001ffd6  lea     r8, [rbp+3Fh+var_80]; struct _GUID
0x18001ffda  mov     edx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18001ffdd  mov     rcx, r13; struct EndpointCharacteristicsDescriptor *
0x18001ffe0  call    ?GetDeviceDefaults@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@3PEA_J4@Z; GetDeviceDefaults(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *,tWAVEFORMATEX * *,__int64 *,__int64 *)
0x18001ffe5  test    eax, eax
0x18001ffe7  js      loc_18001FE18
0x18001ffed  mov     rbx, [rbp+3Fh+ppIAudioMediaType]
0x18001fff1  mov     eax, [rbx+4]
0x18001fff4  mov     rdi, [rbp+3Fh+pv]
0x18001fff8  cmp     [rdi+4], eax
0x18001fffb  jz      loc_1800201FB
0x180020001  mov     qword ptr [rbp+3Fh+var_80.Data1], 0
0x180020009  lea     rdx, [rbp+3Fh+var_80]; struct tWAVEFORMATEX **
0x18002000d  mov     rcx, rbx; Src
0x180020010  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180020015  test    eax, eax
0x180020017  jns     short loc_180020063
0x180020019  mov     rcx, [rbp+47h]; this
  ... truncated ...
```
