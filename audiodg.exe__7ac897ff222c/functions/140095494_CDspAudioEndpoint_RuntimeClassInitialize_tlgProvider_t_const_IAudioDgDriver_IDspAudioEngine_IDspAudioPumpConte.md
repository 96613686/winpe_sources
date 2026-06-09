# CDspAudioEndpoint::RuntimeClassInitialize(_tlgProvider_t const *,IAudioDgDriver *,IDspAudioEngine *,IDspAudioPumpContext *,ushort const *,tWAVEFORMATEX *,__int64)

- ea: `0x140095494`
- end: `0x140095c75`
- name: `?RuntimeClassInitialize@CDspAudioEndpoint@@QEAAJPEBU_tlgProvider_t@@PEAUIAudioDgDriver@@PEAUIDspAudioEngine@@PEAUIDspAudioPumpContext@@PEBGPEAUtWAVEFORMATEX@@_J@Z`
- size: `2017`
- prototype: `__int64 __fastcall(CDspAudioEndpoint *__hidden this, const struct _tlgProvider_t *, struct IAudioDgDriver *, struct IDspAudioEngine *, struct IDspAudioPumpContext *, const unsigned __int16 *, struct tWAVEFORMATEX *Src, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14004eba8`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x140011e00`
- `0x140016f68`
- `0x14001d790`
- `0x1400310a0`
- `0x14004f178`
- `0x1400516e8`
- `0x14005d0e0`
- `0x14005d7bc`
- `0x14005e150`
- `0x14005e168`
- `0x140061904`
- `0x140094968`
- `0x140094a7c`
- `0x140094d0c`
- `0x140094d30`
- `0x140094d54`
- `0x140095090`
- `0x140095494`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140095786`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140095786`
- `ntdll!NtCreateFile` at `0x14009582b`
- `ntdll!NtCreateFile` at `0x14009582b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140095614`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140095614`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140095524`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140095524`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDspAudioEndpoint::RuntimeClassInitialize(
        void **this,
        const struct _tlgProvider_t *a2,
        struct IAudioDgDriver *a3,
        struct IDspAudioEngine *a4,
        struct IDspAudioPumpContext *a5,
        const unsigned __int16 *a6,
        struct tWAVEFORMATEX *Src,
        __int64 a8)
{
  struct tWAVEFORMATEX *v9; // r13
  const unsigned __int16 *v10; // rdi
  HRESULT v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  int v14; // eax
  HANDLE FileW; // rbx
  unsigned int v16; // edi
  size_t v17; // rsi
  GUID *v18; // r15
  __int64 v19; // rdx
  unsigned int v20; // r14d
  unsigned int v21; // r14d
  unsigned int v22; // r14d
  _WORD *v23; // rsi
  NTSTATUS v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  __int64 nBlockAlign; // r8
  int v28; // edi
  __int64 v29; // rdx
  int v30; // r8d
  int v31; // eax
  int v32; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  int ppvd; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+60h] [rbp-A0h] BYREF
  struct IMMDevice *v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h] BYREF
  GUID *v43; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v44; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v45[2]; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+98h] [rbp-68h] BYREF
  struct IAudioDgDriver *v47; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v48; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-50h]
  struct tWAVEFORMATEX *v50; // [rsp+B8h] [rbp-48h] BYREF
  int v51[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct IDspAudioEngine *v52; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v53[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v54; // [rsp+D4h] [rbp-2Ch]
  _WORD *v55; // [rsp+D8h] [rbp-28h]
  size_t Size; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF
  GUID v59; // [rsp+128h] [rbp+28h] BYREF
  int v60; // [rsp+138h] [rbp+38h]
  int v61; // [rsp+13Ch] [rbp+3Ch]
  void *v62; // [rsp+140h] [rbp+40h]
  unsigned int v63; // [rsp+148h] [rbp+48h]
  int v64; // [rsp+14Ch] [rbp+4Ch]
  __int64 v65; // [rsp+150h] [rbp+50h] BYREF
  int v66; // [rsp+158h] [rbp+58h]
  int v67; // [rsp+15Ch] [rbp+5Ch]
  _OWORD v68[4]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v69; // [rsp+1A0h] [rbp+A0h] BYREF
  int v70; // [rsp+1A8h] [rbp+A8h]
  char v71; // [rsp+1ACh] [rbp+ACh]
  __int128 v72; // [rsp+1ADh] [rbp+ADh]
  __int128 v73; // [rsp+1BDh] [rbp+BDh]
  __int128 v74; // [rsp+1CDh] [rbp+CDh]
  __int128 v75; // [rsp+1DDh] [rbp+DDh]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]
  const struct _tlgProvider_t *v77; // [rsp+258h] [rbp+158h] BYREF

  v77 = a2;
  v47 = a3;
  v9 = Src;
  v52 = a4;
  *(_QWORD *)v51 = a5;
  v10 = a6;
  v50 = Src;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(this + 9, a3);
  v46 = 2;
  v48 = 0;
  v11 = CoCreateInstance(
          &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
          0,
          0x17u,
          &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
          &v48);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v11,
      ppv);
LABEL_52:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    return (unsigned int)v12;
  }
  v40 = 0;
  v13 = *(_QWORD *)v48;
  v40 = 0;
  v14 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, struct IMMDevice **))(v13 + 40))(v48, v10, &v40);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v14,
      ppv);
