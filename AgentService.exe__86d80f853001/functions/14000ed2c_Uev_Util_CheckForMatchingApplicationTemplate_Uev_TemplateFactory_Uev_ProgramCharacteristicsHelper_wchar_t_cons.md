# Uev::Util::CheckForMatchingApplicationTemplate<Uev::TemplateFactory,Uev::ProgramCharacteristicsHelper>(wchar_t const *,std::shared_ptr<Uev::Configuration>)

- ea: `0x14000ed2c`
- end: `0x14000ef64`
- name: `??$CheckForMatchingApplicationTemplate@VTemplateFactory@Uev@@VProgramCharacteristicsHelper@2@@Util@Uev@@SA_NPEB_WV?$shared_ptr@VConfiguration@Uev@@@std@@@Z`
- size: `568`
- prototype: `char __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x140014da0`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000ba60`
- `0x14000ed2c`
- `0x14000efc4`
- `0x14000f01c`
- `0x140015e1c`
- `0x1400329bc`
- `0x14009b010`

## string_xrefs

- `0x14000ed5c`: `AgentService.Util::CheckForMatchingApplicationTemplate: Entry( '%s' )`
- `0x14000edc0`: `AgentService.Util::CheckForMatchingApplicationTemplate: File description: '%s'`
- `0x14000eddd`: `AgentService.Util::CheckForMatchingApplicationTemplate: File name: '%s'`
- `0x14000ee08`: `AgentService.Util::CheckForMatchingApplicationTemplate: File version: '%s'`
- `0x14000ee38`: `AgentService.Util::CheckForMatchingApplicationTemplate: Product name: '%s'`
- `0x14000ee5e`: `AgentService.Util::CheckForMatchingApplicationTemplate: Product version: '%s'`
- `0x14000eef1`: `AgentService.Util::CheckForMatchingApplicationTemplate: Exit( '%s' )`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Uev::Util::CheckForMatchingApplicationTemplate<Uev::TemplateFactory,Uev::ProgramCharacteristicsHelper>(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v2; // rdi
  __int64 v4; // r14
  _QWORD *v5; // rbx
  char v6; // si
  volatile signed __int32 *v7; // rbx
  char v9; // [rsp+20h] [rbp-108h]
  _BYTE v11[32]; // [rsp+38h] [rbp-F0h] BYREF
  Uev::UevException *v12; // [rsp+58h] [rbp-D0h] BYREF
  _QWORD v13[3]; // [rsp+60h] [rbp-C8h] BYREF
  _QWORD v14[3]; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v15[16]; // [rsp+A0h] [rbp-88h] BYREF
  _QWORD v16[3]; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD v17[3]; // [rsp+D0h] [rbp-58h] BYREF

  v2 = a2;
  DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: Entry( '%s' )");
  try
  {
    v4 = *v2;
    v5 = operator new(0x50u);
    *v5 = &Uev::TemplateManager::`vftable';
    v5[1] = v4;
    v5[9] = 0;
    Uev::ProgramCharacteristicsHelper::GetProgramCharacteristics(v13, a1);
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: File description: '%s'");
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: File name: '%s'");
    Uev::Version::ToString(v15, v11);
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: File version: '%s'");
    std::wstring::_Tidy_deallocate(v11);
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: Product name: '%s'");
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: Product version: '%s'");
    v6 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v5 + 24LL))(v5, v13);
    v9 = v6;
    std::wstring::_Tidy_deallocate(v17);
    std::wstring::_Tidy_deallocate(v16);
    std::wstring::_Tidy_deallocate(v14);
    std::wstring::_Tidy_deallocate(v13);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v5)(v5, 1);
  }
  catch ( Uev::UevException *v12 )
  {
    std::wstring::wstring(v11, (char *)v12 + 24);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::CheckForMatchingApplicationTemplate: UevException: %s");
    std::wstring::_Tidy_deallocate(v11);
    v6 = v9;
    v2 = a2;
  }
  v4 = *v2;
  v5 = operator new(0x50u);
  *v5 = &Uev::TemplateManager::`vftable';
  v5[1] = v4;
}

```

## disassembly

