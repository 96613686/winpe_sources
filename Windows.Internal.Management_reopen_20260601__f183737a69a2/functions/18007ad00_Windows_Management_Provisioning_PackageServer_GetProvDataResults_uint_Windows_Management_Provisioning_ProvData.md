# Windows::Management::Provisioning::PackageServer::GetProvDataResults(uint *,Windows::Management::Provisioning::ProvDataResult * *)

- ea: `0x18007ad00`
- end: `0x18007b159`
- name: `?GetProvDataResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvDataResult@234@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvDataResult **)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000868c`
- `0x18000d388`
- `0x1800184c0`
- `0x18001c920`
- `0x18003e5d4`
- `0x1800700ac`
- `0x180079eb0`
- `0x18007a220`
- `0x18007a484`
- `0x18007a718`
- `0x18007a840`
- `0x18007ad00`
- `0x1800ae418`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007ae52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007af51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007ae52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007af51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007afa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007af86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007afa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Management::Provisioning::PackageServer::GetProvDataResults(
        Windows::Management::Provisioning::PackageServer *this,
        unsigned int *a2,
        struct Windows::Management::Provisioning::ProvDataResult **a3,
        const char *a4)
{
  __int64 v6; // r12
  unsigned __int64 v7; // rdi
  struct ResultData *v8; // rbx
  struct ResultData *v9; // rsi
  struct ResultData *v10; // rbx
  struct ResultData *v11; // r13
  __int64 v12; // rax
  int v13; // ecx
  wchar_t **i; // rdx
  HSTRING *v15; // rsi
  int v16; // eax
  HRESULT v17; // eax
  HSTRING v18; // rax
  int v19; // eax
  HRESULT v20; // eax
  int v21; // edx
  __int64 v22; // rax
  _QWORD *v23; // rcx
  int v24; // eax
  HRESULT v25; // eax
  int v26; // eax
  ResultData *v27; // r9
  __int64 result; // rax
  unsigned int v29; // eax
  HSTRING v30; // [rsp+20h] [rbp-118h] BYREF
  HSTRING v31; // [rsp+28h] [rbp-110h] BYREF
  void *v32; // [rsp+30h] [rbp-108h] BYREF
  HSTRING string; // [rsp+38h] [rbp-100h] BYREF
  __int64 v34; // [rsp+40h] [rbp-F8h] BYREF
  struct ResultData *v35; // [rsp+48h] [rbp-F0h] BYREF
  struct ResultData *v36; // [rsp+50h] [rbp-E8h]
  __int64 v37; // [rsp+58h] [rbp-E0h]
  _QWORD *v38; // [rsp+60h] [rbp-D8h] BYREF
  char v39[8]; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+78h] [rbp-C0h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v6 = 0;
    if ( !a2 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
        a4);
    if ( !a3 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
        a4);
    *a3 = 0;
    *a2 = 0;
    ProvResults::EnumerateByPackageId(&v35, (char *)this + 104);
    v7 = 0;
    v8 = v35;
    v9 = v36;
    while ( v8 != v9 )
    {
      ResultData::ResultData((ResultData *)v39, v8);
      v7 += v40;
      ResultData::~ResultData((ResultData *)v39);
      v8 = (struct ResultData *)((char *)v8 + 120);
    }
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvDataResult [0]>(&v32, v7);
    memset_0(v32, 0, 32 * v7);
    v10 = v35;
    v11 = v36;
    while ( v10 != v11 )
    {
      v12 = **(_QWORD **)v10;
      v34 = v12;
      while ( !*(_BYTE *)(v12 + 25) )
      {
        v13 = *(_DWORD *)(v12 + 28);
        string = 0;
        for ( i = &off_1800D15C0; ; i += 2 )
        {
          if ( i == (wchar_t **)&tls_used )
          {
            v29 = wil::verify_hresult<long>(2147943568LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x69,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryindex.cpp",
              (const char *)v29,
              (int)v30);
          }
          if ( v13 == *((_DWORD *)i + 2) )
            break;
        }
        v15 = (HSTRING *)((char *)v32 + 32 * v6);
        v31 = (HSTRING)*i;
        v16 = Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &v31);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFE,
            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
            (const char *)(unsigned int)v16,
            (int)v30);
        v17 = WindowsDuplicateString(string, v15);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
            (const char *)(unsigned int)v17,
            (int)v30);
        v30 = 0;
        v18 = (HSTRING)((char *)v10 + 16);
        if ( *((_QWORD *)v10 + 5) > 7u )
          v18 = *(HSTRING *)v18;
        v31 = v18;
        v19 = Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&v30, &v31);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
            (const char *)(unsigned int)v19,
            (int)v30);
        v20 = WindowsDuplicateString(v30, v15 + 1);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
            (const char *)(unsigned int)v20,
            (int)v30);
        v21 = 0;
        switch ( *((_DWORD *)v10 + 24) )
        {
          case 1:
            v21 = 1;
            break;
          case 2:
            v21 = 2;
            break;
          case 3:
            v21 = 3;
            break;
        }
        *((_DWORD *)v15 + 4) = v21;
        *((_DWORD *)v15 + 5) = *((_DWORD *)v10 + 21);
        v15[3] = 0;
        if ( *((_QWORD *)v10 + 14) )
        {
          v31 = 0;
          v22 = *((_QWORD *)v10 + 13);
          v23 = (_QWORD *)(*(_QWORD *)v22 + 32LL);
          if ( *(_QWORD *)(*(_QWORD *)v22 + 56LL) > 7u )
            v23 = (_QWORD *)*v23;
          v38 = v23;
          v24 = Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&v31, &v38);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x11F,
              (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
              (const char *)(unsigned int)v24,
              (int)v30);
          v25 = WindowsDuplicateString(v31, v15 + 3);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x120,
              (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
              (const char *)(unsigned int)v25,
              (int)v30);
          WindowsDeleteString(v31);
        }
        ++v6;
        WindowsDeleteString(v30);
        v30 = 0;
        WindowsDeleteString(string);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned int>>,std::_Iterator_base0>::operator++(&v34);
        v12 = v34;
      }
      v10 = (struct ResultData *)((char *)v10 + 120);
    }
    LODWORD(v30) = 0;
    v26 = ULongLongToULong(v7, (unsigned int *)&v30);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
        (const char *)(unsigned int)v26,
        (int)v30);
    *a3 = (struct Windows::Management::Provisioning::ProvDataResult *)v32;
    *a2 = (unsigned int)v30;
    v32 = 0;
    if ( v27 )
    {
      std::_Destroy_range<std::allocator<ResultData>>(v27);
      std::_Deallocate<16>(v35, 8 * ((v37 - (__int64)v35) >> 3));
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12D,
                           (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
                           (const char *)v27);
  }
  return result;
}

