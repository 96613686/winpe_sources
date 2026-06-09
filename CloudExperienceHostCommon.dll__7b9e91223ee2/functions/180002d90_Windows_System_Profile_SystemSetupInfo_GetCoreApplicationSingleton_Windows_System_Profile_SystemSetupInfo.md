# Windows::System::Profile::SystemSetupInfo::GetCoreApplicationSingleton(Windows::System::Profile::SystemSetupInfo * *)

- ea: `0x180002d90`
- end: `0x1800030af`
- name: `?GetCoreApplicationSingleton@SystemSetupInfo@Profile@System@Windows@@AEAAJPEAPEAV1234@@Z`
- size: `799`
- prototype: `__int64 __fastcall(Windows::System::Profile::SystemSetupInfo *__hidden this, struct Windows::System::Profile::SystemSetupInfo **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180002b80`
- `0x1800c8660`
- `0x1800c87e0`

## callees

- `0x180002d90`
- `0x180003270`
- `0x180010c8c`
- `0x18001a540`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003087`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003087`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180002de8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003012`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002e07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180002e07`

## string_xrefs

- `0x180002f21`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::System::Profile::SystemSetupInfo::GetCoreApplicationSingleton(
        Windows::System::Profile::SystemSetupInfo *this,
        struct Windows::System::Profile::SystemSetupInfo **a2)
{
  HRESULT v4; // eax
  int ActivationFactory; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  int v14; // eax
  int v15; // [rsp+20h] [rbp-78h]
  char v16; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v17[7]; // [rsp+31h] [rbp-67h] BYREF
  __int64 v18; // [rsp+38h] [rbp-60h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-58h] BYREF
  __int64 v20; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-38h] BYREF
  HSTRING string; // [rsp+78h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    *a2 = 0;
    if ( *((_BYTE *)this + 186) )
    {
      *a2 = this;
      (*(void (__fastcall **)(Windows::System::Profile::SystemSetupInfo *))(*(_QWORD *)this + 8LL))(this);
      return 0;
    }
    v21[0] = 0;
    string = 0;
    v4 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(string, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, v21);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v15);
      v20 = 0;
      v8 = *(_QWORD *)v21[0];
      v20 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v8 + 56))(v21[0], &v20);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
          (const char *)(unsigned int)v9,
          v15);
      v18 = 0;
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
              v20,
              &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
              &v18);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v10,
          v15);
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        &v19,
        L"Windows.System.Profile.SystemSetupInfo");
      v16 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v18 + 64LL))(v18, v19, &v16);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
          (const char *)(unsigned int)v11,
          v15);
      if ( v16 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::System::Profile::SystemSetupInfo **))(*(_QWORD *)v18 + 48LL))(
                v18,
                v19,
                a2);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC3,
            (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
            (const char *)(unsigned int)v12,
            v15);
        goto LABEL_25;
      }
      v21[1] = this;
      (*(void (__fastcall **)(Windows::System::Profile::SystemSetupInfo *))(*(_QWORD *)this + 8LL))(this);
      v17[0] = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, Windows::System::Profile::SystemSetupInfo *, _BYTE *))(*(_QWORD *)v18 + 80LL))(
              v18,
              v19,
              this,
              v17);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
          (const char *)(unsigned int)v14,
          v15);
      v13 = retaddr;
      if ( !v17[0] )
      {
        *a2 = this;
        (*(void (__fastcall **)(Windows::System::Profile::SystemSetupInfo *))(*(_QWORD *)this + 8LL))(this);
        (*(void (__fastcall **)(Windows::System::Profile::SystemSetupInfo *))(*(_QWORD *)this + 16LL))(this);
LABEL_25:
        if ( v19 )
          WindowsDeleteString(v19);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( v21[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21[0] + 16LL))(v21[0]);
        return 0;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
      (const char *)0x8000FFFFLL,
      v15);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD2,
                           (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\systemsetupinfo.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_0], rbx
