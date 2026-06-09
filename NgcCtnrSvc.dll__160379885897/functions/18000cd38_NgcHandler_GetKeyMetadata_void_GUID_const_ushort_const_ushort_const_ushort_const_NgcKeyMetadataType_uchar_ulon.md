# NgcHandler::GetKeyMetadata(void *,_GUID const &,ushort const *,ushort const *,ushort const *,_NgcKeyMetadataType,uchar * *,ulong *)

- ea: `0x18000cd38`
- end: `0x18000d388`
- name: `?GetKeyMetadata@NgcHandler@@QEAAJPEAXAEBU_GUID@@PEBG22W4_NgcKeyMetadataType@@PEAPEAEPEAK@Z`
- size: `1616`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cc40`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000b490`
- `0x18000c7e0`
- `0x18000cd38`
- `0x18000d450`
- `0x180012190`
- `0x1800134a0`
- `0x180014350`
- `0x1800143c0`
- `0x180016eac`
- `0x180018194`
- `0x18002c640`
- `0x18002d500`
- `0x180042a40`
- `0x180047d04`
- `0x18005950c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d13a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d2e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d352`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d13a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d2e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000d352`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d260`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcHandler::GetKeyMetadata(
        __int64 (__fastcall **a1)(LPVOID *, __int64 **),
        unsigned int a2,
        _OWORD *a3,
        void *a4,
        _WORD *a5,
        void *a6,
        int a7,
        _QWORD *a8,
        _DWORD *a9)
{
  int v12; // eax
  int v13; // ebx
  bool v14; // zf
  __int64 (__fastcall *v15)(LPVOID *, __int64 **); // rbx
  __int64 v16; // r9
  __int64 v17; // rax
  _QWORD *v18; // r8
  void *v19; // rcx
  LPVOID v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // r8
  const void *v23; // rdx
  void **v24; // r9
  int *v25; // rdx
  unsigned __int8 *v26; // rdx
  __int64 v28; // rax
  _QWORD *v29; // r8
  __int64 v30; // rax
  _QWORD *v31; // rdx
  LPVOID v32; // rdx
  __int64 v33; // rax
  void *v34; // rcx
  void *v35; // rax
  void *v36; // rdi
  _BYTE v37[8]; // [rsp+40h] [rbp-99h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-91h] BYREF
  size_t size; // [rsp+50h] [rbp-89h] BYREF
  void *Src; // [rsp+58h] [rbp-81h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-79h] BYREF
  char v42; // [rsp+70h] [rbp-69h]
  __int128 v43; // [rsp+80h] [rbp-59h] BYREF
  char v44; // [rsp+90h] [rbp-49h]
  int v45; // [rsp+A0h] [rbp-39h] BYREF
  _DWORD *v46; // [rsp+A8h] [rbp-31h]
  _QWORD v47[3]; // [rsp+B0h] [rbp-29h] BYREF
  unsigned __int64 v48; // [rsp+C8h] [rbp-11h]

  v46 = a9;
  v37[0] = 0;
  v12 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v37, a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v43) = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA251,
        0,
        0,
        (__int64)&v43);
    }
    v14 = v37[0] == 0;
    goto LABEL_83;
  }
  v38 = 0;
  v15 = *a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  *(_OWORD *)pv = *a3;
  v13 = v15(pv, &v38);
  if ( v13 < 0
    || (v45 = 0,
        *(_OWORD *)pv = xmmword_18008F2D8,
        v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, int *))(*v38 + 88))(v38, pv, &v45),
        v13 < 0) )
  {
LABEL_82:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v14 = v37[0] == 0;
LABEL_83:
    if ( !v14 )
      CoUninitialize();
    return (unsigned int)v13;
  }
  if ( !v45 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v43) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)word_1800AA22A,
        0,
        0,
        (__int64)&v43);
    }
    goto LABEL_54;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v47);
  v13 = NgcUtils::NgcContainerKeyName::BuildKeyNameString(a5, a6, a4, (__int64)v47);
  if ( v13 < 0 )
  {
LABEL_81:
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v47);
    goto LABEL_82;
  }
  Src = 0;
  LODWORD(size) = 0;
  if ( a7 > 6 )
  {
    if ( a7 != 7 )
    {
      switch ( a7 )
      {
        case 8:
          v16 = 12;
          goto LABEL_61;
        case 10:
          v16 = 14;
          goto LABEL_61;
        case 11:
          v16 = 15;
          goto LABEL_61;
        case 12:
          v16 = 16;
          goto LABEL_61;
        case 13:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl'::`2'::impl) )
          {
            v16 = 17;
            goto LABEL_61;
          }
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            v26 = (unsigned __int8 *)byte_1800AA1F5;
            goto LABEL_52;
          }
