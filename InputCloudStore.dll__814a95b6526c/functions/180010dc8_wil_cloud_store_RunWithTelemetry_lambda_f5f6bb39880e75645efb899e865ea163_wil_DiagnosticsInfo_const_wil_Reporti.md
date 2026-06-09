# wil::cloud_store::RunWithTelemetry<_lambda_f5f6bb39880e75645efb899e865ea163_>(wil::DiagnosticsInfo const &,wil::ReportingKind,_lambda_f5f6bb39880e75645efb899e865ea163_ &&)

- ea: `0x180010dc8`
- end: `0x180010e6c`
- name: `??$RunWithTelemetry@V_lambda_f5f6bb39880e75645efb899e865ea163_@@@cloud_store@wil@@CA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@AEBUDiagnosticsInfo@1@W4ReportingKind@1@$$QEAV_lambda_f5f6bb39880e75645efb899e865ea163_@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, const struct DiagnosticsInfo *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180015a74`

## callees

- `0x180003560`
- `0x180010094`
- `0x180010dc8`
- `0x18001213c`
- `0x180019b90`
- `0x1800210c0`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::RunWithTelemetry<_lambda_f5f6bb39880e75645efb899e865ea163_>(
        __int64 a1,
        const struct DiagnosticsInfo *a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edx
  _QWORD v8[3]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD *v9; // [rsp+58h] [rbp-30h] BYREF
  unsigned __int64 v10; // [rsp+70h] [rbp-18h]

  v8[0] = *a4;
  v8[1] = a4[1];
  v8[2] = a4[2];
  std::string::string(&v9, a4 + 3);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl'::`2'::impl);
  wil::details::RunFeatureDispatch<_lambda_b5d880d1204a557b87a027d71d0466b6_ &>(a1, v6, a2, (__int64)v8);
  if ( v10 > 0xF )
    std::_Deallocate<16>(v9, v10 + 1);
  return a1;
}

```

## disassembly

```asm
0x180010dc8  mov     r11, rsp
0x180010dcb  mov     [r11+10h], rbx
0x180010dcf  push    rdi
0x180010dd0  sub     rsp, 80h
0x180010dd7  mov     rax, cs:__security_cookie
0x180010dde  xor     rax, rsp
0x180010de1  mov     [rsp+88h+var_10], rax
0x180010de6  mov     rbx, rdx
0x180010de9  mov     rdi, rcx
0x180010dec  mov     [rsp+88h+var_50], rcx
0x180010df1  mov     rax, [r9]
0x180010df4  mov     [r11-48h], rax
0x180010df8  mov     rax, [r9+8]
0x180010dfc  mov     [r11-40h], rax
0x180010e00  mov     rax, [r9+10h]
0x180010e04  mov     [r11-38h], rax
0x180010e08  lea     rdx, [r9+18h]
0x180010e0c  lea     rcx, [r11-30h]
0x180010e10  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180010e15  nop
0x180010e16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudStore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore> `wil::Feature<__WilFeatureTraits_Feature_CloudStore>::GetImpl(void)'::`2'::impl
0x180010e1d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudStore@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudStore>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010e22  lea     r9, [rsp+88h+var_48]
0x180010e27  mov     r8, rbx
0x180010e2a  mov     rcx, rdi
0x180010e2d  call    ??$RunFeatureDispatch@AEAV_lambda_b5d880d1204a557b87a027d71d0466b6_@@@details@wil@@YA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@IAEBUDiagnosticsInfo@1@AEAV_lambda_b5d880d1204a557b87a027d71d0466b6_@@Utag_return_other@01@@Z; wil::details::RunFeatureDispatch<_lambda_b5d880d1204a557b87a027d71d0466b6_ &>(uint,wil::DiagnosticsInfo const &,_lambda_b5d880d1204a557b87a027d71d0466b6_ &,wil::details::tag_return_other)
0x180010e32  nop
0x180010e33  mov     rdx, [rsp+88h+var_18]
0x180010e38  cmp     rdx, 0Fh
0x180010e3c  jbe     short loc_180010E4B
0x180010e3e  inc     rdx
0x180010e41  mov     rcx, [rsp+88h+var_30]
0x180010e46  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010e4b  mov     rax, rdi
0x180010e4e  mov     rcx, [rsp+88h+var_10]
0x180010e53  xor     rcx, rsp; StackCookie
0x180010e56  call    __security_check_cookie
0x180010e5b  mov     rbx, [rsp+88h+arg_8]
0x180010e63  add     rsp, 80h
0x180010e6a  pop     rdi
0x180010e6b  retn
```
