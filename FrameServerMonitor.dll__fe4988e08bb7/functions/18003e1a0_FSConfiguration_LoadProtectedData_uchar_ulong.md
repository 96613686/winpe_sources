# FSConfiguration::LoadProtectedData(uchar *,ulong)

- ea: `0x18003e1a0`
- end: `0x18003e7c6`
- name: `?LoadProtectedData@FSConfiguration@@UEAAJPEAEK@Z`
- size: `1574`
- prototype: `int(FSConfiguration *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180006a98`
- `0x180007020`
- `0x18000d024`
- `0x18000d7c4`
- `0x18001c63c`
- `0x180025bf0`
- `0x180035f40`
- `0x18003e1a0`
- `0x18003eb3c`
- `0x18003ec28`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e69d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e69d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e714`
- `CRYPT32!CryptUnprotectData` at `0x18003e50d`
- `CRYPT32!CryptUnprotectData` at `0x18003e693`
- `CRYPT32!CryptUnprotectData` at `0x18003e50d`
- `CRYPT32!CryptUnprotectData` at `0x18003e693`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e555`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e586`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e6d7`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e555`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e586`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e6d7`

## pseudocode

```c
__int64 __fastcall FSConfiguration::LoadProtectedData(FSConfiguration *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 v4; // rcx
  signed int v7; // edi
  __int64 v8; // rdx
  char v9; // al
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rdi
  unsigned int v14; // ebx
  const void *v15; // rax
  char v16; // bl
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // edx
  __int64 v20; // r8
  __int64 v21; // rax
  UINT v22; // r14d
  __int64 v23; // rcx
  signed int LastError; // eax
  HRESULT v25; // eax
  __int64 v26; // rdx
  signed int v27; // eax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataIn; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v34[72]; // [rsp+70h] [rbp-90h] BYREF

  v4 = *((_QWORD *)this + 7);
  pDataIn = 0;
  pDataOut = 0;
  if ( !v4 )
  {
    v7 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_62;
    v8 = 54;
    goto LABEL_4;
  }
  v9 = byte_18005E5A5;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 48LL))(*((_QWORD *)this + 7));
    WPP_SF_qDSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), a3, v12, v11, v10);
    v9 = byte_18005E5A5;
  }
  if ( a2 )
  {
    if ( a3 >= 0x28 )
    {
      if ( *(_DWORD *)a2 > a3 )
      {
        v7 = -2147024809;
        if ( v9 )
          WPP_SF_qddd(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            58,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            -2147024809,
            *(_DWORD *)a2,
            a3);
        goto LABEL_62;
      }
      v13 = *((_QWORD *)this + 7);
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
      v15 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
      if ( memcmp_0(a2 + 8, v15, v14) )
      {
        v16 = byte_18005E5A5;
        v7 = -2147024809;
        if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
        {
          memset_0(v34, 0, 0x82u);
          if ( a2 != (unsigned __int8 *)-8LL )
          {
            v17 = 0;
            v18 = 0;
            do
            {
              v19 = a2[v18++ + 8];
              v34[v17] = a0123456789abcd_0[(unsigned __int64)v19 >> 4];
              v20 = (unsigned int)(v17 + 1);
              v34[v20] = a0123456789abcd_0[v19 & 0xF];
              v17 = (unsigned int)(v20 + 1);
            }
            while ( v18 != 32 );
            v34[v17] = 0;
          }
          if ( v16 )
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
            WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), 87, (__int64)v34, v21);
          }
        }
        goto LABEL_62;
      }
      v22 = a3 - 40;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
      {
        if ( *((_BYTE *)this + 88) )
        {
          v25 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), a2 + 40, v22);
          v7 = v25;
          if ( v25 >= 0 || !g_wppLevels )
            goto LABEL_62;
          v26 = 64;
        }
        else
        {
          pDataIn.pbData = a2 + 40;
          pDataIn.cbData = v22;
          if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
          {
            v31 = 0;
            if ( (int)FSGetUserSidString(v23, (LPWSTR *)&v31) < 0 )
            {
              if ( (unsigned __int8)byte_18005E5A5 >= 8u )
                WPP_SF_qqD(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  61,
                  &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
                  this,
                  pDataIn.pbData,
                  pDataIn.cbData);
            }
            else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
            {
              WPP_SF_qSqD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                60,
                (unsigned int)&WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
                (_DWORD)this,
                v31,
                (char)pDataIn.pbData,
                pDataIn.cbData);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
          }
          if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            if ( v7 < 0 )
            {
              if ( g_wppLevels )
              {
                v8 = 62;
                goto LABEL_4;
              }
              goto LABEL_62;
            }
          }
          v25 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
          v7 = v25;
          if ( v25 >= 0 || !g_wppLevels )
            goto LABEL_62;
          v26 = 63;
        }
      }
      else
      {
        pDataIn.pbData = a2 + 40;
        pDataIn.cbData = v22;
        if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
        {
          v31 = 0;
          if ( (int)FSGetUserSidString(v23, (LPWSTR *)&v31) < 0 )
          {
            if ( (unsigned __int8)byte_18005E5A5 >= 8u )
              WPP_SF_qqD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                66,
                &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
                this,
                pDataIn.pbData,
                pDataIn.cbData);
          }
          else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            WPP_SF_qSqD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              65,
              (unsigned int)&WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
              (_DWORD)this,
              v31,
              (char)pDataIn.pbData,
              pDataIn.cbData);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v31);
        }
        if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        {
          v27 = GetLastError();
          v7 = v27;
          if ( v27 > 0 )
            v7 = (unsigned __int16)v27 | 0x80070000;
          if ( v7 < 0 )
          {
            if ( g_wppLevels )
            {
              v8 = 67;
              goto LABEL_4;
            }
            goto LABEL_62;
          }
        }
        v25 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
        v7 = v25;
        if ( v25 >= 0 || !g_wppLevels )
          goto LABEL_62;
        v26 = 68;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v25);
      goto LABEL_62;
    }
    v7 = -2147024809;
    if ( g_wppLevels )
    {
      v8 = 57;
      goto LABEL_4;
    }
  }
  else
  {
    v7 = -2147024809;
    if ( g_wppLevels )
    {
      v8 = 56;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v7);
    }
  }