LABEL_51:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    goto LABEL_52;
  }
  lpFileName = 0;
  v39 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpFileName,
    0);
  GetPathToKsFilter(v40, v9, (unsigned __int16 **)&lpFileName, &v39);
  if ( !lpFileName )
  {
    v12 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)0x80070490LL,
      ppv);
LABEL_50:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
    goto LABEL_51;
  }
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  v44 = FileW;
  v16 = v9->cbSize + 82;
  v17 = v16 + 72LL;
  Size = v17;
  v18 = (GUID *)operator new[](v17);
  v43 = v18;
  memset_0(v18, 0, v17);
  *v18 = GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
  *(_QWORD *)&v18[1].Data1 = 1;
  *(GUID *)((char *)v18 + 24) = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
  *(_QWORD *)v18[2].Data4 = 0;
  v18[3].Data1 = v39;
  *(_QWORD *)v18[3].Data4 = 0;
  v18[4].Data1 = 0x40000000;
  *(_DWORD *)&v18[4].Data2 = 0x40000000;
  *(_QWORD *)v18[4].Data4 = v16;
  *(_DWORD *)&v18[5].Data2 = 0;
  *(GUID *)((char *)v18 + 88) = GUID_73647561_0000_0010_8000_00aa00389b71;
  *(GUID *)((char *)v18 + 120) = GUID_05589f81_c356_11ce_bf01_00aa0055595a;
  memcpy_0(v18[8].Data4, v9, v9->cbSize + 18LL);
  if ( v9->wFormatTag == 0xFFFE )
  {
    *(GUID *)((char *)v18 + 104) = *(GUID *)((char *)&v9[1].nSamplesPerSec + 2);
  }
  else
  {
    *(GUID *)((char *)v18 + 104) = GUID_00000000_0000_0010_8000_00aa00389b71;
    *(_DWORD *)v18[6].Data4 = v9->wFormatTag;
  }
  v45[0] = 0;
  if ( (int)LongLongToUInt(76, v45) < 0 )
  {
    v19 = 308;
LABEL_48:
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)0x80070057LL,
      ppva);
    goto LABEL_49;
  }
  if ( v45[0] >= 0xFFFFFFFE )
  {
    v19 = 309;
    goto LABEL_48;
  }
  v20 = v16 + 72 + v45[0] + 2;
  if ( v20 < v16 + 72 )
  {
    v19 = 310;
    goto LABEL_48;
  }
  v21 = v20 + 1;
  if ( !v21 )
  {
    v19 = 315;
    goto LABEL_48;
  }
  v22 = v21 & 0xFFFFFFFE;
  if ( v22 > 0xFFFF )
  {
    v19 = 328;
    goto LABEL_48;
  }
  v23 = operator new[](v22);
  *(_QWORD *)v45 = v23;
  memset_0(v23, 0, v22);
  _o_wcscpy_s(v23, v22, L"{146F1A80-4791-11D0-A5D6-28DB04C10000}");
  v23[38] = 92;
  memcpy_0(v23 + 39, v18, Size);
  v54 = 0;
  v55 = v23;
  v53[0] = v22;
  v53[1] = v22;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = FileW;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v53;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 10,
    0);
  v24 = NtCreateFile(this + 10, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, 0x60u, 0, 0);
  if ( v24 < 0 )
  {
    v12 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x175,
            (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
            (const char *)(unsigned int)v24,
            ppvb);
LABEL_19:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v45);
LABEL_49:
    std::unique_ptr<KSPIN_CONNECT>::~unique_ptr<KSPIN_CONNECT>(&v43);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
    goto LABEL_50;
  }
  v41 = 0;
  v25 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))v40->lpVtbl->QueryInterface)(
          v40,
          &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
          &v41);
  v12 = v25;
  if ( v25 < 0 )
  {
    v26 = 376;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v25,
      ppvb);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    goto LABEL_19;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 24LL))(v41, &v46);
  v12 = v25;
  if ( v25 < 0 )
  {
    v26 = 377;
    goto LABEL_22;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v45);
  std::unique_ptr<KSPIN_CONNECT>::~unique_ptr<KSPIN_CONNECT>(&v43);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v44);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  nBlockAlign = v9->nBlockAlign;
  v39 = 0;
  v28 = a8;
  v12 = LongLongToUInt(
          nBlockAlign
        * (unsigned int)(int)((double)(int)(v9->nAvgBytesPerSec / (unsigned int)nBlockAlign)
                            * (double)(int)a8
                            / 10000000.0
                            + 0.5),
          &v39);
  if ( v12 >= 0 )
  {
    v12 = LongLongToUInt(2LL * v39, &v39);
    if ( v12 < 0 )
    {
      v29 = 385;
      goto LABEL_27;
    }
    v59 = GUID_3c58e72b_cb3c_4076_93e8_9c528830f2d2;
    v60 = 4;
    v61 = 1;
    v62 = this[10];
    v63 = v39;
    v64 = 0;
    memset_0(&v69, 0, 0x4Du);
    v49 = 0;
    ppvb = 77;
    v12 = (*(__int64 (__fastcall **)(struct IAudioDgDriver *, GUID *, __int64, __int64 *))(*(_QWORD *)v47 + 40LL))(
            v47,
            &v59,
            40,
            &v69);
    if ( v12 < 0 )
    {
      v29 = 396;
      goto LABEL_27;
    }
    if ( v49 < 0x4D )
    {
      v12 = -2147418113;
      v29 = 397;
      goto LABEL_27;
    }
    v65 = v69;
    v66 = v70;
    if ( v71 )
      v28 = 0;
    v67 = v28;
    memset_0(v68, 0, sizeof(v68));
    v68[0] = v72;
    v68[1] = v73;
    v68[2] = v74;
    v68[3] = v75;
    if ( v46 )
    {
      if ( v46 != 1 )
        return 0;
      v47 = (struct IAudioDgDriver *)&v65;
      v41 = 0;
      v32 = Microsoft::WRL::Details::MakeAndInitialize<CDspAudioEngineAudioInputEndpoint,CDspAudioEngineAudioInputEndpoint,_tlgProvider_t const * &,IAudioDgDriver * &,IDspAudioEngine * &,IDspAudioPumpContext * &,AUDIO_ENDPOINT_PROPERTIES *,tWAVEFORMATEX * &,__int64 &>(
              (unsigned int)&v41,
              (unsigned int)&v77,
              v30,
              (unsigned int)&v52,
              (__int64)v51,
              (__int64)&v47,
              (__int64)&v50,
              (__int64)&a8);
      v12 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
          (const char *)(unsigned int)v32,
          ppvd);
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v41);
        return (unsigned int)v12;
      }
    }
    else
    {
      v47 = (struct IAudioDgDriver *)&v65;
      v41 = 0;
      v31 = Microsoft::WRL::Details::MakeAndInitialize<CDspAudioEngineAudioOutputEndpoint,CDspAudioEngineAudioOutputEndpoint,_tlgProvider_t const * &,IAudioDgDriver * &,IDspAudioEngine * &,IDspAudioPumpContext * &,AUDIO_ENDPOINT_PROPERTIES *,tWAVEFORMATEX * &,__int64 &>(
              (unsigned int)&v41,
              (unsigned int)&v77,
              v30,
              (unsigned int)&v52,
              (__int64)v51,
              (__int64)&v47,
              (__int64)&v50,
              (__int64)&a8);
      v12 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19C,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
          (const char *)(unsigned int)v31,
          ppvc);
        wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v41);
        return (unsigned int)v12;
      }
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(this + 8, v41);
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v41);
    return 0;
  }
  v29 = 384;
