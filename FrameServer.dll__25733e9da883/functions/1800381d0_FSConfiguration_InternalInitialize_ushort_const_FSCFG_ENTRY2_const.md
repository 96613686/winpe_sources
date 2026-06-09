# FSConfiguration::InternalInitialize(ushort const *,FSCFG_ENTRY2 const &)

- ea: `0x1800381d0`
- end: `0x180038654`
- name: `?InternalInitialize@FSConfiguration@@MEAAJPEBGAEBUFSCFG_ENTRY2@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(FSConfiguration *this, const char *, const struct FSCFG_ENTRY2 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009f50`
- `0x18000a880`
- `0x18000a91c`
- `0x180017a3c`
- `0x18002836c`
- `0x18002b7d4`
- `0x18002bc0c`
- `0x18002db74`
- `0x1800381d0`
- `0x180039774`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003861c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003861c`
- `MFPlat!MFCreateAttributes` at `0x180038327`
- `MFPlat!MFCreateAttributes` at `0x180038327`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800384a3`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800384a3`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(
        FSConfiguration *this,
        const char *a2,
        const struct FSCFG_ENTRY2 *a3)
{
  char v3; // bl
  BlobTrace *v7; // rax
  const char *String; // rax
  int v9; // edi
  __int64 v10; // rbx
  GuidTrace *v11; // rax
  const char *v12; // rcx
  HRESULT v13; // eax
  int v14; // edi
  __int64 v15; // rdx
  DEVPROPGUID v16; // xmm0
  unsigned int v17; // edi
  __int64 unique; // rax
  unsigned __int8 *v19; // rbx
  unsigned int v20; // r15d
  struct IMFAttributesVtbl *lpVtbl; // rax
  const struct _GUID *v22; // r8
  __int64 v23; // rdx
  void *v24; // rdx
  void *v25; // rcx
  unsigned int *v27; // [rsp+28h] [rbp-81h]
  unsigned int v28; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-65h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-61h] BYREF
  void *v31; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int8 *v33; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v34[8]; // [rsp+68h] [rbp-41h] BYREF
  LPVOID *p_pv; // [rsp+70h] [rbp-39h] BYREF
  __int64 v36; // [rsp+78h] [rbp-31h] BYREF
  char v37; // [rsp+80h] [rbp-29h]
  _BYTE v38[32]; // [rsp+90h] [rbp-19h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+B0h] [rbp+7h] BYREF

  v3 = 0;
  memset(&PropertyKey, 0, sizeof(PropertyKey));
  v28 = 0;
  v33 = 0;
  pv = 0;
  v29 = 0;
  v31 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = BlobTrace::BlobTrace((BlobTrace *)&p_pv, (char *)a3 + 24, (unsigned int)a3);
    String = FSString::GetString((BlobTrace *)((char *)v7 + 8));
    v9 = *((_DWORD *)a3 + 1);
    v10 = (__int64)String;
    v11 = GuidTrace::GuidTrace((GuidTrace *)v38, (const struct _GUID *)((char *)a3 + 8));
    v27 = (unsigned int *)GuidTrace::GetString(v11);
    v12 = a2;
    if ( !a2 )
      v12 = L"<nullptr>";
    WPP_SF_qSsds(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v12, (__int64)v27, v9, v10);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)v38);
  }
  if ( (v3 & 1) != 0 )
  {
    p_pv = &FSSourceIdentityControlTrace::`vftable';
    FSString::~FSString((FSString *)&v36);
  }
  if ( !a2 )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( g_wppLevels )
    {
      v15 = 76;
LABEL_43:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v13);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v16 = *(DEVPROPGUID *)((char *)a3 + 8);
  PropertyKey.pid = *((_DWORD *)a3 + 1);
  PropertyKey.fmtid = v16;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v13 = MFCreateAttributes(&ppMFAttributes, 1u);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 77;
      goto LABEL_43;
    }