LABEL_62:
  LocalFree(pDataOut.pbData);
  if ( v7 >= 0 )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
LABEL_66:
      v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
      v29 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
      WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, v29, v28);
    }
  }
  else if ( byte_18005E5A5 )
  {
    goto LABEL_66;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e1a0  push    rbp
0x18003e1a2  push    rbx
0x18003e1a3  push    rsi
0x18003e1a4  push    rdi
0x18003e1a5  push    r12
0x18003e1a7  push    r14
0x18003e1a9  push    r15
0x18003e1ab  lea     rbp, [rsp-10h]
0x18003e1b0  sub     rsp, 110h
0x18003e1b7  mov     rax, cs:__security_cookie
0x18003e1be  xor     rax, rsp
0x18003e1c1  mov     [rbp+40h+var_40], rax
0x18003e1c5  mov     rsi, rcx
0x18003e1c8  xorps   xmm0, xmm0
0x18003e1cb  mov     rcx, [rcx+38h]
0x18003e1cf  xorps   xmm1, xmm1
0x18003e1d2  mov     r14d, r8d
0x18003e1d5  mov     r15, rdx
0x18003e1d8  movups  xmmword ptr [rsp+140h+pDataIn.cbData], xmm0
0x18003e1dd  movups  xmmword ptr [rsp+140h+var_E8.cbData], xmm1
0x18003e1e2  test    rcx, rcx
0x18003e1e5  jnz     short loc_18003E205
0x18003e1e7  mov     edi, 80070057h
0x18003e1ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e1f3  jb      loc_18003E70F
0x18003e1f9  lea     edx, [rcx+36h]
0x18003e1fc  mov     dword ptr [rsp+140h+pPromptStruct], edi
0x18003e200  jmp     loc_18003E6F5
0x18003e205  mov     al, cs:byte_18005E5A5
0x18003e20b  cmp     al, 8
0x18003e20d  jb      short loc_18003E271
0x18003e20f  mov     rax, [rcx]
0x18003e212  mov     rax, [rax+38h]
0x18003e216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e21b  mov     rcx, [rsi+38h]
0x18003e21f  mov     rdi, rax
0x18003e222  mov     rax, [rcx]
0x18003e225  mov     rax, [rax+40h]
0x18003e229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e22e  mov     rcx, [rsi+38h]
0x18003e232  mov     rbx, rax
0x18003e235  mov     rax, [rcx]
0x18003e238  mov     rax, [rax+30h]
0x18003e23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e241  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e248  mov     r9, rsi
0x18003e24b  mov     [rsp+140h+var_108], rdi; __int64
0x18003e250  mov     [rsp+140h+pDataOut], rbx; __int64
0x18003e255  mov     qword ptr [rsp+140h+dwFlags], rax; __int64
0x18003e25a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003e261  mov     dword ptr [rsp+140h+pPromptStruct], r14d; char
0x18003e266  call    WPP_SF_qDSSS
0x18003e26b  mov     al, cs:byte_18005E5A5
0x18003e271  test    r15, r15
0x18003e274  jnz     short loc_18003E291
0x18003e276  mov     edi, 80070057h
0x18003e27b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e282  jb      loc_18003E70F
0x18003e288  lea     edx, [r15+38h]
0x18003e28c  jmp     loc_18003E1FC
0x18003e291  cmp     r14d, 28h ; '('
0x18003e295  jnb     short loc_18003E2B3
0x18003e297  mov     edi, 80070057h
0x18003e29c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e2a3  jb      loc_18003E70F
0x18003e2a9  mov     edx, 39h ; '9'
0x18003e2ae  jmp     loc_18003E1FC
0x18003e2b3  mov     ecx, [r15]
0x18003e2b6  cmp     ecx, r14d
0x18003e2b9  jbe     short loc_18003E300
0x18003e2bb  mov     edi, 80070057h
0x18003e2c0  cmp     al, 1
0x18003e2c2  jb      loc_18003E70F
0x18003e2c8  mov     dword ptr [rsp+140h+pDataOut], r14d
0x18003e2cd  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e2d4  mov     [rsp+140h+dwFlags], ecx
0x18003e2d8  mov     edx, 3Ah ; ':'
0x18003e2dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2e4  mov     r9, rsi
0x18003e2e7  mov     dword ptr [rsp+140h+pPromptStruct], 80070057h
0x18003e2ef  mov     rcx, [rcx+0D8h]
0x18003e2f6  call    WPP_SF_qddd
0x18003e2fb  jmp     loc_18003E70F
0x18003e300  mov     rdi, [rsi+38h]
0x18003e304  mov     rcx, rdi
0x18003e307  mov     rax, [rdi]
0x18003e30a  mov     rax, [rax+28h]
0x18003e30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e313  mov     ebx, eax
0x18003e315  lea     r12, [r15+8]
0x18003e319  mov     rax, [rdi]
0x18003e31c  mov     rcx, rdi
0x18003e31f  mov     rax, [rax+20h]
0x18003e323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e328  mov     rdx, rax; Buf2
0x18003e32b  mov     r8d, ebx; Size
0x18003e32e  mov     rcx, r12; Buf1
0x18003e331  call    memcmp_0
0x18003e336  test    eax, eax
0x18003e338  jz      loc_18003E401
0x18003e33e  mov     bl, cs:byte_18005E5A5
0x18003e344  mov     edi, 80070057h
0x18003e349  cmp     bl, 10h
0x18003e34c  jb      loc_18003E70F
0x18003e352  xor     edx, edx; Val
0x18003e354  lea     rcx, [rsp+140h+var_D0]; void *
0x18003e359  mov     r8d, 82h; Size
0x18003e35f  call    memset_0
0x18003e364  test    r12, r12
0x18003e367  jz      short loc_18003E3B1
0x18003e369  xor     r8d, r8d
0x18003e36c  lea     r10, a0123456789abcd_0; "0123456789ABCDEF"
0x18003e373  xor     r9d, r9d
0x18003e376  movzx   edx, byte ptr [r12+r9]
0x18003e37b  inc     r9
0x18003e37e  mov     eax, edx
0x18003e380  and     edx, 0Fh
0x18003e383  shr     rax, 4
0x18003e387  movzx   eax, word ptr [r10+rax*2]
0x18003e38c  mov     [rsp+r8*2+140h+var_D0], ax
0x18003e392  inc     r8d
0x18003e395  movzx   eax, word ptr [r10+rdx*2]
0x18003e39a  mov     [rsp+r8*2+140h+var_D0], ax
0x18003e3a0  inc     r8d
0x18003e3a3  cmp     r9, 20h ; ' '
0x18003e3a7  jnz     short loc_18003E376
0x18003e3a9  xor     eax, eax
0x18003e3ab  mov     [rsp+r8*2+140h+var_D0], ax
0x18003e3b1  cmp     bl, 1
0x18003e3b4  jb      loc_18003E70F
0x18003e3ba  mov     rcx, [rsi+38h]
0x18003e3be  mov     rax, [rcx]
0x18003e3c1  mov     rax, [rax+48h]
0x18003e3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3d1  mov     edx, 3Bh ; ';'
0x18003e3d6  mov     [rsp+140h+pDataOut], rax; __int64
0x18003e3db  mov     r9, rsi
0x18003e3de  lea     rax, [rsp+140h+var_D0]
0x18003e3e3  mov     qword ptr [rsp+140h+dwFlags], rax; __int64
0x18003e3e8  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003e3ef  mov     dword ptr [rsp+140h+pPromptStruct], 80070057h; char
0x18003e3f7  call    WPP_SF_qDSS
0x18003e3fc  jmp     loc_18003E70F
0x18003e401  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18003e408  add     r14d, 0FFFFFFD8h
0x18003e40c  lea     rbx, [r15+28h]
0x18003e410  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18003e415  test    al, al
0x18003e417  jz      loc_18003E5AD
0x18003e41d  cmp     byte ptr [rsi+58h], 0
0x18003e421  jnz     loc_18003E57C
0x18003e427  cmp     cs:byte_18005E5A5, 10h
0x18003e42e  mov     [rsp+140h+pDataIn.pbData], rbx
0x18003e433  mov     [rsp+140h+pDataIn.cbData], r14d
0x18003e438  jb      loc_18003E4E5
0x18003e43e  lea     rdx, [rsp+140h+var_100]
0x18003e443  mov     [rsp+140h+var_100], 0
0x18003e44c  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003e451  test    eax, eax
0x18003e453  js      short loc_18003E49E
0x18003e455  cmp     cs:byte_18005E5A5, 8
0x18003e45c  jb      short loc_18003E4DB
0x18003e45e  mov     eax, [rsp+140h+pDataIn.cbData]
0x18003e462  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e469  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e470  mov     edx, 3Ch ; '<'
0x18003e475  mov     dword ptr [rsp+140h+pDataOut], eax
0x18003e479  mov     r9, rsi
0x18003e47c  mov     rax, [rsp+140h+pDataIn.pbData]
0x18003e481  mov     qword ptr [rsp+140h+dwFlags], rax
0x18003e486  mov     rax, [rsp+140h+var_100]
0x18003e48b  mov     rcx, [rcx+0D8h]
0x18003e492  mov     [rsp+140h+pPromptStruct], rax
0x18003e497  call    WPP_SF_qSqD
0x18003e49c  jmp     short loc_18003E4DB
0x18003e49e  cmp     cs:byte_18005E5A5, 8
0x18003e4a5  jb      short loc_18003E4DB
0x18003e4a7  mov     eax, [rsp+140h+pDataIn.cbData]
0x18003e4ab  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e4b9  mov     edx, 3Dh ; '='
0x18003e4be  mov     [rsp+140h+dwFlags], eax
0x18003e4c2  mov     r9, rsi
0x18003e4c5  mov     rax, [rsp+140h+pDataIn.pbData]
0x18003e4ca  mov     [rsp+140h+pPromptStruct], rax
0x18003e4cf  mov     rcx, [rcx+0D8h]
0x18003e4d6  call    WPP_SF_qqD
0x18003e4db  lea     rcx, [rsp+140h+var_100]
0x18003e4e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003e4e5  lea     rax, [rsp+140h+var_E8]
0x18003e4ea  xor     r9d, r9d; pvReserved
0x18003e4ed  mov     [rsp+140h+pDataOut], rax; pDataOut
0x18003e4f2  lea     rcx, [rsp+140h+pDataIn]; pDataIn
0x18003e4f7  mov     [rsp+140h+dwFlags], 0; dwFlags
0x18003e4ff  xor     r8d, r8d; pOptionalEntropy
0x18003e502  xor     edx, edx; ppszDataDescr
0x18003e504  mov     [rsp+140h+pPromptStruct], 0; pPromptStruct
0x18003e50d  call    cs:__imp_CryptUnprotectData
0x18003e513  test    eax, eax
0x18003e515  jnz     short loc_18003E547
0x18003e517  call    cs:__imp_GetLastError
0x18003e51d  mov     edi, eax
0x18003e51f  test    eax, eax
0x18003e521  jle     short loc_18003E52C
0x18003e523  movzx   edi, ax
0x18003e526  or      edi, 80070000h
0x18003e52c  test    edi, edi
0x18003e52e  jns     short loc_18003E547
0x18003e530  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e537  jb      loc_18003E70F
0x18003e53d  mov     edx, 3Eh ; '>'
0x18003e542  jmp     loc_18003E1FC
0x18003e547  mov     r8d, [rsp+140h+var_E8.cbData]; cbBufSize
0x18003e54c  mov     rdx, [rsp+140h+var_E8.pbData]; pBuf
0x18003e551  mov     rcx, [rsi+50h]; pAttributes
0x18003e555  call    cs:__imp_MFInitAttributesFromBlob
0x18003e55b  mov     edi, eax
0x18003e55d  test    eax, eax
0x18003e55f  jns     loc_18003E70F
0x18003e565  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e56c  jb      loc_18003E70F
0x18003e572  mov     edx, 3Fh ; '?'
0x18003e577  jmp     loc_18003E6F1
0x18003e57c  mov     rcx, [rsi+50h]; pAttributes
0x18003e580  mov     r8d, r14d; cbBufSize
0x18003e583  mov     rdx, rbx; pBuf
0x18003e586  call    cs:__imp_MFInitAttributesFromBlob
0x18003e58c  mov     edi, eax
0x18003e58e  test    eax, eax
0x18003e590  jns     loc_18003E70F
0x18003e596  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e59d  jb      loc_18003E70F
0x18003e5a3  mov     edx, 40h ; '@'
0x18003e5a8  jmp     loc_18003E6F1
0x18003e5ad  cmp     cs:byte_18005E5A5, 10h
0x18003e5b4  mov     [rsp+140h+pDataIn.pbData], rbx
0x18003e5b9  mov     [rsp+140h+pDataIn.cbData], r14d
0x18003e5be  jb      loc_18003E66B
0x18003e5c4  lea     rdx, [rsp+140h+var_100]
0x18003e5c9  mov     [rsp+140h+var_100], 0
0x18003e5d2  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003e5d7  test    eax, eax
0x18003e5d9  js      short loc_18003E624
0x18003e5db  cmp     cs:byte_18005E5A5, 8
0x18003e5e2  jb      short loc_18003E661
0x18003e5e4  mov     eax, [rsp+140h+pDataIn.cbData]
0x18003e5e8  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5f6  mov     edx, 41h ; 'A'
0x18003e5fb  mov     dword ptr [rsp+140h+pDataOut], eax
0x18003e5ff  mov     r9, rsi
0x18003e602  mov     rax, [rsp+140h+pDataIn.pbData]
0x18003e607  mov     qword ptr [rsp+140h+dwFlags], rax
0x18003e60c  mov     rax, [rsp+140h+var_100]
0x18003e611  mov     rcx, [rcx+0D8h]
0x18003e618  mov     [rsp+140h+pPromptStruct], rax
0x18003e61d  call    WPP_SF_qSqD
0x18003e622  jmp     short loc_18003E661
0x18003e624  cmp     cs:byte_18005E5A5, 8
0x18003e62b  jb      short loc_18003E661
0x18003e62d  mov     eax, [rsp+140h+pDataIn.cbData]
0x18003e631  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e638  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e63f  mov     edx, 42h ; 'B'
0x18003e644  mov     [rsp+140h+dwFlags], eax
0x18003e648  mov     r9, rsi
0x18003e64b  mov     rax, [rsp+140h+pDataIn.pbData]
0x18003e650  mov     [rsp+140h+pPromptStruct], rax
0x18003e655  mov     rcx, [rcx+0D8h]
0x18003e65c  call    WPP_SF_qqD
0x18003e661  lea     rcx, [rsp+140h+var_100]
0x18003e666  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003e66b  lea     rax, [rsp+140h+var_E8]
0x18003e670  xor     r9d, r9d; pvReserved
0x18003e673  mov     [rsp+140h+pDataOut], rax; pDataOut
0x18003e678  lea     rcx, [rsp+140h+pDataIn]; pDataIn
0x18003e67d  mov     [rsp+140h+dwFlags], 0; dwFlags
0x18003e685  xor     r8d, r8d; pOptionalEntropy
0x18003e688  xor     edx, edx; ppszDataDescr
0x18003e68a  mov     [rsp+140h+pPromptStruct], 0; pPromptStruct
0x18003e693  call    cs:__imp_CryptUnprotectData
0x18003e699  test    eax, eax
0x18003e69b  jnz     short loc_18003E6C9
0x18003e69d  call    cs:__imp_GetLastError
0x18003e6a3  mov     edi, eax
0x18003e6a5  test    eax, eax
0x18003e6a7  jle     short loc_18003E6B2
0x18003e6a9  movzx   edi, ax
0x18003e6ac  or      edi, 80070000h
0x18003e6b2  test    edi, edi
0x18003e6b4  jns     short loc_18003E6C9
0x18003e6b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e6bd  jb      short loc_18003E70F
0x18003e6bf  mov     edx, 43h ; 'C'
0x18003e6c4  jmp     loc_18003E1FC
0x18003e6c9  mov     r8d, [rsp+140h+var_E8.cbData]; cbBufSize
0x18003e6ce  mov     rdx, [rsp+140h+var_E8.pbData]; pBuf
0x18003e6d3  mov     rcx, [rsi+50h]; pAttributes
0x18003e6d7  call    cs:__imp_MFInitAttributesFromBlob
  ... truncated ...
```
