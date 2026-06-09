# Windows::Internal::Storage::Cloud::CloudStoreCache::LoadDataDescriptor(ushort const *,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor * *)

- ea: `0x1800c78f0`
- end: `0x1800c7b17`
- name: `?LoadDataDescriptor@CloudStoreCache@Cloud@Storage@Internal@Windows@@UEAAJPEBG00PEAPEAUICloudStoreDataDescriptor@2345@@Z`
- size: `551`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStoreCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000f4b4`
- `0x18005ac7c`
- `0x18007d4c4`
- `0x180091b04`
- `0x1800c78f0`
- `0x1800c8458`
- `0x1801ad09c`
- `0x1801bda88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c79be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7afd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c79be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c7afd`

## string_xrefs

- `0x1800c799d`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x1800c7a43`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`
- `0x1800c7a88`: `onecoreuap\shell\cloudstore\store\cache\src\cloudstorecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStoreCache::LoadDataDescriptor(
        Windows::Internal::Storage::Cloud::CloudStoreCache *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor **a5)
{
  struct IStream *v8; // r15
  int Instance; // ebx
  void *v10; // rcx
  __int64 v12; // rdx
  void *v13; // rcx
  LPVOID v14; // r8
  int v15; // eax
  __int64 v16; // rdx
  void *v17; // rcx
  int v18; // [rsp+20h] [rbp-60h]
  int v19; // [rsp+20h] [rbp-60h]
  struct Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor **v20; // [rsp+38h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Storage::Streams::IBuffer *v22; // [rsp+48h] [rbp-38h] BYREF
  struct IStream *v23; // [rsp+50h] [rbp-30h] BYREF
  int v24; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+5Ch] [rbp-24h]
  int v26; // [rsp+64h] [rbp-1Ch]
  LPVOID *p_pv; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v28; // [rsp+70h] [rbp-10h] BYREF
  char v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v8 = (struct IStream *)a5;
  *a5 = 0;
  v24 = 2;
  v25 = 0;
  v26 = 0;
  pv = 0;
  LODWORD(a5) = 0;
  p_pv = &pv;
  v28 = 0;
  v29 = 1;
  Instance = Windows::Internal::Storage::Cloud::CloudStoreCache::Load(
               this,
               a2,
               a3,
               a4,
               0,
               (struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *)&v24,
               &v28,
               (unsigned int *)&a5);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( Instance == -2147024894 )
  {
    v10 = pv;
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
    return 2147942402LL;
  }
  if ( Instance < 0 )
  {
    v12 = 54;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
      (const char *)(unsigned int)Instance,
      v18);
LABEL_8:
    v13 = pv;
    pv = 0;
    if ( v13 )
      CoTaskMemFree(v13);
    return (unsigned int)Instance;
  }
  if ( v26 != 1 )
  {
    v22 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    v14 = pv;
    pv = 0;
    v15 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
            (int)a5,
            (int)a5,
            (__int64)v14,
            (void (__fastcall *)(__int64))CoTaskMemFree,
            &v22);
    Instance = v15;
    if ( v15 >= 0 )
    {
      v23 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      Instance = ConvertIBufferToIStream(v22, &v23);
      if ( Instance >= 0 )
      {
        Instance = Windows::Internal::Storage::Cloud::CloudStoreDataDescriptor_CreateInstance(
                     (Windows::Internal::Storage::Cloud *)a2,
                     a3,
                     a4,
                     0,
                     v25,
                     (unsigned __int64)v23,
                     v8,
                     v20);
        if ( Instance >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
          goto LABEL_23;
        }
        v16 = 67;
      }
      else
      {
        v16 = 66;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
        (const char *)(unsigned int)Instance,
        v19);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudstorecache.cpp",
        (const char *)(unsigned int)v15,
        v19);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    goto LABEL_8;
  }
  Instance = Windows::Internal::Storage::Cloud::CloudStoreDataDescriptor_CreateInstance(
               (Windows::Internal::Storage::Cloud *)a2,
               a3,
               a4,
               (const unsigned __int16 *)pv,
               v25,
               0,
               v8,
               v20);
  if ( Instance < 0 )
  {
    v12 = 58;
    goto LABEL_7;
  }
LABEL_23:
  v17 = pv;
  pv = 0;
  if ( v17 )
    CoTaskMemFree(v17);
  return 0;
}

