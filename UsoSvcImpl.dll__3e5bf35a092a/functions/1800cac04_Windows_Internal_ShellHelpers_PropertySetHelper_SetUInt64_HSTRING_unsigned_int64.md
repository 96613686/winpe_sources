# Windows::Internal::ShellHelpers::PropertySetHelper::SetUInt64(HSTRING__ *,unsigned __int64)

- ea: `0x1800cac04`
- end: `0x1800cae88`
- name: `?SetUInt64@PropertySetHelper@ShellHelpers@Internal@Windows@@QEAAJPEAUHSTRING__@@_K@Z`
- size: `644`
- prototype: `__int64 __fastcall(Windows::Internal::ShellHelpers::PropertySetHelper *__hidden this, HSTRING, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800cf920`

## callees

- `0x180008e64`
- `0x180092dd8`
- `0x1800ca89c`
- `0x1800cac04`
- `0x1800d35fc`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cac4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cac4c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cac69`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cac69`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::ShellHelpers::PropertySetHelper::SetUInt64(
        Windows::Internal::ShellHelpers::PropertySetHelper *this,
        HSTRING a2,
        __int64 a3)
{
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v14; // rcx
  int v15; // eax
  struct ABI::Windows::Foundation::IPropertyValue *v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v18; // rcx
  struct ABI::Windows::Foundation::IPropertyValue *v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v21; // rcx
  struct ABI::Windows::Foundation::IPropertyValue *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v24; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // [rsp+48h] [rbp-18h] BYREF
  struct ABI::Windows::Foundation::IPropertyValue *v30; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v28 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x1800CAE87LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v28);
  v10 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v29 = 0;
    v12 =  ABI::Windows::Foundation::IPropertyValueStatics::`vcall'{104,{flat}}(v28, a3, &v29);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v30 = 0;
      v15 = (**v29)(v29, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v30);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v10 = Windows::Internal::ShellHelpers::PropertySetHelper::SetPropVal(this, a2, v30);
        if ( v10 >= 0 )
        {
          v22 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v23 = v29;
          if ( v29 )
          {
            v29 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v23)[2])(v23);
          }
          v24 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          return 0;
        }
        else
        {
          v19 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v19 + 16LL))(v19);
          }
          v20 = v29;
          if ( v29 )
          {
            v29 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v20)[2])(v20);
          }
          v21 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
          (const char *)(unsigned int)v15,
          (int)hstringHeader.Reserved.Reserved1);
        v16 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v17 = v29;
        if ( v29 )
        {
          v29 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v17)[2])(v17);
        }
        v18 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
        (const char *)(unsigned int)v12,
        (int)hstringHeader.Reserved.Reserved1);
      v13 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v13)[2])(v13);
      }
      v14 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    v11 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800cac04  mov     [rsp-28h+arg_18], rbx
0x1800cac09  push    rbp
0x1800cac0a  push    rsi
0x1800cac0b  push    rdi
0x1800cac0c  push    r14
0x1800cac0e  push    r15
0x1800cac10  mov     rbp, rsp
0x1800cac13  sub     rsp, 60h
0x1800cac17  mov     rax, cs:__security_cookie
0x1800cac1e  xor     rax, rsp
0x1800cac21  mov     [rbp+var_8], rax
0x1800cac25  mov     rdi, r8
0x1800cac28  mov     r14, rdx
0x1800cac2b  mov     rsi, rcx
0x1800cac2e  xor     r15d, r15d
0x1800cac31  mov     [rbp+var_20], r15
0x1800cac35  mov     [rbp+string], r15
0x1800cac39  lea     r9, [rbp+string]; string
0x1800cac3d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800cac41  lea     edx, [r15+20h]; length
0x1800cac45  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QB_WB; "Windows.Foundation.PropertyValue"
0x1800cac4c  call    cs:__imp_WindowsCreateStringReference
0x1800cac52  test    eax, eax
0x1800cac54  js      loc_1800CAE80
0x1800cac5a  lea     r8, [rbp+var_20]
0x1800cac5e  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800cac65  mov     rcx, [rbp+string]
0x1800cac69  call    cs:__imp_RoGetActivationFactory
0x1800cac6f  mov     ebx, eax
0x1800cac71  test    eax, eax
0x1800cac73  jns     short loc_1800CACAC
0x1800cac75  mov     rcx, [rbp+28h]; this
0x1800cac79  mov     r9d, eax; char *
0x1800cac7c  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800cac83  lea     edx, [r15+50h]; void *
0x1800cac87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cac8c  nop
0x1800cac8d  mov     rcx, [rbp+var_20]
0x1800cac91  test    rcx, rcx
0x1800cac94  jz      short loc_1800CACA7
0x1800cac96  mov     [rbp+var_20], r15
0x1800cac9a  mov     rax, [rcx]
0x1800cac9d  mov     rax, [rax+10h]
0x1800caca1  call    _guard_dispatch_icall
0x1800caca6  nop
0x1800caca7  jmp     loc_1800CAE5E
0x1800cacac  mov     [rbp+var_18], r15
0x1800cacb0  lea     r8, [rbp+var_18]
0x1800cacb4  mov     rdx, rdi
0x1800cacb7  mov     rcx, [rbp+var_20]
0x1800cacbb  call    ??_9IPropertyValueStatics@Foundation@Windows@ABI@@$BGI@AA; [thunk]: ABI::Windows::Foundation::IPropertyValueStatics::`vcall'{104,{flat}}
0x1800cacc0  mov     ebx, eax
0x1800cacc2  test    eax, eax
0x1800cacc4  jns     short loc_1800CAD18
0x1800cacc6  mov     rcx, [rbp+28h]; this
0x1800cacca  mov     r9d, eax; char *
0x1800caccd  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800cacd4  mov     edx, 52h ; 'R'; void *
0x1800cacd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cacde  nop
0x1800cacdf  mov     rcx, [rbp+var_18]
0x1800cace3  test    rcx, rcx
0x1800cace6  jz      short loc_1800CACF9
0x1800cace8  mov     [rbp+var_18], r15
0x1800cacec  mov     rax, [rcx]
0x1800cacef  mov     rax, [rax+10h]
0x1800cacf3  call    _guard_dispatch_icall
0x1800cacf8  nop
0x1800cacf9  mov     rcx, [rbp+var_20]
0x1800cacfd  test    rcx, rcx
0x1800cad00  jz      short loc_1800CAD13
0x1800cad02  mov     [rbp+var_20], r15
0x1800cad06  mov     rax, [rcx]
0x1800cad09  mov     rax, [rax+10h]
0x1800cad0d  call    _guard_dispatch_icall
0x1800cad12  nop
0x1800cad13  jmp     loc_1800CAE5E
0x1800cad18  mov     [rbp+var_10], r15
0x1800cad1c  mov     rcx, [rbp+var_18]
0x1800cad20  mov     rax, [rcx]
0x1800cad23  lea     r8, [rbp+var_10]
0x1800cad27  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800cad2e  mov     rax, [rax]
0x1800cad31  call    _guard_dispatch_icall
0x1800cad36  mov     ebx, eax
0x1800cad38  test    eax, eax
0x1800cad3a  jns     short loc_1800CADA8
0x1800cad3c  mov     rcx, [rbp+28h]; this
0x1800cad40  mov     r9d, eax; char *
0x1800cad43  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800cad4a  mov     edx, 54h ; 'T'; void *
0x1800cad4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cad54  nop
0x1800cad55  mov     rcx, [rbp+var_10]
0x1800cad59  test    rcx, rcx
0x1800cad5c  jz      short loc_1800CAD6F
0x1800cad5e  mov     [rbp+var_10], r15
0x1800cad62  mov     rax, [rcx]
0x1800cad65  mov     rax, [rax+10h]
0x1800cad69  call    _guard_dispatch_icall
0x1800cad6e  nop
0x1800cad6f  mov     rcx, [rbp+var_18]
0x1800cad73  test    rcx, rcx
0x1800cad76  jz      short loc_1800CAD89
0x1800cad78  mov     [rbp+var_18], r15
0x1800cad7c  mov     rax, [rcx]
0x1800cad7f  mov     rax, [rax+10h]
0x1800cad83  call    _guard_dispatch_icall
0x1800cad88  nop
0x1800cad89  mov     rcx, [rbp+var_20]
0x1800cad8d  test    rcx, rcx
0x1800cad90  jz      short loc_1800CADA3
0x1800cad92  mov     [rbp+var_20], r15
0x1800cad96  mov     rax, [rcx]
0x1800cad99  mov     rax, [rax+10h]
0x1800cad9d  call    _guard_dispatch_icall
0x1800cada2  nop
0x1800cada3  jmp     loc_1800CAE5E
0x1800cada8  mov     r8, [rbp+var_10]; struct ABI::Windows::Foundation::IPropertyValue *
0x1800cadac  mov     rdx, r14; HSTRING
0x1800cadaf  mov     rcx, rsi; this
0x1800cadb2  call    ?SetPropVal@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAUIPropertyValue@Foundation@4ABI@@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetPropVal(HSTRING__ *,ABI::Windows::Foundation::IPropertyValue *)
0x1800cadb7  mov     ebx, eax
0x1800cadb9  test    eax, eax
0x1800cadbb  jns     short loc_1800CAE0D
0x1800cadbd  mov     rcx, [rbp+var_10]
0x1800cadc1  test    rcx, rcx
0x1800cadc4  jz      short loc_1800CADD7
0x1800cadc6  mov     [rbp+var_10], r15
0x1800cadca  mov     rax, [rcx]
0x1800cadcd  mov     rax, [rax+10h]
0x1800cadd1  call    _guard_dispatch_icall
0x1800cadd6  nop
0x1800cadd7  mov     rcx, [rbp+var_18]
0x1800caddb  test    rcx, rcx
0x1800cadde  jz      short loc_1800CADF1
0x1800cade0  mov     [rbp+var_18], r15
0x1800cade4  mov     rax, [rcx]
0x1800cade7  mov     rax, [rax+10h]
0x1800cadeb  call    _guard_dispatch_icall
0x1800cadf0  nop
0x1800cadf1  mov     rcx, [rbp+var_20]
0x1800cadf5  test    rcx, rcx
0x1800cadf8  jz      short loc_1800CAE0B
0x1800cadfa  mov     [rbp+var_20], r15
0x1800cadfe  mov     rax, [rcx]
0x1800cae01  mov     rax, [rax+10h]
0x1800cae05  call    _guard_dispatch_icall
0x1800cae0a  nop
0x1800cae0b  jmp     short loc_1800CAE5E
0x1800cae0d  mov     rcx, [rbp+var_10]
0x1800cae11  test    rcx, rcx
0x1800cae14  jz      short loc_1800CAE27
0x1800cae16  mov     [rbp+var_10], r15
0x1800cae1a  mov     rax, [rcx]
0x1800cae1d  mov     rax, [rax+10h]
0x1800cae21  call    _guard_dispatch_icall
0x1800cae26  nop
0x1800cae27  mov     rcx, [rbp+var_18]
0x1800cae2b  test    rcx, rcx
0x1800cae2e  jz      short loc_1800CAE41
0x1800cae30  mov     [rbp+var_18], r15
0x1800cae34  mov     rax, [rcx]
0x1800cae37  mov     rax, [rax+10h]
0x1800cae3b  call    _guard_dispatch_icall
0x1800cae40  nop
0x1800cae41  mov     rcx, [rbp+var_20]
0x1800cae45  test    rcx, rcx
0x1800cae48  jz      short loc_1800CAE5B
0x1800cae4a  mov     [rbp+var_20], r15
0x1800cae4e  mov     rax, [rcx]
0x1800cae51  mov     rax, [rax+10h]
0x1800cae55  call    _guard_dispatch_icall
0x1800cae5a  nop
0x1800cae5b  mov     ebx, r15d
0x1800cae5e  mov     eax, ebx
0x1800cae60  mov     rcx, [rbp+var_8]
0x1800cae64  xor     rcx, rsp; StackCookie
0x1800cae67  call    __security_check_cookie
0x1800cae6c  mov     rbx, [rsp+60h+arg_18]
0x1800cae74  add     rsp, 60h
0x1800cae78  pop     r15
0x1800cae7a  pop     r14
0x1800cae7c  pop     rdi
0x1800cae7d  pop     rsi
0x1800cae7e  pop     rbp
0x1800cae7f  retn
0x1800cae80  mov     ecx, eax; this
0x1800cae82  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
