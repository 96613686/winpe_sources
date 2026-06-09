# FSConfiguration::InternalInitializeGlobalConfiguration(IFSConfigurationKey *,uchar const *,ulong,bool)

- ea: `0x18003dd10`
- end: `0x18003e0f8`
- name: `?InternalInitializeGlobalConfiguration@FSConfiguration@@MEAAJPEAUIFSConfigurationKey@@PEBEK_N@Z`
- size: `1000`
- prototype: `int(FSConfiguration *__hidden this, struct IFSConfigurationKey *, const unsigned __int8 *, unsigned int, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005f98`
- `0x180005ff8`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x180007020`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d7c4`
- `0x18001c63c`
- `0x180035f40`
- `0x18003c670`
- `0x18003dd10`
- `0x18004bf50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dfd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e01c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dfd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e01c`
- `CRYPT32!CryptUnprotectData` at `0x18003df7d`
- `CRYPT32!CryptUnprotectData` at `0x18003df7d`
- `MFPlat!MFCreateAttributes` at `0x18003de69`
- `MFPlat!MFCreateAttributes` at `0x18003de69`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003dff3`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e02c`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003dff3`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003e02c`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitializeGlobalConfiguration(
        FSConfiguration *this,
        struct IFSConfigurationKey *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        bool a5)
{
  unsigned __int64 v5; // r14
  HRESULT v9; // eax
  signed int v10; // edi
  __int64 v11; // rdx
  const struct std::nothrow_t *unique; // rax
  const UINT8 *v13; // rbx
  __int64 v14; // rcx
  bool v15; // r12
  signed int LastError; // eax
  __int64 *v17; // r15
  HRESULT v18; // eax
  __int64 v19; // rdx
  void *v21; // [rsp+40h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-30h] BYREF
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-28h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-18h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+D0h] [rbp+58h] BYREF

  v5 = a4;
  ppMFAttributes = 0;
  v21 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
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
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v22, v5);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v21, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v22);
  v13 = (const UINT8 *)v21;
  if ( !v21 )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v21 + 94),
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024882);
    goto LABEL_46;
  }
  memcpy_0(v21, a3, v5);
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
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
    v17 = (__int64 *)((char *)this + 80);
  }
  else
  {
    pDataIn.pbData = (BYTE *)(v13 + 40);
    pDataOut = 0;
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.cbData = v5 - 40;
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      v22 = 0;
      if ( (int)FSGetUserSidString(v14, (LPWSTR *)&v22) < 0 )
      {
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            97,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            pDataIn.pbData,
            pDataIn.cbData);
      }
      else if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        WPP_SF_qSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          96,
          (unsigned int)&WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
          (_DWORD)this,
          v22,
          (char)pDataIn.pbData,
          pDataIn.cbData);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v22);
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
        if ( byte_18005E5A5 )
        {
          v19 = 101;
LABEL_51:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v19,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            v10);
          goto LABEL_52;
        }
        goto LABEL_52;
      }
    }
    v17 = (__int64 *)((char *)this + 80);
    v18 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 10), pDataOut.pbData, pDataOut.cbData);
    v10 = v18;
    if ( v18 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v18);
      goto LABEL_35;
    }
    if ( pDataOut.pbData )
      LocalFree(pDataOut.pbData);
  }
  v21 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v13;
  *((_DWORD *)this + 18) = v5;
  *((_BYTE *)this + 88) = v15;
  wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=((__int64 *)this + 7, (__int64)a2);
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::operator=(v17, (__int64 *)&ppMFAttributes);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v19 = 102;
    goto LABEL_51;
  }
