# wil::cloud_store::save<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,wil::cloud_store_save_options,unsigned __int64,char const *)

- ea: `0x180017618`
- end: `0x1800176ef`
- name: `??$save@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001d208`

## callees

- `0x180003560`
- `0x1800107dc`
- `0x18001213c`
- `0x180017618`
- `0x180019bd8`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::save<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-69h] BYREF
  __int64 v9; // [rsp+28h] [rbp-61h] BYREF
  __int64 v10; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-51h] BYREF
  __int16 v12; // [rsp+50h] [rbp-39h]
  _QWORD v13[6]; // [rsp+58h] [rbp-31h] BYREF
  _QWORD *v14[3]; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int64 v15; // [rsp+A0h] [rbp+17h]
  _UNKNOWN *retaddr; // [rsp+D8h] [rbp+4Fh]

  std::string::string(v14, &qword_180033B90);
  v13[0] = a1;
  v13[1] = a3;
  v13[2] = &v9;
  v13[3] = &v8;
  v13[4] = &v10;
  v13[5] = v14;
  v11[0] = retaddr;
  v11[1] = "onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h";
  v11[2] = "Save";
  v12 = 1434;
  ((void (__fastcall *)(__int64, _QWORD *, __int64, _QWORD *, _DWORD, _QWORD, _QWORD))wil::cloud_store::RunWithTelemetry<_lambda_71e851bdf04a99fc5621a939bf475e0b_>)(
    a2,
    v11,
    v6,
    v13,
    0,
    0,
    0);
  if ( v15 > 0xF )
    std::_Deallocate<16>(v14[0], v15 + 1);
  return a2;
}

```

## disassembly

```asm
0x180017618  push    rbp
0x18001761a  push    rbx
0x18001761b  push    rsi
0x18001761c  push    rdi
0x18001761d  lea     rbp, [rsp-2Fh]
0x180017622  sub     rsp, 0B8h
0x180017629  mov     rax, cs:__security_cookie
0x180017630  xor     rax, rsp
0x180017633  mov     [rbp+47h+var_28], rax
0x180017637  mov     rdi, r8
0x18001763a  mov     rsi, rdx
0x18001763d  mov     rbx, rcx
0x180017640  lea     rdx, qword_180033B90
0x180017647  lea     rcx, [rbp+47h+var_48]
0x18001764b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180017650  nop
0x180017651  xor     eax, eax
0x180017653  mov     [rbp+47h+var_A0], rax
0x180017657  mov     [rbp+47h+var_B0], eax
0x18001765a  mov     [rbp+47h+var_A8], rax
0x18001765e  mov     [rbp+47h+var_78], rbx
0x180017662  mov     [rbp+47h+var_70], rdi
0x180017666  lea     rax, [rbp+47h+var_A8]
0x18001766a  mov     [rbp+47h+var_68], rax
0x18001766e  lea     rax, [rbp+47h+var_B0]
0x180017672  mov     [rbp+47h+var_60], rax
0x180017676  lea     rax, [rbp+47h+var_A0]
0x18001767a  mov     [rbp+47h+var_58], rax
0x18001767e  lea     rax, [rbp+47h+var_48]
0x180017682  mov     [rbp+47h+var_50], rax
0x180017686  mov     rax, [rbp+4Fh]
0x18001768a  mov     [rbp+47h+var_98], rax
0x18001768e  lea     rax, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180017695  mov     [rbp+47h+var_90], rax
0x180017699  lea     rax, aSave; "Save"
0x1800176a0  mov     [rbp+47h+var_88], rax
0x1800176a4  mov     eax, 59Ah
0x1800176a9  mov     [rbp+47h+var_80], ax
0x1800176ad  lea     r9, [rbp+47h+var_78]
0x1800176b1  lea     rdx, [rbp+47h+var_98]
0x1800176b5  mov     rcx, rsi
0x1800176b8  call    ??$RunWithTelemetry@V_lambda_71e851bdf04a99fc5621a939bf475e0b_@@@cloud_store@wil@@CA?AVcloud_store_save_result@1@AEBUDiagnosticsInfo@1@W4ReportingKind@1@$$QEAV_lambda_71e851bdf04a99fc5621a939bf475e0b_@@@Z; wil::cloud_store::RunWithTelemetry<_lambda_71e851bdf04a99fc5621a939bf475e0b_>(wil::DiagnosticsInfo const &,wil::ReportingKind,_lambda_71e851bdf04a99fc5621a939bf475e0b_ &&)
0x1800176bd  nop
0x1800176be  mov     rdx, [rbp+47h+var_30]
0x1800176c2  cmp     rdx, 0Fh
0x1800176c6  jbe     short loc_1800176D4
0x1800176c8  inc     rdx
0x1800176cb  mov     rcx, [rbp+47h+var_48]
0x1800176cf  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800176d4  mov     rax, rsi
0x1800176d7  mov     rcx, [rbp+47h+var_28]
0x1800176db  xor     rcx, rsp; StackCookie
0x1800176de  call    __security_check_cookie
0x1800176e3  add     rsp, 0B8h
0x1800176ea  pop     rdi
0x1800176eb  pop     rsi
0x1800176ec  pop     rbx
0x1800176ed  pop     rbp
0x1800176ee  retn
```
