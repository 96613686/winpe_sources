# Details::GetAppResult(Windows::System::ILaunchUriResult *)

- ea: `0x180025080`
- end: `0x1800252fd`
- name: `?GetAppResult@Details@@YA?AW4CloudExperienceHostResult@@PEAUILaunchUriResult@System@Windows@@@Z`
- size: `637`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180023bbc`
- `0x180023d08`
- `0x18002418c`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x18000c970`
- `0x180017c58`
- `0x18001ac98`
- `0x180020ff8`
- `0x1800211e4`
- `0x180025080`
- `0x180028db4`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180025253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180025253`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Details::GetAppResult(__int64 a1)
{
  __int64 (__fastcall *v2)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v3; // eax
  __int64 (__fastcall ***v4)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v5)(_QWORD, GUID *, __int64 *); // rdi
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  unsigned int i; // ebx
  int v16; // eax
  INT32 result; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-58h] BYREF
  HSTRING string2; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string1; // [rsp+48h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v25[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v19 = 0;
  v2 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v3 = v2(a1, &v19);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
      (const char *)(unsigned int)v3,
      result);
  v4 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v19;
  if ( v19 )
  {
    v22 = 0;
    v5 = **v19;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v6 = v5(v4, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v22);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v6,
        result);
    v21 = 0;
    v7 = v22;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v25, off_180057A50);
    v10 = v8(v7, *(_QWORD *)(v9 + 24), &v21);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v10,
        result);
    v24 = 0;
    v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v21, &v24);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v11,
        result);
    string1 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 152LL))(v24, &string1);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
        (const char *)(unsigned int)v12,
        result);
    for ( i = 0; ; ++i )
    {
      if ( (unsigned __int64)(int)i >= 0xC )
        wil::details::in1diag3::Throw_Hr(retaddr, v13, v14, (const char *)0x8000FFFFLL, result);
      string2 = 0;
      v16 = Windows::Internal::String::Initialize<unsigned short const *>(&string2, (__int64 *)&off_180057A70[i], v14);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x77,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostlaunchhelpers.h",
          (const char *)(unsigned int)v16,
          result);
      result = 0;
      WindowsCompareStringOrdinal(string1, string2, &result);
      Windows::Internal::String::~String((Windows::Internal::String *)&string2);
      if ( !result )
        break;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    return i;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    return 2;
  }
}

```

## disassembly

