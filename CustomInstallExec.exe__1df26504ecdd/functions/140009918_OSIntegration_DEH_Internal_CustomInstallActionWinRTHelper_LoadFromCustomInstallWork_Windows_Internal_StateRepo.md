# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::LoadFromCustomInstallWork(Windows::Internal::StateRepository::ICustomInstallWork *)

- ea: `0x140009918`
- end: `0x140009cd1`
- name: `?LoadFromCustomInstallWork@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAXPEAUICustomInstallWork@StateRepository@2Windows@@@Z`
- size: `953`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *__hidden this, struct Windows::Internal::StateRepository::ICustomInstallWork *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009cd8`

## callees

- `0x1400050a0`
- `0x140007d78`
- `0x1400083f4`
- `0x1400098dc`
- `0x140009918`
- `0x14000b7a8`
- `0x14000b7d0`
- `0x14000e61c`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000996a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400099b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140009a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000996a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400099b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140009a05`

## string_xrefs

- `0x140009c80`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installaction.cpp`
- `0x140009ba1`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009bd5`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009bea`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009bff`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c14`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c29`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c3e`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c53`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c68`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009c95`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009caa`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009cbf`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009b95`: `CustomInstallWork Flags are INVALID`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::LoadFromCustomInstallWork(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this,
        struct Windows::Internal::StateRepository::ICustomInstallWork *a2)
{
  int v4; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v6; // eax
  int v7; // eax
  const unsigned __int16 *v8; // rax
  int v9; // eax
  int v10; // eax
  const unsigned __int16 *v11; // rax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // esi
  int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // r8d
  int v23; // [rsp+20h] [rbp-40h]
  const char *v24; // [rsp+28h] [rbp-38h]
  int v25; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-28h] BYREF
  HSTRING v27; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  __int64 v29; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v31; // [rsp+88h] [rbp+28h] BYREF
  unsigned int v32; // [rsp+90h] [rbp+30h] BYREF
  int v33; // [rsp+98h] [rbp+38h] BYREF

  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)0x8000FFFFLL,
      v23);
  string = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, HSTRING *))(*(_QWORD *)a2 + 144LL))(
         a2,
         &string);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v4,
      v23);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v6 = Common::StringBuffer::SetValueFromString(this, StringRawBuffer);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v6,
      v23);
  v27 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, HSTRING *))(*(_QWORD *)a2 + 256LL))(
         a2,
         &v27);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v7,
      v23);
  v8 = WindowsGetStringRawBuffer(v27, 0);
  v9 = Common::StringBuffer::SetValueFromString(
         (OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)((char *)this + 24),
         v8);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v9,
      v23);
  v26 = 0;
  v10 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, HSTRING *))(*(_QWORD *)a2 + 304LL))(
          a2,
          &v26);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v11 = WindowsGetStringRawBuffer(v26, 0);
  v12 = Common::StringBuffer::SetValueFromString(
          (OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)((char *)this + 48),
          v11);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v12,
      v23);
  v33 = -1;
  v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, int *))(*(_QWORD *)a2 + 160LL))(
          a2,
          &v33);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v13,
      v23);
  v14 = (unsigned int)v33 >> 31;
  if ( v33 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installaction.cpp",
      (const char *)0x8000FFFFLL,
      v23);
  *((_DWORD *)this + 18) = v33;
  v32 = 0;
  v31 = v14;
  v15 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, unsigned int *))(*(_QWORD *)a2 + 176LL))(
          a2,
          &v32);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v15,
      v23);
  v16 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, char *))(*(_QWORD *)a2 + 224LL))(
          a2,
          &v31);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v16,
      v23);
  *((_BYTE *)this + 84) = v31 != 0;
  v17 = v32 & 0xFFFFFFFB;
  v32 = v17;
  v18 = 1;
  if ( (v17 & 3) != 0 )
  {
    if ( (v17 & 2) != 0 )
    {
      *((_DWORD *)this + 20) = 1;
    }
    else
    {
      if ( (v17 & 1) == 0 )
      {
        v20 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xC6,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)v20,
          (int)"CustomInstallWork Flags are INVALID",
          v24);
      }
      *((_DWORD *)this + 20) = 2;
    }
  }
  v25 = 0;
  v19 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *, int *))(*(_QWORD *)a2 + 240LL))(
          a2,
          &v25);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v19,
      v23);
  if ( v25 )
  {
    if ( v25 != 1 )
    {
      if ( v25 != 2 )
      {
        v21 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x64, v22, (const char *)v21, v23);
      }
      v18 = 2;
    }
  }
  else
  {
    v18 = 0;
  }
  *((_DWORD *)this + 19) = v18;
  *((_DWORD *)this + 24) = v18;
  if ( *((struct Windows::Internal::StateRepository::ICustomInstallWork **)this + 11) != a2 )
  {
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::ICustomInstallWork *))(*(_QWORD *)a2 + 8LL))(a2);
    v29 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v27);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
}

```

## disassembly

