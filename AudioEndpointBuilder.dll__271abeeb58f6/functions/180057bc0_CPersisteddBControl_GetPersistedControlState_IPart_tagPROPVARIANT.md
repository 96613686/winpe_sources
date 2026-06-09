# CPersisteddBControl::GetPersistedControlState(IPart *,tagPROPVARIANT *)

- ea: `0x180057bc0`
- end: `0x180057d99`
- name: `?GetPersistedControlState@CPersisteddBControl@@UEAAJPEAUIPart@@PEAUtagPROPVARIANT@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(CPersisteddBControl *__hidden this, struct IPart *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x18001d560`
- `0x18001f374`
- `0x180034a74`
- `0x180057bc0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057d5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057d5a`

## string_xrefs

- `0x180057d45`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x180057d72`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
__int64 __fastcall CPersisteddBControl::GetPersistedControlState(
        CPersisteddBControl *this,
        struct IPart *a2,
        struct tagPROPVARIANT *a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // r9d
  int v8; // r8d
  HRESULT (__stdcall *Activate)(IPart *, DWORD, const IID *const, void **); // r14
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r9
  BYTE **unique_cotaskmem; // rax
  BYTE *v16; // rbx
  void *v17; // rcx
  __int64 v18; // rdi
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // r14d
  int v23; // [rsp+20h] [rbp-20h]
  int v24[2]; // [rsp+30h] [rbp-10h] BYREF
  BYTE *v25; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v27; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF
  __int64 v29; // [rsp+88h] [rbp+48h] BYREF

  v29 = 0;
  v25 = 0;
  v27 = 0;
  v6 = AudioEndpointBuilderTelemetryProvider::Provider();
  v8 = *(_DWORD *)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    LODWORD(pv) = *((_DWORD *)this + 16);
    *(_QWORD *)v24 = *((_QWORD *)this + 9);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (unsigned int)byte_180077579,
      v8,
      v7,
      (__int64)v24,
      (__int64)&pv);
  }
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  Activate = a2->lpVtbl->Activate;
  v10 = v29;
  v29 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = ((__int64 (__fastcall *)(struct IPart *, __int64, char *, __int64 *))Activate)(a2, 1, (char *)this + 96, &v29);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 875;
LABEL_9:
    v14 = (unsigned int)v11;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)v14,
      v23);
    goto LABEL_20;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 24LL))(v29, &v27);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 878;
    goto LABEL_9;
  }
  unique_cotaskmem = (BYTE **)wil::make_unique_cotaskmem_nothrow<float [0]>(&pv, v27);
  v16 = *unique_cotaskmem;
  *unique_cotaskmem = 0;
  v25 = v16;
  v17 = pv;
  pv = 0;
  if ( v17 )
    CoTaskMemFree(v17);
  if ( !v16 )
  {
    v12 = -2147024882;
    v14 = 2147942414LL;
    v13 = 881;
    goto LABEL_19;
  }
  v18 = 0;
  v19 = v27;
  if ( !v27 )
  {
LABEL_16:
    a3->vt = 65;
    a3->lVal = 4 * v19;
    a3->bstrblobVal.pData = v16;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    return 0;
  }
  while ( 1 )
  {
    LODWORD(pv) = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v29 + 40LL))(v29, (unsigned int)v18, &pv);
    v21 = v20;
    if ( v20 < 0 )
      break;
    *(_DWORD *)&v16[4 * v18] = (_DWORD)pv;
    v18 = (unsigned int)(v18 + 1);
    v19 = v27;
    if ( (unsigned int)v18 >= v27 )
      goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37B,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
    (const char *)(unsigned int)v20,
    v23);
  CoTaskMemFree(v16);
  v12 = v21;
LABEL_20:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  return v12;
}

```

## disassembly

