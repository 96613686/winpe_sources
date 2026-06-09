# FSConfiguration::InternalInitialize(ushort const *,FSCFG_ENTRY2 const &)

- ea: `0x18003d740`
- end: `0x18003dbd8`
- name: `?InternalInitialize@FSConfiguration@@MEAAJPEBGAEBUFSCFG_ENTRY2@@@Z`
- size: `1176`
- prototype: `int(FSConfiguration *__hidden this, const unsigned __int16 *, const struct FSCFG_ENTRY2 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180005ff8`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000e338`
- `0x18000e66c`
- `0x180011438`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18002fd04`
- `0x180032ec8`
- `0x18003c670`
- `0x18003d740`
- `0x18003ed5c`
- `0x1800407b0`
- `0x18004bf44`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dba0`
- `MFPlat!MFCreateAttributes` at `0x18003d897`
- `MFPlat!MFCreateAttributes` at `0x18003d897`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003da13`
- `MFPlat!MFInitAttributesFromBlob` at `0x18003da13`

## pseudocode

```c
__int64 __fastcall FSConfiguration::InternalInitialize(
        FSConfiguration *this,
        const struct std::nothrow_t *a2,
        const struct FSCFG_ENTRY2 *a3)
{
  char v3; // bl
  BlobTrace *v7; // rax
  const char *String; // rax
  int v9; // edi
  __int64 v10; // rbx
  GuidTrace *v11; // rax
  const char *v12; // rcx
  int v13; // eax
  int v14; // edi
  __int64 v15; // rdx
  DEVPROPGUID v16; // xmm0
  unsigned int v17; // edi
  const struct std::nothrow_t *unique; // rax
  unsigned __int8 *v19; // rbx
  unsigned int v20; // r15d
  struct IMFAttributesVtbl *lpVtbl; // rax
  const struct _GUID *v22; // r8
  void *v23; // rcx
  __int64 v24; // rdx
  void *v25; // rdx
  void *v26; // rcx
  unsigned int *v28; // [rsp+28h] [rbp-81h]
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
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v7 = BlobTrace::BlobTrace((BlobTrace *)&p_pv, (char *)a3 + 24, (unsigned int)a3);
    String = FSString::GetString((BlobTrace *)((char *)v7 + 8));
    v9 = *((_DWORD *)a3 + 1);
    v10 = (__int64)String;
    v11 = GuidTrace::GuidTrace((GuidTrace *)v39, (const struct _GUID *)((char *)a3 + 8));
    v28 = (unsigned int *)GuidTrace::GetString(v11);
    v12 = (const char *)a2;
    if ( !a2 )
      v12 = L"<nullptr>";
    WPP_SF_qSsds(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v12, (__int64)v28, v9, v10);
    v3 = 3;
  }
  if ( (v3 & 2) != 0 )
  {
    v3 &= ~2u;
    FSString::~FSString((FSString *)v39, a2);
  }
  if ( (v3 & 1) != 0 )
  {
    p_pv = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)&v37, a2);
  }
  if ( !a2 )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( g_wppLevels )
    {
      v15 = 76;
LABEL_45:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v13);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  v16 = *(DEVPROPGUID *)((char *)a3 + 8);
  PropertyKey.pid = *((_DWORD *)a3 + 1);
  PropertyKey.fmtid = v16;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v13 = MFCreateAttributes(&ppMFAttributes, 1u);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 77;
      goto LABEL_45;
    }
LABEL_46:
    if ( !byte_18005E5A5 )
      goto LABEL_51;
    v24 = 87;
    goto LABEL_50;
  }
  v13 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, 0, 0, &v29);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 78;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v17 = v29;
  if ( v29 < 0x28 )
  {
    v13 = -2147023881;
    v14 = -2147023881;
    if ( g_wppLevels )
    {
      v15 = 79;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v35, v29);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v34, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v35);
  v19 = v34;
  if ( !v34 )
  {
    v14 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v34 + 80),
        &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids,
        this,
        -2147024882);
    goto LABEL_46;
  }
  v13 = FSGetDeviceInterfaceProperty2((LPCWSTR)a2, &PropertyKey, 0x1003u, v34, v17, &v29);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 81;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v20 = v29;
  if ( v29 < 0x28 )
  {
    v13 = -2147023881;
    v14 = -2147023881;
    if ( g_wppLevels )
    {
      v15 = 82;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  if ( memcmp_0(v19 + 8, (char *)a3 + 24, 0x20u) )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( g_wppLevels )
    {
      v15 = 83;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v13 = MFInitAttributesFromBlob(ppMFAttributes, v19 + 40, v20 - 40);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 84;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  lpVtbl = ppMFAttributes->lpVtbl;
  p_pv = &pv;
  v37 = 0;
  v38 = 1;
  v14 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64 *, unsigned int *))lpVtbl->GetAllocatedBlob)(
          ppMFAttributes,
          FSM_WSEOPTIN_CONFIGURATION_KEY_INFO,
          &v37,
          &v30);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v14);
    goto LABEL_46;
  }
  v23 = v32;
  v32 = 0;
  if ( v23 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  v13 = FSConfigurationKey::CreateKeyFromBlob((GUID *)pv, v30, v22, &v32);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 86;
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  v25 = v32;
  v34 = (unsigned __int8 *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v19;
  *((_DWORD *)this + 18) = v20;
  *((_BYTE *)this + 88) = 1;
  wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=((__int64 *)this + 7, (__int64)v25);
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::operator=((__int64 *)this + 10, (__int64 *)&ppMFAttributes);
  if ( (unsigned __int8)byte_18005E5A5 < 8u )
    goto LABEL_51;
  v24 = 88;
LABEL_50:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v24, &WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids, this, v14);
LABEL_51:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v32);
  v26 = pv;
  pv = 0;
  if ( v26 )
    CoTaskMemFree(v26);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v34);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003d740  mov     [rsp-8+arg_18], rbx
0x18003d745  push    rbp
0x18003d746  push    rsi
0x18003d747  push    rdi
0x18003d748  push    r12
0x18003d74a  push    r13
0x18003d74c  push    r14
0x18003d74e  push    r15
0x18003d750  lea     rbp, [rsp-27h]
0x18003d755  sub     rsp, 0D0h
0x18003d75c  mov     rax, cs:__security_cookie
0x18003d763  xor     rax, rsp
0x18003d766  mov     [rbp+57h+var_38], rax
0x18003d76a  xor     r14d, r14d
0x18003d76d  xorps   xmm0, xmm0
0x18003d770  mov     ebx, r14d
0x18003d773  xor     eax, eax
0x18003d775  mov     [rbp+57h+var_BC], ebx
0x18003d778  mov     r13, r8
0x18003d77b  movups  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x18003d77f  mov     [rbp+57h+PropertyKey.pid], eax
0x18003d782  mov     r12, rdx
0x18003d785  mov     [rbp+57h+var_C0], r14d
0x18003d789  mov     rsi, rcx
0x18003d78c  mov     [rbp+57h+var_A0], r14
0x18003d790  mov     [rbp+57h+pv], r14
0x18003d794  mov     [rbp+57h+var_BC], r14d
0x18003d798  mov     [rbp+57h+var_B0], r14
0x18003d79c  mov     [rbp+57h+ppMFAttributes], r14
0x18003d7a0  cmp     cs:byte_18005E5A5, 8
0x18003d7a7  jb      short loc_18003D819
0x18003d7a9  lea     rdx, [r8+18h]; void *
0x18003d7ad  lea     rcx, [rbp+57h+var_90]; this
0x18003d7b1  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x18003d7b6  lea     rcx, [rax+8]; this
0x18003d7ba  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003d7bf  mov     edi, [r13+4]
0x18003d7c3  lea     rcx, [rbp+57h+var_70]; this
0x18003d7c7  lea     rdx, [r13+8]; struct _GUID *
0x18003d7cb  mov     rbx, rax
0x18003d7ce  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18003d7d3  mov     rcx, rax; this
0x18003d7d6  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18003d7db  mov     [rsp+100h+var_C8], rbx; __int64
0x18003d7e0  lea     rdx, aNullptr; "<nullptr>"
0x18003d7e7  test    r12, r12
0x18003d7ea  mov     dword ptr [rsp+100h+var_D0], edi; char
0x18003d7ee  mov     [rsp+100h+var_D8], rax; __int64
0x18003d7f3  mov     rcx, r12
0x18003d7f6  cmovz   rcx, rdx
0x18003d7fa  mov     r9, rsi
0x18003d7fd  mov     qword ptr [rsp+100h+var_E0], rcx; __int64
0x18003d802  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d809  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003d810  call    WPP_SF_qSsds
0x18003d815  lea     ebx, [r14+3]
0x18003d819  mov     rdi, r13
0x18003d81c  test    bl, 2
0x18003d81f  jz      short loc_18003D82D
0x18003d821  and     ebx, 0FFFFFFFDh
0x18003d824  lea     rcx, [rbp+57h+var_70]; this
0x18003d828  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003d82d  test    bl, 1
0x18003d830  jz      short loc_18003D846
0x18003d832  lea     rax, ??_7SensorGroupBlobHeaderTrace@@6B@; const SensorGroupBlobHeaderTrace::`vftable'
0x18003d839  lea     rcx, [rbp+57h+var_88]; this
0x18003d83d  mov     [rbp+57h+var_90], rax
0x18003d841  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003d846  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003d84d  test    r12, r12
0x18003d850  jnz     short loc_18003D870
0x18003d852  mov     eax, 80070057h
0x18003d857  mov     edi, eax
0x18003d859  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d860  jb      loc_18003DB14
0x18003d866  lea     edx, [r12+4Ch]
0x18003d86b  jmp     loc_18003DAFA
0x18003d870  mov     eax, 8
0x18003d875  lea     rcx, [rbp+57h+ppMFAttributes]
0x18003d879  movups  xmm0, xmmword ptr [rdi+rax]
0x18003d87d  mov     eax, [r13+4]
0x18003d881  mov     [rbp+57h+PropertyKey.pid], eax
0x18003d884  movdqu  xmmword ptr [rbp+57h+PropertyKey.fmtid.Data1], xmm0
0x18003d889  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18003d88e  mov     edx, 1; cInitialSize
0x18003d893  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x18003d897  call    cs:__imp_MFCreateAttributes
0x18003d89d  mov     edi, eax
0x18003d89f  test    eax, eax
0x18003d8a1  jns     short loc_18003D8BA
0x18003d8a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d8aa  jb      loc_18003DB14
0x18003d8b0  mov     edx, 4Dh ; 'M'
0x18003d8b5  jmp     loc_18003DAFA
0x18003d8ba  lea     rax, [rbp+57h+var_C0]
0x18003d8be  mov     r15d, 1003h
0x18003d8c4  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18003d8c9  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x18003d8cd  mov     r8d, r15d; unsigned int
0x18003d8d0  mov     [rsp+100h+var_E0], 0; unsigned int
0x18003d8d8  xor     r9d, r9d; unsigned __int8 *
0x18003d8db  mov     rcx, r12; pszDeviceInterface
0x18003d8de  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x18003d8e3  mov     edi, eax
0x18003d8e5  test    eax, eax
0x18003d8e7  jns     short loc_18003D900
0x18003d8e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d8f0  jb      loc_18003DB14
0x18003d8f6  mov     edx, 4Eh ; 'N'
0x18003d8fb  jmp     loc_18003DAFA
0x18003d900  mov     edi, [rbp+57h+var_C0]
0x18003d903  cmp     edi, 28h ; '('
0x18003d906  jnb     short loc_18003D926
0x18003d908  mov     eax, 800703F7h
0x18003d90d  mov     edi, eax
0x18003d90f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d916  jb      loc_18003DB14
0x18003d91c  mov     edx, 4Fh ; 'O'
0x18003d921  jmp     loc_18003DAFA
0x18003d926  mov     rdx, rdi
0x18003d929  lea     rcx, [rbp+57h+var_98]
0x18003d92d  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003d932  mov     rdx, rax
0x18003d935  lea     rcx, [rbp+57h+var_A0]
0x18003d939  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003d93e  lea     rcx, [rbp+57h+var_98]
0x18003d942  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003d947  mov     rbx, [rbp+57h+var_A0]
0x18003d94b  test    rbx, rbx
0x18003d94e  jnz     short loc_18003D96E
0x18003d950  mov     edi, 8007000Eh
0x18003d955  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d95c  jb      loc_18003DB14
0x18003d962  lea     edx, [rbx+50h]
0x18003d965  mov     [rsp+100h+var_E0], edi
0x18003d969  jmp     loc_18003DAFE
0x18003d96e  lea     rax, [rbp+57h+var_C0]
0x18003d972  mov     r9, rbx; unsigned __int8 *
0x18003d975  mov     [rsp+100h+var_D8], rax; unsigned int *
0x18003d97a  lea     rdx, [rbp+57h+PropertyKey]; PropertyKey
0x18003d97e  mov     r8d, r15d; unsigned int
0x18003d981  mov     [rsp+100h+var_E0], edi; unsigned int
0x18003d985  mov     rcx, r12; pszDeviceInterface
0x18003d988  call    ?FSGetDeviceInterfaceProperty2@@YAJPEBGAEBU_DEVPROPKEY@@KPEAEKPEAK@Z; FSGetDeviceInterfaceProperty2(ushort const *,_DEVPROPKEY const &,ulong,uchar *,ulong,ulong *)
0x18003d98d  mov     edi, eax
0x18003d98f  test    eax, eax
0x18003d991  jns     short loc_18003D9AA
0x18003d993  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d99a  jb      loc_18003DB14
0x18003d9a0  mov     edx, 51h ; 'Q'
0x18003d9a5  jmp     loc_18003DAFA
0x18003d9aa  mov     r15d, [rbp+57h+var_C0]
0x18003d9ae  cmp     r15d, 28h ; '('
0x18003d9b2  jnb     short loc_18003D9D2
0x18003d9b4  mov     eax, 800703F7h
0x18003d9b9  mov     edi, eax
0x18003d9bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d9c2  jb      loc_18003DB14
0x18003d9c8  mov     edx, 52h ; 'R'
0x18003d9cd  jmp     loc_18003DAFA
0x18003d9d2  lea     rdx, [r13+18h]; Buf2
0x18003d9d6  mov     r8d, 20h ; ' '; Size
0x18003d9dc  lea     rcx, [rbx+8]; Buf1
0x18003d9e0  call    memcmp_0
0x18003d9e5  test    eax, eax
0x18003d9e7  jz      short loc_18003DA07
0x18003d9e9  mov     eax, 80070057h
0x18003d9ee  mov     edi, eax
0x18003d9f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d9f7  jb      loc_18003DB14
0x18003d9fd  mov     edx, 53h ; 'S'
0x18003da02  jmp     loc_18003DAFA
0x18003da07  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x18003da0b  lea     r8d, [r15-28h]; cbBufSize
0x18003da0f  lea     rdx, [rbx+28h]; pBuf
0x18003da13  call    cs:__imp_MFInitAttributesFromBlob
0x18003da19  mov     edi, eax
0x18003da1b  test    eax, eax
0x18003da1d  jns     short loc_18003DA36
0x18003da1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003da26  jb      loc_18003DB14
0x18003da2c  mov     edx, 54h ; 'T'
0x18003da31  jmp     loc_18003DAFA
0x18003da36  mov     rcx, [rbp+57h+ppMFAttributes]
0x18003da3a  lea     rdx, [rbp+57h+pv]
0x18003da3e  lea     r9, [rbp+57h+var_BC]
0x18003da42  lea     r8, [rbp+57h+var_88]
0x18003da46  mov     rax, [rcx]
0x18003da49  mov     [rbp+57h+var_90], rdx
0x18003da4d  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_KEY_INFO
0x18003da54  mov     [rbp+57h+var_88], 0
0x18003da5c  mov     [rbp+57h+var_80], 1
0x18003da60  mov     rax, [rax+80h]
0x18003da67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da6c  lea     rcx, [rbp+57h+var_90]
0x18003da70  mov     edi, eax
0x18003da72  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003da77  mov     eax, edi
0x18003da79  lea     r14, WPP_4a8290e74cd23a2793ab70cd17e4201e_Traceguids
0x18003da80  shr     eax, 1Fh
0x18003da83  test    al, al
0x18003da85  jz      short loc_18003DAB9
0x18003da87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003da8e  jb      short loc_18003DAAF
0x18003da90  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da97  mov     edx, 55h ; 'U'
0x18003da9c  mov     r9, rsi
0x18003da9f  mov     [rsp+100h+var_E0], edi
0x18003daa3  mov     r8, r14
0x18003daa6  mov     rcx, [rcx+10h]
0x18003daaa  call    WPP_SF_qD
0x18003daaf  test    edi, edi
0x18003dab1  jns     loc_18003DB52
0x18003dab7  jmp     short loc_18003DB14
0x18003dab9  mov     rcx, [rbp+57h+var_B0]
0x18003dabd  mov     [rbp+57h+var_B0], 0
0x18003dac5  test    rcx, rcx
0x18003dac8  jz      short loc_18003DAD6
0x18003daca  mov     rax, [rcx]
0x18003dacd  mov     rax, [rax+10h]
0x18003dad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dad6  mov     edx, [rbp+57h+var_BC]; unsigned int
0x18003dad9  lea     r9, [rbp+57h+var_B0]; void **
0x18003dadd  mov     rcx, [rbp+57h+pv]; unsigned __int8 *
0x18003dae1  call    ?CreateKeyFromBlob@FSConfigurationKey@@SAJPEBEKAEBU_GUID@@PEAPEAX@Z; FSConfigurationKey::CreateKeyFromBlob(uchar const *,ulong,_GUID const &,void * *)
0x18003dae6  mov     edi, eax
0x18003dae8  test    eax, eax
0x18003daea  jns     short loc_18003DB24
0x18003daec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003daf3  jb      short loc_18003DB14
0x18003daf5  mov     edx, 56h ; 'V'
0x18003dafa  mov     [rsp+100h+var_E0], eax
0x18003dafe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db05  mov     r9, rsi
0x18003db08  mov     r8, r14
0x18003db0b  mov     rcx, [rcx+10h]
0x18003db0f  call    WPP_SF_qD
0x18003db14  cmp     cs:byte_18005E5A5, 1
0x18003db1b  jb      short loc_18003DB7D
0x18003db1d  mov     edx, 57h ; 'W'
0x18003db22  jmp     short loc_18003DB60
0x18003db24  mov     rax, [rsi+40h]
0x18003db28  lea     rcx, [rsi+38h]
0x18003db2c  mov     rdx, [rbp+57h+var_B0]
0x18003db30  mov     [rbp+57h+var_A0], rax
0x18003db34  mov     [rsi+40h], rbx
0x18003db38  mov     [rsi+48h], r15d
0x18003db3c  mov     byte ptr [rsi+58h], 1
0x18003db40  call    ??4?$com_ptr_t@UIFSConfigurationKey@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSConfigurationKey@@@Z; wil::com_ptr_t<IFSConfigurationKey,wil::err_returncode_policy>::operator=(IFSConfigurationKey *)
0x18003db45  lea     rcx, [rsi+50h]
0x18003db49  lea     rdx, [rbp+57h+ppMFAttributes]
0x18003db4d  call    ??4?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy> const &)
0x18003db52  cmp     cs:byte_18005E5A5, 8
0x18003db59  jb      short loc_18003DB7D
0x18003db5b  mov     edx, 58h ; 'X'
0x18003db60  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db67  mov     r9, rsi
0x18003db6a  mov     r8, r14
0x18003db6d  mov     [rsp+100h+var_E0], edi
0x18003db71  mov     rcx, [rcx+0D8h]
0x18003db78  call    WPP_SF_qD
0x18003db7d  lea     rcx, [rbp+57h+ppMFAttributes]
0x18003db81  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003db86  lea     rcx, [rbp+57h+var_B0]
0x18003db8a  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18003db8f  mov     rcx, [rbp+57h+pv]; pv
0x18003db93  mov     [rbp+57h+pv], 0
0x18003db9b  test    rcx, rcx
0x18003db9e  jz      short loc_18003DBA6
0x18003dba0  call    cs:__imp_CoTaskMemFree
0x18003dba6  lea     rcx, [rbp+57h+var_A0]
0x18003dbaa  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003dbaf  mov     eax, edi
0x18003dbb1  mov     rcx, [rbp+57h+var_38]
0x18003dbb5  xor     rcx, rsp; StackCookie
0x18003dbb8  call    __security_check_cookie
0x18003dbbd  mov     rbx, [rsp+100h+arg_18]
0x18003dbc5  add     rsp, 0D0h
0x18003dbcc  pop     r15
0x18003dbce  pop     r14
0x18003dbd0  pop     r13
0x18003dbd2  pop     r12
0x18003dbd4  pop     rdi
0x18003dbd5  pop     rsi
0x18003dbd6  pop     rbp
0x18003dbd7  retn
```
