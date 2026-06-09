# GetHostUsingEndpointUtility(IMMDevice *,tWAVEFORMATEX const *,int,ushort * *,uint *)

- ea: `0x140052b74`
- end: `0x140052e3b`
- name: `?GetHostUsingEndpointUtility@@YAJPEAUIMMDevice@@PEBUtWAVEFORMATEX@@HPEAPEAGPEAI@Z`
- size: `711`
- prototype: `int(struct IMMDevice *, const struct tWAVEFORMATEX *, int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140095090`

## callees

- `0x1400079f0`
- `0x140008124`
- `0x14000c33c`
- `0x140016f68`
- `0x14001d76c`
- `0x140031a68`
- `0x1400516e8`
- `0x140052b74`
- `0x14005a654`
- `0x1400709e4`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052e23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052bed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052e23`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetHostUsingEndpointUtility(
        struct IMMDevice *a1,
        const struct tWAVEFORMATEX *a2,
        unsigned int a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  int v8; // ebx
  void *v9; // rcx
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 **); // rbx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  void *v22; // rcx
  int v23; // [rsp+20h] [rbp-51h]
  LPVOID pv; // [rsp+40h] [rbp-31h] BYREF
  __int64 v25; // [rsp+48h] [rbp-29h] BYREF
  __int64 *v26; // [rsp+50h] [rbp-21h] BYREF
  int v27[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 *v28; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-9h] BYREF
  void *p_pv; // [rsp+70h] [rbp-1h] BYREF
  struct KSDATAFORMAT_WAVEFORMATEX *v31; // [rsp+78h] [rbp+7h] BYREF
  char v32; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  pv = 0;
  p_pv = &pv;
  v31 = 0;
  v32 = 1;
  v8 = CreateKSFormatFromWFXFormat(a2, &v31);
  wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v8,
      v23);
LABEL_3:
    v9 = pv;
    pv = 0;
    if ( v9 )
      CoTaskMemFree(v9);
    return (unsigned int)v8;
  }
  lpVtbl = a1->lpVtbl;
  *(_QWORD *)v27 = 0;
  v12 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))lpVtbl->Activate)(
          a1,
          &GUID_2b0711de_dab7_4610_a16f_d3383749b220,
          23);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v12,
      (int)v27);
LABEL_8:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v27);
    goto LABEL_3;
  }
  v26 = 0;
  v13 = **(_QWORD **)v27;
  v26 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, _QWORD, _QWORD))(v13 + 88))(
          *(_QWORD *)v27,
          pv,
          *(unsigned int *)pv,
          a3);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v14,
      1);
LABEL_11:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    goto LABEL_8;
  }
  v25 = 0;
  v15 = *v26;
  v25 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v26, 0, &v25);
  if ( v8 < 0 )
  {
    v16 = 141;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v8,
      1);
LABEL_15:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    goto LABEL_11;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 32LL))(v25, a5);
  if ( v8 < 0 )
  {
    v16 = 144;
    goto LABEL_14;
  }
  *((_WORD *)a5 + 1) = 0;
  v28 = 0;
  v17 = v25;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v25 + 96LL);
  wil::com_ptr_t<ISpatialStreamNode,wil::err_returncode_policy>::reset(&v28);
  v19 = v18(v17, &v28);
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v19,
      1);
LABEL_20:
    wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v28);
    goto LABEL_15;
  }
  v29 = 0;
  v20 = *v28;
  p_pv = &v29;
  v31 = 0;
  v32 = 1;
  v8 = (*(__int64 (__fastcall **)(__int64 *, struct KSDATAFORMAT_WAVEFORMATEX **))(v20 + 64))(v28, &v31);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
  if ( v8 < 0 )
  {
    v21 = 155;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\dspoffload\\client\\dspaudioendpoint.cpp",
      (const char *)(unsigned int)v8,
      1);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
    goto LABEL_20;
  }
  v8 = KsFilterPathFromPnpDeviceId(v29, a4);
  if ( v8 < 0 )
  {
    v21 = 158;
    goto LABEL_23;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v27);
  v22 = pv;
  pv = 0;
  if ( v22 )
    CoTaskMemFree(v22);
  return 0;
}

```

## disassembly

