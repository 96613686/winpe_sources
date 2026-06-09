# IPxlatInterface::UpdateTranslationState(void)

- ea: `0x1800172a4`
- end: `0x1800176c8`
- name: `?UpdateTranslationState@IPxlatInterface@@AEAAXXZ`
- size: `1060`
- prototype: `void __fastcall(IPxlatInterface *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180015340`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x180011f3c`
- `0x180012388`
- `0x180012728`
- `0x1800127fc`
- `0x180015a1c`
- `0x180016f84`
- `0x1800172a4`
- `0x180017930`
- `0x1800179d0`

## import_xrefs

- `NSI!NsiSetAllParameters` at `0x18001731f`
- `NSI!NsiSetAllParameters` at `0x180017514`
- `NSI!NsiSetAllParameters` at `0x18001731f`
- `NSI!NsiSetAllParameters` at `0x180017514`

## string_xrefs

- `0x18001741b`: `Translation already disabled`
- `0x180017343`: `Could not delete IPxlat instance`
- `0x18001766b`: `Translation already enabled`
- `0x180017538`: `Could not create IPxlat instance`

## pseudocode

```c
void __fastcall IPxlatInterface::UpdateTranslationState(IPxlatInterface *this)
{
  char v2; // al
  int v3; // eax
  int v4; // edx
  int v5; // r14d
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rdx
  char *v10; // rax
  const char *v11; // rax
  __int64 *v12; // rax
  unsigned __int8 IsEnabled; // al
  char v14; // r9
  _OWORD *v15; // r15
  int v16; // edx
  char v17; // r8
  __int128 v18; // xmm1
  int v19; // ecx
  int v20; // eax
  int v21; // edx
  int v22; // ecx
  int v23; // r14d
  const char *v24; // rax
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  _DWORD v31[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[36]; // [rsp+88h] [rbp-78h] BYREF
  char v34; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  int *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  char *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  int *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  int *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  char *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  __int64 *v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]

  v30 = *(_QWORD *)this;
  v2 = *((_BYTE *)this + 70);
  if ( *((_BYTE *)this + 73) )
  {
    if ( !v2 || !*((_BYTE *)this + 72) )
    {
      v3 = NsiSetAllParameters(1, 3, NPI_MS_WINNAT_MODULEID);
      v5 = v3;
      if ( v3 && v3 != 1168 )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
          McTemplateU0sqx_EventWriteTransfer(
            *(_QWORD *)this,
            v4,
            (unsigned int)"Could not delete IPxlat instance",
            v3,
            *(_QWORD *)this);
        return;
      }
      IPxlatInterface::UnPlumbSyntheticIpAndRoute(this);
      *((_BYTE *)this + 73) = 0;
      if ( v5 )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
          return;
        v25 = *(_QWORD *)this;
        v11 = "Translation already disabled";
        *(_QWORD *)v33 = 29;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl'::`2'::impl) )
          IPxlatTelemetry::IPxlatTranslationStopped<_GUID &>((char *)this + 208);
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl'::`2'::impl) )
        {
          v6 = 4;
          if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) == 0 )
            return;
          v8 = 2;
          v25 = *(_QWORD *)this;
          v9 = IPXLATCFG_TRANSLATION_STOPPED_EVENT;
          *(_QWORD *)v33 = 8;
          *((_QWORD *)&v32 + 1) = &v25;
          v10 = (char *)v31;
          goto LABEL_43;
        }
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
          return;
        v25 = *(_QWORD *)this;
        v11 = "Translation disabled";
        *(_QWORD *)v33 = 21;
      }
      *((_QWORD *)&v32 + 1) = v11;
      v12 = &v25;
      *(_QWORD *)&v33[16] = 8;
LABEL_42:
      *(_QWORD *)&v33[8] = v12;
      v9 = IPXLATCFG_INTERFACE_INFO_EVENT;
      v10 = (char *)v31;
      v8 = 3;
