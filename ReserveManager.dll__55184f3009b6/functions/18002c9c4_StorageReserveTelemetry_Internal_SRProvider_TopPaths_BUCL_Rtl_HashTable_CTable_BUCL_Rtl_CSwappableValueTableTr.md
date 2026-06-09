# StorageReserveTelemetry::Internal::SRProvider::TopPaths_(BUCL::Rtl::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>> &,ushort const *,ushort)

- ea: `0x18002c9c4`
- end: `0x18002ce0c`
- name: `?TopPaths_@SRProvider@Internal@StorageReserveTelemetry@@QEAAXAEAV?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@Rtl@BUCL@@PEBGG@Z`
- size: `1096`
- prototype: `void __fastcall(__int64, __int64, unsigned __int64, __int16)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180027414`

## callees

- `0x180001470`
- `0x180003870`
- `0x180025c3c`
- `0x180026054`
- `0x18002821c`
- `0x180028510`
- `0x18002939c`
- `0x18002c9c4`
- `0x18002ceac`
- `0x18002cf48`
- `0x18002e01c`
- `0x18002f008`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002ca7b`
- `ntdll!RtlFreeHeap` at `0x18002cbb2`
- `ntdll!RtlFreeHeap` at `0x18002ca7b`
- `ntdll!RtlFreeHeap` at `0x18002cbb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002caac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002caac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cac0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002cac0`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::TopPaths_(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int16 a4)
{
  __int64 v4; // r14
  __int64 v5; // rdi
  __int16 v6; // r15
  void *v7; // r12
  StorageReserveTelemetry::Internal::SRProvider::PathMapPair *v8; // rbx
  __int64 v9; // rsi
  char *v10; // rbx
  int v11; // r12d
  unsigned int v12; // r15d
  char *v13; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbx
  unsigned __int64 v17; // r8
  void *v18; // rdi
  HANDLE v19; // rax
  HANDLE v20; // rax
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r9
  __int64 v23; // r8
  __int64 v24; // rax
  void **v25; // rbx
  __int16 v26; // [rsp+E0h] [rbp-80h] BYREF
  __int16 v27; // [rsp+E2h] [rbp-7Eh] BYREF
  __int64 v28; // [rsp+E8h] [rbp-78h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-70h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-68h] BYREF
  PVOID P; // [rsp+100h] [rbp-60h] BYREF
  int v32; // [rsp+108h] [rbp-58h]
  LPVOID lpMem; // [rsp+110h] [rbp-50h] BYREF
  int v34; // [rsp+118h] [rbp-48h] BYREF
  int v35; // [rsp+11Ch] [rbp-44h] BYREF
  int v36; // [rsp+120h] [rbp-40h] BYREF
  int v37; // [rsp+124h] [rbp-3Ch] BYREF
  int v38; // [rsp+128h] [rbp-38h] BYREF
  int v39; // [rsp+12Ch] [rbp-34h] BYREF
  __int64 v40; // [rsp+130h] [rbp-30h] BYREF
  __int64 v41; // [rsp+138h] [rbp-28h] BYREF
  __int64 v42; // [rsp+140h] [rbp-20h] BYREF
  __int64 v43; // [rsp+148h] [rbp-18h] BYREF
  __int64 v44; // [rsp+150h] [rbp-10h] BYREF
  __int64 v45; // [rsp+158h] [rbp-8h] BYREF
  __int64 v46; // [rsp+160h] [rbp+0h] BYREF
  __int64 v47; // [rsp+168h] [rbp+8h] BYREF
  __int64 v48; // [rsp+170h] [rbp+10h] BYREF
  __int64 v49; // [rsp+178h] [rbp+18h] BYREF
  __int64 v50; // [rsp+180h] [rbp+20h] BYREF
  __int64 v51; // [rsp+190h] [rbp+30h] BYREF
  int v52; // [rsp+198h] [rbp+38h]
  __int64 v53; // [rsp+1A0h] [rbp+40h]
  int v54; // [rsp+1A8h] [rbp+48h]
  __int64 v55; // [rsp+1B0h] [rbp+50h]
  int v56; // [rsp+1B8h] [rbp+58h]
  __int64 v57; // [rsp+1C0h] [rbp+60h]
  int v58; // [rsp+1C8h] [rbp+68h]
  __int64 v59; // [rsp+1D0h] [rbp+70h]
  int v60; // [rsp+1D8h] [rbp+78h]
  __int64 v61; // [rsp+1E0h] [rbp+80h]
  int v62; // [rsp+1E8h] [rbp+88h]
  __int64 v63; // [rsp+1F0h] [rbp+90h]
  int v64; // [rsp+1F8h] [rbp+98h]
  __int64 v65; // [rsp+200h] [rbp+A0h]
  int v66; // [rsp+208h] [rbp+A8h]
  __int64 v67; // [rsp+210h] [rbp+B0h]
  int v68; // [rsp+218h] [rbp+B8h]
  __int64 v69; // [rsp+220h] [rbp+C0h]
  int v70; // [rsp+228h] [rbp+C8h]
  __int64 v71; // [rsp+230h] [rbp+D0h] BYREF

  v4 = 10;
  v26 = a4;
  v5 = 10;
  v28 = a3;
  v6 = a4;
  v29 = a2;
  v7 = (void *)a3;
  v8 = (StorageReserveTelemetry::Internal::SRProvider::PathMapPair *)&v51;
  v9 = a2;
  do
  {
    StorageReserveTelemetry::Internal::SRProvider::PathMapPair::PathMapPair(v8, a2, a3);
    v8 = (StorageReserveTelemetry::Internal::SRProvider::PathMapPair *)((char *)v8 + 16);
    --v5;
  }
  while ( v5 );
  StorageReserveTelemetry::Internal::SRProvider::HeapifyTopTen((__int64)&v51, v9, a3);
  P = 0;
  v32 = 0;
  if ( (int)PiiFilter::Initialize((PiiFilter *)&P) >= 0 )
  {
    v11 = v32;
    v12 = 0;
    v13 = (char *)P;
    do
    {
      if ( *(_WORD *)*(&v51 + 2 * v12) )
      {
        ProcessHeap = GetProcessHeap();
        v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x20Au);
        v30 = (__int64)v15;
        v16 = v15;
        if ( !v15 )
          break;
        *v15 = 0;
        v15[260] = 0;
        if ( (v11 || (PiiFilter::Initialize((PiiFilter *)&P), v11 = v32, v13 = (char *)P, v32))
          && (int)PiiFilterExecute(v16) >= 0 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
            &v51 + 2 * v12,
            &v30);
          v16 = (unsigned __int16 *)v30;
        }
        else
        {
          wil::make_process_heap_string_nothrow((wil *)&lpMem, L"Unable to Mask  Due to Unhandled Failure", v17);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
            &v51 + 2 * v12,
            &lpMem);
          v18 = lpMem;
          if ( lpMem )
          {
            v19 = GetProcessHeap();
            HeapFree(v19, 0, v18);
          }
        }
        if ( v16 )
        {
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v16);
        }
      }
      ++v12;
    }
    while ( (int)v12 < 10 );
    if ( v13 )
    {
      RtlNameValueArray::Free((RtlNameValueArray *)v13);
      RtlNameValueArray::Free((RtlNameValueArray *)(v13 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    }
    v7 = (void *)v28;
    v6 = v26;
    v9 = v29;
  }
  else
  {
    v10 = (char *)P;
    if ( P )
    {
      RtlNameValueArray::Free((RtlNameValueArray *)P);
      RtlNameValueArray::Free((RtlNameValueArray *)(v10 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    }
  }
  v21 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  v23 = (__int64)v21;
  if ( *(_DWORD *)v21 > 5u )
  {
    v24 = *((_QWORD *)v21 + 3);
    if ( (*(_QWORD *)(v23 + 16) & 0x400000000000LL) != 0 && (v24 & 0x400000000000LL) == v24 )
    {
      v26 = *(_WORD *)(v9 + 32);
      v34 = v70;
      v41 = v69;
      v35 = v68;
      v42 = v67;
      v36 = v66;
      v43 = v65;
      v37 = v64;
      v44 = v63;
      v38 = v62;
      v45 = v61;
      v39 = v60;
      v46 = v59;
      LODWORD(lpMem) = v58;
      v47 = v57;
      LODWORD(v30) = v56;
      v48 = v55;
      LODWORD(v28) = v54;
      v49 = v53;
      LODWORD(v29) = v52;
      v50 = v51;
      v40 = 0x1000000;
      v27 = v6;
      P = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
        v23,
        (int)&byte_1800449B3,
        v23,
        v22,
        (const unsigned __int16 **)&P,
        (const unsigned __int16 **)&v50,
        (__int64)&v29,
        (const unsigned __int16 **)&v49,
        (__int64)&v28,
        (const unsigned __int16 **)&v48,
        (__int64)&v30,
        (const unsigned __int16 **)&v47,
        (__int64)&lpMem,
        (const unsigned __int16 **)&v46,
        (__int64)&v39,
        (const unsigned __int16 **)&v45,
        (__int64)&v38,
        (const unsigned __int16 **)&v44,
        (__int64)&v37,
        (const unsigned __int16 **)&v43,
        (__int64)&v36,
        (const unsigned __int16 **)&v42,
        (__int64)&v35,
        (const unsigned __int16 **)&v41,
        (__int64)&v34,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v40);
    }
  }
  v25 = (void **)&v71;
  do
  {
    v25 -= 2;
    StorageReserveTelemetry::Internal::SRProvider::PathMapPair::~PathMapPair(v25);
    --v4;
  }
  while ( v4 );
}

```

