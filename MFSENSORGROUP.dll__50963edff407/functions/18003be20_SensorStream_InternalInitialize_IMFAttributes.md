# SensorStream::InternalInitialize(IMFAttributes *)

- ea: `0x18003be20`
- end: `0x18003c4d6`
- name: `?InternalInitialize@SensorStream@@MEAAJPEAUIMFAttributes@@@Z`
- size: `1718`
- prototype: `__int64 __fastcall(SensorStream *__hidden this, struct IMFAttributes *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180008fe4`
- `0x1800099b4`
- `0x18000ae40`
- `0x180019d8c`
- `0x18001b144`
- `0x18001ba24`
- `0x18001bce0`
- `0x18001c96c`
- `0x18001ee8c`
- `0x180030428`
- `0x180031920`
- `0x18003491c`
- `0x1800373c8`
- `0x18003be20`
- `0x1800513d0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfe5`
- `MFPlat!MFCreateMediaType` at `0x18003c0c8`
- `MFPlat!MFCreateMediaType` at `0x18003c0c8`
- `MFPlat!MFCreateAttributes` at `0x18003beff`
- `MFPlat!MFCreateAttributes` at `0x18003beff`

## pseudocode

```c
__int64 __fastcall SensorStream::InternalInitialize(SensorStream *this, struct IMFAttributes *a2)
{
  int v4; // esi
  HRESULT v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  IMFAttributes *v8; // r14
  void *v9; // rbx
  HRESULT (__stdcall *GetAllocatedBlob)(IMFAttributes *, const GUID *const, UINT8 **, UINT32 *); // r15
  IMFAttributes *v11; // r14
  void *v12; // rbx
  HRESULT (__stdcall *v13)(IMFAttributes *, const GUID *const, UINT8 **, UINT32 *); // r15
  unsigned __int64 v14; // r12
  unsigned int v15; // r14d
  int v16; // r15d
  char *v17; // rdx
  char *v18; // r13
  HRESULT v19; // eax
  __int64 (__fastcall *v20)(SensorStream *, char *, IMFMediaType *, LPVOID, _DWORD, int *, char *); // rax
  __int64 v21; // rdx
  MediaTypeTracer *v22; // rax
  const char *String; // rax
  MediaTypeTracer *v24; // rax
  const char *v25; // rax
  MediaTypeTracer *v26; // rax
  const char *v27; // rax
  __int64 v28; // rdx
  IMFMediaType *ppMFType; // [rsp+40h] [rbp-69h] BYREF
  struct IMFMediaType *v31; // [rsp+48h] [rbp-61h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-59h] BYREF
  UINT32 cInitialSize; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v34; // [rsp+5Ch] [rbp-4Dh] BYREF
  unsigned int v35; // [rsp+60h] [rbp-49h] BYREF
  LPVOID v36; // [rsp+68h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-39h] BYREF
  int v38; // [rsp+78h] [rbp-31h] BYREF
  LPVOID v39; // [rsp+80h] [rbp-29h]
  __int64 v40; // [rsp+88h] [rbp-21h] BYREF
  char *v41; // [rsp+90h] [rbp-19h]
  _BYTE v42[104]; // [rsp+98h] [rbp-11h] BYREF
  int v43; // [rsp+118h] [rbp+6Fh] BYREF
  char v44; // [rsp+120h] [rbp+77h] BYREF
  bool v45; // [rsp+128h] [rbp+7Fh]

  v43 = 0;
  cInitialSize = 0;
  v4 = 0;
  ppMFAttributes = 0;
  pv = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v40 = 0;
  v38 = 0;
  v45 = SGIsProcessInContainer();
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 59, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, this, a2);
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 60;
LABEL_77:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, this, v5);
    goto LABEL_78;
  }
  v5 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))a2->lpVtbl->GetCount)(a2, &cInitialSize);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 61;
    goto LABEL_77;
  }
  v5 = MFCreateAttributes(&ppMFAttributes, cInitialSize);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 62;
    goto LABEL_77;
  }
  v5 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a2->lpVtbl->CopyAllItems)(a2, ppMFAttributes);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 63;
    goto LABEL_77;
  }
  v8 = ppMFAttributes;
  v9 = pv;
  GetAllocatedBlob = ppMFAttributes->lpVtbl->GetAllocatedBlob;
  if ( pv )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v43);
    CoTaskMemFree(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v43);
  }
  pv = 0;
  v5 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, LPVOID *, unsigned int *))GetAllocatedBlob)(
         v8,
         MF_SENSORSTREAM_SENSORMEDIATYPEINFO_LIST,
         &pv,
         &v34);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 64;
    goto LABEL_77;
  }
  v11 = ppMFAttributes;
  v12 = v36;
  v13 = ppMFAttributes->lpVtbl->GetAllocatedBlob;
  if ( v36 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v43);
    CoTaskMemFree(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v43);
  }
  v36 = 0;
  v5 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, LPVOID *, unsigned int *))v13)(
         v11,
         MF_SENSORSTREAM_SENSORMEDIATYPEENTRY_LIST,
         &v36,
         &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 65;
    goto LABEL_77;
  }
  v14 = v34 / 0x18uLL;
  if ( v34 != 24 * v14 || (v15 = v35 / 0x1C, v35 % 0x1CuLL) )
  {
    v5 = -2147024809;
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_78;
    v7 = 66;
    goto LABEL_77;
  }
  v16 = 0;
  v17 = (char *)v36;
  v39 = pv;
  v41 = (char *)v36;
  if ( v15 )
  {
    while ( 1 )
    {
      ppMFType = 0;
      v31 = 0;
      LOBYTE(v43) = 0;
      v44 = 0;
      v18 = &v17[28 * v16];
      if ( *((_DWORD *)v18 + 1) != v16 )
      {
        v6 = -2147418113;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
            this,
            -2147418113);
        goto LABEL_71;
      }
      v19 = MFCreateMediaType(&ppMFType);
      v6 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
        {
          v21 = 68;
          goto LABEL_58;
        }
        goto LABEL_71;
      }
      v20 = *(__int64 (__fastcall **)(SensorStream *, char *, IMFMediaType *, LPVOID, _DWORD, int *, char *))(*(_QWORD *)this + 384LL);
      if ( v45 )
      {
        v19 = v20(this, v18, ppMFType, v39, v14, &v43, &v44);
        v6 = v19;
        if ( v19 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_71;
          v21 = 69;
          goto LABEL_58;
        }
      }
      else
      {
        v19 = v20(this, v18, ppMFType, v39, v14, &v43, 0);
        v6 = v19;
        if ( v19 < 0 )
        {
          if ( g_wppLevels )
          {
            v21 = 70;
            goto LABEL_58;
          }
          goto LABEL_71;
        }
      }
      if ( v44 )
      {
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v4 |= 1u;
          v22 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v42, ppMFType);
          String = FSString::GetString((MediaTypeTracer *)((char *)v22 + 8));
          WPP_SF_qDs(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            71,
            (unsigned int)&WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
            (_DWORD)this,
            v16,
            (__int64)String);
        }
        if ( (v4 & 1) != 0 )
        {
          v4 &= ~1u;
          MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v42);
        }
        goto LABEL_54;
      }
      v19 = MFCreatePassthroughTranslatedMediaType(ppMFType, &GUID_5f3ee6ff_f69d_409c_8e41_d51107e9bb78, &v31);
      v6 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
        {
          v21 = 72;
          goto LABEL_58;
        }
        goto LABEL_71;
      }
      if ( !(_BYTE)v43 )
        break;
      if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64 *)this + 12, (__int64)v31) )
      {
        v19 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_71;
        v21 = 73;
        goto LABEL_58;
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v4 |= 2u;
        v24 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v42, v31);
        v25 = FSString::GetString((MediaTypeTracer *)((char *)v24 + 8));
        WPP_SF_qDs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          74,
          (unsigned int)&WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
          (_DWORD)this,
          v16,
          (__int64)v25);
      }
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
LABEL_52:
        MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v42);
      }
LABEL_53:
      v19 = MaxMediaTypesEx(
              (_DWORD)ppMFType,
              (unsigned int)&v40,
              (unsigned int)&v38,
              (int)this + 672,
              (__int64)this + 664);
      v6 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
        {
          v21 = 77;
LABEL_58:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
            this,
            v19);
          goto LABEL_71;
        }
        goto LABEL_71;
      }
LABEL_54:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v31);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFType);
      if ( ++v16 >= v15 )
        goto LABEL_72;
      v17 = v41;
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64 *)this + 9, (__int64)v31) )
    {
      v19 = -2147024882;
      v6 = -2147024882;
      if ( g_wppLevels )
      {
        v21 = 75;
        goto LABEL_58;
      }
LABEL_71:
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v31);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFType);
LABEL_78:
      CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll((char *)this + 72);
      if ( byte_18008D62D )
      {
        v28 = 78;
LABEL_80:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v28, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, this, v6);
      }
      goto LABEL_81;
    }
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v4 |= 4u;
      v26 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v42, v31);
      v27 = FSString::GetString((MediaTypeTracer *)((char *)v26 + 8));
      WPP_SF_qDs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        76,
        (unsigned int)&WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
        (_DWORD)this,
        v16,
        (__int64)v27);
    }
    if ( (v4 & 4) == 0 )
      goto LABEL_53;
    v4 &= ~4u;
    goto LABEL_52;
  }
LABEL_72:
  ((void (__fastcall *)(IMFAttributes *, __int64 *))ppMFAttributes->lpVtbl->DeleteItem)(
    ppMFAttributes,
    MF_SENSORSTREAM_SENSORMEDIATYPEINFO_LIST);
  ((void (__fastcall *)(IMFAttributes *, __int64 *))ppMFAttributes->lpVtbl->DeleteItem)(
    ppMFAttributes,
    MF_SENSORSTREAM_SENSORMEDIATYPEENTRY_LIST);
  ComSmartPtr<IMFAttributes>::operator=((_QWORD *)this + 8, &ppMFAttributes);
  if ( v6 < 0 )
    goto LABEL_78;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v28 = 79;
    goto LABEL_80;
  }
LABEL_81:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v36);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003be20  mov     [rsp-8+arg_0], rbx
0x18003be25  push    rbp
0x18003be26  push    rsi
0x18003be27  push    rdi
0x18003be28  push    r12
0x18003be2a  push    r13
0x18003be2c  push    r14
0x18003be2e  push    r15
0x18003be30  lea     rbp, [rsp-27h]
0x18003be35  sub     rsp, 0D0h
0x18003be3c  xor     r13d, r13d
0x18003be3f  mov     r14, rdx
0x18003be42  mov     [rbp+57h+arg_8], r13d
0x18003be46  mov     rdi, rcx
0x18003be49  mov     [rbp+57h+cInitialSize], r13d
0x18003be4d  mov     esi, r13d
0x18003be50  mov     [rbp+57h+ppMFAttributes], r13
0x18003be54  mov     [rbp+57h+pv], r13
0x18003be58  mov     [rbp+57h+var_A4], r13d
0x18003be5c  mov     [rbp+57h+var_98], r13
0x18003be60  mov     [rbp+57h+var_A0], r13d
0x18003be64  mov     [rbp+57h+var_78], r13
0x18003be68  mov     [rbp+57h+var_88], r13d
0x18003be6c  call    ?SGIsProcessInContainer@@YA_NXZ; SGIsProcessInContainer(void)
0x18003be71  mov     [rbp+57h+arg_18], al
0x18003be74  cmp     cs:byte_18008D62D, 8
0x18003be7b  jb      short loc_18003BEA3
0x18003be7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be84  lea     edx, [r13+3Bh]
0x18003be88  mov     r9, rdi
0x18003be8b  mov     [rsp+100h+var_E0], r14
0x18003be90  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x18003be97  mov     rcx, [rcx+0D8h]
0x18003be9e  call    WPP_SF_qq
0x18003bea3  test    r14, r14
0x18003bea6  jnz     short loc_18003BEC5
0x18003bea8  mov     eax, 80070057h
0x18003bead  mov     ebx, eax
0x18003beaf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003beb6  jb      loc_18003C466
0x18003bebc  lea     edx, [r14+3Ch]
0x18003bec0  jmp     loc_18003C448
0x18003bec5  mov     rax, [r14]
0x18003bec8  lea     rdx, [rbp+57h+cInitialSize]
0x18003becc  mov     rcx, r14
0x18003becf  mov     rax, [rax+0F0h]
0x18003bed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bedb  mov     ebx, eax
0x18003bedd  test    eax, eax
0x18003bedf  jns     short loc_18003BEF8
0x18003bee1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bee8  jb      loc_18003C466
0x18003beee  mov     edx, 3Dh ; '='
0x18003bef3  jmp     loc_18003C448
0x18003bef8  mov     edx, [rbp+57h+cInitialSize]; cInitialSize
0x18003befb  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x18003beff  call    cs:__imp_MFCreateAttributes
0x18003bf05  mov     ebx, eax
0x18003bf07  test    eax, eax
0x18003bf09  jns     short loc_18003BF22
0x18003bf0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bf12  jb      loc_18003C466
0x18003bf18  mov     edx, 3Eh ; '>'
0x18003bf1d  jmp     loc_18003C448
0x18003bf22  mov     rax, [r14]
0x18003bf25  mov     rcx, r14
0x18003bf28  mov     rdx, [rbp+57h+ppMFAttributes]
0x18003bf2c  mov     rax, [rax+100h]
0x18003bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf38  mov     ebx, eax
0x18003bf3a  test    eax, eax
0x18003bf3c  jns     short loc_18003BF55
0x18003bf3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bf45  jb      loc_18003C466
0x18003bf4b  mov     edx, 3Fh ; '?'
0x18003bf50  jmp     loc_18003C448
0x18003bf55  mov     r14, [rbp+57h+ppMFAttributes]
0x18003bf59  mov     rbx, [rbp+57h+pv]
0x18003bf5d  mov     rax, [r14]
0x18003bf60  mov     r15, [rax+80h]
0x18003bf67  test    rbx, rbx
0x18003bf6a  jz      short loc_18003BF87
0x18003bf6c  lea     rcx, [rbp+57h+arg_8]; this
0x18003bf70  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003bf75  mov     rcx, rbx; pv
0x18003bf78  call    cs:__imp_CoTaskMemFree
0x18003bf7e  lea     rcx, [rbp+57h+arg_8]; this
0x18003bf82  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003bf87  lea     r9, [rbp+57h+var_A4]
0x18003bf8b  mov     [rbp+57h+pv], r13
0x18003bf8f  lea     r8, [rbp+57h+pv]
0x18003bf93  mov     rcx, r14
0x18003bf96  lea     rdx, MF_SENSORSTREAM_SENSORMEDIATYPEINFO_LIST
0x18003bf9d  mov     rax, r15
0x18003bfa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfa5  mov     ebx, eax
0x18003bfa7  test    eax, eax
0x18003bfa9  jns     short loc_18003BFC2
0x18003bfab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003bfb2  jb      loc_18003C466
0x18003bfb8  mov     edx, 40h ; '@'
0x18003bfbd  jmp     loc_18003C448
0x18003bfc2  mov     r14, [rbp+57h+ppMFAttributes]
0x18003bfc6  mov     rbx, [rbp+57h+var_98]
0x18003bfca  mov     rax, [r14]
0x18003bfcd  mov     r15, [rax+80h]
0x18003bfd4  test    rbx, rbx
0x18003bfd7  jz      short loc_18003BFF4
0x18003bfd9  lea     rcx, [rbp+57h+arg_8]; this
0x18003bfdd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003bfe2  mov     rcx, rbx; pv
0x18003bfe5  call    cs:__imp_CoTaskMemFree
0x18003bfeb  lea     rcx, [rbp+57h+arg_8]; this
0x18003bfef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003bff4  lea     r9, [rbp+57h+var_A0]
0x18003bff8  mov     [rbp+57h+var_98], r13
0x18003bffc  lea     r8, [rbp+57h+var_98]
0x18003c000  mov     rcx, r14
0x18003c003  lea     rdx, MF_SENSORSTREAM_SENSORMEDIATYPEENTRY_LIST
0x18003c00a  mov     rax, r15
0x18003c00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c012  mov     ebx, eax
0x18003c014  test    eax, eax
0x18003c016  jns     short loc_18003C02F
0x18003c018  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c01f  jb      loc_18003C466
0x18003c025  mov     edx, 41h ; 'A'
0x18003c02a  jmp     loc_18003C448
0x18003c02f  mov     ecx, [rbp+57h+var_A4]
0x18003c032  mov     rax, 0AAAAAAAAAAAAAAABh
0x18003c03c  mul     rcx
0x18003c03f  mov     r12, rdx
0x18003c042  shr     r12, 4
0x18003c046  lea     rax, [r12+r12*2]
0x18003c04a  shl     rax, 3
0x18003c04e  cmp     rcx, rax
0x18003c051  jnz     loc_18003C433
0x18003c057  mov     ecx, [rbp+57h+var_A0]
0x18003c05a  mov     rax, 2492492492492493h
0x18003c064  mul     rcx
0x18003c067  mov     r14d, ecx
0x18003c06a  sub     r14, rdx
0x18003c06d  shr     r14, 1
0x18003c070  add     r14, rdx
0x18003c073  shr     r14, 4
0x18003c077  imul    rax, r14, 1Ch
0x18003c07b  sub     rcx, rax
0x18003c07e  jnz     loc_18003C433
0x18003c084  mov     rax, [rbp+57h+pv]
0x18003c088  mov     r15d, r13d
0x18003c08b  mov     rdx, [rbp+57h+var_98]
0x18003c08f  mov     [rbp+57h+var_80], rax
0x18003c093  mov     [rbp+57h+var_70], rdx
0x18003c097  test    r14d, r14d
0x18003c09a  jz      loc_18003C3DE
0x18003c0a0  mov     [rbp+57h+ppMFType], r13
0x18003c0a4  mov     [rbp+57h+var_B8], r13
0x18003c0a8  mov     byte ptr [rbp+57h+arg_8], r13b
0x18003c0ac  mov     [rbp+57h+arg_10], r13b
0x18003c0b0  mov     eax, r15d
0x18003c0b3  imul    r13, rax, 1Ch
0x18003c0b7  add     r13, rdx
0x18003c0ba  cmp     [r13+4], r15d
0x18003c0be  jnz     loc_18003C396
0x18003c0c4  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18003c0c8  call    cs:__imp_MFCreateMediaType
0x18003c0ce  mov     ebx, eax
0x18003c0d0  test    eax, eax
0x18003c0d2  js      loc_18003C386
0x18003c0d8  cmp     [rbp+57h+arg_18], 0
0x18003c0dc  mov     rdx, r13
0x18003c0df  mov     rax, [rdi]
0x18003c0e2  mov     r9, [rbp+57h+var_80]
0x18003c0e6  mov     r8, [rbp+57h+ppMFType]
0x18003c0ea  mov     rax, [rax+180h]
0x18003c0f1  jz      short loc_18003C131
0x18003c0f3  lea     rcx, [rbp+57h+arg_10]
0x18003c0f7  mov     [rsp+100h+var_D0], rcx
0x18003c0fc  lea     rcx, [rbp+57h+arg_8]
0x18003c100  mov     [rsp+100h+var_D8], rcx
0x18003c105  mov     rcx, rdi
0x18003c108  mov     dword ptr [rsp+100h+var_E0], r12d
0x18003c10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c112  xor     r13d, r13d
0x18003c115  mov     ebx, eax
0x18003c117  test    eax, eax
0x18003c119  jns     short loc_18003C15D
0x18003c11b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c122  jb      loc_18003C3C7
0x18003c128  lea     edx, [r13+45h]
0x18003c12c  jmp     loc_18003C339
0x18003c131  lea     rcx, [rbp+57h+arg_8]
0x18003c135  mov     [rsp+100h+var_D0], 0
0x18003c13e  mov     [rsp+100h+var_D8], rcx
0x18003c143  mov     rcx, rdi
0x18003c146  mov     dword ptr [rsp+100h+var_E0], r12d
0x18003c14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c150  xor     r13d, r13d
0x18003c153  mov     ebx, eax
0x18003c155  test    eax, eax
0x18003c157  js      loc_18003C376
0x18003c15d  cmp     [rbp+57h+arg_10], r13b
0x18003c161  jz      short loc_18003C1CC
0x18003c163  cmp     cs:byte_18008D62D, 8
0x18003c16a  jb      short loc_18003C1B1
0x18003c16c  mov     rdx, [rbp+57h+ppMFType]; struct IMFMediaType *
0x18003c170  lea     rcx, [rbp+57h+var_68]; this
0x18003c174  or      esi, 1
0x18003c177  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x18003c17c  lea     rcx, [rax+8]; this
0x18003c180  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003c185  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c18c  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x18003c193  mov     [rsp+100h+var_D8], rax
0x18003c198  mov     edx, 47h ; 'G'
0x18003c19d  mov     r9, rdi
0x18003c1a0  mov     dword ptr [rsp+100h+var_E0], r15d
0x18003c1a5  mov     rcx, [rcx+0D8h]
0x18003c1ac  call    WPP_SF_qDs
0x18003c1b1  test    sil, 1
0x18003c1b5  jz      loc_18003C2F9
0x18003c1bb  and     esi, 0FFFFFFFEh
0x18003c1be  lea     rcx, [rbp+57h+var_68]; this
0x18003c1c2  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x18003c1c7  jmp     loc_18003C2F9
0x18003c1cc  mov     rcx, [rbp+57h+ppMFType]
0x18003c1d0  lea     r8, [rbp+57h+var_B8]
0x18003c1d4  lea     rdx, _GUID_5f3ee6ff_f69d_409c_8e41_d51107e9bb78
0x18003c1db  call    MFCreatePassthroughTranslatedMediaType
0x18003c1e0  mov     ebx, eax
0x18003c1e2  test    eax, eax
0x18003c1e4  js      loc_18003C366
0x18003c1ea  mov     rdx, [rbp+57h+var_B8]
0x18003c1ee  cmp     byte ptr [rbp+57h+arg_8], r13b
0x18003c1f2  jz      short loc_18003C25E
0x18003c1f4  lea     rcx, [rdi+60h]
0x18003c1f8  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18003c1fd  test    eax, eax
0x18003c1ff  jz      loc_18003C320
0x18003c205  cmp     cs:byte_18008D62D, 8
0x18003c20c  jb      short loc_18003C253
0x18003c20e  mov     rdx, [rbp+57h+var_B8]; struct IMFMediaType *
0x18003c212  lea     rcx, [rbp+57h+var_68]; this
0x18003c216  or      esi, 2
0x18003c219  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x18003c21e  lea     rcx, [rax+8]; this
0x18003c222  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003c227  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c22e  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x18003c235  mov     [rsp+100h+var_D8], rax
0x18003c23a  mov     edx, 4Ah ; 'J'
0x18003c23f  mov     r9, rdi
0x18003c242  mov     dword ptr [rsp+100h+var_E0], r15d
0x18003c247  mov     rcx, [rcx+0D8h]
0x18003c24e  call    WPP_SF_qDs
0x18003c253  test    sil, 2
0x18003c257  jz      short loc_18003C2CF
0x18003c259  and     esi, 0FFFFFFFDh
0x18003c25c  jmp     short loc_18003C2C6
0x18003c25e  lea     rcx, [rdi+48h]
0x18003c262  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18003c267  test    eax, eax
0x18003c269  jz      loc_18003C34F
0x18003c26f  cmp     cs:byte_18008D62D, 8
0x18003c276  jb      short loc_18003C2BD
0x18003c278  mov     rdx, [rbp+57h+var_B8]; struct IMFMediaType *
0x18003c27c  lea     rcx, [rbp+57h+var_68]; this
0x18003c280  or      esi, 4
0x18003c283  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x18003c288  lea     rcx, [rax+8]; this
0x18003c28c  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003c291  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c298  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x18003c29f  mov     [rsp+100h+var_D8], rax
0x18003c2a4  mov     edx, 4Ch ; 'L'
0x18003c2a9  mov     r9, rdi
0x18003c2ac  mov     dword ptr [rsp+100h+var_E0], r15d
0x18003c2b1  mov     rcx, [rcx+0D8h]
0x18003c2b8  call    WPP_SF_qDs
0x18003c2bd  test    sil, 4
0x18003c2c1  jz      short loc_18003C2CF
0x18003c2c3  and     esi, 0FFFFFFFBh
0x18003c2c6  lea     rcx, [rbp+57h+var_68]; this
0x18003c2ca  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x18003c2cf  mov     rcx, [rbp+57h+ppMFType]
0x18003c2d3  lea     rax, [rdi+298h]
0x18003c2da  lea     r9, [rdi+2A0h]
0x18003c2e1  mov     [rsp+100h+var_E0], rax
0x18003c2e6  lea     r8, [rbp+57h+var_88]
0x18003c2ea  lea     rdx, [rbp+57h+var_78]
0x18003c2ee  call    ?MaxMediaTypesEx@@YAJPEAUIMFMediaType@@PEA_KPEAMAEAV?$ComSmartPtr@UIMFMediaType@@@@3@Z; MaxMediaTypesEx(IMFMediaType *,unsigned __int64 *,float *,ComSmartPtr<IMFMediaType> &,ComSmartPtr<IMFMediaType> &)
0x18003c2f3  mov     ebx, eax
0x18003c2f5  test    eax, eax
0x18003c2f7  js      short loc_18003C33F
0x18003c2f9  lea     rcx, [rbp+57h+var_B8]
0x18003c2fd  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18003c302  lea     rcx, [rbp+57h+ppMFType]
0x18003c306  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18003c30b  inc     r15d
0x18003c30e  cmp     r15d, r14d
  ... truncated ...
```
