# GetFxClsidsFromPropertyStore(IPropertyStore *,IPropertyStore *,_tagpropertykey,_tagpropertykey,ushort const *,uint *,_GUID * *)

- ea: `0x18002c4e4`
- end: `0x18002c924`
- name: `?GetFxClsidsFromPropertyStore@@YAJPEAUIPropertyStore@@0U_tagpropertykey@@1PEBGPEAIPEAPEAU_GUID@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(struct IPropertyStore *, struct IPropertyStore *, struct _tagpropertykey *, struct _tagpropertykey *, unsigned __int16 *, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002addc`

## callees

- `0x1800094f8`
- `0x18000cba0`
- `0x18000e284`
- `0x18001280c`
- `0x18002c4e4`
- `0x18002ca38`
- `0x18002cb98`
- `0x18002cbc4`
- `0x180070cf0`
- `0x18015ff5c`
- `0x180160028`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c908`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002c908`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c5e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c701`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c5e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002c701`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c5d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c6d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c8c6`

## pseudocode

```c
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
  if ( (unsigned int)operator==(a4, qword_180187740) )
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
0x18002c4e4  push    rbp
0x18002c4e6  push    rbx
0x18002c4e7  push    rsi
0x18002c4e8  push    rdi
0x18002c4e9  push    r12
0x18002c4eb  push    r13
0x18002c4ed  push    r14
0x18002c4ef  push    r15
0x18002c4f1  lea     rbp, [rsp-7]
0x18002c4f6  sub     rsp, 98h
0x18002c4fd  mov     r14, r9
0x18002c500  mov     r9, r8
0x18002c503  mov     r13, rdx
0x18002c506  mov     r15, rcx
0x18002c509  mov     r12, [rbp+3Fh+arg_20]
0x18002c50d  mov     [rbp+3Fh+var_60], r12
0x18002c511  mov     rax, [rbp+3Fh+arg_28]
0x18002c515  mov     [rbp+3Fh+var_50], rax
0x18002c519  mov     rcx, [rbp+3Fh+arg_30]
0x18002c51d  mov     [rbp+3Fh+var_58], rcx
0x18002c521  xor     esi, esi
0x18002c523  mov     [rax], esi
0x18002c525  mov     [rcx], rsi
0x18002c528  xorps   xmm0, xmm0
0x18002c52b  xor     eax, eax
0x18002c52d  movups  xmmword ptr [rbp+3Fh+lpsz], xmm0
0x18002c531  mov     [rbp+3Fh+var_78], rax
0x18002c535  mov     edi, esi
0x18002c537  mov     [rbp+3Fh+pclsid], rsi
0x18002c53b  mov     rax, [rdx]
0x18002c53e  lea     r8, [rbp+3Fh+lpsz]
0x18002c542  mov     rdx, r9
0x18002c545  mov     rcx, r13
0x18002c548  mov     rax, [rax+28h]
0x18002c54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c551  mov     ebx, eax
0x18002c553  test    eax, eax
0x18002c555  jns     short loc_18002C564
0x18002c557  mov     r9d, eax
0x18002c55a  mov     edx, 1A3h
0x18002c55f  jmp     loc_18002C74E
0x18002c564  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x18002c568  test    ax, ax
0x18002c56b  jz      loc_18002C638
0x18002c571  cmp     eax, 1Fh
0x18002c574  jz      short loc_18002C5A8
0x18002c576  mov     edx, 1A9h; void *
0x18002c57b  mov     dword ptr [rsp+0D0h+var_A8], eax; char *
0x18002c57f  mov     ebx, 8007070Ch
0x18002c584  lea     rax, a0x08x; "0x%08X"
0x18002c58b  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c592  mov     r9d, ebx; char *
0x18002c595  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18002c59a  mov     rcx, [rbp+47h]; this
0x18002c59e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002c5a3  jmp     loc_18002C75F
0x18002c5a8  mov     edx, 1
0x18002c5ad  lea     rcx, [rbp+3Fh+pv]
0x18002c5b1  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x18002c5b6  mov     rdx, rax
0x18002c5b9  lea     rcx, [rbp+3Fh+pclsid]
0x18002c5bd  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18002c5c2  mov     rcx, [rbp+3Fh+pv]; pv
0x18002c5c6  xor     r14d, r14d
0x18002c5c9  mov     [rbp+3Fh+pv], r14
0x18002c5cd  test    rcx, rcx
0x18002c5d0  jz      short loc_18002C5D8
0x18002c5d2  call    cs:__imp_CoTaskMemFree
0x18002c5d8  mov     rdi, [rbp+3Fh+pclsid]
0x18002c5dc  test    rdi, rdi
0x18002c5df  jz      short loc_18002C62E
0x18002c5e1  mov     rdx, rdi; pclsid
0x18002c5e4  mov     rcx, [rbp+3Fh+lpsz+8]; lpsz
0x18002c5e8  call    cs:__imp_CLSIDFromString
0x18002c5ee  mov     ebx, eax
0x18002c5f0  test    eax, eax
0x18002c5f2  jns     short loc_18002C624
0x18002c5f4  mov     rcx, [rbp+47h]; this
0x18002c5f8  mov     r9d, eax; char *
0x18002c5fb  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c602  mov     edx, 1AEh; void *
0x18002c607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c60c  nop
0x18002c60d  test    rdi, rdi
0x18002c610  jz      loc_18002C904
0x18002c616  mov     rcx, rdi; pv
0x18002c619  call    cs:__imp_CoTaskMemFree
0x18002c61f  jmp     loc_18002C904
0x18002c624  mov     esi, 1
0x18002c629  jmp     loc_18002C767
0x18002c62e  mov     edx, 1ADh
0x18002c633  jmp     loc_18002C746
0x18002c638  lea     rdx, qword_180187740
0x18002c63f  mov     rcx, r14
0x18002c642  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18002c647  test    eax, eax
0x18002c649  jnz     loc_18002C764
0x18002c64f  mov     rax, [r13+0]
0x18002c653  lea     r8, [rbp+3Fh+lpsz]
0x18002c657  mov     rdx, r14
0x18002c65a  mov     rcx, r13
0x18002c65d  mov     rax, [rax+28h]
0x18002c661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c666  mov     ebx, eax
0x18002c668  xor     r14d, r14d
0x18002c66b  test    eax, eax
0x18002c66d  jns     short loc_18002C67C
0x18002c66f  mov     r9d, eax
0x18002c672  mov     edx, 1B2h
0x18002c677  jmp     loc_18002C74E
0x18002c67c  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x18002c680  test    ax, ax
0x18002c683  jz      loc_18002C767
0x18002c689  mov     ecx, 101Fh
0x18002c68e  cmp     ax, cx
0x18002c691  jz      short loc_18002C69D
0x18002c693  mov     edx, 1B5h
0x18002c698  jmp     loc_18002C57B
0x18002c69d  mov     esi, dword ptr [rbp+3Fh+lpsz+8]
0x18002c6a0  test    esi, esi
0x18002c6a2  jnz     short loc_18002C6B3
0x18002c6a4  mov     ebx, 8007000Dh
0x18002c6a9  mov     edx, 1B6h
0x18002c6ae  jmp     loc_18002C74B
0x18002c6b3  mov     rdx, rsi
0x18002c6b6  lea     rcx, [rbp+3Fh+pv]
0x18002c6ba  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x18002c6bf  mov     rdx, rax
0x18002c6c2  lea     rcx, [rbp+3Fh+pclsid]
0x18002c6c6  call    ??4?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18002c6cb  mov     rcx, [rbp+3Fh+pv]; pv
0x18002c6cf  mov     [rbp+3Fh+pv], r14
0x18002c6d3  test    rcx, rcx
0x18002c6d6  jz      short loc_18002C6DE
0x18002c6d8  call    cs:__imp_CoTaskMemFree
0x18002c6de  mov     rdi, [rbp+3Fh+pclsid]
0x18002c6e2  test    rdi, rdi
0x18002c6e5  jz      short loc_18002C741
0x18002c6e7  mov     ebx, r14d
0x18002c6ea  cmp     ebx, esi
0x18002c6ec  jnb     short loc_18002C764
0x18002c6ee  mov     eax, ebx
0x18002c6f0  mov     edx, ebx
0x18002c6f2  shl     rdx, 4
0x18002c6f6  add     rdx, rdi; pclsid
0x18002c6f9  mov     rcx, [rbp+3Fh+var_78]
0x18002c6fd  mov     rcx, [rcx+rax*8]; lpsz
0x18002c701  call    cs:__imp_CLSIDFromString
0x18002c707  mov     r14d, eax
0x18002c70a  test    eax, eax
0x18002c70c  js      short loc_18002C712
0x18002c70e  inc     ebx
0x18002c710  jmp     short loc_18002C6EA
0x18002c712  mov     rcx, [rbp+47h]; this
0x18002c716  mov     r9d, r14d; char *
0x18002c719  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c720  mov     edx, 1BDh; void *
0x18002c725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c72a  nop
0x18002c72b  test    rdi, rdi
0x18002c72e  jz      short loc_18002C739
0x18002c730  mov     rcx, rdi; pv
0x18002c733  call    cs:__imp_CoTaskMemFree
0x18002c739  mov     ebx, r14d
0x18002c73c  jmp     loc_18002C904
0x18002c741  mov     edx, 1BAh; void *
0x18002c746  mov     ebx, 8007000Eh
0x18002c74b  mov     r9d, ebx; char *
0x18002c74e  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c755  mov     rcx, [rbp+47h]; this
0x18002c759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c75e  nop
0x18002c75f  jmp     loc_18002C904
0x18002c764  xor     r14d, r14d
0x18002c767  mov     rbx, r14
0x18002c76a  mov     [rbp+3Fh+var_98], rbx
0x18002c76e  test    r15, r15
0x18002c771  jz      short loc_18002C7BB
0x18002c773  xor     edx, edx
0x18002c775  lea     rcx, [rbp+3Fh+var_98]
0x18002c779  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c77e  lea     rdx, [rbp+3Fh+var_98]; unsigned __int16 **
0x18002c782  mov     rcx, r15; struct IPropertyStore *
0x18002c785  call    ?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z; GetDeviceInstanceId(IPropertyStore *,ushort * *)
0x18002c78a  mov     ebx, eax
0x18002c78c  test    eax, eax
0x18002c78e  jns     short loc_18002C7B7
0x18002c790  mov     rcx, [rbp+47h]; this
0x18002c794  mov     r9d, eax; char *
0x18002c797  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c79e  mov     edx, 1C6h; void *
0x18002c7a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7a8  nop
0x18002c7a9  lea     rcx, [rbp+3Fh+var_98]
0x18002c7ad  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c7b2  jmp     loc_18002C60D
0x18002c7b7  mov     rbx, [rbp+3Fh+var_98]
0x18002c7bb  mov     r15d, r14d
0x18002c7be  cmp     r15d, esi
0x18002c7c1  jnb     loc_18002C8EB
0x18002c7c7  mov     r14d, r15d
0x18002c7ca  add     r14, r14
0x18002c7cd  xor     eax, eax
0x18002c7cf  test    r12, r12
0x18002c7d2  jnz     short loc_18002C838
0x18002c7d4  mov     [rbp+3Fh+pv], rax
0x18002c7d8  xor     edx, edx
0x18002c7da  lea     rcx, [rbp+3Fh+pv]
0x18002c7de  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c7e3  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c7e8  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c7ed  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x18002c7f1  lea     rdx, [rbp+3Fh+var_70]; struct _GUID
0x18002c7f5  mov     rcx, r13; struct IPropertyStore *
0x18002c7f8  call    ?GetApoDeviceFromFxPropStore@@YAJPEAUIPropertyStore@@U_GUID@@PEAPEAG@Z; GetApoDeviceFromFxPropStore(IPropertyStore *,_GUID,ushort * *)
0x18002c7fd  mov     r12d, eax
0x18002c800  test    eax, eax
0x18002c802  js      loc_18002C891
0x18002c808  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c80d  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c812  lea     r8, [rbp+3Fh+var_70]; struct _GUID
0x18002c816  mov     rdx, rbx; unsigned __int16 *
0x18002c819  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x18002c81d  call    ?LookUpApoRegistration@@YAJPEAG0U_GUID@@@Z; LookUpApoRegistration(ushort *,ushort *,_GUID)
0x18002c822  mov     r14d, eax
0x18002c825  test    eax, eax
0x18002c827  js      short loc_18002C860
0x18002c829  lea     rcx, [rbp+3Fh+pv]
0x18002c82d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c832  mov     r12, [rbp+3Fh+var_60]
0x18002c836  jmp     short loc_18002C858
0x18002c838  movups  xmm0, xmmword ptr [rdi+r14*8]
0x18002c83d  movdqu  xmmword ptr [rbp+3Fh+var_70.Data1], xmm0
0x18002c842  lea     r8, [rbp+3Fh+var_70]; struct _GUID
0x18002c846  mov     rdx, rbx; unsigned __int16 *
0x18002c849  mov     rcx, r12; unsigned __int16 *
0x18002c84c  call    ?LookUpApoRegistration@@YAJPEAG0U_GUID@@@Z; LookUpApoRegistration(ushort *,ushort *,_GUID)
0x18002c851  mov     r14d, eax
0x18002c854  test    eax, eax
0x18002c856  js      short loc_18002C8D1
0x18002c858  inc     r15d
0x18002c85b  jmp     loc_18002C7BE
0x18002c860  mov     rcx, [rbp+47h]; this
0x18002c864  mov     r9d, r14d; char *
0x18002c867  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c86e  mov     edx, 1D3h; void *
0x18002c873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c878  nop
0x18002c879  lea     rcx, [rbp+3Fh+pv]
0x18002c87d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c882  nop
0x18002c883  lea     rcx, [rbp+3Fh+var_98]
0x18002c887  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c88c  jmp     loc_18002C72B
0x18002c891  mov     rcx, [rbp+47h]; this
0x18002c895  mov     r9d, r12d; char *
0x18002c898  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c89f  mov     edx, 1D2h; void *
0x18002c8a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8a9  nop
0x18002c8aa  lea     rcx, [rbp+3Fh+pv]
0x18002c8ae  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c8b3  nop
0x18002c8b4  lea     rcx, [rbp+3Fh+var_98]
0x18002c8b8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c8bd  nop
0x18002c8be  test    rdi, rdi
0x18002c8c1  jz      short loc_18002C8CC
0x18002c8c3  mov     rcx, rdi; pv
0x18002c8c6  call    cs:__imp_CoTaskMemFree
0x18002c8cc  mov     ebx, r12d
0x18002c8cf  jmp     short loc_18002C904
0x18002c8d1  mov     rcx, [rbp+47h]; this
0x18002c8d5  mov     r9d, r14d; char *
0x18002c8d8  lea     r8, aAvcoreAudiocor_64; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002c8df  mov     edx, 1D8h; void *
0x18002c8e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c8e9  jmp     short loc_18002C883
0x18002c8eb  mov     rax, [rbp+3Fh+var_58]
0x18002c8ef  mov     [rax], rdi
0x18002c8f2  mov     rax, [rbp+3Fh+var_50]
0x18002c8f6  mov     [rax], esi
0x18002c8f8  lea     rcx, [rbp+3Fh+var_98]
0x18002c8fc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002c901  nop
0x18002c902  xor     ebx, ebx
0x18002c904  lea     rcx, [rbp+3Fh+lpsz]; pvar
0x18002c908  call    cs:__imp_PropVariantClear
0x18002c90e  mov     eax, ebx
0x18002c910  add     rsp, 98h
0x18002c917  pop     r15
0x18002c919  pop     r14
0x18002c91b  pop     r13
0x18002c91d  pop     r12
0x18002c91f  pop     rdi
0x18002c920  pop     rsi
0x18002c921  pop     rbx
0x18002c922  pop     rbp
0x18002c923  retn
```
