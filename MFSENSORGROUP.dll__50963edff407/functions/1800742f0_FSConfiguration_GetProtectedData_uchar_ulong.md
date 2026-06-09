# FSConfiguration::GetProtectedData(uchar * *,ulong *)

- ea: `0x1800742f0`
- end: `0x180074b63`
- name: `?GetProtectedData@FSConfiguration@@UEAAJPEAPEAEPEAK@Z`
- size: `2163`
- prototype: `__int64 __fastcall(FSConfiguration *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005fa0`
- `0x18000aa08`
- `0x18000c2ec`
- `0x18000f5a0`
- `0x180010218`
- `0x1800133fc`
- `0x180028eb4`
- `0x18002b778`
- `0x1800313f8`
- `0x18003cc5c`
- `0x18003ccec`
- `0x18003d064`
- `0x18004a270`
- `0x180050690`
- `0x1800742f0`
- `0x18007598c`
- `0x180075bd0`
- `0x180075c84`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074b47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074b47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074322`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800748a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800748a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074a26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074a26`
- `CRYPT32!CryptProtectData` at `0x1800745c2`
- `CRYPT32!CryptProtectData` at `0x18007489a`
- `CRYPT32!CryptProtectData` at `0x1800745c2`
- `CRYPT32!CryptProtectData` at `0x18007489a`
- `MFPlat!MFGetAttributesAsBlob` at `0x1800744b7`
- `MFPlat!MFGetAttributesAsBlob` at `0x1800744b7`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180074446`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x180074446`

## pseudocode

