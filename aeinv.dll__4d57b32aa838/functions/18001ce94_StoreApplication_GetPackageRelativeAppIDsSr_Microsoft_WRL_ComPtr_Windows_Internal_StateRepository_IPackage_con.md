# StoreApplication::GetPackageRelativeAppIDsSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x18001ce94`
- end: `0x18001d315`
- name: `?GetPackageRelativeAppIDsSr@StoreApplication@@SAXAEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `1153`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a5f8`

## callees

- `0x18000a39c`
- `0x180018300`
- `0x180018a60`
- `0x180018ff4`
- `0x18001bb44`
- `0x18001ce94`
- `0x18001d31c`
- `0x18001e0d0`
- `0x1800293b0`
- `0x180040500`
- `0x180042280`
- `0x1800518f0`
- `0x180053948`
- `0x180059920`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001d301`
- `KERNEL32!SetLastError` at `0x18001d301`

## string_xrefs

- `0x18001cf4f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001cfa1`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001cfdc`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001d02b`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001d072`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001d0e6`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24 #try_helpers=1
HRESULT __fastcall StoreApplication::GetPackageRelativeAppIDsSr(_QWORD *a1, __int64 a2)
{
  int v4; // r14d
  int StringReference; // eax
  int v6; // edx
  unsigned int v7; // r8d
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  HRESULT result; // eax
  unsigned int i; // edi
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // r8
  PCWSTR v23; // rax
  __int64 v24; // r8
  __int64 v25; // rbx
  _QWORD *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // [rsp+20h] [rbp-138h]
  _QWORD *v30; // [rsp+30h] [rbp-128h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-120h] BYREF
  HSTRING v32; // [rsp+40h] [rbp-118h] BYREF
  __int64 v33; // [rsp+48h] [rbp-110h] BYREF
  HSTRING string; // [rsp+50h] [rbp-108h] BYREF
  _QWORD v35[5]; // [rsp+58h] [rbp-100h] BYREF
  __int128 v36; // [rsp+80h] [rbp-D8h] BYREF
  __int128 v37; // [rsp+90h] [rbp-C8h]
  _OWORD v38[2]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v39[32]; // [rsp+C0h] [rbp-98h] BYREF
  _BYTE v40[32]; // [rsp+E0h] [rbp-78h] BYREF
  _BYTE v41[32]; // [rsp+100h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v35[1] = -2;
  v4 = 0;
  v31 = 0;
  v35[0] = 0;
  *((_QWORD *)&v37 + 1) = 0;
  if ( !g_ApiWindowsCreateStringReference )
  {
    SetLastError(0x32u);
    StringReference = -2147467263;
    goto LABEL_45;
  }
  StringReference = g_ApiWindowsCreateStringReference();
  if ( StringReference < 0 )
  {
LABEL_45:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    JUMPOUT(0x18001D313LL);
  }
  v8 = *((_QWORD *)&v37 + 1);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(v35);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, v35);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x453,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v29);
  v33 = 0;
  v10 = v35[0];
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35[0] + 144LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v33);
  v12 = v11(v10, *a1, &v33);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x456,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v12,
      v29);
  v31 = 0;
  result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 56LL))(v33, &v31);
  if ( result < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)result,
      v29);
  for ( i = 0; i < v31; ++i )
  {
    v30 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v33 + 48LL))(v33, i, &v30);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x45F,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v15,
        v29);
    v32 = 0;
    v16 = *v30;
    v32 = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v16 + 224))(v30, &v32);
    if ( v17 >= 0 )
    {
      string = 0;
      v19 = *v30;
      string = 0;
      result = (*(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v19 + 392))(v30, &string);
      if ( result >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v32, 0);
        v36 = 0;
        v37 = 0;
        v22 = -1;
        do
          ++v22;
        while ( StringRawBuffer[v22] );
        std::wstring::_Construct<1,unsigned short const *>(&v36);
        v23 = WindowsGetStringRawBuffer(string, 0);
        memset(v38, 0, sizeof(v38));
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        std::wstring::_Construct<1,unsigned short const *>(v38);
        v25 = Utility::ToLower((__int64)v41, (__int64 *)v38);
        std::wstring::wstring(v39, &v36);
        std::wstring::wstring(v40, v25);
        std::vector<std::pair<std::wstring,std::wstring>>::push_back(a2, v39);
        std::wstring::~wstring(v40);
        std::wstring::~wstring(v39);
        std::wstring::~wstring(v41);
        std::wstring::~wstring(v38);
        result = std::wstring::~wstring(&v36);
        if ( string )
          result = WindowsDeleteString(string);
        v4 |= 1u;
        if ( v32 )
          result = WindowsDeleteString(v32);
        v26 = v30;
        if ( v30 )
        {
          v30 = 0;
          result = (*(__int64 (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
        }
      }
      else
      {
        if ( result != -2147024809 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x472,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)result,
            v29);
        if ( string )
          result = WindowsDeleteString(string);
        if ( v32 )
          result = WindowsDeleteString(v32);
        v20 = v30;
        if ( v30 )
        {
          v30 = 0;
          result = (*(__int64 (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
        }
      }
    }
    else
    {
      if ( v17 != -2147024809 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x465,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v17,
          v29);
      result = wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v32);
      v18 = v30;
      if ( v30 )
      {
        v30 = 0;
        result = (*(__int64 (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
    }
  }
  v27 = v33;
  if ( v33 )
  {
    v33 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v35[0];
  if ( v35[0] )
  {
    v35[0] = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  return result;
}

```

