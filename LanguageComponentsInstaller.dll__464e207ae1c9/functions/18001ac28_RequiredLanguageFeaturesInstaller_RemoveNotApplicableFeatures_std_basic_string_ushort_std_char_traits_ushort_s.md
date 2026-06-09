# RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> &)

- ea: `0x18001ac28`
- end: `0x18001acc9`
- name: `?RemoveNotApplicableFeatures@RequiredLanguageFeaturesInstaller@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bc70`

## callees

- `0x180013b68`
- `0x180013c74`
- `0x18001ac28`
- `0x180021f74`

## pseudocode

```c
__int64 __fastcall RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // r14
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 result; // rax
  const char *v8; // r9
  _QWORD v9[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v9[0] = a1;
  v9[1] = a2;
  v4 = a3[1];
  v5 = *a3;
  try
  {
    while ( v5 != v4 && !(unsigned __int8)_lambda_1dbbe6b6737489787fb6c14722dc4ffb_::operator()(v9, v5) )
      v5 += 192;
    v6 = v5;
    if ( v5 != v4 )
    {
      while ( 1 )
      {
        v5 += 192;
        if ( v5 == v4 )
          break;
        if ( !(unsigned __int8)_lambda_1dbbe6b6737489787fb6c14722dc4ffb_::operator()(v9, v5) )
        {
          CbsLanguageFeature::operator=(v6, v5);
          v6 += 192;
        }
      }
    }
    result = ((__int64 (__fastcall *)(__int64 *, _QWORD *, __int64, __int64))std::vector<CbsLanguageFeature>::erase)(
               a3,
               v9,
               v6,
               a3[1]);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xC5,
             (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\RequiredLangua"
                           "geComponentsInstaller.h",
             v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001ac28  mov     rax, rsp
0x18001ac2b  mov     [rax+8], rbx
0x18001ac2f  mov     [rax+10h], rsi
0x18001ac33  push    rdi
0x18001ac34  push    r14
0x18001ac36  push    r15
0x18001ac38  sub     rsp, 30h
0x18001ac3c  mov     rsi, r8
0x18001ac3f  mov     [rax-28h], rcx
0x18001ac43  mov     [rax-20h], rdx
0x18001ac47  mov     r14, [r8+8]
0x18001ac4b  mov     rbx, [r8]
0x18001ac4e  mov     r15d, 0C0h
0x18001ac54  cmp     rbx, r14
0x18001ac57  jz      short loc_18001AC6F
0x18001ac59  mov     rdx, rbx
0x18001ac5c  lea     rcx, [rsp+48h+var_28]
0x18001ac61  call    ??R_lambda_1dbbe6b6737489787fb6c14722dc4ffb_@@QEBA_NAEBVCbsLanguageFeature@@@Z; _lambda_1dbbe6b6737489787fb6c14722dc4ffb_::operator()(CbsLanguageFeature const &)
0x18001ac66  test    al, al
0x18001ac68  jnz     short loc_18001AC6F
0x18001ac6a  add     rbx, r15
0x18001ac6d  jmp     short loc_18001AC54
0x18001ac6f  mov     rdi, rbx
0x18001ac72  cmp     rbx, r14
0x18001ac75  jz      short loc_18001ACA0
0x18001ac77  add     rbx, r15
0x18001ac7a  cmp     rbx, r14
0x18001ac7d  jz      short loc_18001ACA0
0x18001ac7f  mov     rdx, rbx
0x18001ac82  lea     rcx, [rsp+48h+var_28]
0x18001ac87  call    ??R_lambda_1dbbe6b6737489787fb6c14722dc4ffb_@@QEBA_NAEBVCbsLanguageFeature@@@Z; _lambda_1dbbe6b6737489787fb6c14722dc4ffb_::operator()(CbsLanguageFeature const &)
0x18001ac8c  test    al, al
0x18001ac8e  jnz     short loc_18001AC77
0x18001ac90  mov     rdx, rbx
0x18001ac93  mov     rcx, rdi
0x18001ac96  call    ??4CbsLanguageFeature@@QEAAAEAV0@$$QEAV0@@Z; CbsLanguageFeature::operator=(CbsLanguageFeature &&)
0x18001ac9b  add     rdi, r15
0x18001ac9e  jmp     short loc_18001AC77
0x18001aca0  mov     r9, [rsi+8]
0x18001aca4  mov     r8, rdi
0x18001aca7  lea     rdx, [rsp+48h+var_28]
0x18001acac  mov     rcx, rsi
0x18001acaf  call    ?erase@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@0@Z; std::vector<CbsLanguageFeature>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>)
0x18001acb4  nop
0x18001acb5  mov     rbx, [rsp+48h+arg_0]
0x18001acba  mov     rsi, [rsp+48h+arg_8]
0x18001acbf  add     rsp, 30h
0x18001acc3  pop     r15
0x18001acc5  pop     r14
0x18001acc7  pop     rdi
0x18001acc8  retn
```
