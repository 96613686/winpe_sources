# FSConfiguration::InternalInitializeGlobalConfiguration(IFSConfigurationKey *,uchar const *,ulong,bool)

- ea: `0x180038790`
- end: `0x180038b71`
- name: `?InternalInitializeGlobalConfiguration@FSConfiguration@@MEAAJPEAUIFSConfigurationKey@@PEBEK_N@Z`
- size: `993`
- prototype: `__int64 __fastcall(FSConfiguration *this, struct IFSConfigurationKey *, const unsigned __int8 *, unsigned int, bool)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009f50`
- `0x18000a600`
- `0x18000a880`
- `0x18000a91c`
- `0x180017a3c`
- `0x1800180c8`
- `0x18002ed08`
- `0x180038790`
- `0x1800396c0`
- `0x1800e924c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a95`
- `CRYPT32!CryptUnprotectData` at `0x1800389f6`
- `CRYPT32!CryptUnprotectData` at `0x1800389f6`
- `MFPlat!MFCreateAttributes` at `0x1800388e9`
- `MFPlat!MFCreateAttributes` at `0x1800388e9`
- `MFPlat!MFInitAttributesFromBlob` at `0x180038a6c`
- `MFPlat!MFInitAttributesFromBlob` at `0x180038aa5`
- `MFPlat!MFInitAttributesFromBlob` at `0x180038a6c`
- `MFPlat!MFInitAttributesFromBlob` at `0x180038aa5`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitializeGlobalConfiguration(
        FSConfiguration *this,
        struct IFSConfigurationKey *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        bool a5)
{
  size_t v5; // r14
  HRESULT v9; // eax
  signed int v10; // edi
  __int64 v11; // rdx
  __int64 unique; // rax
  const UINT8 *v13; // rbx
  __int64 v14; // rcx
  bool v15; // r12
  int v16; // r8d
  signed int LastError; // eax
  char *v18; // r15
  HRESULT v19; // eax
  __int64 v20; // rdx
  void *v22; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+48h] [rbp-30h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-28h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-18h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+D0h] [rbp+58h] BYREF

  v5 = a4;
  ppMFAttributes = 0;
  v22 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 27), 89, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, a3, a4);
  if ( !a3 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_46;
    v11 = 90;
LABEL_45:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v9);
    goto LABEL_46;
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_46;
    v11 = 91;
    goto LABEL_45;
  }
  if ( (unsigned int)v5 < 0x28 )
  {
    v9 = -2147023881;
    v10 = -2147023881;
    if ( !g_wppLevels )
      goto LABEL_46;
    v11 = 92;
    goto LABEL_45;
  }
  if ( *(_DWORD *)a3 > (unsigned int)v5 )
  {
    v9 = -2147023881;
    v10 = -2147023881;
    if ( !g_wppLevels )
      goto LABEL_46;
    v11 = 93;
    goto LABEL_45;
  }
  unique = wil::make_unique_nothrow<unsigned char [0]>(&v23, v5);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v22, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v23);
  v13 = (const UINT8 *)v22;
  if ( !v22 )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v22 + 94),
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024882);
    goto LABEL_46;
  }
  memcpy_0(v22, a3, v5);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v9 = MFCreateAttributes(&ppMFAttributes, 1u);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_46;
    v11 = 95;
    goto LABEL_45;
  }
  v15 = a5;
  if ( a5 )
  {
    v9 = MFInitAttributesFromBlob(ppMFAttributes, v13 + 40, v5 - 40);
    v10 = v9;
    if ( v9 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_46;
      v11 = 100;
      goto LABEL_45;
    }
    v18 = (char *)this + 80;
  }
  else
  {
    pDataIn.pbData = (BYTE *)(v13 + 40);
    pDataOut = 0;
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.cbData = v5 - 40;
    if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    {
      v23 = 0;
      if ( (int)FSGetUserSidString(v14, &v23) < 0 )
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            97,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            pDataIn.pbData,
            pDataIn.cbData);
      }
      else if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        WPP_SF_qSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          96,
          v16,
          (_DWORD)this,
          v23,
          (char)pDataIn.pbData,
          pDataIn.cbData);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    }
    if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            v10);
