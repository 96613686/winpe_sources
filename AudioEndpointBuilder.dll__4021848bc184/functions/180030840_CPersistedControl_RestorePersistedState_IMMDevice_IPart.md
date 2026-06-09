# CPersistedControl::RestorePersistedState(IMMDevice *,IPart *)

- ea: `0x180030840`
- end: `0x180030f63`
- name: `?RestorePersistedState@CPersistedControl@@QEAAJPEAUIMMDevice@@PEAUIPart@@@Z`
- size: `1827`
- prototype: `__int64 __fastcall(CPersistedControl *__hidden this, struct IMMDevice *, struct IPart *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fd30`
- `0x1800301b8`

## callees

- `0x180010da8`
- `0x18001d420`
- `0x18001f374`
- `0x18001ff7c`
- `0x180030840`
- `0x180033578`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800309b5`
- `ntdll!EtwEventWriteTransfer` at `0x1800309b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030a88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030b84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030c30`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030d39`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030e06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030f27`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030a88`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030b84`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030c30`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030d39`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030e06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030f27`

## string_xrefs

- `0x180030a2c`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030b28`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030bd4`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030cdd`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180030daa`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPersistedControl::RestorePersistedState(
        CPersistedControl *this,
        struct IMMDevice *a2,
        struct IPart *a3)
{
  __int64 v6; // r10
  const WCHAR *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct IUnknown *v10; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rdi
  struct IMMDevice *v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  struct IMMDevice *v16; // rcx
  struct IMMDevice *v17; // rdi
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // r14
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  unsigned int v23; // edi
  struct IMMDevice *v24; // rdi
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rsi
  __int64 v26; // rcx
  int v27; // edi
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, struct IPart **); // rsi
  struct IPart *v30; // rcx
  int v31; // eax
  unsigned int v32; // edi
  struct IPart *v33; // rcx
  const struct _tlgProvider_t *v34; // rax
  int v35; // r8d
  int v36; // r9d
  int v37; // [rsp+20h] [rbp-E0h]
  _BYTE v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IMMDevice *v39; // [rsp+48h] [rbp-B8h] BYREF
  struct IPart *v40; // [rsp+50h] [rbp-B0h] BYREF
  int v41[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v44; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  _DWORD v48[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  __int128 v50; // [rsp+A0h] [rbp-60h] BYREF
  int v51; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v52; // [rsp+C0h] [rbp-40h]
  int v53; // [rsp+C8h] [rbp-38h]
  int v54; // [rsp+CCh] [rbp-34h]
  __int16 *v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+D8h] [rbp-28h]
  int v57; // [rsp+DCh] [rbp-24h]
  const WCHAR *v58; // [rsp+E0h] [rbp-20h]
  int v59; // [rsp+E8h] [rbp-18h]
  int v60; // [rsp+ECh] [rbp-14h]
  int *v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]
  __int64 *v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  _BYTE *v65; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v42 = 0;
  v50 = 0;
  v51 = 0;
  *(_OWORD *)pvar = 0;
  v47 = 0;
  v39 = 0;
  *(_QWORD *)v41 = 0;
  v40 = 0;
  v6 = *((_QWORD *)AudioEndpointBuilderTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v6 > 4u )
  {
    v38[0] = *((_BYTE *)this + 92);
    LODWORD(v45) = *((_DWORD *)this + 22);
    v43 = *((_DWORD *)this + 16);
    v7 = (const WCHAR *)*((_QWORD *)this + 9);
    v65 = v38;
    v66 = 1;
    v63 = &v45;
    v64 = 4;
    v61 = &v43;
    v62 = 4;
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = &LocaleName;
      v9 = 2;
    }
    v58 = v7;
    v59 = v9;
    v60 = 0;
    v48[0] = 184549376;
    v48[1] = 4;
    v49 = 0;
    v52 = *(unsigned __int16 **)(v6 + 8);
    v53 = *v52;
    v54 = 2;
    v55 = word_180077812;
    v56 = 104;
    v57 = 1;
    v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    v37 = 6;
    EtwEventWriteTransfer(*(_QWORD *)(v6 + 32), v48, 0, 0);
  }
  (*(void (__fastcall **)(CPersistedControl *, __int128 *))(*(_QWORD *)this + 40LL))(this, &v50);
  if ( a2 )
  {
    v16 = v39;
    v39 = 0;
    if ( v16 )
      ((void (__fastcall *)(struct IMMDevice *))v16->lpVtbl->Release)(v16);
    v39 = a2;
    ((void (__fastcall *)(struct IMMDevice *))a2->lpVtbl->AddRef)(a2);
  }
  else
  {
    v10 = g_DeviceEnumerator;
    Release = g_DeviceEnumerator->lpVtbl[1].Release;
    v12 = v39;
    v39 = 0;
    if ( v12 )
    {
      ((void (__fastcall *)(struct IMMDevice *))v12->lpVtbl->Release)(v12);
      v10 = g_DeviceEnumerator;
    }
    v13 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IMMDevice **))Release)(
            v10,
            *((_QWORD *)this + 9),
            &v39);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x244,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
        (const char *)(unsigned int)v13,
        v37);
      if ( v40 )
        ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
      if ( *(_QWORD *)v41 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
      if ( v39 )
        ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
      PropVariantClear(pvar);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      return v14;
    }
  }
  v17 = v39;
  OpenPropertyStore = v39->lpVtbl->OpenPropertyStore;
  v19 = v42;
  v42 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(v17, 0, &v42);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v20,
      v37);
    if ( v40 )
      ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
    if ( *(_QWORD *)v41 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    if ( v39 )
      ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
    PropVariantClear(pvar);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    return v21;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v42 + 40LL))(v42, &v50, pvar);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v22,
      v37);
    if ( v40 )
      ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
    if ( *(_QWORD *)v41 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
    if ( v39 )
      ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
    PropVariantClear(pvar);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    return v23;
  }
  if ( LOWORD(pvar[0]) )
  {
    if ( a3 )
    {
      v33 = v40;
      v40 = 0;
      if ( v33 )
        ((void (__fastcall *)(struct IPart *))v33->lpVtbl->Release)(v33);
      v40 = a3;
      ((void (__fastcall *)(struct IPart *))a3->lpVtbl->AddRef)(a3);
    }
    else
    {
      v24 = v39;
      Activate = v39->lpVtbl->Activate;
      v26 = *(_QWORD *)v41;
      *(_QWORD *)v41 = 0;
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v27 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64, _QWORD))Activate)(
              v24,
              &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
              1,
              0);
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x25A,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v27,
          (int)"Failed to activate device topology for device %ls",
          *((const char **)this + 9));
        if ( v40 )
          ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
        if ( *(_QWORD *)v41 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
        if ( v39 )
          ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
        PropVariantClear(pvar);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        return (unsigned int)v27;
      }
      v28 = *(_QWORD *)v41;
      v29 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IPart **))(**(_QWORD **)v41 + 56LL);
      v30 = v40;
      v40 = 0;
      if ( v30 )
        ((void (__fastcall *)(struct IPart *))v30->lpVtbl->Release)(v30);
      v31 = v29(v28, *((unsigned int *)this + 16), &v40);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x25C,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
          (const char *)(unsigned int)v31,
          (int)v41);
        if ( v40 )
          ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
        if ( *(_QWORD *)v41 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
        if ( v39 )
          ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
        PropVariantClear(pvar);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        return v32;
      }
    }
    (*(void (__fastcall **)(CPersistedControl *, struct IPart *, PROPVARIANT *))(*(_QWORD *)this + 56LL))(
      this,
      v40,
      pvar);
    *((_BYTE *)this + 92) = 0;
  }
  else
  {
    v34 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v34 > 4u )
    {
      v38[0] = *((_BYTE *)this + 92);
      v44 = *((_DWORD *)this + 22);
      v43 = *((_DWORD *)this + 16);
      v45 = *((_QWORD *)this + 9);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v34,
        (unsigned int)&word_18007777E,
        v35,
        v36,
        (__int64)&v45,
        (__int64)&v43,
        (__int64)&v44,
        (__int64)v38);
    }
  }
  if ( v40 )
    ((void (__fastcall *)(struct IPart *))v40->lpVtbl->Release)(v40);
  if ( *(_QWORD *)v41 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
  if ( v39 )
    ((void (__fastcall *)(struct IMMDevice *))v39->lpVtbl->Release)(v39);
  PropVariantClear(pvar);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  return 0;
}

