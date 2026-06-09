# DataStoreCache::TargetedContentTransformer::AddTileTemplateSettings(DataStoreCache::DataStorePropertyIdentifier const &,DataStoreCache::TargetedContentTransformer::UpdateContext &)

- ea: `0x1801e4738`
- end: `0x1801e4a58`
- name: `?AddTileTemplateSettings@TargetedContentTransformer@DataStoreCache@@CAXAEBUDataStorePropertyIdentifier@2@AEAUUpdateContext@12@@Z`
- size: `800`
- prototype: `void __fastcall(const struct DataStoreCache::DataStorePropertyIdentifier *, struct DataStoreCache::TargetedContentTransformer::UpdateContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1803781ac`

## callees

- `0x1800139dc`
- `0x18001dac0`
- `0x18002dde0`
- `0x18004ffc0`
- `0x1801e4738`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48a2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48ca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e48f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e483f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e483f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e4907`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e4881`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e4881`

## string_xrefs

- `0x1801e481c`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801e4863`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801e49c4`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801e49f9`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801e4788`: `templateType`
- `0x1801e47ed`: `templateType`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall DataStoreCache::TargetedContentTransformer::AddTileTemplateSettings(
        const struct DataStoreCache::DataStorePropertyIdentifier *a1,
        struct DataStoreCache::TargetedContentTransformer::UpdateContext *a2)
{
  UINT32 v4; // esi
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, __int64, char *); // rbx
  char v7; // r14
  char v8; // al
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  const WCHAR *StringRawBuffer; // rbx
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, __int64, char *); // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  char v23; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v24[3]; // [rsp+31h] [rbp-3Fh] BYREF
  UINT32 length; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  length = 0;
  v4 = 0;
  v23 = 0;
  v5 = *((_QWORD *)a2 + 3);
  v6 = *(int (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v5 + 64LL);
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"templateType", 0xDu, 0xCu);
  v7 = 1;
  length = 1;
  if ( v6(v5, v29, &v23) < 0 || (v8 = 1, !v23) )
    v8 = 0;
  if ( v8 )
  {
    v26 = 0;
    v9 = *((_QWORD *)a2 + 3);
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v9 + 48LL);
    v26 = 0;
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"templateType", 0xDu, 0xCu);
    v11 = v10(v9, v29, &v26);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x659,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
    string = 0;
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v14,
        bIgnoreCase);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( CompareStringOrdinal(StringRawBuffer, length, L"priceAndRating", 14, 1) == 2 )
    {
      v4 = 5;
    }
    else if ( CompareStringOrdinal(StringRawBuffer, length, L"rating", 6, 1) == 2 )
    {
      v4 = 1;
    }
    else if ( CompareStringOrdinal(StringRawBuffer, length, L"priceAndDescription", 19, 1) == 2 )
    {
      v4 = 4;
    }
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v26);
  }
  v16 = *((_QWORD *)a2 + 3);
  v17 = *(int (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v16 + 64LL);
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"isAppListEligible", 0x12u, 0x11u);
  length = 2;
  if ( v17(v16, v29, &v23) < 0 || !v23 )
    v7 = 0;
  if ( v7 )
  {
    v26 = 0;
    v18 = *((_QWORD *)a2 + 3);
    v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v18 + 48LL);
    v26 = 0;
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"isAppListEligible", 0x12u, 0x11u);
    v20 = v19(v18, v29, &v26);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x672,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    v24[0] = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v26 + 88LL))(v26, v24);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x675,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
    if ( v24[0] )
      v4 |= 0x10u;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v26);
  }
  if ( v4 )
  {
    length = v4;
    DataStoreCache::PropertyBagLookaside::SetLookasideValueType<unsigned int>(*((_QWORD *)a2 + 2), a1, &length);
  }
}

```

## disassembly

