# GetFxClsidsFromPropertyStore(IPropertyStore *,IPropertyStore *,_tagpropertykey,_tagpropertykey,ushort const *,uint *,_GUID * *)

- ea: `0x18002187c`
- end: `0x180021caa`
- name: `?GetFxClsidsFromPropertyStore@@YAJPEAUIPropertyStore@@0U_tagpropertykey@@1PEBGPEAIPEAPEAU_GUID@@@Z`
- size: `1070`
- prototype: `__int64 __fastcall(struct IPropertyStore *, struct IPropertyStore *, struct _tagpropertykey *, struct _tagpropertykey *, const unsigned __int16 *, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180021658`

## callees

- `0x18000fb60`
- `0x180010da8`
- `0x18002187c`
- `0x180021cb0`
- `0x180033578`
- `0x1800343c4`
- `0x180034ae8`
- `0x1800394c4`
- `0x18003f780`
- `0x18005e78c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021981`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021aa8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021981`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180021aa8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021c8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180021c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002196b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002196b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800219b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021a7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021c80`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetFxClsidsFromPropertyStore(
        struct IPropertyStore *a1,
        struct IPropertyStore *a2,
        struct _tagpropertykey *a3,
        struct _tagpropertykey *a4,
        const unsigned __int16 *a5,
        unsigned int *a6,
        struct _GUID **a7)
{
  unsigned int v10; // r12d
  LPCLSID v11; // rsi
  int v12; // eax
  unsigned int v13; // ebx
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // r14d
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  void *v20; // rcx
  HRESULT v21; // eax
  int v22; // eax
  __int64 unique_cotaskmem; // rax
  void *v24; // rcx
  unsigned int i; // ebx
  HRESULT v26; // eax
  HRESULT v27; // edi
  unsigned __int16 *v28; // rbx
  int DeviceInstanceId; // eax
  unsigned int j; // r15d
  int ApoDeviceFromFxPropStore; // eax
  void *v32; // rdi
  int v33; // eax
  int v35; // [rsp+20h] [rbp-61h]
  char *v36; // [rsp+28h] [rbp-59h]
  LPVOID pv; // [rsp+30h] [rbp-51h] BYREF
  LPCLSID pclsid; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v39; // [rsp+40h] [rbp-41h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v41; // [rsp+58h] [rbp-29h]
  struct _GUID **v42; // [rsp+60h] [rbp-21h]
  unsigned int *v43; // [rsp+68h] [rbp-19h]
  struct _GUID v44; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v43 = a6;
  v42 = a7;
  *a6 = 0;
  v10 = 0;
  *a7 = 0;
  *(_OWORD *)lpsz = 0;
  v41 = 0;
  v11 = 0;
  pclsid = 0;
  v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, LPCOLESTR *))a2->lpVtbl->GetValue)(
          a2,
          a3,
          lpsz);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = (unsigned int)v12;
    v15 = 419;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
      (const char *)v14,
      v35);
    goto LABEL_64;
  }
  v16 = 1;
  v17 = LOWORD(lpsz[0]);
  if ( !LOWORD(lpsz[0]) )
  {
    v16 = 0;
    if ( !a4->pid && !memcmp_0(a4, qword_18006DFC0, 0x10u) )
      goto LABEL_39;
    v22 = ((__int64 (__fastcall *)(struct IPropertyStore *, struct _tagpropertykey *, LPCOLESTR *))a2->lpVtbl->GetValue)(
            a2,
            a4,
            lpsz);
    v13 = v22;
    if ( v22 < 0 )
    {
      v14 = (unsigned int)v22;
      v15 = 434;
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
    v16 = (unsigned int)lpsz[1];
    if ( !LODWORD(lpsz[1]) )
    {
      v13 = -2147024883;
      v15 = 438;
LABEL_37:
      v14 = v13;
      goto LABEL_38;
    }
    unique_cotaskmem = wil::make_unique_cotaskmem_nothrow<_GUID [0]>(&pv, LODWORD(lpsz[1]));
    wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      &pclsid,
      unique_cotaskmem);
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v11 = pclsid;
    if ( pclsid )
    {
      for ( i = 0; i < v16; ++i )
      {
        v26 = CLSIDFromString(*(LPCOLESTR *)(v41 + 8LL * i), &v11[i]);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BD,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
            (const char *)(unsigned int)v26,
            v35);
          goto LABEL_32;
        }
      }
      goto LABEL_39;
    }
    v15 = 442;
