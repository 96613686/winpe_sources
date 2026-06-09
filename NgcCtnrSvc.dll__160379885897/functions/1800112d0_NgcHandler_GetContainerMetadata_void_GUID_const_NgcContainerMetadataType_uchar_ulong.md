# NgcHandler::GetContainerMetadata(void *,_GUID const &,_NgcContainerMetadataType,uchar * *,ulong *)

- ea: `0x1800112d0`
- end: `0x180011a08`
- name: `?GetContainerMetadata@NgcHandler@@QEAAJPEAXAEBU_GUID@@W4_NgcContainerMetadataType@@PEAPEAEPEAK@Z`
- size: `1848`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800111fc`

## callees

- `0x18000c7e0`
- `0x18000d450`
- `0x1800112d0`
- `0x180012190`
- `0x1800134a0`
- `0x180014350`
- `0x1800143c0`
- `0x180016eac`
- `0x180017210`
- `0x180018194`
- `0x18002d500`
- `0x180047b94`
- `0x180047d04`
- `0x180047d28`
- `0x18005950c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011732`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001198c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800119e9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011732`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001198c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800119e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001147a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001154a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001147a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001154a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011589`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NgcHandler::GetContainerMetadata(
        __int64 (__fastcall **a1)(LPVOID *, __int64 **),
        __int64 a2,
        _OWORD *a3,
        int a4,
        _QWORD *a5,
        _DWORD *a6)
{
  int v9; // eax
  int v10; // ebx
  __int64 (__fastcall *v11)(LPVOID *, __int64 **); // rbx
  __int64 v12; // rdx
  void *v13; // rcx
  LPVOID v14; // rdx
  void *v15; // rcx
  _QWORD *v16; // rax
  void *v17; // rcx
  _QWORD *unique; // rax
  void *v19; // rcx
  _DWORD *v20; // rdx
  const void *v21; // rdx
  void **v22; // r9
  unsigned __int8 *v23; // rdx
  int v24; // edi
  int v25; // edi
  int v26; // edi
  int v27; // edi
  int v28; // edi
  LPVOID v30; // rdx
  LPVOID v31; // rdx
  __int64 v32; // rax
  void *v33; // rax
  void *v34; // rdi
  int v35; // [rsp+40h] [rbp-59h] BYREF
  __int64 *v36; // [rsp+48h] [rbp-51h] BYREF
  size_t size[2]; // [rsp+50h] [rbp-49h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-39h] BYREF
  char v39; // [rsp+70h] [rbp-29h]
  void *Src; // [rsp+80h] [rbp-19h] BYREF
  int v41; // [rsp+88h] [rbp-11h] BYREF
  _DWORD *v42; // [rsp+90h] [rbp-9h] BYREF
  int v43; // [rsp+98h] [rbp-1h] BYREF
  int v44; // [rsp+9Ch] [rbp+3h] BYREF
  int v45[16]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v46; // [rsp+F8h] [rbp+5Fh] BYREF

  v46 = a2;
  LOBYTE(v46) = 0;
  v9 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v46, a2);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v35 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AA0F9,
        0,
        0,
        (__int64)&v35);
    }
    goto LABEL_80;
  }
  v36 = 0;
  v11 = *a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  *(_OWORD *)pv = *a3;
  v10 = v11(pv, &v36);
  if ( v10 < 0
    || (v44 = 0,
        *(_OWORD *)pv = xmmword_18008F2D8,
        v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, int *))(*v36 + 88))(v36, pv, &v44),
        v10 < 0) )
  {
LABEL_79:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
LABEL_80:
    if ( (_BYTE)v46 )
      CoUninitialize();
    return (unsigned int)v10;
  }
  if ( !v44 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v35 = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AA134,
        0,
        0,
        (__int64)&v35);
    }
LABEL_57:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    if ( (_BYTE)v46 )
      CoUninitialize();
    return 2147942487LL;
  }
  Src = 0;
  LODWORD(size[0]) = 0;
  v12 = 6;
  if ( a4 > 6 )
  {
    v24 = a4 - 7;
    if ( !v24 )
    {
      v12 = 10;
      goto LABEL_70;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      v43 = 0;
      LODWORD(v42) = 0;
      v35 = 0;
      v41 = 0;
      v45[0] = 0;
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *, _DWORD **, int *, int *, int *))(*v36 + 208))(
              v36,
              1,
              &v43,
              &v42,
              &v35,
              &v41,
              v45);
      if ( v10 >= 0 )
      {
        wil::make_unique_cotaskmem<SoftLockoutInfoMetadata,>(pv);
        *(_DWORD *)pv[0] = v43;
        *((_DWORD *)pv[0] + 1) = v41;
        *((_DWORD *)pv[0] + 2) = v45[0];
        *((_DWORD *)pv[0] + 3) = (_DWORD)v42;
        *((_DWORD *)pv[0] + 4) = v35;
        v31 = pv[0];
        pv[0] = 0;
        wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &Src,
          v31);
        LODWORD(size[0]) = 20;
        goto LABEL_21;
      }
      goto LABEL_78;
    }
    v26 = v25 - 1;
    if ( v26 )
    {
      v27 = v26 - 1;
      if ( v27 )
      {
        v28 = v27 - 1;
        if ( v28 )
        {
          if ( v28 != 1 )
            goto LABEL_54;
          v12 = 12;
          goto LABEL_70;
        }
        wil::make_unique_cotaskmem<int,>(pv);
        v35 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64 *, int *, LPVOID))(*v36 + 72))(v36, &v35, pv[0]);
        if ( v10 >= 0 )
        {
LABEL_62:
          v30 = pv[0];
          pv[0] = 0;
          wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &Src,
            v30);
          LODWORD(size[0]) = 4;
          goto LABEL_21;
        }
      }
      else
      {
        wil::make_unique_cotaskmem<int,>(pv);
        v35 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, int *))(*v36 + 72))(v36, pv[0], &v35);
        if ( v10 >= 0 )
          goto LABEL_62;
      }
    }
    else
    {
      wil::make_unique_cotaskmem<unsigned long,>(pv);
      v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*v36 + 24))(v36, pv[0]);
      if ( v10 >= 0 )
      {
LABEL_20:
        v14 = pv[0];
        pv[0] = 0;
        wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &Src,
          v14);
        LODWORD(size[0]) = 4;
LABEL_21:
        v15 = pv[0];
        pv[0] = 0;
        goto LABEL_22;
      }
    }
LABEL_18:
    v13 = pv[0];
    pv[0] = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    goto LABEL_78;
  }
  switch ( a4 )
  {
    case 6:
      v12 = 9;
      goto LABEL_70;
    case 0:
      v12 = 1;
      goto LABEL_70;
    case 1:
      goto LABEL_36;
    case 2:
LABEL_70:
      v32 = *v36;
      pv[0] = &Src;
      pv[1] = 0;
      v39 = 1;
      v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *, size_t *))(v32 + 120))(v36, v12, &pv[1], size);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pv);
      if ( v10 >= 0 )
        goto LABEL_71;
      goto LABEL_78;
  }
  if ( a4 != 3 )
  {
    if ( a4 != 4 )
    {
      if ( a4 == 5 )
      {
        wil::make_unique_cotaskmem<unsigned long,>(pv);
        v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*v36 + 104))(v36, pv[0]);
        if ( v10 < 0 )
          goto LABEL_18;
        goto LABEL_20;
      }
LABEL_54:
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v35 = -2147024809;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800A9FCB,
          0,
          0,
          (__int64)&v35);
      }
      wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &Src,
        0);
      goto LABEL_57;
    }
LABEL_36:
    v41 = 0;
    v43 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, int *, int *, _QWORD, _QWORD))(*v36 + 208))(
            v36,
            1,
            0,
            &v41,
            &v43,
            0,
            0);
    if ( v10 < 0 )
      goto LABEL_78;
    pv[1] = 0;
    v39 = 1;
    pv[0] = &Src;
    if ( a4 == 1 )
    {
      v10 = NgcUtils::CoMemAllocCopy((NgcUtils *)&v41, v21, (unsigned __int64)&pv[1], v22);
      wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pv);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v23 = (unsigned __int8 *)&dword_1800AA094;
LABEL_41:
          v35 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            v23,
            0,
            0,
            (__int64)&v35);
        }
LABEL_78:
        wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &Src,
          0);
        goto LABEL_79;
      }
    }
    else
    {
      v10 = NgcUtils::CoMemAllocCopy((NgcUtils *)&v43, v21, (unsigned __int64)&pv[1], v22);
      wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pv);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_1800BE0B8 <= 2 )
          goto LABEL_78;
        v23 = (unsigned __int8 *)&unk_1800AA068;
        goto LABEL_41;
      }
    }
    LODWORD(size[0]) = 4;
    goto LABEL_71;
  }
  v42 = 0;
  v41 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _DWORD **, int *))(*v36 + 152))(v36, 1, 7, &v42, &v41);
  if ( v10 >= 0 )
  {
    if ( v41 && v42 )
      goto LABEL_35;
    unique = wil::make_unique_cotaskmem<unsigned long,>(pv);
    wistd::unique_ptr<unsigned long,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      &v42,
      unique);
    v19 = pv[0];
    pv[0] = 0;
    if ( v19 )
      CoTaskMemFree(v19);
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 3 )
    {
      v35 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&unk_1800AA0C0,
        0,
        0,
        (__int64)&v35);
    }
    v16 = wil::make_unique_cotaskmem<unsigned long,>(pv);
    wistd::unique_ptr<unsigned long,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
      &v42,
      v16);
    v17 = pv[0];
    pv[0] = 0;
    if ( v17 )
      CoTaskMemFree(v17);
    v10 = 0;
  }
  *v42 = 0;
LABEL_35:
  v20 = v42;
  v42 = 0;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, v20);
  LODWORD(size[0]) = 4;
  v15 = v42;
  v42 = 0;
LABEL_22:
  if ( v15 )
    CoTaskMemFree(v15);
LABEL_71:
  v33 = MIDL_user_allocate(LODWORD(size[0]));
  v34 = v33;
  pv[0] = v33;
  if ( v33 )
  {
    memcpy_0(v33, Src, LODWORD(size[0]));
    pv[0] = 0;
    *a5 = v34;
    *a6 = size[0];
    std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(pv);
    goto LABEL_78;
  }
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v35 = -2147024882;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)&dword_1800A9F94,
      0,
      0,
      (__int64)&v35);
  }
  std::unique_ptr<unsigned char,rpcmem_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_delete<unsigned char>>(pv);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, 0);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  if ( (_BYTE)v46 )
    CoUninitialize();
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800112d0  mov     [rsp-8+arg_8], rdx
0x1800112d5  push    rbp
0x1800112d6  push    rbx
0x1800112d7  push    rsi
0x1800112d8  push    rdi
0x1800112d9  push    r14
0x1800112db  push    r15
0x1800112dd  lea     rbp, [rsp-1Fh]
0x1800112e2  sub     rsp, 0B8h
0x1800112e9  mov     edi, r9d
0x1800112ec  mov     rsi, r8
0x1800112ef  mov     r14, rcx
0x1800112f2  xor     r15d, r15d
0x1800112f5  mov     byte ptr [rbp+47h+arg_8], r15b
0x1800112f9  lea     rcx, [rbp+47h+arg_8]; this
0x1800112fd  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180011302  mov     ebx, eax
0x180011304  test    eax, eax
0x180011306  jns     short loc_180011341
0x180011308  mov     ecx, cs:dword_1800BE0B8
0x18001130e  cmp     ecx, 2
0x180011311  jbe     loc_1800119E3
0x180011317  mov     [rbp+47h+var_A0], eax
0x18001131a  lea     rax, [rbp+47h+var_A0]
0x18001131e  mov     [rsp+0E0h+var_C0], rax
0x180011323  xor     r9d, r9d
0x180011326  xor     r8d, r8d
0x180011329  lea     rdx, byte_1800AA0F9
0x180011330  lea     rcx, dword_1800BE0B8
0x180011337  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001133c  jmp     loc_1800119E3
0x180011341  mov     [rbp+47h+var_98], r15
0x180011345  mov     rbx, [r14]
0x180011348  lea     rcx, [rbp+47h+var_98]
0x18001134c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011351  movups  xmm0, xmmword ptr [rsi]
0x180011354  movdqu  xmmword ptr [rbp+47h+pv], xmm0
0x180011359  lea     rdx, [rbp+47h+var_98]
0x18001135d  lea     rcx, [rbp+47h+pv]
0x180011361  mov     rax, rbx
0x180011364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011369  mov     ebx, eax
0x18001136b  test    eax, eax
0x18001136d  js      loc_1800119D9
0x180011373  mov     [rbp+47h+var_44], r15d
0x180011377  mov     rcx, [rbp+47h+var_98]
0x18001137b  movups  xmm0, cs:xmmword_18008F2D8
0x180011382  movdqu  xmmword ptr [rbp+47h+pv], xmm0
0x180011387  mov     rax, [rcx]
0x18001138a  lea     r8, [rbp+47h+var_44]
0x18001138e  lea     rdx, [rbp+47h+pv]
0x180011392  mov     rax, [rax+58h]
0x180011396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139b  mov     ebx, eax
0x18001139d  test    eax, eax
0x18001139f  js      loc_1800119D9
0x1800113a5  cmp     [rbp+47h+var_44], r15d
0x1800113a9  jnz     short loc_1800113E8
0x1800113ab  mov     eax, cs:dword_1800BE0B8
0x1800113b1  cmp     eax, 2
0x1800113b4  jbe     loc_180011722
0x1800113ba  mov     [rbp+47h+var_A0], 80070057h
0x1800113c1  lea     rax, [rbp+47h+var_A0]
0x1800113c5  mov     [rsp+0E0h+var_C0], rax
0x1800113ca  xor     r9d, r9d
0x1800113cd  xor     r8d, r8d
0x1800113d0  lea     rdx, dword_1800AA134
0x1800113d7  lea     rcx, dword_1800BE0B8
0x1800113de  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800113e3  jmp     loc_180011722
0x1800113e8  mov     [rbp+47h+Src], r15
0x1800113ec  mov     dword ptr [rbp+47h+size], r15d
0x1800113f0  lea     rsi, dword_1800BE0B8
0x1800113f7  mov     edx, 6
0x1800113fc  lea     r14d, [rdx-5]
0x180011400  cmp     edi, edx
0x180011402  jg      loc_1800116B7
0x180011408  jz      loc_1800116AD
0x18001140e  mov     ecx, edi
0x180011410  test    edi, edi
0x180011412  jz      loc_1800116A5
0x180011418  sub     ecx, r14d
0x18001141b  jz      loc_1800115C1
0x180011421  sub     ecx, r14d
0x180011424  jz      loc_1800118E7
0x18001142a  sub     ecx, r14d
0x18001142d  jz      loc_1800114C5
0x180011433  sub     ecx, r14d
0x180011436  jz      loc_1800115C1
0x18001143c  cmp     ecx, r14d
0x18001143f  jnz     loc_1800116E5
0x180011445  lea     rcx, [rbp+47h+pv]
0x180011449  call    ??$make_unique_cotaskmem@K$$V@wil@@YA?AV?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<ulong,>(void)
0x18001144e  nop
0x18001144f  mov     rcx, [rbp+47h+var_98]
0x180011453  mov     rax, [rcx]
0x180011456  mov     rdx, [rbp+47h+pv]
0x18001145a  mov     rax, [rax+68h]
0x18001145e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011463  mov     ebx, eax
0x180011465  test    eax, eax
0x180011467  jns     short loc_18001148B
0x180011469  mov     rcx, [rbp+47h+pv]; pv
0x18001146d  mov     [rbp+47h+pv], r15
0x180011471  test    rcx, rcx
0x180011474  jz      loc_1800119CD
0x18001147a  call    cs:__imp_CoTaskMemFree
0x180011481  nop     dword ptr [rax+rax+00h]
0x180011486  jmp     loc_1800119CD
0x18001148b  mov     rdx, [rbp+47h+pv]
0x18001148f  mov     [rbp+47h+pv], r15
0x180011493  lea     rcx, [rbp+47h+Src]
0x180011497  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x18001149c  mov     dword ptr [rbp+47h+size], 4
0x1800114a3  mov     rcx, [rbp+47h+pv]; pv
0x1800114a7  mov     [rbp+47h+pv], r15
0x1800114ab  test    rcx, rcx
0x1800114ae  jz      loc_180011922
0x1800114b4  call    cs:__imp_CoTaskMemFree
0x1800114bb  nop     dword ptr [rax+rax+00h]
0x1800114c0  jmp     loc_180011922
0x1800114c5  mov     [rbp+47h+var_50], r15
0x1800114c9  mov     [rbp+47h+var_58], r15d
0x1800114cd  mov     rcx, [rbp+47h+var_98]
0x1800114d1  mov     rax, [rcx]
0x1800114d4  lea     r8, [rbp+47h+var_58]
0x1800114d8  mov     [rsp+0E0h+var_C0], r8
0x1800114dd  lea     r9, [rbp+47h+var_50]
0x1800114e1  mov     r8d, 7
0x1800114e7  mov     edx, r14d
0x1800114ea  mov     rax, [rax+98h]
0x1800114f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f6  mov     ebx, eax
0x1800114f8  test    eax, eax
0x1800114fa  jns     short loc_18001155B
0x1800114fc  mov     eax, cs:dword_1800BE0B8
0x180011502  cmp     eax, 3
0x180011505  jbe     short loc_180011528
0x180011507  mov     [rbp+47h+var_A0], ebx
0x18001150a  lea     rax, [rbp+47h+var_A0]
0x18001150e  mov     [rsp+0E0h+var_C0], rax
0x180011513  xor     r9d, r9d
0x180011516  xor     r8d, r8d
0x180011519  lea     rdx, unk_1800AA0C0
0x180011520  mov     rcx, rsi
0x180011523  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011528  lea     rcx, [rbp+47h+pv]
0x18001152c  call    ??$make_unique_cotaskmem@K$$V@wil@@YA?AV?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<ulong,>(void)
0x180011531  mov     rdx, rax
0x180011534  lea     rcx, [rbp+47h+var_50]
0x180011538  call    ??4?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<ulong,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18001153d  mov     rcx, [rbp+47h+pv]; pv
0x180011541  mov     [rbp+47h+pv], r15
0x180011545  test    rcx, rcx
0x180011548  jz      short loc_180011556
0x18001154a  call    cs:__imp_CoTaskMemFree
0x180011551  nop     dword ptr [rax+rax+00h]
0x180011556  mov     ebx, r15d
0x180011559  jmp     short loc_180011595
0x18001155b  cmp     [rbp+47h+var_58], r15d
0x18001155f  jz      short loc_180011567
0x180011561  cmp     [rbp+47h+var_50], r15
0x180011565  jnz     short loc_18001159C
0x180011567  lea     rcx, [rbp+47h+pv]
0x18001156b  call    ??$make_unique_cotaskmem@K$$V@wil@@YA?AV?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<ulong,>(void)
0x180011570  mov     rdx, rax
0x180011573  lea     rcx, [rbp+47h+var_50]
0x180011577  call    ??4?$unique_ptr@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<ulong,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18001157c  mov     rcx, [rbp+47h+pv]; pv
0x180011580  mov     [rbp+47h+pv], r15
0x180011584  test    rcx, rcx
0x180011587  jz      short loc_180011595
0x180011589  call    cs:__imp_CoTaskMemFree
0x180011590  nop     dword ptr [rax+rax+00h]
0x180011595  mov     rax, [rbp+47h+var_50]
0x180011599  mov     [rax], r15d
0x18001159c  mov     rdx, [rbp+47h+var_50]
0x1800115a0  mov     [rbp+47h+var_50], r15
0x1800115a4  lea     rcx, [rbp+47h+Src]
0x1800115a8  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x1800115ad  mov     dword ptr [rbp+47h+size], 4
0x1800115b4  mov     rcx, [rbp+47h+var_50]
0x1800115b8  mov     [rbp+47h+var_50], r15
0x1800115bc  jmp     loc_1800114AB
0x1800115c1  mov     [rbp+47h+var_58], r15d
0x1800115c5  mov     [rbp+47h+var_48], r15d
0x1800115c9  mov     rcx, [rbp+47h+var_98]
0x1800115cd  mov     rax, [rcx]
0x1800115d0  mov     [rsp+0E0h+var_B0], r15
0x1800115d5  mov     [rsp+0E0h+var_B8], r15
0x1800115da  lea     rdx, [rbp+47h+var_48]
0x1800115de  mov     [rsp+0E0h+var_C0], rdx
0x1800115e3  lea     r9, [rbp+47h+var_58]
0x1800115e7  xor     r8d, r8d
0x1800115ea  mov     edx, r14d
0x1800115ed  mov     rax, [rax+0D0h]
0x1800115f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f9  mov     ebx, eax
0x1800115fb  test    eax, eax
0x1800115fd  js      loc_1800119CD
0x180011603  lea     rax, [rbp+47h+Src]
0x180011607  mov     [rbp+47h+pv+8], r15
0x18001160b  mov     [rbp+47h+var_70], r14b
0x18001160f  lea     r8, [rbp+47h+pv+8]; unsigned __int64
0x180011613  mov     [rbp+47h+pv], rax
0x180011617  cmp     edi, r14d
0x18001161a  jnz     short loc_180011669
0x18001161c  lea     rcx, [rbp+47h+var_58]; this
0x180011620  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180011625  mov     ebx, eax
0x180011627  lea     rcx, [rbp+47h+pv]
0x18001162b  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180011630  test    ebx, ebx
0x180011632  jns     short loc_180011699
0x180011634  mov     eax, cs:dword_1800BE0B8
0x18001163a  cmp     eax, 2
0x18001163d  jbe     loc_1800119CD
0x180011643  lea     rdx, dword_1800AA094
0x18001164a  xor     r9d, r9d
0x18001164d  lea     rax, [rbp+47h+var_A0]
0x180011651  xor     r8d, r8d
0x180011654  mov     [rsp+0E0h+var_C0], rax
0x180011659  mov     [rbp+47h+var_A0], ebx
0x18001165c  mov     rcx, rsi
0x18001165f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011664  jmp     loc_1800119CD
0x180011669  lea     rcx, [rbp+47h+var_48]; this
0x18001166d  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x180011672  mov     ebx, eax
0x180011674  lea     rcx, [rbp+47h+pv]
0x180011678  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001167d  test    ebx, ebx
0x18001167f  jns     short loc_180011699
0x180011681  mov     eax, cs:dword_1800BE0B8
0x180011687  cmp     eax, 2
0x18001168a  jbe     loc_1800119CD
0x180011690  lea     rdx, unk_1800AA068
0x180011697  jmp     short loc_18001164A
0x180011699  mov     dword ptr [rbp+47h+size], 4
0x1800116a0  jmp     loc_180011922
0x1800116a5  mov     edx, r14d
0x1800116a8  jmp     loc_1800118E7
0x1800116ad  mov     edx, 9
0x1800116b2  jmp     loc_1800118E7
0x1800116b7  sub     edi, 7
0x1800116ba  jz      loc_1800118E2
0x1800116c0  sub     edi, r14d
0x1800116c3  jz      loc_180011834
0x1800116c9  sub     edi, r14d
0x1800116cc  jz      loc_1800117EE
0x1800116d2  sub     edi, r14d
0x1800116d5  jz      loc_1800117A0
0x1800116db  sub     edi, r14d
0x1800116de  jz      short loc_180011752
0x1800116e0  cmp     edi, r14d
0x1800116e3  jz      short loc_180011748
0x1800116e5  mov     eax, cs:dword_1800BE0B8
0x1800116eb  cmp     eax, 2
0x1800116ee  jbe     short loc_180011716
0x1800116f0  mov     [rbp+47h+var_A0], 80070057h
0x1800116f7  lea     rax, [rbp+47h+var_A0]
0x1800116fb  mov     [rsp+0E0h+var_C0], rax
0x180011700  xor     r9d, r9d
0x180011703  xor     r8d, r8d
0x180011706  lea     rdx, byte_1800A9FCB
0x18001170d  mov     rcx, rsi
0x180011710  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180011715  nop
0x180011716  xor     edx, edx
0x180011718  lea     rcx, [rbp+47h+Src]
0x18001171c  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x180011721  nop
0x180011722  lea     rcx, [rbp+47h+var_98]
0x180011726  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001172b  nop
0x18001172c  cmp     byte ptr [rbp+47h+arg_8], r15b
0x180011730  jz      short loc_18001173E
0x180011732  call    cs:__imp_CoUninitialize
0x180011739  nop     dword ptr [rax+rax+00h]
0x18001173e  mov     eax, 80070057h
0x180011743  jmp     loc_1800119F7
0x180011748  mov     edx, 0Ch
0x18001174d  jmp     loc_1800118E7
0x180011752  lea     rcx, [rbp+47h+pv]
0x180011756  call    ??$make_unique_cotaskmem@H$$V@wil@@YA?AV?$unique_ptr@HU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<int,>(void)
0x18001175b  nop
0x18001175c  mov     [rbp+47h+var_A0], r15d
0x180011760  mov     rcx, [rbp+47h+var_98]
0x180011764  mov     rax, [rcx]
0x180011767  mov     r8, [rbp+47h+pv]
0x18001176b  lea     rdx, [rbp+47h+var_A0]
0x18001176f  mov     rax, [rax+48h]
0x180011773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011778  mov     ebx, eax
0x18001177a  test    eax, eax
0x18001177c  jns     short loc_180011783
0x18001177e  jmp     loc_180011469
0x180011783  mov     rdx, [rbp+47h+pv]
0x180011787  mov     [rbp+47h+pv], r15
0x18001178b  lea     rcx, [rbp+47h+Src]
  ... truncated ...
```
