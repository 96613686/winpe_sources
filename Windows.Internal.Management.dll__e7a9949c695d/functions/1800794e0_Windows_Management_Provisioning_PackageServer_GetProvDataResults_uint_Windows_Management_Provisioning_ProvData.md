# Windows::Management::Provisioning::PackageServer::GetProvDataResults(uint *,Windows::Management::Provisioning::ProvDataResult * *)

- ea: `0x1800794e0`
- end: `0x180079914`
- name: `?GetProvDataResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvDataResult@234@@Z`
- size: `1076`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *this, unsigned int *, struct Windows::Management::Provisioning::ProvDataResult **, const char *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004d50`
- `0x180005904`
- `0x1800084e0`
- `0x18000ce64`
- `0x180019ae4`
- `0x18001e414`
- `0x18003ec00`
- `0x18006ec38`
- `0x1800786cc`
- `0x180078a34`
- `0x180078c80`
- `0x180078f14`
- `0x180079038`
- `0x1800794e0`
- `0x1800ab318`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007968c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007968c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007974e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007974e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079762`

## pseudocode

```c
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
        for ( i = &off_1800CD640; ; i += 2 )
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
0x1800794e0  push    rbx
0x1800794e2  push    rsi
0x1800794e3  push    rdi
0x1800794e4  push    r12
0x1800794e6  push    r13
0x1800794e8  push    r14
0x1800794ea  push    r15
0x1800794ec  sub     rsp, 100h
0x1800794f3  mov     rax, cs:__security_cookie
0x1800794fa  xor     rax, rsp
0x1800794fd  mov     [rsp+138h+var_48], rax
0x180079505  mov     r15, r8
0x180079508  mov     r14, rdx
0x18007950b  mov     rdx, rcx
0x18007950e  xor     r12d, r12d
0x180079511  mov     rcx, [rsp+138h]; this
0x180079519  test    r14, r14
0x18007951c  jz      loc_180079839
0x180079522  mov     rcx, [rsp+138h]; this
0x18007952a  test    r15, r15
0x18007952d  jz      loc_18007984A
0x180079533  mov     [r8], r12
0x180079536  mov     [r14], r12d
0x180079539  add     rdx, 68h ; 'h'
0x18007953d  lea     rcx, [rsp+138h+var_F0]
0x180079542  call    ?EnumerateByPackageId@ProvResults@@SA?AV?$vector@UResultData@@V?$allocator@UResultData@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; ProvResults::EnumerateByPackageId(std::wstring const &)
0x180079547  nop
0x180079548  mov     rdi, r12
0x18007954b  mov     rbx, [rsp+138h+var_F0]
0x180079550  mov     rsi, [rsp+138h+var_E8]
0x180079555  cmp     rbx, rsi
0x180079558  jz      short loc_18007957C
0x18007955a  mov     rdx, rbx; struct ResultData *
0x18007955d  lea     rcx, [rsp+138h+var_C8]; this
0x180079562  call    ??0ResultData@@QEAA@AEBU0@@Z; ResultData::ResultData(ResultData const &)
0x180079567  add     rdi, [rsp+138h+var_C0]
0x18007956c  lea     rcx, [rsp+138h+var_C8]; this
0x180079571  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x180079576  add     rbx, 78h ; 'x'
0x18007957a  jmp     short loc_180079555
0x18007957c  mov     rdx, rdi
0x18007957f  lea     rcx, [rsp+138h+var_108]
0x180079584  call    ??$make_unique_cotaskmem@$$BY0A@UProvDataResult@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvDataResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvDataResult [0]>(unsigned __int64)
0x180079589  nop
0x18007958a  mov     r8, rdi
0x18007958d  shl     r8, 5; Size
0x180079591  xor     edx, edx; Val
0x180079593  mov     rcx, [rsp+138h+var_108]; void *
0x180079598  call    memset_0
0x18007959d  mov     r9, [rsp+138h+var_F0]
0x1800795a2  mov     rbx, r9
0x1800795a5  mov     r10, [rsp+138h+var_E8]
0x1800795aa  mov     r13, r10
0x1800795ad  cmp     rbx, r13
0x1800795b0  jz      loc_180079798
0x1800795b6  mov     rax, [rbx]
0x1800795b9  mov     rax, [rax]
0x1800795bc  mov     [rsp+138h+var_F8], rax
0x1800795c1  cmp     byte ptr [rax+19h], 0
0x1800795c5  jnz     loc_18007978F
0x1800795cb  mov     ecx, [rax+1Ch]
0x1800795ce  mov     [rsp+138h+string], 0
0x1800795d7  lea     rdx, off_1800CD640; "Provisioning"
0x1800795de  lea     rax, _tls_used
0x1800795e5  cmp     rdx, rax
0x1800795e8  jz      loc_1800798D7
0x1800795ee  cmp     ecx, [rdx+8]
0x1800795f1  jnz     loc_180079786
0x1800795f7  mov     rsi, r12
0x1800795fa  shl     rsi, 5
0x1800795fe  add     rsi, [rsp+138h+var_108]
0x180079603  mov     rax, [rdx]
0x180079606  mov     [rsp+138h+var_110], rax
0x18007960b  lea     rdx, [rsp+138h+var_110]
0x180079610  lea     rcx, [rsp+138h+string]
0x180079615  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007961a  mov     rcx, [rsp+138h]; this
0x180079622  test    eax, eax
0x180079624  js      loc_18007985C
0x18007962a  mov     rdx, rsi; newString
0x18007962d  mov     rcx, [rsp+138h+string]; string
0x180079632  call    cs:__imp_WindowsDuplicateString
0x180079638  mov     rcx, [rsp+138h]; this
0x180079640  test    eax, eax
0x180079642  js      loc_180079870
0x180079648  mov     [rsp+138h+var_118], 0; int
0x180079651  lea     rax, [rbx+10h]
0x180079655  cmp     qword ptr [rbx+28h], 7
0x18007965a  jbe     short loc_18007965F
0x18007965c  mov     rax, [rax]
0x18007965f  mov     [rsp+138h+var_110], rax
0x180079664  lea     rdx, [rsp+138h+var_110]
0x180079669  lea     rcx, [rsp+138h+var_118]
0x18007966e  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180079673  mov     rcx, [rsp+138h]; this
0x18007967b  test    eax, eax
0x18007967d  js      loc_180079885
0x180079683  lea     rdx, [rsi+8]; newString
0x180079687  mov     rcx, [rsp+138h+var_118]; string
0x18007968c  call    cs:__imp_WindowsDuplicateString
0x180079692  mov     rcx, [rsp+138h]; this
0x18007969a  xor     r8d, r8d
0x18007969d  test    eax, eax
0x18007969f  js      loc_180079899
0x1800796a5  mov     edx, r8d
0x1800796a8  mov     ecx, [rbx+60h]
0x1800796ab  sub     ecx, 1
0x1800796ae  jz      short loc_1800796C6
0x1800796b0  sub     ecx, 1
0x1800796b3  jz      short loc_1800796BF
0x1800796b5  cmp     ecx, 1
0x1800796b8  jnz     short loc_1800796CB
0x1800796ba  lea     edx, [rcx+2]
0x1800796bd  jmp     short loc_1800796CB
0x1800796bf  mov     edx, 2
0x1800796c4  jmp     short loc_1800796CB
0x1800796c6  mov     edx, 1
0x1800796cb  mov     [rsi+10h], edx
0x1800796ce  mov     eax, [rbx+54h]
0x1800796d1  mov     [rsi+14h], eax
0x1800796d4  mov     [rsi+18h], r8
0x1800796d8  cmp     [rbx+70h], r8
0x1800796dc  jz      short loc_180079746
0x1800796de  mov     [rsp+138h+var_110], r8
0x1800796e3  mov     rax, [rbx+68h]
0x1800796e7  mov     rcx, [rax]
0x1800796ea  add     rcx, 20h ; ' '
0x1800796ee  cmp     qword ptr [rcx+18h], 7
0x1800796f3  jbe     short loc_1800796F8
0x1800796f5  mov     rcx, [rcx]
0x1800796f8  mov     [rsp+138h+var_D8], rcx
0x1800796fd  lea     rdx, [rsp+138h+var_D8]
0x180079702  lea     rcx, [rsp+138h+var_110]
0x180079707  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007970c  mov     rcx, [rsp+138h]; this
0x180079714  test    eax, eax
0x180079716  js      loc_1800798AE
0x18007971c  lea     rdx, [rsi+18h]; newString
0x180079720  mov     rcx, [rsp+138h+var_110]; string
0x180079725  call    cs:__imp_WindowsDuplicateString
0x18007972b  mov     rcx, [rsp+138h]; this
0x180079733  test    eax, eax
0x180079735  js      loc_1800798C2
0x18007973b  mov     rcx, [rsp+138h+var_110]; string
0x180079740  call    cs:__imp_WindowsDeleteString
0x180079746  inc     r12
0x180079749  mov     rcx, [rsp+138h+var_118]; string
0x18007974e  call    cs:__imp_WindowsDeleteString
0x180079754  mov     [rsp+138h+var_118], 0
0x18007975d  mov     rcx, [rsp+138h+string]; string
0x180079762  call    cs:__imp_WindowsDeleteString
0x180079768  lea     rcx, [rsp+138h+var_F8]
0x18007976d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>::operator++(void)
0x180079772  mov     r10, [rsp+138h+var_E8]
0x180079777  mov     r9, [rsp+138h+var_F0]
0x18007977c  mov     rax, [rsp+138h+var_F8]
0x180079781  jmp     loc_1800795C1
0x180079786  add     rdx, 10h
0x18007978a  jmp     loc_1800795E5
0x18007978f  add     rbx, 78h ; 'x'
0x180079793  jmp     loc_1800795AD
0x180079798  mov     dword ptr [rsp+138h+var_118], 0; int
0x1800797a0  lea     rdx, [rsp+138h+var_118]; unsigned int *
0x1800797a5  mov     rcx, rdi; unsigned __int64
0x1800797a8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800797ad  mov     rcx, [rsp+138h]; this
0x1800797b5  test    eax, eax
0x1800797b7  js      loc_1800798FE
0x1800797bd  mov     rax, [rsp+138h+var_108]
0x1800797c2  mov     [r15], rax
0x1800797c5  mov     eax, dword ptr [rsp+138h+var_118]
0x1800797c9  mov     [r14], eax
0x1800797cc  mov     [rsp+138h+var_108], 0
0x1800797d5  test    r9, r9
0x1800797d8  jz      short loc_18007980E
0x1800797da  mov     rdx, r10
0x1800797dd  mov     rcx, r9; this
0x1800797e0  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x1800797e5  mov     rcx, [rsp+138h+var_F0]
0x1800797ea  mov     rax, [rsp+138h+var_E0]
0x1800797ef  sub     rax, rcx
0x1800797f2  sar     rax, 3
0x1800797f6  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x180079800  imul    rax, rdx
0x180079804  imul    rdx, rax, 78h ; 'x'
0x180079808  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007980d  nop
0x18007980e  xor     eax, eax
0x180079810  jmp     short loc_180079816
0x180079812  mov     eax, dword ptr [rsp+138h+var_118]
0x180079816  mov     rcx, [rsp+138h+var_48]
0x18007981e  xor     rcx, rsp; StackCookie
0x180079821  call    __security_check_cookie
0x180079826  add     rsp, 100h
0x18007982d  pop     r15
0x18007982f  pop     r14
0x180079831  pop     r13
0x180079833  pop     r12
0x180079835  pop     rdi
0x180079836  pop     rsi
0x180079837  pop     rbx
0x180079838  retn
0x180079839  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079840  mov     edx, 0E4h; void *
0x180079845  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007984a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079851  mov     edx, 0E5h; void *
0x180079856  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007985c  mov     r9d, eax; char *
0x18007985f  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079866  mov     edx, 0FEh; void *
0x18007986b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079870  mov     r9d, eax; char *
0x180079873  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007987a  mov     edx, 0FFh; void *
0x18007987f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079885  mov     r9d, eax; char *
0x180079888  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007988f  mov     edx, 103h; void *
0x180079894  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079899  mov     r9d, eax; char *
0x18007989c  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800798a3  mov     edx, 104h; void *
0x1800798a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800798ae  mov     r9d, eax; char *
0x1800798b1  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800798b8  mov     edx, 11Fh; void *
0x1800798bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800798c2  mov     r9d, eax; char *
0x1800798c5  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800798cc  mov     edx, 120h; void *
0x1800798d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800798d7  mov     ecx, 80070490h
0x1800798dc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800798e1  mov     r9d, eax; char *
0x1800798e4  mov     rcx, [rsp+138h]; this
0x1800798ec  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\categoryi"...
0x1800798f3  mov     edx, 69h ; 'i'; void *
0x1800798f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800798fe  mov     r9d, eax; char *
0x180079901  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079908  mov     edx, 128h; void *
0x18007990d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