LABEL_36:
    v13 = -2147024882;
    goto LABEL_37;
  }
  if ( LOWORD(lpsz[0]) != 31 )
  {
    v18 = 425;
LABEL_6:
    LODWORD(v36) = v17;
    v13 = -2147023092;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v18,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
      (const char *)0x8007070CLL,
      (int)"0x%08X",
      v36);
    goto LABEL_64;
  }
  v19 = wil::make_unique_cotaskmem_nothrow<_GUID [0]>(&pv, 1);
  wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    &pclsid,
    v19);
  v20 = pv;
  pv = 0;
  if ( v20 )
    CoTaskMemFree(v20);
  v11 = pclsid;
  if ( !pclsid )
  {
    v15 = 429;
    goto LABEL_36;
  }
  v21 = CLSIDFromString(lpsz[1], pclsid);
  v13 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
      (const char *)(unsigned int)v21,
      v35);
LABEL_12:
    if ( v11 )
      CoTaskMemFree(v11);
    goto LABEL_64;
  }
LABEL_39:
  v28 = 0;
  v39 = 0;
  if ( a1 )
  {
    v39 = 0;
    DeviceInstanceId = GetDeviceInstanceId(a1, &v39);
    v13 = DeviceInstanceId;
    if ( DeviceInstanceId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
        (const char *)(unsigned int)DeviceInstanceId,
        v35);
      if ( v39 )
        CoTaskMemFree(v39);
      goto LABEL_12;
    }
    v28 = v39;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= v16 )
    {
      *v42 = v11;
      *v43 = v16;
      if ( v28 )
        CoTaskMemFree(v28);
      goto LABEL_63;
    }
    pv = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      0);
    v44 = v11[j];
    ApoDeviceFromFxPropStore = GetApoDeviceFromFxPropStore(a2, &v44, (unsigned __int16 **)&pv);
    v27 = ApoDeviceFromFxPropStore;
    if ( ApoDeviceFromFxPropStore < 0 )
      break;
    v44 = v11[j];
    v32 = pv;
    v33 = LookUpApoRegistration((unsigned __int16 *)pv, v28, &v44);
    v10 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
        (const char *)(unsigned int)v33,
        v35);
      if ( v32 )
        CoTaskMemFree(v32);
      if ( v28 )
        CoTaskMemFree(v28);
      if ( v11 )
        CoTaskMemFree(v11);
LABEL_63:
      v13 = v10;
      goto LABEL_64;
    }
    v10 = 0;
    if ( v32 )
      CoTaskMemFree(v32);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\epcutil.cpp",
    (const char *)(unsigned int)ApoDeviceFromFxPropStore,
    v35);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v28 )
    CoTaskMemFree(v28);
LABEL_32:
  if ( v11 )
    CoTaskMemFree(v11);
  v13 = v27;
LABEL_64:
  PropVariantClear((PROPVARIANT *)lpsz);
  return v13;
}