LABEL_44:
    if ( !byte_18010EC4D )
      goto LABEL_49;
    v23 = 87;
    goto LABEL_48;
  }
  v13 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, 0, 0, &v28);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 78;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v17 = v28;
  if ( v28 < 0x28 )
  {
    v13 = -2147023881;
    v14 = -2147023881;
    if ( g_wppLevels )
    {
      v15 = 79;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  unique = wil::make_unique_nothrow<unsigned char [0]>(v34, v28);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v33, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(v34);
  v19 = v33;
  if ( !v33 )
  {
    v14 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v33 + 80),
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024882);
    goto LABEL_44;
  }
  v13 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, v33, v17, &v28);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 81;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v20 = v28;
  if ( v28 < 0x28 )
  {
    v13 = -2147023881;
    v14 = -2147023881;
    if ( g_wppLevels )
    {
      v15 = 82;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  if ( memcmp_0(v19 + 8, (char *)a3 + 24, 0x20u) )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( g_wppLevels )
    {
      v15 = 83;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v13 = MFInitAttributesFromBlob(ppMFAttributes, v19 + 40, v20 - 40);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 84;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  lpVtbl = ppMFAttributes->lpVtbl;
  p_pv = &pv;
  v36 = 0;
  v37 = 1;
  v14 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64 *, unsigned int *))lpVtbl->GetAllocatedBlob)(
          ppMFAttributes,
          FSM_WSEOPTIN_CONFIGURATION_KEY_INFO,
          &v36,
          &v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v14);
    goto LABEL_44;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v31);
  v13 = FSConfigurationKey::CreateKeyFromBlob((const unsigned __int8 *)pv, v29, v22, &v31);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 86;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  v24 = v31;
  v33 = (unsigned __int8 *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v19;
  *((_DWORD *)this + 18) = v20;
  *((_BYTE *)this + 88) = 1;
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((char *)this + 56, v24);
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((char *)this + 80, ppMFAttributes);
  if ( (unsigned __int8)byte_18010EC4D < 8u )
    goto LABEL_49;
  v23 = 88;
LABEL_48:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v23, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v14);
LABEL_49:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
  v25 = pv;
  pv = 0;
  if ( v25 )
    CoTaskMemFree(v25);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v33);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800381d0  mov     [rsp-8+arg_18], rbx