```

## disassembly

```asm
0x1800c78f0  push    rbp
0x1800c78f2  push    rbx
0x1800c78f3  push    rsi
0x1800c78f4  push    rdi
0x1800c78f5  push    r12
0x1800c78f7  push    r14
0x1800c78f9  push    r15
0x1800c78fb  mov     rbp, rsp
0x1800c78fe  sub     rsp, 80h
0x1800c7905  mov     rdi, r9
0x1800c7908  mov     rsi, r8
0x1800c790b  mov     r14, rdx
0x1800c790e  xor     r12d, r12d
0x1800c7911  mov     r15, [rbp+arg_20]
0x1800c7915  mov     [r15], r12
0x1800c7918  mov     [rbp+var_28], 2
0x1800c791f  mov     [rbp+var_24], r12
0x1800c7923  mov     [rbp+var_1C], r12d
0x1800c7927  mov     [rbp+pv], r12
0x1800c792b  mov     dword ptr [rbp+arg_20], r12d
0x1800c792f  lea     rax, [rbp+pv]
0x1800c7933  mov     [rbp+var_18], rax
0x1800c7937  mov     [rbp+var_10], r12
0x1800c793b  mov     [rbp+var_8], 1
0x1800c793f  lea     rax, [rbp+arg_20]
0x1800c7943  mov     [rsp+80h+var_48], rax; struct Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor **
0x1800c7948  lea     rax, [rbp+var_10]
0x1800c794c  mov     [rsp+80h+var_50], rax; unsigned __int8 **
0x1800c7951  lea     rax, [rbp+var_28]
0x1800c7955  mov     [rsp+80h+var_58], rax; struct Windows::Internal::Storage::Cloud::CloudStoreMetadata *
0x1800c795a  mov     byte ptr [rsp+80h+var_60], r12b; int
0x1800c795f  call    ?Load@CloudStoreCache@Cloud@Storage@Internal@Windows@@QEAAJPEBG00_NPEAVCloudStoreMetadata@2345@PEAPEAEPEAK@Z; Windows::Internal::Storage::Cloud::CloudStoreCache::Load(ushort const *,ushort const *,ushort const *,bool,Windows::Internal::Storage::Cloud::CloudStoreMetadata *,uchar * *,ulong *)
0x1800c7964  mov     ebx, eax
0x1800c7966  lea     rcx, [rbp+var_18]
0x1800c796a  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800c796f  cmp     ebx, 80070002h
0x1800c7975  jnz     short loc_1800C7994
0x1800c7977  mov     rcx, [rbp+pv]; pv
0x1800c797b  mov     [rbp+pv], r12
0x1800c797f  test    rcx, rcx
0x1800c7982  jz      short loc_1800C798A
0x1800c7984  call    cs:__imp_CoTaskMemFree
0x1800c798a  mov     eax, 80070002h
0x1800c798f  jmp     loc_1800C7B05
0x1800c7994  test    ebx, ebx
0x1800c7996  jns     short loc_1800C79CB
0x1800c7998  mov     edx, 36h ; '6'; void *
0x1800c799d  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c79a4  mov     r9d, ebx; char *
0x1800c79a7  mov     rcx, [rbp+38h]; this
0x1800c79ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c79b0  nop
0x1800c79b1  mov     rcx, [rbp+pv]; pv
0x1800c79b5  mov     [rbp+pv], r12
0x1800c79b9  test    rcx, rcx
0x1800c79bc  jz      short loc_1800C79C4
0x1800c79be  call    cs:__imp_CoTaskMemFree
0x1800c79c4  mov     eax, ebx
0x1800c79c6  jmp     loc_1800C7B05
0x1800c79cb  cmp     [rbp+var_1C], 1
0x1800c79cf  jnz     short loc_1800C7A07
0x1800c79d1  mov     [rsp+80h+var_50], r15; struct IStream *
0x1800c79d6  mov     [rsp+80h+var_58], r12; unsigned __int64
0x1800c79db  mov     rax, [rbp+var_24]
0x1800c79df  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800c79e4  mov     r9, [rbp+pv]; unsigned __int16 *
0x1800c79e8  mov     r8, rdi; unsigned __int16 *
0x1800c79eb  mov     rdx, rsi; unsigned __int16 *
0x1800c79ee  mov     rcx, r14; this
0x1800c79f1  call    ?CloudStoreDataDescriptor_CreateInstance@Cloud@Storage@Internal@Windows@@YAJPEBG000_KPEAUIStream@@PEAPEAUICloudStoreDataDescriptor@1234@@Z; Windows::Internal::Storage::Cloud::CloudStoreDataDescriptor_CreateInstance(ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,IStream *,Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor * *)
0x1800c79f6  mov     ebx, eax
0x1800c79f8  test    eax, eax
0x1800c79fa  jns     loc_1800C7AF0
0x1800c7a00  mov     edx, 3Ah ; ':'
0x1800c7a05  jmp     short loc_1800C799D
0x1800c7a07  mov     [rbp+var_38], r12
0x1800c7a0b  lea     rcx, [rbp+var_38]
0x1800c7a0f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7a14  mov     r8, [rbp+pv]
0x1800c7a18  mov     [rbp+pv], r12
0x1800c7a1c  lea     rax, [rbp+var_38]
0x1800c7a20  mov     [rsp+80h+var_60], rax; int
0x1800c7a25  mov     r9, cs:__imp_CoTaskMemFree
0x1800c7a2c  mov     ecx, dword ptr [rbp+arg_20]
0x1800c7a2f  mov     edx, ecx
0x1800c7a31  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x1800c7a36  mov     ebx, eax
0x1800c7a38  test    eax, eax
0x1800c7a3a  jns     short loc_1800C7A63
0x1800c7a3c  mov     rcx, [rbp+38h]; this
0x1800c7a40  mov     r9d, eax; char *
0x1800c7a43  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c7a4a  mov     edx, 3Fh ; '?'; void *
0x1800c7a4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7a54  nop
0x1800c7a55  lea     rcx, [rbp+var_38]
0x1800c7a59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7a5e  jmp     loc_1800C79B1
0x1800c7a63  mov     [rbp+var_30], r12
0x1800c7a67  lea     rcx, [rbp+var_30]
0x1800c7a6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7a70  lea     rdx, [rbp+var_30]; struct IStream **
0x1800c7a74  mov     rcx, [rbp+var_38]; struct Windows::Storage::Streams::IBuffer *
0x1800c7a78  call    ?ConvertIBufferToIStream@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAPEAUIStream@@@Z; ConvertIBufferToIStream(Windows::Storage::Streams::IBuffer *,IStream * *)
0x1800c7a7d  mov     ebx, eax
0x1800c7a7f  test    eax, eax
0x1800c7a81  jns     short loc_1800C7AA7
0x1800c7a83  mov     edx, 42h ; 'B'; void *
0x1800c7a88  lea     r8, aOnecoreuapShel_56; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800c7a8f  mov     r9d, ebx; char *
0x1800c7a92  mov     rcx, [rbp+38h]; this
0x1800c7a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7a9b  nop
0x1800c7a9c  lea     rcx, [rbp+var_30]
0x1800c7aa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7aa5  jmp     short loc_1800C7A55
0x1800c7aa7  mov     rax, [rbp+var_30]
0x1800c7aab  mov     [rsp+80h+var_50], r15; struct IStream *
0x1800c7ab0  mov     [rsp+80h+var_58], rax; unsigned __int64
0x1800c7ab5  mov     rax, [rbp+var_24]
0x1800c7ab9  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x1800c7abe  xor     r9d, r9d; unsigned __int16 *
0x1800c7ac1  mov     r8, rdi; unsigned __int16 *
0x1800c7ac4  mov     rdx, rsi; unsigned __int16 *
0x1800c7ac7  mov     rcx, r14; this
0x1800c7aca  call    ?CloudStoreDataDescriptor_CreateInstance@Cloud@Storage@Internal@Windows@@YAJPEBG000_KPEAUIStream@@PEAPEAUICloudStoreDataDescriptor@1234@@Z; Windows::Internal::Storage::Cloud::CloudStoreDataDescriptor_CreateInstance(ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,IStream *,Windows::Internal::Storage::Cloud::ICloudStoreDataDescriptor * *)
0x1800c7acf  mov     ebx, eax
0x1800c7ad1  test    eax, eax
0x1800c7ad3  jns     short loc_1800C7ADC
0x1800c7ad5  mov     edx, 43h ; 'C'
0x1800c7ada  jmp     short loc_1800C7A88
0x1800c7adc  lea     rcx, [rbp+var_30]
0x1800c7ae0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7ae5  nop
0x1800c7ae6  lea     rcx, [rbp+var_38]
0x1800c7aea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c7aef  nop
0x1800c7af0  mov     rcx, [rbp+pv]; pv
0x1800c7af4  mov     [rbp+pv], r12
0x1800c7af8  test    rcx, rcx
0x1800c7afb  jz      short loc_1800C7B03
0x1800c7afd  call    cs:__imp_CoTaskMemFree
0x1800c7b03  xor     eax, eax
0x1800c7b05  add     rsp, 80h
0x1800c7b0c  pop     r15
0x1800c7b0e  pop     r14
0x1800c7b10  pop     r12
0x1800c7b12  pop     rdi
0x1800c7b13  pop     rsi
0x1800c7b14  pop     rbx
0x1800c7b15  pop     rbp
0x1800c7b16  retn
```