LABEL_27:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v29,
    (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
    (const char *)(unsigned int)v12,
    ppvb);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140095494  mov     [rsp-8+arg_8], rdx
0x140095499  push    rbp
0x14009549a  push    rbx
0x14009549b  push    rsi
0x14009549c  push    rdi
0x14009549d  push    r12
0x14009549f  push    r13
0x1400954a1  push    r14
0x1400954a3  push    r15
0x1400954a5  lea     rbp, [rsp-108h]
0x1400954ad  sub     rsp, 208h
0x1400954b4  mov     rax, cs:__security_cookie
0x1400954bb  xor     rax, rsp
0x1400954be  mov     [rbp+140h+var_50], rax
0x1400954c5  mov     [rbp+140h+var_1A0], r8
0x1400954c9  mov     r12, rcx
0x1400954cc  mov     r13, [rbp+140h+Src]
0x1400954d3  mov     [rbp+140h+var_178], r9
0x1400954d7  mov     rax, [rbp+140h+arg_20]
0x1400954de  mov     qword ptr [rbp+140h+var_180], rax
0x1400954e2  mov     rdi, [rbp+140h+arg_28]
0x1400954e9  mov     [rbp+140h+var_188], r13
0x1400954ed  add     rcx, 48h ; 'H'
0x1400954f1  mov     rdx, r8
0x1400954f4  call    ??4?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIUnknown@@@Z; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::operator=(IUnknown *)
0x1400954f9  mov     [rbp+140h+var_1A8], 2
0x140095500  xor     r14d, r14d
0x140095503  mov     [rbp+140h+var_198], r14
0x140095507  lea     rax, [rbp+140h+var_198]
0x14009550b  mov     [rsp+240h+ppv], rax; int
0x140095510  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x140095517  xor     edx, edx; pUnkOuter
0x140095519  lea     r8d, [r14+17h]; dwClsContext
0x14009551d  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x140095524  call    cs:__imp_CoCreateInstance
0x14009552a  mov     ebx, eax
0x14009552c  test    eax, eax
0x14009552e  jns     short loc_140095550
0x140095530  mov     rcx, [rbp+148h]; this
0x140095537  mov     r9d, eax; char *
0x14009553a  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140095541  mov     edx, 0ECh; void *
0x140095546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009554b  jmp     loc_140095C47
0x140095550  mov     [rsp+240h+var_1D8], r14
0x140095555  mov     rcx, [rbp+140h+var_198]
0x140095559  mov     rax, [rcx]
0x14009555c  mov     [rsp+240h+var_1D8], r14
0x140095561  lea     r8, [rsp+240h+var_1D8]
0x140095566  mov     rdx, rdi
0x140095569  mov     rax, [rax+28h]
0x14009556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095572  mov     ebx, eax
0x140095574  test    eax, eax
0x140095576  jns     short loc_140095598
0x140095578  mov     rcx, [rbp+148h]; this
0x14009557f  mov     r9d, eax; char *
0x140095582  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140095589  mov     edx, 0EFh; void *
0x14009558e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140095593  jmp     loc_140095C3C
0x140095598  mov     [rsp+240h+lpFileName], r14
0x14009559d  mov     [rsp+240h+var_1E0], r14d
0x1400955a2  xor     edx, edx
0x1400955a4  lea     rcx, [rsp+240h+lpFileName]
0x1400955a9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400955ae  lea     r9, [rsp+240h+var_1E0]; unsigned int *
0x1400955b3  lea     r8, [rsp+240h+lpFileName]; unsigned __int16 **
0x1400955b8  mov     rdx, r13; struct tWAVEFORMATEX *
0x1400955bb  mov     rcx, [rsp+240h+var_1D8]; struct IMMDevice *
0x1400955c0  call    ?GetPathToKsFilter@@YAXPEAUIMMDevice@@PEBUtWAVEFORMATEX@@PEAPEAGPEAI@Z; GetPathToKsFilter(IMMDevice *,tWAVEFORMATEX const *,ushort * *,uint *)
0x1400955c5  mov     rcx, [rsp+240h+lpFileName]; lpFileName
0x1400955ca  test    rcx, rcx
0x1400955cd  jnz     short loc_1400955F4
0x1400955cf  mov     rcx, [rbp+148h]; this
0x1400955d6  mov     ebx, 80070490h
0x1400955db  mov     r9d, ebx; char *
0x1400955de  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x1400955e5  mov     edx, 0F4h; void *
0x1400955ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400955ef  jmp     loc_140095C31
0x1400955f4  mov     [rsp+240h+hTemplateFile], r14; hTemplateFile
0x1400955f9  mov     [rsp+240h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x140095601  mov     dword ptr [rsp+240h+ppv], 3; int
0x140095609  xor     r9d, r9d; lpSecurityAttributes
0x14009560c  xor     r8d, r8d; dwShareMode
0x14009560f  mov     edx, 0C0000000h; dwDesiredAccess
0x140095614  call    cs:__imp_CreateFileW
0x14009561a  mov     rbx, rax
0x14009561d  mov     [rbp+140h+var_1B8], rax
0x140095621  movzx   edi, word ptr [r13+10h]
0x140095626  add     edi, 52h ; 'R'
0x140095629  mov     esi, edi
0x14009562b  add     rsi, 48h ; 'H'
0x14009562f  mov     [rbp+140h+Size], rsi
0x140095633  mov     rcx, rsi; unsigned __int64
0x140095636  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14009563b  mov     r15, rax
0x14009563e  mov     [rbp+140h+var_1C0], rax
0x140095642  mov     r8, rsi; Size
0x140095645  xor     edx, edx; Val
0x140095647  mov     rcx, rax; void *
0x14009564a  call    memset_0
0x14009564f  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x140095656  movdqu  xmmword ptr [r15], xmm0
0x14009565b  mov     qword ptr [r15+10h], 1
0x140095663  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x14009566a  movdqu  xmmword ptr [r15+18h], xmm0
0x140095670  mov     [r15+28h], r14
0x140095674  mov     eax, [rsp+240h+var_1E0]
0x140095678  mov     [r15+30h], eax
0x14009567c  mov     [r15+38h], r14
0x140095680  mov     eax, 40000000h
0x140095685  mov     [r15+40h], eax
0x140095689  mov     [r15+44h], eax
0x14009568d  mov     [r15+48h], edi
0x140095691  mov     [r15+4Ch], r14d
0x140095695  mov     [r15+54h], r14d
0x140095699  movups  xmm0, xmmword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data1
0x1400956a0  movdqu  xmmword ptr [r15+58h], xmm0
0x1400956a6  movups  xmm1, xmmword ptr cs:_GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data1
0x1400956ad  movdqu  xmmword ptr [r15+78h], xmm1
0x1400956b3  movzx   r8d, word ptr [r13+10h]
0x1400956b8  add     r8, 12h; Size
0x1400956bc  lea     rcx, [r15+88h]; void *
0x1400956c3  mov     rdx, r13; Src
0x1400956c6  call    memcpy_0
0x1400956cb  mov     eax, 0FFFEh
0x1400956d0  cmp     [r13+0], ax
0x1400956d5  jnz     short loc_1400956E4
0x1400956d7  movups  xmm0, xmmword ptr [r13+18h]
0x1400956dc  movdqu  xmmword ptr [r15+68h], xmm0
0x1400956e2  jmp     short loc_1400956FA
0x1400956e4  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x1400956eb  movdqu  xmmword ptr [r15+68h], xmm0
0x1400956f1  movzx   eax, word ptr [r13+0]
0x1400956f6  mov     [r15+68h], eax
0x1400956fa  mov     [rbp+140h+var_1B0], r14d
0x1400956fe  lea     rdx, [rbp+140h+var_1B0]; unsigned int *
0x140095702  mov     ecx, 4Ch ; 'L'; __int64
0x140095707  call    ?LongLongToUInt@@YAJ_JPEAI@Z; LongLongToUInt(__int64,uint *)
0x14009570c  test    eax, eax
0x14009570e  jns     short loc_14009571A
0x140095710  mov     edx, 134h
0x140095715  jmp     loc_140095C01
0x14009571a  mov     ecx, [rbp+140h+var_1B0]
0x14009571d  add     ecx, 2
0x140095720  cmp     ecx, 2
0x140095723  jb      loc_140095BFC
0x140095729  lea     eax, [rdi+48h]
0x14009572c  lea     r14d, [rax+rcx]
0x140095730  cmp     r14d, eax
0x140095733  jb      loc_140095BF5
0x140095739  inc     r14d
0x14009573c  cmp     r14d, 1
0x140095740  jb      loc_140095BEE
0x140095746  and     r14d, 0FFFFFFFEh
0x14009574a  cmp     r14d, 0FFFFh
0x140095751  jbe     short loc_14009575D
0x140095753  mov     edx, 148h
0x140095758  jmp     loc_140095C01
0x14009575d  mov     ecx, r14d; unsigned __int64
0x140095760  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140095765  mov     rsi, rax
0x140095768  mov     qword ptr [rbp+140h+var_1B0], rax
0x14009576c  mov     r8d, r14d; Size
0x14009576f  xor     edx, edx; Val
0x140095771  mov     rcx, rax; void *
0x140095774  call    memset_0
0x140095779  lea     r8, a146f1a80479111; "{146F1A80-4791-11D0-A5D6-28DB04C10000}"
0x140095780  mov     edx, r14d
0x140095783  mov     rcx, rsi
0x140095786  call    cs:__imp__o_wcscpy_s
0x14009578c  mov     word ptr [rsi+4Ch], 5Ch ; '\'
0x140095792  lea     rcx, [rsi+4Eh]; void *
0x140095796  mov     r8, [rbp+140h+Size]; Size
0x14009579a  mov     rdx, r15; Src
0x14009579d  call    memcpy_0
0x1400957a2  xor     r15d, r15d
0x1400957a5  mov     [rbp+140h+var_16C], r15d
0x1400957a9  mov     [rbp+140h+var_168], rsi
0x1400957ad  mov     [rbp+140h+var_170], r14w
0x1400957b2  mov     [rbp+140h+var_16E], r14w
0x1400957b7  mov     qword ptr [rbp+140h+ObjectAttributes.Length], 30h ; '0'
0x1400957bf  mov     qword ptr [rbp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x1400957c7  mov     [rbp+140h+ObjectAttributes.RootDirectory], rbx
0x1400957cb  lea     rax, [rbp+140h+var_170]
0x1400957cf  mov     [rbp+140h+ObjectAttributes.ObjectName], rax
0x1400957d3  xorps   xmm0, xmm0
0x1400957d6  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400957db  movups  xmmword ptr [rbp+140h+IoStatusBlock], xmm0
0x1400957df  lea     rsi, [r12+50h]
0x1400957e4  xor     edx, edx
0x1400957e6  mov     rcx, rsi
0x1400957e9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400957ee  mov     [rsp+240h+EaLength], r15d; EaLength
0x1400957f3  mov     [rsp+240h+EaBuffer], r15; EaBuffer
0x1400957f8  mov     [rsp+240h+CreateOptions], 60h ; '`'; CreateOptions
0x140095800  lea     r14d, [r15+1]
0x140095804  mov     [rsp+240h+CreateDisposition], r14d; CreateDisposition
0x140095809  mov     dword ptr [rsp+240h+hTemplateFile], r15d; ShareAccess
0x14009580e  mov     [rsp+240h+dwFlagsAndAttributes], 80h; FileAttributes
0x140095816  mov     [rsp+240h+ppv], r15; int
0x14009581b  lea     r9, [rbp+140h+IoStatusBlock]; IoStatusBlock
0x14009581f  lea     r8, [rbp+140h+ObjectAttributes]; ObjectAttributes
0x140095823  mov     edx, 0C0100000h; DesiredAccess
0x140095828  mov     rcx, rsi; FileHandle
0x14009582b  call    cs:__imp_NtCreateFile
0x140095831  test    eax, eax
0x140095833  jns     short loc_140095860
0x140095835  mov     rcx, [rbp+148h]; this
0x14009583c  mov     r9d, eax; char *
0x14009583f  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140095846  mov     edx, 175h; void *
0x14009584b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140095850  mov     ebx, eax
0x140095852  lea     rcx, [rbp+140h+var_1B0]
0x140095856  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x14009585b  jmp     loc_140095C1D
0x140095860  mov     [rsp+240h+var_1D0], r15
0x140095865  mov     rcx, [rsp+240h+var_1D8]
0x14009586a  mov     rax, [rcx]
0x14009586d  lea     r8, [rsp+240h+var_1D0]
0x140095872  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x140095879  mov     rax, [rax]
0x14009587c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095881  mov     ebx, eax
0x140095883  test    eax, eax
0x140095885  jns     short loc_1400958AF
0x140095887  mov     edx, 178h; void *
0x14009588c  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140095893  mov     r9d, eax; char *
0x140095896  mov     rcx, [rbp+148h]; this
0x14009589d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400958a2  nop
0x1400958a3  lea     rcx, [rsp+240h+var_1D0]
0x1400958a8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400958ad  jmp     short loc_140095852
0x1400958af  mov     rcx, [rsp+240h+var_1D0]
0x1400958b4  mov     rax, [rcx]
0x1400958b7  lea     rdx, [rbp+140h+var_1A8]
0x1400958bb  mov     rax, [rax+18h]
0x1400958bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400958c4  mov     ebx, eax
0x1400958c6  test    eax, eax
0x1400958c8  jns     short loc_1400958D1
0x1400958ca  mov     edx, 179h
0x1400958cf  jmp     short loc_14009588C
0x1400958d1  lea     rcx, [rsp+240h+var_1D0]
0x1400958d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400958db  nop
0x1400958dc  lea     rcx, [rbp+140h+var_1B0]
0x1400958e0  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1400958e5  nop
0x1400958e6  lea     rcx, [rbp+140h+var_1C0]
0x1400958ea  call    ??1?$unique_ptr@UKSPIN_CONNECT@@U?$default_delete@UKSPIN_CONNECT@@@std@@@std@@QEAA@XZ; std::unique_ptr<KSPIN_CONNECT>::~unique_ptr<KSPIN_CONNECT>(void)
0x1400958ef  nop
0x1400958f0  lea     rcx, [rbp+140h+var_1B8]
0x1400958f4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400958f9  nop
0x1400958fa  lea     rcx, [rsp+240h+lpFileName]
0x1400958ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140095904  nop
0x140095905  lea     rcx, [rsp+240h+var_1D8]
0x14009590a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14009590f  nop
0x140095910  lea     rcx, [rbp+140h+var_198]
0x140095914  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140095919  movzx   r8d, word ptr [r13+0Ch]
0x14009591e  mov     [rsp+240h+var_1E0], r15d
0x140095923  xor     edx, edx
0x140095925  mov     eax, [r13+8]
0x140095929  div     r8d
0x14009592c  mov     ecx, eax
0x14009592e  xorps   xmm1, xmm1
0x140095931  cvtsi2sd xmm1, rcx
0x140095936  mov     rdi, [rbp+140h+arg_38]
0x14009593d  xorps   xmm0, xmm0
0x140095940  cvtsi2sd xmm0, rdi
0x140095945  mulsd   xmm1, xmm0
0x140095949  divsd   xmm1, cs:__real@416312d000000000
0x140095951  addsd   xmm1, cs:__real@3fe0000000000000
0x140095959  cvttsd2si rcx, xmm1
0x14009595e  mov     ecx, ecx
0x140095960  imul    rcx, r8; __int64
0x140095964  lea     rdx, [rsp+240h+var_1E0]; unsigned int *
0x140095969  call    ?LongLongToUInt@@YAJ_JPEAI@Z; LongLongToUInt(__int64,uint *)
0x14009596e  mov     ebx, eax
0x140095970  test    eax, eax
0x140095972  jns     short loc_140095994
0x140095974  mov     edx, 180h; void *
0x140095979  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140095980  mov     r9d, ebx; char *
0x140095983  mov     rcx, [rbp+148h]; this
0x14009598a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14009598f  jmp     loc_140095C50
0x140095994  mov     ecx, [rsp+240h+var_1E0]
0x140095998  add     rcx, rcx; __int64
0x14009599b  lea     rdx, [rsp+240h+var_1E0]; unsigned int *
0x1400959a0  call    ?LongLongToUInt@@YAJ_JPEAI@Z; LongLongToUInt(__int64,uint *)
  ... truncated ...
```
