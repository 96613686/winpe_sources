# CTypeServices::ResolveItem(ushort const *,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer * *,unsigned __int64 *)

- ea: `0x180065d40`
- end: `0x18006614b`
- name: `?ResolveItem@CTypeServices@@UEAAJPEBGPEAUIBuffer@Streams@Storage@Windows@@_K1212PEAPEAU2345@PEA_K@Z`
- size: `1035`
- prototype: `int(CTypeServices *__hidden this, const unsigned __int16 *, struct Windows::Storage::Streams::IBuffer *, unsigned __int64, struct Windows::Storage::Streams::IBuffer *, unsigned __int64, struct Windows::Storage::Streams::IBuffer *, unsigned __int64, struct Windows::Storage::Streams::IBuffer **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task`

## callees

- `0x180016cf4`
- `0x1800205a0`
- `0x18002850c`
- `0x180029da4`
- `0x18002aa88`
- `0x18002b464`
- `0x18002c020`
- `0x18005ad88`
- `0x18005edd0`
- `0x180064400`
- `0x180065d40`
- `0x180067300`
- `0x180096a88`
- `0x1800c8458`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800660a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065d7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800660a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180066132`

## string_xrefs

- `0x1800660bc`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800660d1`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800660e6`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800660fb`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x180066118`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CTypeServices::ResolveItem(
        CTypeServices *this,
        const unsigned __int16 *a2,
        __int64 (__fastcall ***a3)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***),
        __int64 a4,
        __int64 (__fastcall ***a5)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***),
        unsigned __int64 a6,
        __int64 (__fastcall ***a7)(struct Windows::Storage::Streams::IBuffer *, GUID *, std::_Ref_count_base ***),
        unsigned __int64 a8,
        struct Windows::Storage::Streams::IBuffer **string,
        unsigned __int64 *a10)
{
  struct Windows::Storage::Streams::IBuffer **v13; // rsi
  unsigned __int64 *v14; // r14
  CTypeServices *v15; // rdi
  int QualifiedTypeNameFromDataStoreId; // eax
  unsigned int v17; // ebx
  PCWSTR StringRawBuffer; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r10
  unsigned __int64 v25; // r9
  __int64 v26; // r10
  __int64 v27; // r9
  const struct bond::blob *v28; // rax
  int v29; // eax
  const char *v30; // r9
  __int64 result; // rax
  int v32[4]; // [rsp+20h] [rbp-318h] BYREF
  int v33; // [rsp+30h] [rbp-308h]
  __int128 v34; // [rsp+38h] [rbp-300h] BYREF
  int v35; // [rsp+48h] [rbp-2F0h]
  __int128 v36; // [rsp+50h] [rbp-2E8h] BYREF
  int v37; // [rsp+60h] [rbp-2D8h]
  _BYTE v38[24]; // [rsp+68h] [rbp-2D0h] BYREF
  _BYTE v39[16]; // [rsp+80h] [rbp-2B8h] BYREF
  _BYTE v40[56]; // [rsp+90h] [rbp-2A8h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-270h]
  _BYTE v42[56]; // [rsp+D0h] [rbp-268h] BYREF
  __int64 v43; // [rsp+108h] [rbp-230h]
  _BYTE v44[56]; // [rsp+110h] [rbp-228h] BYREF
  unsigned __int64 v45; // [rsp+148h] [rbp-1F0h]
  _BYTE v46[56]; // [rsp+150h] [rbp-1E8h] BYREF
  unsigned __int64 v47; // [rsp+188h] [rbp-1B0h]
  _BYTE v48[56]; // [rsp+190h] [rbp-1A8h] BYREF
  unsigned __int64 v49; // [rsp+1C8h] [rbp-170h]
  _BYTE v50[56]; // [rsp+1D0h] [rbp-168h] BYREF
  __int64 v51; // [rsp+208h] [rbp-130h]
  _BYTE v52[56]; // [rsp+210h] [rbp-128h] BYREF
  _BYTE v53[56]; // [rsp+248h] [rbp-F0h] BYREF
  _BYTE v54[64]; // [rsp+280h] [rbp-B8h] BYREF
  _BYTE v55[120]; // [rsp+2C0h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v13 = string;
  *string = 0;
  v14 = a10;
  *a10 = 0;
  v15 = (CTypeServices *)((char *)this - 16);
  WindowsDeleteString(0);
  string = 0;
  try
  {
    QualifiedTypeNameFromDataStoreId = CTypeServices::GetQualifiedTypeNameFromDataStoreId(v15, a2, (HSTRING *)&string);
    v17 = QualifiedTypeNameFromDataStoreId;
    if ( QualifiedTypeNameFromDataStoreId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)(unsigned int)QualifiedTypeNameFromDataStoreId,
        v32[0]);
      WindowsDeleteString((HSTRING)string);
      result = v17;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)string, 0);
      CTypeServices::GetSchemaOfTypeNameInternal(v15, v38, StringRawBuffer);
      v36 = 0;
      v37 = 0;
      v19 = ConvertIBufferToBondBlob(a3, (struct bond::blob *)&v36);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v19,
          v32[0]);
      schematized_data::schematized_data(
        (schematized_data *)v54,
        (const struct bond::RuntimeSchema *)v38,
        (const struct bond::blob *)&v36);
      v34 = 0;
      v35 = 0;
      v20 = ConvertIBufferToBondBlob(a5, (struct bond::blob *)&v34);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F6,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v20,
          v32[0]);
      schematized_data::schematized_data(
        (schematized_data *)v53,
        (const struct bond::RuntimeSchema *)v38,
        (const struct bond::blob *)&v34);
      *(_OWORD *)v32 = 0;
      v33 = 0;
      v21 = ConvertIBufferToBondBlob(a7, (struct bond::blob *)v32);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3FA,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v21,
          v32[0]);
      schematized_data::schematized_data(
        (schematized_data *)v52,
        (const struct bond::RuntimeSchema *)v38,
        (const struct bond::blob *)v32);
      schematized_data::schematized_data((schematized_data *)v50, (const struct schematized_data *)v54);
      v51 = a4;
      schematized_data::schematized_data((schematized_data *)v48, (const struct schematized_data *)v53);
      v49 = a6;
      schematized_data::schematized_data((schematized_data *)v46, (const struct schematized_data *)v52);
      v47 = a8;
      v23 = a4 + 1;
      v24 = a4 + 1;
      if ( v22 > a4 + 1 )
        v24 = v22;
      if ( a8 > v23 )
        v23 = a8;
      v25 = v23 + 1;
      if ( v23 != v24 )
        v25 = v23;
      versioned<schematized_data>::versioned<schematized_data>(v55, v50, a4, v25);
      schematized_data::schematized_data((schematized_data *)v42, (const struct schematized_data *)v48);
      v43 = v26;
      schematized_data::schematized_data((schematized_data *)v40, (const struct schematized_data *)v46);
      v41 = v27;
      ResolveSchematizedData(v44, v55, v42, v40);
      schematized_data::~schematized_data((schematized_data *)v40);
      schematized_data::~schematized_data((schematized_data *)v42);
      schematized_data::~schematized_data((schematized_data *)v55);
      v28 = schematized_data::as_blob((schematized_data *)v44);
      v29 = ConvertBondBlobToIBuffer(v28, v13);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x402,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v29,
          v32[0]);
      *v14 = v45;
      schematized_data::~schematized_data((schematized_data *)v44);
      schematized_data::~schematized_data((schematized_data *)v46);
      schematized_data::~schematized_data((schematized_data *)v48);
      schematized_data::~schematized_data((schematized_data *)v50);
      schematized_data::~schematized_data((schematized_data *)v52);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v32[2]);
      schematized_data::~schematized_data((schematized_data *)v53);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v34 + 8));
      schematized_data::~schematized_data((schematized_data *)v54);
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)((char *)&v36 + 8));
      boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v39);
      WindowsDeleteString((HSTRING)string);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x406,
                        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
                        v30);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180065d40  push    rbx
0x180065d42  push    rsi
0x180065d43  push    rdi
0x180065d44  push    r13
0x180065d46  push    r14
0x180065d48  push    r15
0x180065d4a  sub     rsp, 308h
0x180065d51  mov     r13, r9
0x180065d54  mov     r15, r8
0x180065d57  mov     rbx, rdx
0x180065d5a  mov     rsi, [rsp+338h+string]
0x180065d62  mov     qword ptr [rsi], 0
0x180065d69  mov     r14, [rsp+338h+arg_48]
0x180065d71  mov     qword ptr [r14], 0
0x180065d78  lea     rdi, [rcx-10h]
0x180065d7c  xor     ecx, ecx; string
0x180065d7e  call    cs:__imp_WindowsDeleteString
0x180065d84  mov     [rsp+338h+string], 0
0x180065d90  lea     r8, [rsp+338h+string]; HSTRING *
0x180065d98  mov     rdx, rbx; unsigned __int16 *
0x180065d9b  mov     rcx, rdi; this
0x180065d9e  call    ?GetQualifiedTypeNameFromDataStoreId@CTypeServices@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; CTypeServices::GetQualifiedTypeNameFromDataStoreId(ushort const *,HSTRING__ * *)
0x180065da3  mov     ebx, eax
0x180065da5  test    eax, eax
0x180065da7  js      loc_18006610D
0x180065dad  xor     edx, edx; length
0x180065daf  mov     rcx, [rsp+338h+string]; string
0x180065db7  call    cs:__imp_WindowsGetStringRawBuffer
0x180065dbd  mov     r8, rax
0x180065dc0  lea     rdx, [rsp+338h+var_2D0]
0x180065dc5  mov     rcx, rdi
0x180065dc8  call    ?GetSchemaOfTypeNameInternal@CTypeServices@@AEAA?BVRuntimeSchema@bond@@PEBG@Z; CTypeServices::GetSchemaOfTypeNameInternal(ushort const *)
0x180065dcd  nop
0x180065dce  xorps   xmm0, xmm0
0x180065dd1  movdqu  [rsp+338h+var_2E8], xmm0
0x180065dd7  mov     [rsp+338h+var_2D8], 0
0x180065ddf  lea     rdx, [rsp+338h+var_2E8]; struct bond::blob *
0x180065de4  mov     rcx, r15; struct Windows::Storage::Streams::IBuffer *
0x180065de7  call    ?ConvertIBufferToBondBlob@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAVblob@bond@@@Z; ConvertIBufferToBondBlob(Windows::Storage::Streams::IBuffer *,bond::blob *)
0x180065dec  mov     rcx, [rsp+338h]; this
0x180065df4  test    eax, eax
0x180065df6  js      loc_1800660B9
0x180065dfc  lea     r8, [rsp+338h+var_2E8]; struct bond::blob *
0x180065e01  lea     rdx, [rsp+338h+var_2D0]; struct bond::RuntimeSchema *
0x180065e06  lea     rcx, [rsp+338h+var_B8]; this
0x180065e0e  call    ??0schematized_data@@QEAA@AEBVRuntimeSchema@bond@@AEBVblob@2@@Z; schematized_data::schematized_data(bond::RuntimeSchema const &,bond::blob const &)
0x180065e13  nop
0x180065e14  xorps   xmm0, xmm0
0x180065e17  movdqu  [rsp+338h+var_300], xmm0
0x180065e1d  mov     [rsp+338h+var_2F0], 0
0x180065e25  lea     rdx, [rsp+338h+var_300]; struct bond::blob *
0x180065e2a  mov     rcx, [rsp+338h+arg_20]; struct Windows::Storage::Streams::IBuffer *
0x180065e32  call    ?ConvertIBufferToBondBlob@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAVblob@bond@@@Z; ConvertIBufferToBondBlob(Windows::Storage::Streams::IBuffer *,bond::blob *)
0x180065e37  mov     rcx, [rsp+338h]; this
0x180065e3f  test    eax, eax
0x180065e41  js      loc_1800660CE
0x180065e47  lea     r8, [rsp+338h+var_300]; struct bond::blob *
0x180065e4c  lea     rdx, [rsp+338h+var_2D0]; struct bond::RuntimeSchema *
0x180065e51  lea     rcx, [rsp+338h+var_F0]; this
0x180065e59  call    ??0schematized_data@@QEAA@AEBVRuntimeSchema@bond@@AEBVblob@2@@Z; schematized_data::schematized_data(bond::RuntimeSchema const &,bond::blob const &)
0x180065e5e  nop
0x180065e5f  xorps   xmm0, xmm0
0x180065e62  movdqu  xmmword ptr [rsp+338h+var_318], xmm0; int
0x180065e68  mov     [rsp+338h+var_308], 0
0x180065e70  lea     rdx, [rsp+338h+var_318]; struct bond::blob *
0x180065e75  mov     rcx, [rsp+338h+arg_30]; struct Windows::Storage::Streams::IBuffer *
0x180065e7d  call    ?ConvertIBufferToBondBlob@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAVblob@bond@@@Z; ConvertIBufferToBondBlob(Windows::Storage::Streams::IBuffer *,bond::blob *)
0x180065e82  mov     rcx, [rsp+338h]; this
0x180065e8a  test    eax, eax
0x180065e8c  js      loc_1800660E3
0x180065e92  lea     r8, [rsp+338h+var_318]; struct bond::blob *
0x180065e97  lea     rdx, [rsp+338h+var_2D0]; struct bond::RuntimeSchema *
0x180065e9c  lea     rcx, [rsp+338h+var_128]; this
0x180065ea4  call    ??0schematized_data@@QEAA@AEBVRuntimeSchema@bond@@AEBVblob@2@@Z; schematized_data::schematized_data(bond::RuntimeSchema const &,bond::blob const &)
0x180065ea9  nop
0x180065eaa  lea     rdx, [rsp+338h+var_B8]; struct schematized_data *
0x180065eb2  lea     rcx, [rsp+338h+var_168]; this
0x180065eba  call    ??0schematized_data@@QEAA@AEBV0@@Z; schematized_data::schematized_data(schematized_data const &)
0x180065ebf  mov     [rsp+338h+var_130], r13
0x180065ec7  lea     rdx, [rsp+338h+var_F0]; struct schematized_data *
0x180065ecf  lea     rcx, [rsp+338h+var_1A8]; this
0x180065ed7  call    ??0schematized_data@@QEAA@AEBV0@@Z; schematized_data::schematized_data(schematized_data const &)
0x180065edc  mov     r8, [rsp+338h+arg_28]
0x180065ee4  mov     [rsp+338h+var_170], r8
0x180065eec  lea     rdx, [rsp+338h+var_128]; struct schematized_data *
0x180065ef4  lea     rcx, [rsp+338h+var_1E8]; this
0x180065efc  call    ??0schematized_data@@QEAA@AEBV0@@Z; schematized_data::schematized_data(schematized_data const &)
0x180065f01  mov     rcx, [rsp+338h+arg_38]
0x180065f09  mov     [rsp+338h+var_1B0], rcx
0x180065f11  lea     rax, [r13+1]
0x180065f15  mov     r10, rax
0x180065f18  cmp     r8, rax
0x180065f1b  cmova   r10, r8
0x180065f1f  cmp     rcx, rax
0x180065f22  cmova   rax, rcx
0x180065f26  lea     r9, [rax+1]
0x180065f2a  cmp     rax, r10
0x180065f2d  cmovnz  r9, rax
0x180065f31  mov     r8, r13
0x180065f34  lea     rdx, [rsp+338h+var_168]
0x180065f3c  lea     rcx, [rsp+338h+var_78]
0x180065f44  call    ??0?$versioned@Vschematized_data@@@@QEAA@AEBVschematized_data@@_K@Z; versioned<schematized_data>::versioned<schematized_data>(schematized_data const &,unsigned __int64)
0x180065f49  nop
0x180065f4a  lea     rdx, [rsp+338h+var_1A8]; struct schematized_data *
0x180065f52  lea     rcx, [rsp+338h+var_268]; this
0x180065f5a  call    ??0schematized_data@@QEAA@AEBV0@@Z; schematized_data::schematized_data(schematized_data const &)
0x180065f5f  mov     [rsp+338h+var_230], r10
0x180065f67  lea     rdx, [rsp+338h+var_1E8]; struct schematized_data *
0x180065f6f  lea     rcx, [rsp+338h+var_2A8]; this
0x180065f77  call    ??0schematized_data@@QEAA@AEBV0@@Z; schematized_data::schematized_data(schematized_data const &)
0x180065f7c  mov     [rsp+338h+var_270], r9
0x180065f84  lea     r9, [rsp+338h+var_2A8]
0x180065f8c  lea     r8, [rsp+338h+var_268]
0x180065f94  lea     rdx, [rsp+338h+var_78]
0x180065f9c  lea     rcx, [rsp+338h+var_228]
0x180065fa4  call    ?ResolveSchematizedData@@YA?AV?$versioned@Vschematized_data@@@@AEBV1@00@Z; ResolveSchematizedData(versioned<schematized_data> const &,versioned<schematized_data> const &,versioned<schematized_data> const &)
0x180065fa9  nop
0x180065faa  lea     rcx, [rsp+338h+var_2A8]; this
0x180065fb2  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180065fb7  nop
0x180065fb8  lea     rcx, [rsp+338h+var_268]; this
0x180065fc0  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180065fc5  nop
0x180065fc6  lea     rcx, [rsp+338h+var_78]; this
0x180065fce  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180065fd3  nop
0x180065fd4  lea     rcx, [rsp+338h+var_228]; this
0x180065fdc  call    ?as_blob@schematized_data@@QEBAAEBVblob@bond@@XZ; schematized_data::as_blob(void)
0x180065fe1  mov     rdx, rsi; struct Windows::Storage::Streams::IBuffer **
0x180065fe4  mov     rcx, rax; struct bond::blob *
0x180065fe7  call    ?ConvertBondBlobToIBuffer@@YAJAEBVblob@bond@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; ConvertBondBlobToIBuffer(bond::blob const &,Windows::Storage::Streams::IBuffer * *)
0x180065fec  mov     rcx, [rsp+338h]; this
0x180065ff4  test    eax, eax
0x180065ff6  js      loc_1800660F8
0x180065ffc  mov     rax, [rsp+338h+var_1F0]
0x180066004  mov     [r14], rax
0x180066007  lea     rcx, [rsp+338h+var_228]; this
0x18006600f  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180066014  nop
0x180066015  lea     rcx, [rsp+338h+var_1E8]; this
0x18006601d  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180066022  nop
0x180066023  lea     rcx, [rsp+338h+var_1A8]; this
0x18006602b  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180066030  nop
0x180066031  lea     rcx, [rsp+338h+var_168]; this
0x180066039  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x18006603e  nop
0x18006603f  lea     rcx, [rsp+338h+var_128]; this
0x180066047  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x18006604c  nop
0x18006604d  lea     rcx, [rsp+338h+var_318+8]; this
0x180066052  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180066057  nop
0x180066058  lea     rcx, [rsp+338h+var_F0]; this
0x180066060  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x180066065  nop
0x180066066  lea     rcx, [rsp+338h+var_300+8]; this
0x18006606b  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180066070  nop
0x180066071  lea     rcx, [rsp+338h+var_B8]; this
0x180066079  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x18006607e  nop
0x18006607f  lea     rcx, [rsp+338h+var_2E8+8]; this
0x180066084  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180066089  nop
0x18006608a  lea     rcx, [rsp+338h+var_2B8]; this
0x180066092  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180066097  nop
0x180066098  mov     rcx, [rsp+338h+string]; string
0x1800660a0  call    cs:__imp_WindowsDeleteString
0x1800660a6  xor     eax, eax
0x1800660a8  add     rsp, 308h
0x1800660af  pop     r15
0x1800660b1  pop     r14
0x1800660b3  pop     r13
0x1800660b5  pop     rdi
0x1800660b6  pop     rsi
0x1800660b7  pop     rbx
0x1800660b8  retn
0x1800660b9  mov     r9d, eax; char *
0x1800660bc  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800660c3  mov     edx, 3F2h; void *
0x1800660c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800660ce  mov     r9d, eax; char *
0x1800660d1  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800660d8  mov     edx, 3F6h; void *
0x1800660dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800660e3  mov     r9d, eax; char *
0x1800660e6  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800660ed  mov     edx, 3FAh; void *
0x1800660f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800660f8  mov     r9d, eax; char *
0x1800660fb  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x180066102  mov     edx, 402h; void *
0x180066107  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006610d  mov     rcx, [rsp+338h]; this
0x180066115  mov     r9d, ebx; char *
0x180066118  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x18006611f  mov     edx, 3EDh; void *
0x180066124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066129  nop
0x18006612a  mov     rcx, [rsp+338h+string]; string
0x180066132  call    cs:__imp_WindowsDeleteString
0x180066138  mov     eax, ebx
0x18006613a  jmp     loc_1800660A8
0x18006613f  mov     eax, dword ptr [rsp+338h+string]
0x180066146  jmp     loc_1800660A8
```