```

## disassembly

```asm
0x180030840  push    rbp
0x180030842  push    rbx
0x180030843  push    rsi
0x180030844  push    rdi
0x180030845  push    r14
0x180030847  push    r15
0x180030849  lea     rbp, [rsp-38h]
0x18003084e  sub     rsp, 138h
0x180030855  mov     rax, cs:__security_cookie
0x18003085c  xor     rax, rsp
0x18003085f  mov     [rbp+60h+var_40], rax
0x180030863  mov     rsi, r8
0x180030866  mov     rdi, rdx
0x180030869  mov     rbx, rcx
0x18003086c  xor     r15d, r15d
0x18003086f  mov     [rsp+160h+var_100], r15
0x180030874  xorps   xmm0, xmm0
0x180030877  xor     eax, eax
0x180030879  movups  [rbp+60h+var_C0], xmm0
0x18003087d  mov     [rbp+60h+var_B0], eax
0x180030880  xorps   xmm1, xmm1
0x180030883  movups  xmmword ptr [rsp+160h+pvar], xmm1
0x180030888  mov     [rbp+60h+var_D8], rax
0x18003088c  mov     [rsp+160h+var_118], r15
0x180030891  mov     qword ptr [rsp+160h+var_108], r15
0x180030896  mov     [rsp+160h+var_110], r15
0x18003089b  call    ?Instance@AudioEndpointBuilderTelemetryProvider@@KAPEAV1@XZ; AudioEndpointBuilderTelemetryProvider::Instance(void)
0x1800308a0  mov     r10, [rax+8]
0x1800308a4  mov     eax, [r10]
0x1800308a7  cmp     eax, 4
0x1800308aa  jbe     loc_1800309BB
0x1800308b0  movzx   eax, byte ptr [rbx+5Ch]
0x1800308b4  mov     [rsp+160h+var_120], al
0x1800308b8  mov     eax, [rbx+58h]
0x1800308bb  mov     dword ptr [rsp+160h+var_F0], eax
0x1800308bf  mov     eax, [rbx+40h]
0x1800308c2  mov     [rsp+160h+var_F8], eax
0x1800308c6  mov     rcx, [rbx+48h]
0x1800308ca  lea     rax, [rsp+160h+var_120]
0x1800308cf  mov     [rbp+60h+var_50], rax
0x1800308d3  mov     [rbp+60h+var_48], 1
0x1800308db  lea     rax, [rsp+160h+var_F0]
0x1800308e0  mov     [rbp+60h+var_60], rax
0x1800308e4  mov     [rbp+60h+var_58], 4
0x1800308ec  lea     rax, [rsp+160h+var_F8]
0x1800308f1  mov     [rbp+60h+var_70], rax
0x1800308f5  mov     [rbp+60h+var_68], 4
0x1800308fd  test    rcx, rcx
0x180030900  jz      short loc_180030924
0x180030902  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180030909  nop     dword ptr [rax+00000000h]
0x180030910  lea     rax, [rax+1]
0x180030914  cmp     word ptr [rcx+rax*2], 0
0x180030919  jnz     short loc_180030910
0x18003091b  lea     eax, ds:2[rax*2]
0x180030922  jmp     short loc_180030930
0x180030924  lea     rcx, LocaleName
0x18003092b  mov     eax, 2
0x180030930  mov     [rbp+60h+var_80], rcx
0x180030934  mov     [rbp+60h+var_78], eax
0x180030937  mov     [rbp+60h+var_74], r15d
0x18003093b  mov     [rbp+60h+var_D0], 0B000000h
0x180030942  movzx   eax, cs:word_180077808
0x180030949  mov     [rbp+60h+var_CC], eax
0x18003094c  mov     [rbp+60h+var_C8], r15
0x180030950  mov     rax, [r10+8]
0x180030954  mov     [rbp+60h+var_A0], rax
0x180030958  movzx   eax, word ptr [rax]
0x18003095b  mov     [rbp+60h+var_98], eax
0x18003095e  mov     [rbp+60h+var_94], 2
0x180030965  lea     rax, word_180077812
0x18003096c  mov     [rbp+60h+var_90], rax
0x180030970  mov     [rbp+60h+var_88], 68h ; 'h'
0x180030977  mov     [rbp+60h+var_84], 1
0x18003097e  lea     rax, _TraceLoggingMetadataEnd
0x180030985  lea     rcx, _TraceLoggingMetadata
0x18003098c  sub     eax, ecx
0x18003098e  mov     [rsp+160h+var_F4], eax
0x180030992  mov     eax, [rsp+160h+var_F4]
0x180030996  lea     rax, [rbp+60h+var_A0]
0x18003099a  mov     [rsp+160h+var_138], rax
0x18003099f  mov     [rsp+160h+var_140], 6; int
0x1800309a7  xor     r9d, r9d
0x1800309aa  xor     r8d, r8d
0x1800309ad  lea     rdx, [rbp+60h+var_D0]
0x1800309b1  mov     rcx, [r10+20h]
0x1800309b5  call    cs:__imp_EtwEventWriteTransfer
0x1800309bb  mov     rax, [rbx]
0x1800309be  lea     rdx, [rbp+60h+var_C0]
0x1800309c2  mov     rcx, rbx
0x1800309c5  mov     rax, [rax+28h]
0x1800309c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309ce  test    rdi, rdi
0x1800309d1  jnz     loc_180030AAD
0x1800309d7  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1800309de  mov     rax, [r9]
0x1800309e1  mov     rdi, [rax+28h]
0x1800309e5  mov     rcx, [rsp+160h+var_118]
0x1800309ea  mov     [rsp+160h+var_118], r15
0x1800309ef  test    rcx, rcx
0x1800309f2  jz      short loc_180030A07
0x1800309f4  mov     r8, [rcx]
0x1800309f7  mov     rax, [r8+10h]
0x1800309fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a00  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180030a07  lea     r8, [rsp+160h+var_118]
0x180030a0c  mov     rdx, [rbx+48h]
0x180030a10  mov     rcx, r9
0x180030a13  mov     rax, rdi
0x180030a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a1b  mov     edi, eax
0x180030a1d  test    eax, eax
0x180030a1f  jns     loc_180030ADD
0x180030a25  mov     rcx, [rbp+68h]; this
0x180030a29  mov     r9d, eax; char *
0x180030a2c  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030a33  mov     edx, 244h; void *
0x180030a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a3d  nop
0x180030a3e  mov     rcx, [rsp+160h+var_110]
0x180030a43  test    rcx, rcx
0x180030a46  jz      short loc_180030A55
0x180030a48  mov     rax, [rcx]
0x180030a4b  mov     rax, [rax+10h]
0x180030a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a54  nop
0x180030a55  mov     rcx, qword ptr [rsp+160h+var_108]
0x180030a5a  test    rcx, rcx
0x180030a5d  jz      short loc_180030A6C
0x180030a5f  mov     rax, [rcx]
0x180030a62  mov     rax, [rax+10h]
0x180030a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a6b  nop
0x180030a6c  mov     rcx, [rsp+160h+var_118]
0x180030a71  test    rcx, rcx
0x180030a74  jz      short loc_180030A83
0x180030a76  mov     rax, [rcx]
0x180030a79  mov     rax, [rax+10h]
0x180030a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a82  nop
0x180030a83  lea     rcx, [rsp+160h+pvar]; pvar
0x180030a88  call    cs:__imp_PropVariantClear
0x180030a8e  nop
0x180030a8f  mov     rcx, [rsp+160h+var_100]
0x180030a94  test    rcx, rcx
0x180030a97  jz      short loc_180030AA6
0x180030a99  mov     rax, [rcx]
0x180030a9c  mov     rax, [rax+10h]
0x180030aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030aa5  nop
0x180030aa6  mov     eax, edi
0x180030aa8  jmp     loc_180030F47
0x180030aad  mov     rcx, [rsp+160h+var_118]
0x180030ab2  mov     [rsp+160h+var_118], r15
0x180030ab7  test    rcx, rcx
0x180030aba  jz      short loc_180030AC9
0x180030abc  mov     rax, [rcx]
0x180030abf  mov     rax, [rax+10h]
0x180030ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ac8  nop
0x180030ac9  mov     [rsp+160h+var_118], rdi
0x180030ace  mov     rax, [rdi]
0x180030ad1  mov     rcx, rdi
0x180030ad4  mov     rax, [rax+8]
0x180030ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030add  mov     rdi, [rsp+160h+var_118]
0x180030ae2  mov     rax, [rdi]
0x180030ae5  mov     r14, [rax+20h]
0x180030ae9  mov     rcx, [rsp+160h+var_100]
0x180030aee  mov     [rsp+160h+var_100], r15
0x180030af3  test    rcx, rcx
0x180030af6  jz      short loc_180030B05
0x180030af8  mov     rdx, [rcx]
0x180030afb  mov     rax, [rdx+10h]
0x180030aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b04  nop
0x180030b05  lea     r8, [rsp+160h+var_100]
0x180030b0a  xor     edx, edx
0x180030b0c  mov     rcx, rdi
0x180030b0f  mov     rax, r14
0x180030b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b17  mov     edi, eax
0x180030b19  test    eax, eax
0x180030b1b  jns     loc_180030BA9
0x180030b21  mov     rcx, [rbp+68h]; this
0x180030b25  mov     r9d, eax; char *
0x180030b28  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030b2f  mov     edx, 24Ch; void *
0x180030b34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b39  nop
0x180030b3a  mov     rcx, [rsp+160h+var_110]
0x180030b3f  test    rcx, rcx
0x180030b42  jz      short loc_180030B51
0x180030b44  mov     rax, [rcx]
0x180030b47  mov     rax, [rax+10h]
0x180030b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b50  nop
0x180030b51  mov     rcx, qword ptr [rsp+160h+var_108]
0x180030b56  test    rcx, rcx
0x180030b59  jz      short loc_180030B68
0x180030b5b  mov     rax, [rcx]
0x180030b5e  mov     rax, [rax+10h]
0x180030b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b67  nop
0x180030b68  mov     rcx, [rsp+160h+var_118]
0x180030b6d  test    rcx, rcx
0x180030b70  jz      short loc_180030B7F
0x180030b72  mov     rax, [rcx]
0x180030b75  mov     rax, [rax+10h]
0x180030b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b7e  nop
0x180030b7f  lea     rcx, [rsp+160h+pvar]; pvar
0x180030b84  call    cs:__imp_PropVariantClear
0x180030b8a  nop
0x180030b8b  mov     rcx, [rsp+160h+var_100]
0x180030b90  test    rcx, rcx
0x180030b93  jz      short loc_180030BA2
0x180030b95  mov     rax, [rcx]
0x180030b98  mov     rax, [rax+10h]
0x180030b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ba1  nop
0x180030ba2  mov     eax, edi
0x180030ba4  jmp     loc_180030F47
0x180030ba9  mov     rcx, [rsp+160h+var_100]
0x180030bae  mov     rax, [rcx]
0x180030bb1  lea     r8, [rsp+160h+pvar]
0x180030bb6  lea     rdx, [rbp+60h+var_C0]
0x180030bba  mov     rax, [rax+28h]
0x180030bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bc3  mov     edi, eax
0x180030bc5  test    eax, eax
0x180030bc7  jns     loc_180030C55
0x180030bcd  mov     rcx, [rbp+68h]; this
0x180030bd1  mov     r9d, eax; char *
0x180030bd4  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180030bdb  mov     edx, 24Fh; void *
0x180030be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030be5  nop
0x180030be6  mov     rcx, [rsp+160h+var_110]
0x180030beb  test    rcx, rcx
0x180030bee  jz      short loc_180030BFD
0x180030bf0  mov     rax, [rcx]
0x180030bf3  mov     rax, [rax+10h]
0x180030bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bfc  nop
0x180030bfd  mov     rcx, qword ptr [rsp+160h+var_108]
0x180030c02  test    rcx, rcx
0x180030c05  jz      short loc_180030C14
0x180030c07  mov     rax, [rcx]
0x180030c0a  mov     rax, [rax+10h]
0x180030c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c13  nop
0x180030c14  mov     rcx, [rsp+160h+var_118]
0x180030c19  test    rcx, rcx
0x180030c1c  jz      short loc_180030C2B
0x180030c1e  mov     rax, [rcx]
0x180030c21  mov     rax, [rax+10h]
0x180030c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c2a  nop
0x180030c2b  lea     rcx, [rsp+160h+pvar]; pvar
0x180030c30  call    cs:__imp_PropVariantClear
0x180030c36  nop
0x180030c37  mov     rcx, [rsp+160h+var_100]
0x180030c3c  test    rcx, rcx
0x180030c3f  jz      short loc_180030C4E
0x180030c41  mov     rax, [rcx]
0x180030c44  mov     rax, [rax+10h]
0x180030c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c4d  nop
0x180030c4e  mov     eax, edi
0x180030c50  jmp     loc_180030F47
0x180030c55  cmp     word ptr [rsp+160h+pvar], 0
0x180030c5b  jz      loc_180030E7A
0x180030c61  test    rsi, rsi
0x180030c64  jnz     loc_180030E2B
0x180030c6a  mov     rdi, [rsp+160h+var_118]
0x180030c6f  mov     rax, [rdi]
0x180030c72  mov     rsi, [rax+18h]
0x180030c76  mov     rcx, qword ptr [rsp+160h+var_108]
0x180030c7b  mov     qword ptr [rsp+160h+var_108], r15
0x180030c80  test    rcx, rcx
0x180030c83  jz      short loc_180030C92
0x180030c85  mov     rax, [rcx]
0x180030c88  mov     rax, [rax+10h]
0x180030c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c91  nop
0x180030c92  lea     rax, [rsp+160h+var_108]
0x180030c97  mov     qword ptr [rsp+160h+var_140], rax; int
0x180030c9c  xor     r9d, r9d
0x180030c9f  mov     r8d, 1
0x180030ca5  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180030cac  mov     rcx, rdi
0x180030caf  mov     rax, rsi
0x180030cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cb7  mov     edi, eax
0x180030cb9  test    eax, eax
0x180030cbb  jns     loc_180030D5E
0x180030cc1  mov     rcx, [rbp+68h]; this
0x180030cc5  mov     rdx, [rbx+48h]
0x180030cc9  mov     [rsp+160h+var_138], rdx; char *
  ... truncated ...
```
