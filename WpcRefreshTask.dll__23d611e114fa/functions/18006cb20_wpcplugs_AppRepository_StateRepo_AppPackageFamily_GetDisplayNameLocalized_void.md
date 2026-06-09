# wpcplugs::AppRepository::StateRepo::AppPackageFamily::GetDisplayNameLocalized(void)

- ea: `0x18006cb20`
- end: `0x18006ce9c`
- name: `?GetDisplayNameLocalized@AppPackageFamily@StateRepo@AppRepository@wpcplugs@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `892`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x180008d50`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x180048f8c`
- `0x18004a230`
- `0x18006a6b0`
- `0x18006cb20`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cb78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cb78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cc28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cdb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cbfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cc28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cda4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cdb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cc57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cd29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cc57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cc87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cd29`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cbb2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cbb2`
- `MrmCoreR!ResourceManagerQueueSetGlobalFlags` at `0x18006cb57`
- `MrmCoreR!ResourceManagerQueueSetGlobalFlags` at `0x18006cb57`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18006ccab`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18006cd4d`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18006ccab`
- `MrmCoreR!ResourceManagerQueueGetString` at `0x18006cd4d`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18006cc3f`
- `Bcp47Langs!GetUserLanguagesForUser` at `0x18006cc3f`

## string_xrefs

- `0x18006ce19`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ce2e`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ce4b`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ce60`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ce75`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ce8a`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
unsigned __int64 __fastcall wpcplugs::AppRepository::StateRepo::AppPackageFamily::GetDisplayNameLocalized(
        __int64 a1,
        unsigned __int64 a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  int UserLanguagesForUser; // eax
  PCWSTR StringRawBuffer; // r14
  __int64 v15; // rdi
  __int64 v16; // rbx
  PCWSTR v17; // rax
  int v18; // eax
  char *v19; // rdi
  unsigned __int64 v20; // rcx
  size_t v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rdi
  PCWSTR v24; // rax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v31; // [rsp+20h] [rbp-49h]
  HSTRING v32; // [rsp+30h] [rbp-39h] BYREF
  __int64 v33; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v34; // [rsp+40h] [rbp-29h] BYREF
  __int64 v35; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-19h]
  __int64 v37; // [rsp+58h] [rbp-11h] BYREF
  void *v38; // [rsp+60h] [rbp-9h]
  __int64 v39; // [rsp+68h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v36 = a2;
  ResourceManagerQueueSetGlobalFlags(1);
  v33 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.MrtPackage", 0x2Bu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_27:
    wil::details::in1diag3::Throw_Hr(
      v8,
      (void *)0x23A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v31);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_ede4711a_0c90_4d5b_acf3_58af696d9425, &v33);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_27;
  v35 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 80LL))(v33, *(_QWORD *)(a1 + 8), &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v9,
      v31);
  v34 = 0;
  v10 = v35;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 80LL);
  WindowsDeleteString(0);
  v34 = 0;
  v12 = v11(v10, &v34);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x240,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v12,
      v31);
  WindowsDeleteString(0);
  v32 = 0;
  UserLanguagesForUser = GetUserLanguagesForUser(a1 + 16, 59, &v32);
  if ( UserLanguagesForUser < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x243,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)UserLanguagesForUser,
      v31);
  StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
  std::vector<unsigned short>::vector<unsigned short>(&v37, 512);
  v36 = 0;
  v15 = v37;
  v16 = (v39 - v37) >> 1;
  v17 = WindowsGetStringRawBuffer(v32, 0);
  v18 = ResourceManagerQueueGetString(StringRawBuffer, L"Language", v17, v15);
  if ( v18 == -2147024774 )
  {
    v19 = (char *)v38;
    v20 = ((__int64)v38 - v37) >> 1;
    if ( v36 >= v20 )
    {
      if ( v36 <= v20 )
        goto LABEL_14;
      if ( v36 > (v39 - v37) >> 1 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v37, v36);
        v19 = (char *)v38;
        goto LABEL_14;
      }
      v21 = 2 * (v36 - v20);
      memset_0(v38, 0, v21);
      v19 += v21;
    }
    else
    {
      v19 = (char *)(v37 + 2 * v36);
    }
    v38 = v19;