LABEL_53:
          wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &Src,
            0);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v47);
LABEL_54:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          if ( v37[0] )
            CoUninitialize();
          return 2147942487LL;
      }
LABEL_46:
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v26 = (unsigned __int8 *)&unk_1800AA1C0;
LABEL_52:
        LODWORD(pv[0]) = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          v26,
          0,
          0,
          (__int64)pv);
        goto LABEL_53;
      }
      goto LABEL_53;
    }
    pv[0] = 0;
    v30 = *v38;
    *(_QWORD *)&v43 = pv;
    *((_QWORD *)&v43 + 1) = 0;
    v44 = 1;
    v31 = v47;
    if ( v48 > 7 )
      v31 = (_QWORD *)v47[0];
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, __int64, char *))(v30 + 168))(v38, v31, 1, (char *)&v43 + 8);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v43);
    if ( v13 < 0 )
    {
LABEL_24:
      v19 = pv[0];
      pv[0] = 0;
      if ( v19 )
        CoTaskMemFree(v19);
      goto LABEL_80;
    }
    v32 = pv[0];
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)pv[0] + v33) );
    LODWORD(size) = 2 * v33 + 2;
    pv[0] = 0;
    wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &Src,
      v32);
LABEL_71:
    v34 = pv[0];
    v14 = pv[0] == 0;
    pv[0] = 0;
    if ( !v14 )
      CoTaskMemFree(v34);
    goto LABEL_73;
  }
  switch ( a7 )
  {
    case 6:
      v16 = 11;
      goto LABEL_61;
    case 0:
      LODWORD(v43) = 0;
      v21 = *v38;
      v22 = v47;
      if ( v48 > 7 )
        v22 = (_QWORD *)v47[0];
      *(_OWORD *)pv = xmmword_18008F2D8;
      v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, _QWORD *, __int128 *))(v21 + 280))(v38, pv, v22, &v43);
      if ( v13 >= 0 )
      {
        pv[0] = &Src;
        pv[1] = 0;
        v42 = 1;
        v13 = NgcUtils::CoMemAllocCopy((NgcUtils *)&v43, v23, (unsigned __int64)&pv[1], v24);
        wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pv);
        if ( v13 >= 0 )
        {
          LODWORD(size) = 4;
          goto LABEL_73;
        }
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v25 = &dword_1800AA18C;
          goto LABEL_34;
        }
      }
      else if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v25 = &dword_1800AA28C;
LABEL_34:
        LODWORD(pv[0]) = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)v25,
          0,
          0,
          (__int64)pv);
      }
LABEL_80:
      wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &Src,
        0);
      goto LABEL_81;
    case 1:
      v16 = 4;
      goto LABEL_61;
    case 2:
      v16 = 5;
      goto LABEL_61;
    case 3:
      wil::make_unique_cotaskmem<unsigned long,>(pv);
      v17 = *v38;
      v18 = v47;
      if ( v48 > 7 )
        v18 = (_QWORD *)v47[0];
      v43 = xmmword_18008F2D8;
      v13 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, LPVOID))(v17 + 296))(v38, &v43, v18, pv[0]);
      if ( v13 < 0 )
        goto LABEL_24;
      v20 = pv[0];
      pv[0] = 0;
      wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &Src,
        v20);
      LODWORD(size) = 4;
      goto LABEL_71;
    case 4:
      v16 = 7;
      goto LABEL_61;
  }
  if ( a7 != 5 )
    goto LABEL_46;
  v16 = 8;
LABEL_61:
  pv[0] = 0;
  v28 = *v38;
  v29 = v47;
  if ( v48 > 7 )
    v29 = (_QWORD *)v47[0];
  v43 = xmmword_18008F2D8;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD *, __int64, LPVOID *, size_t *))(v28 + 136))(
          v38,
          &v43,
          v29,
          v16,
          pv,
          &size);
  if ( v13 < 0 )
    goto LABEL_80;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &Src,
    pv[0]);
