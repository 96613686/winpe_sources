# FSConfiguration::InternalInitializeGlobalConfiguration(IFSConfigurationKey *,uchar const *,ulong,bool)

- ea: `0x180074d40`
- end: `0x180075121`
- name: `?InternalInitializeGlobalConfiguration@FSConfiguration@@MEAAJPEAUIFSConfigurationKey@@PEBEK_N@Z`
- size: `993`
- prototype: `int(FSConfiguration *__hidden this, struct IFSConfigurationKey *, const unsigned __int8 *, unsigned int, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c2ec`
- `0x18000f5a0`
- `0x180010218`
- `0x1800133fc`
- `0x180028d34`
- `0x180028eb4`
- `0x18002b778`
- `0x1800359cc`
- `0x180060d50`
- `0x180074d40`
- `0x180075bd0`
- `0x180076280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074fb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075045`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075045`
- `CRYPT32!CryptUnprotectData` at `0x180074fa6`
- `CRYPT32!CryptUnprotectData` at `0x180074fa6`
- `MFPlat!MFCreateAttributes` at `0x180074e99`
- `MFPlat!MFCreateAttributes` at `0x180074e99`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007501c`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075055`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007501c`
- `MFPlat!MFInitAttributesFromBlob` at `0x180075055`

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
  void **unique; // rax
  const UINT8 *v13; // rbx
  __int64 v14; // rcx
  bool v15; // r12
  int v16; // r8d
  signed int LastError; // eax
  __int64 *v18; // r15
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
  if ( (unsigned __int8)byte_18008D62D >= 8u )
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
  unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v23, v5);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(&v22, unique);
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
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
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
    v18 = (__int64 *)((char *)this + 80);
  }
  else
  {
    pDataIn.pbData = (BYTE *)(v13 + 40);
    pDataOut = 0;
    *(&pDataIn.cbData + 1) = 0;
    pDataIn.cbData = v5 - 40;
    if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    {
      v23 = 0;
      if ( (int)FSGetUserSidString(v14, (LPWSTR *)&v23) < 0 )
      {
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            97,
            &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
            this,
            pDataIn.pbData,
            pDataIn.cbData);
      }
      else if ( (unsigned __int8)byte_18008D62D >= 8u )
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
        if ( byte_18008D62D )
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
    v18 = (__int64 *)((char *)this + 80);
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
  wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=((__int64 *)this + 7, (__int64)a2);
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(
    v18,
    (__int64 *)&ppMFAttributes);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v20 = 102;
    goto LABEL_51;
  }