LABEL_43:
      McGenEventWrite_EventWriteTransfer(v6, v9, v7, v8, v10);
    }
  }
  else if ( v2 && *((_BYTE *)this + 72) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl'::`2'::impl);
    v14 = *((_BYTE *)this + 69);
    v15 = (_OWORD *)((char *)this + 36);
    v16 = *((_DWORD *)this + 33);
    v17 = *((_BYTE *)this + 52);
    v18 = *(_OWORD *)((char *)this + 53);
    v31[1] = *((_DWORD *)this + 32);
    v31[0] = v16;
    *(_QWORD *)&v33[1] = 0;
    v33[0] = v14;
    v32 = v18;
    if ( IsEnabled )
    {
      v19 = *((_DWORD *)this + 7);
      memset(&v33[9], 0, 27);
      v33[18] = v17;
      *(_OWORD *)&v33[2] = *v15;
      if ( (unsigned int)(v19 - 243) > 1 && v19 != 237 )
        *(_OWORD *)&v33[20] = *(_OWORD *)((char *)this + 136);
    }
    else
    {
      *(_OWORD *)&v33[4] = 0;
      v33[18] = v17;
      *(_OWORD *)&v33[2] = *v15;
    }
    v20 = NsiSetAllParameters(1, 1, NPI_MS_WINNAT_MODULEID);
    v23 = v20;
    if ( !v20 || v20 == 5010 )
    {
      IPxlatInterface::PlumbSyntheticIpAndRoute(this);
      *((_BYTE *)this + 73) = 1;
      if ( v23 )
      {
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
          return;
        v26 = *(_QWORD *)this;
        v24 = "Translation already enabled";
        *(_QWORD *)v33 = 28;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl'::`2'::impl) )
          IPxlatTelemetry::IPxlatTranslationStarted<_GUID &>((char *)this + 208);
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl'::`2'::impl) )
        {
          v6 = 4;
          if ( (Microsoft_Windows_IPxlatCfgEnableBits & 4) == 0 )
            return;
          LODWORD(v25) = *((_DWORD *)this + 33);
          v8 = 8;
          v28 = *((unsigned __int8 *)this + 52);
          v26 = *(_QWORD *)this;
          v35 = &v26;
          v37 = &v27;
          v41 = &v28;
          v43 = &v29;
          v45 = (char *)this + 136;
          v47 = &v25;
          v10 = &v34;
          v29 = 16;
          v27 = 16;
          v40 = 16;
          v46 = 16;
          v9 = IPXLATCFG_TRANSLATION_STARTED_EVENT;
          v36 = 8;
          v38 = 4;
          v39 = (char *)this + 36;
          v42 = 4;
          v44 = 4;
          v48 = 4;
          goto LABEL_43;
        }
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) == 0 )
          return;
        v26 = *(_QWORD *)this;
        v24 = "Translation enabled";
        *(_QWORD *)v33 = 20;
      }
      *((_QWORD *)&v32 + 1) = v24;
      v12 = &v26;
      *(_QWORD *)&v33[16] = 8;
      goto LABEL_42;
    }
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
      McTemplateU0sqx_EventWriteTransfer(
        v22,
        v21,
        (unsigned int)"Could not create IPxlat instance",
        v20,
        *(_QWORD *)this);
  }
}

