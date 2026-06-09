# Windows::Internal::Storage::Cloud::CloudStoreCache::CleanupSyncData(ushort const *,CSimpleEnumString *)

- ea: `0x1801a93a4`
- end: `0x1801a966c`
- name: `?CleanupSyncData@CloudStoreCache@Cloud@Storage@Internal@Windows@@QEAAJPEBGPEAVCSimpleEnumString@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreCache *__hidden this, const unsigned __int16 *, struct CSimpleEnumString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18010de2c`

## callees

- `0x18000f4b4`
- `0x180047904`
- `0x180062040`
- `0x18007d4c4`
- `0x180091b04`
- `0x1800c8458`
- `0x1801a8f00`
- `0x1801a93a4`
- `0x1801c273c`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a957c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a95fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9632`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a957c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a95fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9632`

## string_xrefs

- `0x1801a9403`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x1801a95db`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x1801a9613`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::CleanupSyncData(
        Windows::Internal::Storage::Cloud::CloudStoreCache *this,
        const unsigned __int16 *a2,
        struct CSimpleEnumString *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, const unsigned __int16 *, __int64 **); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // ebx
  int v12; // esi
  int v13; // eax
  int v14; // edi
  int v15; // r8d
  int v16; // eax
  void *v17; // rcx
  bool v18; // zf
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rcx
  void *v21; // rcx
  int v23; // [rsp+20h] [rbp-59h]
  int v24; // [rsp+20h] [rbp-59h]
  int v25; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v26; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v28; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v29; // [rsp+58h] [rbp-21h] BYREF
  int v30; // [rsp+60h] [rbp-19h] BYREF
  Windows::Internal::Storage::Cloud *v31; // [rsp+64h] [rbp-15h]
  int v32; // [rsp+6Ch] [rbp-Dh]
  int v33; // [rsp+70h] [rbp-9h] BYREF
  __int64 v34; // [rsp+74h] [rbp-5h]
  int v35; // [rsp+7Ch] [rbp+3h]
  void *p_pv; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int8 *v37; // [rsp+88h] [rbp+Fh] BYREF
  char v38; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  unsigned int v40; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v41; // [rsp+F8h] [rbp+7Fh] BYREF

  v29 = 0;
  v6 = *((_QWORD *)this + 2);
  v7 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 **))(*(_QWORD *)v6 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v8 = v7(v6, a2, &v29);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)(unsigned int)v8,
      v23);
    goto LABEL_27;
  }
  v28 = 0;
  while ( 1 )
  {
    v10 = *v29;
    p_pv = &v28;
    v37 = 0;
    v38 = 1;
    v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned __int8 **))(v10 + 24))(v29, 1, &v37);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
    if ( v11 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
      v9 = 0;
      goto LABEL_27;
    }
    v30 = 2;
    v31 = 0;
    v32 = 0;
    v26 = 0;
    v40 = 0;
    p_pv = &v26;
    v37 = 0;
    v38 = 1;
    v12 = Windows::Internal::Storage::Cloud::CloudStoreCache::Load(
            this,
            v28,
            a2,
            L"Cloud",
            0,
            (struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&v30,
            &v37,
            &v40);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v12 >= 0 && v32 == 1 )
    {
      v13 = CSimpleEnumString::AddString(a3, v26);
      v9 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
          (const char *)(unsigned int)v13,
          v24);
        goto LABEL_21;
      }
    }
    v33 = 2;
    v34 = 0;
    v35 = 0;
    pv = 0;
    p_pv = &pv;
    v37 = 0;
    v38 = 1;
    v14 = Windows::Internal::Storage::Cloud::CloudStoreCache::Load(
            this,
            v28,
            a2,
            L"Current",
            0,
            (struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&v33,
            &v37,
            &v41);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v14 >= 0 )
    {
      if ( v35 != 1 )
        goto LABEL_12;
      v16 = CSimpleEnumString::AddString(a3, (const unsigned __int16 *)pv);
      v9 = v16;
      if ( v16 < 0 )
        break;
    }
    if ( v14 == -2147024894
      && v12 >= 0
      && !v40
      && Windows::Internal::Storage::Cloud::IsVersionOlderThanNDays(v31, 0x1Eu, v15) )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 2) + 56LL))(
        *((_QWORD *)this + 2),
        v28,
        a2);
    }
