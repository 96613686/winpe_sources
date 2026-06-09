# FSConfiguration::GetProtectedData(uchar * *,ulong *)

- ea: `0x18003ce10`
- end: `0x18003d66c`
- name: `?GetProtectedData@FSConfiguration@@UEAAJPEAPEAEPEAK@Z`
- size: `2140`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005740`
- `0x180006a98`
- `0x180006cc0`
- `0x180007020`
- `0x18000723c`
- `0x18000d024`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18000d7c4`
- `0x180018418`
- `0x18001c63c`
- `0x180025a14`
- `0x180035f40`
- `0x18003ce10`
- `0x18003ea2c`
- `0x18003eb3c`
- `0x18003ee88`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ce3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ce3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d0e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d538`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d538`
- `CRYPT32!CryptProtectData` at `0x18003d0d7`
- `CRYPT32!CryptProtectData` at `0x18003d3b2`
- `CRYPT32!CryptProtectData` at `0x18003d0d7`
- `CRYPT32!CryptProtectData` at `0x18003d3b2`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18003cf54`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18003cf54`
- `MFPlat!MFGetAttributesAsBlob` at `0x18003cfc5`
- `MFPlat!MFGetAttributesAsBlob` at `0x18003cfc5`

## pseudocode

```c
__int64 __fastcall FSConfiguration::GetProtectedData(FSConfiguration *this, unsigned __int8 **a2, unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  unsigned __int8 *v7; // r14
  const char *v8; // rax
  HRESULT v9; // eax
  signed int v10; // esi
  __int64 v11; // rdx
  const struct std::nothrow_t *unique; // rax
  BYTE *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // r8
  signed int LastError; // eax
  __int64 v17; // rdx
  DWORD v18; // r12d
  const struct std::nothrow_t *v19; // rax
  DWORD *v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // ebx
  const void *v24; // rax
  const struct std::nothrow_t *v25; // rax
  DWORD *v26; // rax
  unsigned int v27; // ebx
  const void *v28; // rax
  DWORD *v29; // rax
  __int64 v30; // r8
  signed int v31; // eax
  const struct std::nothrow_t *v32; // rax
  DWORD *v33; // rax
  unsigned int v34; // ebx
  const void *v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rbx
  __int64 v39; // rax
  UINT8 *pBuf; // [rsp+50h] [rbp-19h] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-11h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-1h] BYREF
  UINT32 pcbBufSize; // [rsp+D0h] [rbp+67h] BYREF
  DWORD *v45; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int *v46; // [rsp+E0h] [rbp+77h]
  __int64 v47; // [rsp+E8h] [rbp+7Fh] BYREF

  v46 = a3;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  pBuf = 0;
  pDataIn = 0;
  pcbBufSize = 0;
  v7 = 0;
  pDataOut = 0;
  v45 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v8 = "true";
      if ( !*((_BYTE *)this + 88) )
        v8 = "false";
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        29,
        (unsigned int)&WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        (_DWORD)this,
        (__int64)v8);
    }
  }
  else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this);
  }
  if ( !a2 )
  {
    v9 = -2147467261;
    v10 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_80;
    v11 = 31;
    goto LABEL_11;
  }
  *a2 = 0;
  if ( !a3 )
  {
    v9 = -2147467261;
    v10 = -2147467261;
    if ( g_wppLevels )
    {
      v11 = 32;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v9);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  *a3 = 0;
  v9 = MFGetAttributesAsBlobSize(*((IMFAttributes **)this + 10), &pcbBufSize);
  v10 = v9;
  if ( v9 >= 0 )
  {
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v47, pcbBufSize);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&pBuf, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v47);
    v13 = pBuf;
    if ( !pBuf )
    {
      v9 = -2147024882;
      v10 = -2147024882;
      if ( g_wppLevels )
      {
        v11 = (unsigned int)((_DWORD)pBuf + 34);
        goto LABEL_11;
      }
      goto LABEL_80;
    }
    v9 = MFGetAttributesAsBlob(*((IMFAttributes **)this + 10), pBuf, pcbBufSize);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( g_wppLevels )
      {
        v11 = 35;
        goto LABEL_11;
      }
      goto LABEL_80;
    }
    pDataIn.cbData = pcbBufSize;
    pDataIn.pbData = v13;
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      v47 = 0;
      if ( (int)FSGetUserSidString(v14, (LPWSTR *)&v47) < 0 )
      {
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            37,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            pDataIn.pbData,
            pDataIn.cbData);
      }
      else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        WPP_SF_qSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          36,
          (unsigned int)&WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
          (_DWORD)this,
          v47,
          (char)pDataIn.pbData,
          pDataIn.cbData);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
    {
      if ( *((_BYTE *)this + 88) )
      {
        v18 = pDataIn.cbData + 40;
        v25 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v47, pDataIn.cbData + 40);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v45, v25);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v47);
        v26 = v45;
        if ( !v45 )
        {
          v21 = -2147024882;
          v10 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_79;
          v22 = 43;
          goto LABEL_44;
        }
        *v45 = v18;
        v7 = (unsigned __int8 *)v26;
        v26[1] = 0;
        v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
        v28 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
        if ( memcpy_s(v7 + 8, 0x20u, v28, v27) )
        {
          v21 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v22 = 44;
          goto LABEL_44;
        }
        if ( memcpy_s(v7 + 40, v18 - 40LL, pDataIn.pbData, pDataIn.cbData) )
        {
          v21 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v22 = 45;
          goto LABEL_44;
        }
      }
      else
      {
        if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          if ( !byte_18005E5A5 )
            goto LABEL_80;
          v17 = 38;
          goto LABEL_38;
        }
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qqDqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            39,
            v15,
            this,
            pDataIn.pbData,
            pDataIn.cbData,
            pDataOut.pbData,
            pDataOut.cbData);
        v18 = pDataOut.cbData + 40;
        v19 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v47, pDataOut.cbData + 40);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v45, v19);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v47);
        v20 = v45;
        if ( !v45 )
        {
          v21 = -2147024882;
          v10 = -2147024882;
          if ( !g_wppLevels )
          {
LABEL_79:
            v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
            goto LABEL_80;
          }
          v22 = 40;
LABEL_44:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v22,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            v21);
          goto LABEL_79;
        }
        *v45 = v18;
        v7 = (unsigned __int8 *)v20;
        v20[1] = 0;
        v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
        v24 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
        if ( memcpy_s(v7 + 8, 0x20u, v24, v23) )
        {
          v21 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v22 = 41;
          goto LABEL_44;
        }
        if ( memcpy_s(v7 + 40, v18 - 40LL, pDataOut.pbData, pDataOut.cbData) )
        {
          v21 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v22 = 42;
          goto LABEL_44;
        }
      }
      v29 = (DWORD *)*((_QWORD *)this + 8);
      *((_QWORD *)this + 8) = v7;
    }
    else
    {
      if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
      {
        v31 = GetLastError();
        v10 = v31;
        if ( v31 > 0 )
          v10 = (unsigned __int16)v31 | 0x80070000;
        if ( !byte_18005E5A5 )
          goto LABEL_80;
        v17 = 46;
LABEL_38:
        WPP_SF_qDqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v17,
          &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
          this,
          v10,
          pDataIn.pbData,
          pDataIn.cbData);
        goto LABEL_80;
      }
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qqDqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          47,
          v30,
          this,
          pDataIn.pbData,
          pDataIn.cbData,
          pDataOut.pbData,
          pDataOut.cbData);
      v18 = pDataOut.cbData + 40;
      v32 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v47, pDataOut.cbData + 40);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v45, v32);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v47);
      v33 = v45;
      if ( !v45 )
      {
        v21 = -2147024882;
        v10 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_79;
        v22 = 48;
        goto LABEL_44;
      }
      *v45 = v18;
      v7 = (unsigned __int8 *)v33;
      v33[1] = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
      v35 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
      if ( memcpy_s(v7 + 8, 0x20u, v35, v34) )
      {
        v21 = -1072875845;
        v10 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_79;
        v22 = 49;
        goto LABEL_44;
      }
      if ( memcpy_s(v7 + 40, v18 - 40LL, pDataOut.pbData, pDataOut.cbData) )
      {
        v21 = -1072875845;
        v10 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_79;
        v22 = 50;
        goto LABEL_44;
      }
      v29 = (DWORD *)*((_QWORD *)this + 8);
      *((_QWORD *)this + 8) = v7;
    }
    v45 = v29;
    *((_DWORD *)this + 18) = v18;
    *a2 = v7;
    *v46 = *((_DWORD *)this + 18);
    goto LABEL_79;
  }
  if ( g_wppLevels )
  {
    v11 = 33;
    goto LABEL_11;
  }
LABEL_80:
  LocalFree(pDataOut.pbData);
  if ( v10 >= 0 )
  {
    if ( v7 )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
        v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
        WPP_SF_qDDDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, *(_DWORD *)v7, *((_DWORD *)v7 + 1), v37, v36);
      }
    }
    else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
LABEL_87:
      v38 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
      WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, v39, v38);
    }
  }
  else if ( byte_18005E5A5 )
  {
    goto LABEL_87;
  }
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v45);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
  LeaveCriticalSection(v3);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003ce10  mov     [rsp-8+arg_10], r8
0x18003ce15  push    rbp
0x18003ce16  push    rbx
0x18003ce17  push    rsi
0x18003ce18  push    rdi
0x18003ce19  push    r12
0x18003ce1b  push    r13
0x18003ce1d  push    r14
0x18003ce1f  push    r15
0x18003ce21  lea     rbp, [rsp-1Fh]
0x18003ce26  sub     rsp, 88h
0x18003ce2d  lea     r12, [rcx+10h]
0x18003ce31  mov     rdi, rcx
0x18003ce34  mov     rcx, r12; lpCriticalSection
0x18003ce37  mov     rbx, r8
0x18003ce3a  mov     r13, rdx
0x18003ce3d  call    cs:__imp_EnterCriticalSection
0x18003ce43  xor     esi, esi
0x18003ce45  xorps   xmm0, xmm0
0x18003ce48  xorps   xmm1, xmm1
0x18003ce4b  mov     [rbp+57h+pBuf], rsi
0x18003ce4f  movups  xmmword ptr [rbp+57h+pDataIn.cbData], xmm0
0x18003ce53  mov     [rbp+57h+pcbBufSize], esi
0x18003ce56  mov     r14d, esi
0x18003ce59  movups  xmmword ptr [rbp+57h+var_58.cbData], xmm1
0x18003ce5d  mov     [rbp+57h+arg_8], rsi
0x18003ce61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18003ce68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18003ce6d  test    al, al
0x18003ce6f  jz      short loc_18003CEBA
0x18003ce71  mov     r15b, 8
0x18003ce74  cmp     cs:byte_18005E5A5, r15b
0x18003ce7b  jb      short loc_18003CEE8
0x18003ce7d  cmp     [rdi+58h], sil
0x18003ce81  lea     rcx, aFalse; "false"
0x18003ce88  lea     rax, aTrue_0; "true"
0x18003ce8f  mov     r9, rdi
0x18003ce92  cmovz   rax, rcx
0x18003ce96  lea     edx, [rsi+1Dh]
0x18003ce99  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cea0  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003cea7  mov     [rsp+0C0h+pPromptStruct], rax
0x18003ceac  mov     rcx, [rcx+0D8h]
0x18003ceb3  call    WPP_SF_qs
0x18003ceb8  jmp     short loc_18003CEE8
0x18003ceba  mov     r15b, 8
0x18003cebd  cmp     cs:byte_18005E5A5, r15b
0x18003cec4  jb      short loc_18003CEE8
0x18003cec6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cecd  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003ced4  mov     edx, 1Eh
0x18003ced9  mov     r9, rdi
0x18003cedc  mov     rcx, [rcx+0D8h]
0x18003cee3  call    WPP_SF_q
0x18003cee8  test    r13, r13
0x18003ceeb  jnz     short loc_18003CF28
0x18003ceed  mov     eax, 80004003h
0x18003cef2  mov     esi, eax
0x18003cef4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cefb  jb      loc_18003D534
0x18003cf01  lea     edx, [r13+1Fh]
0x18003cf05  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf0c  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003cf13  mov     r9, rdi
0x18003cf16  mov     dword ptr [rsp+0C0h+pPromptStruct], eax
0x18003cf1a  mov     rcx, [rcx+10h]
0x18003cf1e  call    WPP_SF_qD
0x18003cf23  jmp     loc_18003D534
0x18003cf28  mov     [r13+0], rsi
0x18003cf2c  test    rbx, rbx
0x18003cf2f  jnz     short loc_18003CF4A
0x18003cf31  mov     eax, 80004003h
0x18003cf36  mov     esi, eax
0x18003cf38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cf3f  jb      loc_18003D534
0x18003cf45  lea     edx, [rbx+20h]
0x18003cf48  jmp     short loc_18003CF05
0x18003cf4a  mov     [rbx], esi
0x18003cf4c  lea     rdx, [rbp+57h+pcbBufSize]; pcbBufSize
0x18003cf50  mov     rcx, [rdi+50h]; pAttributes
0x18003cf54  call    cs:__imp_MFGetAttributesAsBlobSize
0x18003cf5a  mov     esi, eax
0x18003cf5c  test    eax, eax
0x18003cf5e  jns     short loc_18003CF74
0x18003cf60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cf67  jb      loc_18003D534
0x18003cf6d  mov     edx, 21h ; '!'
0x18003cf72  jmp     short loc_18003CF05
0x18003cf74  mov     edx, [rbp+57h+pcbBufSize]
0x18003cf77  lea     rcx, [rbp+57h+arg_18]
0x18003cf7b  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003cf80  mov     rdx, rax
0x18003cf83  lea     rcx, [rbp+57h+pBuf]
0x18003cf87  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003cf8c  lea     rcx, [rbp+57h+arg_18]
0x18003cf90  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003cf95  mov     rbx, [rbp+57h+pBuf]
0x18003cf99  test    rbx, rbx
0x18003cf9c  jnz     short loc_18003CFBA
0x18003cf9e  mov     eax, 8007000Eh
0x18003cfa3  mov     esi, eax
0x18003cfa5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cfac  jb      loc_18003D534
0x18003cfb2  lea     edx, [rbx+22h]
0x18003cfb5  jmp     loc_18003CF05
0x18003cfba  mov     r8d, [rbp+57h+pcbBufSize]; cbBufSize
0x18003cfbe  mov     rdx, rbx; pBuf
0x18003cfc1  mov     rcx, [rdi+50h]; pAttributes
0x18003cfc5  call    cs:__imp_MFGetAttributesAsBlob
0x18003cfcb  mov     esi, eax
0x18003cfcd  test    eax, eax
0x18003cfcf  jns     short loc_18003CFE8
0x18003cfd1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cfd8  jb      loc_18003D534
0x18003cfde  mov     edx, 23h ; '#'
0x18003cfe3  jmp     loc_18003CF05
0x18003cfe8  cmp     cs:byte_18005E5A5, 10h
0x18003cfef  mov     eax, [rbp+57h+pcbBufSize]
0x18003cff2  mov     [rbp+57h+pDataIn.cbData], eax
0x18003cff5  mov     [rbp+57h+pDataIn.pbData], rbx
0x18003cff9  jb      loc_18003D09A
0x18003cfff  lea     rdx, [rbp+57h+arg_18]
0x18003d003  mov     [rbp+57h+arg_18], r14
0x18003d007  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003d00c  test    eax, eax
0x18003d00e  js      short loc_18003D056
0x18003d010  cmp     cs:byte_18005E5A5, r15b
0x18003d017  jb      short loc_18003D091
0x18003d019  mov     eax, [rbp+57h+pDataIn.cbData]
0x18003d01c  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003d023  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d02a  mov     edx, 24h ; '$'
0x18003d02f  mov     dword ptr [rsp+0C0h+pDataOut], eax
0x18003d033  mov     r9, rdi
0x18003d036  mov     rax, [rbp+57h+pDataIn.pbData]
0x18003d03a  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18003d03f  mov     rax, [rbp+57h+arg_18]
0x18003d043  mov     rcx, [rcx+0D8h]
0x18003d04a  mov     [rsp+0C0h+pPromptStruct], rax
0x18003d04f  call    WPP_SF_qSqD
0x18003d054  jmp     short loc_18003D091
0x18003d056  cmp     cs:byte_18005E5A5, r15b
0x18003d05d  jb      short loc_18003D091
0x18003d05f  mov     eax, [rbp+57h+pDataIn.cbData]
0x18003d062  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003d069  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d070  mov     edx, 25h ; '%'
0x18003d075  mov     [rsp+0C0h+dwFlags], eax
0x18003d079  mov     r9, rdi
0x18003d07c  mov     rax, [rbp+57h+pDataIn.pbData]
0x18003d080  mov     [rsp+0C0h+pPromptStruct], rax
0x18003d085  mov     rcx, [rcx+0D8h]
0x18003d08c  call    WPP_SF_qqD
0x18003d091  lea     rcx, [rbp+57h+arg_18]
0x18003d095  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d09a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18003d0a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18003d0a6  xor     ecx, ecx
0x18003d0a8  test    al, al
0x18003d0aa  jz      loc_18003D394
0x18003d0b0  cmp     [rdi+58h], cl
0x18003d0b3  jnz     loc_18003D293
0x18003d0b9  lea     rax, [rbp+57h+var_58]
0x18003d0bd  xor     r9d, r9d; pvReserved
0x18003d0c0  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x18003d0c5  xor     r8d, r8d; pOptionalEntropy
0x18003d0c8  mov     [rsp+0C0h+dwFlags], ecx; dwFlags
0x18003d0cc  xor     edx, edx; szDataDescr
0x18003d0ce  mov     [rsp+0C0h+pPromptStruct], rcx; pPromptStruct
0x18003d0d3  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18003d0d7  call    cs:__imp_CryptProtectData
0x18003d0dd  test    eax, eax
0x18003d0df  jnz     short loc_18003D13E
0x18003d0e1  call    cs:__imp_GetLastError
0x18003d0e7  mov     esi, eax
0x18003d0e9  test    eax, eax
0x18003d0eb  jle     short loc_18003D0F6
0x18003d0ed  movzx   esi, ax
0x18003d0f0  or      esi, 80070000h
0x18003d0f6  cmp     cs:byte_18005E5A5, 1
0x18003d0fd  jb      loc_18003D534
0x18003d103  mov     edx, 26h ; '&'
0x18003d108  mov     eax, [rbp+57h+pDataIn.cbData]
0x18003d10b  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003d112  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d119  mov     r9, rdi
0x18003d11c  mov     dword ptr [rsp+0C0h+pDataOut], eax
0x18003d120  mov     rax, [rbp+57h+pDataIn.pbData]
0x18003d124  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18003d129  mov     rcx, [rcx+0D8h]
0x18003d130  mov     dword ptr [rsp+0C0h+pPromptStruct], esi
0x18003d134  call    WPP_SF_qDqD
0x18003d139  jmp     loc_18003D534
0x18003d13e  cmp     cs:byte_18005E5A5, r15b
0x18003d145  jb      short loc_18003D182
0x18003d147  mov     eax, [rbp+57h+var_58.cbData]
0x18003d14a  mov     edx, 27h ; '''
0x18003d14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d156  mov     r9, rdi
0x18003d159  mov     dword ptr [rsp+0C0h+var_88], eax
0x18003d15d  mov     rax, [rbp+57h+var_58.pbData]
0x18003d161  mov     [rsp+0C0h+pDataOut], rax
0x18003d166  mov     eax, [rbp+57h+pDataIn.cbData]
0x18003d169  mov     rcx, [rcx+0D8h]
0x18003d170  mov     [rsp+0C0h+dwFlags], eax
0x18003d174  mov     rax, [rbp+57h+pDataIn.pbData]
0x18003d178  mov     [rsp+0C0h+pPromptStruct], rax
0x18003d17d  call    WPP_SF_qqDqD
0x18003d182  mov     r12d, [rbp+57h+var_58.cbData]
0x18003d186  lea     rcx, [rbp+57h+arg_18]
0x18003d18a  add     r12d, 28h ; '('
0x18003d18e  mov     edx, r12d
0x18003d191  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003d196  mov     rdx, rax
0x18003d199  lea     rcx, [rbp+57h+arg_8]
0x18003d19d  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003d1a2  lea     rcx, [rbp+57h+arg_18]
0x18003d1a6  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003d1ab  mov     rax, [rbp+57h+arg_8]
0x18003d1af  test    rax, rax
0x18003d1b2  jnz     short loc_18003D1F0
0x18003d1b4  mov     eax, 8007000Eh
0x18003d1b9  mov     esi, eax
0x18003d1bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d1c2  jb      loc_18003D530
0x18003d1c8  mov     edx, 28h ; '('
0x18003d1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1d4  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003d1db  mov     r9, rdi
0x18003d1de  mov     dword ptr [rsp+0C0h+pPromptStruct], eax
0x18003d1e2  mov     rcx, [rcx+10h]
0x18003d1e6  call    WPP_SF_qD
0x18003d1eb  jmp     loc_18003D530
0x18003d1f0  mov     [rax], r12d
0x18003d1f3  mov     r14, rax
0x18003d1f6  mov     dword ptr [rax+4], 0
0x18003d1fd  mov     rcx, [rdi+38h]
0x18003d201  mov     rax, [rcx]
0x18003d204  mov     rax, [rax+28h]
0x18003d208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d20d  mov     rcx, [rdi+38h]
0x18003d211  mov     ebx, eax
0x18003d213  mov     rax, [rcx]
0x18003d216  mov     rax, [rax+20h]
0x18003d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21f  lea     rcx, [r14+8]; Destination
0x18003d223  mov     r9d, ebx; SourceSize
0x18003d226  mov     r8, rax; Source
0x18003d229  mov     edx, 20h ; ' '; DestinationSize
0x18003d22e  call    memcpy_s
0x18003d233  test    eax, eax
0x18003d235  jz      short loc_18003D255
0x18003d237  mov     eax, 0C00D36BBh
0x18003d23c  mov     esi, eax
0x18003d23e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d245  jb      loc_18003D530
0x18003d24b  mov     edx, 29h ; ')'
0x18003d250  jmp     loc_18003D1CD
0x18003d255  mov     r9d, [rbp+57h+var_58.cbData]; SourceSize
0x18003d259  lea     rcx, [r14+28h]; Destination
0x18003d25d  mov     r8, [rbp+57h+var_58.pbData]; Source
0x18003d261  mov     edx, r12d
0x18003d264  add     rdx, 0FFFFFFFFFFFFFFD8h; DestinationSize
0x18003d268  call    memcpy_s
0x18003d26d  test    eax, eax
0x18003d26f  jz      loc_18003D382
0x18003d275  mov     eax, 0C00D36BBh
0x18003d27a  mov     esi, eax
0x18003d27c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d283  jb      loc_18003D530
0x18003d289  mov     edx, 2Ah ; '*'
0x18003d28e  jmp     loc_18003D1CD
0x18003d293  mov     r12d, [rbp+57h+pDataIn.cbData]
0x18003d297  lea     rcx, [rbp+57h+arg_18]
0x18003d29b  add     r12d, 28h ; '('
0x18003d29f  mov     edx, r12d
0x18003d2a2  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003d2a7  mov     rdx, rax
0x18003d2aa  lea     rcx, [rbp+57h+arg_8]
0x18003d2ae  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003d2b3  lea     rcx, [rbp+57h+arg_18]
0x18003d2b7  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003d2bc  mov     rax, [rbp+57h+arg_8]
0x18003d2c0  test    rax, rax
0x18003d2c3  jnz     short loc_18003D2E3
0x18003d2c5  mov     eax, 8007000Eh
0x18003d2ca  mov     esi, eax
0x18003d2cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d2d3  jb      loc_18003D530
0x18003d2d9  mov     edx, 2Bh ; '+'
0x18003d2de  jmp     loc_18003D1CD
0x18003d2e3  mov     [rax], r12d
0x18003d2e6  mov     r14, rax
0x18003d2e9  mov     dword ptr [rax+4], 0
0x18003d2f0  mov     rcx, [rdi+38h]
0x18003d2f4  mov     rax, [rcx]
0x18003d2f7  mov     rax, [rax+28h]
0x18003d2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d300  mov     rcx, [rdi+38h]
0x18003d304  mov     ebx, eax
  ... truncated ...
```
