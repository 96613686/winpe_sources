# wil::cloud_store::call_load<Windows::Data::PlaceholderTileCollectionLocal>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180054fe4`
- end: `0x18005539e`
- name: `??$call_load@UPlaceholderTileCollectionLocal@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UPlaceholderTileCollectionLocal@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `954`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180054ed8`

## callees

- `0x180011188`
- `0x18001dac0`
- `0x180054fe4`
- `0x1800553a4`
- `0x180056798`
- `0x1800574a8`
- `0x1800579bc`
- `0x180147be8`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800552e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800552f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005530e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055324`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055337`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005534a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005535d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055370`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800552e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800552f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005530e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055324`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055337`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005534a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005535d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800550b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005511f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800551ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800550b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005511f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180055179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800551ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::PlaceholderTileCollectionLocal>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v9; // rax
  const WCHAR *v10; // rsi
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  const WCHAR *v16; // rsi
  unsigned __int64 v17; // rbx
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  const WCHAR *v21; // rsi
  unsigned __int64 v22; // rbx
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  int v26; // ebx
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  __int64 *v30; // rax
  __int64 v31; // r8
  int v32; // eax
  wil::details::in1diag3 *v33; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 *v38; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER v39; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v40; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER v41; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING v42; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v43; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v44; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v47[3]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v48; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v38 = *(__int64 **)wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v37 = *v38;
  v9 = wil::cloud_store::widen_string(v47, a5);
  v10 = (const WCHAR *)v9;
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v10 = *(const WCHAR **)v9;
  string = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
LABEL_43:
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  v14 = v13 - 1;
  if ( (unsigned int)v12 < v13 )
    v14 = v12;
  v15 = WindowsCreateStringReference(v10, v14, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    RaiseException(v15, 1u, 0, 0);
LABEL_45:
    RaiseException(v20, 1u, 0, 0);
    goto LABEL_46;
  }
  wil::cloud_store::convert_cloud_store_load_options(a4);
  v16 = (const WCHAR *)(a3 + 8);
  if ( (unsigned __int64)a3[11] > 7 )
    v16 = *(const WCHAR **)v16;
  v44 = 0;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0xFFFFFFFF )
    goto LABEL_42;
  v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v17);
  v19 = v18 - 1;
  if ( (unsigned int)v17 < v18 )
    v19 = v17;
  v20 = WindowsCreateStringReference(v16, v19, &v43, &v44);
  if ( v20 < 0 )
    goto LABEL_45;
  v21 = (const WCHAR *)(a3 + 4);
  if ( (unsigned __int64)a3[7] > 7 )
    v21 = *(const WCHAR **)v21;
  v42 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( v22 > 0xFFFFFFFF )
    goto LABEL_41;
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v22);
  v24 = v23 - 1;
  if ( (unsigned int)v22 < v23 )
    v24 = v22;
  v25 = WindowsCreateStringReference(v21, v24, &v41, &v42);
  if ( v25 < 0 )
  {
LABEL_46:
    RaiseException(v25, 1u, 0, 0);
LABEL_47:
    RaiseException(v29, 1u, 0, 0);
    goto LABEL_48;
  }
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v40 = 0;
  do
    ++v11;
  while ( *((_WORD *)a3 + v11) );
  if ( v11 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_41:
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_42:
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_43;
  }
  v26 = (int)v42;
  v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v28 = v27 - 1;
  if ( (unsigned int)v11 < v27 )
    v28 = v11;
  v29 = WindowsCreateStringReference((PCWSTR)a3, v28, &v39, &v40);
  if ( v29 < 0 )
    goto LABEL_47;
  v30 = *(__int64 **)(a1 + 24);
  if ( v30 )
    v31 = *v30;
  else
    v31 = 0;
  v35 = v26;
  v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, HSTRING))(v37 + 72))(
          v38,
          *(unsigned int *)(a1 + 16),
          v31,
          v40);
  v33 = retaddr;
  if ( v32 < 0 )
LABEL_48:
    wil::details::in1diag3::Throw_Hr(
      v33,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v32,
      v35);
  v40 = 0;
  v42 = 0;
  v44 = 0;
  string = 0;
  if ( v48 > 7 )
    std::_Deallocate<16>(v47[0], 2 * v48 + 2);
  wil::cloud_store::unmarshal<Windows::Data::PlaceholderTileCollectionLocal>(a2, 0, a4);
  return a2;
}

```

## disassembly

