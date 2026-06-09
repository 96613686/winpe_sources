# Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(ushort const *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x18005d938`
- end: `0x18005ddd9`
- name: `?LoadInternal@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAPEAEPEAKPEA_K@Z`
- size: `1185`
- prototype: `__int64 __fastcall(__int64 **this, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a478`
- `0x18005c204`

## callees

- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180024fd0`
- `0x180047904`
- `0x18005b950`
- `0x18005d938`
- `0x18005f34c`
- `0x18005f7bc`
- `0x18005f914`
- `0x180077e10`
- `0x180077e30`
- `0x180091b04`
- `0x1800c8458`
- `0x1801201a0`
- `0x18013b170`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005daf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dc8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dcd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005daf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005db9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dc8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dcd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(
        __int64 **this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int64 *a5)
{
  unsigned int *v5; // r15
  unsigned __int8 **v6; // r14
  unsigned __int64 *v9; // r12
  char v10; // di
  int v11; // eax
  int RootFromAttribute; // ebx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  HKEY *v16; // r9
  LPVOID v17; // r12
  LPVOID *v18; // r14
  void *v19; // r15
  int v20; // eax
  __int64 *v21; // rcx
  __int64 v22; // rax
  void *v23; // rcx
  void *v24; // rcx
  __int64 v25; // rdx
  void *v26; // rcx
  unsigned int v28; // edx
  unsigned __int64 i; // rcx
  LPVOID v30; // rbx
  unsigned int v31; // edi
  char v32; // si
  _QWORD *v33; // rax
  int v34; // ecx
  void *v35; // rcx
  bool v36; // zf
  __int64 *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rdx
  int v40; // [rsp+20h] [rbp-B1h]
  int *v41; // [rsp+20h] [rbp-B1h]
  LPVOID pv; // [rsp+40h] [rbp-91h] BYREF
  unsigned int v43; // [rsp+48h] [rbp-89h]
  LPVOID v44; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-79h]
  char v46[8]; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int8 **v47; // [rsp+68h] [rbp-69h]
  unsigned int *v48; // [rsp+70h] [rbp-61h]
  unsigned __int64 *v49; // [rsp+78h] [rbp-59h]
  LPVOID *p_pv; // [rsp+80h] [rbp-51h] BYREF
  int v51[2]; // [rsp+88h] [rbp-49h] BYREF
  char v52; // [rsp+90h] [rbp-41h]
  __int128 v53; // [rsp+A0h] [rbp-31h] BYREF
  _BYTE v54[32]; // [rsp+B0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v5 = a4;
  v48 = a4;
  v6 = a3;
  v47 = a3;
  v9 = a5;
  v49 = a5;
  v10 = 0;
  v43 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v53 = 0;
  v11 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)this);
  RootFromAttribute = v11;
  if ( v11 < 0 )
  {
    v25 = 4511;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, __int128 *))(*this[60] + 32))(
            this[60],
            a2,
            &v53);
    RootFromAttribute = v11;
    if ( v11 >= 0 )
    {
      RootFromAttribute = 0;
      goto LABEL_4;
    }
    v25 = 4512;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
    (const char *)(unsigned int)v11,
    v40);
LABEL_4:
  if ( RootFromAttribute < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11BE,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)RootFromAttribute,
      v40);
    return (unsigned int)RootFromAttribute;
  }
  v44 = 0;
  p_pv = &v44;
  *(_QWORD *)v51 = 0;
  v52 = 1;
  RootFromAttribute = CloudStoreUtilities::GetRootFromAttribute(this + 29, (unsigned int)v53, v13, v51);
  if ( v52 )
  {
    v17 = *(LPVOID *)v51;
    v18 = p_pv;
    v19 = *p_pv;
    if ( *p_pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v46);
      CoTaskMemFree(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v46);
    }
    *v18 = v17;
    v6 = v47;
    v5 = v48;
    v9 = v49;
  }
  if ( RootFromAttribute < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C0,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)RootFromAttribute,
      v40);
LABEL_43:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v44);
    return (unsigned int)RootFromAttribute;
  }
  v20 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache((RTL_SRWLOCK *)this, v14, v15, v16);
  RootFromAttribute = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C1,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)v20,
      v40);
    goto LABEL_23;
  }
  pv = 0;
  v43 = 0;
  v45 = 0;
  v21 = this[62];
  v22 = *v21;
  p_pv = &pv;
  *(_QWORD *)v51 = 0;
  v52 = 1;
  RootFromAttribute = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, LPVOID, const unsigned __int16 *))(v22 + 24))(
                        v21,
                        a2,
                        v44,
                        L"Current");
  if ( v52 )
  {
    v23 = *p_pv;
    *p_pv = *(LPVOID *)v51;
    if ( v23 )
      CoTaskMemFree(v23);
  }
  if ( RootFromAttribute != -2147024894 )
  {
    if ( RootFromAttribute >= 0 )
      goto LABEL_32;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C7,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)RootFromAttribute,
      (int)v51);
    v26 = pv;
    pv = 0;
    if ( v26 )
      CoTaskMemFree(v26);
LABEL_23:
    if ( v44 )
      CoTaskMemFree(v44);
    return (unsigned int)RootFromAttribute;
  }
  if ( (_DWORD)v53 != 1 )
    goto LABEL_16;
  v37 = this[62];
  v38 = *v37;
  p_pv = &pv;
  *(_QWORD *)v51 = 0;
  v52 = 1;
  v41 = v51;
  RootFromAttribute = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, LPVOID, const unsigned __int16 *))(v38 + 24))(
                        v37,
                        a2,
                        v44,
                        L"Cloud");
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( RootFromAttribute == -2147024894 )
  {
LABEL_16:
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    goto LABEL_29;
  }
  if ( RootFromAttribute < 0 )
  {
    v39 = 4558;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)RootFromAttribute,
      (int)v41);
    v35 = pv;
    v36 = pv == 0;
    pv = 0;
    if ( !v36 )
      CoTaskMemFree(v35);
    goto LABEL_43;
  }
LABEL_32:
  v28 = v43;
  if ( v43 )
  {
    if ( v43 < 4uLL )
    {
LABEL_50:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x11DF,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)0x80070570LL,
        (int)v51);
      if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
      {
        v30 = pv;
        v31 = v43;
        v32 = v45;
        std::wstring::wstring(&p_pv);
        v33 = (_QWORD *)WideStringToUtf8String(v54, &p_pv);
        if ( v33[3] > 0xFu )
          v33 = (_QWORD *)*v33;
        McTemplateU0ssxqbr3_EventWriteTransfer(
          v34,
          (unsigned int)LoadedCorruptData,
          (unsigned int)byte_1802299F5,
          (_DWORD)v33,
          v32,
          v31,
          (__int64)v30);
        v10 = 3;
      }
      if ( (v10 & 2) != 0 )
      {
        v10 &= ~2u;
        std::string::_Tidy_deallocate(v54);
      }
      if ( (v10 & 1) != 0 )
        std::wstring::~wstring(&p_pv);
      RootFromAttribute = -2147024894;
      v39 = 4579;
      goto LABEL_41;
    }
    for ( i = 0; i < 4; ++i )
    {
      if ( *((_BYTE *)pv + i) != *((_BYTE *)&qword_18022A7F0 + i) )
        goto LABEL_50;
    }
  }
  *v6 = (unsigned __int8 *)pv;
  *v5 = v28;
  *v9 = v45;
  pv = 0;
LABEL_29:
  if ( v44 )
    CoTaskMemFree(v44);
  return 0;
}

```