LABEL_35:
        if ( pDataOut.pbData )
          LocalFree(pDataOut.pbData);
LABEL_46:
        if ( byte_18010EC4D )
        {
          v20 = 101;
LABEL_51:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v20,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            v10);
          goto LABEL_52;
        }
        goto LABEL_52;
      }
    }
    v18 = (char *)this + 80;
    v19 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
    v10 = v19;
    if ( v19 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v19);
      goto LABEL_35;
    }
    if ( pDataOut.pbData )
      LocalFree(pDataOut.pbData);
  }
  v22 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v13;
  *((_DWORD *)this + 18) = v5;
  *((_BYTE *)this + 88) = v15;
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((char *)this + 56, a2);
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(v18, ppMFAttributes);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v20 = 102;
    goto LABEL_51;
  }
LABEL_52:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v22);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180038790  push    rbp
0x180038792  push    rbx
0x180038793  push    rsi
0x180038794  push    rdi
0x180038795  push    r12
0x180038797  push    r13
0x180038799  push    r14
0x18003879b  push    r15
0x18003879d  mov     rbp, rsp
0x1800387a0  sub     rsp, 78h
0x1800387a4  mov     r14d, r9d
0x1800387a7  mov     rdi, r8
0x1800387aa  mov     r13, rdx
0x1800387ad  mov     [rbp+ppMFAttributes], 0
0x1800387b5  mov     rsi, rcx
0x1800387b8  mov     [rbp+var_38], 0
0x1800387c0  cmp     cs:byte_18010EC4D, 8
0x1800387c7  jb      short loc_1800387F5
0x1800387c9  mov     r9, rcx
0x1800387cc  mov     [rsp+78h+dwFlags], r14d
0x1800387d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387d8  mov     edx, 59h ; 'Y'
0x1800387dd  mov     [rsp+78h+pPromptStruct], r8
0x1800387e2  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800387e9  mov     rcx, [rcx+0D8h]
0x1800387f0  call    WPP_SF_qqD
0x1800387f5  test    rdi, rdi
0x1800387f8  jnz     short loc_180038818
0x1800387fa  mov     eax, 80070057h
0x1800387ff  mov     edi, eax
0x180038801  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038808  jb      loc_180038ADD
0x18003880e  mov     edx, 5Ah ; 'Z'
0x180038813  jmp     loc_180038ABF
0x180038818  test    r13, r13
0x18003881b  jnz     short loc_18003883A
0x18003881d  mov     eax, 80070057h
0x180038822  mov     edi, eax
0x180038824  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003882b  jb      loc_180038ADD
0x180038831  lea     edx, [r13+5Bh]
0x180038835  jmp     loc_180038ABF
0x18003883a  cmp     r14d, 28h ; '('
0x18003883e  jnb     short loc_18003885E
0x180038840  mov     eax, 800703F7h
0x180038845  mov     edi, eax
0x180038847  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003884e  jb      loc_180038ADD
0x180038854  mov     edx, 5Ch ; '\'
0x180038859  jmp     loc_180038ABF
0x18003885e  cmp     [rdi], r14d
0x180038861  jbe     short loc_180038881
0x180038863  mov     eax, 800703F7h
0x180038868  mov     edi, eax
0x18003886a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038871  jb      loc_180038ADD
0x180038877  mov     edx, 5Dh ; ']'
0x18003887c  jmp     loc_180038ABF
0x180038881  mov     rdx, r14
0x180038884  lea     rcx, [rbp+var_30]
0x180038888  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003888d  mov     rdx, rax
0x180038890  lea     rcx, [rbp+var_38]
0x180038894  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x180038899  lea     rcx, [rbp+var_30]
0x18003889d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800388a2  mov     rbx, [rbp+var_38]
0x1800388a6  test    rbx, rbx
0x1800388a9  jnz     short loc_1800388C9
0x1800388ab  mov     edi, 8007000Eh
0x1800388b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800388b7  jb      loc_180038ADD
0x1800388bd  lea     edx, [rbx+5Eh]
0x1800388c0  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x1800388c4  jmp     loc_180038AC3
0x1800388c9  mov     r8, r14; Size
0x1800388cc  mov     rdx, rdi; Src
0x1800388cf  mov     rcx, rbx; void *
0x1800388d2  call    memcpy_0
0x1800388d7  lea     rcx, [rbp+ppMFAttributes]
0x1800388db  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800388e0  mov     edx, 1; cInitialSize
0x1800388e5  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1800388e9  call    cs:__imp_MFCreateAttributes
0x1800388ef  xor     r15d, r15d
0x1800388f2  mov     edi, eax
0x1800388f4  test    eax, eax
0x1800388f6  jns     short loc_18003890E
0x1800388f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800388ff  jb      loc_180038ADD
0x180038905  lea     edx, [r15+5Fh]
0x180038909  jmp     loc_180038ABF
0x18003890e  mov     r12b, [rbp+arg_20]
0x180038912  lea     r8d, [r14-28h]; cbBufSize
0x180038916  test    r12b, r12b
0x180038919  jnz     loc_180038A9D
0x18003891f  cmp     cs:byte_18010EC4D, 10h
0x180038926  lea     rax, [rbx+28h]
0x18003892a  xorps   xmm0, xmm0
0x18003892d  mov     [rbp+pDataIn.pbData], rax
0x180038931  movups  xmmword ptr [rbp+var_18.cbData], xmm0
0x180038935  mov     dword ptr [rbp+pDataIn+4], r15d
0x180038939  mov     [rbp+pDataIn.cbData], r8d
0x18003893d  jb      loc_1800389D7
0x180038943  lea     rdx, [rbp+var_30]
0x180038947  mov     [rbp+var_30], r15
0x18003894b  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180038950  test    eax, eax
0x180038952  js      short loc_180038993
0x180038954  cmp     cs:byte_18010EC4D, 8
0x18003895b  jb      short loc_1800389CE
0x18003895d  mov     eax, [rbp+pDataIn.cbData]
0x180038960  mov     edx, 60h ; '`'
0x180038965  mov     rcx, cs:WPP_GLOBAL_Control
0x18003896c  mov     r9, rsi
0x18003896f  mov     dword ptr [rsp+78h+pDataOut], eax
0x180038973  mov     rax, [rbp+pDataIn.pbData]
0x180038977  mov     qword ptr [rsp+78h+dwFlags], rax
0x18003897c  mov     rax, [rbp+var_30]
0x180038980  mov     rcx, [rcx+0D8h]
0x180038987  mov     [rsp+78h+pPromptStruct], rax
0x18003898c  call    WPP_SF_qSqD
0x180038991  jmp     short loc_1800389CE
0x180038993  cmp     cs:byte_18010EC4D, 8
0x18003899a  jb      short loc_1800389CE
0x18003899c  mov     eax, [rbp+pDataIn.cbData]
0x18003899f  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800389a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389ad  mov     edx, 61h ; 'a'
0x1800389b2  mov     [rsp+78h+dwFlags], eax
0x1800389b6  mov     r9, rsi
0x1800389b9  mov     rax, [rbp+pDataIn.pbData]
0x1800389bd  mov     [rsp+78h+pPromptStruct], rax
0x1800389c2  mov     rcx, [rcx+0D8h]
0x1800389c9  call    WPP_SF_qqD
0x1800389ce  lea     rcx, [rbp+var_30]
0x1800389d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800389d7  lea     rax, [rbp+var_18]
0x1800389db  xor     r9d, r9d; pvReserved
0x1800389de  mov     [rsp+78h+pDataOut], rax; pDataOut
0x1800389e3  lea     rcx, [rbp+pDataIn]; pDataIn
0x1800389e7  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x1800389ec  xor     r8d, r8d; pOptionalEntropy
0x1800389ef  xor     edx, edx; ppszDataDescr
0x1800389f1  mov     [rsp+78h+pPromptStruct], r15; pPromptStruct
0x1800389f6  call    cs:__imp_CryptUnprotectData
0x1800389fc  test    eax, eax
0x1800389fe  jnz     short loc_180038A5D
0x180038a00  call    cs:__imp_GetLastError
0x180038a06  mov     edi, eax
0x180038a08  test    eax, eax
0x180038a0a  jle     short loc_180038A15
0x180038a0c  movzx   edi, ax
0x180038a0f  or      edi, 80070000h
0x180038a15  test    edi, edi
0x180038a17  jns     short loc_180038A5D
0x180038a19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038a20  jb      short loc_180038A45
0x180038a22  mov     edx, 62h ; 'b'
0x180038a27  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x180038a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a32  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180038a39  mov     r9, rsi
0x180038a3c  mov     rcx, [rcx+10h]
0x180038a40  call    WPP_SF_qD
0x180038a45  mov     rcx, [rbp+var_18.pbData]; hMem
0x180038a49  test    rcx, rcx
0x180038a4c  jz      loc_180038ADD
0x180038a52  call    cs:__imp_LocalFree
0x180038a58  jmp     loc_180038ADD
0x180038a5d  mov     r8d, [rbp+var_18.cbData]; cbBufSize
0x180038a61  lea     r15, [rsi+50h]
0x180038a65  mov     rcx, [r15]; pAttributes
0x180038a68  mov     rdx, [rbp+var_18.pbData]; pBuf
0x180038a6c  call    cs:__imp_MFInitAttributesFromBlob
0x180038a72  mov     edi, eax
0x180038a74  test    eax, eax
0x180038a76  jns     short loc_180038A8C
0x180038a78  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038a7f  jb      short loc_180038A45
0x180038a81  mov     edx, 63h ; 'c'
0x180038a86  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x180038a8a  jmp     short loc_180038A2B
0x180038a8c  mov     rcx, [rbp+var_18.pbData]; hMem
0x180038a90  test    rcx, rcx
0x180038a93  jz      short loc_180038AF1
0x180038a95  call    cs:__imp_LocalFree
0x180038a9b  jmp     short loc_180038AF1
0x180038a9d  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x180038aa1  lea     rdx, [rbx+28h]; pBuf
0x180038aa5  call    cs:__imp_MFInitAttributesFromBlob
0x180038aab  mov     edi, eax
0x180038aad  test    eax, eax
0x180038aaf  jns     short loc_180038AED
0x180038ab1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038ab8  jb      short loc_180038ADD
0x180038aba  mov     edx, 64h ; 'd'
0x180038abf  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x180038ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180038aca  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180038ad1  mov     r9, rsi
0x180038ad4  mov     rcx, [rcx+10h]
0x180038ad8  call    WPP_SF_qD
0x180038add  cmp     cs:byte_18010EC4D, 1
0x180038ae4  jb      short loc_180038B4C
0x180038ae6  mov     edx, 65h ; 'e'
0x180038aeb  jmp     short loc_180038B2B
0x180038aed  lea     r15, [rsi+50h]
0x180038af1  mov     rax, [rsi+40h]
0x180038af5  lea     rcx, [rsi+38h]
0x180038af9  mov     rdx, r13
0x180038afc  mov     [rbp+var_38], rax
0x180038b00  mov     [rsi+40h], rbx
0x180038b04  mov     [rsi+48h], r14d
0x180038b08  mov     [rsi+58h], r12b
0x180038b0c  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180038b11  mov     rdx, [rbp+ppMFAttributes]
0x180038b15  mov     rcx, r15
0x180038b18  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180038b1d  cmp     cs:byte_18010EC4D, 8
0x180038b24  jb      short loc_180038B4C
0x180038b26  mov     edx, 66h ; 'f'
0x180038b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b32  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180038b39  mov     r9, rsi
0x180038b3c  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x180038b40  mov     rcx, [rcx+0D8h]
0x180038b47  call    WPP_SF_qD
0x180038b4c  lea     rcx, [rbp+var_38]
0x180038b50  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180038b55  lea     rcx, [rbp+ppMFAttributes]; void *
0x180038b59  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180038b5e  mov     eax, edi
0x180038b60  add     rsp, 78h
0x180038b64  pop     r15
0x180038b66  pop     r14
0x180038b68  pop     r13
0x180038b6a  pop     r12
0x180038b6c  pop     rdi
0x180038b6d  pop     rsi
0x180038b6e  pop     rbx
0x180038b6f  pop     rbp
0x180038b70  retn
```