```

## disassembly

```asm
0x18007ad00  push    rbx
0x18007ad02  push    rsi
0x18007ad03  push    rdi
0x18007ad04  push    r12
0x18007ad06  push    r13
0x18007ad08  push    r14
0x18007ad0a  push    r15
0x18007ad0c  sub     rsp, 100h
0x18007ad13  mov     rax, cs:__security_cookie
0x18007ad1a  xor     rax, rsp
0x18007ad1d  mov     [rsp+138h+var_48], rax
0x18007ad25  mov     r15, r8
0x18007ad28  mov     r14, rdx
0x18007ad2b  mov     rdx, rcx
0x18007ad2e  xor     r12d, r12d
0x18007ad31  mov     rcx, [rsp+138h]; this
0x18007ad39  test    r14, r14
0x18007ad3c  jz      loc_18007B07E
0x18007ad42  mov     rcx, [rsp+138h]; this
0x18007ad4a  test    r15, r15
0x18007ad4d  jz      loc_18007B08F
0x18007ad53  mov     [r8], r12
0x18007ad56  mov     [r14], r12d
0x18007ad59  add     rdx, 68h ; 'h'
0x18007ad5d  lea     rcx, [rsp+138h+var_F0]
0x18007ad62  call    ?EnumerateByPackageId@ProvResults@@SA?AV?$vector@UResultData@@V?$allocator@UResultData@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; ProvResults::EnumerateByPackageId(std::wstring const &)
0x18007ad67  nop
0x18007ad68  mov     rdi, r12
0x18007ad6b  mov     rbx, [rsp+138h+var_F0]
0x18007ad70  mov     rsi, [rsp+138h+var_E8]
0x18007ad75  cmp     rbx, rsi
0x18007ad78  jz      short loc_18007AD9C
0x18007ad7a  mov     rdx, rbx; struct ResultData *
0x18007ad7d  lea     rcx, [rsp+138h+var_C8]; this
0x18007ad82  call    ??0ResultData@@QEAA@AEBU0@@Z; ResultData::ResultData(ResultData const &)
0x18007ad87  add     rdi, [rsp+138h+var_C0]
0x18007ad8c  lea     rcx, [rsp+138h+var_C8]; this
0x18007ad91  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x18007ad96  add     rbx, 78h ; 'x'
0x18007ad9a  jmp     short loc_18007AD75
0x18007ad9c  mov     rdx, rdi
0x18007ad9f  lea     rcx, [rsp+138h+var_108]
0x18007ada4  call    ??$make_unique_cotaskmem@$$BY0A@UProvDataResult@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvDataResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvDataResult [0]>(unsigned __int64)
0x18007ada9  nop
0x18007adaa  mov     r8, rdi
0x18007adad  shl     r8, 5; Size
0x18007adb1  xor     edx, edx; Val
0x18007adb3  mov     rcx, [rsp+138h+var_108]; void *
0x18007adb8  call    memset_0
0x18007adbd  mov     r9, [rsp+138h+var_F0]
0x18007adc2  mov     rbx, r9
0x18007adc5  mov     r10, [rsp+138h+var_E8]
0x18007adca  mov     r13, r10
0x18007adcd  cmp     rbx, r13
0x18007add0  jz      loc_18007AFDC
0x18007add6  mov     rax, [rbx]
0x18007add9  mov     rax, [rax]
0x18007addc  mov     [rsp+138h+var_F8], rax
0x18007ade1  cmp     byte ptr [rax+19h], 0
0x18007ade5  jnz     loc_18007AFD3
0x18007adeb  mov     ecx, [rax+1Ch]
0x18007adee  mov     [rsp+138h+string], 0
0x18007adf7  lea     rdx, off_1800D15C0; "Provisioning"
0x18007adfe  lea     rax, _tls_used
0x18007ae05  cmp     rdx, rax
0x18007ae08  jz      loc_18007B11C
0x18007ae0e  cmp     ecx, [rdx+8]
0x18007ae11  jnz     loc_18007AFCA
0x18007ae17  mov     rsi, r12
0x18007ae1a  shl     rsi, 5
0x18007ae1e  add     rsi, [rsp+138h+var_108]
0x18007ae23  mov     rax, [rdx]
0x18007ae26  mov     [rsp+138h+var_110], rax
0x18007ae2b  lea     rdx, [rsp+138h+var_110]
0x18007ae30  lea     rcx, [rsp+138h+string]
0x18007ae35  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007ae3a  mov     rcx, [rsp+138h]; this
0x18007ae42  test    eax, eax
0x18007ae44  js      loc_18007B0A1
0x18007ae4a  mov     rdx, rsi; newString
0x18007ae4d  mov     rcx, [rsp+138h+string]; string
0x18007ae52  call    cs:__imp_WindowsDuplicateString
0x18007ae59  nop     dword ptr [rax+rax+00h]
0x18007ae5e  mov     rcx, [rsp+138h]; this
0x18007ae66  test    eax, eax
0x18007ae68  js      loc_18007B0B5
0x18007ae6e  mov     [rsp+138h+var_118], 0; int
0x18007ae77  lea     rax, [rbx+10h]
0x18007ae7b  cmp     qword ptr [rbx+28h], 7
0x18007ae80  jbe     short loc_18007AE85
0x18007ae82  mov     rax, [rax]
0x18007ae85  mov     [rsp+138h+var_110], rax
0x18007ae8a  lea     rdx, [rsp+138h+var_110]
0x18007ae8f  lea     rcx, [rsp+138h+var_118]
0x18007ae94  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007ae99  mov     rcx, [rsp+138h]; this
0x18007aea1  test    eax, eax
0x18007aea3  js      loc_18007B0CA
0x18007aea9  lea     rdx, [rsi+8]; newString
0x18007aead  mov     rcx, [rsp+138h+var_118]; string
0x18007aeb2  call    cs:__imp_WindowsDuplicateString
0x18007aeb9  nop     dword ptr [rax+rax+00h]
0x18007aebe  mov     rcx, [rsp+138h]; this
0x18007aec6  xor     r8d, r8d
0x18007aec9  test    eax, eax
0x18007aecb  js      loc_18007B0DE
0x18007aed1  mov     edx, r8d
0x18007aed4  mov     ecx, [rbx+60h]
0x18007aed7  sub     ecx, 1
0x18007aeda  jz      short loc_18007AEF2
0x18007aedc  sub     ecx, 1
0x18007aedf  jz      short loc_18007AEEB
0x18007aee1  cmp     ecx, 1
0x18007aee4  jnz     short loc_18007AEF7
0x18007aee6  lea     edx, [rcx+2]
0x18007aee9  jmp     short loc_18007AEF7
0x18007aeeb  mov     edx, 2
0x18007aef0  jmp     short loc_18007AEF7
0x18007aef2  mov     edx, 1
0x18007aef7  mov     [rsi+10h], edx
0x18007aefa  mov     eax, [rbx+54h]
0x18007aefd  mov     [rsi+14h], eax
0x18007af00  mov     [rsi+18h], r8
0x18007af04  cmp     [rbx+70h], r8
0x18007af08  jz      short loc_18007AF7E
0x18007af0a  mov     [rsp+138h+var_110], r8
0x18007af0f  mov     rax, [rbx+68h]
0x18007af13  mov     rcx, [rax]
0x18007af16  add     rcx, 20h ; ' '
0x18007af1a  cmp     qword ptr [rcx+18h], 7
0x18007af1f  jbe     short loc_18007AF24
0x18007af21  mov     rcx, [rcx]
0x18007af24  mov     [rsp+138h+var_D8], rcx
0x18007af29  lea     rdx, [rsp+138h+var_D8]
0x18007af2e  lea     rcx, [rsp+138h+var_110]
0x18007af33  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007af38  mov     rcx, [rsp+138h]; this
0x18007af40  test    eax, eax
0x18007af42  js      loc_18007B0F3
0x18007af48  lea     rdx, [rsi+18h]; newString
0x18007af4c  mov     rcx, [rsp+138h+var_110]; string
0x18007af51  call    cs:__imp_WindowsDuplicateString
0x18007af58  nop     dword ptr [rax+rax+00h]
0x18007af5d  mov     rcx, [rsp+138h]; this
0x18007af65  test    eax, eax
0x18007af67  js      loc_18007B107
0x18007af6d  mov     rcx, [rsp+138h+var_110]; string
0x18007af72  call    cs:__imp_WindowsDeleteString
0x18007af79  nop     dword ptr [rax+rax+00h]
0x18007af7e  inc     r12
0x18007af81  mov     rcx, [rsp+138h+var_118]; string
0x18007af86  call    cs:__imp_WindowsDeleteString
0x18007af8d  nop     dword ptr [rax+rax+00h]
0x18007af92  mov     [rsp+138h+var_118], 0
0x18007af9b  mov     rcx, [rsp+138h+string]; string
0x18007afa0  call    cs:__imp_WindowsDeleteString
0x18007afa7  nop     dword ptr [rax+rax+00h]
0x18007afac  lea     rcx, [rsp+138h+var_F8]
0x18007afb1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>::operator++(void)
0x18007afb6  mov     r10, [rsp+138h+var_E8]
0x18007afbb  mov     r9, [rsp+138h+var_F0]
0x18007afc0  mov     rax, [rsp+138h+var_F8]
0x18007afc5  jmp     loc_18007ADE1
0x18007afca  add     rdx, 10h
0x18007afce  jmp     loc_18007AE05
0x18007afd3  add     rbx, 78h ; 'x'
0x18007afd7  jmp     loc_18007ADCD
0x18007afdc  mov     dword ptr [rsp+138h+var_118], 0; int
0x18007afe4  lea     rdx, [rsp+138h+var_118]; unsigned int *
0x18007afe9  mov     rcx, rdi; unsigned __int64
0x18007afec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007aff1  mov     rcx, [rsp+138h]; this
0x18007aff9  test    eax, eax
0x18007affb  js      loc_18007B143
0x18007b001  mov     rax, [rsp+138h+var_108]
0x18007b006  mov     [r15], rax
0x18007b009  mov     eax, dword ptr [rsp+138h+var_118]
0x18007b00d  mov     [r14], eax
0x18007b010  mov     [rsp+138h+var_108], 0
0x18007b019  test    r9, r9
0x18007b01c  jz      short loc_18007B052
0x18007b01e  mov     rdx, r10
0x18007b021  mov     rcx, r9; this
0x18007b024  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x18007b029  mov     rcx, [rsp+138h+var_F0]
0x18007b02e  mov     rax, [rsp+138h+var_E0]
0x18007b033  sub     rax, rcx
0x18007b036  sar     rax, 3
0x18007b03a  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x18007b044  imul    rax, rdx
0x18007b048  imul    rdx, rax, 78h ; 'x'
0x18007b04c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007b051  nop
0x18007b052  xor     eax, eax
0x18007b054  jmp     short loc_18007B05A
0x18007b056  mov     eax, dword ptr [rsp+138h+var_118]
0x18007b05a  mov     rcx, [rsp+138h+var_48]
0x18007b062  xor     rcx, rsp; StackCookie
0x18007b065  call    __security_check_cookie
0x18007b06a  add     rsp, 100h
0x18007b071  pop     r15
0x18007b073  pop     r14
0x18007b075  pop     r13
0x18007b077  pop     r12
0x18007b079  pop     rdi
0x18007b07a  pop     rsi
0x18007b07b  pop     rbx
0x18007b07c  retn
0x18007b07e  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b085  mov     edx, 0E4h; void *
0x18007b08a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007b08f  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b096  mov     edx, 0E5h; void *
0x18007b09b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007b0a1  mov     r9d, eax; char *
0x18007b0a4  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b0ab  mov     edx, 0FEh; void *
0x18007b0b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b0b5  mov     r9d, eax; char *
0x18007b0b8  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b0bf  mov     edx, 0FFh; void *
0x18007b0c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b0ca  mov     r9d, eax; char *
0x18007b0cd  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b0d4  mov     edx, 103h; void *
0x18007b0d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b0de  mov     r9d, eax; char *
0x18007b0e1  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b0e8  mov     edx, 104h; void *
0x18007b0ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b0f3  mov     r9d, eax; char *
0x18007b0f6  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b0fd  mov     edx, 11Fh; void *
0x18007b102  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b107  mov     r9d, eax; char *
0x18007b10a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b111  mov     edx, 120h; void *
0x18007b116  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b11c  mov     ecx, 80070490h
0x18007b121  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18007b126  mov     r9d, eax; char *
0x18007b129  mov     rcx, [rsp+138h]; this
0x18007b131  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x18007b138  mov     edx, 69h ; 'i'; void *
0x18007b13d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007b143  mov     r9d, eax; char *
0x18007b146  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b14d  mov     edx, 128h; void *
0x18007b152  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
