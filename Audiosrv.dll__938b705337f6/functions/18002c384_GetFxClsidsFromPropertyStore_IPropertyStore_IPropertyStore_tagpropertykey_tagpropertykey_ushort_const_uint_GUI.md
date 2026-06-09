# GetFxClsidsFromPropertyStore(IPropertyStore *,IPropertyStore *,_tagpropertykey,_tagpropertykey,ushort const *,uint *,_GUID * *)

- ea: `0x18002c384`
- end: `0x18002c7c4`
- name: `?GetFxClsidsFromPropertyStore@@YAJPEAUIPropertyStore@@0U_tagpropertykey@@1PEBGPEAIPEAPEAU_GUID@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(struct IPropertyStore *, struct IPropertyStore *, struct _tagpropertykey *, struct _tagpropertykey *, const unsigned __int16 *, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ac7c`

## callees

- `0x1800093a8`
- `0x18000ca50`
- `0x18000e134`
- `0x1800126bc`
- `0x18002c384`
- `0x18002c8d8`
- `0x18002ca38`
- `0x18002ca64`
- `0x1800711f0`
- `0x18015f24c`
- `0x18015f318`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c7a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c7a8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c488`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c5a1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c488`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c5a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c4b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c766`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetFxClsidsFromPropertyStore(
        struct IPropertyStore *a1,
        struct IPropertyStore *a2,
        struct _tagpropertykey *a3,
        struct _tagpropertykey *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        struct _GUID **a7)
{
  unsigned __int16 *v10; // r12
  unsigned int v11; // esi
  LPCLSID v12; // rdi
  int v13; // eax
  unsigned int v14; // ebx
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 unique_cotaskmem; // rax
  void *v20; // rcx
  HRESULT v21; // eax
  int v22; // eax
  __int64 v23; // rax
  void *v24; // rcx
  unsigned int j; // ebx
  HRESULT v26; // eax
  unsigned int v27; // r14d
  unsigned __int16 *v28; // rbx
  int DeviceInstanceId; // eax
  unsigned int i; // r15d
  int ApoDeviceFromFxPropStore; // eax
  unsigned int v32; // r12d
  int v33; // eax
  int v34; // eax
  int v36; // [rsp+20h] [rbp-71h]
  char *v37; // [rsp+28h] [rbp-69h]
  LPVOID pv; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int16 *v39; // [rsp+38h] [rbp-59h] BYREF
  LPCLSID pclsid; // [rsp+40h] [rbp-51h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v42; // [rsp+58h] [rbp-39h]
  struct _GUID v43; // [rsp+60h] [rbp-31h] BYREF
  const unsigned __int16 *v44; // [rsp+70h] [rbp-21h]
  struct _GUID **v45; // [rsp+78h] [rbp-19h]
  unsigned int *v46; // [rsp+80h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v10 = a5;
  v44 = a5;
  v46 = a6;
  v45 = a7;
  v11 = 0;
  *a6 = 0;
  *a7 = 0;
  *(_OWORD *)lpsz = 0;
  v42 = 0;
  v12 = 0;
  pclsid = 0;
  v13 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, LPCOLESTR *))a2->lpVtbl->GetValue)(
          a2,
          a3,
          lpsz);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = (unsigned int)v13;
    v16 = 419;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
      (const char *)v15,
      v36);
    goto LABEL_58;
  }
  v17 = LOWORD(lpsz[0]);
  if ( LOWORD(lpsz[0]) )
  {
    if ( LOWORD(lpsz[0]) != 31 )
    {
      v18 = 425;
LABEL_6:
      LODWORD(v37) = v17;
      v14 = -2147023092;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v18,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
        (const char *)0x8007070CLL,
        (int)"0x%08X",
        v37);
      goto LABEL_58;
    }
    unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<_GUID [0]>(&pv, 1);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      &pclsid,
      unique_cotaskmem);
    v20 = pv;
    pv = 0;
    if ( v20 )
      CoTaskMemFree(v20);
    v12 = pclsid;
    if ( pclsid )
    {
      v21 = CLSIDFromString(lpsz[1], pclsid);
      v14 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
          (const char *)(unsigned int)v21,
          v36);
        goto LABEL_12;
      }
      v11 = 1;
LABEL_39:
      v28 = 0;
      v39 = 0;
      if ( a1 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v39,
          0);
        DeviceInstanceId = GetDeviceInstanceId(a1, &v39);
        v14 = DeviceInstanceId;
        if ( DeviceInstanceId < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
            (const char *)(unsigned int)DeviceInstanceId,
            v36);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v39);
LABEL_12:
          if ( v12 )
            CoTaskMemFree(v12);
          goto LABEL_58;
        }
        v28 = v39;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= v11 )
        {
          *v45 = v12;
          *v46 = v11;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v39);
          v14 = 0;
          goto LABEL_58;
        }
        if ( v10 )
        {
          v43 = v12[i];
          v34 = LookUpApoRegistration(v10, v28, &v43);
          v27 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D8,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
              (const char *)(unsigned int)v34,
              v36);
            goto LABEL_52;
          }
        }
        else
        {
          pv = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pv,
            0);
          v43 = v12[i];
          ApoDeviceFromFxPropStore = GetApoDeviceFromFxPropStore(a2, &v43, (unsigned __int16 **)&pv);
          v32 = ApoDeviceFromFxPropStore;
          if ( ApoDeviceFromFxPropStore < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D2,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
              (const char *)(unsigned int)ApoDeviceFromFxPropStore,
              v36);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v39);
            if ( v12 )
              CoTaskMemFree(v12);
            v14 = v32;
            goto LABEL_58;
          }
          v43 = v12[i];
          v33 = LookUpApoRegistration((unsigned __int16 *)pv, v28, &v43);
          v27 = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1D3,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
              (const char *)(unsigned int)v33,
              v36);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
LABEL_52:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v39);
            goto LABEL_32;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
          v10 = (unsigned __int16 *)v44;
        }
      }
    }
    v16 = 429;
    goto LABEL_36;
  }
  if ( (unsigned int)operator==(a4, &unk_1801866E0) )
    goto LABEL_39;
  v22 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, LPCOLESTR *))a2->lpVtbl->GetValue)(
          a2,
          a4,
          lpsz);
  v14 = v22;
  if ( v22 < 0 )
  {
    v15 = (unsigned int)v22;
    v16 = 434;
    goto LABEL_38;
  }
  v17 = LOWORD(lpsz[0]);
  if ( !LOWORD(lpsz[0]) )
    goto LABEL_39;
  if ( LOWORD(lpsz[0]) != 4127 )
  {
    v18 = 437;
    goto LABEL_6;
  }
  v11 = (unsigned int)lpsz[1];
  if ( !LODWORD(lpsz[1]) )
  {
    v14 = -2147024883;
    v16 = 438;
LABEL_37:
    v15 = v14;
    goto LABEL_38;
  }
  v23 = wil::make_unique_cotaskmem_nothrow<_GUID [0]>(&pv, LODWORD(lpsz[1]));
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &pclsid,
    v23);
  v24 = pv;
  pv = 0;
  if ( v24 )
    CoTaskMemFree(v24);
  v12 = pclsid;
  if ( !pclsid )
  {
    v16 = 442;
LABEL_36:
    v14 = -2147024882;
    goto LABEL_37;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= v11 )
      goto LABEL_39;
    v26 = CLSIDFromString(*(LPCOLESTR *)(v42 + 8LL * j), &v12[j]);
    v27 = v26;
    if ( v26 < 0 )
      break;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BD,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
    (const char *)(unsigned int)v26,
    v36);
LABEL_32:
  if ( v12 )
    CoTaskMemFree(v12);
  v14 = v27;
LABEL_58:
  PropVariantClear((PROPVARIANT *)lpsz);
  return v14;
}

```