```asm
0x180057bc0  push    rbp
0x180057bc2  push    rbx
0x180057bc3  push    rsi
0x180057bc4  push    rdi
0x180057bc5  push    r14
0x180057bc7  mov     rbp, rsp
0x180057bca  sub     rsp, 40h
0x180057bce  mov     rsi, r8
0x180057bd1  mov     rdi, rdx
0x180057bd4  mov     rbx, rcx
0x180057bd7  mov     [rbp+arg_18], 0
0x180057bdf  mov     [rbp+var_8], 0
0x180057be7  mov     [rbp+arg_0], 0
0x180057bee  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180057bf3  mov     r8d, [rax]
0x180057bf6  cmp     r8d, 4
0x180057bfa  jbe     short loc_180057C2B
0x180057bfc  mov     ecx, [rbx+40h]
0x180057bff  mov     dword ptr [rbp+pv], ecx
0x180057c02  mov     rcx, [rbx+48h]
0x180057c06  mov     qword ptr [rbp+var_10], rcx
0x180057c0a  lea     rcx, [rbp+pv]
0x180057c0e  mov     [rsp+40h+var_18], rcx
0x180057c13  lea     rcx, [rbp+var_10]
0x180057c17  mov     qword ptr [rsp+40h+var_20], rcx; int
0x180057c1c  lea     rdx, byte_180077579
0x180057c23  mov     rcx, rax
0x180057c26  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180057c2b  xorps   xmm0, xmm0
0x180057c2e  xor     eax, eax
0x180057c30  movups  xmmword ptr [rsi], xmm0
0x180057c33  mov     [rsi+10h], rax
0x180057c37  mov     rax, [rdi]
0x180057c3a  mov     r14, [rax+68h]
0x180057c3e  mov     rcx, [rbp+arg_18]
0x180057c42  mov     [rbp+arg_18], 0
0x180057c4a  test    rcx, rcx
0x180057c4d  jz      short loc_180057C5C
0x180057c4f  mov     rax, [rcx]
0x180057c52  mov     rax, [rax+10h]
0x180057c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c5b  nop
0x180057c5c  lea     r8, [rbx+60h]
0x180057c60  lea     r9, [rbp+arg_18]
0x180057c64  mov     edx, 1
0x180057c69  mov     rcx, rdi
0x180057c6c  mov     rax, r14
0x180057c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c74  mov     ebx, eax
0x180057c76  test    eax, eax
0x180057c78  jns     short loc_180057C81
0x180057c7a  mov     edx, 36Bh
0x180057c7f  jmp     short loc_180057CA0
0x180057c81  mov     rcx, [rbp+arg_18]
0x180057c85  mov     rax, [rcx]
0x180057c88  lea     rdx, [rbp+arg_0]
0x180057c8c  mov     rax, [rax+18h]
0x180057c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c95  mov     ebx, eax
0x180057c97  test    eax, eax
0x180057c99  jns     short loc_180057CA8
0x180057c9b  mov     edx, 36Eh
0x180057ca0  mov     r9d, eax
0x180057ca3  jmp     loc_180057D72
0x180057ca8  mov     edx, [rbp+arg_0]
0x180057cab  lea     rcx, [rbp+pv]
0x180057caf  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@M@wil@@YA?AV?$unique_ptr@$$BY0A@MU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<float [0]>(unsigned __int64)
0x180057cb4  mov     rbx, [rax]
0x180057cb7  mov     qword ptr [rax], 0
0x180057cbe  mov     [rbp+var_8], rbx
0x180057cc2  mov     rcx, [rbp+pv]; pv
0x180057cc6  mov     [rbp+pv], 0
0x180057cce  test    rcx, rcx
0x180057cd1  jz      short loc_180057CD9
0x180057cd3  call    cs:__imp_CoTaskMemFree
0x180057cd9  test    rbx, rbx
0x180057cdc  jz      loc_180057D65
0x180057ce2  xor     edi, edi
0x180057ce4  mov     eax, [rbp+arg_0]
0x180057ce7  test    eax, eax
0x180057ce9  jz      short loc_180057D22
0x180057ceb  mov     dword ptr [rbp+pv], 0
0x180057cf2  mov     rcx, [rbp+arg_18]
0x180057cf6  mov     rax, [rcx]
0x180057cf9  lea     r8, [rbp+pv]
0x180057cfd  mov     edx, edi
0x180057cff  mov     rax, [rax+28h]
0x180057d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d08  mov     r14d, eax
0x180057d0b  test    eax, eax
0x180057d0d  js      short loc_180057D3E
0x180057d0f  movss   xmm0, dword ptr [rbp+pv]
0x180057d14  movss   dword ptr [rbx+rdi*4], xmm0
0x180057d19  inc     edi
0x180057d1b  mov     eax, [rbp+arg_0]
0x180057d1e  cmp     edi, eax
0x180057d20  jb      short loc_180057CEB
0x180057d22  mov     word ptr [rsi], 41h ; 'A'
0x180057d27  shl     eax, 2
0x180057d2a  mov     [rsi+8], eax
0x180057d2d  mov     [rsi+10h], rbx
0x180057d31  lea     rcx, [rbp+arg_18]
0x180057d35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180057d3a  xor     eax, eax
0x180057d3c  jmp     short loc_180057D8E
0x180057d3e  mov     rcx, [rbp+28h]; this
0x180057d42  mov     r9d, r14d; char *
0x180057d45  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180057d4c  mov     edx, 37Bh; void *
0x180057d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d56  nop
0x180057d57  mov     rcx, rbx; pv
0x180057d5a  call    cs:__imp_CoTaskMemFree
0x180057d60  mov     ebx, r14d
0x180057d63  jmp     short loc_180057D83
0x180057d65  mov     ebx, 8007000Eh
0x180057d6a  mov     r9d, ebx; char *
0x180057d6d  mov     edx, 371h; void *
0x180057d72  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180057d79  mov     rcx, [rbp+28h]; this
0x180057d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057d82  nop
0x180057d83  lea     rcx, [rbp+arg_18]
0x180057d87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180057d8c  mov     eax, ebx
0x180057d8e  add     rsp, 40h
0x180057d92  pop     r14
0x180057d94  pop     rdi
0x180057d95  pop     rsi
0x180057d96  pop     rbx
0x180057d97  pop     rbp
0x180057d98  retn
```