LABEL_52:
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v22);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180074d40  push    rbp
0x180074d42  push    rbx
0x180074d43  push    rsi
0x180074d44  push    rdi
0x180074d45  push    r12
0x180074d47  push    r13
0x180074d49  push    r14
0x180074d4b  push    r15
0x180074d4d  mov     rbp, rsp
0x180074d50  sub     rsp, 78h
0x180074d54  mov     r14d, r9d
0x180074d57  mov     rdi, r8
0x180074d5a  mov     r13, rdx
0x180074d5d  mov     [rbp+ppMFAttributes], 0
0x180074d65  mov     rsi, rcx
0x180074d68  mov     [rbp+var_38], 0
0x180074d70  cmp     cs:byte_18008D62D, 8
0x180074d77  jb      short loc_180074DA5
0x180074d79  mov     r9, rcx
0x180074d7c  mov     [rsp+78h+dwFlags], r14d
0x180074d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d88  mov     edx, 59h ; 'Y'
0x180074d8d  mov     [rsp+78h+pPromptStruct], r8
0x180074d92  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074d99  mov     rcx, [rcx+0D8h]
0x180074da0  call    WPP_SF_qqD
0x180074da5  test    rdi, rdi
0x180074da8  jnz     short loc_180074DC8
0x180074daa  mov     eax, 80070057h
0x180074daf  mov     edi, eax
0x180074db1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074db8  jb      loc_18007508D
0x180074dbe  mov     edx, 5Ah ; 'Z'
0x180074dc3  jmp     loc_18007506F
0x180074dc8  test    r13, r13
0x180074dcb  jnz     short loc_180074DEA
0x180074dcd  mov     eax, 80070057h
0x180074dd2  mov     edi, eax
0x180074dd4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074ddb  jb      loc_18007508D
0x180074de1  lea     edx, [r13+5Bh]
0x180074de5  jmp     loc_18007506F
0x180074dea  cmp     r14d, 28h ; '('
0x180074dee  jnb     short loc_180074E0E
0x180074df0  mov     eax, 800703F7h
0x180074df5  mov     edi, eax
0x180074df7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074dfe  jb      loc_18007508D
0x180074e04  mov     edx, 5Ch ; '\'
0x180074e09  jmp     loc_18007506F
0x180074e0e  cmp     [rdi], r14d
0x180074e11  jbe     short loc_180074E31
0x180074e13  mov     eax, 800703F7h
0x180074e18  mov     edi, eax
0x180074e1a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074e21  jb      loc_18007508D
0x180074e27  mov     edx, 5Dh ; ']'
0x180074e2c  jmp     loc_18007506F
0x180074e31  mov     rdx, r14
0x180074e34  lea     rcx, [rbp+var_30]
0x180074e38  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180074e3d  mov     rdx, rax
0x180074e40  lea     rcx, [rbp+var_38]
0x180074e44  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180074e49  lea     rcx, [rbp+var_30]
0x180074e4d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180074e52  mov     rbx, [rbp+var_38]
0x180074e56  test    rbx, rbx
0x180074e59  jnz     short loc_180074E79
0x180074e5b  mov     edi, 8007000Eh
0x180074e60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074e67  jb      loc_18007508D
0x180074e6d  lea     edx, [rbx+5Eh]
0x180074e70  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x180074e74  jmp     loc_180075073
0x180074e79  mov     r8, r14; Size
0x180074e7c  mov     rdx, rdi; Src
0x180074e7f  mov     rcx, rbx; void *
0x180074e82  call    memcpy_0
0x180074e87  lea     rcx, [rbp+ppMFAttributes]
0x180074e8b  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180074e90  mov     edx, 1; cInitialSize
0x180074e95  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180074e99  call    cs:__imp_MFCreateAttributes
0x180074e9f  xor     r15d, r15d
0x180074ea2  mov     edi, eax
0x180074ea4  test    eax, eax
0x180074ea6  jns     short loc_180074EBE
0x180074ea8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074eaf  jb      loc_18007508D
0x180074eb5  lea     edx, [r15+5Fh]
0x180074eb9  jmp     loc_18007506F
0x180074ebe  mov     r12b, [rbp+arg_20]
0x180074ec2  lea     r8d, [r14-28h]; cbBufSize
0x180074ec6  test    r12b, r12b
0x180074ec9  jnz     loc_18007504D
0x180074ecf  cmp     cs:byte_18008D62D, 10h
0x180074ed6  lea     rax, [rbx+28h]
0x180074eda  xorps   xmm0, xmm0
0x180074edd  mov     [rbp+pDataIn.pbData], rax
0x180074ee1  movups  xmmword ptr [rbp+var_18.cbData], xmm0
0x180074ee5  mov     dword ptr [rbp+pDataIn+4], r15d
0x180074ee9  mov     [rbp+pDataIn.cbData], r8d
0x180074eed  jb      loc_180074F87
0x180074ef3  lea     rdx, [rbp+var_30]
0x180074ef7  mov     [rbp+var_30], r15
0x180074efb  call    ?FSGetUserSidString@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; FSGetUserSidString(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180074f00  test    eax, eax
0x180074f02  js      short loc_180074F43
0x180074f04  cmp     cs:byte_18008D62D, 8
0x180074f0b  jb      short loc_180074F7E
0x180074f0d  mov     eax, [rbp+pDataIn.cbData]
0x180074f10  mov     edx, 60h ; '`'
0x180074f15  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f1c  mov     r9, rsi
0x180074f1f  mov     dword ptr [rsp+78h+pDataOut], eax
0x180074f23  mov     rax, [rbp+pDataIn.pbData]
0x180074f27  mov     qword ptr [rsp+78h+dwFlags], rax
0x180074f2c  mov     rax, [rbp+var_30]
0x180074f30  mov     rcx, [rcx+0D8h]
0x180074f37  mov     [rsp+78h+pPromptStruct], rax
0x180074f3c  call    WPP_SF_qSqD
0x180074f41  jmp     short loc_180074F7E
0x180074f43  cmp     cs:byte_18008D62D, 8
0x180074f4a  jb      short loc_180074F7E
0x180074f4c  mov     eax, [rbp+pDataIn.cbData]
0x180074f4f  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f5d  mov     edx, 61h ; 'a'
0x180074f62  mov     [rsp+78h+dwFlags], eax
0x180074f66  mov     r9, rsi
0x180074f69  mov     rax, [rbp+pDataIn.pbData]
0x180074f6d  mov     [rsp+78h+pPromptStruct], rax
0x180074f72  mov     rcx, [rcx+0D8h]
0x180074f79  call    WPP_SF_qqD
0x180074f7e  lea     rcx, [rbp+var_30]
0x180074f82  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180074f87  lea     rax, [rbp+var_18]
0x180074f8b  xor     r9d, r9d; pvReserved
0x180074f8e  mov     [rsp+78h+pDataOut], rax; pDataOut
0x180074f93  lea     rcx, [rbp+pDataIn]; pDataIn
0x180074f97  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x180074f9c  xor     r8d, r8d; pOptionalEntropy
0x180074f9f  xor     edx, edx; ppszDataDescr
0x180074fa1  mov     [rsp+78h+pPromptStruct], r15; pPromptStruct
0x180074fa6  call    cs:__imp_CryptUnprotectData
0x180074fac  test    eax, eax
0x180074fae  jnz     short loc_18007500D
0x180074fb0  call    cs:__imp_GetLastError
0x180074fb6  mov     edi, eax
0x180074fb8  test    eax, eax
0x180074fba  jle     short loc_180074FC5
0x180074fbc  movzx   edi, ax
0x180074fbf  or      edi, 80070000h
0x180074fc5  test    edi, edi
0x180074fc7  jns     short loc_18007500D
0x180074fc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180074fd0  jb      short loc_180074FF5
0x180074fd2  mov     edx, 62h ; 'b'
0x180074fd7  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x180074fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074fe2  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180074fe9  mov     r9, rsi
0x180074fec  mov     rcx, [rcx+10h]
0x180074ff0  call    WPP_SF_qD
0x180074ff5  mov     rcx, [rbp+var_18.pbData]; hMem
0x180074ff9  test    rcx, rcx
0x180074ffc  jz      loc_18007508D
0x180075002  call    cs:__imp_LocalFree
0x180075008  jmp     loc_18007508D
0x18007500d  mov     r8d, [rbp+var_18.cbData]; cbBufSize
0x180075011  lea     r15, [rsi+50h]
0x180075015  mov     rcx, [r15]; pAttributes
0x180075018  mov     rdx, [rbp+var_18.pbData]; pBuf
0x18007501c  call    cs:__imp_MFInitAttributesFromBlob
0x180075022  mov     edi, eax
0x180075024  test    eax, eax
0x180075026  jns     short loc_18007503C
0x180075028  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007502f  jb      short loc_180074FF5
0x180075031  mov     edx, 63h ; 'c'
0x180075036  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x18007503a  jmp     short loc_180074FDB
0x18007503c  mov     rcx, [rbp+var_18.pbData]; hMem
0x180075040  test    rcx, rcx
0x180075043  jz      short loc_1800750A1
0x180075045  call    cs:__imp_LocalFree
0x18007504b  jmp     short loc_1800750A1
0x18007504d  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x180075051  lea     rdx, [rbx+28h]; pBuf
0x180075055  call    cs:__imp_MFInitAttributesFromBlob
0x18007505b  mov     edi, eax
0x18007505d  test    eax, eax
0x18007505f  jns     short loc_18007509D
0x180075061  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075068  jb      short loc_18007508D
0x18007506a  mov     edx, 64h ; 'd'
0x18007506f  mov     dword ptr [rsp+78h+pPromptStruct], eax
0x180075073  mov     rcx, cs:WPP_GLOBAL_Control
0x18007507a  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180075081  mov     r9, rsi
0x180075084  mov     rcx, [rcx+10h]
0x180075088  call    WPP_SF_qD
0x18007508d  cmp     cs:byte_18008D62D, 1
0x180075094  jb      short loc_1800750FC
0x180075096  mov     edx, 65h ; 'e'
0x18007509b  jmp     short loc_1800750DB
0x18007509d  lea     r15, [rsi+50h]
0x1800750a1  mov     rax, [rsi+40h]
0x1800750a5  lea     rcx, [rsi+38h]
0x1800750a9  mov     rdx, r13
0x1800750ac  mov     [rbp+var_38], rax
0x1800750b0  mov     [rsi+40h], rbx
0x1800750b4  mov     [rsi+48h], r14d
0x1800750b8  mov     [rsi+58h], r12b
0x1800750bc  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x1800750c1  lea     rdx, [rbp+ppMFAttributes]
0x1800750c5  mov     rcx, r15
0x1800750c8  call    ??4?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy> const &)
0x1800750cd  cmp     cs:byte_18008D62D, 8
0x1800750d4  jb      short loc_1800750FC
0x1800750d6  mov     edx, 66h ; 'f'
0x1800750db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800750e2  lea     r8, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800750e9  mov     r9, rsi
0x1800750ec  mov     dword ptr [rsp+78h+pPromptStruct], edi
0x1800750f0  mov     rcx, [rcx+0D8h]
0x1800750f7  call    WPP_SF_qD
0x1800750fc  lea     rcx, [rbp+var_38]
0x180075100  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180075105  lea     rcx, [rbp+ppMFAttributes]
0x180075109  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18007510e  mov     eax, edi
0x180075110  add     rsp, 78h
0x180075114  pop     r15
0x180075116  pop     r14
0x180075118  pop     r13
0x18007511a  pop     r12
0x18007511c  pop     rdi
0x18007511d  pop     rsi
0x18007511e  pop     rbx
0x18007511f  pop     rbp
0x180075120  retn
```