LABEL_14:
    v22 = v37;
    v23 = (__int64)&v19[-v37] >> 1;
    v24 = WindowsGetStringRawBuffer(v32, 0);
    v25 = ResourceManagerQueueGetString(StringRawBuffer, L"Language", v24, v22);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v25,
        v23);
    goto LABEL_17;
  }
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25D,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v18,
      v16);
LABEL_17:
  v26 = v37;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  v27 = -1;
  do
    ++v27;
  while ( *(_WORD *)(v26 + 2 * v27) );
  std::wstring::_Construct<1,unsigned short const *>(a2, v26, v27);
  std::vector<unsigned short>::~vector<unsigned short>(&v37);
  WindowsDeleteString(v32);
  v32 = 0;
  WindowsDeleteString(v34);
  v34 = 0;
  v28 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return a2;
}

```

## disassembly

```asm
0x18006cb20  mov     [rsp-8+arg_10], rbx
0x18006cb25  push    rbp
0x18006cb26  push    rsi
0x18006cb27  push    rdi
0x18006cb28  push    r14
0x18006cb2a  push    r15
0x18006cb2c  lea     rbp, [rsp-37h]
0x18006cb31  sub     rsp, 0A0h
0x18006cb38  mov     rax, cs:__security_cookie
0x18006cb3f  xor     rax, rsp
0x18006cb42  mov     [rbp+57h+var_28], rax
0x18006cb46  mov     rsi, rdx
0x18006cb49  mov     r14, rcx
0x18006cb4c  mov     [rbp+57h+var_70], rdx
0x18006cb50  xor     r15d, r15d
0x18006cb53  lea     ecx, [r15+1]
0x18006cb57  call    cs:__imp_ResourceManagerQueueSetGlobalFlags
0x18006cb5d  mov     [rbp+57h+var_88], r15
0x18006cb61  mov     [rbp+57h+string], r15
0x18006cb65  lea     r9, [rbp+57h+string]; string
0x18006cb69  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006cb6d  lea     edx, [r15+2Bh]; length
0x18006cb71  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtPackage@@3QBGB; "Windows.Internal.StateRepository.MrtPac"...
0x18006cb78  call    cs:__imp_WindowsCreateStringReference
0x18006cb7e  test    eax, eax
0x18006cb80  js      loc_18006CE40
0x18006cb86  mov     rbx, [rbp+57h+string]
0x18006cb8a  mov     rcx, [rbp+57h+var_88]
0x18006cb8e  test    rcx, rcx
0x18006cb91  jz      short loc_18006CBA4
0x18006cb93  mov     [rbp+57h+var_88], r15
0x18006cb97  mov     rax, [rcx]
0x18006cb9a  mov     rax, [rax+10h]
0x18006cb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cba3  nop
0x18006cba4  lea     r8, [rbp+57h+var_88]
0x18006cba8  lea     rdx, _GUID_ede4711a_0c90_4d5b_acf3_58af696d9425
0x18006cbaf  mov     rcx, rbx
0x18006cbb2  call    cs:__imp_RoGetActivationFactory
0x18006cbb8  mov     rcx, [rbp+5Fh]
0x18006cbbc  test    eax, eax
0x18006cbbe  js      loc_18006CE48
0x18006cbc4  mov     [rbp+57h+var_78], r15
0x18006cbc8  mov     rcx, [rbp+57h+var_88]
0x18006cbcc  mov     rax, [rcx]
0x18006cbcf  lea     r8, [rbp+57h+var_78]
0x18006cbd3  mov     rdx, [r14+8]
0x18006cbd7  mov     rax, [rax+50h]
0x18006cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbe0  mov     rcx, [rbp+5Fh]; this
0x18006cbe4  test    eax, eax
0x18006cbe6  js      loc_18006CE5D
0x18006cbec  mov     [rbp+57h+var_80], r15
0x18006cbf0  mov     rdi, [rbp+57h+var_78]
0x18006cbf4  mov     rax, [rdi]
0x18006cbf7  mov     rbx, [rax+50h]
0x18006cbfb  xor     ecx, ecx; string
0x18006cbfd  call    cs:__imp_WindowsDeleteString
0x18006cc03  mov     [rbp+57h+var_80], r15
0x18006cc07  lea     rdx, [rbp+57h+var_80]
0x18006cc0b  mov     rcx, rdi
0x18006cc0e  mov     rax, rbx
0x18006cc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc16  mov     rcx, [rbp+5Fh]; this
0x18006cc1a  test    eax, eax
0x18006cc1c  js      loc_18006CE72
0x18006cc22  mov     [rbp+57h+var_90], r15
0x18006cc26  xor     ecx, ecx; string
0x18006cc28  call    cs:__imp_WindowsDeleteString
0x18006cc2e  mov     [rbp+57h+var_90], r15
0x18006cc32  mov     edx, 3Bh ; ';'
0x18006cc37  lea     rcx, [r14+10h]
0x18006cc3b  lea     r8, [rbp+57h+var_90]
0x18006cc3f  call    cs:__imp_GetUserLanguagesForUser
0x18006cc45  mov     rcx, [rbp+5Fh]; this
0x18006cc49  test    eax, eax
0x18006cc4b  js      loc_18006CE87
0x18006cc51  xor     edx, edx; length
0x18006cc53  mov     rcx, [rbp+57h+var_80]; string
0x18006cc57  call    cs:__imp_WindowsGetStringRawBuffer
0x18006cc5d  mov     r14, rax
0x18006cc60  mov     edx, 200h
0x18006cc65  lea     rcx, [rbp+57h+var_68]
0x18006cc69  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18006cc6e  nop
0x18006cc6f  mov     [rbp+57h+var_70], r15
0x18006cc73  mov     rdi, [rbp+57h+var_68]
0x18006cc77  mov     rbx, [rbp+57h+var_58]
0x18006cc7b  sub     rbx, rdi
0x18006cc7e  sar     rbx, 1
0x18006cc81  xor     edx, edx; length
0x18006cc83  mov     rcx, [rbp+57h+var_90]; string
0x18006cc87  call    cs:__imp_WindowsGetStringRawBuffer
0x18006cc8d  lea     rcx, [rbp+57h+var_70]
0x18006cc91  mov     [rsp+0C0h+var_98], rcx
0x18006cc96  mov     qword ptr [rsp+0C0h+var_A0], rbx; int
0x18006cc9b  mov     r9, rdi
0x18006cc9e  mov     r8, rax
0x18006cca1  lea     rdx, aLanguage; "Language"
0x18006cca8  mov     rcx, r14
0x18006ccab  call    cs:__imp_ResourceManagerQueueGetString
0x18006ccb1  cmp     eax, 8007007Ah
0x18006ccb6  jnz     loc_18006CD61
0x18006ccbc  mov     rbx, [rbp+57h+var_70]
0x18006ccc0  mov     rdx, [rbp+57h+var_68]
0x18006ccc4  mov     rdi, [rbp+57h+var_60]
0x18006ccc8  mov     rcx, rdi
0x18006cccb  sub     rcx, rdx
0x18006ccce  sar     rcx, 1
0x18006ccd1  cmp     rbx, rcx
0x18006ccd4  jnb     short loc_18006CCDC
0x18006ccd6  lea     rdi, [rdx+rbx*2]
0x18006ccda  jmp     short loc_18006CD15
0x18006ccdc  jbe     short loc_18006CD19
0x18006ccde  mov     rax, [rbp+57h+var_58]
0x18006cce2  sub     rax, rdx
0x18006cce5  sar     rax, 1
0x18006cce8  cmp     rbx, rax
0x18006cceb  jbe     short loc_18006CCFF
0x18006cced  mov     rdx, rbx
0x18006ccf0  lea     rcx, [rbp+57h+var_68]
0x18006ccf4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006ccf9  mov     rdi, [rbp+57h+var_60]
0x18006ccfd  jmp     short loc_18006CD19
0x18006ccff  sub     rbx, rcx
0x18006cd02  add     rbx, rbx
0x18006cd05  mov     r8, rbx; Size
0x18006cd08  xor     edx, edx; Val
0x18006cd0a  mov     rcx, rdi; void *
0x18006cd0d  call    memset_0
0x18006cd12  add     rdi, rbx
0x18006cd15  mov     [rbp+57h+var_60], rdi
0x18006cd19  mov     rbx, [rbp+57h+var_68]
0x18006cd1d  sub     rdi, rbx
0x18006cd20  sar     rdi, 1
0x18006cd23  xor     edx, edx; length
0x18006cd25  mov     rcx, [rbp+57h+var_90]; string
0x18006cd29  call    cs:__imp_WindowsGetStringRawBuffer
0x18006cd2f  lea     rcx, [rbp+57h+var_70]
0x18006cd33  mov     [rsp+0C0h+var_98], rcx
0x18006cd38  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x18006cd3d  mov     r9, rbx
0x18006cd40  mov     r8, rax
0x18006cd43  lea     rdx, aLanguage; "Language"
0x18006cd4a  mov     rcx, r14
0x18006cd4d  call    cs:__imp_ResourceManagerQueueGetString
0x18006cd53  mov     rcx, [rbp+5Fh]; this
0x18006cd57  test    eax, eax
0x18006cd59  js      loc_18006CE2B
0x18006cd5f  jmp     short loc_18006CD6D
0x18006cd61  mov     rcx, [rbp+5Fh]; this
0x18006cd65  test    eax, eax
0x18006cd67  js      loc_18006CE16
0x18006cd6d  mov     rdx, [rbp+57h+var_68]
0x18006cd71  xorps   xmm0, xmm0
0x18006cd74  movups  xmmword ptr [rsi], xmm0
0x18006cd77  mov     [rsi+10h], r15
0x18006cd7b  mov     [rsi+18h], r15
0x18006cd7f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006cd83  inc     r8
0x18006cd86  cmp     [rdx+r8*2], r15w
0x18006cd8b  jnz     short loc_18006CD83
0x18006cd8d  mov     rcx, rsi
0x18006cd90  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006cd95  nop
0x18006cd96  lea     rcx, [rbp+57h+var_68]
0x18006cd9a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18006cd9f  nop
0x18006cda0  mov     rcx, [rbp+57h+var_90]; string
0x18006cda4  call    cs:__imp_WindowsDeleteString
0x18006cdaa  mov     [rbp+57h+var_90], r15
0x18006cdae  mov     rcx, [rbp+57h+var_80]; string
0x18006cdb2  call    cs:__imp_WindowsDeleteString
0x18006cdb8  mov     [rbp+57h+var_80], r15
0x18006cdbc  mov     rcx, [rbp+57h+var_78]
0x18006cdc0  test    rcx, rcx
0x18006cdc3  jz      short loc_18006CDD6
0x18006cdc5  mov     [rbp+57h+var_78], r15
0x18006cdc9  mov     rax, [rcx]
0x18006cdcc  mov     rax, [rax+10h]
0x18006cdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cdd5  nop
0x18006cdd6  mov     rcx, [rbp+57h+var_88]
0x18006cdda  test    rcx, rcx
0x18006cddd  jz      short loc_18006CDF0
0x18006cddf  mov     [rbp+57h+var_88], r15
0x18006cde3  mov     rdx, [rcx]
0x18006cde6  mov     rax, [rdx+10h]
0x18006cdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cdef  nop
0x18006cdf0  mov     rax, rsi
0x18006cdf3  mov     rcx, [rbp+57h+var_28]
0x18006cdf7  xor     rcx, rsp; StackCookie
0x18006cdfa  call    __security_check_cookie
0x18006cdff  mov     rbx, [rsp+0C0h+arg_10]
0x18006ce07  add     rsp, 0A0h
0x18006ce0e  pop     r15
0x18006ce10  pop     r14
0x18006ce12  pop     rdi
0x18006ce13  pop     rsi
0x18006ce14  pop     rbp
0x18006ce15  retn
0x18006ce16  mov     r9d, eax; char *
0x18006ce19  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce20  mov     edx, 25Dh; void *
0x18006ce25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ce2b  mov     r9d, eax; char *
0x18006ce2e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce35  mov     edx, 259h; void *
0x18006ce3a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ce40  mov     ecx, eax; this
0x18006ce42  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006ce47  nop
0x18006ce48  mov     r9d, eax; char *
0x18006ce4b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce52  mov     edx, 23Ah; void *
0x18006ce57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ce5d  mov     r9d, eax; char *
0x18006ce60  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce67  mov     edx, 23Dh; void *
0x18006ce6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ce72  mov     r9d, eax; char *
0x18006ce75  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce7c  mov     edx, 240h; void *
0x18006ce81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ce87  mov     r9d, eax; char *
0x18006ce8a  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ce91  mov     edx, 243h; void *
0x18006ce96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