## disassembly

```asm
0x18002c384  push    rbp
0x18002c386  push    rbx
0x18002c387  push    rsi
0x18002c388  push    rdi
0x18002c389  push    r12
0x18002c38b  push    r13
0x18002c38d  push    r14
0x18002c38f  push    r15
0x18002c391  lea     rbp, [rsp-7]
0x18002c396  sub     rsp, 98h
0x18002c39d  mov     r14, r9
0x18002c3a0  mov     r9, r8
0x18002c3a3  mov     r13, rdx
0x18002c3a6  mov     r15, rcx
0x18002c3a9  mov     r12, [rbp+3Fh+arg_20]
0x18002c3ad  mov     [rbp+3Fh+var_60], r12
0x18002c3b1  mov     rax, [rbp+3Fh+arg_28]
0x18002c3b5  mov     [rbp+3Fh+var_50], rax
0x18002c3b9  mov     rcx, [rbp+3Fh+arg_30]
0x18002c3bd  mov     [rbp+3Fh+var_58], rcx
0x18002c3c1  xor     esi, esi
0x18002c3c3  mov     [rax], esi
0x18002c3c5  mov     [rcx], rsi
0x18002c3c8  xorps   xmm0, xmm0
0x18002c3cb  xor     eax, eax
0x18002c3cd  movups  xmmword ptr [rbp+3Fh+lpsz], xmm0
0x18002c3d1  mov     [rbp+3Fh+var_78], rax
0x18002c3d5  mov     edi, esi
0x18002c3d7  mov     [rbp+3Fh+pclsid], rsi
0x18002c3db  mov     rax, [rdx]
0x18002c3de  lea     r8, [rbp+3Fh+lpsz]
0x18002c3e2  mov     rdx, r9
0x18002c3e5  mov     rcx, r13
0x18002c3e8  mov     rax, [rax+28h]
0x18002c3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3f1  mov     ebx, eax
0x18002c3f3  test    eax, eax
0x18002c3f5  jns     short loc_18002C404
0x18002c3f7  mov     r9d, eax
0x18002c3fa  mov     edx, 1A3h
0x18002c3ff  jmp     loc_18002C5EE
0x18002c404  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x18002c408  test    ax, ax
0x18002c40b  jz      loc_18002C4D8
0x18002c411  cmp     eax, 1Fh
0x18002c414  jz      short loc_18002C448
0x18002c416  mov     edx, 1A9h; void *
0x18002c41b  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x18002c41f  mov     ebx, 8007070Ch
0x18002c424  lea     rax, a0x08x; "0x%08X"
0x18002c42b  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c432  mov     r9d, ebx; char *
0x18002c435  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18002c43a  mov     rcx, [rbp+47h]; this
0x18002c43e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002c443  jmp     loc_18002C5FF
0x18002c448  mov     edx, 1
0x18002c44d  lea     rcx, [rbp+3Fh+pv]
0x18002c451  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x18002c456  mov     rdx, rax
0x18002c459  lea     rcx, [rbp+3Fh+pclsid]
0x18002c45d  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18002c462  mov     rcx, [rbp+3Fh+pv]; pv
0x18002c466  xor     r14d, r14d
0x18002c469  mov     [rbp+3Fh+pv], r14
0x18002c46d  test    rcx, rcx
0x18002c470  jz      short loc_18002C478
0x18002c472  call    cs:__imp_CoTaskMemFree
0x18002c478  mov     rdi, [rbp+3Fh+pclsid]
0x18002c47c  test    rdi, rdi
0x18002c47f  jz      short loc_18002C4CE
0x18002c481  mov     rdx, rdi; pclsid
0x18002c484  mov     rcx, [rbp+3Fh+lpsz+8]; lpsz
0x18002c488  call    cs:__imp_CLSIDFromString
0x18002c48e  mov     ebx, eax
0x18002c490  test    eax, eax
0x18002c492  jns     short loc_18002C4C4
0x18002c494  mov     rcx, [rbp+47h]; this
0x18002c498  mov     r9d, eax; char *
0x18002c49b  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c4a2  mov     edx, 1AEh; void *
0x18002c4a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4ac  nop
0x18002c4ad  test    rdi, rdi
0x18002c4b0  jz      loc_18002C7A4
0x18002c4b6  mov     rcx, rdi; pv
0x18002c4b9  call    cs:__imp_CoTaskMemFree
0x18002c4bf  jmp     loc_18002C7A4
0x18002c4c4  mov     esi, 1
0x18002c4c9  jmp     loc_18002C607
0x18002c4ce  mov     edx, 1ADh
0x18002c4d3  jmp     loc_18002C5E6
0x18002c4d8  lea     rdx, unk_1801866E0
0x18002c4df  mov     rcx, r14
0x18002c4e2  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002c4e7  test    eax, eax
0x18002c4e9  jnz     loc_18002C604
0x18002c4ef  mov     rax, [r13+0]
0x18002c4f3  lea     r8, [rbp+3Fh+lpsz]
0x18002c4f7  mov     rdx, r14
0x18002c4fa  mov     rcx, r13
0x18002c4fd  mov     rax, [rax+28h]
0x18002c501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c506  mov     ebx, eax
0x18002c508  xor     r14d, r14d
0x18002c50b  test    eax, eax
0x18002c50d  jns     short loc_18002C51C
0x18002c50f  mov     r9d, eax
0x18002c512  mov     edx, 1B2h
0x18002c517  jmp     loc_18002C5EE
0x18002c51c  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x18002c520  test    ax, ax
0x18002c523  jz      loc_18002C607
0x18002c529  mov     ecx, 101Fh
0x18002c52e  cmp     ax, cx
0x18002c531  jz      short loc_18002C53D
0x18002c533  mov     edx, 1B5h
0x18002c538  jmp     loc_18002C41B
0x18002c53d  mov     esi, dword ptr [rbp+3Fh+lpsz+8]
0x18002c540  test    esi, esi
0x18002c542  jnz     short loc_18002C553
0x18002c544  mov     ebx, 8007000Dh
0x18002c549  mov     edx, 1B6h
0x18002c54e  jmp     loc_18002C5EB
0x18002c553  mov     rdx, rsi
0x18002c556  lea     rcx, [rbp+3Fh+pv]
0x18002c55a  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x18002c55f  mov     rdx, rax
0x18002c562  lea     rcx, [rbp+3Fh+pclsid]
0x18002c566  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18002c56b  mov     rcx, [rbp+3Fh+pv]; pv
0x18002c56f  mov     [rbp+3Fh+pv], r14
0x18002c573  test    rcx, rcx
0x18002c576  jz      short loc_18002C57E
0x18002c578  call    cs:__imp_CoTaskMemFree
0x18002c57e  mov     rdi, [rbp+3Fh+pclsid]
0x18002c582  test    rdi, rdi
0x18002c585  jz      short loc_18002C5E1
0x18002c587  mov     ebx, r14d
0x18002c58a  cmp     ebx, esi
0x18002c58c  jnb     short loc_18002C604
0x18002c58e  mov     eax, ebx
0x18002c590  mov     edx, ebx
0x18002c592  shl     rdx, 4
0x18002c596  add     rdx, rdi; pclsid
0x18002c599  mov     rcx, [rbp+3Fh+var_78]
0x18002c59d  mov     rcx, [rcx+rax*8]; lpsz
0x18002c5a1  call    cs:__imp_CLSIDFromString
0x18002c5a7  mov     r14d, eax
0x18002c5aa  test    eax, eax
0x18002c5ac  js      short loc_18002C5B2
0x18002c5ae  inc     ebx
0x18002c5b0  jmp     short loc_18002C58A
0x18002c5b2  mov     rcx, [rbp+47h]; this
0x18002c5b6  mov     r9d, r14d; char *
0x18002c5b9  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c5c0  mov     edx, 1BDh; void *
0x18002c5c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5ca  nop
0x18002c5cb  test    rdi, rdi
0x18002c5ce  jz      short loc_18002C5D9
0x18002c5d0  mov     rcx, rdi; pv
0x18002c5d3  call    cs:__imp_CoTaskMemFree
0x18002c5d9  mov     ebx, r14d
0x18002c5dc  jmp     loc_18002C7A4
0x18002c5e1  mov     edx, 1BAh; void *
0x18002c5e6  mov     ebx, 8007000Eh
0x18002c5eb  mov     r9d, ebx; char *
0x18002c5ee  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c5f5  mov     rcx, [rbp+47h]; this
0x18002c5f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5fe  nop
0x18002c5ff  jmp     loc_18002C7A4
0x18002c604  xor     r14d, r14d
0x18002c607  mov     rbx, r14
0x18002c60a  mov     [rbp+3Fh+var_98], rbx
0x18002c60e  test    r15, r15
0x18002c611  jz      short loc_18002C65B
0x18002c613  xor     edx, edx
0x18002c615  lea     rcx, [rbp+3Fh+var_98]
0x18002c619  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c61e  lea     rdx, [rbp+3Fh+var_98]; unsigned __int16 **
0x18002c622  mov     rcx, r15; struct IPropertyStore *
0x18002c625  call    ?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z; GetDeviceInstanceId(IPropertyStore *,ushort * *)
0x18002c62a  mov     ebx, eax
0x18002c62c  test    eax, eax
0x18002c62e  jns     short loc_18002C657
0x18002c630  mov     rcx, [rbp+47h]; this
0x18002c634  mov     r9d, eax; char *
0x18002c637  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c63e  mov     edx, 1C6h; void *
0x18002c643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c648  nop
0x18002c649  lea     rcx, [rbp+3Fh+var_98]
0x18002c64d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c652  jmp     loc_18002C4AD
0x18002c657  mov     rbx, [rbp+3Fh+var_98]
0x18002c65b  mov     r15d, r14d
0x18002c65e  cmp     r15d, esi
0x18002c661  jnb     loc_18002C78B
0x18002c667  mov     r14d, r15d
0x18002c66a  add     r14, r14
0x18002c66d  xor     eax, eax
0x18002c66f  test    r12, r12
0x18002c672  jnz     short loc_18002C6D8
0x18002c674  mov     [rbp+3Fh+pv], rax
0x18002c678  xor     edx, edx
0x18002c67a  lea     rcx, [rbp+3Fh+pv]
0x18002c67e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c683  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c688  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c68d  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x18002c691  lea     rdx, [rbp+3Fh+var_70]; struct _GUID
0x18002c695  mov     rcx, r13; struct IPropertyStore *
0x18002c698  call    ?GetApoDeviceFromFxPropStore@@YAJPEAUIPropertyStore@@U_GUID@@PEAPEAG@Z; GetApoDeviceFromFxPropStore(IPropertyStore *,_GUID,ushort * *)
0x18002c69d  mov     r12d, eax
0x18002c6a0  test    eax, eax
0x18002c6a2  js      loc_18002C731
0x18002c6a8  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c6ad  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c6b2  lea     r8, [rbp+3Fh+var_70]; struct _GUID
0x18002c6b6  mov     rdx, rbx; unsigned __int16 *
0x18002c6b9  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18002c6bd  call    ?LookUpApoRegistration@@YAJPEAG0U_GUID@@@Z; LookUpApoRegistration(ushort *,ushort *,_GUID)
0x18002c6c2  mov     r14d, eax
0x18002c6c5  test    eax, eax
0x18002c6c7  js      short loc_18002C700
0x18002c6c9  lea     rcx, [rbp+3Fh+pv]
0x18002c6cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c6d2  mov     r12, [rbp+3Fh+var_60]
0x18002c6d6  jmp     short loc_18002C6F8
0x18002c6d8  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c6dd  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c6e2  lea     r8, [rbp+3Fh+var_70]; struct _GUID
0x18002c6e6  mov     rdx, rbx; unsigned __int16 *
0x18002c6e9  mov     rcx, r12; unsigned __int16 *
0x18002c6ec  call    ?LookUpApoRegistration@@YAJPEAG0U_GUID@@@Z; LookUpApoRegistration(ushort *,ushort *,_GUID)
0x18002c6f1  mov     r14d, eax
0x18002c6f4  test    eax, eax
0x18002c6f6  js      short loc_18002C771
0x18002c6f8  inc     r15d
0x18002c6fb  jmp     loc_18002C65E
0x18002c700  mov     rcx, [rbp+47h]; this
0x18002c704  mov     r9d, r14d; char *
0x18002c707  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c70e  mov     edx, 1D3h; void *
0x18002c713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c718  nop
0x18002c719  lea     rcx, [rbp+3Fh+pv]
0x18002c71d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c722  nop
0x18002c723  lea     rcx, [rbp+3Fh+var_98]
0x18002c727  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c72c  jmp     loc_18002C5CB
0x18002c731  mov     rcx, [rbp+47h]; this
0x18002c735  mov     r9d, r12d; char *
0x18002c738  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c73f  mov     edx, 1D2h; void *
0x18002c744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c749  nop
0x18002c74a  lea     rcx, [rbp+3Fh+pv]
0x18002c74e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c753  nop
0x18002c754  lea     rcx, [rbp+3Fh+var_98]
0x18002c758  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c75d  nop
0x18002c75e  test    rdi, rdi
0x18002c761  jz      short loc_18002C76C
0x18002c763  mov     rcx, rdi; pv
0x18002c766  call    cs:__imp_CoTaskMemFree
0x18002c76c  mov     ebx, r12d
0x18002c76f  jmp     short loc_18002C7A4
0x18002c771  mov     rcx, [rbp+47h]; this
0x18002c775  mov     r9d, r14d; char *
0x18002c778  lea     r8, aAvcoreAudiocor_63; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c77f  mov     edx, 1D8h; void *
0x18002c784  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c789  jmp     short loc_18002C723
0x18002c78b  mov     rax, [rbp+3Fh+var_58]
0x18002c78f  mov     [rax], rdi
0x18002c792  mov     rax, [rbp+3Fh+var_50]
0x18002c796  mov     [rax], esi
0x18002c798  lea     rcx, [rbp+3Fh+var_98]
0x18002c79c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c7a1  nop
0x18002c7a2  xor     ebx, ebx
0x18002c7a4  lea     rcx, [rbp+3Fh+lpsz]; pvar
0x18002c7a8  call    cs:__imp_PropVariantClear
0x18002c7ae  mov     eax, ebx
0x18002c7b0  add     rsp, 98h
0x18002c7b7  pop     r15
0x18002c7b9  pop     r14
0x18002c7bb  pop     r13
0x18002c7bd  pop     r12
0x18002c7bf  pop     rdi
0x18002c7c0  pop     rsi
0x18002c7c1  pop     rbx
0x18002c7c2  pop     rbp
0x18002c7c3  retn
```