```asm
0x14000ed2c  mov     [rsp+arg_10], rbx
0x14000ed31  push    rsi
0x14000ed32  push    rdi
0x14000ed33  push    r14
0x14000ed35  sub     rsp, 110h
0x14000ed3c  mov     rax, cs:__security_cookie
0x14000ed43  xor     rax, rsp
0x14000ed46  mov     [rsp+128h+var_28], rax
0x14000ed4e  mov     rdi, rdx
0x14000ed51  mov     rsi, rcx
0x14000ed54  mov     [rsp+128h+var_F8], rdx
0x14000ed59  mov     rdx, rcx
0x14000ed5c  lea     rcx, aAgentserviceUt_24; "AgentService.Util::CheckForMatchingAppl"...
0x14000ed63  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000ed68  mov     [rsp+128h+var_108], 0
0x14000ed6d  mov     r14, [rdi]
0x14000ed70  mov     ecx, 50h ; 'P'; Size
0x14000ed75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ed7a  mov     rbx, rax
0x14000ed7d  lea     rax, ??_7TemplateManager@Uev@@6B@; const Uev::TemplateManager::`vftable'
0x14000ed84  mov     [rbx], rax
0x14000ed87  mov     [rbx+8], r14
0x14000ed8b  mov     qword ptr [rbx+48h], 0
0x14000ed93  mov     [rsp+128h+var_100], rbx
0x14000ed98  mov     rdx, rsi
0x14000ed9b  lea     rcx, [rsp+128h+var_C8]
0x14000eda0  call    ?GetProgramCharacteristics@ProgramCharacteristicsHelper@Uev@@SA?AUProgramCharacteristics@2@PEB_W@Z; Uev::ProgramCharacteristicsHelper::GetProgramCharacteristics(wchar_t const *)
0x14000eda5  nop
0x14000eda6  lea     rdx, [rsp+128h+var_A8]
0x14000edae  cmp     [rsp+128h+var_90], 7
0x14000edb7  cmova   rdx, [rsp+128h+var_A8]
0x14000edc0  lea     rcx, aAgentserviceUt_7; "AgentService.Util::CheckForMatchingAppl"...
0x14000edc7  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000edcc  lea     rdx, [rsp+128h+var_C8]
0x14000edd1  cmp     [rsp+128h+var_B0], 7
0x14000edd7  cmova   rdx, [rsp+128h+var_C8]
0x14000eddd  lea     rcx, aAgentserviceUt_26; "AgentService.Util::CheckForMatchingAppl"...
0x14000ede4  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000ede9  lea     rdx, [rsp+128h+var_F0]
0x14000edee  lea     rcx, [rsp+128h+var_88]
0x14000edf6  call    ?ToString@Version@Uev@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Uev::Version::ToString(void)
0x14000edfb  cmp     qword ptr [rax+18h], 7
0x14000ee00  jbe     short loc_14000EE05
0x14000ee02  mov     rax, [rax]
0x14000ee05  mov     rdx, rax
0x14000ee08  lea     rcx, aAgentserviceUt_29; "AgentService.Util::CheckForMatchingAppl"...
0x14000ee0f  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000ee14  lea     rcx, [rsp+128h+var_F0]
0x14000ee19  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000ee1e  lea     rdx, [rsp+128h+var_78]
0x14000ee26  cmp     [rsp+128h+var_60], 7
0x14000ee2f  cmova   rdx, [rsp+128h+var_78]
0x14000ee38  lea     rcx, aAgentserviceUt_23; "AgentService.Util::CheckForMatchingAppl"...
0x14000ee3f  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000ee44  lea     rdx, [rsp+128h+var_58]
0x14000ee4c  cmp     [rsp+128h+var_40], 7
0x14000ee55  cmova   rdx, [rsp+128h+var_58]
0x14000ee5e  lea     rcx, aAgentserviceUt_10; "AgentService.Util::CheckForMatchingAppl"...
0x14000ee65  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000ee6a  mov     rax, [rbx]
0x14000ee6d  lea     rdx, [rsp+128h+var_C8]
0x14000ee72  mov     rcx, rbx
0x14000ee75  mov     rax, [rax+18h]
0x14000ee79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee7e  mov     sil, al
0x14000ee81  mov     [rsp+128h+var_108], al
0x14000ee85  lea     rcx, [rsp+128h+var_58]
0x14000ee8d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000ee92  lea     rcx, [rsp+128h+var_78]
0x14000ee9a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000ee9f  lea     rcx, [rsp+128h+var_A8]
0x14000eea7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000eeac  lea     rcx, [rsp+128h+var_C8]
0x14000eeb1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000eeb6  nop
0x14000eeb7  test    rbx, rbx
0x14000eeba  jz      short loc_14000EED0
0x14000eebc  mov     rax, [rbx]
0x14000eebf  mov     edx, 1
0x14000eec4  mov     rcx, rbx
0x14000eec7  mov     rax, [rax]
0x14000eeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eecf  nop
0x14000eed0  jmp     short loc_14000EEDC
0x14000eed2  mov     sil, [rsp+128h+var_108]
0x14000eed7  mov     rdi, [rsp+128h+var_F8]
0x14000eedc  lea     rdx, aTrue_0; "True"
0x14000eee3  lea     rax, aFalse_0; "False"
0x14000eeea  test    sil, sil
0x14000eeed  cmovz   rdx, rax
0x14000eef1  lea     rcx, aAgentserviceUt_0; "AgentService.Util::CheckForMatchingAppl"...
0x14000eef8  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14000eefd  nop
0x14000eefe  mov     rbx, [rdi+8]
0x14000ef02  test    rbx, rbx
0x14000ef05  jz      short loc_14000EF3D
0x14000ef07  or      edi, 0FFFFFFFFh
0x14000ef0a  mov     eax, edi
0x14000ef0c  lock xadd [rbx+8], eax
0x14000ef11  add     eax, edi
0x14000ef13  jnz     short loc_14000EF3D
0x14000ef15  mov     rax, [rbx]
0x14000ef18  mov     rcx, rbx
0x14000ef1b  mov     rax, [rax]
0x14000ef1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef23  mov     edx, edi
0x14000ef25  lock xadd [rbx+0Ch], edx
0x14000ef2a  add     edx, edi
0x14000ef2c  jnz     short loc_14000EF3D
0x14000ef2e  mov     rdx, [rbx]
0x14000ef31  mov     rcx, rbx
0x14000ef34  mov     rax, [rdx+8]
0x14000ef38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef3d  mov     al, sil
0x14000ef40  mov     rcx, [rsp+128h+var_28]
0x14000ef48  xor     rcx, rsp; StackCookie
0x14000ef4b  call    __security_check_cookie
0x14000ef50  mov     rbx, [rsp+128h+arg_10]
0x14000ef58  add     rsp, 110h
0x14000ef5f  pop     r14
0x14000ef61  pop     rdi
0x14000ef62  pop     rsi
0x14000ef63  retn
```
