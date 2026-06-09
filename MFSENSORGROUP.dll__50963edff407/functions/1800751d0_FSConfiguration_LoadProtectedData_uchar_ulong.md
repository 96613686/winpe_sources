# FSConfiguration::LoadProtectedData(uchar *,ulong)

- ea: `0x1800751d0`
- end: `0x1800757fa`
- name: `?LoadProtectedData@FSConfiguration@@UEAAJPEAEK@Z`
- size: `1578`
- prototype: `int(FSConfiguration *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005fa0`
- `0x18000c2ec`
- `0x180010218`
- `0x18002b778`
- `0x18003d064`
- `0x180044f30`
- `0x180045900`
- `0x18004a074`
- `0x18004a270`
- `0x1800751d0`
- `0x180075a9c`
- `0x180075bd0`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800756c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007573d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007573d`
- `CRYPT32!CryptUnprotectData` at `0x18007553d`
- `CRYPT32!CryptUnprotectData` at `0x1800756bc`
- `CRYPT32!CryptUnprotectData` at `0x18007553d`
- `CRYPT32!CryptUnprotectData` at `0x1800756bc`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075585`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800755b6`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075700`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075585`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800755b6`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075700`

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
  int v24; // r8d
  signed int LastError; // eax
  HRESULT v26; // eax
  __int64 v27; // rdx
  int v28; // r8d
  signed int v29; // eax
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  DATA_BLOB pDataIn; // [rsp+48h] [rbp-B8h] BYREF
  DATA_BLOB pDataOut; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v36[72]; // [rsp+70h] [rbp-90h] BYREF

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
  v9 = byte_18008D62D;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 48LL))(*((_QWORD *)this + 7));
    WPP_SF_qDSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), a3, v12, v11, v10);
    v9 = byte_18008D62D;
  }
  if ( a2 )
  {
    if ( a3 >= 0x28 )
    {
      if ( *(_DWORD *)a2 > a3 )
      {
        v7 = -2147024809;
        if ( v9 )
          WPP_SF_qDDD(
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
        v16 = byte_18008D62D;
        v7 = -2147024809;
        if ( (unsigned __int8)byte_18008D62D >= 0x10u )
        {
          memset_0(v36, 0, 0x82u);
          if ( a2 != (unsigned __int8 *)-8LL )
          {
            v17 = 0;
            v18 = 0;
            do
            {
              v19 = a2[v18++ + 8];
              v36[v17] = a0123456789abcd[(unsigned __int64)v19 >> 4];
              v20 = (unsigned int)(v17 + 1);
              v36[v20] = a0123456789abcd[v19 & 0xF];
              v17 = (unsigned int)(v20 + 1);
            }
            while ( v18 != 32 );
            v36[v17] = 0;
          }
          if ( v16 )
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 72LL))(*((_QWORD *)this + 7));
            WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), 87, (__int64)v36, v21);
          }
        }
        goto LABEL_62;
      }
      v22 = a3 - 40;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
      {
        if ( *((_BYTE *)this + 88) )
        {
          v26 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), a2 + 40, v22);
          v7 = v26;
          if ( v26 >= 0 || !g_wppLevels )
            goto LABEL_62;
          v27 = 64;
        }
        else
        {
          pDataIn.pbData = a2 + 40;
          pDataIn.cbData = v22;
          if ( (unsigned __int8)byte_18008D62D >= 0x10u )
          {
            v33 = 0;
            if ( (int)FSGetUserSidString(v23, (LPWSTR *)&v33) < 0 )
            {
              if ( (unsigned __int8)byte_18008D62D >= 8u )
                WPP_SF_qqD(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  61,
                  &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
                  this,
                  pDataIn.pbData,
                  pDataIn.cbData);
            }
            else if ( (unsigned __int8)byte_18008D62D >= 8u )
            {
              WPP_SF_qSqD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                60,
                v24,
                (_DWORD)this,
                v33,
                (char)pDataIn.pbData,
                pDataIn.cbData);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
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
          v26 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
          v7 = v26;
          if ( v26 >= 0 || !g_wppLevels )
            goto LABEL_62;
          v27 = 63;
        }
      }
      else
      {
        pDataIn.pbData = a2 + 40;
        pDataIn.cbData = v22;
        if ( (unsigned __int8)byte_18008D62D >= 0x10u )
        {
          v33 = 0;
          if ( (int)FSGetUserSidString(v23, (LPWSTR *)&v33) < 0 )
          {
            if ( (unsigned __int8)byte_18008D62D >= 8u )
              WPP_SF_qqD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                66,
                &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
                this,
                pDataIn.pbData,
                pDataIn.cbData);
          }
          else if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            WPP_SF_qSqD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              65,
              v28,
              (_DWORD)this,
              v33,
              (char)pDataIn.pbData,
              pDataIn.cbData);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        }
        if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
        {
          v29 = GetLastError();
          v7 = v29;
          if ( v29 > 0 )
            v7 = (unsigned __int16)v29 | 0x80070000;
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
        v26 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
        v7 = v26;
        if ( v26 >= 0 || !g_wppLevels )
          goto LABEL_62;
        v27 = 68;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v26);
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
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
LABEL_66:
      v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 56LL))(*((_QWORD *)this + 7));
      v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7));
      WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, v31, v30);
    }
  }
  else if ( byte_18008D62D )
  {
    goto LABEL_66;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800751d0  push    rbp
0x1800751d2  push    rbx
0x1800751d3  push    rsi
0x1800751d4  push    rdi
0x1800751d5  push    r12
0x1800751d7  push    r14
0x1800751d9  push    r15
0x1800751db  lea     rbp, [rsp-10h]
0x1800751e0  sub     rsp, 110h
0x1800751e7  mov     rax, cs:__security_cookie
0x1800751ee  xor     rax, rsp
0x1800751f1  mov     [rbp+40h+var_40], rax
0x1800751f5  mov     rsi, rcx
0x1800751f8  xorps   xmm0, xmm0
0x1800751fb  mov     rcx, [rcx+38h]
0x1800751ff  xorps   xmm1, xmm1
0x180075202  mov     r14d, r8d
0x180075205  mov     r15, rdx
0x180075208  movups  xmmword ptr [rsp+140h+pDataIn.cbData], xmm0
0x18007520d  movups  xmmword ptr [rsp+140h+var_E8.cbData], xmm1
0x180075212  test    rcx, rcx
0x180075215  jnz     short loc_180075235
0x180075217  mov     edi, 80070057h
0x18007521c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075223  jb      loc_180075738
0x180075229  lea     edx, [rcx+36h]
0x18007522c  mov     dword ptr [rsp+140h+pPromptStruct], edi
0x180075230  jmp     loc_18007571E
0x180075235  mov     al, cs:byte_18008D62D
0x18007523b  cmp     al, 8
0x18007523d  jb      short loc_1800752A1
0x18007523f  mov     rax, [rcx]
0x180075242  mov     rax, [rax+38h]
0x180075246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007524b  mov     rcx, [rsi+38h]
0x18007524f  mov     rdi, rax
0x180075252  mov     rax, [rcx]
0x180075255  mov     rax, [rax+40h]
0x180075259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007525e  mov     rcx, [rsi+38h]
0x180075262  mov     rbx, rax
0x180075265  mov     rax, [rcx]
0x180075268  mov     rax, [rax+30h]
0x18007526c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075271  mov     rcx, cs:WPP_GLOBAL_Control
0x180075278  mov     r9, rsi
0x18007527b  mov     [rsp+140h+var_108], rdi; __int64
0x180075280  mov     [rsp+140h+pDataOut], rbx; __int64
0x180075285  mov     qword ptr [rsp+140h+dwFlags], rax; __int64
0x18007528a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180075291  mov     dword ptr [rsp+140h+pPromptStruct], r14d; char
0x180075296  call    WPP_SF_qDSSS
0x18007529b  mov     al, cs:byte_18008D62D
0x1800752a1  test    r15, r15
0x1800752a4  jnz     short loc_1800752C1
0x1800752a6  mov     edi, 80070057h
0x1800752ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800752b2  jb      loc_180075738
0x1800752b8  lea     edx, [r15+38h]
0x1800752bc  jmp     loc_18007522C
0x1800752c1  cmp     r14d, 28h ; '('
0x1800752c5  jnb     short loc_1800752E3
0x1800752c7  mov     edi, 80070057h
0x1800752cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800752d3  jb      loc_180075738
0x1800752d9  mov     edx, 39h ; '9'
0x1800752de  jmp     loc_18007522C
0x1800752e3  mov     ecx, [r15]
0x1800752e6  cmp     ecx, r14d
0x1800752e9  jbe     short loc_180075330
0x1800752eb  mov     edi, 80070057h
0x1800752f0  cmp     al, 1
0x1800752f2  jb      loc_180075738
0x1800752f8  mov     dword ptr [rsp+140h+pDataOut], r14d
0x1800752fd  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180075304  mov     [rsp+140h+dwFlags], ecx
0x180075308  mov     edx, 3Ah ; ':'
0x18007530d  mov     rcx, cs:WPP_GLOBAL_Control
0x180075314  mov     r9, rsi
0x180075317  mov     dword ptr [rsp+140h+pPromptStruct], 80070057h
0x18007531f  mov     rcx, [rcx+0D8h]
0x180075326  call    WPP_SF_qDDD
0x18007532b  jmp     loc_180075738
0x180075330  mov     rdi, [rsi+38h]
0x180075334  mov     rcx, rdi
0x180075337  mov     rax, [rdi]
0x18007533a  mov     rax, [rax+28h]
0x18007533e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075343  mov     ebx, eax
0x180075345  lea     r12, [r15+8]
0x180075349  mov     rax, [rdi]
0x18007534c  mov     rcx, rdi
0x18007534f  mov     rax, [rax+20h]
0x180075353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075358  mov     rdx, rax; Buf2
0x18007535b  mov     r8d, ebx; Size
0x18007535e  mov     rcx, r12; Buf1
0x180075361  call    memcmp_0
0x180075366  test    eax, eax
0x180075368  jz      loc_180075438
0x18007536e  mov     bl, cs:byte_18008D62D
0x180075374  mov     edi, 80070057h
0x180075379  cmp     bl, 10h
0x18007537c  jb      loc_180075738
0x180075382  xor     edx, edx; Val
0x180075384  lea     rcx, [rsp+140h+var_D0]; void *
0x180075389  mov     r8d, 82h; Size
0x18007538f  call    memset_0
0x180075394  test    r12, r12
0x180075397  jz      short loc_1800753E1
0x180075399  xor     r8d, r8d
0x18007539c  lea     r10, a0123456789abcd; "0123456789ABCDEF"
0x1800753a3  xor     r9d, r9d
0x1800753a6  movzx   edx, byte ptr [r12+r9]
0x1800753ab  inc     r9
0x1800753ae  mov     eax, edx
0x1800753b0  and     edx, 0Fh
0x1800753b3  shr     rax, 4
0x1800753b7  movzx   eax, word ptr [r10+rax*2]
0x1800753bc  mov     [rsp+r8*2+140h+var_D0], ax
0x1800753c2  inc     r8d
0x1800753c5  movzx   eax, word ptr [r10+rdx*2]
0x1800753ca  mov     [rsp+r8*2+140h+var_D0], ax
0x1800753d0  inc     r8d
0x1800753d3  cmp     r9, 20h ; ' '
0x1800753d7  jnz     short loc_1800753A6
0x1800753d9  xor     eax, eax
0x1800753db  mov     [rsp+r8*2+140h+var_D0], ax
0x1800753e1  cmp     bl, 1
0x1800753e4  jb      loc_180075738
0x1800753ea  mov     rcx, [rsi+38h]
0x1800753ee  mov     rax, [rcx]
0x1800753f1  mov     rax, [rax+48h]
0x1800753f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800753fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180075401  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180075408  mov     [rsp+140h+pDataOut], rax; __int64
0x18007540d  mov     edx, 3Bh ; ';'
0x180075412  lea     rax, [rsp+140h+var_D0]
0x180075417  mov     r9, rsi
0x18007541a  mov     qword ptr [rsp+140h+dwFlags], rax; __int64
0x18007541f  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180075426  mov     dword ptr [rsp+140h+pPromptStruct], 80070057h; char
0x18007542e  call    WPP_SF_qDSS
0x180075433  jmp     loc_180075738
0x180075438  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18007543f  add     r14d, 0FFFFFFD8h
0x180075443  lea     rbx, [r15+28h]
0x180075447  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18007544c  test    al, al
0x18007544e  jz      loc_1800755DD
0x180075454  cmp     byte ptr [rsi+58h], 0
0x180075458  jnz     loc_1800755AC
0x18007545e  cmp     cs:byte_18008D62D, 10h
0x180075465  mov     [rsp+140h+pDataIn.pbData], rbx
0x18007546a  mov     [rsp+140h+pDataIn.cbData], r14d
0x18007546f  jb      loc_180075515
0x180075475  lea     rdx, [rsp+140h+var_100]
0x18007547a  mov     [rsp+140h+var_100], 0
0x180075483  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180075488  test    eax, eax
0x18007548a  js      short loc_1800754CE
0x18007548c  cmp     cs:byte_18008D62D, 8
0x180075493  jb      short loc_18007550B
0x180075495  mov     eax, [rsp+140h+pDataIn.cbData]
0x180075499  mov     edx, 3Ch ; '<'
0x18007549e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800754a5  mov     r9, rsi
0x1800754a8  mov     dword ptr [rsp+140h+pDataOut], eax
0x1800754ac  mov     rax, [rsp+140h+pDataIn.pbData]
0x1800754b1  mov     qword ptr [rsp+140h+dwFlags], rax
0x1800754b6  mov     rax, [rsp+140h+var_100]
0x1800754bb  mov     rcx, [rcx+0D8h]
0x1800754c2  mov     [rsp+140h+pPromptStruct], rax
0x1800754c7  call    WPP_SF_qSqD
0x1800754cc  jmp     short loc_18007550B
0x1800754ce  cmp     cs:byte_18008D62D, 8
0x1800754d5  jb      short loc_18007550B
0x1800754d7  mov     eax, [rsp+140h+pDataIn.cbData]
0x1800754db  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800754e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800754e9  mov     edx, 3Dh ; '='
0x1800754ee  mov     [rsp+140h+dwFlags], eax
0x1800754f2  mov     r9, rsi
0x1800754f5  mov     rax, [rsp+140h+pDataIn.pbData]
0x1800754fa  mov     [rsp+140h+pPromptStruct], rax
0x1800754ff  mov     rcx, [rcx+0D8h]
0x180075506  call    WPP_SF_qqD
0x18007550b  lea     rcx, [rsp+140h+var_100]
0x180075510  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180075515  lea     rax, [rsp+140h+var_E8]
0x18007551a  xor     r9d, r9d; pvReserved
0x18007551d  mov     [rsp+140h+pDataOut], rax; pDataOut
0x180075522  lea     rcx, [rsp+140h+pDataIn]; pDataIn
0x180075527  mov     [rsp+140h+dwFlags], 0; dwFlags
0x18007552f  xor     r8d, r8d; pOptionalEntropy
0x180075532  xor     edx, edx; ppszDataDescr
0x180075534  mov     [rsp+140h+pPromptStruct], 0; pPromptStruct
0x18007553d  call    cs:__imp_CryptUnprotectData
0x180075543  test    eax, eax
0x180075545  jnz     short loc_180075577
0x180075547  call    cs:__imp_GetLastError
0x18007554d  mov     edi, eax
0x18007554f  test    eax, eax
0x180075551  jle     short loc_18007555C
0x180075553  movzx   edi, ax
0x180075556  or      edi, 80070000h
0x18007555c  test    edi, edi
0x18007555e  jns     short loc_180075577
0x180075560  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075567  jb      loc_180075738
0x18007556d  mov     edx, 3Eh ; '>'
0x180075572  jmp     loc_18007522C
0x180075577  mov     r8d, [rsp+140h+var_E8.cbData]; cbBufSize
0x18007557c  mov     rdx, [rsp+140h+var_E8.pbData]; pBuf
0x180075581  mov     rcx, [rsi+50h]; pAttributes
0x180075585  call    cs:__imp_MFInitAttributesFromBlob
0x18007558b  mov     edi, eax
0x18007558d  test    eax, eax
0x18007558f  jns     loc_180075738
0x180075595  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007559c  jb      loc_180075738
0x1800755a2  mov     edx, 3Fh ; '?'
0x1800755a7  jmp     loc_18007571A
0x1800755ac  mov     rcx, [rsi+50h]; pAttributes
0x1800755b0  mov     r8d, r14d; cbBufSize
0x1800755b3  mov     rdx, rbx; pBuf
0x1800755b6  call    cs:__imp_MFInitAttributesFromBlob
0x1800755bc  mov     edi, eax
0x1800755be  test    eax, eax
0x1800755c0  jns     loc_180075738
0x1800755c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800755cd  jb      loc_180075738
0x1800755d3  mov     edx, 40h ; '@'
0x1800755d8  jmp     loc_18007571A
0x1800755dd  cmp     cs:byte_18008D62D, 10h
0x1800755e4  mov     [rsp+140h+pDataIn.pbData], rbx
0x1800755e9  mov     [rsp+140h+pDataIn.cbData], r14d
0x1800755ee  jb      loc_180075694
0x1800755f4  lea     rdx, [rsp+140h+var_100]
0x1800755f9  mov     [rsp+140h+var_100], 0
0x180075602  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180075607  test    eax, eax
0x180075609  js      short loc_18007564D
0x18007560b  cmp     cs:byte_18008D62D, 8
0x180075612  jb      short loc_18007568A
0x180075614  mov     eax, [rsp+140h+pDataIn.cbData]
0x180075618  mov     edx, 41h ; 'A'
0x18007561d  mov     rcx, cs:WPP_GLOBAL_Control
0x180075624  mov     r9, rsi
0x180075627  mov     dword ptr [rsp+140h+pDataOut], eax
0x18007562b  mov     rax, [rsp+140h+pDataIn.pbData]
0x180075630  mov     qword ptr [rsp+140h+dwFlags], rax
0x180075635  mov     rax, [rsp+140h+var_100]
0x18007563a  mov     rcx, [rcx+0D8h]
0x180075641  mov     [rsp+140h+pPromptStruct], rax
0x180075646  call    WPP_SF_qSqD
0x18007564b  jmp     short loc_18007568A
0x18007564d  cmp     cs:byte_18008D62D, 8
0x180075654  jb      short loc_18007568A
0x180075656  mov     eax, [rsp+140h+pDataIn.cbData]
0x18007565a  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180075661  mov     rcx, cs:WPP_GLOBAL_Control
0x180075668  mov     edx, 42h ; 'B'
0x18007566d  mov     [rsp+140h+dwFlags], eax
0x180075671  mov     r9, rsi
0x180075674  mov     rax, [rsp+140h+pDataIn.pbData]
0x180075679  mov     [rsp+140h+pPromptStruct], rax
0x18007567e  mov     rcx, [rcx+0D8h]
0x180075685  call    WPP_SF_qqD
0x18007568a  lea     rcx, [rsp+140h+var_100]
0x18007568f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180075694  lea     rax, [rsp+140h+var_E8]
0x180075699  xor     r9d, r9d; pvReserved
0x18007569c  mov     [rsp+140h+pDataOut], rax; pDataOut
0x1800756a1  lea     rcx, [rsp+140h+pDataIn]; pDataIn
0x1800756a6  mov     [rsp+140h+dwFlags], 0; dwFlags
0x1800756ae  xor     r8d, r8d; pOptionalEntropy
0x1800756b1  xor     edx, edx; ppszDataDescr
0x1800756b3  mov     [rsp+140h+pPromptStruct], 0; pPromptStruct
0x1800756bc  call    cs:__imp_CryptUnprotectData
0x1800756c2  test    eax, eax
0x1800756c4  jnz     short loc_1800756F2
0x1800756c6  call    cs:__imp_GetLastError
0x1800756cc  mov     edi, eax
0x1800756ce  test    eax, eax
0x1800756d0  jle     short loc_1800756DB
0x1800756d2  movzx   edi, ax
0x1800756d5  or      edi, 80070000h
0x1800756db  test    edi, edi
0x1800756dd  jns     short loc_1800756F2
0x1800756df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800756e6  jb      short loc_180075738
0x1800756e8  mov     edx, 43h ; 'C'
0x1800756ed  jmp     loc_18007522C
0x1800756f2  mov     r8d, [rsp+140h+var_E8.cbData]; cbBufSize
0x1800756f7  mov     rdx, [rsp+140h+var_E8.pbData]; pBuf
0x1800756fc  mov     rcx, [rsi+50h]; pAttributes
0x180075700  call    cs:__imp_MFInitAttributesFromBlob
0x180075706  mov     edi, eax
  ... truncated ...
```