LABEL_73:
  v35 = MIDL_user_allocate((unsigned int)size);
  v36 = v35;
  *(_QWORD *)&v43 = v35;
  if ( v35 )
  {
    memcpy_0(v35, Src, (unsigned int)size);
    *(_QWORD *)&v43 = 0;
    *a8 = v36;
    *v46 = size;
    std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v43);
    goto LABEL_80;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(pv[0]) = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AA15B,
      0,
      0,
      (__int64)pv);
  }
  std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(&v43);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, 0);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  if ( v37[0] )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000cd38  mov     [rsp-8+arg_8], rbx
0x18000cd3d  push    rbp
0x18000cd3e  push    rsi
0x18000cd3f  push    rdi
0x18000cd40  push    r12
0x18000cd42  push    r13
0x18000cd44  push    r14
0x18000cd46  push    r15
0x18000cd48  lea     rbp, [rsp-7]
0x18000cd4d  sub     rsp, 0E0h
0x18000cd54  mov     rax, cs:__security_cookie
0x18000cd5b  xor     rax, rsp
0x18000cd5e  mov     [rbp+37h+var_40], rax
0x18000cd62  mov     r14, r9
0x18000cd65  mov     rsi, r8
0x18000cd68  mov     rdi, rcx
0x18000cd6b  mov     r15, [rbp+37h+arg_20]
0x18000cd6f  mov     r12, [rbp+37h+arg_28]
0x18000cd73  mov     r13, [rbp+37h+arg_38]
0x18000cd77  mov     rax, [rbp+37h+arg_40]
0x18000cd7e  mov     [rbp+37h+var_68], rax
0x18000cd82  mov     [rsp+110h+var_D0], 0
0x18000cd87  lea     rcx, [rsp+110h+var_D0]; this
0x18000cd8c  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18000cd91  mov     ebx, eax
0x18000cd93  test    eax, eax
0x18000cd95  jns     short loc_18000CDD2
0x18000cd97  mov     ecx, cs:dword_1800BE0B8
0x18000cd9d  cmp     ecx, 2
0x18000cda0  jbe     short loc_18000CDC8
0x18000cda2  mov     dword ptr [rbp+37h+var_90], eax
0x18000cda5  lea     rax, [rbp+37h+var_90]
0x18000cda9  mov     [rsp+110h+var_F0], rax
0x18000cdae  xor     r9d, r9d
0x18000cdb1  xor     r8d, r8d
0x18000cdb4  lea     rdx, byte_1800AA251
0x18000cdbb  lea     rcx, dword_1800BE0B8
0x18000cdc2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000cdc7  nop
0x18000cdc8  cmp     [rsp+110h+var_D0], 0
0x18000cdcd  jmp     loc_18000D350
0x18000cdd2  mov     [rsp+110h+var_C8], 0
0x18000cddb  mov     rbx, [rdi]
0x18000cdde  lea     rcx, [rsp+110h+var_C8]
0x18000cde3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cde8  movups  xmm0, xmmword ptr [rsi]
0x18000cdeb  movdqu  xmmword ptr [rbp+37h+pv], xmm0
0x18000cdf0  lea     rdx, [rsp+110h+var_C8]
0x18000cdf5  lea     rcx, [rbp+37h+pv]
0x18000cdf9  mov     rax, rbx
0x18000cdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce01  mov     ebx, eax
0x18000ce03  xor     esi, esi
0x18000ce05  test    eax, eax
0x18000ce07  js      loc_18000D340
0x18000ce0d  mov     [rbp+37h+var_70], esi
0x18000ce10  mov     rcx, [rsp+110h+var_C8]
0x18000ce15  movups  xmm0, cs:xmmword_18008F2D8
0x18000ce1c  movdqu  xmmword ptr [rbp+37h+pv], xmm0
0x18000ce21  mov     rax, [rcx]
0x18000ce24  lea     r8, [rbp+37h+var_70]
0x18000ce28  lea     rdx, [rbp+37h+pv]
0x18000ce2c  mov     rax, [rax+58h]
0x18000ce30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce35  mov     ebx, eax
0x18000ce37  test    eax, eax
0x18000ce39  js      loc_18000D340
0x18000ce3f  cmp     [rbp+37h+var_70], esi
0x18000ce42  jnz     short loc_18000CE81
0x18000ce44  mov     eax, cs:dword_1800BE0B8
0x18000ce4a  cmp     eax, 2
0x18000ce4d  jbe     loc_18000D128
0x18000ce53  mov     dword ptr [rbp+37h+var_90], 80070057h
0x18000ce5a  lea     rax, [rbp+37h+var_90]
0x18000ce5e  mov     [rsp+110h+var_F0], rax
0x18000ce63  xor     r9d, r9d
0x18000ce66  xor     r8d, r8d
0x18000ce69  lea     rdx, word_1800AA22A
0x18000ce70  lea     rcx, dword_1800BE0B8
0x18000ce77  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000ce7c  jmp     loc_18000D128
0x18000ce81  lea     rcx, [rbp+37h+var_60]
0x18000ce85  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18000ce8a  nop
0x18000ce8b  lea     r9, [rbp+37h+var_60]
0x18000ce8f  mov     r8, r14
0x18000ce92  mov     rdx, r12
0x18000ce95  mov     rcx, r15; Src
0x18000ce98  call    ?BuildKeyNameString@NgcContainerKeyName@NgcUtils@@YAJPEBG00PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::NgcContainerKeyName::BuildKeyNameString(ushort const *,ushort const *,ushort const *,std::wstring *)
0x18000ce9d  mov     ebx, eax
0x18000ce9f  test    eax, eax
0x18000cea1  js      loc_18000D336
0x18000cea7  mov     [rsp+110h+Src], rsi
0x18000ceac  mov     dword ptr [rsp+110h+size], esi
0x18000ceb0  mov     ecx, [rbp+37h+arg_30]
0x18000ceb3  cmp     ecx, 6
0x18000ceb6  jg      loc_18000D07B
0x18000cebc  jz      loc_18000D070
0x18000cec2  test    ecx, ecx
0x18000cec4  jz      loc_18000CFA3
0x18000ceca  sub     ecx, 1
0x18000cecd  jz      loc_18000CF98
0x18000ced3  sub     ecx, 1
0x18000ced6  jz      loc_18000CF8D
0x18000cedc  sub     ecx, 1
0x18000cedf  jz      short loc_18000CF03
0x18000cee1  sub     ecx, 1
0x18000cee4  jz      short loc_18000CEF8
0x18000cee6  cmp     ecx, 1
0x18000cee9  jnz     loc_18000D0AD
0x18000ceef  lea     r9d, [rcx+7]
0x18000cef3  jmp     loc_18000D16E
0x18000cef8  mov     r9d, 7
0x18000cefe  jmp     loc_18000D16E
0x18000cf03  lea     rcx, [rbp+37h+pv]
0x18000cf07  call    ??$make_unique_cotaskmem@K$$V@wil@@YA?AV?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<ulong,>(void)
0x18000cf0c  nop
0x18000cf0d  mov     rcx, [rsp+110h+var_C8]
0x18000cf12  mov     rax, [rcx]
0x18000cf15  lea     r8, [rbp+37h+var_60]
0x18000cf19  cmp     [rbp+37h+var_48], 7
0x18000cf1e  cmova   r8, [rbp+37h+var_60]
0x18000cf23  movups  xmm0, cs:xmmword_18008F2D8
0x18000cf2a  movdqu  [rbp+37h+var_90], xmm0
0x18000cf2f  mov     r9, [rbp+37h+pv]
0x18000cf33  lea     rdx, [rbp+37h+var_90]
0x18000cf37  mov     rax, [rax+128h]
0x18000cf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf43  mov     ebx, eax
0x18000cf45  test    eax, eax
0x18000cf47  jns     short loc_18000CF6B
0x18000cf49  mov     rcx, [rbp+37h+pv]; pv
0x18000cf4d  mov     [rbp+37h+pv], rsi
0x18000cf51  test    rcx, rcx
0x18000cf54  jz      loc_18000D329
0x18000cf5a  call    cs:__imp_CoTaskMemFree
0x18000cf61  nop     dword ptr [rax+rax+00h]
0x18000cf66  jmp     loc_18000D329
0x18000cf6b  mov     rdx, [rbp+37h+pv]
0x18000cf6f  mov     [rbp+37h+pv], rsi
0x18000cf73  lea     rcx, [rsp+110h+Src]
0x18000cf78  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x18000cf7d  mov     r9d, 4
0x18000cf83  mov     dword ptr [rsp+110h+size], r9d
0x18000cf88  jmp     loc_18000D253
0x18000cf8d  mov     r9d, 5
0x18000cf93  jmp     loc_18000D16E
0x18000cf98  mov     r9d, 4
0x18000cf9e  jmp     loc_18000D16E
0x18000cfa3  mov     dword ptr [rbp+37h+var_90], esi
0x18000cfa6  mov     rcx, [rsp+110h+var_C8]
0x18000cfab  mov     rax, [rcx]
0x18000cfae  lea     r8, [rbp+37h+var_60]
0x18000cfb2  cmp     [rbp+37h+var_48], 7
0x18000cfb7  cmova   r8, [rbp+37h+var_60]
0x18000cfbc  movups  xmm0, cs:xmmword_18008F2D8
0x18000cfc3  movdqu  xmmword ptr [rbp+37h+pv], xmm0
0x18000cfc8  lea     r9, [rbp+37h+var_90]
0x18000cfcc  lea     rdx, [rbp+37h+pv]
0x18000cfd0  mov     rax, [rax+118h]
0x18000cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfdc  mov     ebx, eax
0x18000cfde  test    eax, eax
0x18000cfe0  jns     short loc_18000D01B
0x18000cfe2  mov     ecx, cs:dword_1800BE0B8
0x18000cfe8  cmp     ecx, 2
0x18000cfeb  jbe     loc_18000D329
0x18000cff1  lea     rdx, dword_1800AA28C
0x18000cff8  xor     r9d, r9d
0x18000cffb  lea     rax, [rbp+37h+pv]
0x18000cfff  xor     r8d, r8d
0x18000d002  mov     [rsp+110h+var_F0], rax
0x18000d007  mov     dword ptr [rbp+37h+pv], ebx
0x18000d00a  lea     rcx, dword_1800BE0B8
0x18000d011  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d016  jmp     loc_18000D329
0x18000d01b  lea     rax, [rsp+110h+Src]
0x18000d020  mov     [rbp+37h+pv], rax
0x18000d024  mov     [rbp+37h+pv+8], rsi
0x18000d028  mov     [rbp+37h+var_A0], 1
0x18000d02c  lea     r8, [rbp+37h+pv+8]; unsigned __int64
0x18000d030  lea     rcx, [rbp+37h+var_90]; this
0x18000d034  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x18000d039  mov     ebx, eax
0x18000d03b  lea     rcx, [rbp+37h+pv]
0x18000d03f  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000d044  test    ebx, ebx
0x18000d046  jns     short loc_18000D060
0x18000d048  mov     eax, cs:dword_1800BE0B8
0x18000d04e  cmp     eax, 2
0x18000d051  jbe     loc_18000D329
0x18000d057  lea     rdx, dword_1800AA18C
0x18000d05e  jmp     short loc_18000CFF8
0x18000d060  mov     r9d, 4
0x18000d066  mov     dword ptr [rsp+110h+size], r9d
0x18000d06b  jmp     loc_18000D26C
0x18000d070  mov     r9d, 0Bh
0x18000d076  jmp     loc_18000D16E
0x18000d07b  sub     ecx, 7
0x18000d07e  jz      loc_18000D1D4
0x18000d084  sub     ecx, 1
0x18000d087  jz      loc_18000D168
0x18000d08d  sub     ecx, 2
0x18000d090  jz      loc_18000D160
0x18000d096  sub     ecx, 1
0x18000d099  jz      loc_18000D158
0x18000d09f  sub     ecx, 1
0x18000d0a2  jz      loc_18000D150
0x18000d0a8  cmp     ecx, 1
0x18000d0ab  jz      short loc_18000D0C1
0x18000d0ad  mov     eax, cs:dword_1800BE0B8
0x18000d0b3  cmp     eax, 2
0x18000d0b6  jbe     short loc_18000D111
0x18000d0b8  lea     rdx, unk_1800AA1C0
0x18000d0bf  jmp     short loc_18000D0EE
0x18000d0c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF> `wil::Feature<__WilFeatureTraits_Feature_MakeCredentialPRF>::GetImpl(void)'::`2'::impl
0x18000d0c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MakeCredentialPRF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MakeCredentialPRF>::__private_IsEnabled(void)
0x18000d0cd  test    al, al
0x18000d0cf  jz      short loc_18000D0DC
0x18000d0d1  mov     r9d, 11h
0x18000d0d7  jmp     loc_18000D16E
0x18000d0dc  mov     eax, cs:dword_1800BE0B8
0x18000d0e2  cmp     eax, 2
0x18000d0e5  jbe     short loc_18000D111
0x18000d0e7  lea     rdx, byte_1800AA1F5
0x18000d0ee  lea     rax, [rbp+37h+pv]
0x18000d0f2  mov     [rsp+110h+var_F0], rax
0x18000d0f7  mov     dword ptr [rbp+37h+pv], 80070057h
0x18000d0fe  xor     r9d, r9d
0x18000d101  xor     r8d, r8d
0x18000d104  lea     rcx, dword_1800BE0B8
0x18000d10b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000d110  nop
0x18000d111  xor     edx, edx
0x18000d113  lea     rcx, [rsp+110h+Src]
0x18000d118  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x18000d11d  nop
0x18000d11e  lea     rcx, [rbp+37h+var_60]
0x18000d122  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18000d127  nop
0x18000d128  lea     rcx, [rsp+110h+var_C8]
0x18000d12d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d132  nop
0x18000d133  cmp     [rsp+110h+var_D0], sil
0x18000d138  jz      short loc_18000D146
0x18000d13a  call    cs:__imp_CoUninitialize
0x18000d141  nop     dword ptr [rax+rax+00h]
0x18000d146  mov     eax, 80070057h
0x18000d14b  jmp     loc_18000D360
0x18000d150  mov     r9d, 10h
0x18000d156  jmp     short loc_18000D16E
0x18000d158  mov     r9d, 0Fh
0x18000d15e  jmp     short loc_18000D16E
0x18000d160  mov     r9d, 0Eh
0x18000d166  jmp     short loc_18000D16E
0x18000d168  mov     r9d, 0Ch
0x18000d16e  mov     [rbp+37h+pv], rsi
0x18000d172  mov     rcx, [rsp+110h+var_C8]
0x18000d177  mov     rax, [rcx]
0x18000d17a  lea     r8, [rbp+37h+var_60]
0x18000d17e  cmp     [rbp+37h+var_48], 7
0x18000d183  cmova   r8, [rbp+37h+var_60]
0x18000d188  movups  xmm0, cs:xmmword_18008F2D8
0x18000d18f  movdqu  [rbp+37h+var_90], xmm0
0x18000d194  lea     rdx, [rsp+110h+size]
0x18000d199  mov     [rsp+110h+var_E8], rdx
0x18000d19e  lea     rdx, [rbp+37h+pv]
0x18000d1a2  mov     [rsp+110h+var_F0], rdx
0x18000d1a7  lea     rdx, [rbp+37h+var_90]
0x18000d1ab  mov     rax, [rax+88h]
0x18000d1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1b7  mov     ebx, eax
0x18000d1b9  test    eax, eax
0x18000d1bb  js      loc_18000D329
0x18000d1c1  mov     rdx, [rbp+37h+pv]
0x18000d1c5  lea     rcx, [rsp+110h+Src]
0x18000d1ca  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x18000d1cf  jmp     loc_18000D26C
0x18000d1d4  mov     [rbp+37h+pv], rsi
0x18000d1d8  mov     rcx, [rsp+110h+var_C8]
0x18000d1dd  mov     rax, [rcx]
0x18000d1e0  lea     rdx, [rbp+37h+pv]
0x18000d1e4  mov     qword ptr [rbp+37h+var_90], rdx
0x18000d1e8  mov     qword ptr [rbp+37h+var_90+8], rsi
0x18000d1ec  mov     [rbp+37h+var_80], 1
0x18000d1f0  lea     rdx, [rbp+37h+var_60]
0x18000d1f4  cmp     [rbp+37h+var_48], 7
0x18000d1f9  cmova   rdx, [rbp+37h+var_60]
0x18000d1fe  lea     r9, [rbp+37h+var_90+8]
0x18000d202  mov     r8d, 1
0x18000d208  mov     rax, [rax+0A8h]
0x18000d20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d214  mov     ebx, eax
0x18000d216  lea     rcx, [rbp+37h+var_90]
0x18000d21a  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18000d21f  test    ebx, ebx
0x18000d221  jns     short loc_18000D228
0x18000d223  jmp     loc_18000CF49
0x18000d228  mov     rdx, [rbp+37h+pv]
0x18000d22c  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