0x1800381d5  push    rbp
0x1800381d6  push    rsi
0x1800381d7  push    rdi
0x1800381d8  push    r12
0x1800381da  push    r13
0x1800381dc  push    r14
0x1800381de  push    r15
0x1800381e0  lea     rbp, [rsp-27h]
0x1800381e5  sub     rsp, 0D0h
0x1800381ec  mov     rax, cs:__security_cookie
0x1800381f3  xor     rax, rsp
0x1800381f6  mov     [rbp+57h+var_38], rax
0x1800381fa  xor     r14d, r14d
0x1800381fd  xorps   xmm0, xmm0
0x180038200  mov     ebx, r14d
0x180038203  xor     eax, eax
0x180038205  mov     [rbp+57h+var_BC], ebx
0x180038208  mov     r13, r8
0x18003820b  movups  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x18003820f  mov     [rbp+57h+PropertyKey.pid], eax
0x180038212  mov     r12, rdx
0x180038215  mov     [rbp+57h+var_C0], r14d
0x180038219  mov     rsi, rcx
0x18003821c  mov     [rbp+57h+var_A0], r14
0x180038220  mov     [rbp+57h+pv], r14
0x180038224  mov     [rbp+57h+var_BC], r14d
0x180038228  mov     [rbp+57h+var_B0], r14
0x18003822c  mov     [rbp+57h+ppMFAttributes], r14
0x180038230  cmp     cs:byte_18010EC4D, 8
0x180038237  jb      short loc_1800382A9
0x180038239  lea     rdx, [r8+18h]; void *
0x18003823d  lea     rcx, [rbp+57h+var_90]; this
0x180038241  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x180038246  lea     rcx, [rax+8]; this
0x18003824a  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003824f  mov     edi, [r13+4]
0x180038253  lea     rcx, [rbp+57h+var_70]; this
0x180038257  lea     rdx, [r13+8]; struct _GUID *
0x18003825b  mov     rbx, rax
0x18003825e  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180038263  mov     rcx, rax; this
0x180038266  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18003826b  mov     [rsp+100h+var_C8], rbx; __int64
0x180038270  lea     rdx, aNullptr_0; "<nullptr>"
0x180038277  test    r12, r12
0x18003827a  mov     dword ptr [rsp+100h+var_D0], edi; char
0x18003827e  mov     [rsp+100h+var_D8], rax; __int64
0x180038283  mov     rcx, r12
0x180038286  cmovz   rcx, rdx
0x18003828a  mov     r9, rsi
0x18003828d  mov     qword ptr [rsp+100h+var_E0], rcx; __int64
0x180038292  mov     rcx, cs:WPP_GLOBAL_Control
0x180038299  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800382a0  call    WPP_SF_qSsds
0x1800382a5  lea     ebx, [r14+3]
0x1800382a9  mov     rdi, r13
0x1800382ac  test    bl, 2
0x1800382af  jz      short loc_1800382BD
0x1800382b1  and     ebx, 0FFFFFFFDh
0x1800382b4  lea     rcx, [rbp+57h+var_70]; this
0x1800382b8  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800382bd  test    bl, 1
0x1800382c0  jz      short loc_1800382D6
0x1800382c2  lea     rax, ??_7FSSourceIdentityControlTrace@@6B@; const FSSourceIdentityControlTrace::`vftable'
0x1800382c9  lea     rcx, [rbp+57h+var_88]; this
0x1800382cd  mov     [rbp+57h+var_90], rax
0x1800382d1  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800382d6  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x1800382dd  test    r12, r12
0x1800382e0  jnz     short loc_180038300
0x1800382e2  mov     eax, 80070057h
0x1800382e7  mov     edi, eax
0x1800382e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800382f0  jb      loc_180038590
0x1800382f6  lea     edx, [r12+4Ch]
0x1800382fb  jmp     loc_180038576
0x180038300  mov     eax, 8
0x180038305  lea     rcx, [rbp+57h+ppMFAttributes]
0x180038309  movups  xmm0, xmmword ptr [rdi+rax]
0x18003830d  mov     eax, [r13+4]
0x180038311  mov     [rbp+57h+PropertyKey.pid], eax
0x180038314  movdqu  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x180038319  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003831e  mov     edx, 1; cInitialSize
0x180038323  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180038327  call    cs:__imp_MFCreateAttributes
0x18003832d  mov     edi, eax
0x18003832f  test    eax, eax
0x180038331  jns     short loc_18003834A
0x180038333  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003833a  jb      loc_180038590
0x180038340  mov     edx, 4Dh ; 'M'
0x180038345  jmp     loc_180038576
0x18003834a  lea     rax, [rbp+57h+var_C0]
0x18003834e  mov     r15d, 1003h
0x180038354  mov     [rsp+100h+var_D8], rax; unsigned int *
0x180038359  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x18003835d  mov     r8d, r15d; unsigned int
0x180038360  mov     [rsp+100h+var_E0], 0; unsigned int
0x180038368  xor     r9d, r9d; unsigned __int8 *
0x18003836b  mov     rcx, r12; pszDeviceInterface
0x18003836e  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x180038373  mov     edi, eax
0x180038375  test    eax, eax
0x180038377  jns     short loc_180038390
0x180038379  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038380  jb      loc_180038590
0x180038386  mov     edx, 4Eh ; 'N'
0x18003838b  jmp     loc_180038576
0x180038390  mov     edi, [rbp+57h+var_C0]
0x180038393  cmp     edi, 28h ; '('
0x180038396  jnb     short loc_1800383B6
0x180038398  mov     eax, 800703F7h
0x18003839d  mov     edi, eax
0x18003839f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800383a6  jb      loc_180038590
0x1800383ac  mov     edx, 4Fh ; 'O'
0x1800383b1  jmp     loc_180038576
0x1800383b6  mov     rdx, rdi
0x1800383b9  lea     rcx, [rbp+57h+var_98]
0x1800383bd  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800383c2  mov     rdx, rax
0x1800383c5  lea     rcx, [rbp+57h+var_A0]
0x1800383c9  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x1800383ce  lea     rcx, [rbp+57h+var_98]
0x1800383d2  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800383d7  mov     rbx, [rbp+57h+var_A0]
0x1800383db  test    rbx, rbx
0x1800383de  jnz     short loc_1800383FE
0x1800383e0  mov     edi, 8007000Eh
0x1800383e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800383ec  jb      loc_180038590
0x1800383f2  lea     edx, [rbx+50h]
0x1800383f5  mov     [rsp+100h+var_E0], edi
0x1800383f9  jmp     loc_18003857A
0x1800383fe  lea     rax, [rbp+57h+var_C0]
0x180038402  mov     r9, rbx; unsigned __int8 *
0x180038405  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18003840a  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x18003840e  mov     r8d, r15d; unsigned int
0x180038411  mov     [rsp+100h+var_E0], edi; unsigned int
0x180038415  mov     rcx, r12; pszDeviceInterface
0x180038418  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x18003841d  mov     edi, eax
0x18003841f  test    eax, eax
0x180038421  jns     short loc_18003843A
0x180038423  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003842a  jb      loc_180038590
0x180038430  mov     edx, 51h ; 'Q'
0x180038435  jmp     loc_180038576
0x18003843a  mov     r15d, [rbp+57h+var_C0]
0x18003843e  cmp     r15d, 28h ; '('
0x180038442  jnb     short loc_180038462
0x180038444  mov     eax, 800703F7h
0x180038449  mov     edi, eax
0x18003844b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038452  jb      loc_180038590
0x180038458  mov     edx, 52h ; 'R'
0x18003845d  jmp     loc_180038576
0x180038462  lea     rdx, [r13+18h]; Buf2
0x180038466  mov     r8d, 20h ; ' '; Size
0x18003846c  lea     rcx, [rbx+8]; Buf1
0x180038470  call    memcmp_0
0x180038475  test    eax, eax
0x180038477  jz      short loc_180038497
0x180038479  mov     eax, 80070057h
0x18003847e  mov     edi, eax
0x180038480  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038487  jb      loc_180038590
0x18003848d  mov     edx, 53h ; 'S'
0x180038492  jmp     loc_180038576
0x180038497  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x18003849b  lea     r8d, [r15-28h]; cbBufSize
0x18003849f  lea     rdx, [rbx+28h]; pBuf
0x1800384a3  call    cs:__imp_MFInitAttributesFromBlob
0x1800384a9  mov     edi, eax
0x1800384ab  test    eax, eax
0x1800384ad  jns     short loc_1800384C6
0x1800384af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800384b6  jb      loc_180038590
0x1800384bc  mov     edx, 54h ; 'T'
0x1800384c1  jmp     loc_180038576
0x1800384c6  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800384ca  lea     rdx, [rbp+57h+pv]
0x1800384ce  lea     r9, [rbp+57h+var_BC]
0x1800384d2  lea     r8, [rbp+57h+var_88]
0x1800384d6  mov     rax, [rcx]
0x1800384d9  mov     [rbp+57h+var_90], rdx
0x1800384dd  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_KEY_INFO
0x1800384e4  mov     [rbp+57h+var_88], 0
0x1800384ec  mov     [rbp+57h+var_80], 1
0x1800384f0  mov     rax, [rax+80h]
0x1800384f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384fc  lea     rcx, [rbp+57h+var_90]
0x180038500  mov     edi, eax
0x180038502  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180038507  mov     eax, edi
0x180038509  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180038510  shr     eax, 1Fh
0x180038513  test    al, al
0x180038515  jz      short loc_180038549
0x180038517  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003851e  jb      short loc_18003853F
0x180038520  mov     rcx, cs:WPP_GLOBAL_Control
0x180038527  mov     edx, 55h ; 'U'
0x18003852c  mov     r9, rsi
0x18003852f  mov     [rsp+100h+var_E0], edi
0x180038533  mov     r8, r14
0x180038536  mov     rcx, [rcx+10h]
0x18003853a  call    WPP_SF_qD
0x18003853f  test    edi, edi
0x180038541  jns     loc_1800385CE
0x180038547  jmp     short loc_180038590
0x180038549  lea     rcx, [rbp+57h+var_B0]
0x18003854d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180038552  mov     edx, [rbp+57h+var_BC]; unsigned int
0x180038555  lea     r9, [rbp+57h+var_B0]; void **
0x180038559  mov     rcx, [rbp+57h+pv]; unsigned __int8 *
0x18003855d  call    ?CreateKeyFromBlob@FSConfigurationKey@@SAJPEBEKAEBU_GUID@@PEAPEAX@Z; FSConfigurationKey::CreateKeyFromBlob(uchar const *,ulong,_GUID const &,void * *)
0x180038562  mov     edi, eax
0x180038564  test    eax, eax
0x180038566  jns     short loc_1800385A0
0x180038568  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003856f  jb      short loc_180038590
0x180038571  mov     edx, 56h ; 'V'
0x180038576  mov     [rsp+100h+var_E0], eax
0x18003857a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038581  mov     r9, rsi
0x180038584  mov     r8, r14
0x180038587  mov     rcx, [rcx+10h]
0x18003858b  call    WPP_SF_qD
0x180038590  cmp     cs:byte_18010EC4D, 1
0x180038597  jb      short loc_1800385F9
0x180038599  mov     edx, 57h ; 'W'
0x18003859e  jmp     short loc_1800385DC
0x1800385a0  mov     rax, [rsi+40h]
0x1800385a4  lea     rcx, [rsi+38h]
0x1800385a8  mov     rdx, [rbp+57h+var_B0]
0x1800385ac  mov     [rbp+57h+var_A0], rax
0x1800385b0  mov     [rsi+40h], rbx
0x1800385b4  mov     [rsi+48h], r15d
0x1800385b8  mov     byte ptr [rsi+58h], 1
0x1800385bc  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800385c1  mov     rdx, [rbp+57h+ppMFAttributes]
0x1800385c5  lea     rcx, [rsi+50h]
0x1800385c9  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800385ce  cmp     cs:byte_18010EC4D, 8
0x1800385d5  jb      short loc_1800385F9
0x1800385d7  mov     edx, 58h ; 'X'
0x1800385dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385e3  mov     r9, rsi
0x1800385e6  mov     r8, r14
0x1800385e9  mov     [rsp+100h+var_E0], edi
0x1800385ed  mov     rcx, [rcx+0D8h]
0x1800385f4  call    WPP_SF_qD
0x1800385f9  lea     rcx, [rbp+57h+ppMFAttributes]; void *
0x1800385fd  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180038602  lea     rcx, [rbp+57h+var_B0]; void *
0x180038606  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003860b  mov     rcx, [rbp+57h+pv]; pv
0x18003860f  mov     [rbp+57h+pv], 0
0x180038617  test    rcx, rcx
0x18003861a  jz      short loc_180038622
0x18003861c  call    cs:__imp_CoTaskMemFree
0x180038622  lea     rcx, [rbp+57h+var_A0]
0x180038626  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18003862b  mov     eax, edi
0x18003862d  mov     rcx, [rbp+57h+var_38]
0x180038631  xor     rcx, rsp; StackCookie
0x180038634  call    __security_check_cookie
0x180038639  mov     rbx, [rsp+100h+arg_18]
0x180038641  add     rsp, 0D0h
0x180038648  pop     r15
0x18003864a  pop     r14
0x18003864c  pop     r13
0x18003864e  pop     r12
0x180038650  pop     rdi
0x180038651  pop     rsi
0x180038652  pop     rbp
0x180038653  retn
```
