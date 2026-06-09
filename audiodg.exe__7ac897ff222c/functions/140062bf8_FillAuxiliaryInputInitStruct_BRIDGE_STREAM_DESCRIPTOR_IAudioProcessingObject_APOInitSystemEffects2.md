# FillAuxiliaryInputInitStruct(BRIDGE_STREAM_DESCRIPTOR *,IAudioProcessingObject *,APOInitSystemEffects2 &)

- ea: `0x140062bf8`
- end: `0x140062da5`
- name: `?FillAuxiliaryInputInitStruct@@YAJPEAUBRIDGE_STREAM_DESCRIPTOR@@PEAUIAudioProcessingObject@@AEAUAPOInitSystemEffects2@@@Z`
- size: `429`
- prototype: `int(struct BRIDGE_STREAM_DESCRIPTOR *, struct IAudioProcessingObject *, struct APOInitSystemEffects2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400585a8`

## callees

- `0x14000664c`
- `0x140008124`
- `0x14000c33c`
- `0x140031a68`
- `0x140062bf8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140062c3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140062c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140062d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140062d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140062d21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140062d73`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FillAuxiliaryInputInitStruct(
        struct BRIDGE_STREAM_DESCRIPTOR *a1,
        struct IAudioProcessingObject *a2,
        struct APOInitSystemEffects2 *a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  int v9; // eax
  struct IAudioProcessingObjectVtbl *lpVtbl; // rax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  void *v13; // rcx
  int v14; // eax
  void *v15; // rcx
  int ppv; // [rsp+20h] [rbp-40h]
  struct IMMDevice *v18; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v19; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v20; // [rsp+40h] [rbp-20h] BYREF
  char v21; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  LPVOID pv; // [rsp+98h] [rbp+38h] BYREF

  v19 = 0;
  v6 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v19);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoendpoint.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_15;
  }
  v18 = 0;
  v8 = *(_QWORD *)v19;
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMMDevice **))(v8 + 40))(v19, *((_QWORD *)a1 + 7), &v18);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoendpoint.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_5:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    goto LABEL_15;
  }
  pv = 0;
  lpVtbl = a2->lpVtbl;
  *(_QWORD *)&v20.Data1 = &pv;
  *(_QWORD *)v20.Data4 = 0;
  v21 = 1;
  v7 = ((__int64 (__fastcall *)(struct IAudioProcessingObject *, unsigned __int8 *))lpVtbl->GetRegistrationProperties)(
         a2,
         v20.Data4);
  wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v20);
  if ( v7 < 0 )
  {
    v11 = (unsigned int)v7;
    v12 = 33;
    goto LABEL_8;
  }
  v20 = (struct _GUID)*((_OWORD *)a1 + 2);
  v14 = FillAPOInitSystemEffectsStructure(
          v18,
          (struct _GUID *)pv,
          &v20,
          0,
          (enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)*((_DWORD *)a1 + 2),
          a3);
  v7 = v14;
  if ( v14 < 0 )
  {
    v11 = (unsigned int)v14;
    v12 = 35;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoendpoint.cpp",
      (const char *)v11,
      ppv);
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_5;
  }
  v15 = pv;
  pv = 0;
  if ( v15 )
    CoTaskMemFree(v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  v7 = 0;
LABEL_15:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140062bf8  mov     [rsp-18h+arg_0], rbx
0x140062bfd  mov     [rsp-18h+arg_8], rsi
0x140062c02  push    rbp
0x140062c03  push    rdi
0x140062c04  push    r14
0x140062c06  mov     rbp, rsp
0x140062c09  sub     rsp, 60h
0x140062c0d  mov     r14, r8
0x140062c10  mov     rsi, rdx
0x140062c13  mov     rdi, rcx
0x140062c16  mov     [rbp+var_28], 0
0x140062c1e  lea     rax, [rbp+var_28]
0x140062c22  mov     [rsp+60h+ppv], rax; int
0x140062c27  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x140062c2e  xor     edx, edx; pUnkOuter
0x140062c30  lea     r8d, [rdx+17h]; dwClsContext
0x140062c34  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x140062c3b  call    cs:__imp_CoCreateInstance
0x140062c41  mov     ebx, eax
0x140062c43  test    eax, eax
0x140062c45  jns     short loc_140062C64
0x140062c47  mov     rcx, [rbp+18h]; this
0x140062c4b  mov     r9d, eax; char *
0x140062c4e  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140062c55  mov     edx, 1Bh; void *
0x140062c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140062c5f  jmp     loc_140062D85
0x140062c64  mov     [rbp+var_30], 0
0x140062c6c  mov     rcx, [rbp+var_28]
0x140062c70  mov     rax, [rcx]
0x140062c73  mov     [rbp+var_30], 0
0x140062c7b  lea     r8, [rbp+var_30]
0x140062c7f  mov     rdx, [rdi+38h]
0x140062c83  mov     rax, [rax+28h]
0x140062c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062c8c  mov     ebx, eax
0x140062c8e  test    eax, eax
0x140062c90  jns     short loc_140062CB9
0x140062c92  mov     rcx, [rbp+18h]; this
0x140062c96  mov     r9d, eax; char *
0x140062c99  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140062ca0  mov     edx, 1Eh; void *
0x140062ca5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140062caa  nop
0x140062cab  lea     rcx, [rbp+var_30]
0x140062caf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140062cb4  jmp     loc_140062D85
0x140062cb9  mov     [rbp+pv], 0
0x140062cc1  mov     rax, [rsi]
0x140062cc4  lea     rcx, [rbp+pv]
0x140062cc8  mov     qword ptr [rbp+var_20.Data1], rcx
0x140062ccc  mov     qword ptr [rbp+var_20.Data4], 0
0x140062cd4  mov     [rbp+var_10], 1
0x140062cd8  lea     rdx, [rbp+var_20.Data4]
0x140062cdc  mov     rcx, rsi
0x140062cdf  mov     rax, [rax+28h]
0x140062ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062ce8  mov     ebx, eax
0x140062cea  lea     rcx, [rbp+var_20]
0x140062cee  call    ??1?$out_param_t@V?$unique_ptr@UAPO_REG_PROPERTIES@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<APO_REG_PROPERTIES,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x140062cf3  test    ebx, ebx
0x140062cf5  jns     short loc_140062D29
0x140062cf7  mov     r9d, ebx; char *
0x140062cfa  mov     edx, 21h ; '!'; void *
0x140062cff  lea     r8, aAvcoreAudiocor_35; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140062d06  mov     rcx, [rbp+18h]; this
0x140062d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140062d0f  nop
0x140062d10  mov     rcx, [rbp+pv]; pv
0x140062d14  mov     [rbp+pv], 0
0x140062d1c  test    rcx, rcx
0x140062d1f  jz      short loc_140062CAB
0x140062d21  call    cs:__imp_CoTaskMemFree
0x140062d27  jmp     short loc_140062CAB
0x140062d29  movups  xmm0, xmmword ptr [rdi+20h]
0x140062d2d  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x140062d32  mov     [rsp+60h+var_38], r14; struct APOInitSystemEffects2 *
0x140062d37  mov     eax, [rdi+8]
0x140062d3a  mov     dword ptr [rsp+60h+ppv], eax; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x140062d3e  xor     r9d, r9d; int
0x140062d41  lea     r8, [rbp+var_20]; struct _GUID *
0x140062d45  mov     rdx, [rbp+pv]; struct _GUID *
0x140062d49  mov     rcx, [rbp+var_30]; struct IMMDevice *
0x140062d4d  call    ?FillAPOInitSystemEffectsStructure@@YAJPEAUIMMDevice@@PEAU_GUID@@U2@HW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@AEAUAPOInitSystemEffects2@@@Z; FillAPOInitSystemEffectsStructure(IMMDevice *,_GUID *,_GUID,int,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,APOInitSystemEffects2 &)
0x140062d52  mov     ebx, eax
0x140062d54  test    eax, eax
0x140062d56  jns     short loc_140062D62
0x140062d58  mov     r9d, eax
0x140062d5b  mov     edx, 23h ; '#'
0x140062d60  jmp     short loc_140062CFF
0x140062d62  mov     rcx, [rbp+pv]; pv
0x140062d66  mov     [rbp+pv], 0
0x140062d6e  test    rcx, rcx
0x140062d71  jz      short loc_140062D7A
0x140062d73  call    cs:__imp_CoTaskMemFree
0x140062d79  nop
0x140062d7a  lea     rcx, [rbp+var_30]
0x140062d7e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140062d83  xor     ebx, ebx
0x140062d85  lea     rcx, [rbp+var_28]
0x140062d89  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140062d8e  mov     eax, ebx
0x140062d90  lea     r11, [rsp+60h+var_s0]
0x140062d95  mov     rbx, [r11+20h]
0x140062d99  mov     rsi, [r11+28h]
0x140062d9d  mov     rsp, r11
0x140062da0  pop     r14
0x140062da2  pop     rdi
0x140062da3  pop     rbp
0x140062da4  retn
```