## disassembly

```asm
0x18005d938  push    rbp
0x18005d93a  push    rbx
0x18005d93b  push    rsi
0x18005d93c  push    rdi
0x18005d93d  push    r12
0x18005d93f  push    r13
0x18005d941  push    r14
0x18005d943  push    r15
0x18005d945  lea     rbp, [rsp-17h]
0x18005d94a  sub     rsp, 0E8h
0x18005d951  mov     rax, cs:__security_cookie
0x18005d958  xor     rax, rsp
0x18005d95b  mov     [rbp+4Fh+var_50], rax
0x18005d95f  mov     r15, r9
0x18005d962  mov     [rbp+4Fh+var_B0], r9
0x18005d966  mov     r14, r8
0x18005d969  mov     [rbp+4Fh+var_B8], r8
0x18005d96d  mov     r13, rdx
0x18005d970  mov     rsi, rcx
0x18005d973  mov     r12, [rbp+4Fh+arg_20]
0x18005d977  mov     [rbp+4Fh+var_A8], r12
0x18005d97b  xor     eax, eax
0x18005d97d  mov     edi, eax
0x18005d97f  mov     [rsp+120h+var_D8], eax
0x18005d983  mov     [r8], rax
0x18005d986  mov     [r9], eax
0x18005d989  mov     [r12], rax
0x18005d98d  xorps   xmm0, xmm0
0x18005d990  movups  [rbp+4Fh+var_80], xmm0
0x18005d994  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x18005d999  mov     ebx, eax
0x18005d99b  test    eax, eax
0x18005d99d  js      loc_18005DCA4
0x18005d9a3  mov     rcx, [rsi+1E0h]
0x18005d9aa  mov     rax, [rcx]
0x18005d9ad  lea     r8, [rbp+4Fh+var_80]
0x18005d9b1  mov     rdx, r13
0x18005d9b4  mov     rax, [rax+20h]
0x18005d9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9bd  mov     ebx, eax
0x18005d9bf  test    eax, eax
0x18005d9c1  js      loc_18005DB00
0x18005d9c7  xor     ebx, ebx
0x18005d9c9  test    ebx, ebx
0x18005d9cb  js      loc_18005DCAE
0x18005d9d1  mov     [rsp+120h+var_D0], 0
0x18005d9da  lea     rax, [rsp+120h+var_D0]
0x18005d9df  mov     [rbp+4Fh+var_A0], rax
0x18005d9e3  mov     qword ptr [rbp+4Fh+var_98], 0
0x18005d9eb  mov     [rbp+4Fh+var_90], 1
0x18005d9ef  lea     rcx, [rsi+0E8h]
0x18005d9f6  lea     r9, [rbp+4Fh+var_98]
0x18005d9fa  mov     edx, dword ptr [rbp+4Fh+var_80]
0x18005d9fd  call    ?GetRootFromAttribute@CloudStoreUtilities@@YAJAEBVEffectiveWebAccountContext@@W4ScopeValue@@W4TRIBIT@@PEAPEAG@Z; CloudStoreUtilities::GetRootFromAttribute(EffectiveWebAccountContext const &,ScopeValue,TRIBIT,ushort * *)
0x18005da02  mov     ebx, eax
0x18005da04  cmp     [rbp+4Fh+var_90], 0
0x18005da08  jz      short loc_18005DA2D
0x18005da0a  mov     r12, qword ptr [rbp+4Fh+var_98]
0x18005da0e  mov     r14, [rbp+4Fh+var_A0]
0x18005da12  mov     r15, [r14]
0x18005da15  test    r15, r15
0x18005da18  jnz     loc_18005DCCB
0x18005da1e  mov     [r14], r12
0x18005da21  mov     r14, [rbp+4Fh+var_B8]
0x18005da25  mov     r15, [rbp+4Fh+var_B0]
0x18005da29  mov     r12, [rbp+4Fh+var_A8]
0x18005da2d  test    ebx, ebx
0x18005da2f  js      loc_18005DCEB
0x18005da35  mov     rcx, rsi; this
0x18005da38  call    ?EnsureCloudStoreCache@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache(void)
0x18005da3d  mov     ebx, eax
0x18005da3f  xor     r8d, r8d
0x18005da42  test    eax, eax
0x18005da44  js      loc_18005DB1D
0x18005da4a  mov     [rsp+120h+pv], r8
0x18005da4f  mov     [rsp+120h+var_D8], r8d
0x18005da54  mov     [rbp+4Fh+var_C8], r8
0x18005da58  mov     rcx, [rsi+1F0h]
0x18005da5f  mov     rax, [rcx]
0x18005da62  lea     rdx, [rsp+120h+pv]
0x18005da67  mov     [rbp+4Fh+var_A0], rdx
0x18005da6b  mov     qword ptr [rbp+4Fh+var_98], r8
0x18005da6f  mov     [rbp+4Fh+var_90], 1
0x18005da73  lea     rdx, [rbp+4Fh+var_C8]
0x18005da77  mov     [rsp+120h+var_F0], rdx
0x18005da7c  lea     rdx, [rsp+120h+var_D8]
0x18005da81  mov     [rsp+120h+var_F8], rdx
0x18005da86  lea     rdx, [rbp+4Fh+var_98]
0x18005da8a  mov     qword ptr [rsp+120h+var_100], rdx; int
0x18005da8f  lea     r9, aCurrent_1; "Current"
0x18005da96  mov     r8, [rsp+120h+var_D0]
0x18005da9b  mov     rdx, r13
0x18005da9e  mov     rax, [rax+18h]
0x18005daa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daa7  mov     ebx, eax
0x18005daa9  cmp     [rbp+4Fh+var_90], 0
0x18005daad  jz      short loc_18005DAC8
0x18005daaf  mov     r8, [rbp+4Fh+var_A0]
0x18005dab3  mov     rcx, [r8]; pv
0x18005dab6  mov     rdx, qword ptr [rbp+4Fh+var_98]
0x18005daba  mov     [r8], rdx
0x18005dabd  test    rcx, rcx
0x18005dac0  jz      short loc_18005DAC8
0x18005dac2  call    cs:__imp_CoTaskMemFree
0x18005dac8  cmp     ebx, 80070002h
0x18005dace  jnz     loc_18005DBC9
0x18005dad4  cmp     dword ptr [rbp+4Fh+var_80], 1
0x18005dad8  jz      loc_18005DD05
0x18005dade  mov     rcx, [rsp+120h+pv]; pv
0x18005dae3  mov     [rsp+120h+pv], 0
0x18005daec  test    rcx, rcx
0x18005daef  jz      loc_18005DBBD
0x18005daf5  call    cs:__imp_CoTaskMemFree
0x18005dafb  jmp     loc_18005DBBD
0x18005db00  mov     edx, 11A0h; void *
0x18005db05  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005db0c  mov     r9d, eax; char *
0x18005db0f  mov     rcx, [rbp+57h]; this
0x18005db13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db18  jmp     loc_18005D9C9
0x18005db1d  mov     rcx, [rbp+57h]; this
0x18005db21  mov     r9d, ebx; char *
0x18005db24  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005db2b  mov     edx, 11C1h; void *
0x18005db30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db35  jmp     short loc_18005DB68
0x18005db37  mov     rcx, [rbp+57h]; this
0x18005db3b  mov     r9d, ebx; char *
0x18005db3e  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005db45  mov     edx, 11C7h; void *
0x18005db4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db4f  mov     rcx, [rsp+120h+pv]; pv
0x18005db54  mov     [rsp+120h+pv], 0
0x18005db5d  test    rcx, rcx
0x18005db60  jz      short loc_18005DB68
0x18005db62  call    cs:__imp_CoTaskMemFree
0x18005db68  mov     rcx, [rsp+120h+var_D0]; pv
0x18005db6d  test    rcx, rcx
0x18005db70  jnz     short loc_18005DB9E
0x18005db72  mov     eax, ebx
0x18005db74  jmp     short loc_18005DB7E
0x18005db76  call    cs:__imp_CoTaskMemFree
0x18005db7c  xor     eax, eax
0x18005db7e  mov     rcx, [rbp+4Fh+var_50]
0x18005db82  xor     rcx, rsp; StackCookie
0x18005db85  call    __security_check_cookie
0x18005db8a  add     rsp, 0E8h
0x18005db91  pop     r15
0x18005db93  pop     r14
0x18005db95  pop     r13
0x18005db97  pop     r12
0x18005db99  pop     rdi
0x18005db9a  pop     rsi
0x18005db9b  pop     rbx
0x18005db9c  pop     rbp
0x18005db9d  retn
0x18005db9e  call    cs:__imp_CoTaskMemFree
0x18005dba4  jmp     short loc_18005DB72
0x18005dba6  mov     [r14], r8
0x18005dba9  mov     [r15], edx
0x18005dbac  mov     rax, [rbp+4Fh+var_C8]
0x18005dbb0  mov     [r12], rax
0x18005dbb4  mov     [rsp+120h+pv], 0
0x18005dbbd  mov     rcx, [rsp+120h+var_D0]; pv
0x18005dbc2  test    rcx, rcx
0x18005dbc5  jnz     short loc_18005DB76
0x18005dbc7  jmp     short loc_18005DB7C
0x18005dbc9  test    ebx, ebx
0x18005dbcb  js      loc_18005DB37
0x18005dbd1  mov     edx, [rsp+120h+var_D8]
0x18005dbd5  mov     eax, edx
0x18005dbd7  mov     r8, [rsp+120h+pv]
0x18005dbdc  test    edx, edx
0x18005dbde  jz      short loc_18005DBA6
0x18005dbe0  cmp     rax, 4
0x18005dbe4  jb      loc_18005DD81
0x18005dbea  xor     ecx, ecx
0x18005dbec  cmp     rcx, 4
0x18005dbf0  jnb     short loc_18005DBA6
0x18005dbf2  lea     rax, qword_18022A7F0
0x18005dbf9  mov     al, [rcx+rax]
0x18005dbfc  cmp     [r8+rcx], al
0x18005dc00  jnz     loc_18005DD81
0x18005dc06  inc     rcx
0x18005dc09  jmp     short loc_18005DBEC
0x18005dc0b  mov     rbx, [rsp+120h+pv]
0x18005dc10  mov     edi, [rsp+120h+var_D8]
0x18005dc14  mov     rsi, [rbp+4Fh+var_C8]
0x18005dc18  mov     rdx, r13
0x18005dc1b  lea     rcx, [rbp+4Fh+var_A0]
0x18005dc1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005dc24  lea     rdx, [rbp+4Fh+var_A0]
0x18005dc28  lea     rcx, [rbp+4Fh+var_70]
0x18005dc2c  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x18005dc31  cmp     qword ptr [rax+18h], 0Fh
0x18005dc36  jbe     short loc_18005DC3B
0x18005dc38  mov     rax, [rax]
0x18005dc3b  mov     [rsp+120h+var_F0], rbx
0x18005dc40  mov     dword ptr [rsp+120h+var_F8], edi
0x18005dc44  mov     qword ptr [rsp+120h+var_100], rsi
0x18005dc49  mov     r9, rax
0x18005dc4c  lea     r8, byte_1802299F5
0x18005dc53  lea     rdx, LoadedCorruptData
0x18005dc5a  call    McTemplateU0ssxqbr3_EventWriteTransfer
0x18005dc5f  mov     edi, 3
0x18005dc64  jmp     loc_18005DDA9
0x18005dc69  mov     r9d, ebx; char *
0x18005dc6c  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005dc73  mov     rcx, [rbp+57h]; this
0x18005dc77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dc7c  mov     rcx, [rsp+120h+pv]; pv
0x18005dc81  test    rcx, rcx
0x18005dc84  mov     [rsp+120h+pv], 0
0x18005dc8d  jz      short loc_18005DC95
0x18005dc8f  call    cs:__imp_CoTaskMemFree
0x18005dc95  lea     rcx, [rsp+120h+var_D0]
0x18005dc9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005dc9f  jmp     loc_18005DB72
0x18005dca4  mov     edx, 119Fh
0x18005dca9  jmp     loc_18005DB05
0x18005dcae  mov     rcx, [rbp+57h]; this
0x18005dcb2  mov     r9d, ebx; char *
0x18005dcb5  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005dcbc  mov     edx, 11BEh; void *
0x18005dcc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dcc6  jmp     loc_18005DB72
0x18005dccb  lea     rcx, [rbp+4Fh+var_C0]; this
0x18005dccf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005dcd4  mov     rcx, r15; pv
0x18005dcd7  call    cs:__imp_CoTaskMemFree
0x18005dcdd  lea     rcx, [rbp+4Fh+var_C0]; this
0x18005dce1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005dce6  jmp     loc_18005DA1E
0x18005dceb  mov     rcx, [rbp+57h]; this
0x18005dcef  mov     r9d, ebx; char *
0x18005dcf2  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005dcf9  mov     edx, 11C0h; void *
0x18005dcfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dd03  jmp     short loc_18005DC95
0x18005dd05  mov     rcx, [rsi+1F0h]
0x18005dd0c  mov     rax, [rcx]
0x18005dd0f  lea     rdx, [rsp+120h+pv]
0x18005dd14  mov     [rbp+4Fh+var_A0], rdx
0x18005dd18  mov     qword ptr [rbp+4Fh+var_98], 0
0x18005dd20  mov     [rbp+4Fh+var_90], 1
0x18005dd24  lea     rdx, [rbp+4Fh+var_C8]
0x18005dd28  mov     [rsp+120h+var_F0], rdx
0x18005dd2d  lea     rdx, [rsp+120h+var_D8]
0x18005dd32  mov     [rsp+120h+var_F8], rdx
0x18005dd37  lea     rdx, [rbp+4Fh+var_98]
0x18005dd3b  mov     qword ptr [rsp+120h+var_100], rdx; int
0x18005dd40  lea     r9, aCloud; "Cloud"
0x18005dd47  mov     r8, [rsp+120h+var_D0]
0x18005dd4c  mov     rdx, r13
0x18005dd4f  mov     rax, [rax+18h]
0x18005dd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dd58  mov     ebx, eax
0x18005dd5a  lea     rcx, [rbp+4Fh+var_A0]
0x18005dd5e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18005dd63  cmp     ebx, 80070002h
0x18005dd69  jz      loc_18005DADE
0x18005dd6f  test    ebx, ebx
0x18005dd71  jns     loc_18005DBD1
0x18005dd77  mov     edx, 11CEh; void *
0x18005dd7c  jmp     loc_18005DC69
0x18005dd81  mov     rcx, [rbp+57h]; this
0x18005dd85  mov     r9d, 80070570h; char *
0x18005dd8b  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18005dd92  mov     edx, 11DFh; void *
0x18005dd97  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18005dd9c  test    cs:Microsoft_Windows_CloudStoreEnableBits, 1
0x18005dda3  jnz     loc_18005DC0B
0x18005dda9  test    dil, 2
0x18005ddad  jz      short loc_18005DDBB
0x18005ddaf  and     edi, 0FFFFFFFDh
0x18005ddb2  lea     rcx, [rbp+4Fh+var_70]; void *
0x18005ddb6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005ddbb  test    dil, 1
0x18005ddbf  jz      short loc_18005DDCA
0x18005ddc1  lea     rcx, [rbp+4Fh+var_A0]
0x18005ddc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ddca  mov     ebx, 80070002h
0x18005ddcf  mov     edx, 11E3h
0x18005ddd4  jmp     loc_18005DC69
```
