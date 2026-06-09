# GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints,std::default_delete<PacketSizeConstraints>> &)

- ea: `0x180039028`
- end: `0x1800394a1`
- name: `?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800197e4`
- `0x180019ce8`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x18001f2b0`
- `0x180026500`
- `0x180039028`
- `0x1800394a8`
- `0x1800394c4`
- `0x1800394f8`
- `0x18003e920`
- `0x18003edfc`
- `0x18003efd0`
- `0x18003f038`
- `0x18003f78c`
- `0x180048fd0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039213`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800392a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039303`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039330`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003936c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039469`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039213`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800392a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039303`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039330`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003936c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039444`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039444`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall GetPacketSizeConstraints(__int64 a1, __int64 a2, __int64 *a3)
{
  struct IUnknown *v5; // r15
  int *i; // rdi
  int v7; // eax
  void *v8; // rcx
  unsigned int v9; // ebx
  __int16 v10; // ax
  int v11; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  void *v16; // rcx
  __int64 v17; // rdx
  char v18; // si
  void *v19; // rcx
  void *v20; // rdi
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rdx
  void *v26; // rcx
  __int64 *v27; // [rsp+20h] [rbp-59h] BYREF
  void *pv; // [rsp+28h] [rbp-51h] BYREF
  __int64 v29; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v30; // [rsp+38h] [rbp-41h] BYREF
  size_t Size[2]; // [rsp+40h] [rbp-39h] BYREF
  void *Src; // [rsp+50h] [rbp-29h]
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v34; // [rsp+68h] [rbp-11h]
  void **p_pv; // [rsp+70h] [rbp-9h] BYREF
  void *v36; // [rsp+78h] [rbp-1h] BYREF
  char v37; // [rsp+80h] [rbp+7h]
  _DWORD v38[6]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = g_DeviceEnumerator;
  if ( dword_180086D30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180086D30);
    if ( dword_180086D30 == -1 )
    {
      xmmword_180086BC8 = DEVPKEY_KsAudio_PacketSize_Constraints2;
      dword_180086BD8 = 2;
      xmmword_180086BDC = DEVPKEY_KsAudio_PacketSize_Constraints;
      dword_180086BEC = 2;
      Init_thread_footer(&dword_180086D30);
    }
  }
  v30 = 0;
  for ( i = (int *)&xmmword_180086BC8; ; i += 5 )
  {
    if ( i == &CKsNotificationsMonitor::m_cRefAll )
      return 2147943568LL;
    *(_OWORD *)Size = 0;
    Src = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, int *, size_t *))(*(_QWORD *)a2 + 40LL))(a2, i, Size);
    v9 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36E,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v7,
        (int)v27);
      goto LABEL_43;
    }
    v10 = Size[0];
    if ( !LOWORD(Size[0]) )
    {
      *(_OWORD *)pvar = 0;
      v34 = 0;
      v38[0] = 590439624;
      v38[1] = 1283267372;
      v38[2] = 1907779772;
      v38[3] = 1730509416;
      v38[4] = 1;
      v11 = (*(__int64 (__fastcall **)(__int64, _DWORD *, PROPVARIANT *))(*(_QWORD *)a2 + 40LL))(a2, v38, pvar);
      v9 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x376,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v11,
          (int)v27);
      }
      else
      {
        if ( LOWORD(pvar[0]) != 31 )
        {
          PropVariantClear(pvar);
          v9 = -2147023728;
LABEL_43:
          PropVariantClear((PROPVARIANT *)Size);
          return v9;
        }
        lpVtbl = v5->lpVtbl;
        v27 = 0;
        v13 = ((__int64 (__fastcall *)(struct IUnknown *, PROPVARIANT, __int64 **))lpVtbl[1].Release)(v5, pvar[1], &v27);
        v9 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37C,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v13,
            (int)v27);
        }
        else
        {
          v29 = 0;
          v14 = *v27;
          v29 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v14 + 32))(v27, 0, &v29);
          v9 = v15;
          if ( v15 < 0 )
          {
            v17 = 895;
          }
          else
          {
            v15 = (*(__int64 (__fastcall **)(__int64, int *, size_t *))(*(_QWORD *)v29 + 40LL))(v29, i, Size);
            v9 = v15;
            if ( v15 >= 0 )
            {
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
              PropVariantClear(pvar);
              v10 = Size[0];
              goto LABEL_14;
            }
            v17 = 897;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v15,
            (int)v27);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      }
      PropVariantClear(pvar);
      goto LABEL_43;
    }
LABEL_14:
    if ( v10 == 65 && LODWORD(Size[1]) >= 0x28 )
      break;
LABEL_20:
    PropVariantClear((PROPVARIANT *)Size);
  }
  pv = 0;
  p_pv = &pv;
  v36 = 0;
  v37 = 1;
  v9 = CTCoAllocPolicy::Alloc(v8, 1u, LODWORD(Size[1]), &v36);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38C,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)v9,
      (int)v27);
    v26 = pv;
    pv = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    goto LABEL_43;
  }
  memcpy_0(pv, Src, LODWORD(Size[1]));
  v16 = pv;
  if ( LODWORD(Size[1]) < 24 * *((_DWORD *)pv + 3) + 16 )
  {
    pv = 0;
    if ( v16 )
      CoTaskMemFree(v16);
    goto LABEL_20;
  }
  v18 = operator==(i);
  wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(&v30, &pv);
  v19 = pv;
  pv = 0;
  if ( v19 )
    CoTaskMemFree(v19);
  PropVariantClear((PROPVARIANT *)Size);
  v20 = v30;
  if ( !v30 )
    return 2147943568LL;
  v21 = operator new[](0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v21;
  if ( !v21 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A0,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      0);
    std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v27);
    if ( v20 )
      CoTaskMemFree(v20);
    return v9;
  }
  *v21 = 0;
  v21[1] = 0;
  *(_BYTE *)v21 = v18;
  wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::operator=(
    v21 + 1,
    &v30);
  v27 = 0;
  v24 = *a3;
  *a3 = (__int64)v22;
  if ( v24 )
    std::default_delete<PacketSizeConstraints>::operator()(v23, v24);
  std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v27);
  if ( v30 )
    CoTaskMemFree(v30);
  return 0;
}

```