```

## disassembly

```asm
0x18002187c  push    rbp
0x18002187e  push    rbx
0x18002187f  push    rsi
0x180021880  push    rdi
0x180021881  push    r12
0x180021883  push    r13
0x180021885  push    r14
0x180021887  push    r15
0x180021889  lea     rbp, [rsp-7]
0x18002188e  sub     rsp, 88h
0x180021895  mov     rdi, r9
0x180021898  mov     r9, r8
0x18002189b  mov     r13, rdx
0x18002189e  mov     r15, rcx
0x1800218a1  mov     r12, [rbp+3Fh+arg_28]
0x1800218a5  mov     [rbp+3Fh+var_58], r12
0x1800218a9  mov     rax, [rbp+3Fh+arg_30]
0x1800218ad  mov     [rbp+3Fh+var_60], rax
0x1800218b1  mov     dword ptr [r12], 0
0x1800218b9  xor     r12d, r12d
0x1800218bc  mov     [rax], r12
0x1800218bf  xorps   xmm0, xmm0
0x1800218c2  xor     eax, eax
0x1800218c4  movups  xmmword ptr [rbp+3Fh+lpsz], xmm0
0x1800218c8  mov     [rbp+3Fh+var_68], rax
0x1800218cc  mov     esi, r12d
0x1800218cf  mov     [rbp+3Fh+pclsid], r12
0x1800218d3  mov     rax, [rdx]
0x1800218d6  lea     r8, [rbp+3Fh+lpsz]
0x1800218da  mov     rdx, r9
0x1800218dd  mov     rcx, r13
0x1800218e0  mov     rax, [rax+28h]
0x1800218e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e9  mov     ebx, eax
0x1800218eb  test    eax, eax
0x1800218ed  jns     short loc_1800218FC
0x1800218ef  mov     r9d, eax
0x1800218f2  mov     edx, 1A3h
0x1800218f7  jmp     loc_180021AF3
0x1800218fc  mov     r14d, 1
0x180021902  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x180021906  test    ax, ax
0x180021909  jz      loc_1800219CB
0x18002190f  cmp     eax, 1Fh
0x180021912  jz      short loc_180021946
0x180021914  mov     edx, 1A9h; void *
0x180021919  mov     dword ptr [rsp+0C0h+var_98], eax; char *
0x18002191d  mov     ebx, 8007070Ch
0x180021922  lea     rax, a0x08x; "0x%08X"
0x180021929  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021930  mov     r9d, ebx; char *
0x180021933  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180021938  mov     rcx, [rbp+47h]; this
0x18002193c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021941  jmp     loc_180021B04
0x180021946  mov     rdx, r14
0x180021949  lea     rcx, [rbp+3Fh+pv]
0x18002194d  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x180021952  mov     rdx, rax
0x180021955  lea     rcx, [rbp+3Fh+pclsid]
0x180021959  call    ??4?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18002195e  mov     rcx, [rbp+3Fh+pv]; pv
0x180021962  mov     [rbp+3Fh+pv], r12
0x180021966  test    rcx, rcx
0x180021969  jz      short loc_180021971
0x18002196b  call    cs:__imp_CoTaskMemFree
0x180021971  mov     rsi, [rbp+3Fh+pclsid]
0x180021975  test    rsi, rsi
0x180021978  jz      short loc_1800219C1
0x18002197a  mov     rdx, rsi; pclsid
0x18002197d  mov     rcx, [rbp+3Fh+lpsz+8]; lpsz
0x180021981  call    cs:__imp_CLSIDFromString
0x180021987  mov     ebx, eax
0x180021989  test    eax, eax
0x18002198b  jns     loc_180021B09
0x180021991  mov     rcx, [rbp+47h]; this
0x180021995  mov     r9d, eax; char *
0x180021998  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x18002199f  mov     edx, 1AEh; void *
0x1800219a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219a9  nop
0x1800219aa  test    rsi, rsi
0x1800219ad  jz      loc_180021C8A
0x1800219b3  mov     rcx, rsi; pv
0x1800219b6  call    cs:__imp_CoTaskMemFree
0x1800219bc  jmp     loc_180021C8A
0x1800219c1  mov     edx, 1ADh
0x1800219c6  jmp     loc_180021AEB
0x1800219cb  mov     r14d, r12d
0x1800219ce  mov     eax, cs:dword_18006DFD0
0x1800219d4  cmp     [rdi+10h], eax
0x1800219d7  jnz     short loc_1800219F6
0x1800219d9  mov     r8d, 10h; Size
0x1800219df  lea     rdx, qword_18006DFC0; Buf2
0x1800219e6  mov     rcx, rdi; Buf1
0x1800219e9  call    memcmp_0
0x1800219ee  test    eax, eax
0x1800219f0  jz      loc_180021B09
0x1800219f6  mov     rax, [r13+0]
0x1800219fa  lea     r8, [rbp+3Fh+lpsz]
0x1800219fe  mov     rdx, rdi
0x180021a01  mov     rcx, r13
0x180021a04  mov     rax, [rax+28h]
0x180021a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a0d  mov     ebx, eax
0x180021a0f  test    eax, eax
0x180021a11  jns     short loc_180021A20
0x180021a13  mov     r9d, eax
0x180021a16  mov     edx, 1B2h
0x180021a1b  jmp     loc_180021AF3
0x180021a20  movzx   eax, word ptr [rbp+3Fh+lpsz]
0x180021a24  test    ax, ax
0x180021a27  jz      loc_180021B09
0x180021a2d  mov     ecx, 101Fh
0x180021a32  cmp     ax, cx
0x180021a35  jz      short loc_180021A41
0x180021a37  mov     edx, 1B5h
0x180021a3c  jmp     loc_180021919
0x180021a41  mov     r14d, dword ptr [rbp+3Fh+lpsz+8]
0x180021a45  test    r14d, r14d
0x180021a48  jnz     short loc_180021A59
0x180021a4a  mov     ebx, 8007000Dh
0x180021a4f  mov     edx, 1B6h
0x180021a54  jmp     loc_180021AF0
0x180021a59  mov     rdx, r14
0x180021a5c  lea     rcx, [rbp+3Fh+pv]
0x180021a60  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<_GUID [0]>(unsigned __int64)
0x180021a65  mov     rdx, rax
0x180021a68  lea     rcx, [rbp+3Fh+pclsid]
0x180021a6c  call    ??4?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180021a71  mov     rcx, [rbp+3Fh+pv]; pv
0x180021a75  mov     [rbp+3Fh+pv], r12
0x180021a79  test    rcx, rcx
0x180021a7c  jz      short loc_180021A84
0x180021a7e  call    cs:__imp_CoTaskMemFree
0x180021a84  mov     rsi, [rbp+3Fh+pclsid]
0x180021a88  test    rsi, rsi
0x180021a8b  jz      short loc_180021AE6
0x180021a8d  mov     ebx, r12d
0x180021a90  cmp     ebx, r14d
0x180021a93  jnb     short loc_180021B09
0x180021a95  mov     eax, ebx
0x180021a97  mov     edx, ebx
0x180021a99  shl     rdx, 4
0x180021a9d  add     rdx, rsi; pclsid
0x180021aa0  mov     rcx, [rbp+3Fh+var_68]
0x180021aa4  mov     rcx, [rcx+rax*8]; lpsz
0x180021aa8  call    cs:__imp_CLSIDFromString
0x180021aae  mov     edi, eax
0x180021ab0  test    eax, eax
0x180021ab2  js      short loc_180021AB8
0x180021ab4  inc     ebx
0x180021ab6  jmp     short loc_180021A90
0x180021ab8  mov     rcx, [rbp+47h]; this
0x180021abc  mov     r9d, edi; char *
0x180021abf  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021ac6  mov     edx, 1BDh; void *
0x180021acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ad0  nop
0x180021ad1  test    rsi, rsi
0x180021ad4  jz      short loc_180021ADF
0x180021ad6  mov     rcx, rsi; pv
0x180021ad9  call    cs:__imp_CoTaskMemFree
0x180021adf  mov     ebx, edi
0x180021ae1  jmp     loc_180021C8A
0x180021ae6  mov     edx, 1BAh; void *
0x180021aeb  mov     ebx, 8007000Eh
0x180021af0  mov     r9d, ebx; char *
0x180021af3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021afa  mov     rcx, [rbp+47h]; this
0x180021afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b03  nop
0x180021b04  jmp     loc_180021C8A
0x180021b09  mov     rbx, r12
0x180021b0c  mov     [rbp+3Fh+var_80], rbx
0x180021b10  test    r15, r15
0x180021b13  jz      short loc_180021B60
0x180021b15  mov     [rbp+3Fh+var_80], r12
0x180021b19  lea     rdx, [rbp+3Fh+var_80]; unsigned __int16 **
0x180021b1d  mov     rcx, r15; struct IPropertyStore *
0x180021b20  call    ?GetDeviceInstanceId@@YAJPEAUIPropertyStore@@PEAPEAG@Z; GetDeviceInstanceId(IPropertyStore *,ushort * *)
0x180021b25  mov     ebx, eax
0x180021b27  test    eax, eax
0x180021b29  jns     short loc_180021B5C
0x180021b2b  mov     rcx, [rbp+47h]; this
0x180021b2f  mov     r9d, eax; char *
0x180021b32  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021b39  mov     edx, 1C6h; void *
0x180021b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b43  nop
0x180021b44  mov     rcx, [rbp+3Fh+var_80]; pv
0x180021b48  test    rcx, rcx
0x180021b4b  jz      loc_1800219AA
0x180021b51  call    cs:__imp_CoTaskMemFree
0x180021b57  jmp     loc_1800219AA
0x180021b5c  mov     rbx, [rbp+3Fh+var_80]
0x180021b60  mov     r15d, r12d
0x180021b63  cmp     r15d, r14d
0x180021b66  jnb     loc_180021C6A
0x180021b6c  mov     r12d, r15d
0x180021b6f  add     r12, r12
0x180021b72  mov     [rbp+3Fh+pv], 0
0x180021b7a  xor     edx, edx
0x180021b7c  lea     rcx, [rbp+3Fh+pv]
0x180021b80  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180021b85  movups  xmm0, xmmword ptr [rsi+r12*8]
0x180021b8a  movdqu  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x180021b8f  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x180021b93  lea     rdx, [rbp+3Fh+var_50]; struct _GUID
0x180021b97  mov     rcx, r13; struct IPropertyStore *
0x180021b9a  call    ?GetApoDeviceFromFxPropStore@@YAJPEAUIPropertyStore@@U_GUID@@PEAPEAG@Z; GetApoDeviceFromFxPropStore(IPropertyStore *,_GUID,ushort * *)
0x180021b9f  mov     edi, eax
0x180021ba1  test    eax, eax
0x180021ba3  js      loc_180021C2A
0x180021ba9  movups  xmm0, xmmword ptr [rsi+r12*8]
0x180021bae  movdqu  xmmword ptr [rbp+3Fh+var_50.Data1], xmm0
0x180021bb3  lea     r8, [rbp+3Fh+var_50]; struct _GUID
0x180021bb7  mov     rdx, rbx; unsigned __int16 *
0x180021bba  mov     rdi, [rbp+3Fh+pv]
0x180021bbe  mov     rcx, rdi; unsigned __int16 *
0x180021bc1  call    ?LookUpApoRegistration@@YAJPEAG0U_GUID@@@Z; LookUpApoRegistration(ushort *,ushort *,_GUID)
0x180021bc6  mov     r12d, eax
0x180021bc9  test    eax, eax
0x180021bcb  js      short loc_180021BE3
0x180021bcd  xor     r12d, r12d
0x180021bd0  test    rdi, rdi
0x180021bd3  jz      short loc_180021BDE
0x180021bd5  mov     rcx, rdi; pv
0x180021bd8  call    cs:__imp_CoTaskMemFree
0x180021bde  inc     r15d
0x180021be1  jmp     short loc_180021B63
0x180021be3  mov     rcx, [rbp+47h]; this
0x180021be7  mov     r9d, r12d; char *
0x180021bea  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021bf1  mov     edx, 1D3h; void *
0x180021bf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bfb  nop
0x180021bfc  test    rdi, rdi
0x180021bff  jz      short loc_180021C0B
0x180021c01  mov     rcx, rdi; pv
0x180021c04  call    cs:__imp_CoTaskMemFree
0x180021c0a  nop
0x180021c0b  test    rbx, rbx
0x180021c0e  jz      short loc_180021C1A
0x180021c10  mov     rcx, rbx; pv
0x180021c13  call    cs:__imp_CoTaskMemFree
0x180021c19  nop
0x180021c1a  test    rsi, rsi
0x180021c1d  jz      short loc_180021C87
0x180021c1f  mov     rcx, rsi; pv
0x180021c22  call    cs:__imp_CoTaskMemFree
0x180021c28  jmp     short loc_180021C87
0x180021c2a  mov     rcx, [rbp+47h]; this
0x180021c2e  mov     r9d, edi; char *
0x180021c31  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\server\\lib\\audioen"...
0x180021c38  mov     edx, 1D2h; void *
0x180021c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021c42  nop
0x180021c43  mov     rcx, [rbp+3Fh+pv]; pv
0x180021c47  test    rcx, rcx
0x180021c4a  jz      short loc_180021C53
0x180021c4c  call    cs:__imp_CoTaskMemFree
0x180021c52  nop
0x180021c53  test    rbx, rbx
0x180021c56  jz      loc_180021AD1
0x180021c5c  mov     rcx, rbx; pv
0x180021c5f  call    cs:__imp_CoTaskMemFree
0x180021c65  jmp     loc_180021AD1
0x180021c6a  mov     rax, [rbp+3Fh+var_60]
0x180021c6e  mov     [rax], rsi
0x180021c71  mov     rax, [rbp+3Fh+var_58]
0x180021c75  mov     [rax], r14d
0x180021c78  test    rbx, rbx
0x180021c7b  jz      short loc_180021C87
0x180021c7d  mov     rcx, rbx; pv
0x180021c80  call    cs:__imp_CoTaskMemFree
0x180021c86  nop
0x180021c87  mov     ebx, r12d
0x180021c8a  lea     rcx, [rbp+3Fh+lpsz]; pvar
0x180021c8e  call    cs:__imp_PropVariantClear
0x180021c94  mov     eax, ebx
0x180021c96  add     rsp, 88h
0x180021c9d  pop     r15
0x180021c9f  pop     r14
0x180021ca1  pop     r13
0x180021ca3  pop     r12
0x180021ca5  pop     rdi
0x180021ca6  pop     rsi
0x180021ca7  pop     rbx
0x180021ca8  pop     rbp
0x180021ca9  retn
```
