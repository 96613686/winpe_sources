# wil::cloud_store::load_internal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store_load_options,Windows::Data::Platform::ItemReference<Windows::Data::Accessibility::EyeControl::SyncedSettings> const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180015a74`
- end: `0x180015b3a`
- name: `??$load_internal@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@W4cloud_store_load_options@1@PEBU?$ItemReference@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@Platform@Data@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180015598`

## callees

- `0x180003560`
- `0x180010dc8`
- `0x18001213c`
- `0x180015a74`
- `0x180019b90`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::load_internal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-31h] BYREF
  __int64 v9; // [rsp+30h] [rbp-21h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-19h] BYREF
  __int16 v11; // [rsp+50h] [rbp-1h]
  __int64 v12; // [rsp+58h] [rbp+7h]
  _QWORD v13[3]; // [rsp+60h] [rbp+Fh] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+27h] BYREF
  unsigned __int64 v15; // [rsp+90h] [rbp+3Fh]
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+57h]

  v12 = a2;
  v9 = 0;
  v8 = 2;
  v13[0] = a1;
  v13[1] = &v8;
  v13[2] = &v9;
  std::string::string(&v14, a5);
  v10[0] = retaddr;
  v10[1] = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
  v10[2] = "Load";
  v11 = 1300;
  wil::cloud_store::RunWithTelemetry<_lambda_f5f6bb39880e75645efb899e865ea163_>(a2, v10, v6, v13);
  if ( v15 > 0xF )
    std::_Deallocate<16>(v14, v15 + 1);
  return a2;
}

```

## disassembly

```asm
0x180015a74  mov     [rsp-8+arg_0], rbx
0x180015a79  push    rbp
0x180015a7a  lea     rbp, [rsp-4Fh]
0x180015a7f  sub     rsp, 0A0h
0x180015a86  mov     rax, cs:__security_cookie
0x180015a8d  xor     rax, rsp
0x180015a90  mov     [rbp+4Fh+var_8], rax
0x180015a94  mov     rbx, rdx
0x180015a97  mov     [rbp+4Fh+var_48], rdx
0x180015a9b  mov     rdx, [rbp+4Fh+arg_20]
0x180015a9f  mov     [rbp+4Fh+var_70], 0
0x180015aa7  mov     [rbp+4Fh+var_80], 2
0x180015aae  mov     [rbp+4Fh+var_40], rcx
0x180015ab2  lea     rax, [rbp+4Fh+var_80]
0x180015ab6  mov     [rbp+4Fh+var_38], rax
0x180015aba  lea     rax, [rbp+4Fh+var_70]
0x180015abe  mov     [rbp+4Fh+var_30], rax
0x180015ac2  lea     rcx, [rbp+4Fh+var_28]
0x180015ac6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180015acb  nop
0x180015acc  mov     rax, [rbp+57h]
0x180015ad0  mov     [rbp+4Fh+var_68], rax
0x180015ad4  lea     rax, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180015adb  mov     [rbp+4Fh+var_60], rax
0x180015adf  lea     rax, aLoad; "Load"
0x180015ae6  mov     [rbp+4Fh+var_58], rax
0x180015aea  mov     eax, 514h
0x180015aef  mov     [rbp+4Fh+var_50], ax
0x180015af3  lea     r9, [rbp+4Fh+var_40]
0x180015af7  lea     rdx, [rbp+4Fh+var_68]
0x180015afb  mov     rcx, rbx
0x180015afe  call    ??$RunWithTelemetry@V_lambda_f5f6bb39880e75645efb899e865ea163_@@@cloud_store@wil@@CA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@AEBUDiagnosticsInfo@1@W4ReportingKind@1@$$QEAV_lambda_f5f6bb39880e75645efb899e865ea163_@@@Z; wil::cloud_store::RunWithTelemetry<_lambda_f5f6bb39880e75645efb899e865ea163_>(wil::DiagnosticsInfo const &,wil::ReportingKind,_lambda_f5f6bb39880e75645efb899e865ea163_ &&)
0x180015b03  nop
0x180015b04  mov     rdx, [rbp+4Fh+var_10]
0x180015b08  cmp     rdx, 0Fh
0x180015b0c  jbe     short loc_180015B1A
0x180015b0e  inc     rdx
0x180015b11  mov     rcx, [rbp+4Fh+var_28]
0x180015b15  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015b1a  mov     rax, rbx
0x180015b1d  mov     rcx, [rbp+4Fh+var_8]
0x180015b21  xor     rcx, rsp; StackCookie
0x180015b24  call    __security_check_cookie
0x180015b29  mov     rbx, [rsp+0A0h+arg_0]
0x180015b31  add     rsp, 0A0h
0x180015b38  pop     rbp
0x180015b39  retn
```