LABEL_12:
    v17 = pv;
    v18 = pv == 0;
    pv = 0;
    if ( !v18 )
      CoTaskMemFree(v17);
    v19 = v26;
    v26 = 0;
    if ( v19 )
      CoTaskMemFree(v19);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x112,
    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
    (const char *)(unsigned int)v16,
    v25);
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
LABEL_21:
  v20 = v26;
  v18 = v26 == 0;
  v26 = 0;
  if ( !v18 )
    CoTaskMemFree(v20);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v28);
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  return v9;
}

```

## disassembly

```asm
0x1801a93a4  mov     [rsp-8+arg_8], rbx
0x1801a93a9  push    rbp
0x1801a93aa  push    rsi
0x1801a93ab  push    rdi
0x1801a93ac  push    r12
0x1801a93ae  push    r13
0x1801a93b0  push    r14
0x1801a93b2  push    r15
0x1801a93b4  lea     rbp, [rsp-27h]
0x1801a93b9  sub     rsp, 0A0h
0x1801a93c0  mov     r12, r8
0x1801a93c3  mov     r14, rdx
0x1801a93c6  mov     r15, rcx
0x1801a93c9  xor     r13d, r13d
0x1801a93cc  mov     [rbp+57h+var_78], r13
0x1801a93d0  mov     rdi, [rcx+10h]
0x1801a93d4  mov     rax, [rdi]
0x1801a93d7  mov     rbx, [rax+40h]
0x1801a93db  lea     rcx, [rbp+57h+var_78]
0x1801a93df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a93e4  lea     r8, [rbp+57h+var_78]
0x1801a93e8  mov     rdx, r14
0x1801a93eb  mov     rcx, rdi
0x1801a93ee  mov     rax, rbx
0x1801a93f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a93f6  mov     ebx, eax
0x1801a93f8  test    eax, eax
0x1801a93fa  jns     short loc_1801A9419
0x1801a93fc  mov     rcx, [rbp+5Fh]; this
0x1801a9400  mov     r9d, eax; char *
0x1801a9403  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a940a  mov     edx, 0FDh; void *
0x1801a940f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9414  jmp     loc_1801A9646
0x1801a9419  mov     [rbp+57h+var_80], r13
0x1801a941d  mov     rcx, [rbp+57h+var_78]
0x1801a9421  mov     rax, [rcx]
0x1801a9424  lea     rdx, [rbp+57h+var_80]
0x1801a9428  mov     [rbp+57h+var_50], rdx
0x1801a942c  mov     [rbp+57h+var_48], r13
0x1801a9430  mov     [rbp+57h+var_40], 1
0x1801a9434  xor     r9d, r9d
0x1801a9437  lea     r8, [rbp+57h+var_48]
0x1801a943b  lea     edx, [r9+1]
0x1801a943f  mov     rax, [rax+18h]
0x1801a9443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9448  mov     ebx, eax
0x1801a944a  lea     rcx, [rbp+57h+var_50]
0x1801a944e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1801a9453  test    ebx, ebx
0x1801a9455  jnz     loc_1801A963A
0x1801a945b  mov     [rbp+57h+var_70], 2
0x1801a9462  mov     [rbp+57h+var_6C], r13
0x1801a9466  mov     [rbp+57h+var_64], r13d
0x1801a946a  mov     [rbp+57h+var_90], r13
0x1801a946e  mov     [rbp+57h+arg_0], r13d
0x1801a9472  lea     rax, [rbp+57h+var_90]
0x1801a9476  mov     [rbp+57h+var_50], rax
0x1801a947a  mov     [rbp+57h+var_48], r13
0x1801a947e  mov     [rbp+57h+var_40], 1
0x1801a9482  lea     rax, [rbp+57h+arg_0]
0x1801a9486  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x1801a948b  lea     rax, [rbp+57h+var_48]
0x1801a948f  mov     [rsp+0D0h+var_A0], rax; unsigned __int8 **
0x1801a9494  lea     rax, [rbp+57h+var_70]
0x1801a9498  mov     [rsp+0D0h+var_A8], rax; struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *
0x1801a949d  mov     [rsp+0D0h+var_B0], r13b; int
0x1801a94a2  lea     r9, aCloud; "Cloud"
0x1801a94a9  mov     r8, r14; unsigned __int16 *
0x1801a94ac  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1801a94b0  mov     rcx, r15; this
0x1801a94b3  call    ?Load@CloudStoreCache@Cloud@Storage@Internal@Windows@@QEAAJPEBG00_NPEAVCloudStoreMetadata@2345@PEAPEAEPEAK@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::Load(ushort const *,ushort const *,ushort const *,bool,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar * *,ulong *)
0x1801a94b8  mov     esi, eax
0x1801a94ba  lea     rcx, [rbp+57h+var_50]
0x1801a94be  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801a94c3  test    esi, esi
0x1801a94c5  js      short loc_1801A94E3
0x1801a94c7  cmp     [rbp+57h+var_64], 1
0x1801a94cb  jnz     short loc_1801A94E3
0x1801a94cd  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1801a94d1  mov     rcx, r12; this
0x1801a94d4  call    ?AddString@CSimpleEnumString@@QEAAJPEBG@Z; CSimpleEnumString::AddString(ushort const *)
0x1801a94d9  mov     ebx, eax
0x1801a94db  test    eax, eax
0x1801a94dd  js      loc_1801A95D4
0x1801a94e3  mov     [rbp+57h+var_60], 2
0x1801a94ea  mov     [rbp+57h+var_5C], r13
0x1801a94ee  mov     [rbp+57h+var_54], r13d
0x1801a94f2  mov     [rbp+57h+pv], r13
0x1801a94f6  lea     rax, [rbp+57h+pv]
0x1801a94fa  mov     [rbp+57h+var_50], rax
0x1801a94fe  mov     [rbp+57h+var_48], r13
0x1801a9502  mov     [rbp+57h+var_40], 1
0x1801a9506  lea     rax, [rbp+57h+arg_18]
0x1801a950a  mov     [rsp+0D0h+var_98], rax; unsigned int *
0x1801a950f  lea     rax, [rbp+57h+var_48]
0x1801a9513  mov     [rsp+0D0h+var_A0], rax; unsigned __int8 **
0x1801a9518  lea     rax, [rbp+57h+var_60]
0x1801a951c  mov     [rsp+0D0h+var_A8], rax; struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *
0x1801a9521  mov     [rsp+0D0h+var_B0], r13b; int
0x1801a9526  lea     r9, aCurrent_1; "Current"
0x1801a952d  mov     r8, r14; unsigned __int16 *
0x1801a9530  mov     rdx, [rbp+57h+var_80]; unsigned __int16 *
0x1801a9534  mov     rcx, r15; this
0x1801a9537  call    ?Load@CloudStoreCache@Cloud@Storage@Internal@Windows@@QEAAJPEBG00_NPEAVCloudStoreMetadata@2345@PEAPEAEPEAK@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::Load(ushort const *,ushort const *,ushort const *,bool,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar * *,ulong *)
0x1801a953c  mov     edi, eax
0x1801a953e  lea     rcx, [rbp+57h+var_50]
0x1801a9542  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801a9547  test    edi, edi
0x1801a9549  js      short loc_1801A9567
0x1801a954b  cmp     [rbp+57h+var_54], 1
0x1801a954f  jnz     short loc_1801A956F
0x1801a9551  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x1801a9555  mov     rcx, r12; this
0x1801a9558  call    ?AddString@CSimpleEnumString@@QEAAJPEBG@Z; CSimpleEnumString::AddString(ushort const *)
0x1801a955d  mov     ebx, eax
0x1801a955f  test    eax, eax
0x1801a9561  js      loc_1801A960C
0x1801a9567  cmp     edi, 80070002h
0x1801a956d  jz      short loc_1801A959F
0x1801a956f  mov     rcx, [rbp+57h+pv]; pv
0x1801a9573  test    rcx, rcx
0x1801a9576  mov     [rbp+57h+pv], r13
0x1801a957a  jz      short loc_1801A9583
0x1801a957c  call    cs:__imp_CoTaskMemFree
0x1801a9582  nop
0x1801a9583  mov     rcx, [rbp+57h+var_90]; pv
0x1801a9587  mov     [rbp+57h+var_90], r13
0x1801a958b  test    rcx, rcx
0x1801a958e  jz      loc_1801A941D
0x1801a9594  call    cs:__imp_CoTaskMemFree
0x1801a959a  jmp     loc_1801A941D
0x1801a959f  test    esi, esi
0x1801a95a1  js      short loc_1801A956F
0x1801a95a3  cmp     [rbp+57h+arg_0], r13d
0x1801a95a7  jnz     short loc_1801A956F
0x1801a95a9  mov     edx, 1Eh; unsigned __int64
0x1801a95ae  mov     rcx, [rbp+57h+var_6C]; this
0x1801a95b2  call    ?IsVersionOlderThanNDays@Cloud@Storage@Internal@Windows@@YA_N_KH@Z; Windows::Internal::Storage::Cloud::IsVersionOlderThanNDays(unsigned __int64,int)
0x1801a95b7  test    al, al
0x1801a95b9  jz      short loc_1801A956F
0x1801a95bb  mov     rcx, [r15+10h]
0x1801a95bf  mov     rax, [rcx]
0x1801a95c2  mov     r8, r14
0x1801a95c5  mov     rdx, [rbp+57h+var_80]
0x1801a95c9  mov     rax, [rax+38h]
0x1801a95cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a95d2  jmp     short loc_1801A956F
0x1801a95d4  mov     rcx, [rbp+5Fh]; this
0x1801a95d8  mov     r9d, eax; char *
0x1801a95db  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a95e2  mov     edx, 109h; void *
0x1801a95e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a95ec  nop
0x1801a95ed  mov     rcx, [rbp+57h+var_90]; pv
0x1801a95f1  test    rcx, rcx
0x1801a95f4  mov     [rbp+57h+var_90], r13
0x1801a95f8  jz      short loc_1801A9601
0x1801a95fa  call    cs:__imp_CoTaskMemFree
0x1801a9600  nop
0x1801a9601  lea     rcx, [rbp+57h+var_80]
0x1801a9605  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a960a  jmp     short loc_1801A9646
0x1801a960c  mov     rcx, [rbp+5Fh]; this
0x1801a9610  mov     r9d, eax; char *
0x1801a9613  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a961a  mov     edx, 112h; void *
0x1801a961f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9624  nop
0x1801a9625  mov     rcx, [rbp+57h+pv]; pv
0x1801a9629  mov     [rbp+57h+pv], r13
0x1801a962d  test    rcx, rcx
0x1801a9630  jz      short loc_1801A95ED
0x1801a9632  call    cs:__imp_CoTaskMemFree
0x1801a9638  jmp     short loc_1801A95ED
0x1801a963a  lea     rcx, [rbp+57h+var_80]
0x1801a963e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a9643  mov     ebx, r13d
0x1801a9646  lea     rcx, [rbp+57h+var_78]
0x1801a964a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a964f  mov     eax, ebx
0x1801a9651  mov     rbx, [rsp+0D0h+arg_8]
0x1801a9659  add     rsp, 0A0h
0x1801a9660  pop     r15
0x1801a9662  pop     r14
0x1801a9664  pop     r13
0x1801a9666  pop     r12
0x1801a9668  pop     rdi
0x1801a9669  pop     rsi
0x1801a966a  pop     rbp
0x1801a966b  retn
```