```

## disassembly

```asm
0x1800172a4  push    rbp
0x1800172a6  push    rbx
0x1800172a7  push    rdi
0x1800172a8  push    r12
0x1800172aa  push    r14
0x1800172ac  push    r15
0x1800172ae  lea     rbp, [rsp-48h]
0x1800172b3  sub     rsp, 148h
0x1800172ba  mov     rax, cs:__security_cookie
0x1800172c1  xor     rax, rsp
0x1800172c4  mov     [rbp+70h+var_40], rax
0x1800172c8  mov     rax, [rcx]
0x1800172cb  xor     r12d, r12d
0x1800172ce  mov     rbx, rcx
0x1800172d1  mov     [rsp+170h+var_108], rax
0x1800172d6  mov     al, [rcx+46h]
0x1800172d9  cmp     [rcx+49h], r12b
0x1800172dd  jz      loc_18001742C
0x1800172e3  test    al, al
0x1800172e5  jz      short loc_1800172F1
0x1800172e7  cmp     [rcx+48h], r12b
0x1800172eb  jnz     loc_1800176AB
0x1800172f1  mov     edi, 8
0x1800172f6  mov     [rsp+170h+var_138], r12d
0x1800172fb  mov     [rsp+170h+var_140], r12
0x180017300  lea     rax, [rsp+170h+var_108]
0x180017305  mov     [rsp+170h+var_148], edi
0x180017309  lea     r8, NPI_MS_WINNAT_MODULEID
0x180017310  mov     [rsp+170h+var_150], rax
0x180017315  lea     r9d, [rdi+3]
0x180017319  lea     edx, [rdi-5]
0x18001731c  lea     ecx, [rdi-7]
0x18001731f  call    cs:__imp_NsiSetAllParameters
0x180017325  mov     r14d, eax
0x180017328  test    eax, eax
0x18001732a  jz      short loc_180017354
0x18001732c  cmp     eax, 490h
0x180017331  jz      short loc_180017354
0x180017333  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18001733a  jz      loc_1800176AB
0x180017340  mov     rcx, [rbx]
0x180017343  lea     r8, aCouldNotDelete_3; "Could not delete IPxlat instance"
0x18001734a  mov     [rsp+170h+var_150], rcx
0x18001734f  jmp     loc_180017544
0x180017354  mov     rcx, rbx; this
0x180017357  call    ?UnPlumbSyntheticIpAndRoute@IPxlatInterface@@AEAAXXZ; IPxlatInterface::UnPlumbSyntheticIpAndRoute(void)
0x18001735c  mov     [rbx+49h], r12b
0x180017360  test    r14d, r14d
0x180017363  jnz     loc_180017406
0x180017369  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl(void)'::`2'::impl
0x180017370  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(void)
0x180017375  test    al, al
0x180017377  jz      short loc_180017385
0x180017379  lea     rcx, [rbx+0D0h]
0x180017380  call    ??$IPxlatTranslationStopped@AEAU_GUID@@@IPxlatTelemetry@@SAXAEAU_GUID@@@Z; IPxlatTelemetry::IPxlatTranslationStopped<_GUID &>(_GUID &)
0x180017385  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl(void)'::`2'::impl
0x18001738c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(void)
0x180017391  test    al, al
0x180017393  jz      short loc_1800173D0
0x180017395  mov     ecx, 4
0x18001739a  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, cl
0x1800173a0  jz      loc_1800176AB
0x1800173a6  mov     rax, [rbx]
0x1800173a9  lea     r9d, [rcx-2]
0x1800173ad  mov     [rsp+170h+var_130], rax
0x1800173b2  lea     rdx, IPXLATCFG_TRANSLATION_STOPPED_EVENT
0x1800173b9  lea     rax, [rsp+170h+var_130]
0x1800173be  mov     qword ptr [rbp+70h+var_F0+8], rdi
0x1800173c2  mov     qword ptr [rbp+70h+var_F0], rax
0x1800173c6  lea     rax, [rsp+170h+var_100]
0x1800173cb  jmp     loc_1800176A1
0x1800173d0  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x1800173d7  jz      loc_1800176AB
0x1800173dd  mov     rax, [rbx]
0x1800173e0  mov     [rsp+170h+var_130], rax
0x1800173e5  lea     rax, aTranslationDis; "Translation disabled"
0x1800173ec  mov     qword ptr [rbp+70h+var_F0+8], 15h
0x1800173f4  mov     qword ptr [rbp+70h+var_F0], rax
0x1800173f8  lea     rax, [rsp+170h+var_130]
0x1800173fd  mov     qword ptr [rbp+70h+var_D8], rdi
0x180017401  jmp     loc_18001768B
0x180017406  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18001740d  jz      loc_1800176AB
0x180017413  mov     rax, [rbx]
0x180017416  mov     [rsp+170h+var_130], rax
0x18001741b  lea     rax, aTranslationAlr; "Translation already disabled"
0x180017422  mov     qword ptr [rbp+70h+var_F0+8], 1Dh
0x18001742a  jmp     short loc_1800173F4
0x18001742c  test    al, al
0x18001742e  jz      loc_1800176AB
0x180017434  cmp     [rcx+48h], r12b
0x180017438  jz      loc_1800176AB
0x18001743e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::GetImpl(void)'::`2'::impl
0x180017445  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_RandomLocalAddress>::__private_IsEnabled(void)
0x18001744a  mov     r9b, [rbx+45h]
0x18001744e  xorps   xmm0, xmm0
0x180017451  mov     ecx, [rbx+80h]
0x180017457  lea     r15, [rbx+24h]
0x18001745b  mov     edx, [rbx+84h]
0x180017461  mov     r8b, [r15+10h]
0x180017465  movups  xmm1, xmmword ptr [rbx+35h]
0x180017469  movups  xmmword ptr [rsp+71h], xmm0
0x18001746e  mov     [rsp+170h+var_FC], ecx
0x180017472  mov     [rsp+170h+var_100], edx
0x180017476  movups  [rbp+70h+var_F0+1], xmm0
0x18001747a  mov     byte ptr [rbp+70h+var_F0+8], r9b
0x18001747e  movdqu  xmmword ptr [rsp+78h], xmm1
0x180017484  test    al, al
0x180017486  jz      short loc_1800174CE
0x180017488  mov     ecx, [rbx+1Ch]
0x18001748b  movups  xmmword ptr [rbp-6Fh], xmm0
0x18001748f  mov     byte ptr [rbp+70h+var_D8+2], r8b
0x180017493  movups  [rbp+70h+var_D8+4], xmm0
0x180017497  lea     eax, [rcx-0F3h]
0x18001749d  movups  xmm0, xmmword ptr [r15]
0x1800174a1  movdqu  [rbp+70h+var_F0+0Ah], xmm0
0x1800174a6  cmp     eax, 1
0x1800174a9  jbe     short loc_1800174BF
0x1800174ab  cmp     ecx, 0EDh
0x1800174b1  jz      short loc_1800174BF
0x1800174b3  movups  xmm0, xmmword ptr [rbx+88h]
0x1800174ba  movdqu  [rbp+70h+var_D8+4], xmm0
0x1800174bf  mov     [rsp+170h+var_138], 3Ch ; '<'
0x1800174c7  lea     rax, [rsp+170h+var_100]
0x1800174cc  jmp     short loc_1800174EC
0x1800174ce  movups  [rbp+70h+var_F0+0Ch], xmm0
0x1800174d2  mov     byte ptr [rbp+70h+var_D8+2], r8b
0x1800174d6  lea     rax, [rsp+170h+var_100]
0x1800174db  movups  xmm0, xmmword ptr [r15]
0x1800174df  mov     [rsp+170h+var_138], 2Ch ; ','
0x1800174e7  movdqu  [rbp+70h+var_F0+0Ah], xmm0
0x1800174ec  mov     [rsp+170h+var_140], rax
0x1800174f1  lea     r8, NPI_MS_WINNAT_MODULEID
0x1800174f8  mov     edi, 8
0x1800174fd  lea     rax, [rsp+170h+var_108]
0x180017502  mov     [rsp+170h+var_148], edi
0x180017506  mov     [rsp+170h+var_150], rax
0x18001750b  lea     edx, [rdi-7]
0x18001750e  mov     ecx, edx
0x180017510  lea     r9d, [rdi+3]
0x180017514  call    cs:__imp_NsiSetAllParameters
0x18001751a  mov     r14d, eax
0x18001751d  test    eax, eax
0x18001751f  jz      short loc_180017551
0x180017521  cmp     eax, 1392h
0x180017526  jz      short loc_180017551
0x180017528  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x18001752f  jz      loc_1800176AB
0x180017535  mov     rax, [rbx]
0x180017538  lea     r8, aCouldNotCreate_0; "Could not create IPxlat instance"
0x18001753f  mov     [rsp+170h+var_150], rax
0x180017544  mov     r9d, r14d
0x180017547  call    McTemplateU0sqx_EventWriteTransfer
0x18001754c  jmp     loc_1800176AB
0x180017551  mov     rcx, rbx; this
0x180017554  call    ?PlumbSyntheticIpAndRoute@IPxlatInterface@@AEAAXXZ; IPxlatInterface::PlumbSyntheticIpAndRoute(void)
0x180017559  mov     byte ptr [rbx+49h], 1
0x18001755d  test    r14d, r14d
0x180017560  jnz     loc_18001765A
0x180017566  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl(void)'::`2'::impl
0x18001756d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(void)
0x180017572  test    al, al
0x180017574  jz      short loc_180017582
0x180017576  lea     rcx, [rbx+0D0h]
0x18001757d  call    ??$IPxlatTranslationStarted@AEAU_GUID@@@IPxlatTelemetry@@SAXAEAU_GUID@@@Z; IPxlatTelemetry::IPxlatTranslationStarted<_GUID &>(_GUID &)
0x180017582  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::GetImpl(void)'::`2'::impl
0x180017589  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Events@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Events>::__private_IsEnabled(void)
0x18001758e  test    al, al
0x180017590  jz      loc_180017638
0x180017596  mov     ecx, 4
0x18001759b  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, cl
0x1800175a1  jz      loc_1800176AB
0x1800175a7  mov     eax, [rbx+84h]
0x1800175ad  lea     edx, [rcx+0Ch]
0x1800175b0  mov     dword ptr [rsp+170h+var_130], eax
0x1800175b4  mov     r9d, edi
0x1800175b7  movzx   eax, byte ptr [rbx+34h]
0x1800175bb  mov     [rsp+170h+var_118], eax
0x1800175bf  mov     rax, [rbx]
0x1800175c2  mov     [rsp+170h+var_128], rax
0x1800175c7  lea     rax, [rsp+170h+var_128]
0x1800175cc  mov     [rbp+70h+var_B0], rax
0x1800175d0  lea     rax, [rsp+170h+var_120]
0x1800175d5  mov     [rbp+70h+var_A0], rax
0x1800175d9  lea     rax, [rsp+170h+var_118]
0x1800175de  mov     [rbp+70h+var_80], rax
0x1800175e2  lea     rax, [rsp+170h+var_110]
0x1800175e7  mov     [rbp+70h+var_70], rax
0x1800175eb  lea     rax, [rbx+88h]
0x1800175f2  mov     [rbp+70h+var_60], rax
0x1800175f6  lea     rax, [rsp+170h+var_130]
0x1800175fb  mov     [rbp+70h+var_50], rax
0x1800175ff  lea     rax, [rbp+70h+var_C0]
0x180017603  mov     [rsp+170h+var_110], edx
0x180017607  mov     [rsp+170h+var_120], edx
0x18001760b  mov     [rbp+70h+var_88], rdx
0x18001760f  mov     [rbp+70h+var_58], rdx
0x180017613  lea     rdx, IPXLATCFG_TRANSLATION_STARTED_EVENT
0x18001761a  mov     [rbp+70h+var_A8], 8
0x180017622  mov     [rbp+70h+var_98], rcx
0x180017626  mov     [rbp+70h+var_90], r15
0x18001762a  mov     [rbp+70h+var_78], rcx
0x18001762e  mov     [rbp+70h+var_68], rcx
0x180017632  mov     [rbp+70h+var_48], rcx
0x180017636  jmp     short loc_1800176A1
0x180017638  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18001763f  jz      short loc_1800176AB
0x180017641  mov     rax, [rbx]
0x180017644  mov     [rsp+170h+var_128], rax
0x180017649  lea     rax, aTranslationEna; "Translation enabled"
0x180017650  mov     qword ptr [rbp+70h+var_F0+8], 14h
0x180017658  jmp     short loc_18001767A
0x18001765a  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x180017661  jz      short loc_1800176AB
0x180017663  mov     rax, [rbx]
0x180017666  mov     [rsp+170h+var_128], rax
0x18001766b  lea     rax, aTranslationAlr_0; "Translation already enabled"
0x180017672  mov     qword ptr [rbp+70h+var_F0+8], 1Ch
0x18001767a  mov     qword ptr [rbp+70h+var_F0], rax
0x18001767e  lea     rax, [rsp+170h+var_128]
0x180017683  mov     qword ptr [rbp+70h+var_D8], 8
0x18001768b  mov     [rbp+70h+var_E0], rax
0x18001768f  lea     rdx, IPXLATCFG_INTERFACE_INFO_EVENT
0x180017696  lea     rax, [rsp+170h+var_100]
0x18001769b  mov     r9d, 3
0x1800176a1  mov     [rsp+170h+var_150], rax
0x1800176a6  call    McGenEventWrite_EventWriteTransfer
0x1800176ab  mov     rcx, [rbp+70h+var_40]
0x1800176af  xor     rcx, rsp; StackCookie
0x1800176b2  call    __security_check_cookie
0x1800176b7  add     rsp, 148h
0x1800176be  pop     r15
0x1800176c0  pop     r14
0x1800176c2  pop     r12
0x1800176c4  pop     rdi
0x1800176c5  pop     rbx
0x1800176c6  pop     rbp
0x1800176c7  retn
```