## disassembly

```asm
0x18001ce94  mov     r11, rsp
0x18001ce97  push    rsi
0x18001ce98  push    rdi
0x18001ce99  push    r12
0x18001ce9b  push    r14
0x18001ce9d  push    r15
0x18001ce9f  sub     rsp, 130h
0x18001cea6  mov     [rsp+158h+var_F8], 0FFFFFFFFFFFFFFFEh
0x18001ceaf  mov     [r11+18h], rbx
0x18001ceb3  mov     rax, cs:__security_cookie
0x18001ceba  xor     rax, rsp
0x18001cebd  mov     [rsp+158h+var_38], rax
0x18001cec5  mov     r15, rdx
0x18001cec8  mov     rsi, rcx
0x18001cecb  xor     r12d, r12d
0x18001cece  mov     r14d, r12d
0x18001ced1  mov     [rsp+158h+var_120], r12d
0x18001ced6  mov     [rsp+158h+var_100], r12
0x18001cedb  mov     [r11-0C0h], r12
0x18001cee2  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x18001cee9  test    rax, rax
0x18001ceec  jz      loc_18001D2FC
0x18001cef2  lea     r9, [r11-0C0h]
0x18001cef9  lea     r8, [r11-0D8h]
0x18001cf00  lea     edx, [r12+2Ch]
0x18001cf05  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18001cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf11  test    eax, eax
0x18001cf13  js      loc_18001D30C
0x18001cf19  mov     rbx, [rsp+158h+var_C0]
0x18001cf21  lea     rcx, [rsp+158h+var_100]
0x18001cf26  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18001cf2b  lea     r8, [rsp+158h+var_100]
0x18001cf30  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18001cf37  mov     rcx, rbx
0x18001cf3a  call    RoGetActivationFactory
0x18001cf3f  nop
0x18001cf40  mov     rcx, [rsp+158h]; this
0x18001cf48  test    eax, eax
0x18001cf4a  jns     short loc_18001CF61
0x18001cf4c  mov     r9d, eax; char *
0x18001cf4f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001cf56  mov     edx, 453h; void *
0x18001cf5b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001cf61  mov     [rsp+158h+var_110], r12
0x18001cf66  mov     rdi, [rsp+158h+var_100]
0x18001cf6b  mov     rax, [rdi]
0x18001cf6e  mov     rbx, [rax+90h]
0x18001cf75  lea     rcx, [rsp+158h+var_110]
0x18001cf7a  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18001cf7f  lea     r8, [rsp+158h+var_110]
0x18001cf84  mov     rdx, [rsi]
0x18001cf87  mov     rcx, rdi
0x18001cf8a  mov     rax, rbx
0x18001cf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf92  mov     rcx, [rsp+158h]; this
0x18001cf9a  test    eax, eax
0x18001cf9c  jns     short loc_18001CFB2
0x18001cf9e  mov     r9d, eax; char *
0x18001cfa1  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001cfa8  mov     edx, 456h; void *
0x18001cfad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001cfb2  mov     [rsp+158h+var_120], r12d
0x18001cfb7  mov     rcx, [rsp+158h+var_110]
0x18001cfbc  mov     rax, [rcx]
0x18001cfbf  lea     rdx, [rsp+158h+var_120]
0x18001cfc4  mov     rax, [rax+38h]
0x18001cfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfcd  mov     rcx, [rsp+158h]; this
0x18001cfd5  test    eax, eax
0x18001cfd7  jns     short loc_18001CFED
0x18001cfd9  mov     r9d, eax; char *
0x18001cfdc  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001cfe3  mov     edx, 459h; void *
0x18001cfe8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001cfed  mov     edi, r12d
0x18001cff0  mov     esi, 80070057h
0x18001cff5  cmp     edi, [rsp+158h+var_120]
0x18001cff9  jnb     loc_18001D298
0x18001cfff  mov     [rsp+158h+var_128], r12
0x18001d004  mov     rcx, [rsp+158h+var_110]
0x18001d009  mov     rax, [rcx]
0x18001d00c  lea     r8, [rsp+158h+var_128]
0x18001d011  mov     edx, edi
0x18001d013  mov     rax, [rax+30h]
0x18001d017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d01c  mov     rcx, [rsp+158h]; this
0x18001d024  test    eax, eax
0x18001d026  jns     short loc_18001D03C
0x18001d028  mov     r9d, eax; char *
0x18001d02b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001d032  mov     edx, 45Fh; void *
0x18001d037  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d03c  mov     [rsp+158h+var_118], r12
0x18001d041  mov     rcx, [rsp+158h+var_128]
0x18001d046  mov     rax, [rcx]
0x18001d049  mov     [rsp+158h+var_118], r12
0x18001d04e  lea     rdx, [rsp+158h+var_118]
0x18001d053  mov     rax, [rax+0E0h]
0x18001d05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d05f  test    eax, eax
0x18001d061  jns     short loc_18001D0B0
0x18001d063  cmp     eax, esi
0x18001d065  jz      short loc_18001D084
0x18001d067  mov     rcx, [rsp+158h]; this
0x18001d06f  mov     r9d, eax; char *
0x18001d072  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001d079  mov     edx, 465h; void *
0x18001d07e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d084  lea     rcx, [rsp+158h+var_118]
0x18001d089  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18001d08e  nop
0x18001d08f  mov     rcx, [rsp+158h+var_128]
0x18001d094  test    rcx, rcx
0x18001d097  jz      short loc_18001D0AB
0x18001d099  mov     [rsp+158h+var_128], r12
0x18001d09e  mov     rax, [rcx]
0x18001d0a1  mov     rax, [rax+10h]
0x18001d0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0aa  nop
0x18001d0ab  jmp     loc_18001D291
0x18001d0b0  mov     [rsp+158h+string], r12
0x18001d0b5  mov     rcx, [rsp+158h+var_128]
0x18001d0ba  mov     rax, [rcx]
0x18001d0bd  mov     [rsp+158h+string], r12
0x18001d0c2  lea     rdx, [rsp+158h+string]
0x18001d0c7  mov     rax, [rax+188h]
0x18001d0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0d3  test    eax, eax
0x18001d0d5  jns     short loc_18001D139
0x18001d0d7  cmp     eax, esi
0x18001d0d9  jz      short loc_18001D0F8
0x18001d0db  mov     rcx, [rsp+158h]; this
0x18001d0e3  mov     r9d, eax; char *
0x18001d0e6  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001d0ed  mov     edx, 472h; void *
0x18001d0f2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d0f8  mov     rcx, [rsp+158h+string]; string
0x18001d0fd  test    rcx, rcx
0x18001d100  jz      short loc_18001D108
0x18001d102  call    WindowsDeleteString
0x18001d107  nop
0x18001d108  mov     rcx, [rsp+158h+var_118]; string
0x18001d10d  test    rcx, rcx
0x18001d110  jz      short loc_18001D118
0x18001d112  call    WindowsDeleteString
0x18001d117  nop
0x18001d118  mov     rcx, [rsp+158h+var_128]
0x18001d11d  test    rcx, rcx
0x18001d120  jz      short loc_18001D134
0x18001d122  mov     [rsp+158h+var_128], r12
0x18001d127  mov     rax, [rcx]
0x18001d12a  mov     rax, [rax+10h]
0x18001d12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d133  nop
0x18001d134  jmp     loc_18001D291
0x18001d139  xor     edx, edx; length
0x18001d13b  mov     rcx, [rsp+158h+var_118]; string
0x18001d140  call    WindowsGetStringRawBuffer
0x18001d145  xorps   xmm0, xmm0
0x18001d148  movups  [rsp+158h+var_D8], xmm0
0x18001d150  xorps   xmm1, xmm1
0x18001d153  movdqu  xmmword ptr [rsp+90h], xmm1
0x18001d15c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d160  inc     r8
0x18001d163  cmp     [rax+r8*2], r12w
0x18001d168  jnz     short loc_18001D160
0x18001d16a  mov     rdx, rax
0x18001d16d  lea     rcx, [rsp+158h+var_D8]
0x18001d175  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d17a  nop
0x18001d17b  xor     edx, edx; length
0x18001d17d  mov     rcx, [rsp+158h+string]; string
0x18001d182  call    WindowsGetStringRawBuffer
0x18001d187  xorps   xmm0, xmm0
0x18001d18a  movups  [rsp+158h+var_B8], xmm0
0x18001d192  xorps   xmm1, xmm1
0x18001d195  movdqu  [rsp+158h+var_A8], xmm1
0x18001d19e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d1a2  inc     r8
0x18001d1a5  cmp     [rax+r8*2], r12w
0x18001d1aa  jnz     short loc_18001D1A2
0x18001d1ac  mov     rdx, rax
0x18001d1af  lea     rcx, [rsp+158h+var_B8]
0x18001d1b7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001d1bc  nop
0x18001d1bd  lea     rdx, [rsp+158h+var_B8]
0x18001d1c5  lea     rcx, [rsp+158h+var_58]
0x18001d1cd  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18001d1d2  mov     rbx, rax
0x18001d1d5  lea     rdx, [rsp+158h+var_D8]
0x18001d1dd  lea     rcx, [rsp+158h+var_98]
0x18001d1e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d1ea  mov     rdx, rbx
0x18001d1ed  lea     rcx, [rsp+158h+var_78]
0x18001d1f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001d1fa  nop
0x18001d1fb  lea     rdx, [rsp+158h+var_98]
0x18001d203  mov     rcx, r15
0x18001d206  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x18001d20b  nop
0x18001d20c  lea     rcx, [rsp+158h+var_78]
0x18001d214  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d219  lea     rcx, [rsp+158h+var_98]
0x18001d221  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d226  nop
0x18001d227  lea     rcx, [rsp+158h+var_58]
0x18001d22f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d234  nop
0x18001d235  lea     rcx, [rsp+158h+var_B8]
0x18001d23d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d242  nop
0x18001d243  lea     rcx, [rsp+158h+var_D8]
0x18001d24b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d250  nop
0x18001d251  mov     rcx, [rsp+158h+string]; string
0x18001d256  test    rcx, rcx
0x18001d259  jz      short loc_18001D261
0x18001d25b  call    WindowsDeleteString
0x18001d260  nop
0x18001d261  or      r14d, 1
0x18001d265  mov     rcx, [rsp+158h+var_118]; string
0x18001d26a  test    rcx, rcx
0x18001d26d  jz      short loc_18001D275
0x18001d26f  call    WindowsDeleteString
0x18001d274  nop
0x18001d275  mov     rcx, [rsp+158h+var_128]
0x18001d27a  test    rcx, rcx
0x18001d27d  jz      short loc_18001D291
0x18001d27f  mov     [rsp+158h+var_128], r12
0x18001d284  mov     rax, [rcx]
0x18001d287  mov     rax, [rax+10h]
0x18001d28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d290  nop
0x18001d291  inc     edi
0x18001d293  jmp     loc_18001CFF5
0x18001d298  mov     rcx, [rsp+158h+var_110]
0x18001d29d  test    rcx, rcx
0x18001d2a0  jz      short loc_18001D2B4
0x18001d2a2  mov     [rsp+158h+var_110], r12
0x18001d2a7  mov     rax, [rcx]
0x18001d2aa  mov     rax, [rax+10h]
0x18001d2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2b3  nop
0x18001d2b4  mov     rcx, [rsp+158h+var_100]
0x18001d2b9  test    rcx, rcx
0x18001d2bc  jz      short loc_18001D2D0
0x18001d2be  mov     [rsp+158h+var_100], r12
0x18001d2c3  mov     rax, [rcx]
0x18001d2c6  mov     rax, [rax+10h]
0x18001d2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cf  nop
0x18001d2d0  mov     rcx, [rsp+158h+var_38]
0x18001d2d8  xor     rcx, rsp; StackCookie
0x18001d2db  call    __security_check_cookie
0x18001d2e0  mov     rbx, [rsp+158h+arg_10]
0x18001d2e8  add     rsp, 130h
0x18001d2ef  pop     r15
0x18001d2f1  pop     r14
0x18001d2f3  pop     r12
0x18001d2f5  pop     rdi
0x18001d2f6  pop     rsi
0x18001d2f7  retn
0x18001d2f8  jmp     short loc_18001D2D0
0x18001d2fa  jmp     short loc_18001D2D0
0x18001d2fc  mov     ecx, 32h ; '2'; dwErrCode
0x18001d301  call    cs:__imp_SetLastError
0x18001d307  mov     eax, 80004001h
0x18001d30c  mov     ecx, eax; this
0x18001d30e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