## disassembly

```asm
0x180039028  mov     [rsp-8+arg_0], rbx
0x18003902d  mov     [rsp-8+arg_18], rsi
0x180039032  push    rbp
0x180039033  push    rdi
0x180039034  push    r12
0x180039036  push    r14
0x180039038  push    r15
0x18003903a  lea     rbp, [rsp-37h]
0x18003903f  sub     rsp, 0B0h
0x180039046  mov     rax, cs:__security_cookie
0x18003904d  xor     rax, rsp
0x180039050  mov     [rbp+57h+var_30], rax
0x180039054  mov     r14, r8
0x180039057  mov     rsi, rdx
0x18003905a  mov     r15, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039061  mov     ecx, cs:_tls_index
0x180039067  mov     rax, gs:58h
0x180039070  mov     edx, 4
0x180039075  mov     rax, [rax+rcx*8]
0x180039079  mov     ecx, [rdx+rax]
0x18003907c  cmp     cs:dword_180086D30, ecx
0x180039082  jle     short loc_1800390D9
0x180039084  lea     rcx, dword_180086D30
0x18003908b  call    _Init_thread_header
0x180039090  cmp     cs:dword_180086D30, 0FFFFFFFFh
0x180039097  jnz     short loc_1800390D9
0x180039099  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints2
0x1800390a0  movups  cs:xmmword_180086BC8, xmm0
0x1800390a7  mov     eax, cs:dword_18006E750
0x1800390ad  mov     cs:dword_180086BD8, eax
0x1800390b3  movups  xmm0, cs:DEVPKEY_KsAudio_PacketSize_Constraints
0x1800390ba  movups  cs:xmmword_180086BDC, xmm0
0x1800390c1  mov     eax, cs:dword_180073D40
0x1800390c7  mov     cs:dword_180086BEC, eax
0x1800390cd  lea     rcx, dword_180086D30
0x1800390d4  call    _Init_thread_footer
0x1800390d9  xor     r12d, r12d
0x1800390dc  mov     [rbp+57h+var_98], r12
0x1800390e0  lea     rdi, xmmword_180086BC8
0x1800390e7  lea     rax, ?m_cRefAll@CKsNotificationsMonitor@@2JA; long CKsNotificationsMonitor::m_cRefAll
0x1800390ee  cmp     rdi, rax
0x1800390f1  jz      loc_180039474
0x1800390f7  xorps   xmm0, xmm0
0x1800390fa  xor     eax, eax
0x1800390fc  movups  xmmword ptr [rbp+57h+Size], xmm0
0x180039100  mov     [rbp+57h+Src], rax
0x180039104  mov     rax, [rsi]
0x180039107  lea     r8, [rbp+57h+Size]
0x18003910b  mov     rdx, rdi
0x18003910e  mov     rcx, rsi
0x180039111  mov     rax, [rax+28h]
0x180039115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003911a  mov     ebx, eax
0x18003911c  test    eax, eax
0x18003911e  js      loc_18003944C
0x180039124  movzx   eax, word ptr [rbp+57h+Size]
0x180039128  test    ax, ax
0x18003912b  jnz     loc_18003921D
0x180039131  xorps   xmm0, xmm0
0x180039134  xor     eax, eax
0x180039136  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003913a  mov     [rbp+57h+var_68], rax
0x18003913e  mov     [rbp+57h+var_48], 233164C8h
0x180039145  mov     [rbp+57h+var_44], 4C7D1B2Ch
0x18003914c  mov     [rbp+57h+var_40], 71B668BCh
0x180039153  mov     [rbp+57h+var_3C], 67257A68h
0x18003915a  mov     [rbp+57h+var_38], 1
0x180039161  mov     rax, [rsi]
0x180039164  lea     r8, [rbp+57h+pvar]
0x180039168  lea     rdx, [rbp+57h+var_48]
0x18003916c  mov     rcx, rsi
0x18003916f  mov     rax, [rax+28h]
0x180039173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039178  mov     ebx, eax
0x18003917a  test    eax, eax
0x18003917c  js      loc_180039313
0x180039182  cmp     word ptr [rbp+57h+pvar], 1Fh
0x180039187  jnz     loc_1800392FF
0x18003918d  mov     rax, [r15]
0x180039190  mov     [rbp+57h+var_B0], r12
0x180039194  lea     r8, [rbp+57h+var_B0]
0x180039198  mov     rdx, [rbp+57h+pvar+8]
0x18003919c  mov     rcx, r15
0x18003919f  mov     rax, [rax+28h]
0x1800391a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391a8  mov     ebx, eax
0x1800391aa  test    eax, eax
0x1800391ac  js      loc_1800392DB
0x1800391b2  mov     [rbp+57h+var_A0], r12
0x1800391b6  mov     rcx, [rbp+57h+var_B0]
0x1800391ba  mov     rax, [rcx]
0x1800391bd  mov     [rbp+57h+var_A0], r12
0x1800391c1  lea     r8, [rbp+57h+var_A0]
0x1800391c5  xor     edx, edx
0x1800391c7  mov     rax, [rax+20h]
0x1800391cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391d0  mov     ebx, eax
0x1800391d2  test    eax, eax
0x1800391d4  js      loc_1800392B7
0x1800391da  mov     rcx, [rbp+57h+var_A0]
0x1800391de  mov     rax, [rcx]
0x1800391e1  lea     r8, [rbp+57h+Size]
0x1800391e5  mov     rdx, rdi
0x1800391e8  mov     rax, [rax+28h]
0x1800391ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391f1  mov     ebx, eax
0x1800391f3  test    eax, eax
0x1800391f5  js      loc_1800392B0
0x1800391fb  lea     rcx, [rbp+57h+var_A0]
0x1800391ff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039204  nop
0x180039205  lea     rcx, [rbp+57h+var_B0]
0x180039209  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003920e  nop
0x18003920f  lea     rcx, [rbp+57h+pvar]; pvar
0x180039213  call    cs:__imp_PropVariantClear
0x180039219  movzx   eax, word ptr [rbp+57h+Size]
0x18003921d  cmp     ax, 41h ; 'A'
0x180039221  jnz     short loc_18003929D
0x180039223  cmp     dword ptr [rbp+57h+Size+8], 28h ; '('
0x180039227  jb      short loc_18003929D
0x180039229  mov     [rbp+57h+pv], r12
0x18003922d  lea     rax, [rbp+57h+pv]
0x180039231  mov     [rbp+57h+var_60], rax
0x180039235  mov     [rbp+57h+var_58], r12
0x180039239  mov     [rbp+57h+var_50], 1
0x18003923d  mov     r8d, dword ptr [rbp+57h+Size+8]; unsigned __int64
0x180039241  lea     r9, [rbp+57h+var_58]; void **
0x180039245  mov     edx, 1; unsigned int
0x18003924a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003924f  mov     ebx, eax
0x180039251  lea     rcx, [rbp+57h+var_60]
0x180039255  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003925a  test    ebx, ebx
0x18003925c  js      loc_18003941E
0x180039262  mov     r8d, dword ptr [rbp+57h+Size+8]; Size
0x180039266  mov     rdx, [rbp+57h+Src]; Src
0x18003926a  mov     rcx, [rbp+57h+pv]; void *
0x18003926e  call    memcpy_0
0x180039273  mov     rcx, [rbp+57h+pv]; pv
0x180039277  mov     eax, [rcx+0Ch]
0x18003927a  lea     edx, [rax+rax*2]
0x18003927d  lea     edx, ds:10h[rdx*8]
0x180039284  cmp     dword ptr [rbp+57h+Size+8], edx
0x180039287  jnb     loc_18003933B
0x18003928d  mov     [rbp+57h+pv], r12
0x180039291  test    rcx, rcx
0x180039294  jz      short loc_18003929D
0x180039296  call    cs:__imp_CoTaskMemFree
0x18003929c  nop
0x18003929d  lea     rcx, [rbp+57h+Size]; pvar
0x1800392a1  call    cs:__imp_PropVariantClear
0x1800392a7  add     rdi, 14h
0x1800392ab  jmp     loc_1800390E7
0x1800392b0  mov     edx, 381h
0x1800392b5  jmp     short loc_1800392BC
0x1800392b7  mov     edx, 37Fh; void *
0x1800392bc  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800392c3  mov     r9d, eax; char *
0x1800392c6  mov     rcx, [rbp+5Fh]; this
0x1800392ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392cf  nop
0x1800392d0  lea     rcx, [rbp+57h+var_A0]
0x1800392d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800392d9  jmp     short loc_1800392F4
0x1800392db  mov     rcx, [rbp+5Fh]; this
0x1800392df  mov     r9d, eax; char *
0x1800392e2  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800392e9  mov     edx, 37Ch; void *
0x1800392ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392f3  nop
0x1800392f4  lea     rcx, [rbp+57h+var_B0]
0x1800392f8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800392fd  jmp     short loc_18003932C
0x1800392ff  lea     rcx, [rbp+57h+pvar]; pvar
0x180039303  call    cs:__imp_PropVariantClear
0x180039309  mov     ebx, 80070490h
0x18003930e  jmp     loc_180039465
0x180039313  mov     rcx, [rbp+5Fh]; this
0x180039317  mov     r9d, eax; char *
0x18003931a  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039321  mov     edx, 376h; void *
0x180039326  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003932b  nop
0x18003932c  lea     rcx, [rbp+57h+pvar]; pvar
0x180039330  call    cs:__imp_PropVariantClear
0x180039336  jmp     loc_180039465
0x18003933b  mov     rcx, rdi
0x18003933e  call    ??8@YA_NAEBU_DEVPROPKEY@@0@Z; operator==(_DEVPROPKEY const &,_DEVPROPKEY const &)
0x180039343  mov     sil, al
0x180039346  lea     rdx, [rbp+57h+pv]
0x18003934a  lea     rcx, [rbp+57h+var_98]
0x18003934e  call    ??4?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x180039353  nop
0x180039354  mov     rcx, [rbp+57h+pv]; pv
0x180039358  mov     [rbp+57h+pv], r12
0x18003935c  test    rcx, rcx
0x18003935f  jz      short loc_180039368
0x180039361  call    cs:__imp_CoTaskMemFree
0x180039367  nop
0x180039368  lea     rcx, [rbp+57h+Size]; pvar
0x18003936c  call    cs:__imp_PropVariantClear
0x180039372  mov     rdi, [rbp+57h+var_98]
0x180039376  test    rdi, rdi
0x180039379  jz      loc_180039474
0x18003937f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039386  mov     ecx, 10h; unsigned __int64
0x18003938b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180039390  mov     rbx, rax
0x180039393  test    rax, rax
0x180039396  jz      short loc_1800393E3
0x180039398  mov     [rax], r12
0x18003939b  mov     [rax+8], r12
0x18003939f  mov     [rax], sil
0x1800393a2  lea     rcx, [rax+8]
0x1800393a6  lea     rdx, [rbp+57h+var_98]
0x1800393aa  call    ??4?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::operator=(wistd::unique_ptr<_GUID [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800393af  mov     [rbp+57h+var_B0], r12
0x1800393b3  mov     rdx, [r14]
0x1800393b6  mov     [r14], rbx
0x1800393b9  test    rdx, rdx
0x1800393bc  jz      short loc_1800393C3
0x1800393be  call    ??R?$default_delete@UPacketSizeConstraints@@@std@@QEBAXPEAUPacketSizeConstraints@@@Z; std::default_delete<PacketSizeConstraints>::operator()(PacketSizeConstraints *)
0x1800393c3  lea     rcx, [rbp+57h+var_B0]
0x1800393c7  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x1800393cc  nop
0x1800393cd  mov     rcx, [rbp+57h+var_98]; pv
0x1800393d1  test    rcx, rcx
0x1800393d4  jz      short loc_1800393DC
0x1800393d6  call    cs:__imp_CoTaskMemFree
0x1800393dc  xor     eax, eax
0x1800393de  jmp     loc_180039479
0x1800393e3  mov     [rbp+57h+var_B0], r12
0x1800393e7  mov     rcx, [rbp+5Fh]; this
0x1800393eb  mov     ebx, 8007000Eh
0x1800393f0  mov     r9d, ebx; char *
0x1800393f3  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x1800393fa  mov     edx, 3A0h; void *
0x1800393ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039404  lea     rcx, [rbp+57h+var_B0]
0x180039408  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x18003940d  nop
0x18003940e  test    rdi, rdi
0x180039411  jz      short loc_180039470
0x180039413  mov     rcx, rdi; pv
0x180039416  call    cs:__imp_CoTaskMemFree
0x18003941c  jmp     short loc_180039470
0x18003941e  mov     rcx, [rbp+5Fh]; this
0x180039422  mov     r9d, ebx; char *
0x180039425  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003942c  mov     edx, 38Ch; void *
0x180039431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039436  nop
0x180039437  mov     rcx, [rbp+57h+pv]; pv
0x18003943b  mov     [rbp+57h+pv], r12
0x18003943f  test    rcx, rcx
0x180039442  jz      short loc_180039465
0x180039444  call    cs:__imp_CoTaskMemFree
0x18003944a  jmp     short loc_180039465
0x18003944c  mov     rcx, [rbp+5Fh]; this
0x180039450  mov     r9d, eax; char *
0x180039453  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18003945a  mov     edx, 36Eh; void *
0x18003945f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039464  nop
0x180039465  lea     rcx, [rbp+57h+Size]; pvar
0x180039469  call    cs:__imp_PropVariantClear
0x18003946f  nop
0x180039470  mov     eax, ebx
0x180039472  jmp     short loc_180039479
0x180039474  mov     eax, 80070490h
0x180039479  mov     rcx, [rbp+57h+var_30]
0x18003947d  xor     rcx, rsp; StackCookie
0x180039480  call    __security_check_cookie
0x180039485  lea     r11, [rsp+0D0h+var_20]
0x18003948d  mov     rbx, [r11+30h]
0x180039491  mov     rsi, [r11+48h]
0x180039495  mov     rsp, r11
0x180039498  pop     r15
0x18003949a  pop     r14
0x18003949c  pop     r12
0x18003949e  pop     rdi
0x18003949f  pop     rbp
0x1800394a0  retn
```
