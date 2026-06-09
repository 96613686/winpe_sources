# FSConfiguration::InternalInitialize(ushort const *,FSCFG_ENTRY2 const &)

- ea: `0x1800444f0`
- end: `0x18004499e`
- name: `?InternalInitialize@FSConfiguration@@MEAAJPEBGAEBUFSCFG_ENTRY2@@@Z`
- size: `1198`
- prototype: `int(FSConfiguration *__hidden this, const unsigned __int16 *, const struct FSCFG_ENTRY2 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000f5a0`
- `0x1800133fc`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x180028d34`
- `0x180028eb4`
- `0x1800329bc`
- `0x1800359cc`
- `0x180036258`
- `0x180037220`
- `0x18003ccec`
- `0x1800444f0`
- `0x1800449a4`
- `0x180044f30`
- `0x180060d50`
- `0x180072974`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044966`
- `MFPlat!MFCreateAttributes` at `0x18004465c`
- `MFPlat!MFCreateAttributes` at `0x18004465c`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800447d8`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800447d8`

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
  GuidTrace *v11; // rcx
  const char *v12; // rax
  const char *v13; // rcx
  HRESULT v14; // eax
  int v15; // edi
  __int64 v16; // rdx
  DEVPROPGUID v17; // xmm0
  unsigned int v18; // edi
  void **unique; // rax
  unsigned __int8 *v20; // rbx
  unsigned int v21; // r15d
  struct IMFAttributesVtbl *lpVtbl; // rax
  const struct _GUID *v23; // r8
  void *v24; // rcx
  __int64 v25; // rdx
  void *v26; // rdx
  void *v27; // rcx
  unsigned int v29; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-65h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-61h] BYREF
  void *v32; // [rsp+50h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int8 *v34; // [rsp+60h] [rbp-49h] BYREF
  __int64 v35; // [rsp+68h] [rbp-41h] BYREF
  LPVOID *p_pv; // [rsp+70h] [rbp-39h] BYREF
  __int64 v37; // [rsp+78h] [rbp-31h] BYREF
  char v38; // [rsp+80h] [rbp-29h]
  _BYTE v39[32]; // [rsp+90h] [rbp-19h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+B0h] [rbp+7h] BYREF

  v3 = 0;
  memset(&PropertyKey, 0, sizeof(PropertyKey));
  v29 = 0;
  v34 = 0;
  pv = 0;
  v30 = 0;
  v32 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v7 = BlobTrace::BlobTrace((BlobTrace *)&p_pv, (char *)a3 + 24, 0x20u);
    String = FSString::GetString((BlobTrace *)((char *)v7 + 8));
    v9 = *((_DWORD *)a3 + 1);
    v10 = (__int64)String;
    v11 = GuidTrace::GuidTrace((GuidTrace *)v39, (const struct _GUID *)((char *)a3 + 8));
    v12 = (const char *)*((_QWORD *)v11 + 3);
    if ( !v12 )
      v12 = FSString::GetString(v11);
    v13 = a2;
    if ( !a2 )
      v13 = L"<nullptr>";
    WPP_SF_qSsds(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v13, (__int64)v12, v9, v10);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)v39);
  }
  if ( (v3 & 1) != 0 )
  {
    p_pv = &BlobTrace::`vftable';
    FSString::~FSString((FSString *)&v37);
  }
  if ( !a2 )
  {
    v14 = -2147024809;
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 76;
LABEL_47:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v14);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  v17 = *(DEVPROPGUID *)((char *)a3 + 8);
  PropertyKey.pid = *((_DWORD *)a3 + 1);
  PropertyKey.fmtid = v17;
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v14 = MFCreateAttributes(&ppMFAttributes, 1u);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 77;
      goto LABEL_47;
    }
LABEL_48:
    if ( !byte_18008D62D )
      goto LABEL_53;
    v25 = 87;
    goto LABEL_52;
  }
  v14 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, 0, 0, &v29);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 78;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v18 = v29;
  if ( v29 < 0x28 )
  {
    v14 = -2147023881;
    v15 = -2147023881;
    if ( g_wppLevels )
    {
      v16 = 79;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v35, v29);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v34, unique);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v35);
  v20 = v34;
  if ( !v34 )
  {
    v15 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v34 + 80),
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024882);
    goto LABEL_48;
  }
  v14 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, v34, v18, &v29);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 81;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v21 = v29;
  if ( v29 < 0x28 )
  {
    v14 = -2147023881;
    v15 = -2147023881;
    if ( g_wppLevels )
    {
      v16 = 82;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  if ( memcmp_0(v20 + 8, (char *)a3 + 24, 0x20u) )
  {
    v14 = -2147024809;
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 83;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v14 = MFInitAttributesFromBlob(ppMFAttributes, v20 + 40, v21 - 40);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 84;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  lpVtbl = ppMFAttributes->lpVtbl;
  p_pv = &pv;
  v37 = 0;
  v38 = 1;
  v15 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64 *, unsigned int *))lpVtbl->GetAllocatedBlob)(
          ppMFAttributes,
          FSM_WSEOPTIN_CONFIGURATION_KEY_INFO,
          &v37,
          &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v15);
    goto LABEL_48;
  }
  v24 = v32;
  v32 = 0;
  if ( v24 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
  v14 = FSConfigurationKey::CreateKeyFromBlob((const unsigned __int8 *)pv, v30, v23, &v32);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 86;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap((char *)this + 64, &v34);
  v26 = v32;
  *((_DWORD *)this + 18) = v21;
  *((_BYTE *)this + 88) = 1;
  wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=((__int64 *)this + 7, (__int64)v26);
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(
    (__int64 *)this + 10,
    (__int64 *)&ppMFAttributes);
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_53;
  v25 = 88;
LABEL_52:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v25, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v15);
LABEL_53:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v32);
  v27 = pv;
  pv = 0;
  if ( v27 )
    CoTaskMemFree(v27);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v34);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800444f0  mov     [rsp-8+arg_18], rbx
0x1800444f5  push    rbp
0x1800444f6  push    rsi
0x1800444f7  push    rdi
0x1800444f8  push    r12
0x1800444fa  push    r13
0x1800444fc  push    r14
0x1800444fe  push    r15
0x180044500  lea     rbp, [rsp-27h]
0x180044505  sub     rsp, 0D0h
0x18004450c  mov     rax, cs:__security_cookie
0x180044513  xor     rax, rsp
0x180044516  mov     [rbp+57h+var_38], rax
0x18004451a  xor     r14d, r14d
0x18004451d  xorps   xmm0, xmm0
0x180044520  mov     ebx, r14d
0x180044523  xor     eax, eax
0x180044525  mov     [rbp+57h+var_BC], ebx
0x180044528  mov     r13, r8
0x18004452b  movups  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x18004452f  mov     [rbp+57h+PropertyKey.pid], eax
0x180044532  mov     r15, rdx
0x180044535  mov     [rbp+57h+var_C0], r14d
0x180044539  mov     rsi, rcx
0x18004453c  mov     [rbp+57h+var_A0], r14
0x180044540  mov     [rbp+57h+pv], r14
0x180044544  mov     [rbp+57h+var_BC], r14d
0x180044548  mov     [rbp+57h+var_B0], r14
0x18004454c  mov     [rbp+57h+ppMFAttributes], r14
0x180044550  lea     r12d, [r14+8]
0x180044554  cmp     cs:byte_18008D62D, r12b
0x18004455b  jb      short loc_1800445DB
0x18004455d  lea     rdx, [r8+18h]; void *
0x180044561  lea     r8d, [r14+20h]; unsigned int
0x180044565  lea     rcx, [rbp+57h+var_90]; this
0x180044569  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x18004456e  lea     rcx, [rax+8]; this
0x180044572  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180044577  mov     edi, [r13+4]
0x18004457b  lea     rcx, [rbp+57h+var_70]; this
0x18004457f  lea     rdx, [r13+8]; struct _GUID *
0x180044583  mov     rbx, rax
0x180044586  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18004458b  mov     rcx, rax; this
0x18004458e  mov     rax, [rax+18h]
0x180044592  test    rax, rax
0x180044595  jnz     short loc_18004459C
0x180044597  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18004459c  mov     [rsp+100h+var_C8], rbx; __int64
0x1800445a1  lea     rdx, aNullptr; "<nullptr>"
0x1800445a8  test    r15, r15
0x1800445ab  mov     dword ptr [rsp+100h+var_D0], edi; char
0x1800445af  mov     [rsp+100h+var_D8], rax; __int64
0x1800445b4  mov     rcx, r15
0x1800445b7  cmovz   rcx, rdx
0x1800445bb  mov     r9, rsi
0x1800445be  mov     qword ptr [rsp+100h+var_E0], rcx; __int64
0x1800445c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800445ca  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800445d1  call    WPP_SF_qSsds
0x1800445d6  mov     ebx, 3
0x1800445db  mov     rdi, r13
0x1800445de  test    bl, 2
0x1800445e1  jz      short loc_1800445EF
0x1800445e3  and     ebx, 0FFFFFFFDh
0x1800445e6  lea     rcx, [rbp+57h+var_70]; this
0x1800445ea  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800445ef  test    bl, 1
0x1800445f2  jz      short loc_180044608
0x1800445f4  lea     rax, ??_7BlobTrace@@6B@; const BlobTrace::`vftable'
0x1800445fb  lea     rcx, [rbp+57h+var_88]; this
0x1800445ff  mov     [rbp+57h+var_90], rax
0x180044603  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180044608  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18004460f  test    r15, r15
0x180044612  jnz     short loc_180044635
0x180044614  mov     eax, 80070057h
0x180044619  mov     edi, eax
0x18004461b  lea     r12d, [r15+1]
0x18004461f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180044626  jb      loc_1800448D9
0x18004462c  lea     edx, [r15+4Ch]
0x180044630  jmp     loc_1800448BF
0x180044635  movups  xmm0, xmmword ptr [r12+rdi]
0x18004463a  mov     eax, [r13+4]
0x18004463e  lea     rcx, [rbp+57h+ppMFAttributes]
0x180044642  mov     [rbp+57h+PropertyKey.pid], eax
0x180044645  movdqu  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x18004464a  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18004464f  mov     r12d, 1
0x180044655  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180044659  mov     edx, r12d; cInitialSize
0x18004465c  call    cs:__imp_MFCreateAttributes
0x180044662  mov     edi, eax
0x180044664  test    eax, eax
0x180044666  jns     short loc_18004467F
0x180044668  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18004466f  jb      loc_1800448D9
0x180044675  lea     edx, [r12+4Ch]
0x18004467a  jmp     loc_1800448BF
0x18004467f  lea     rax, [rbp+57h+var_C0]
0x180044683  xor     r9d, r9d; unsigned __int8 *
0x180044686  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18004468b  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x18004468f  mov     r8d, 1003h; unsigned int
0x180044695  mov     [rsp+100h+var_E0], 0; unsigned int
0x18004469d  mov     rcx, r15; pszDeviceInterface
0x1800446a0  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x1800446a5  mov     edi, eax
0x1800446a7  test    eax, eax
0x1800446a9  jns     short loc_1800446C2
0x1800446ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800446b2  jb      loc_1800448D9
0x1800446b8  mov     edx, 4Eh ; 'N'
0x1800446bd  jmp     loc_1800448BF
0x1800446c2  mov     edi, [rbp+57h+var_C0]
0x1800446c5  cmp     edi, 28h ; '('
0x1800446c8  jnb     short loc_1800446E8
0x1800446ca  mov     eax, 800703F7h
0x1800446cf  mov     edi, eax
0x1800446d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800446d8  jb      loc_1800448D9
0x1800446de  mov     edx, 4Fh ; 'O'
0x1800446e3  jmp     loc_1800448BF
0x1800446e8  mov     rdx, rdi
0x1800446eb  lea     rcx, [rbp+57h+var_98]
0x1800446ef  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800446f4  mov     rdx, rax
0x1800446f7  lea     rcx, [rbp+57h+var_A0]
0x1800446fb  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x180044700  lea     rcx, [rbp+57h+var_98]
0x180044704  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180044709  mov     rbx, [rbp+57h+var_A0]
0x18004470d  test    rbx, rbx
0x180044710  jnz     short loc_180044730
0x180044712  mov     edi, 8007000Eh
0x180044717  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18004471e  jb      loc_1800448D9
0x180044724  lea     edx, [rbx+50h]
0x180044727  mov     [rsp+100h+var_E0], edi
0x18004472b  jmp     loc_1800448C3
0x180044730  lea     rax, [rbp+57h+var_C0]
0x180044734  mov     r9, rbx; unsigned __int8 *
0x180044737  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18004473c  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x180044740  mov     r8d, 1003h; unsigned int
0x180044746  mov     [rsp+100h+var_E0], edi; unsigned int
0x18004474a  mov     rcx, r15; pszDeviceInterface
0x18004474d  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x180044752  mov     edi, eax
0x180044754  test    eax, eax
0x180044756  jns     short loc_18004476F
0x180044758  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18004475f  jb      loc_1800448D9
0x180044765  mov     edx, 51h ; 'Q'
0x18004476a  jmp     loc_1800448BF
0x18004476f  mov     r15d, [rbp+57h+var_C0]
0x180044773  cmp     r15d, 28h ; '('
0x180044777  jnb     short loc_180044797
0x180044779  mov     eax, 800703F7h
0x18004477e  mov     edi, eax
0x180044780  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180044787  jb      loc_1800448D9
0x18004478d  mov     edx, 52h ; 'R'
0x180044792  jmp     loc_1800448BF
0x180044797  lea     rdx, [r13+18h]; Buf2
0x18004479b  mov     r8d, 20h ; ' '; Size
0x1800447a1  lea     rcx, [rbx+8]; Buf1
0x1800447a5  call    memcmp_0
0x1800447aa  test    eax, eax
0x1800447ac  jz      short loc_1800447CC
0x1800447ae  mov     eax, 80070057h
0x1800447b3  mov     edi, eax
0x1800447b5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800447bc  jb      loc_1800448D9
0x1800447c2  mov     edx, 53h ; 'S'
0x1800447c7  jmp     loc_1800448BF
0x1800447cc  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x1800447d0  lea     r8d, [r15-28h]; cbBufSize
0x1800447d4  lea     rdx, [rbx+28h]; pBuf
0x1800447d8  call    cs:__imp_MFInitAttributesFromBlob
0x1800447de  mov     edi, eax
0x1800447e0  test    eax, eax
0x1800447e2  jns     short loc_1800447FB
0x1800447e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800447eb  jb      loc_1800448D9
0x1800447f1  mov     edx, 54h ; 'T'
0x1800447f6  jmp     loc_1800448BF
0x1800447fb  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800447ff  lea     rdx, [rbp+57h+pv]
0x180044803  lea     r9, [rbp+57h+var_BC]
0x180044807  lea     r8, [rbp+57h+var_88]
0x18004480b  mov     rax, [rcx]
0x18004480e  mov     [rbp+57h+var_90], rdx
0x180044812  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_KEY_INFO
0x180044819  mov     [rbp+57h+var_88], 0
0x180044821  mov     [rbp+57h+var_80], r12b
0x180044825  mov     rax, [rax+80h]
0x18004482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044831  lea     rcx, [rbp+57h+var_90]
0x180044835  mov     edi, eax
0x180044837  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004483c  mov     eax, edi
0x18004483e  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x180044845  shr     eax, 1Fh
0x180044848  test    al, al
0x18004484a  jz      short loc_18004487E
0x18004484c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180044853  jb      short loc_180044874
0x180044855  mov     rcx, cs:WPP_GLOBAL_Control
0x18004485c  mov     edx, 55h ; 'U'
0x180044861  mov     r9, rsi
0x180044864  mov     [rsp+100h+var_E0], edi
0x180044868  mov     r8, r14
0x18004486b  mov     rcx, [rcx+10h]
0x18004486f  call    WPP_SF_qD
0x180044874  test    edi, edi
0x180044876  jns     loc_180044918
0x18004487c  jmp     short loc_1800448D9
0x18004487e  mov     rcx, [rbp+57h+var_B0]
0x180044882  mov     [rbp+57h+var_B0], 0
0x18004488a  test    rcx, rcx
0x18004488d  jz      short loc_18004489B
0x18004488f  mov     rax, [rcx]
0x180044892  mov     rax, [rax+10h]
0x180044896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004489b  mov     edx, [rbp+57h+var_BC]; unsigned int
0x18004489e  lea     r9, [rbp+57h+var_B0]; void **
0x1800448a2  mov     rcx, [rbp+57h+pv]; unsigned __int8 *
0x1800448a6  call    ?CreateKeyFromBlob@FSConfigurationKey@@SAJPEBEKAEBU_GUID@@PEAPEAX@Z; FSConfigurationKey::CreateKeyFromBlob(uchar const *,ulong,_GUID const &,void * *)
0x1800448ab  mov     edi, eax
0x1800448ad  test    eax, eax
0x1800448af  jns     short loc_1800448E9
0x1800448b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800448b8  jb      short loc_1800448D9
0x1800448ba  mov     edx, 56h ; 'V'
0x1800448bf  mov     [rsp+100h+var_E0], eax
0x1800448c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800448ca  mov     r9, rsi
0x1800448cd  mov     r8, r14
0x1800448d0  mov     rcx, [rcx+10h]
0x1800448d4  call    WPP_SF_qD
0x1800448d9  cmp     cs:byte_18008D62D, r12b
0x1800448e0  jb      short loc_180044943
0x1800448e2  mov     edx, 57h ; 'W'
0x1800448e7  jmp     short loc_180044926
0x1800448e9  lea     rcx, [rsi+40h]
0x1800448ed  lea     rdx, [rbp+57h+var_A0]
0x1800448f1  call    ?swap@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::swap(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &)
0x1800448f6  mov     rdx, [rbp+57h+var_B0]
0x1800448fa  lea     rcx, [rsi+38h]
0x1800448fe  mov     [rsi+48h], r15d
0x180044902  mov     [rsi+58h], r12b
0x180044906  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x18004490b  lea     rcx, [rsi+50h]
0x18004490f  lea     rdx, [rbp+57h+ppMFAttributes]
0x180044913  call    ??4?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::operator=(wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy> const &)
0x180044918  cmp     cs:byte_18008D62D, 8
0x18004491f  jb      short loc_180044943
0x180044921  mov     edx, 58h ; 'X'
0x180044926  mov     rcx, cs:WPP_GLOBAL_Control
0x18004492d  mov     r9, rsi
0x180044930  mov     r8, r14
0x180044933  mov     [rsp+100h+var_E0], edi
0x180044937  mov     rcx, [rcx+0D8h]
0x18004493e  call    WPP_SF_qD
0x180044943  lea     rcx, [rbp+57h+ppMFAttributes]
0x180044947  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004494c  lea     rcx, [rbp+57h+var_B0]
0x180044950  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180044955  mov     rcx, [rbp+57h+pv]; pv
0x180044959  mov     [rbp+57h+pv], 0
0x180044961  test    rcx, rcx
0x180044964  jz      short loc_18004496C
0x180044966  call    cs:__imp_CoTaskMemFree
0x18004496c  lea     rcx, [rbp+57h+var_A0]
0x180044970  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180044975  mov     eax, edi
0x180044977  mov     rcx, [rbp+57h+var_38]
0x18004497b  xor     rcx, rsp; StackCookie
0x18004497e  call    __security_check_cookie
0x180044983  mov     rbx, [rsp+100h+arg_18]
0x18004498b  add     rsp, 0D0h
0x180044992  pop     r15
0x180044994  pop     r14
0x180044996  pop     r13
0x180044998  pop     r12
0x18004499a  pop     rdi
0x18004499b  pop     rsi
0x18004499c  pop     rbp
0x18004499d  retn
```