```asm
0x180054fe4  push    rbp
0x180054fe6  push    rbx
0x180054fe7  push    rsi
0x180054fe8  push    rdi
0x180054fe9  push    r12
0x180054feb  push    r13
0x180054fed  push    r14
0x180054fef  push    r15
0x180054ff1  lea     rbp, [rsp-38h]
0x180054ff6  sub     rsp, 138h
0x180054ffd  mov     rax, cs:__security_cookie
0x180055004  xor     rax, rsp
0x180055007  mov     [rbp+70h+var_50], rax
0x18005500b  mov     r12d, r9d
0x18005500e  mov     [rsp+170h+var_114], r9d
0x180055013  mov     r14, r8
0x180055016  mov     r15, rdx
0x180055019  mov     r13, rcx
0x18005501c  mov     [rsp+170h+var_110], rdx
0x180055021  mov     rbx, [rbp+70h+arg_20]
0x180055028  xor     edi, edi
0x18005502a  mov     [rsp+170h+var_120], rdi
0x18005502f  mov     rcx, [rcx]
0x180055032  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x180055037  mov     rax, [rax]
0x18005503a  mov     [rsp+170h+var_F8], rax
0x18005503f  mov     rax, [rax]
0x180055042  mov     [rsp+170h+var_110], rax
0x180055047  mov     rcx, [rsp+170h+var_120]
0x18005504c  mov     [rsp+170h+var_120], rdi
0x180055051  test    rcx, rcx
0x180055054  jnz     loc_18005538C
0x18005505a  mov     rdx, rbx
0x18005505d  lea     rcx, [rbp+70h+var_70]
0x180055061  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180055066  mov     rsi, rax
0x180055069  cmp     qword ptr [rax+18h], 7
0x18005506e  jbe     short loc_180055073
0x180055070  mov     rsi, [rax]
0x180055073  mov     [rbp+70h+string], rdi
0x180055077  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005507b  mov     rbx, rdi
0x18005507e  xor     eax, eax
0x180055080  inc     rbx
0x180055083  cmp     [rsi+rbx*2], ax
0x180055087  jnz     short loc_180055080
0x180055089  mov     eax, 0FFFFFFFFh
0x18005508e  cmp     rbx, rax
0x180055091  ja      loc_180055315
0x180055097  mov     ecx, ebx; unsigned int
0x180055099  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005509e  lea     edx, [rax-1]
0x1800550a1  cmp     ebx, eax
0x1800550a3  cmovb   edx, ebx; length
0x1800550a6  lea     r9, [rbp+70h+string]; string
0x1800550aa  lea     r8, [rbp+70h+hstringHeader]; hstringHeader
0x1800550ae  mov     rcx, rsi; sourceString
0x1800550b1  call    cs:__imp_WindowsCreateStringReference
0x1800550b7  test    eax, eax
0x1800550b9  js      loc_18005532B
0x1800550bf  mov     rax, [rbp+70h+string]
0x1800550c3  mov     [rsp+170h+var_100], rax
0x1800550c8  mov     ecx, r12d
0x1800550cb  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x1800550d0  mov     [rsp+170h+var_118], eax
0x1800550d4  lea     rsi, [r14+40h]
0x1800550d8  cmp     qword ptr [rsi+18h], 7
0x1800550dd  ja      loc_1800552A0
0x1800550e3  xor     r12d, r12d
0x1800550e6  mov     [rbp+70h+var_98], r12
0x1800550ea  mov     rbx, rdi
0x1800550ed  inc     rbx
0x1800550f0  cmp     [rsi+rbx*2], r12w
0x1800550f5  jnz     short loc_1800550ED
0x1800550f7  mov     eax, 0FFFFFFFFh
0x1800550fc  cmp     rbx, rax
0x1800550ff  ja      loc_1800552FF
0x180055105  mov     ecx, ebx; unsigned int
0x180055107  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18005510c  lea     edx, [rax-1]
0x18005510f  cmp     ebx, eax
0x180055111  cmovb   edx, ebx; length
0x180055114  lea     r9, [rbp+70h+var_98]; string
0x180055118  lea     r8, [rbp+70h+var_B0]; hstringHeader
0x18005511c  mov     rcx, rsi; sourceString
0x18005511f  call    cs:__imp_WindowsCreateStringReference
0x180055125  test    eax, eax
0x180055127  js      loc_18005533E
0x18005512d  lea     rsi, [r14+20h]
0x180055131  cmp     qword ptr [rsi+18h], 7
0x180055136  ja      loc_1800552A8
0x18005513c  mov     [rbp+70h+var_B8], r12
0x180055140  mov     rbx, rdi
0x180055143  inc     rbx
0x180055146  cmp     [rsi+rbx*2], r12w
0x18005514b  jnz     short loc_180055143
0x18005514d  mov     eax, 0FFFFFFFFh
0x180055152  cmp     rbx, rax
0x180055155  ja      loc_1800552E9
0x18005515b  mov     r12, [rbp+70h+var_98]
0x18005515f  mov     ecx, ebx; unsigned int
0x180055161  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055166  lea     edx, [rax-1]
0x180055169  cmp     ebx, eax
0x18005516b  cmovb   edx, ebx; length
0x18005516e  lea     r9, [rbp+70h+var_B8]; string
0x180055172  lea     r8, [rbp+70h+var_D0]; hstringHeader
0x180055176  mov     rcx, rsi; sourceString
0x180055179  call    cs:__imp_WindowsCreateStringReference
0x18005517f  xor     esi, esi
0x180055181  test    eax, eax
0x180055183  js      loc_180055351
0x180055189  cmp     qword ptr [r14+18h], 7
0x18005518e  ja      loc_1800552B0
0x180055194  mov     [rbp+70h+var_D8], rsi
0x180055198  inc     rdi
0x18005519b  cmp     [r14+rdi*2], si
0x1800551a0  jnz     short loc_180055198
0x1800551a2  mov     eax, 0FFFFFFFFh
0x1800551a7  cmp     rdi, rax
0x1800551aa  ja      loc_1800552D3
0x1800551b0  mov     rbx, [rbp+70h+var_B8]
0x1800551b4  mov     ecx, edi; unsigned int
0x1800551b6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800551bb  lea     edx, [rax-1]
0x1800551be  cmp     edi, eax
0x1800551c0  cmovb   edx, edi; length
0x1800551c3  lea     r9, [rbp+70h+var_D8]; string
0x1800551c7  lea     r8, [rbp+70h+var_F0]; hstringHeader
0x1800551cb  mov     rcx, r14; sourceString
0x1800551ce  call    cs:__imp_WindowsCreateStringReference
0x1800551d4  test    eax, eax
0x1800551d6  js      loc_180055364
0x1800551dc  mov     rax, [r13+18h]
0x1800551e0  test    rax, rax
0x1800551e3  jz      loc_1800552B8
0x1800551e9  mov     r8, [rax]
0x1800551ec  lea     rax, [rsp+170h+var_120]
0x1800551f1  mov     [rsp+170h+var_130], rax
0x1800551f6  mov     rax, [rsp+170h+var_100]
0x1800551fb  mov     [rsp+170h+var_138], rax
0x180055200  mov     eax, [rsp+170h+var_118]
0x180055204  mov     [rsp+170h+var_140], eax
0x180055208  mov     [rsp+170h+var_148], r12
0x18005520d  mov     [rsp+170h+var_150], rbx
0x180055212  mov     r9, [rbp+70h+var_D8]
0x180055216  mov     edx, [r13+10h]
0x18005521a  mov     rcx, [rsp+170h+var_F8]
0x18005521f  mov     rax, [rsp+170h+var_110]
0x180055224  mov     rax, [rax+48h]
0x180055228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005522d  mov     rcx, [rbp+78h]
0x180055231  test    eax, eax
0x180055233  js      loc_180055377
0x180055239  mov     [rbp+70h+var_D8], rsi
0x18005523d  mov     [rbp+70h+var_B8], rsi
0x180055241  mov     [rbp+70h+var_98], rsi
0x180055245  mov     [rbp+70h+string], rsi
0x180055249  mov     rdx, [rbp+70h+var_58]
0x18005524d  cmp     rdx, 7
0x180055251  ja      short loc_1800552C0
0x180055253  mov     r8d, [rsp+170h+var_114]
0x180055258  mov     rdx, [rsp+170h+var_120]
0x18005525d  mov     rcx, r15
0x180055260  call    ??$unmarshal@UPlaceholderTileCollectionLocal@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@UPlaceholderTileCollectionLocal@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::PlaceholderTileCollectionLocal>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x180055265  nop
0x180055266  mov     rcx, [rsp+170h+var_120]
0x18005526b  test    rcx, rcx
0x18005526e  jz      short loc_18005527D
0x180055270  mov     rdx, [rcx]
0x180055273  mov     rax, [rdx+10h]
0x180055277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005527c  nop
0x18005527d  mov     rax, r15
0x180055280  mov     rcx, [rbp+70h+var_50]
0x180055284  xor     rcx, rsp; StackCookie
0x180055287  call    __security_check_cookie
0x18005528c  add     rsp, 138h
0x180055293  pop     r15
0x180055295  pop     r14
0x180055297  pop     r13
0x180055299  pop     r12
0x18005529b  pop     rdi
0x18005529c  pop     rsi
0x18005529d  pop     rbx
0x18005529e  pop     rbp
0x18005529f  retn
0x1800552a0  mov     rsi, [rsi]
0x1800552a3  jmp     loc_1800550E3
0x1800552a8  mov     rsi, [rsi]
0x1800552ab  jmp     loc_18005513C
0x1800552b0  mov     r14, [r14]
0x1800552b3  jmp     loc_180055194
0x1800552b8  mov     r8, rsi
0x1800552bb  jmp     loc_1800551EC
0x1800552c0  lea     rdx, ds:2[rdx*2]
0x1800552c8  mov     rcx, [rbp+70h+var_70]
0x1800552cc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800552d1  jmp     short loc_180055253
0x1800552d3  xor     r9d, r9d; lpArguments
0x1800552d6  xor     r8d, r8d; nNumberOfArguments
0x1800552d9  lea     edx, [r9+1]; dwExceptionFlags
0x1800552dd  mov     ecx, 80070216h; dwExceptionCode
0x1800552e2  call    cs:__imp_RaiseException
0x1800552e8  nop
0x1800552e9  xor     r9d, r9d; lpArguments
0x1800552ec  xor     r8d, r8d; nNumberOfArguments
0x1800552ef  lea     edx, [r9+1]; dwExceptionFlags
0x1800552f3  mov     ecx, 80070216h; dwExceptionCode
0x1800552f8  call    cs:__imp_RaiseException
0x1800552fe  nop
0x1800552ff  xor     r9d, r9d; lpArguments
0x180055302  xor     r8d, r8d; nNumberOfArguments
0x180055305  lea     edx, [r9+1]; dwExceptionFlags
0x180055309  mov     ecx, 80070216h; dwExceptionCode
0x18005530e  call    cs:__imp_RaiseException
0x180055314  nop
0x180055315  xor     r9d, r9d; lpArguments
0x180055318  xor     r8d, r8d; nNumberOfArguments
0x18005531b  lea     edx, [r9+1]; dwExceptionFlags
0x18005531f  mov     ecx, 80070216h; dwExceptionCode
0x180055324  call    cs:__imp_RaiseException
0x18005532a  int     3; Trap to Debugger
0x18005532b  xor     r9d, r9d; lpArguments
0x18005532e  xor     r8d, r8d; nNumberOfArguments
0x180055331  lea     edx, [r9+1]; dwExceptionFlags
0x180055335  mov     ecx, eax; dwExceptionCode
0x180055337  call    cs:__imp_RaiseException
0x18005533d  nop
0x18005533e  xor     r9d, r9d; lpArguments
0x180055341  xor     r8d, r8d; nNumberOfArguments
0x180055344  lea     edx, [r9+1]; dwExceptionFlags
0x180055348  mov     ecx, eax; dwExceptionCode
0x18005534a  call    cs:__imp_RaiseException
0x180055350  nop
0x180055351  xor     r9d, r9d; lpArguments
0x180055354  xor     r8d, r8d; nNumberOfArguments
0x180055357  lea     edx, [r9+1]; dwExceptionFlags
0x18005535b  mov     ecx, eax; dwExceptionCode
0x18005535d  call    cs:__imp_RaiseException
0x180055363  nop
0x180055364  xor     r9d, r9d; lpArguments
0x180055367  xor     r8d, r8d; nNumberOfArguments
0x18005536a  lea     edx, [r9+1]; dwExceptionFlags
0x18005536e  mov     ecx, eax; dwExceptionCode
0x180055370  call    cs:__imp_RaiseException
0x180055376  nop
0x180055377  mov     r9d, eax; char *
0x18005537a  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180055381  mov     edx, 588h; void *
0x180055386  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005538c  mov     rax, [rcx]
0x18005538f  mov     rax, [rax+10h]
0x180055393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055398  jmp     loc_18005505A
```
