# GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)

- ea: `0x180037c60`
- end: `0x180037fc7`
- name: `?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(struct IMMDeviceEnumerator *, struct IPropertyStore *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *, struct tWAVEFORMATEX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800170ac`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x180026500`
- `0x180036f80`
- `0x180037c60`
- `0x180037fd0`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037d69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037f94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037fa1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037d69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037f94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037fa1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetProposedConnectorFormatForProcessingMode(
        struct IMMDeviceEnumerator *a1,
        struct IPropertyStore *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        struct _GUID *a4,
        struct tWAVEFORMATEX **a5)
{
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  struct IMMDeviceEnumeratorVtbl *lpVtbl; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  void *v20; // rcx
  int v21; // eax
  void *v22; // rcx
  int v24; // [rsp+20h] [rbp-B1h]
  int v25[2]; // [rsp+30h] [rbp-A1h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-91h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-89h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-81h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v31; // [rsp+68h] [rbp-69h]
  LPVOID *p_pv; // [rsp+70h] [rbp-61h] BYREF
  __int64 v33; // [rsp+78h] [rbp-59h] BYREF
  char v34; // [rsp+80h] [rbp-51h]
  PROPVARIANT v35[2]; // [rsp+88h] [rbp-49h] BYREF
  __int64 v36; // [rsp+98h] [rbp-39h]
  __int128 v37; // [rsp+A0h] [rbp-31h] BYREF
  _DWORD v38[6]; // [rsp+B0h] [rbp-21h] BYREF
  _DWORD v39[6]; // [rsp+C8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  *a5 = 0;
  v38[0] = 590439624;
  v38[1] = 1283267372;
  v38[2] = 1907779772;
  v38[3] = 1730509416;
  v38[4] = 1;
  v39[0] = -1702713381;
  v39[1] = 1102331579;
  v39[2] = -1223116157;
  v39[3] = -65530063;
  v39[4] = 1;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, _DWORD *, PROPVARIANT *))a2->lpVtbl->GetValue)(a2, v38, v35);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x415,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v8,
      v24);
    goto LABEL_26;
  }
  *(_OWORD *)pvar = 0;
  v31 = 0;
  v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, _DWORD *, PROPVARIANT *))a2->lpVtbl->GetValue)(a2, v39, pvar);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v10,
      v24);
LABEL_5:
    PropVariantClear(pvar);
    goto LABEL_26;
  }
  lpVtbl = a1->lpVtbl;
  v26 = 0;
  v12 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))lpVtbl->GetDevice)(
          a1,
          v35[1],
          &v26);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41B,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v12,
      v24);
LABEL_8:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
    goto LABEL_5;
  }
  *(_QWORD *)v25 = 0;
  v13 = *v26;
  *(_QWORD *)v25 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v13 + 24))(
          v26,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          23);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41E,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v14,
      (int)v25);
LABEL_11:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v25);
    goto LABEL_8;
  }
  v28 = 0;
  v15 = **(_QWORD **)v25;
  v28 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v15 + 56))(*(_QWORD *)v25, LODWORD(pvar[1]), &v28);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x421,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v16,
      (int)v25);
LABEL_14:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
    goto LABEL_11;
  }
  v29 = 0;
  v17 = *v28;
  v29 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v17 + 104))(
          v28,
          23,
          &GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81,
          &v29);
  v9 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x424,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v18,
      (int)v25);
LABEL_17:
    wil::com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>::~com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>((__int64 *)&v29);
    goto LABEL_14;
  }
  pv = 0;
  v19 = *v29;
  p_pv = &pv;
  v33 = 0;
  v34 = 1;
  v37 = (__int128)*a4;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v19 + 24))(v29, &v37, &v33);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v9 < 0 )
  {
LABEL_19:
    v20 = pv;
    pv = 0;
    if ( v20 )
      CoTaskMemFree(v20);
    goto LABEL_17;
  }
  v21 = CloneWaveFormat((const struct tWAVEFORMATEX *)((char *)pv + 64), a5);
  v9 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v21,
      (int)v25);
    goto LABEL_19;
  }
  v22 = pv;
  pv = 0;
  if ( v22 )
    CoTaskMemFree(v22);
  wil::com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>::~com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>((__int64 *)&v29);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v26);
  PropVariantClear(pvar);
  v9 = 0;
LABEL_26:
  PropVariantClear(v35);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037c60  push    rbp
0x180037c62  push    rbx
0x180037c63  push    rsi
0x180037c64  push    rdi
0x180037c65  push    r12
0x180037c67  push    r14
0x180037c69  push    r15
0x180037c6b  lea     rbp, [rsp-1Fh]
0x180037c70  sub     rsp, 0F0h
0x180037c77  mov     rax, cs:__security_cookie
0x180037c7e  xor     rax, rsp
0x180037c81  mov     [rbp+4Fh+var_40], rax
0x180037c85  mov     r15, r9
0x180037c88  mov     rdi, rdx
0x180037c8b  mov     rsi, rcx
0x180037c8e  mov     r14, [rbp+4Fh+arg_20]
0x180037c92  xor     r12d, r12d
0x180037c95  mov     [r14], r12
0x180037c98  mov     [rbp+4Fh+var_70], 233164C8h
0x180037c9f  mov     [rbp+4Fh+var_6C], 4C7D1B2Ch
0x180037ca6  mov     [rbp+4Fh+var_68], 71B668BCh
0x180037cad  mov     [rbp+4Fh+var_64], 67257A68h
0x180037cb4  lea     ecx, [r12+1]
0x180037cb9  mov     [rbp+4Fh+var_60], ecx
0x180037cbc  mov     [rbp+4Fh+var_58], 9A82A7DBh
0x180037cc3  mov     [rbp+4Fh+var_54], 41B43EBBh
0x180037cca  mov     [rbp+4Fh+var_50], 0B718BA83h
0x180037cd1  mov     [rbp+4Fh+var_4C], 0FC181731h
0x180037cd8  mov     [rbp+4Fh+var_48], ecx
0x180037cdb  xorps   xmm0, xmm0
0x180037cde  xor     eax, eax
0x180037ce0  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180037ce4  mov     [rbp+4Fh+var_88], rax
0x180037ce8  mov     rax, [rdx]
0x180037ceb  lea     r8, [rbp+4Fh+var_98]
0x180037cef  lea     rdx, [rbp+4Fh+var_70]
0x180037cf3  mov     rcx, rdi
0x180037cf6  mov     rax, [rax+28h]
0x180037cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cff  mov     ebx, eax
0x180037d01  test    eax, eax
0x180037d03  jns     short loc_180037D22
0x180037d05  mov     rcx, [rbp+57h]; this
0x180037d09  mov     r9d, eax; char *
0x180037d0c  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037d13  mov     edx, 415h; void *
0x180037d18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d1d  jmp     loc_180037F9D
0x180037d22  xorps   xmm0, xmm0
0x180037d25  xor     eax, eax
0x180037d27  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180037d2b  mov     [rbp+4Fh+var_B8], rax
0x180037d2f  mov     rax, [rdi]
0x180037d32  lea     r8, [rbp+4Fh+pvar]
0x180037d36  lea     rdx, [rbp+4Fh+var_58]
0x180037d3a  mov     rcx, rdi
0x180037d3d  mov     rax, [rax+28h]
0x180037d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d46  mov     ebx, eax
0x180037d48  test    eax, eax
0x180037d4a  jns     short loc_180037D74
0x180037d4c  mov     rcx, [rbp+57h]; this
0x180037d50  mov     r9d, eax; char *
0x180037d53  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037d5a  mov     edx, 418h; void *
0x180037d5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037d64  nop
0x180037d65  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180037d69  call    cs:__imp_PropVariantClear
0x180037d6f  jmp     loc_180037F9D
0x180037d74  mov     rax, [rsi]
0x180037d77  mov     [rsp+120h+var_E8], r12
0x180037d7c  lea     r8, [rsp+120h+var_E8]
0x180037d81  mov     rdx, [rbp+4Fh+var_98+8]
0x180037d85  mov     rcx, rsi
0x180037d88  mov     rax, [rax+28h]
0x180037d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d91  mov     ebx, eax
0x180037d93  test    eax, eax
0x180037d95  jns     short loc_180037DBC
0x180037d97  mov     rcx, [rbp+57h]; this
0x180037d9b  mov     r9d, eax; char *
0x180037d9e  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037da5  mov     edx, 41Bh; void *
0x180037daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037daf  nop
0x180037db0  lea     rcx, [rsp+120h+var_E8]
0x180037db5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037dba  jmp     short loc_180037D65
0x180037dbc  mov     qword ptr [rsp+120h+var_F0], r12
0x180037dc1  mov     rcx, [rsp+120h+var_E8]
0x180037dc6  mov     rax, [rcx]
0x180037dc9  mov     qword ptr [rsp+120h+var_F0], r12
0x180037dce  lea     rdx, [rsp+120h+var_F0]
0x180037dd3  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180037dd8  xor     r9d, r9d
0x180037ddb  lea     r8d, [r9+17h]
0x180037ddf  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180037de6  mov     rax, [rax+18h]
0x180037dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037def  mov     ebx, eax
0x180037df1  test    eax, eax
0x180037df3  jns     short loc_180037E1A
0x180037df5  mov     rcx, [rbp+57h]; this
0x180037df9  mov     r9d, eax; char *
0x180037dfc  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037e03  mov     edx, 41Eh; void *
0x180037e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e0d  nop
0x180037e0e  lea     rcx, [rsp+120h+var_F0]
0x180037e13  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037e18  jmp     short loc_180037DB0
0x180037e1a  mov     [rsp+120h+var_D8], r12
0x180037e1f  mov     rcx, qword ptr [rsp+120h+var_F0]
0x180037e24  mov     rax, [rcx]
0x180037e27  mov     [rsp+120h+var_D8], r12
0x180037e2c  lea     r8, [rsp+120h+var_D8]
0x180037e31  mov     edx, dword ptr [rbp+4Fh+pvar+8]
0x180037e34  mov     rax, [rax+38h]
0x180037e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e3d  mov     ebx, eax
0x180037e3f  test    eax, eax
0x180037e41  jns     short loc_180037E68
0x180037e43  mov     rcx, [rbp+57h]; this
0x180037e47  mov     r9d, eax; char *
0x180037e4a  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037e51  mov     edx, 421h; void *
0x180037e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e5b  nop
0x180037e5c  lea     rcx, [rsp+120h+var_D8]
0x180037e61  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037e66  jmp     short loc_180037E0E
0x180037e68  mov     [rsp+120h+var_D0], r12
0x180037e6d  mov     rcx, [rsp+120h+var_D8]
0x180037e72  mov     rax, [rcx]
0x180037e75  mov     [rsp+120h+var_D0], r12
0x180037e7a  lea     r9, [rsp+120h+var_D0]
0x180037e7f  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x180037e86  mov     edx, 17h
0x180037e8b  mov     rax, [rax+68h]
0x180037e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e94  mov     ebx, eax
0x180037e96  test    eax, eax
0x180037e98  jns     short loc_180037EBF
0x180037e9a  mov     rcx, [rbp+57h]; this
0x180037e9e  mov     r9d, eax; char *
0x180037ea1  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037ea8  mov     edx, 424h; void *
0x180037ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037eb2  nop
0x180037eb3  lea     rcx, [rsp+120h+var_D0]
0x180037eb8  call    ??1?$com_ptr_t@UIKsGetProposedFormat@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>::~com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>(void)
0x180037ebd  jmp     short loc_180037E5C
0x180037ebf  mov     [rsp+120h+pv], r12
0x180037ec4  mov     rcx, [rsp+120h+var_D0]
0x180037ec9  mov     rax, [rcx]
0x180037ecc  lea     rdx, [rsp+120h+pv]
0x180037ed1  mov     [rbp+4Fh+var_B0], rdx
0x180037ed5  mov     [rbp+4Fh+var_A8], r12
0x180037ed9  mov     [rbp+4Fh+var_A0], 1
0x180037edd  movaps  xmm0, xmmword ptr [r15]
0x180037ee1  movdqa  [rbp+4Fh+var_80], xmm0
0x180037ee6  lea     r8, [rbp+4Fh+var_A8]
0x180037eea  lea     rdx, [rbp+4Fh+var_80]
0x180037eee  mov     rax, [rax+18h]
0x180037ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ef7  mov     ebx, eax
0x180037ef9  lea     rcx, [rbp+4Fh+var_B0]
0x180037efd  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180037f02  test    ebx, ebx
0x180037f04  jns     short loc_180037F1D
0x180037f06  mov     rcx, [rsp+120h+pv]; pv
0x180037f0b  mov     [rsp+120h+pv], r12
0x180037f10  test    rcx, rcx
0x180037f13  jz      short loc_180037EB3
0x180037f15  call    cs:__imp_CoTaskMemFree
0x180037f1b  jmp     short loc_180037EB3
0x180037f1d  mov     rcx, [rsp+120h+pv]
0x180037f22  add     rcx, 40h ; '@'; Src
0x180037f26  mov     rdx, r14; struct tWAVEFORMATEX **
0x180037f29  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180037f2e  mov     ebx, eax
0x180037f30  test    eax, eax
0x180037f32  jns     short loc_180037F4E
0x180037f34  mov     rcx, [rbp+57h]; this
0x180037f38  mov     r9d, eax; char *
0x180037f3b  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180037f42  mov     edx, 42Bh; void *
0x180037f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f4c  jmp     short loc_180037F06
0x180037f4e  mov     rcx, [rsp+120h+pv]; pv
0x180037f53  mov     [rsp+120h+pv], r12
0x180037f58  test    rcx, rcx
0x180037f5b  jz      short loc_180037F64
0x180037f5d  call    cs:__imp_CoTaskMemFree
0x180037f63  nop
0x180037f64  lea     rcx, [rsp+120h+var_D0]
0x180037f69  call    ??1?$com_ptr_t@UIKsGetProposedFormat@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>::~com_ptr_t<IKsGetProposedFormat,wil::err_returncode_policy>(void)
0x180037f6e  nop
0x180037f6f  lea     rcx, [rsp+120h+var_D8]
0x180037f74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037f79  nop
0x180037f7a  lea     rcx, [rsp+120h+var_F0]
0x180037f7f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037f84  nop
0x180037f85  lea     rcx, [rsp+120h+var_E8]
0x180037f8a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180037f8f  nop
0x180037f90  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180037f94  call    cs:__imp_PropVariantClear
0x180037f9a  mov     ebx, r12d
0x180037f9d  lea     rcx, [rbp+4Fh+var_98]; pvar
0x180037fa1  call    cs:__imp_PropVariantClear
0x180037fa7  mov     eax, ebx
0x180037fa9  mov     rcx, [rbp+4Fh+var_40]
0x180037fad  xor     rcx, rsp; StackCookie
0x180037fb0  call    __security_check_cookie
0x180037fb5  add     rsp, 0F0h
0x180037fbc  pop     r15
0x180037fbe  pop     r14
0x180037fc0  pop     r12
0x180037fc2  pop     rdi
0x180037fc3  pop     rsi
0x180037fc4  pop     rbx
0x180037fc5  pop     rbp
0x180037fc6  retn
```