```c
__int64 __fastcall FSConfiguration::GetProtectedData(FSConfiguration *this, unsigned __int8 **a2, unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r15
  _DWORD *v7; // r12
  const char *v8; // rax
  HRESULT v9; // eax
  signed int v10; // esi
  __int64 v11; // rdx
  void **unique; // rax
  UINT8 *v13; // rbx
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // r8
  signed int LastError; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r15
  void **v20; // rax
  _DWORD *v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // ebx
  const void *v25; // rax
  void **v26; // rax
  _DWORD *v27; // rax
  unsigned int v28; // ebx
  const void *v29; // rax
  char *v30; // rcx
  __int64 v31; // r8
  signed int v32; // eax
  void **v33; // rax
  _DWORD *v34; // rax
  unsigned int v35; // ebx
  const void *v36; // rax
  unsigned __int8 **v37; // rcx
  unsigned __int8 *v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v44; // [rsp+50h] [rbp-19h] BYREF
  UINT8 *pBuf; // [rsp+58h] [rbp-11h] BYREF
  DATA_BLOB pDataIn; // [rsp+60h] [rbp-9h] BYREF
  DATA_BLOB pDataOut; // [rsp+70h] [rbp+7h] BYREF
  UINT32 pcbBufSize; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int8 **v49; // [rsp+D8h] [rbp+6Fh]
  unsigned int *v50; // [rsp+E0h] [rbp+77h]
  _DWORD *v51; // [rsp+E8h] [rbp+7Fh] BYREF

  v50 = a3;
  v49 = a2;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  pBuf = 0;
  pcbBufSize = 0;
  pDataIn = 0;
  v51 = 0;
  v7 = 0;
  pDataOut = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
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
  else if ( (unsigned __int8)byte_18008D62D >= 8u )
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
    unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v44, pcbBufSize);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&pBuf, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v44);
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
    if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    {
      v44 = 0;
      if ( (int)FSGetUserSidString(v14, (LPWSTR *)&v44) < 0 )
      {
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            37,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            pDataIn.pbData,
            pDataIn.cbData);
      }
      else if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        WPP_SF_qSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          36,
          v15,
          (_DWORD)this,
          v44,
          (char)pDataIn.pbData,
          pDataIn.cbData);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
    {
      if ( *((_BYTE *)this + 88) )
      {
        v19 = pDataIn.cbData + 40;
        v26 = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v44, v19);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v51, v26);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v44);
        v27 = v51;
        if ( !v51 )
        {
          v22 = -2147024882;
          v10 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_79;
          v23 = 43;
          goto LABEL_44;
        }
        *v51 = v19;
        v7 = v27;
        v27[1] = 0;
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
        v29 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
        if ( memcpy_s_1(v7 + 2, 0x20u, v29, v28) )
        {
          v22 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v23 = 44;
          goto LABEL_44;
        }
        if ( memcpy_s_1(v7 + 10, v19 - 40, pDataIn.pbData, pDataIn.cbData) )
        {
          v22 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v23 = 45;
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
          if ( !byte_18008D62D )
            goto LABEL_80;
          v18 = 38;
          goto LABEL_38;
        }
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_qqDqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            39,
            v16,
            this,
            pDataIn.pbData,
            pDataIn.cbData,
            pDataOut.pbData,
            pDataOut.cbData);
        v19 = pDataOut.cbData + 40;
        v20 = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v44, v19);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v51, v20);
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v44);
        v21 = v51;
        if ( !v51 )
        {
          v22 = -2147024882;
          v10 = -2147024882;
          if ( !g_wppLevels )
          {
LABEL_79:
            v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
            goto LABEL_80;
          }
          v23 = 40;
LABEL_44:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            v22);
          goto LABEL_79;
        }
        *v51 = v19;
        v7 = v21;
        v21[1] = 0;
        v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
        v25 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
        if ( memcpy_s_1(v7 + 2, 0x20u, v25, v24) )
        {
          v22 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v23 = 41;
          goto LABEL_44;
        }
        if ( memcpy_s_1(v7 + 10, v19 - 40, pDataOut.pbData, pDataOut.cbData) )
        {
          v22 = -1072875845;
          v10 = -1072875845;
          if ( !g_wppLevels )
            goto LABEL_79;
          v23 = 42;
          goto LABEL_44;
        }
      }
      v30 = (char *)this + 64;
    }
    else
    {
      if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
      {
        v32 = GetLastError();
        v10 = v32;
        if ( v32 > 0 )
          v10 = (unsigned __int16)v32 | 0x80070000;
        if ( !byte_18008D62D )
          goto LABEL_80;
        v18 = 46;
LABEL_38:
        WPP_SF_qDqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v18,
          &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
          this,
          v10,
          pDataIn.pbData,
          pDataIn.cbData);
        goto LABEL_80;
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_qqDqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          47,
          v31,
          this,
          pDataIn.pbData,
          pDataIn.cbData,
          pDataOut.pbData,
          pDataOut.cbData);
      v19 = pDataOut.cbData + 40;
      v33 = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v44, v19);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v51, v33);
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v44);
      v34 = v51;
      if ( !v51 )
      {
        v22 = -2147024882;
        v10 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_79;
        v23 = 48;
        goto LABEL_44;
      }
      *v51 = v19;
      v7 = v34;
      v34[1] = 0;
      v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 40LL))(*((_QWORD *)this + 7));
      v36 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 32LL))(*((_QWORD *)this + 7));
      if ( memcpy_s_1(v7 + 2, 0x20u, v36, v35) )
      {
        v22 = -1072875845;
        v10 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_79;
        v23 = 49;
        goto LABEL_44;
      }
      if ( memcpy_s_1(v7 + 10, v19 - 40, pDataOut.pbData, pDataOut.cbData) )
      {
        v22 = -1072875845;
        v10 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_79;
        v23 = 50;
        goto LABEL_44;
      }
      v30 = (char *)this + 64;
    }
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap(v30, &v51);
    v38 = *v37;
    *((_DWORD *)this + 18) = v19;
    *v49 = v38;
    *v50 = *((_DWORD *)this + 18);
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
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
        v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
        WPP_SF_qDDDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, *v7, v7[1], v40, v39);
      }
    }
    else if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
LABEL_87:
      v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
      v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
      WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, v42, v41);
    }
  }
  else if ( byte_18008D62D )
  {
    goto LABEL_87;
  }
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v51);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&pBuf);
  LeaveCriticalSection(v3);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800742f0  mov     [rsp-8+arg_10], r8
0x1800742f5  mov     [rsp-8+arg_8], rdx
0x1800742fa  push    rbp
0x1800742fb  push    rbx
0x1800742fc  push    rsi
0x1800742fd  push    rdi
0x1800742fe  push    r12
0x180074300  push    r13
0x180074302  push    r14
0x180074304  push    r15
0x180074306  lea     rbp, [rsp-1Fh]
0x18007430b  sub     rsp, 88h
0x180074312  lea     r15, [rcx+10h]
0x180074316  mov     rdi, rcx
0x180074319  mov     rcx, r15; lpCriticalSection
0x18007431c  mov     rsi, r8
0x18007431f  mov     rbx, rdx
0x180074322  call    cs:__imp_EnterCriticalSection
0x180074328  xorps   xmm0, xmm0
0x18007432b  mov     [rbp+57h+pBuf], 0
0x180074333  xorps   xmm1, xmm1
0x180074336  mov     [rbp+57h+pcbBufSize], 0
0x18007433d  movups  xmmword ptr [rbp+57h+pDataIn.cbData], xmm0
0x180074341  mov     [rbp+57h+arg_18], 0
0x180074349  xor     r12d, r12d
0x18007434c  movups  xmmword ptr [rbp+57h+var_50.cbData], xmm1
0x180074350  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x180074357  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18007435c  test    al, al
0x18007435e  jz      short loc_1800743AB
0x180074360  mov     r14b, 8
0x180074363  cmp     cs:byte_18008D62D, r14b
0x18007436a  jb      short loc_1800743D9
0x18007436c  cmp     [rdi+58h], r12b
0x180074370  lea     rcx, aFalse; "false"
0x180074377  lea     rax, aTrue_0; "true"
0x18007437e  mov     r9, rdi
0x180074381  cmovz   rax, rcx
0x180074385  lea     edx, [r12+1Dh]
0x18007438a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074391  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074398  mov     [rsp+0C0h+pPromptStruct], rax
0x18007439d  mov     rcx, [rcx+0D8h]
0x1800743a4  call    WPP_SF_qs
0x1800743a9  jmp     short loc_1800743D9
0x1800743ab  mov     r14b, 8
0x1800743ae  cmp     cs:byte_18008D62D, r14b
0x1800743b5  jb      short loc_1800743D9
0x1800743b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743be  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800743c5  mov     edx, 1Eh
0x1800743ca  mov     r9, rdi
0x1800743cd  mov     rcx, [rcx+0D8h]
0x1800743d4  call    WPP_SF_q
0x1800743d9  test    rbx, rbx
0x1800743dc  jnz     short loc_180074418
0x1800743de  mov     eax, 80004003h
0x1800743e3  mov     esi, eax
0x1800743e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800743ec  jb      loc_180074A22
0x1800743f2  lea     edx, [rbx+1Fh]
0x1800743f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743fc  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074403  mov     r9, rdi
0x180074406  mov     dword ptr [rsp+0C0h+pPromptStruct], eax
0x18007440a  mov     rcx, [rcx+10h]
0x18007440e  call    WPP_SF_qD
0x180074413  jmp     loc_180074A22
0x180074418  mov     [rbx], r12
0x18007441b  test    rsi, rsi
0x18007441e  jnz     short loc_18007443B
0x180074420  mov     eax, 80004003h
0x180074425  mov     esi, eax
0x180074427  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007442e  jb      loc_180074A22
0x180074434  mov     edx, 20h ; ' '
0x180074439  jmp     short loc_1800743F5
0x18007443b  mov     [rsi], r12d
0x18007443e  lea     rdx, [rbp+57h+pcbBufSize]; pcbBufSize
0x180074442  mov     rcx, [rdi+50h]; pAttributes
0x180074446  call    cs:__imp_MFGetAttributesAsBlobSize
0x18007444c  mov     esi, eax
0x18007444e  test    eax, eax
0x180074450  jns     short loc_180074466
0x180074452  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074459  jb      loc_180074A22
0x18007445f  mov     edx, 21h ; '!'
0x180074464  jmp     short loc_1800743F5
0x180074466  mov     edx, [rbp+57h+pcbBufSize]
0x180074469  lea     rcx, [rbp+57h+var_70]
0x18007446d  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180074472  mov     rdx, rax
0x180074475  lea     rcx, [rbp+57h+pBuf]
0x180074479  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18007447e  lea     rcx, [rbp+57h+var_70]
0x180074482  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180074487  mov     rbx, [rbp+57h+pBuf]
0x18007448b  test    rbx, rbx
0x18007448e  jnz     short loc_1800744AC
0x180074490  mov     eax, 8007000Eh
0x180074495  mov     esi, eax
0x180074497  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007449e  jb      loc_180074A22
0x1800744a4  lea     edx, [rbx+22h]
0x1800744a7  jmp     loc_1800743F5
0x1800744ac  mov     r8d, [rbp+57h+pcbBufSize]; cbBufSize
0x1800744b0  mov     rdx, rbx; pBuf
0x1800744b3  mov     rcx, [rdi+50h]; pAttributes
0x1800744b7  call    cs:__imp_MFGetAttributesAsBlob
0x1800744bd  mov     esi, eax
0x1800744bf  test    eax, eax
0x1800744c1  jns     short loc_1800744DA
0x1800744c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800744ca  jb      loc_180074A22
0x1800744d0  mov     edx, 23h ; '#'
0x1800744d5  jmp     loc_1800743F5
0x1800744da  cmp     cs:byte_18008D62D, 10h
0x1800744e1  mov     eax, [rbp+57h+pcbBufSize]
0x1800744e4  mov     [rbp+57h+pDataIn.cbData], eax
0x1800744e7  mov     [rbp+57h+pDataIn.pbData], rbx
0x1800744eb  jb      loc_180074585
0x1800744f1  lea     rdx, [rbp+57h+var_70]
0x1800744f5  mov     [rbp+57h+var_70], r12
0x1800744f9  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800744fe  test    eax, eax
0x180074500  js      short loc_180074541
0x180074502  cmp     cs:byte_18008D62D, r14b
0x180074509  jb      short loc_18007457C
0x18007450b  mov     eax, [rbp+57h+pDataIn.cbData]
0x18007450e  mov     edx, 24h ; '$'
0x180074513  mov     rcx, cs:WPP_GLOBAL_Control
0x18007451a  mov     r9, rdi
0x18007451d  mov     dword ptr [rsp+0C0h+pDataOut], eax
0x180074521  mov     rax, [rbp+57h+pDataIn.pbData]
0x180074525  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x18007452a  mov     rax, [rbp+57h+var_70]
0x18007452e  mov     rcx, [rcx+0D8h]
0x180074535  mov     [rsp+0C0h+pPromptStruct], rax
0x18007453a  call    WPP_SF_qSqD
0x18007453f  jmp     short loc_18007457C
0x180074541  cmp     cs:byte_18008D62D, r14b
0x180074548  jb      short loc_18007457C
0x18007454a  mov     eax, [rbp+57h+pDataIn.cbData]
0x18007454d  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074554  mov     rcx, cs:WPP_GLOBAL_Control
0x18007455b  mov     edx, 25h ; '%'
0x180074560  mov     [rsp+0C0h+dwFlags], eax
0x180074564  mov     r9, rdi
0x180074567  mov     rax, [rbp+57h+pDataIn.pbData]
0x18007456b  mov     [rsp+0C0h+pPromptStruct], rax
0x180074570  mov     rcx, [rcx+0D8h]
0x180074577  call    WPP_SF_qqD
0x18007457c  lea     rcx, [rbp+57h+var_70]
0x180074580  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074585  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18007458c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x180074591  test    al, al
0x180074593  jz      loc_18007487B
0x180074599  cmp     [rdi+58h], r12b
0x18007459d  jnz     loc_18007477D
0x1800745a3  lea     rax, [rbp+57h+var_50]
0x1800745a7  xor     r9d, r9d; pvReserved
0x1800745aa  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x1800745af  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x1800745b3  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x1800745b8  xor     r8d, r8d; pOptionalEntropy
0x1800745bb  xor     edx, edx; szDataDescr
0x1800745bd  mov     [rsp+0C0h+pPromptStruct], r12; pPromptStruct
0x1800745c2  call    cs:__imp_CryptProtectData
0x1800745c8  test    eax, eax
0x1800745ca  jnz     short loc_180074629
0x1800745cc  call    cs:__imp_GetLastError
0x1800745d2  mov     esi, eax
0x1800745d4  test    eax, eax
0x1800745d6  jle     short loc_1800745E1
0x1800745d8  movzx   esi, ax
0x1800745db  or      esi, 80070000h
0x1800745e1  cmp     cs:byte_18008D62D, 1
0x1800745e8  jb      loc_180074A22
0x1800745ee  mov     edx, 26h ; '&'
0x1800745f3  mov     eax, [rbp+57h+pDataIn.cbData]
0x1800745f6  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800745fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180074604  mov     r9, rdi
0x180074607  mov     dword ptr [rsp+0C0h+pDataOut], eax
0x18007460b  mov     rax, [rbp+57h+pDataIn.pbData]
0x18007460f  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180074614  mov     rcx, [rcx+0D8h]
0x18007461b  mov     dword ptr [rsp+0C0h+pPromptStruct], esi
0x18007461f  call    WPP_SF_qDqD
0x180074624  jmp     loc_180074A22
0x180074629  cmp     cs:byte_18008D62D, r14b
0x180074630  jb      short loc_18007466D
0x180074632  mov     eax, [rbp+57h+var_50.cbData]
0x180074635  mov     edx, 27h ; '''
0x18007463a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074641  mov     r9, rdi
0x180074644  mov     dword ptr [rsp+0C0h+var_88], eax
0x180074648  mov     rax, [rbp+57h+var_50.pbData]
0x18007464c  mov     [rsp+0C0h+pDataOut], rax
0x180074651  mov     eax, [rbp+57h+pDataIn.cbData]
0x180074654  mov     rcx, [rcx+0D8h]
0x18007465b  mov     [rsp+0C0h+dwFlags], eax
0x18007465f  mov     rax, [rbp+57h+pDataIn.pbData]
0x180074663  mov     [rsp+0C0h+pPromptStruct], rax
0x180074668  call    WPP_SF_qqDqD
0x18007466d  mov     r15d, [rbp+57h+var_50.cbData]
0x180074671  lea     rcx, [rbp+57h+var_70]
0x180074675  add     r15d, 28h ; '('
0x180074679  mov     edx, r15d
0x18007467c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180074681  mov     rdx, rax
0x180074684  lea     rcx, [rbp+57h+arg_18]
0x180074688  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18007468d  lea     rcx, [rbp+57h+var_70]
0x180074691  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180074696  mov     rax, [rbp+57h+arg_18]
0x18007469a  test    rax, rax
0x18007469d  jnz     short loc_1800746DB
0x18007469f  mov     eax, 8007000Eh
0x1800746a4  mov     esi, eax
0x1800746a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800746ad  jb      loc_180074A1E
0x1800746b3  mov     edx, 28h ; '('
0x1800746b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800746bf  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800746c6  mov     r9, rdi
0x1800746c9  mov     dword ptr [rsp+0C0h+pPromptStruct], eax
0x1800746cd  mov     rcx, [rcx+10h]
0x1800746d1  call    WPP_SF_qD
0x1800746d6  jmp     loc_180074A1E
0x1800746db  mov     [rax], r15d
0x1800746de  mov     r12, rax
0x1800746e1  mov     dword ptr [rax+4], 0
0x1800746e8  mov     rcx, [rdi+38h]
0x1800746ec  mov     rax, [rcx]
0x1800746ef  mov     rax, [rax+28h]
0x1800746f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746f8  mov     rcx, [rdi+38h]
0x1800746fc  mov     ebx, eax
0x1800746fe  mov     rax, [rcx]
0x180074701  mov     rax, [rax+20h]
0x180074705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007470a  lea     rcx, [r12+8]; Destination
0x18007470f  mov     r9d, ebx; SourceSize
0x180074712  mov     r8, rax; Source
0x180074715  mov     edx, 20h ; ' '; DestinationSize
0x18007471a  call    memcpy_s_1
0x18007471f  test    eax, eax
0x180074721  jz      short loc_180074741
0x180074723  mov     eax, 0C00D36BBh
0x180074728  mov     esi, eax
0x18007472a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074731  jb      loc_180074A1E
0x180074737  mov     edx, 29h ; ')'
0x18007473c  jmp     loc_1800746B8
0x180074741  mov     r9d, [rbp+57h+var_50.cbData]; SourceSize
0x180074745  lea     rdx, [r15-28h]; DestinationSize
0x180074749  mov     r8, [rbp+57h+var_50.pbData]; Source
0x18007474d  lea     rcx, [r12+28h]; Destination
0x180074752  call    memcpy_s_1
0x180074757  test    eax, eax
0x180074759  jz      loc_18007486B
0x18007475f  mov     eax, 0C00D36BBh
0x180074764  mov     esi, eax
0x180074766  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007476d  jb      loc_180074A1E
0x180074773  mov     edx, 2Ah ; '*'
0x180074778  jmp     loc_1800746B8
0x18007477d  mov     r15d, [rbp+57h+pDataIn.cbData]
0x180074781  lea     rcx, [rbp+57h+var_70]
0x180074785  add     r15d, 28h ; '('
0x180074789  mov     edx, r15d
0x18007478c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180074791  mov     rdx, rax
0x180074794  lea     rcx, [rbp+57h+arg_18]
0x180074798  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18007479d  lea     rcx, [rbp+57h+var_70]
0x1800747a1  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800747a6  mov     rax, [rbp+57h+arg_18]
0x1800747aa  test    rax, rax
0x1800747ad  jnz     short loc_1800747CD
0x1800747af  mov     eax, 8007000Eh
0x1800747b4  mov     esi, eax
0x1800747b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800747bd  jb      loc_180074A1E
0x1800747c3  mov     edx, 2Bh ; '+'
0x1800747c8  jmp     loc_1800746B8
0x1800747cd  mov     [rax], r15d
0x1800747d0  mov     r12, rax
0x1800747d3  mov     dword ptr [rax+4], 0
0x1800747da  mov     rcx, [rdi+38h]
0x1800747de  mov     rax, [rcx]
0x1800747e1  mov     rax, [rax+28h]
0x1800747e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747ea  mov     rcx, [rdi+38h]
0x1800747ee  mov     ebx, eax
0x1800747f0  mov     rax, [rcx]
0x1800747f3  mov     rax, [rax+20h]
0x1800747f7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