LABEL_52:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v21);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003dd10  push    rbp
0x18003dd12  push    rbx
0x18003dd13  push    rsi
0x18003dd14  push    rdi
0x18003dd15  push    r12
0x18003dd17  push    r13
0x18003dd19  push    r14
0x18003dd1b  push    r15
0x18003dd1d  mov     rbp, rsp
0x18003dd20  sub     rsp, 78h
0x18003dd24  mov     r14d, r9d
0x18003dd27  mov     rdi, r8
0x18003dd2a  mov     r13, rdx
0x18003dd2d  mov     [rbp+ppMFAttributes], 0
0x18003dd35  mov     rsi, rcx
0x18003dd38  mov     [rbp+var_38], 0
0x18003dd40  cmp     cs:byte_18005E5A5, 8
0x18003dd47  jb      short loc_18003DD75
0x18003dd49  mov     r9, rcx
0x18003dd4c  mov     [rsp+78h+dwFlags], r14d
0x18003dd51  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd58  mov     edx, 59h ; 'Y'
0x18003dd5d  mov     [rsp+78h+pPromptStruct], r8
0x18003dd62  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003dd69  mov     rcx, [rcx+0D8h]
0x18003dd70  call    WPP_SF_qqD
0x18003dd75  test    rdi, rdi
0x18003dd78  jnz     short loc_18003DD98
0x18003dd7a  mov     eax, 80070057h
0x18003dd7f  mov     edi, eax
0x18003dd81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dd88  jb      loc_18003E064
0x18003dd8e  mov     edx, 5Ah ; 'Z'
0x18003dd93  jmp     loc_18003E046
0x18003dd98  test    r13, r13
0x18003dd9b  jnz     short loc_18003DDBA
0x18003dd9d  mov     eax, 80070057h
0x18003dda2  mov     edi, eax
0x18003dda4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ddab  jb      loc_18003E064
0x18003ddb1  lea     edx, [r13+5Bh]
0x18003ddb5  jmp     loc_18003E046
0x18003ddba  cmp     r14d, 28h ; '('
0x18003ddbe  jnb     short loc_18003DDDE
0x18003ddc0  mov     eax, 800703F7h
0x18003ddc5  mov     edi, eax
0x18003ddc7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ddce  jb      loc_18003E064
0x18003ddd4  mov     edx, 5Ch ; '\'
0x18003ddd9  jmp     loc_18003E046
0x18003ddde  cmp     [rdi], r14d
0x18003dde1  jbe     short loc_18003DE01
0x18003dde3  mov     eax, 800703F7h
0x18003dde8  mov     edi, eax
0x18003ddea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ddf1  jb      loc_18003E064
0x18003ddf7  mov     edx, 5Dh ; ']'
0x18003ddfc  jmp     loc_18003E046
0x18003de01  mov     rdx, r14
0x18003de04  lea     rcx, [rbp+var_30]
0x18003de08  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003de0d  mov     rdx, rax
0x18003de10  lea     rcx, [rbp+var_38]
0x18003de14  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003de19  lea     rcx, [rbp+var_30]
0x18003de1d  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003de22  mov     rbx, [rbp+var_38]
0x18003de26  test    rbx, rbx
0x18003de29  jnz     short loc_18003DE49
0x18003de2b  mov     edi, 8007000Eh
0x18003de30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003de37  jb      loc_18003E064
0x18003de3d  lea     edx, [rbx+5Eh]
0x18003de40  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x18003de44  jmp     loc_18003E04A
0x18003de49  mov     r8, r14; Size
0x18003de4c  mov     rdx, rdi; Src
0x18003de4f  mov     rcx, rbx; void *
0x18003de52  call    memcpy_0
0x18003de57  lea     rcx, [rbp+ppMFAttributes]
0x18003de5b  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003de60  mov     edx, 1; cInitialSize
0x18003de65  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18003de69  call    cs:__imp_MFCreateAttributes
0x18003de6f  xor     r15d, r15d
0x18003de72  mov     edi, eax
0x18003de74  test    eax, eax
0x18003de76  jns     short loc_18003DE8E
0x18003de78  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003de7f  jb      loc_18003E064
0x18003de85  lea     edx, [r15+5Fh]
0x18003de89  jmp     loc_18003E046
0x18003de8e  mov     r12b, [rbp+arg_20]
0x18003de92  lea     r8d, [r14-28h]; cbBufSize
0x18003de96  test    r12b, r12b
0x18003de99  jnz     loc_18003E024
0x18003de9f  cmp     cs:byte_18005E5A5, 10h
0x18003dea6  lea     rax, [rbx+28h]
0x18003deaa  xorps   xmm0, xmm0
0x18003dead  mov     [rbp+pDataIn.pbData], rax
0x18003deb1  movups  xmmword ptr [rbp+var_18.cbData], xmm0
0x18003deb5  mov     dword ptr [rbp+pDataIn+4], r15d
0x18003deb9  mov     [rbp+pDataIn.cbData], r8d
0x18003debd  jb      loc_18003DF5E
0x18003dec3  lea     rdx, [rbp+var_30]
0x18003dec7  mov     [rbp+var_30], r15
0x18003decb  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18003ded0  test    eax, eax
0x18003ded2  js      short loc_18003DF1A
0x18003ded4  cmp     cs:byte_18005E5A5, 8
0x18003dedb  jb      short loc_18003DF55
0x18003dedd  mov     eax, [rbp+pDataIn.cbData]
0x18003dee0  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003dee7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003deee  mov     edx, 60h ; '`'
0x18003def3  mov     dword ptr [rsp+78h+pDataOut], eax
0x18003def7  mov     r9, rsi
0x18003defa  mov     rax, [rbp+pDataIn.pbData]
0x18003defe  mov     qword ptr [rsp+78h+dwFlags], rax
0x18003df03  mov     rax, [rbp+var_30]
0x18003df07  mov     rcx, [rcx+0D8h]
0x18003df0e  mov     [rsp+78h+pPromptStruct], rax
0x18003df13  call    WPP_SF_qSqD
0x18003df18  jmp     short loc_18003DF55
0x18003df1a  cmp     cs:byte_18005E5A5, 8
0x18003df21  jb      short loc_18003DF55
0x18003df23  mov     eax, [rbp+pDataIn.cbData]
0x18003df26  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003df2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df34  mov     edx, 61h ; 'a'
0x18003df39  mov     [rsp+78h+dwFlags], eax
0x18003df3d  mov     r9, rsi
0x18003df40  mov     rax, [rbp+pDataIn.pbData]
0x18003df44  mov     [rsp+78h+pPromptStruct], rax
0x18003df49  mov     rcx, [rcx+0D8h]
0x18003df50  call    WPP_SF_qqD
0x18003df55  lea     rcx, [rbp+var_30]
0x18003df59  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003df5e  lea     rax, [rbp+var_18]
0x18003df62  xor     r9d, r9d; pvReserved
0x18003df65  mov     [rsp+78h+pDataOut], rax; pDataOut
0x18003df6a  lea     rcx, [rbp+pDataIn]; pDataIn
0x18003df6e  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x18003df73  xor     r8d, r8d; pOptionalEntropy
0x18003df76  xor     edx, edx; ppszDataDescr
0x18003df78  mov     [rsp+78h+pPromptStruct], r15; pPromptStruct
0x18003df7d  call    cs:__imp_CryptUnprotectData
0x18003df83  test    eax, eax
0x18003df85  jnz     short loc_18003DFE4
0x18003df87  call    cs:__imp_GetLastError
0x18003df8d  mov     edi, eax
0x18003df8f  test    eax, eax
0x18003df91  jle     short loc_18003DF9C
0x18003df93  movzx   edi, ax
0x18003df96  or      edi, 80070000h
0x18003df9c  test    edi, edi
0x18003df9e  jns     short loc_18003DFE4
0x18003dfa0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003dfa7  jb      short loc_18003DFCC
0x18003dfa9  mov     edx, 62h ; 'b'
0x18003dfae  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x18003dfb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfb9  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003dfc0  mov     r9, rsi
0x18003dfc3  mov     rcx, [rcx+10h]
0x18003dfc7  call    WPP_SF_qD
0x18003dfcc  mov     rcx, [rbp+var_18.pbData]; hMem
0x18003dfd0  test    rcx, rcx
0x18003dfd3  jz      loc_18003E064
0x18003dfd9  call    cs:__imp_LocalFree
0x18003dfdf  jmp     loc_18003E064
0x18003dfe4  mov     r8d, [rbp+var_18.cbData]; cbBufSize
0x18003dfe8  lea     r15, [rsi+50h]
0x18003dfec  mov     rcx, [r15]; pAttributes
0x18003dfef  mov     rdx, [rbp+var_18.pbData]; pBuf
0x18003dff3  call    cs:__imp_MFInitAttributesFromBlob
0x18003dff9  mov     edi, eax
0x18003dffb  test    eax, eax
0x18003dffd  jns     short loc_18003E013
0x18003dfff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e006  jb      short loc_18003DFCC
0x18003e008  mov     edx, 63h ; 'c'
0x18003e00d  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x18003e011  jmp     short loc_18003DFB2
0x18003e013  mov     rcx, [rbp+var_18.pbData]; hMem
0x18003e017  test    rcx, rcx
0x18003e01a  jz      short loc_18003E078
0x18003e01c  call    cs:__imp_LocalFree
0x18003e022  jmp     short loc_18003E078
0x18003e024  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x18003e028  lea     rdx, [rbx+28h]; pBuf
0x18003e02c  call    cs:__imp_MFInitAttributesFromBlob
0x18003e032  mov     edi, eax
0x18003e034  test    eax, eax
0x18003e036  jns     short loc_18003E074
0x18003e038  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e03f  jb      short loc_18003E064
0x18003e041  mov     edx, 64h ; 'd'
0x18003e046  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x18003e04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e051  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e058  mov     r9, rsi
0x18003e05b  mov     rcx, [rcx+10h]
0x18003e05f  call    WPP_SF_qD
0x18003e064  cmp     cs:byte_18005E5A5, 1
0x18003e06b  jb      short loc_18003E0D3
0x18003e06d  mov     edx, 65h ; 'e'
0x18003e072  jmp     short loc_18003E0B2
0x18003e074  lea     r15, [rsi+50h]
0x18003e078  mov     rax, [rsi+40h]
0x18003e07c  lea     rcx, [rsi+38h]
0x18003e080  mov     rdx, r13
0x18003e083  mov     [rbp+var_38], rax
0x18003e087  mov     [rsi+40h], rbx
0x18003e08b  mov     [rsi+48h], r14d
0x18003e08f  mov     [rsi+58h], r12b
0x18003e093  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x18003e098  lea     rdx, [rbp+ppMFAttributes]
0x18003e09c  mov     rcx, r15
0x18003e09f  call    ??4?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy> const &)
0x18003e0a4  cmp     cs:byte_18005E5A5, 8
0x18003e0ab  jb      short loc_18003E0D3
0x18003e0ad  mov     edx, 66h ; 'f'
0x18003e0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0b9  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003e0c0  mov     r9, rsi
0x18003e0c3  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x18003e0c7  mov     rcx, [rcx+0D8h]
0x18003e0ce  call    WPP_SF_qD
0x18003e0d3  lea     rcx, [rbp+var_38]
0x18003e0d7  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003e0dc  lea     rcx, [rbp+ppMFAttributes]
0x18003e0e0  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003e0e5  mov     eax, edi
0x18003e0e7  add     rsp, 78h
0x18003e0eb  pop     r15
0x18003e0ed  pop     r14
0x18003e0ef  pop     r13
0x18003e0f1  pop     r12
0x18003e0f3  pop     rdi
0x18003e0f4  pop     rsi
0x18003e0f5  pop     rbx
0x18003e0f6  pop     rbp
0x18003e0f7  retn
```