```asm
0x140009918  mov     [rsp-18h+arg_0], rbx
0x14000991d  push    rbp
0x14000991e  push    rsi
0x14000991f  push    rdi
0x140009920  mov     rbp, rsp
0x140009923  sub     rsp, 60h
0x140009927  mov     rbx, rdx
0x14000992a  mov     rdi, rcx
0x14000992d  mov     rcx, [rbp+18h]; this
0x140009931  test    rdx, rdx
0x140009934  jz      loc_140009BCF
0x14000993a  mov     [rbp+string], 0
0x140009942  mov     rax, [rdx]
0x140009945  lea     rdx, [rbp+string]
0x140009949  mov     rcx, rbx
0x14000994c  mov     rax, [rax+90h]
0x140009953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009958  mov     rcx, [rbp+18h]; this
0x14000995c  test    eax, eax
0x14000995e  js      loc_140009BE7
0x140009964  xor     edx, edx; length
0x140009966  mov     rcx, [rbp+string]; string
0x14000996a  call    cs:__imp_WindowsGetStringRawBuffer
0x140009970  mov     rdx, rax; unsigned __int16 *
0x140009973  mov     rcx, rdi; this
0x140009976  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x14000997b  mov     rcx, [rbp+18h]; this
0x14000997f  test    eax, eax
0x140009981  js      loc_140009BFC
0x140009987  mov     [rbp+var_20], 0
0x14000998f  mov     rax, [rbx]
0x140009992  lea     rdx, [rbp+var_20]
0x140009996  mov     rcx, rbx
0x140009999  mov     rax, [rax+100h]
0x1400099a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099a5  mov     rcx, [rbp+18h]; this
0x1400099a9  test    eax, eax
0x1400099ab  js      loc_140009C11
0x1400099b1  xor     edx, edx; length
0x1400099b3  mov     rcx, [rbp+var_20]; string
0x1400099b7  call    cs:__imp_WindowsGetStringRawBuffer
0x1400099bd  lea     rcx, [rdi+18h]; this
0x1400099c1  mov     rdx, rax; unsigned __int16 *
0x1400099c4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1400099c9  mov     rcx, [rbp+18h]; this
0x1400099cd  test    eax, eax
0x1400099cf  js      loc_140009C26
0x1400099d5  mov     [rbp+var_28], 0
0x1400099dd  mov     rax, [rbx]
0x1400099e0  lea     rdx, [rbp+var_28]
0x1400099e4  mov     rcx, rbx
0x1400099e7  mov     rax, [rax+130h]
0x1400099ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099f3  mov     rcx, [rbp+18h]; this
0x1400099f7  test    eax, eax
0x1400099f9  js      loc_140009C3B
0x1400099ff  xor     edx, edx; length
0x140009a01  mov     rcx, [rbp+var_28]; string
0x140009a05  call    cs:__imp_WindowsGetStringRawBuffer
0x140009a0b  lea     rcx, [rdi+30h]; this
0x140009a0f  mov     rdx, rax; unsigned __int16 *
0x140009a12  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x140009a17  mov     rcx, [rbp+18h]; this
0x140009a1b  test    eax, eax
0x140009a1d  js      loc_140009C50
0x140009a23  mov     [rbp+arg_18], 0FFFFFFFFh
0x140009a2a  mov     rax, [rbx]
0x140009a2d  lea     rdx, [rbp+arg_18]
0x140009a31  mov     rcx, rbx
0x140009a34  mov     rax, [rax+0A0h]
0x140009a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a40  mov     rcx, [rbp+18h]; this
0x140009a44  test    eax, eax
0x140009a46  js      loc_140009C65
0x140009a4c  mov     edx, [rbp+arg_18]
0x140009a4f  mov     rcx, [rbp+18h]; this
0x140009a53  mov     eax, edx
0x140009a55  shr     eax, 1Fh
0x140009a58  test    al, al
0x140009a5a  jnz     loc_140009C7A
0x140009a60  mov     [rdi+48h], edx
0x140009a63  mov     [rbp+arg_10], 0
0x140009a6a  mov     [rbp+arg_8], al
0x140009a6d  mov     rax, [rbx]
0x140009a70  lea     rdx, [rbp+arg_10]
0x140009a74  mov     rcx, rbx
0x140009a77  mov     rax, [rax+0B0h]
0x140009a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a83  mov     rcx, [rbp+18h]; this
0x140009a87  test    eax, eax
0x140009a89  js      loc_140009C92
0x140009a8f  mov     rax, [rbx]
0x140009a92  lea     rdx, [rbp+arg_8]
0x140009a96  mov     rcx, rbx
0x140009a99  mov     rax, [rax+0E0h]
0x140009aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009aa5  mov     rcx, [rbp+18h]; this
0x140009aa9  test    eax, eax
0x140009aab  js      loc_140009CA7
0x140009ab1  cmp     [rbp+arg_8], 0
0x140009ab5  setnz   al
0x140009ab8  mov     [rdi+54h], al
0x140009abb  mov     eax, [rbp+arg_10]
0x140009abe  and     eax, 0FFFFFFFBh
0x140009ac1  mov     [rbp+arg_10], eax
0x140009ac4  mov     esi, 1
0x140009ac9  test    al, 3
0x140009acb  jz      short loc_140009AD4
0x140009acd  test    al, 2
0x140009acf  jz      short loc_140009B08
0x140009ad1  mov     [rdi+50h], esi
0x140009ad4  mov     [rbp+var_30], 0
0x140009adb  mov     rax, [rbx]
0x140009ade  lea     rdx, [rbp+var_30]
0x140009ae2  mov     rcx, rbx
0x140009ae5  mov     rax, [rax+0F0h]
0x140009aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009af1  mov     rcx, [rbp+18h]; this
0x140009af5  test    eax, eax
0x140009af7  js      loc_140009CBC
0x140009afd  mov     eax, [rbp+var_30]
0x140009b00  test    eax, eax
0x140009b02  jnz     short loc_140009B16
0x140009b04  xor     esi, esi
0x140009b06  jmp     short loc_140009B25
0x140009b08  test    sil, al
0x140009b0b  jz      short loc_140009B84
0x140009b0d  mov     dword ptr [rdi+50h], 2
0x140009b14  jmp     short loc_140009AD4
0x140009b16  cmp     eax, esi
0x140009b18  jz      short loc_140009B25
0x140009b1a  cmp     eax, 2
0x140009b1d  jnz     loc_140009BB3
0x140009b23  mov     esi, eax
0x140009b25  mov     [rdi+4Ch], esi
0x140009b28  mov     [rdi+60h], esi
0x140009b2b  cmp     [rdi+58h], rbx
0x140009b2f  jz      short loc_140009B57
0x140009b31  mov     rax, [rbx]
0x140009b34  mov     rcx, rbx
0x140009b37  mov     rax, [rax+8]
0x140009b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b40  nop
0x140009b41  mov     rax, [rdi+58h]
0x140009b45  mov     [rbp+var_10], rax
0x140009b49  mov     [rdi+58h], rbx
0x140009b4d  lea     rcx, [rbp+var_10]
0x140009b51  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009b56  nop
0x140009b57  lea     rcx, [rbp+var_28]
0x140009b5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x140009b60  nop
0x140009b61  lea     rcx, [rbp+var_20]
0x140009b65  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x140009b6a  nop
0x140009b6b  lea     rcx, [rbp+string]
0x140009b6f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x140009b74  mov     rbx, [rsp+60h+arg_0]
0x140009b7c  add     rsp, 60h
0x140009b80  pop     rdi
0x140009b81  pop     rsi
0x140009b82  pop     rbp
0x140009b83  retn
0x140009b84  mov     ecx, 8000FFFFh
0x140009b89  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140009b8e  mov     r9d, eax; char *
0x140009b91  mov     rcx, [rbp+18h]; this
0x140009b95  lea     rax, aCustominstallw; "CustomInstallWork Flags are INVALID"
0x140009b9c  mov     qword ptr [rsp+60h+var_40], rax; int
0x140009ba1  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009ba8  mov     edx, 0C6h; void *
0x140009bad  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140009bb3  mov     ecx, 8000FFFFh
0x140009bb8  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140009bbd  mov     r9d, eax; char *
0x140009bc0  mov     rcx, [rbp+18h]; this
0x140009bc4  mov     edx, 64h ; 'd'; void *
0x140009bc9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140009bcf  mov     r9d, 8000FFFFh; char *
0x140009bd5  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009bdc  mov     edx, 9Ch; void *
0x140009be1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009be7  mov     r9d, eax; char *
0x140009bea  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009bf1  mov     edx, 0A0h; void *
0x140009bf6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009bfc  mov     r9d, eax; char *
0x140009bff  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c06  mov     edx, 0A1h; void *
0x140009c0b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c11  mov     r9d, eax; char *
0x140009c14  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c1b  mov     edx, 0A5h; void *
0x140009c20  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c26  mov     r9d, eax; char *
0x140009c29  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c30  mov     edx, 0A6h; void *
0x140009c35  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c3b  mov     r9d, eax; char *
0x140009c3e  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c45  mov     edx, 0AAh; void *
0x140009c4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c50  mov     r9d, eax; char *
0x140009c53  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c5a  mov     edx, 0ABh; void *
0x140009c5f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c65  mov     r9d, eax; char *
0x140009c68  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c6f  mov     edx, 0AEh; void *
0x140009c74  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c7a  mov     r9d, 8000FFFFh; char *
0x140009c80  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c87  mov     edx, 26h ; '&'; void *
0x140009c8c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009c92  mov     r9d, eax; char *
0x140009c95  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009c9c  mov     edx, 0B3h; void *
0x140009ca1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009ca7  mov     r9d, eax; char *
0x140009caa  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009cb1  mov     edx, 0B4h; void *
0x140009cb6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009cbc  mov     r9d, eax; char *
0x140009cbf  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009cc6  mov     edx, 0CBh; void *
0x140009ccb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
