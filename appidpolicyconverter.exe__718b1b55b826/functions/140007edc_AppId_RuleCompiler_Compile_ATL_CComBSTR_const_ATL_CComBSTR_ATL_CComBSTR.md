# AppId::RuleCompiler::Compile(ATL::CComBSTR const &,ATL::CComBSTR &,ATL::CComBSTR &)

- ea: `0x140007edc`
- end: `0x140007fde`
- name: `?Compile@RuleCompiler@AppId@@YAJAEBVCComBSTR@ATL@@AEAV34@1@Z`
- size: `258`
- prototype: `__int64 __fastcall(AppId::RuleCompiler *this, OLECHAR **, OLECHAR **, struct ATL::CComBSTR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000414c`

## callees

- `0x140007e3c`
- `0x140007e8c`
- `0x140007edc`
- `0x1400080b0`
- `0x1400080e4`
- `0x140008368`
- `0x14000a9ac`
- `0x140013b10`
- `0x140016010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140007f70`
- `OLEAUT32!__imp_SysFreeString` at `0x140007f97`
- `OLEAUT32!__imp_SysFreeString` at `0x140007f70`
- `OLEAUT32!__imp_SysFreeString` at `0x140007f97`

## pseudocode

```c
__int64 __fastcall AppId::RuleCompiler::Compile(
        AppId::RuleCompiler *this,
        OLECHAR **a2,
        OLECHAR **a3,
        struct ATL::CComBSTR *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  ATL::CComBSTR *v8; // rax
  ATL::CComBSTR *v9; // rax
  __int64 v11; // [rsp+0h] [rbp-A8h] BYREF
  Sharp::Util::CRefCount *v12; // [rsp+20h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-80h] BYREF
  exception *v14; // [rsp+30h] [rbp-78h] BYREF
  ATL::CAtlException *v15; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v16[4]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v17[4]; // [rsp+60h] [rbp-48h] BYREF

  v6 = 0;
  try
  {
    v7 = Sharp::Util::ComHelper::ComBstrToString((__int64)v17, (__int64 *)this);
    PolicyModel::CRule::FromXml(&v12, v7);
    std::wstring::_Tidy(v17, 1, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)v12 + 2) + 8LL))(*((_QWORD *)v12 + 2), v16);
    v8 = (ATL::CComBSTR *)Sharp::Util::ComHelper::StringToComBstr(&bstrString, *((_QWORD *)v12 + 2) + 40LL);
    ATL::CComBSTR::operator=(a2, v8);
    SysFreeString(bstrString);
    v9 = (ATL::CComBSTR *)Sharp::Util::ComHelper::StringToComBstr(&bstrString, v16);
    ATL::CComBSTR::operator=(a3, v9);
    SysFreeString(bstrString);
    std::wstring::_Tidy(v16, 1, 0);
    Sharp::Util::CRefCount::ReleaseReference(v12);
  }
  catch ( exception *v14 )
  {
    LODWORD(v12) = Sharp::Util::HResultFromStdException(v14, (const struct exception *)&v11);
    return (unsigned int)v12;
  }
  catch ( ATL::CAtlException *v15 )
  {
    LODWORD(v12) = *(_DWORD *)v15;
    return (unsigned int)v12;
  }
  v7 = Sharp::Util::ComHelper::ComBstrToString((__int64)v17, (__int64 *)this);
}

```

## disassembly

```asm
0x140007edc  push    rbx
0x140007ede  push    rsi
0x140007edf  push    rdi
0x140007ee0  sub     rsp, 90h
0x140007ee7  mov     rax, cs:__security_cookie
0x140007eee  xor     rax, rsp
0x140007ef1  mov     [rsp+0A8h+var_28], rax
0x140007ef9  mov     rsi, r8
0x140007efc  mov     rdi, rdx
0x140007eff  xor     ebx, ebx
0x140007f01  mov     rdx, rcx
0x140007f04  lea     rcx, [rsp+0A8h+var_48]
0x140007f09  call    ?ComBstrToString@ComHelper@Util@Sharp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComBSTR@ATL@@@Z; Sharp::Util::ComHelper::ComBstrToString(ATL::CComBSTR const &)
0x140007f0e  nop
0x140007f0f  mov     rdx, rax
0x140007f12  lea     rcx, [rsp+0A8h+var_88]
0x140007f17  call    ?FromXml@CRule@PolicyModel@@SA?AV?$CSharedPtr@VCRule@PolicyModel@@@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CRule::FromXml(std::wstring const &)
0x140007f1c  nop
0x140007f1d  xor     r8d, r8d
0x140007f20  mov     dl, 1
0x140007f22  lea     rcx, [rsp+0A8h+var_48]
0x140007f27  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140007f2c  mov     rax, [rsp+0A8h+var_88]
0x140007f31  mov     rcx, [rax+10h]
0x140007f35  mov     rax, [rcx]
0x140007f38  lea     rdx, [rsp+0A8h+var_68]
0x140007f3d  mov     rax, [rax+8]
0x140007f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f46  nop
0x140007f47  mov     rax, [rsp+0A8h+var_88]
0x140007f4c  mov     rdx, [rax+10h]
0x140007f50  add     rdx, 28h ; '('
0x140007f54  lea     rcx, [rsp+0A8h+bstrString]
0x140007f59  call    ?StringToComBstr@ComHelper@Util@Sharp@@YA?AVCComBSTR@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::ComHelper::StringToComBstr(std::wstring const &)
0x140007f5e  nop
0x140007f5f  mov     rdx, rax
0x140007f62  mov     rcx, rdi
0x140007f65  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x140007f6a  nop
0x140007f6b  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140007f70  call    cs:__imp_SysFreeString
0x140007f76  lea     rdx, [rsp+0A8h+var_68]
0x140007f7b  lea     rcx, [rsp+0A8h+bstrString]
0x140007f80  call    ?StringToComBstr@ComHelper@Util@Sharp@@YA?AVCComBSTR@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::ComHelper::StringToComBstr(std::wstring const &)
0x140007f85  nop
0x140007f86  mov     rdx, rax
0x140007f89  mov     rcx, rsi
0x140007f8c  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x140007f91  nop
0x140007f92  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x140007f97  call    cs:__imp_SysFreeString
0x140007f9d  nop
0x140007f9e  xor     r8d, r8d
0x140007fa1  mov     dl, 1
0x140007fa3  lea     rcx, [rsp+0A8h+var_68]
0x140007fa8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140007fad  nop
0x140007fae  mov     rcx, [rsp+0A8h+var_88]; this
0x140007fb3  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x140007fb8  nop
0x140007fb9  jmp     short loc_140007FC1
0x140007fbb  jmp     short $+2
0x140007fbd  mov     ebx, dword ptr [rsp+0A8h+var_88]
0x140007fc1  mov     eax, ebx
0x140007fc3  mov     rcx, [rsp+0A8h+var_28]
0x140007fcb  xor     rcx, rsp; StackCookie
0x140007fce  call    __security_check_cookie
0x140007fd3  add     rsp, 90h
0x140007fda  pop     rdi
0x140007fdb  pop     rsi
0x140007fdc  pop     rbx
0x140007fdd  retn
```