## disassembly

```asm
0x18002c9c4  push    rbp
0x18002c9c6  push    rbx
0x18002c9c7  push    rsi
0x18002c9c8  push    rdi
0x18002c9c9  push    r12
0x18002c9cb  push    r13
0x18002c9cd  push    r14
0x18002c9cf  push    r15
0x18002c9d1  lea     rbp, [rsp-0E8h]
0x18002c9d9  sub     rsp, 248h
0x18002c9e0  mov     rax, cs:__security_cookie
0x18002c9e7  xor     rax, rsp
0x18002c9ea  mov     [rbp+120h+var_50], rax
0x18002c9f1  mov     r14d, 0Ah
0x18002c9f7  mov     word ptr [rbp+120h+var_1A0], r9w
0x18002c9fc  mov     edi, r14d
0x18002c9ff  mov     [rbp+120h+var_198], r8
0x18002ca03  movzx   r15d, r9w
0x18002ca07  mov     [rbp+120h+var_190], rdx
0x18002ca0b  mov     r12, r8
0x18002ca0e  lea     rbx, [rbp+120h+var_F0]
0x18002ca12  mov     rsi, rdx
0x18002ca15  xor     r13d, r13d
0x18002ca18  mov     rcx, rbx; this
0x18002ca1b  call    ??0PathMapPair@SRProvider@Internal@StorageReserveTelemetry@@QEAA@XZ; StorageReserveTelemetry::Internal::SRProvider::PathMapPair::PathMapPair(void)
0x18002ca20  add     rbx, 10h
0x18002ca24  sub     rdi, 1
0x18002ca28  jnz     short loc_18002CA18
0x18002ca2a  mov     rdx, rsi
0x18002ca2d  lea     rcx, [rbp+120h+var_F0]
0x18002ca31  call    ?HeapifyTopTen@SRProvider@Internal@StorageReserveTelemetry@@CAXQEAUPathMapPair@123@AEAV?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@Rtl@BUCL@@@Z; StorageReserveTelemetry::Internal::SRProvider::HeapifyTopTen(StorageReserveTelemetry::Internal::SRProvider::PathMapPair * const,BUCL::Rtl::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>> &)
0x18002ca36  lea     rcx, [rbp+120h+P]; this
0x18002ca3a  mov     [rbp+120h+P], r13
0x18002ca3e  mov     [rbp+120h+var_178], r13d
0x18002ca42  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x18002ca47  test    eax, eax
0x18002ca49  jns     short loc_18002CA86
0x18002ca4b  mov     rbx, [rbp+120h+P]
0x18002ca4f  test    rbx, rbx
0x18002ca52  jz      loc_18002CBC5
0x18002ca58  mov     rcx, rbx; this
0x18002ca5b  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x18002ca60  lea     rcx, [rbx+30h]; this
0x18002ca64  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x18002ca69  mov     rcx, gs:60h
0x18002ca72  mov     r8, rbx; P
0x18002ca75  xor     edx, edx; Flags
0x18002ca77  mov     rcx, [rcx+30h]; HeapHandle
0x18002ca7b  call    cs:__imp_RtlFreeHeap
0x18002ca81  jmp     loc_18002CBC5
0x18002ca86  mov     r12d, [rbp+120h+var_178]
0x18002ca8a  mov     r15d, r13d
0x18002ca8d  mov     rsi, [rbp+120h+P]
0x18002ca91  mov     eax, r15d
0x18002ca94  lea     rdi, [rbp+120h+var_F0]
0x18002ca98  shl     rax, 4
0x18002ca9c  add     rdi, rax
0x18002ca9f  mov     rax, [rdi]
0x18002caa2  cmp     [rax], r13w
0x18002caa6  jz      loc_18002CB7E
0x18002caac  call    cs:__imp_GetProcessHeap
0x18002cab2  mov     edx, 8; dwFlags
0x18002cab7  mov     r8d, 20Ah; dwBytes
0x18002cabd  mov     rcx, rax; hHeap
0x18002cac0  call    cs:__imp_HeapAlloc
0x18002cac6  mov     [rbp+120h+var_188], rax
0x18002caca  mov     rbx, rax
0x18002cacd  test    rax, rax
0x18002cad0  jz      loc_18002CB8A
0x18002cad6  mov     [rax], r13w
0x18002cada  mov     [rax+208h], r13w
0x18002cae2  mov     r13, [rdi]
0x18002cae5  test    r12d, r12d
0x18002cae8  jnz     short loc_18002CB05
0x18002caea  lea     rcx, [rbp+120h+P]; this
0x18002caee  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x18002caf3  mov     r12d, [rbp+120h+var_178]
0x18002caf7  mov     rsi, [rbp+120h+P]
0x18002cafb  test    r12d, r12d
0x18002cafe  jnz     short loc_18002CB05
0x18002cb00  xor     r13d, r13d
0x18002cb03  jmp     short loc_18002CB1A
0x18002cb05  mov     r9, r13
0x18002cb08  mov     r8, rsi
0x18002cb0b  mov     rcx, rbx; unsigned __int16 *
0x18002cb0e  call    PiiFilterExecute
0x18002cb13  xor     r13d, r13d
0x18002cb16  test    eax, eax
0x18002cb18  jns     short loc_18002CB55
0x18002cb1a  lea     rdx, aUnableToMaskDu; "Unable to Mask  Due to Unhandled Failur"...
0x18002cb21  lea     rcx, [rbp+120h+lpMem]; this
0x18002cb25  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x18002cb2a  lea     rdx, [rbp+120h+lpMem]
0x18002cb2e  mov     rcx, rdi
0x18002cb31  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002cb36  mov     rdi, [rbp+120h+lpMem]
0x18002cb3a  test    rdi, rdi
0x18002cb3d  jz      short loc_18002CB65
0x18002cb3f  call    cs:__imp_GetProcessHeap
0x18002cb45  mov     r8, rdi; lpMem
0x18002cb48  xor     edx, edx; dwFlags
0x18002cb4a  mov     rcx, rax; hHeap
0x18002cb4d  call    cs:__imp_HeapFree
0x18002cb53  jmp     short loc_18002CB65
0x18002cb55  lea     rdx, [rbp+120h+var_188]
0x18002cb59  mov     rcx, rdi
0x18002cb5c  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002cb61  mov     rbx, [rbp+120h+var_188]
0x18002cb65  test    rbx, rbx
0x18002cb68  jz      short loc_18002CB7E
0x18002cb6a  call    cs:__imp_GetProcessHeap
0x18002cb70  mov     r8, rbx; lpMem
0x18002cb73  xor     edx, edx; dwFlags
0x18002cb75  mov     rcx, rax; hHeap
0x18002cb78  call    cs:__imp_HeapFree
0x18002cb7e  inc     r15d
0x18002cb81  cmp     r15d, r14d
0x18002cb84  jl      loc_18002CA91
0x18002cb8a  test    rsi, rsi
0x18002cb8d  jz      short loc_18002CBB8
0x18002cb8f  mov     rcx, rsi; this
0x18002cb92  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x18002cb97  lea     rcx, [rsi+30h]; this
0x18002cb9b  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x18002cba0  mov     rcx, gs:60h
0x18002cba9  mov     r8, rsi; P
0x18002cbac  xor     edx, edx; Flags
0x18002cbae  mov     rcx, [rcx+30h]; HeapHandle
0x18002cbb2  call    cs:__imp_RtlFreeHeap
0x18002cbb8  mov     r12, [rbp+120h+var_198]
0x18002cbbc  movzx   r15d, word ptr [rbp+120h+var_1A0]
0x18002cbc1  mov     rsi, [rbp+120h+var_190]
0x18002cbc5  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002cbca  mov     r8, rax
0x18002cbcd  mov     ecx, [rax]
0x18002cbcf  cmp     ecx, 5
0x18002cbd2  jbe     loc_18002CDD0
0x18002cbd8  mov     rax, [rax+18h]
0x18002cbdc  mov     rdx, 400000000000h
0x18002cbe6  mov     rcx, [r8+10h]
0x18002cbea  test    rdx, rcx
0x18002cbed  jz      loc_18002CDD0
0x18002cbf3  mov     rcx, rax
0x18002cbf6  and     rcx, rdx
0x18002cbf9  cmp     rcx, rax
0x18002cbfc  jnz     loc_18002CDD0
0x18002cc02  movzx   eax, word ptr [rsi+20h]
0x18002cc06  mov     word ptr [rbp+120h+var_1A0], ax
0x18002cc0a  mov     eax, [rbp+120h+var_58]
0x18002cc10  mov     dword ptr [rbp+120h+var_168], eax
0x18002cc13  mov     rax, [rbp+120h+var_60]
0x18002cc1a  mov     [rbp+120h+var_148], rax
0x18002cc1e  mov     eax, [rbp+120h+var_68]
0x18002cc24  mov     dword ptr [rbp+120h+var_168+4], eax
0x18002cc27  mov     rax, [rbp+120h+var_70]
0x18002cc2e  mov     [rbp+120h+var_140], rax
0x18002cc32  mov     eax, [rbp+120h+var_78]
0x18002cc38  mov     dword ptr [rbp+120h+var_160], eax
0x18002cc3b  mov     rax, [rbp+120h+var_80]
0x18002cc42  mov     [rbp+120h+var_138], rax
0x18002cc46  mov     eax, [rbp+120h+var_88]
0x18002cc4c  mov     dword ptr [rbp+120h+var_160+4], eax
0x18002cc4f  mov     rax, [rbp+120h+var_90]
0x18002cc56  mov     [rbp+120h+var_130], rax
0x18002cc5a  mov     eax, [rbp+120h+var_98]
0x18002cc60  mov     [rbp+120h+var_158], eax
0x18002cc63  mov     rax, [rbp+120h+var_A0]
0x18002cc6a  mov     [rbp+120h+var_128], rax
0x18002cc6e  mov     eax, [rbp+120h+var_A8]
0x18002cc71  mov     [rbp+120h+var_154], eax
0x18002cc74  mov     rax, [rbp+120h+var_B0]
0x18002cc78  mov     [rbp+120h+var_120], rax
0x18002cc7c  mov     eax, [rbp+120h+var_B8]
0x18002cc7f  mov     dword ptr [rbp+120h+lpMem], eax
0x18002cc82  mov     rax, [rbp+120h+var_C0]
0x18002cc86  mov     [rbp+120h+var_118], rax
0x18002cc8a  mov     eax, [rbp+120h+var_C8]
0x18002cc8d  mov     dword ptr [rbp+120h+var_188], eax
0x18002cc90  mov     rax, [rbp+120h+var_D0]
0x18002cc94  mov     [rbp+120h+var_110], rax
0x18002cc98  mov     eax, [rbp+120h+var_D8]
0x18002cc9b  mov     dword ptr [rbp+120h+var_198], eax
0x18002cc9e  mov     rax, [rbp+120h+var_E0]
0x18002cca2  mov     [rbp+120h+var_108], rax
0x18002cca6  mov     eax, [rbp+120h+var_E8]
0x18002cca9  mov     dword ptr [rbp+120h+var_190], eax
0x18002ccac  mov     rax, [rbp+120h+var_F0]
0x18002ccb0  mov     [rbp+120h+var_100], rax
0x18002ccb4  lea     rax, [rbp+120h+var_150]
0x18002ccb8  mov     [rsp+280h+var_1A8], rax; __int64
0x18002ccc0  lea     rax, [rbp+120h+var_1A0]
0x18002ccc4  mov     [rsp+280h+var_1B0], rax; __int64
0x18002cccc  lea     rax, [rbp+120h+var_1A0+2]
0x18002ccd0  mov     [rsp+280h+var_1B8], rax; __int64
0x18002ccd8  lea     rax, [rbp+120h+var_168]
0x18002ccdc  mov     [rsp+280h+var_1C0], rax; __int64
0x18002cce4  lea     rax, [rbp+120h+var_148]
0x18002cce8  mov     [rsp+280h+var_1C8], rax; __int64
0x18002ccf0  lea     rax, [rbp+120h+var_168+4]
0x18002ccf4  mov     [rsp+280h+var_1D0], rax; __int64
0x18002ccfc  lea     rax, [rbp+120h+var_140]
0x18002cd00  mov     [rsp+280h+var_1D8], rax; __int64
0x18002cd08  lea     rax, [rbp+120h+var_160]
0x18002cd0c  mov     [rsp+280h+var_1E0], rax; __int64
0x18002cd14  lea     rax, [rbp+120h+var_138]
0x18002cd18  mov     [rsp+280h+var_1E8], rax; __int64
0x18002cd20  lea     rax, [rbp+120h+var_160+4]
0x18002cd24  mov     [rsp+280h+var_1F0], rax; __int64
0x18002cd2c  lea     rax, [rbp+120h+var_130]
0x18002cd30  mov     [rsp+280h+var_1F8], rax; __int64
0x18002cd38  lea     rax, [rbp+120h+var_158]
0x18002cd3c  mov     [rsp+280h+var_200], rax; __int64
0x18002cd44  lea     rax, [rbp+120h+var_128]
0x18002cd48  mov     [rsp+280h+var_208], rax; __int64
0x18002cd4d  lea     rax, [rbp+120h+var_154]
0x18002cd51  mov     [rsp+280h+var_210], rax; __int64
0x18002cd56  lea     rax, [rbp+120h+var_120]
0x18002cd5a  mov     [rsp+280h+var_218], rax; __int64
0x18002cd5f  lea     rax, [rbp+120h+lpMem]
0x18002cd63  mov     [rsp+280h+var_220], rax; __int64
0x18002cd68  lea     rax, [rbp+120h+var_118]
0x18002cd6c  mov     [rsp+280h+var_228], rax; __int64
0x18002cd71  lea     rax, [rbp+120h+var_188]
0x18002cd75  mov     [rsp+280h+var_230], rax; __int64
0x18002cd7a  mov     [rbp+120h+var_150], 1000000h
0x18002cd82  mov     word ptr [rbp+120h+var_1A0+2], r15w
0x18002cd87  mov     [rbp+120h+P], r12
0x18002cd8b  lea     rax, [rbp+120h+var_110]
0x18002cd8f  mov     rcx, r8; int
0x18002cd92  mov     [rsp+280h+var_238], rax; __int64
0x18002cd97  lea     rdx, byte_1800449B3; int
0x18002cd9e  lea     rax, [rbp+120h+var_198]
0x18002cda2  mov     [rsp+280h+var_240], rax; __int64
0x18002cda7  lea     rax, [rbp+120h+var_108]
0x18002cdab  mov     [rsp+280h+var_248], rax; __int64
0x18002cdb0  lea     rax, [rbp+120h+var_190]
0x18002cdb4  mov     [rsp+280h+var_250], rax; __int64
0x18002cdb9  lea     rax, [rbp+120h+var_100]
0x18002cdbd  mov     [rsp+280h+var_258], rax; __int64
0x18002cdc2  lea     rax, [rbp+120h+P]
0x18002cdc6  mov     [rsp+280h+var_260], rax; __int64
0x18002cdcb  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U1@U2@U1@U2@U1@U2@U1@U2@U1@U2@U1@U2@U1@U2@U?$_tlgWrapperByVal@$01@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@343434343434343434AEBU?$_tlgWrapperByVal@$01@@5AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &)
0x18002cdd0  lea     rbx, [rbp+120h+var_50]
0x18002cdd7  sub     rbx, 10h
0x18002cddb  mov     rcx, rbx; this
0x18002cdde  call    ??1PathMapPair@SRProvider@Internal@StorageReserveTelemetry@@QEAA@XZ; StorageReserveTelemetry::Internal::SRProvider::PathMapPair::~PathMapPair(void)
0x18002cde3  sub     r14, 1
0x18002cde7  jnz     short loc_18002CDD7
0x18002cde9  mov     rcx, [rbp+120h+var_50]
0x18002cdf0  xor     rcx, rsp; StackCookie
0x18002cdf3  call    __security_check_cookie
0x18002cdf8  add     rsp, 248h
0x18002cdff  pop     r15
0x18002ce01  pop     r14
0x18002ce03  pop     r13
0x18002ce05  pop     r12
0x18002ce07  pop     rdi
0x18002ce08  pop     rsi
0x18002ce09  pop     rbx
0x18002ce0a  pop     rbp
0x18002ce0b  retn
```