0x180002d95  mov     [rsp+arg_10], rsi
0x180002d9a  push    rdi
0x180002d9b  sub     rsp, 90h
0x180002da2  mov     rax, cs:__security_cookie
0x180002da9  xor     rax, rsp
0x180002dac  mov     [rsp+98h+var_18], rax
0x180002db4  mov     rdi, rdx
0x180002db7  mov     rbx, rcx
0x180002dba  xor     esi, esi
0x180002dbc  mov     [rdx], rsi
0x180002dbf  cmp     [rcx+0BAh], sil
0x180002dc6  jnz     short loc_180002E32
0x180002dc8  mov     [rsp+98h+var_48], rsi
0x180002dcd  mov     [rsp+98h+string], rsi
0x180002dd2  lea     r9, [rsp+98h+string]; string
0x180002dd7  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180002ddc  mov     edx, 2Dh ; '-'; length
0x180002de1  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180002de8  call    cs:__imp_WindowsCreateStringReference
0x180002dee  test    eax, eax
0x180002df0  js      loc_18000307A
0x180002df6  lea     r8, [rsp+98h+var_48]
0x180002dfb  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180002e02  mov     rcx, [rsp+98h+string]
0x180002e07  call    cs:__imp_RoGetActivationFactory
0x180002e0d  mov     rcx, [rsp+98h]; this
0x180002e15  test    eax, eax
0x180002e17  jns     loc_180002EB0
0x180002e1d  mov     r9d, eax; char *
0x180002e20  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x180002e27  mov     edx, 0B5h; void *
0x180002e2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002e32  mov     [rdx], rbx
0x180002e35  mov     rax, [rcx]
0x180002e38  mov     rax, [rax+8]
0x180002e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e41  nop
0x180002e42  jmp     short loc_180002E89
0x180002e44  mov     rcx, [rsp+98h+var_60]
0x180002e49  test    rcx, rcx
0x180002e4c  jz      short loc_180002E5B
0x180002e4e  mov     rax, [rcx]
0x180002e51  mov     rax, [rax+10h]
0x180002e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5a  nop
0x180002e5b  mov     rcx, [rsp+98h+var_50]
0x180002e60  test    rcx, rcx
0x180002e63  jz      short loc_180002E72
0x180002e65  mov     rax, [rcx]
0x180002e68  mov     rax, [rax+10h]
0x180002e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e71  nop
0x180002e72  mov     rcx, [rsp+98h+var_48]
0x180002e77  test    rcx, rcx
0x180002e7a  jz      short loc_180002E89
0x180002e7c  mov     rax, [rcx]
0x180002e7f  mov     rax, [rax+10h]
0x180002e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e88  nop
0x180002e89  xor     eax, eax
0x180002e8b  mov     rcx, [rsp+98h+var_18]
0x180002e93  xor     rcx, rsp; StackCookie
0x180002e96  call    __security_check_cookie
0x180002e9b  lea     r11, [rsp+98h+var_8]
0x180002ea3  mov     rbx, [r11+10h]
0x180002ea7  mov     rsi, [r11+20h]
0x180002eab  mov     rsp, r11
0x180002eae  pop     rdi
0x180002eaf  retn
0x180002eb0  mov     [rsp+98h+var_50], rsi
0x180002eb5  mov     rcx, [rsp+98h+var_48]
0x180002eba  mov     rax, [rcx]
0x180002ebd  mov     [rsp+98h+var_50], rsi
0x180002ec2  lea     rdx, [rsp+98h+var_50]
0x180002ec7  mov     rax, [rax+38h]
0x180002ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed0  mov     rcx, [rsp+98h]; this
0x180002ed8  test    eax, eax
0x180002eda  jns     short loc_180002EF1
0x180002edc  mov     r9d, eax; char *
0x180002edf  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x180002ee6  mov     edx, 0B8h; void *
0x180002eeb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002ef1  mov     [rsp+98h+var_60], rsi
0x180002ef6  mov     rcx, [rsp+98h+var_50]
0x180002efb  mov     rax, [rcx]
0x180002efe  lea     r8, [rsp+98h+var_60]
0x180002f03  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180002f0a  mov     rax, [rax]
0x180002f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f12  mov     rcx, [rsp+98h]; this
0x180002f1a  test    eax, eax
0x180002f1c  jns     short loc_180002F32
0x180002f1e  mov     r9d, eax; char *
0x180002f21  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002f28  mov     edx, 1CBEh; void *
0x180002f2d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002f32  lea     rdx, ?RuntimeClass_Windows_System_Profile_SystemSetupInfo@@3QBGB; "Windows.System.Profile.SystemSetupInfo"
0x180002f39  lea     rcx, [rsp+98h+var_58]; string
0x180002f3e  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180002f43  nop
0x180002f44  mov     [rsp+98h+var_68], 0
0x180002f49  mov     rcx, [rsp+98h+var_60]
0x180002f4e  mov     rax, [rcx]
0x180002f51  lea     r8, [rsp+98h+var_68]
0x180002f56  mov     rdx, [rsp+98h+var_58]
0x180002f5b  mov     rax, [rax+40h]
0x180002f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f64  test    eax, eax
0x180002f66  jns     short loc_180002F84
0x180002f68  mov     rcx, [rsp+98h]; this
0x180002f70  mov     r9d, eax; char *
0x180002f73  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x180002f7a  mov     edx, 0C0h; void *
0x180002f7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002f84  cmp     [rsp+98h+var_68], 0
0x180002f89  jz      loc_18000301D
0x180002f8f  mov     rcx, [rsp+98h+var_60]
0x180002f94  mov     rax, [rcx]
0x180002f97  mov     r8, rdi
0x180002f9a  mov     rdx, [rsp+98h+var_58]
0x180002f9f  mov     rax, [rax+30h]
0x180002fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa8  mov     rcx, [rsp+98h]; this
0x180002fb0  test    eax, eax
0x180002fb2  jns     short loc_180003004
0x180002fb4  mov     r9d, eax; char *
0x180002fb7  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x180002fbe  mov     edx, 0C3h; void *
0x180002fc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180002fc9  cmp     [rsp+98h+var_67], 0
0x180002fce  setnz   al
0x180002fd1  mov     rcx, [rsp+98h]
0x180002fd9  test    al, al
0x180002fdb  jnz     loc_18000308E
0x180002fe1  mov     [rdi], rbx
0x180002fe4  mov     rax, [rbx]
0x180002fe7  mov     rcx, rbx
0x180002fea  mov     rax, [rax+8]
0x180002fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff3  nop
0x180002ff4  mov     rax, [rbx]
0x180002ff7  mov     rcx, rbx
0x180002ffa  mov     rax, [rax+10h]
0x180002ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003003  nop
0x180003004  mov     rcx, [rsp+98h+var_58]; string
0x180003009  test    rcx, rcx
0x18000300c  jz      loc_180002E44
0x180003012  call    cs:__imp_WindowsDeleteString
0x180003018  jmp     loc_180002E44
0x18000301d  mov     [rsp+98h+var_40], rbx
0x180003022  mov     rax, [rbx]
0x180003025  mov     rcx, rbx
0x180003028  mov     rax, [rax+8]
0x18000302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003031  nop
0x180003032  mov     [rsp+98h+var_67], 0
0x180003037  mov     rcx, [rsp+98h+var_60]
0x18000303c  mov     rax, [rcx]
0x18000303f  lea     r9, [rsp+98h+var_67]
0x180003044  mov     r8, rbx
0x180003047  mov     rdx, [rsp+98h+var_58]
0x18000304c  mov     rax, [rax+50h]
0x180003050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003055  mov     rcx, [rsp+98h]; this
0x18000305d  test    eax, eax
0x18000305f  jns     loc_180002FC9
0x180003065  mov     r9d, eax; char *
0x180003068  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x18000306f  mov     edx, 0CCh; void *
0x180003074  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000307a  xor     r9d, r9d; lpArguments
0x18000307d  xor     r8d, r8d; nNumberOfArguments
0x180003080  mov     edx, 1; dwExceptionFlags
0x180003085  mov     ecx, eax; dwExceptionCode
0x180003087  call    cs:__imp_RaiseException
0x18000308d  nop
0x18000308e  mov     r9d, 8000FFFFh; char *
0x180003094  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\cloudexperiencehost"...
0x18000309b  mov     edx, 0CDh; void *
0x1800030a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800030a6  mov     eax, dword ptr [rsp+98h+var_60]
0x1800030aa  jmp     loc_180002E8B
```