```asm
0x180025080  mov     [rsp-8+arg_8], rbx
0x180025085  mov     [rsp-8+arg_10], rdi
0x18002508a  push    rbp
0x18002508b  mov     rbp, rsp
0x18002508e  sub     rsp, 80h
0x180025095  mov     rax, cs:__security_cookie
0x18002509c  xor     rax, rsp
0x18002509f  mov     [rbp+var_8], rax
0x1800250a3  mov     rdi, rcx
0x1800250a6  mov     [rbp+var_58], 0
0x1800250ae  mov     rax, [rcx]
0x1800250b1  mov     rbx, [rax+38h]
0x1800250b5  lea     rcx, [rbp+var_58]
0x1800250b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800250be  lea     rdx, [rbp+var_58]
0x1800250c2  mov     rcx, rdi
0x1800250c5  mov     rax, rbx
0x1800250c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250cd  mov     rcx, [rbp+8]; this
0x1800250d1  test    eax, eax
0x1800250d3  jns     short loc_1800250EA
0x1800250d5  mov     r9d, eax; char *
0x1800250d8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800250df  mov     edx, 60h ; '`'; void *
0x1800250e4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800250ea  mov     rbx, [rbp+var_58]
0x1800250ee  test    rbx, rbx
0x1800250f1  jz      loc_1800252CD
0x1800250f7  mov     [rbp+var_40], 0
0x1800250ff  mov     rax, [rbx]
0x180025102  mov     rdi, [rax]
0x180025105  lea     rcx, [rbp+var_40]
0x180025109  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002510e  lea     r8, [rbp+var_40]
0x180025112  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180025119  mov     rcx, rbx
0x18002511c  mov     rax, rdi
0x18002511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025124  nop
0x180025125  mov     rcx, [rbp+8]; this
0x180025129  test    eax, eax
0x18002512b  jns     short loc_180025142
0x18002512d  mov     r9d, eax; char *
0x180025130  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025137  mov     edx, 69h ; 'i'; void *
0x18002513c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025142  mov     [rbp+var_48], 0
0x18002514a  mov     rdi, [rbp+var_40]
0x18002514e  mov     rax, [rdi]
0x180025151  mov     rbx, [rax+30h]
0x180025155  lea     rcx, [rbp+var_48]
0x180025159  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002515e  lea     rdx, off_180057A50; "Result"
0x180025165  lea     rcx, [rbp+var_28]
0x180025169  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002516e  nop
0x18002516f  lea     r8, [rbp+var_48]
0x180025173  mov     rdx, [rax+18h]
0x180025177  mov     rcx, rdi
0x18002517a  mov     rax, rbx
0x18002517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025182  mov     rcx, [rbp+8]; this
0x180025186  test    eax, eax
0x180025188  jns     short loc_18002519F
0x18002518a  mov     r9d, eax; char *
0x18002518d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025194  mov     edx, 6Dh ; 'm'; void *
0x180025199  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002519f  mov     [rbp+var_30], 0
0x1800251a7  lea     rdx, [rbp+var_30]
0x1800251ab  lea     rcx, [rbp+var_48]
0x1800251af  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1800251b4  mov     rcx, [rbp+8]; this
0x1800251b8  test    eax, eax
0x1800251ba  jns     short loc_1800251D1
0x1800251bc  mov     r9d, eax; char *
0x1800251bf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800251c6  mov     edx, 6Fh ; 'o'; void *
0x1800251cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800251d1  mov     [rbp+string1], 0
0x1800251d9  mov     rcx, [rbp+var_30]
0x1800251dd  mov     rax, [rcx]
0x1800251e0  lea     rdx, [rbp+string1]
0x1800251e4  mov     rax, [rax+98h]
0x1800251eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251f0  mov     rcx, [rbp+8]; this
0x1800251f4  test    eax, eax
0x1800251f6  jns     short loc_18002520D
0x1800251f8  mov     r9d, eax; char *
0x1800251fb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180025202  mov     edx, 71h ; 'q'; void *
0x180025207  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002520d  xor     ebx, ebx
0x18002520f  movsxd  rax, ebx
0x180025212  cmp     rax, 0Ch
0x180025216  jnb     loc_1800252BD
0x18002521c  mov     [rbp+string2], 0
0x180025224  lea     rcx, off_180057A70; "success"
0x18002522b  lea     rdx, [rcx+rax*8]
0x18002522f  lea     rcx, [rbp+string2]
0x180025233  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x180025238  mov     rcx, [rbp+8]; this
0x18002523c  test    eax, eax
0x18002523e  js      short loc_1800252A8
0x180025240  mov     [rbp+result], 0
0x180025247  lea     r8, [rbp+result]; result
0x18002524b  mov     rdx, [rbp+string2]; string2
0x18002524f  mov     rcx, [rbp+string1]; string1
0x180025253  call    cs:__imp_WindowsCompareStringOrdinal
0x18002525a  nop     dword ptr [rax+rax+00h]
0x18002525f  nop
0x180025260  lea     rcx, [rbp+string2]; this
0x180025264  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180025269  cmp     [rbp+result], 0
0x18002526d  jz      short loc_180025273
0x18002526f  inc     ebx
0x180025271  jmp     short loc_18002520F
0x180025273  lea     rcx, [rbp+string1]; this
0x180025277  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002527c  nop
0x18002527d  lea     rcx, [rbp+var_30]
0x180025281  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025286  nop
0x180025287  lea     rcx, [rbp+var_48]
0x18002528b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025290  nop
0x180025291  lea     rcx, [rbp+var_40]
0x180025295  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002529a  nop
0x18002529b  lea     rcx, [rbp+var_58]
0x18002529f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252a4  mov     eax, ebx
0x1800252a6  jmp     short loc_1800252DB
0x1800252a8  mov     r9d, eax; char *
0x1800252ab  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800252b2  mov     edx, 77h ; 'w'; void *
0x1800252b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800252bd  mov     rcx, [rbp+8]; this
0x1800252c1  mov     r9d, 8000FFFFh; char *
0x1800252c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800252cd  lea     rcx, [rbp+var_58]
0x1800252d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252d6  mov     eax, 2
0x1800252db  mov     rcx, [rbp+var_8]
0x1800252df  xor     rcx, rsp; StackCookie
0x1800252e2  call    __security_check_cookie
0x1800252e7  lea     r11, [rsp+80h+var_s0]
0x1800252ef  mov     rbx, [r11+18h]
0x1800252f3  mov     rdi, [r11+20h]
0x1800252f7  mov     rsp, r11
0x1800252fa  pop     rbp
0x1800252fb  retn
```