```asm
0x140052b74  push    rbp
0x140052b76  push    rbx
0x140052b77  push    rsi
0x140052b78  push    rdi
0x140052b79  push    r14
0x140052b7b  push    r15
0x140052b7d  lea     rbp, [rsp-27h]
0x140052b82  sub     rsp, 98h
0x140052b89  mov     rsi, r9
0x140052b8c  mov     r14d, r8d
0x140052b8f  mov     rax, rdx
0x140052b92  mov     rdi, rcx
0x140052b95  xor     r15d, r15d
0x140052b98  mov     [rbp+4Fh+pv], r15
0x140052b9c  lea     rcx, [rbp+4Fh+pv]
0x140052ba0  mov     [rbp+4Fh+var_50], rcx
0x140052ba4  mov     [rbp+4Fh+var_48], r15
0x140052ba8  mov     [rbp+4Fh+var_40], 1
0x140052bac  lea     rdx, [rbp+4Fh+var_48]; struct KSDATAFORMAT_WAVEFORMATEX **
0x140052bb0  mov     rcx, rax; Src
0x140052bb3  call    ?CreateKSFormatFromWFXFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAUKSDATAFORMAT_WAVEFORMATEX@@@Z; CreateKSFormatFromWFXFormat(tWAVEFORMATEX const *,KSDATAFORMAT_WAVEFORMATEX * *)
0x140052bb8  mov     ebx, eax
0x140052bba  lea     rcx, [rbp+4Fh+var_50]
0x140052bbe  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x140052bc3  test    ebx, ebx
0x140052bc5  jns     short loc_140052BFA
0x140052bc7  mov     rcx, [rbp+57h]; this
0x140052bcb  mov     r9d, ebx; char *
0x140052bce  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052bd5  mov     edx, 82h; void *
0x140052bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052bdf  nop
0x140052be0  mov     rcx, [rbp+4Fh+pv]; pv
0x140052be4  mov     [rbp+4Fh+pv], r15
0x140052be8  test    rcx, rcx
0x140052beb  jz      short loc_140052BF3
0x140052bed  call    cs:__imp_CoTaskMemFree
0x140052bf3  mov     eax, ebx
0x140052bf5  jmp     loc_140052E2B
0x140052bfa  mov     rax, [rdi]
0x140052bfd  mov     qword ptr [rbp+4Fh+var_68], r15
0x140052c01  lea     rcx, [rbp+4Fh+var_68]
0x140052c05  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x140052c0a  xor     r9d, r9d
0x140052c0d  lea     r8d, [r9+17h]
0x140052c11  lea     rdx, _GUID_2b0711de_dab7_4610_a16f_d3383749b220
0x140052c18  mov     rcx, rdi
0x140052c1b  mov     rax, [rax+18h]
0x140052c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052c24  mov     ebx, eax
0x140052c26  test    eax, eax
0x140052c28  jns     short loc_140052C4E
0x140052c2a  mov     rcx, [rbp+57h]; this
0x140052c2e  mov     r9d, eax; char *
0x140052c31  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052c38  mov     edx, 85h; void *
0x140052c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052c42  nop
0x140052c43  lea     rcx, [rbp+4Fh+var_68]
0x140052c47  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052c4c  jmp     short loc_140052BE0
0x140052c4e  mov     [rbp+4Fh+var_70], r15
0x140052c52  mov     rcx, qword ptr [rbp+4Fh+var_68]
0x140052c56  mov     rax, [rcx]
0x140052c59  mov     [rbp+4Fh+var_70], r15
0x140052c5d  mov     rdx, [rbp+4Fh+pv]
0x140052c61  lea     r8, [rbp+4Fh+var_70]
0x140052c65  mov     [rsp+0C0h+var_98], r8
0x140052c6a  mov     [rsp+0C0h+var_A0], 1; int
0x140052c72  mov     r9d, r14d
0x140052c75  mov     r8d, [rdx]
0x140052c78  mov     rax, [rax+58h]
0x140052c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052c81  mov     ebx, eax
0x140052c83  test    eax, eax
0x140052c85  jns     short loc_140052CAB
0x140052c87  mov     rcx, [rbp+57h]; this
0x140052c8b  mov     r9d, eax; char *
0x140052c8e  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052c95  mov     edx, 89h; void *
0x140052c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052c9f  nop
0x140052ca0  lea     rcx, [rbp+4Fh+var_70]
0x140052ca4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052ca9  jmp     short loc_140052C43
0x140052cab  mov     [rbp+4Fh+var_78], r15
0x140052caf  mov     rcx, [rbp+4Fh+var_70]
0x140052cb3  mov     rax, [rcx]
0x140052cb6  mov     [rbp+4Fh+var_78], r15
0x140052cba  lea     r8, [rbp+4Fh+var_78]
0x140052cbe  xor     edx, edx
0x140052cc0  mov     rax, [rax+20h]
0x140052cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052cc9  mov     ebx, eax
0x140052ccb  test    eax, eax
0x140052ccd  jns     short loc_140052CF3
0x140052ccf  mov     edx, 8Dh; void *
0x140052cd4  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052cdb  mov     r9d, ebx; char *
0x140052cde  mov     rcx, [rbp+57h]; this
0x140052ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052ce7  nop
0x140052ce8  lea     rcx, [rbp+4Fh+var_78]
0x140052cec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052cf1  jmp     short loc_140052CA0
0x140052cf3  mov     rcx, [rbp+4Fh+var_78]
0x140052cf7  mov     rax, [rcx]
0x140052cfa  mov     rdi, [rbp+4Fh+arg_20]
0x140052cfe  mov     rdx, rdi
0x140052d01  mov     rax, [rax+20h]
0x140052d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d0a  mov     ebx, eax
0x140052d0c  test    eax, eax
0x140052d0e  jns     short loc_140052D17
0x140052d10  mov     edx, 90h
0x140052d15  jmp     short loc_140052CD4
0x140052d17  mov     [rdi+2], r15w
0x140052d1c  mov     [rbp+4Fh+var_60], r15
0x140052d20  mov     rdi, [rbp+4Fh+var_78]
0x140052d24  mov     rax, [rdi]
0x140052d27  mov     rbx, [rax+60h]
0x140052d2b  lea     rcx, [rbp+4Fh+var_60]
0x140052d2f  call    ?reset@?$com_ptr_t@UISpatialStreamNode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ISpatialStreamNode,wil::err_returncode_policy>::reset(void)
0x140052d34  lea     rdx, [rbp+4Fh+var_60]
0x140052d38  mov     rcx, rdi
0x140052d3b  mov     rax, rbx
0x140052d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d43  mov     ebx, eax
0x140052d45  test    eax, eax
0x140052d47  jns     short loc_140052D70
0x140052d49  mov     rcx, [rbp+57h]; this
0x140052d4d  mov     r9d, eax; char *
0x140052d50  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052d57  mov     edx, 97h; void *
0x140052d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052d61  nop
0x140052d62  lea     rcx, [rbp+4Fh+var_60]
0x140052d66  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140052d6b  jmp     loc_140052CE8
0x140052d70  mov     [rbp+4Fh+var_58], r15
0x140052d74  mov     rcx, [rbp+4Fh+var_60]
0x140052d78  mov     rax, [rcx]
0x140052d7b  lea     rdx, [rbp+4Fh+var_58]
0x140052d7f  mov     [rbp+4Fh+var_50], rdx
0x140052d83  mov     [rbp+4Fh+var_48], r15
0x140052d87  mov     [rbp+4Fh+var_40], 1
0x140052d8b  lea     rdx, [rbp+4Fh+var_48]
0x140052d8f  mov     rax, [rax+40h]
0x140052d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d98  mov     ebx, eax
0x140052d9a  lea     rcx, [rbp+4Fh+var_50]
0x140052d9e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x140052da3  test    ebx, ebx
0x140052da5  jns     short loc_140052DCB
0x140052da7  mov     edx, 9Bh; void *
0x140052dac  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\audiodg\\dsp"...
0x140052db3  mov     r9d, ebx; char *
0x140052db6  mov     rcx, [rbp+57h]; this
0x140052dba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140052dbf  nop
0x140052dc0  lea     rcx, [rbp+4Fh+var_58]
0x140052dc4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140052dc9  jmp     short loc_140052D62
0x140052dcb  mov     rdx, rsi; unsigned __int16 **
0x140052dce  mov     rcx, [rbp+4Fh+var_58]; unsigned __int16 *
0x140052dd2  call    ?KsFilterPathFromPnpDeviceId@@YAJPEBGPEAPEAG@Z; KsFilterPathFromPnpDeviceId(ushort const *,ushort * *)
0x140052dd7  mov     ebx, eax
0x140052dd9  test    eax, eax
0x140052ddb  jns     short loc_140052DE4
0x140052ddd  mov     edx, 9Eh
0x140052de2  jmp     short loc_140052DAC
0x140052de4  lea     rcx, [rbp+4Fh+var_58]
0x140052de8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140052ded  nop
0x140052dee  lea     rcx, [rbp+4Fh+var_60]
0x140052df2  call    ??1?$com_ptr_t@UIDspAudioEngine@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>::~com_ptr_t<IDspAudioEngine,wil::err_returncode_policy>(void)
0x140052df7  nop
0x140052df8  lea     rcx, [rbp+4Fh+var_78]
0x140052dfc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052e01  nop
0x140052e02  lea     rcx, [rbp+4Fh+var_70]
0x140052e06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052e0b  nop
0x140052e0c  lea     rcx, [rbp+4Fh+var_68]
0x140052e10  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140052e15  nop
0x140052e16  mov     rcx, [rbp+4Fh+pv]; pv
0x140052e1a  mov     [rbp+4Fh+pv], r15
0x140052e1e  test    rcx, rcx
0x140052e21  jz      short loc_140052E29
0x140052e23  call    cs:__imp_CoTaskMemFree
0x140052e29  xor     eax, eax
0x140052e2b  add     rsp, 98h
0x140052e32  pop     r15
0x140052e34  pop     r14
0x140052e36  pop     rdi
0x140052e37  pop     rsi
0x140052e38  pop     rbx
0x140052e39  pop     rbp
0x140052e3a  retn
```