```asm
0x1801e4738  mov     [rsp-38h+arg_10], rbx
0x1801e473d  push    rbp
0x1801e473e  push    rsi
0x1801e473f  push    rdi
0x1801e4740  push    r12
0x1801e4742  push    r13
0x1801e4744  push    r14
0x1801e4746  push    r15
0x1801e4748  mov     rbp, rsp
0x1801e474b  sub     rsp, 70h
0x1801e474f  mov     rax, cs:__security_cookie
0x1801e4756  xor     rax, rsp
0x1801e4759  mov     [rbp+var_8], rax
0x1801e475d  mov     r15, rdx
0x1801e4760  mov     r12, rcx
0x1801e4763  xor     r13d, r13d
0x1801e4766  mov     [rbp+length], r13d
0x1801e476a  mov     esi, r13d
0x1801e476d  mov     [rbp+var_40], r13b
0x1801e4771  mov     rdi, [rdx+18h]
0x1801e4775  mov     rax, [rdi]
0x1801e4778  mov     rbx, [rax+40h]
0x1801e477c  mov     [rbp+var_10], r13
0x1801e4780  lea     r9d, [r13+0Ch]; unsigned int
0x1801e4784  lea     r8d, [r13+0Dh]; unsigned int
0x1801e4788  lea     rdx, aTemplatetype; "templateType"
0x1801e478f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e4793  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e4798  nop
0x1801e4799  lea     r14d, [r13+1]
0x1801e479d  mov     [rbp+length], r14d
0x1801e47a1  lea     r8, [rbp+var_40]
0x1801e47a5  mov     rdx, [rbp+var_10]
0x1801e47a9  mov     rcx, rdi
0x1801e47ac  mov     rax, rbx
0x1801e47af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e47b4  test    eax, eax
0x1801e47b6  js      short loc_1801E47C1
0x1801e47b8  cmp     [rbp+var_40], r13b
0x1801e47bc  mov     al, r14b
0x1801e47bf  jnz     short loc_1801E47C4
0x1801e47c1  mov     al, r13b
0x1801e47c4  test    al, al
0x1801e47c6  jz      loc_1801E491A
0x1801e47cc  mov     [rbp+var_38], r13
0x1801e47d0  mov     rdi, [r15+18h]
0x1801e47d4  mov     rax, [rdi]
0x1801e47d7  mov     rbx, [rax+30h]
0x1801e47db  mov     [rbp+var_38], r13
0x1801e47df  mov     [rbp+var_10], r13
0x1801e47e3  mov     r9d, 0Ch; unsigned int
0x1801e47e9  lea     r8d, [r9+1]; unsigned int
0x1801e47ed  lea     rdx, aTemplatetype; "templateType"
0x1801e47f4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e47f8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e47fd  nop
0x1801e47fe  lea     r8, [rbp+var_38]
0x1801e4802  mov     rdx, [rbp+var_10]
0x1801e4806  mov     rcx, rdi
0x1801e4809  mov     rax, rbx
0x1801e480c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4811  mov     rcx, [rbp+38h]; this
0x1801e4815  test    eax, eax
0x1801e4817  jns     short loc_1801E482E
0x1801e4819  mov     r9d, eax; char *
0x1801e481c  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801e4823  mov     edx, 659h; void *
0x1801e4828  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801e482e  mov     [rbp+string], r13
0x1801e4832  mov     rdi, [rbp+var_38]
0x1801e4836  mov     rax, [rdi]
0x1801e4839  mov     rbx, [rax+40h]
0x1801e483d  xor     ecx, ecx; string
0x1801e483f  call    cs:__imp_WindowsDeleteString
0x1801e4845  mov     [rbp+string], r13
0x1801e4849  lea     rdx, [rbp+string]
0x1801e484d  mov     rcx, rdi
0x1801e4850  mov     rax, rbx
0x1801e4853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e4858  mov     rcx, [rbp+38h]; this
0x1801e485c  test    eax, eax
0x1801e485e  jns     short loc_1801E4875
0x1801e4860  mov     r9d, eax; char *
0x1801e4863  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801e486a  mov     edx, 65Ch; void *
0x1801e486f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801e4875  mov     [rbp+length], r13d
0x1801e4879  lea     rdx, [rbp+length]; length
0x1801e487d  mov     rcx, [rbp+string]; string
0x1801e4881  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e4887  mov     rbx, rax
0x1801e488a  mov     [rsp+70h+bIgnoreCase], r14d; bIgnoreCase
0x1801e488f  mov     r9d, 0Eh; cchCount2
0x1801e4895  lea     r8, aPriceandrating; "priceAndRating"
0x1801e489c  mov     edx, [rbp+length]; cchCount1
0x1801e489f  mov     rcx, rax; lpString1
0x1801e48a2  call    cs:__imp_CompareStringOrdinal
0x1801e48a8  cmp     eax, 2
0x1801e48ab  jnz     short loc_1801E48B2
0x1801e48ad  lea     esi, [rax+3]
0x1801e48b0  jmp     short loc_1801E4903
0x1801e48b2  mov     [rsp+70h+bIgnoreCase], r14d; bIgnoreCase
0x1801e48b7  mov     r9d, 6; cchCount2
0x1801e48bd  lea     r8, aRating; "rating"
0x1801e48c4  mov     edx, [rbp+length]; cchCount1
0x1801e48c7  mov     rcx, rbx; lpString1
0x1801e48ca  call    cs:__imp_CompareStringOrdinal
0x1801e48d0  cmp     eax, 2
0x1801e48d3  jnz     short loc_1801E48DA
0x1801e48d5  mov     esi, r14d
0x1801e48d8  jmp     short loc_1801E4903
0x1801e48da  mov     [rsp+70h+bIgnoreCase], r14d; int
0x1801e48df  mov     r9d, 13h; cchCount2
0x1801e48e5  lea     r8, aPriceanddescri; "priceAndDescription"
0x1801e48ec  mov     edx, [rbp+length]; cchCount1
0x1801e48ef  mov     rcx, rbx; lpString1
0x1801e48f2  call    cs:__imp_CompareStringOrdinal
0x1801e48f8  mov     ecx, 4
0x1801e48fd  cmp     eax, 2
0x1801e4900  cmovz   esi, ecx
0x1801e4903  mov     rcx, [rbp+string]; string
0x1801e4907  call    cs:__imp_WindowsDeleteString
0x1801e490d  mov     [rbp+string], r13
0x1801e4911  lea     rcx, [rbp+var_38]; void *
0x1801e4915  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801e491a  mov     rdi, [r15+18h]
0x1801e491e  mov     rax, [rdi]
0x1801e4921  mov     rbx, [rax+40h]
0x1801e4925  mov     [rbp+var_10], r13
0x1801e4929  mov     r9d, 11h; unsigned int
0x1801e492f  lea     r8d, [r9+1]; unsigned int
0x1801e4933  lea     rdx, aIsapplisteligi; "isAppListEligible"
0x1801e493a  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e493e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e4943  nop
0x1801e4944  mov     [rbp+length], 2
0x1801e494b  lea     r8, [rbp+var_40]
0x1801e494f  mov     rdx, [rbp+var_10]
0x1801e4953  mov     rcx, rdi
0x1801e4956  mov     rax, rbx
0x1801e4959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e495e  test    eax, eax
0x1801e4960  js      short loc_1801E4968
0x1801e4962  cmp     [rbp+var_40], r13b
0x1801e4966  jnz     short loc_1801E496B
0x1801e4968  mov     r14b, r13b
0x1801e496b  test    r14b, r14b
0x1801e496e  jz      loc_1801E4A1D
0x1801e4974  mov     [rbp+var_38], r13
0x1801e4978  mov     rdi, [r15+18h]
0x1801e497c  mov     rax, [rdi]
0x1801e497f  mov     rbx, [rax+30h]
0x1801e4983  mov     [rbp+var_38], r13
0x1801e4987  mov     [rbp+var_10], r13
0x1801e498b  mov     r9d, 11h; unsigned int
0x1801e4991  lea     r8d, [r9+1]; unsigned int
0x1801e4995  lea     rdx, aIsapplisteligi; "isAppListEligible"
0x1801e499c  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1801e49a0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801e49a5  nop
0x1801e49a6  lea     r8, [rbp+var_38]
0x1801e49aa  mov     rdx, [rbp+var_10]
0x1801e49ae  mov     rcx, rdi
0x1801e49b1  mov     rax, rbx
0x1801e49b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e49b9  mov     rcx, [rbp+38h]; this
0x1801e49bd  test    eax, eax
0x1801e49bf  jns     short loc_1801E49D6
0x1801e49c1  mov     r9d, eax; char *
0x1801e49c4  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801e49cb  mov     edx, 672h; void *
0x1801e49d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801e49d6  mov     [rbp+var_3F], r13b
0x1801e49da  mov     rcx, [rbp+var_38]
0x1801e49de  mov     rax, [rcx]
0x1801e49e1  lea     rdx, [rbp+var_3F]
0x1801e49e5  mov     rax, [rax+58h]
0x1801e49e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e49ee  mov     rcx, [rbp+38h]; this
0x1801e49f2  test    eax, eax
0x1801e49f4  jns     short loc_1801E4A0B
0x1801e49f6  mov     r9d, eax; char *
0x1801e49f9  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801e4a00  mov     edx, 675h; void *
0x1801e4a05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801e4a0b  cmp     [rbp+var_3F], r13b
0x1801e4a0f  jz      short loc_1801E4A14
0x1801e4a11  or      esi, 10h
0x1801e4a14  lea     rcx, [rbp+var_38]; void *
0x1801e4a18  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801e4a1d  test    esi, esi
0x1801e4a1f  jz      short loc_1801E4A34
0x1801e4a21  mov     [rbp+length], esi
0x1801e4a24  lea     r8, [rbp+length]
0x1801e4a28  mov     rdx, r12
0x1801e4a2b  mov     rcx, [r15+10h]
0x1801e4a2f  call    ??$SetLookasideValueType@I@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@1@AEBI@Z; DataStoreCache::PropertyBagLookaside::SetLookasideValueType<uint>(DataStoreCache::DataStorePropertyIdentifier const &,uint const &)
0x1801e4a34  mov     rcx, [rbp+var_8]
0x1801e4a38  xor     rcx, rsp; StackCookie
0x1801e4a3b  call    __security_check_cookie
0x1801e4a40  mov     rbx, [rsp+70h+arg_10]
0x1801e4a48  add     rsp, 70h
0x1801e4a4c  pop     r15
0x1801e4a4e  pop     r14
0x1801e4a50  pop     r13
0x1801e4a52  pop     r12
0x1801e4a54  pop     rdi
0x1801e4a55  pop     rsi
0x1801e4a56  pop     rbp
0x1801e4a57  retn
```
