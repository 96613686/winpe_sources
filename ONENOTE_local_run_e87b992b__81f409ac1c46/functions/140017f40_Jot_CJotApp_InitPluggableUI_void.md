# Jot::CJotApp::InitPluggableUI(void)

- ea: `0x140017f40`
- end: `0x14001812c`
- name: `?InitPluggableUI@CJotApp@Jot@@AEAAXXZ`
- size: `492`
- prototype: `void __fastcall(Jot::CJotApp *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400121c8`

## callees

- `0x140017f40`
- `0x140056ac0`
- `0x140079970`
- `0x140095f1c`
- `0x1400c8a74`

## import_xrefs

- `onmain!?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@AEBVErrorData@12@@Z` at `0x1400180ce`
- `onmain!?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@AEBVErrorData@12@@Z` at `0x1400180ce`
- `onmain!?Init@CLangConfig@MsoCF@@QEAAXXZ` at `0x140017f77`
- `onmain!?Init@CLangConfig@MsoCF@@QEAAXXZ` at `0x140017f77`
- `onmain!?FixLcidUI@CLangConfig@MsoCF@@QEAAXK@Z` at `0x1400180f3`
- `onmain!?FixLcidUI@CLangConfig@MsoCF@@QEAAXK@Z` at `0x1400180f3`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140017f6e`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140017f7d`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400180e6`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400180f9`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140017f6e`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140017f7d`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400180e6`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400180f9`
- `Mso30Win32Client!__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z` at `0x140017fec`
- `Mso30Win32Client!__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z` at `0x140017fec`
- `Mso30Win32Client!__imp_MsoSetLocale` at `0x140018102`
- `Mso30Win32Client!__imp_MsoSetLocale` at `0x140018102`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x14001802a`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x14001802a`
- `Mso30Win32Client!__imp_?MsoLoadResourceLibrary@Resources@Mso@@YAPEAUHINSTANCE__@@PEB_W@Z` at `0x140017ffa`
- `Mso30Win32Client!__imp_?MsoLoadResourceLibrary@Resources@Mso@@YAPEAUHINSTANCE__@@PEB_W@Z` at `0x140017ffa`
- `Mso30Win32Client!__imp_?MsoGimmeLocalizedLibrary@@YAPEAUHINSTANCE__@@HPEAKKPEA_WHK@Z` at `0x140017faa`
- `Mso30Win32Client!__imp_?MsoGimmeLocalizedLibrary@@YAPEAUHINSTANCE__@@HPEAKKPEA_WHK@Z` at `0x140017faa`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14001805d`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14001805d`
- `Mso20Win32Client!__imp_MsoParseUIntWz` at `0x140018041`
- `Mso20Win32Client!__imp_MsoParseUIntWz` at `0x140018041`

## pseudocode

```c
void __fastcall Jot::CJotApp::InitPluggableUI(Jot::CJotApp *this)
{
  MsoCF::CLangConfig *v2; // rax
  HINSTANCE v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  const wchar_t *v6; // rdx
  __int64 v7; // rcx
  bool v8; // al
  unsigned int v9; // eax
  const struct Jot::Logging::ErrorData *v10; // r9
  MsoCF::CLangConfig *v11; // rax
  __int64 v12; // rax
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-CCh] BYREF
  const char *v15; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-B0h]
  char v18; // [rsp+58h] [rbp-A8h]
  _BYTE v19[32]; // [rsp+60h] [rbp-A0h] BYREF
  char v20; // [rsp+80h] [rbp-80h]
  unsigned int v21; // [rsp+88h] [rbp-78h]
  char v22; // [rsp+8Ch] [rbp-74h]
  char v23; // [rsp+94h] [rbp-6Ch]
  _BYTE v24[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v25[24]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t v26[264]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = (MsoCF::CLangConfig *)MsoCF::CLangConfig::Instance();
  MsoCF::CLangConfig::Init(v2);
  v14 = *(_DWORD *)(MsoCF::CLangConfig::Instance() + 24);
  v3 = MsoGimmeLocalizedLibrary(851970, &v14, 0, 0, 0, 0x8007u);
  *((_QWORD *)this + 62) = v3;
  if ( !v3 )
  {
    Ofc::CAbortException::ThrowTag(v4, 42849886);
    __debugbreak();
  }
  v5 = (_QWORD *)((char *)this + 504);
  if ( MsoFGimmeFileEx(851971, 0, 0, v26, 260, 0x8F1Fu) )
    *v5 = Mso::Resources::MsoLoadResourceLibrary((Mso::Resources *)v26, v6);
  if ( !*v5 )
  {
    Ofc::CAbortException::ThrowTag(v7, 42849888);
    __debugbreak();
  }
  MsoFLoadWz(*((_QWORD *)this + 62), 280693069, v25, 10);
  v13 = 0;
  MsoParseUIntWz(v25, &v13);
  if ( byte_14025EB70 < 0 )
    v8 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_14025EB70);
  else
    v8 = byte_14025EB70 != 0;
  if ( v8 )
  {
    if ( v13 != v14 )
    {
      v21 = v13;
      v16[0] = &Jot::Logging::ErrorData::`vftable'{for `Mso::Logging::IStructuredTrace'};
      v17 = v14;
      v16[1] = &Jot::Logging::ErrorData::`vftable'{for `Mso::Telemetry::IDataField'};
      v18 = 0;
      v20 = 0;
      v22 = 1;
      v23 = 0;
      v15 = "InitPluggableUILcidMismatch";
      v9 = Office::OneNote::EventName(v24, &v15);
      Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x1E043455, v9, (const struct Mso::Telemetry::EventName *)v16, v10);
      if ( v20 )
        std::string::~string(v19);
    }
  }
  else
  {
    v11 = (MsoCF::CLangConfig *)MsoCF::CLangConfig::Instance();
    MsoCF::CLangConfig::FixLcidUI(v11, v13);
  }
  v12 = MsoCF::CLangConfig::Instance();
  MsoSetLocale(*(unsigned int *)(v12 + 24));
}

```

## disassembly

```asm
0x140017f40  mov     [rsp-8+arg_8], rbx
0x140017f45  mov     [rsp-8+arg_10], rdi
0x140017f4a  push    rbp
0x140017f4b  lea     rbp, [rsp-1E0h]
0x140017f53  sub     rsp, 2E0h
0x140017f5a  mov     rax, cs:__security_cookie
0x140017f61  xor     rax, rsp
0x140017f64  mov     [rbp+1E0h+var_10], rax
0x140017f6b  mov     rdi, rcx
0x140017f6e  call    cs:__imp_?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ; MsoCF::CLangConfig::Instance(void)
0x140017f74  mov     rcx, rax
0x140017f77  call    cs:__imp_?Init@CLangConfig@MsoCF@@QEAAXXZ; MsoCF::CLangConfig::Init(void)
0x140017f7d  call    cs:__imp_?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ; MsoCF::CLangConfig::Instance(void)
0x140017f83  mov     [rsp+2E0h+var_2B8], 8007h
0x140017f8b  xor     r9d, r9d
0x140017f8e  xor     r8d, r8d
0x140017f91  mov     [rsp+2E0h+var_2C0], 0
0x140017f99  mov     ecx, 0D0002h
0x140017f9e  mov     edx, [rax+18h]
0x140017fa1  mov     [rsp+2E0h+var_2AC], edx
0x140017fa5  lea     rdx, [rsp+2E0h+var_2AC]
0x140017faa  call    cs:__imp_?MsoGimmeLocalizedLibrary@@YAPEAUHINSTANCE__@@HPEAKKPEA_WHK@Z; MsoGimmeLocalizedLibrary(int,ulong *,ulong,wchar_t *,int,ulong)
0x140017fb0  mov     [rdi+1F0h], rax
0x140017fb7  test    rax, rax
0x140017fba  jnz     short loc_140017FC7
0x140017fbc  mov     edx, 28DD65Eh
0x140017fc1  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x140017fc6  int     3; Trap to Debugger
0x140017fc7  mov     [rsp+2E0h+var_2B8], 8F1Fh
0x140017fcf  lea     r9, [rbp+1E0h+var_220]
0x140017fd3  xor     r8d, r8d
0x140017fd6  mov     [rsp+2E0h+var_2C0], 104h
0x140017fde  xor     edx, edx
0x140017fe0  lea     rbx, [rdi+1F8h]
0x140017fe7  mov     ecx, 0D0003h
0x140017fec  call    cs:__imp_?MsoFGimmeFileEx@@YAHHKPEB_WPEA_WHK@Z; MsoFGimmeFileEx(int,ulong,wchar_t const *,wchar_t *,int,ulong)
0x140017ff2  test    eax, eax
0x140017ff4  jz      short loc_140018003
0x140017ff6  lea     rcx, [rbp+1E0h+var_220]
0x140017ffa  call    cs:__imp_?MsoLoadResourceLibrary@Resources@Mso@@YAPEAUHINSTANCE__@@PEB_W@Z; Mso::Resources::MsoLoadResourceLibrary(wchar_t const *)
0x140018000  mov     [rbx], rax
0x140018003  cmp     qword ptr [rbx], 0
0x140018007  jnz     short loc_140018014
0x140018009  mov     edx, 28DD660h
0x14001800e  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x140018013  int     3; Trap to Debugger
0x140018014  mov     rcx, [rdi+1F0h]
0x14001801b  lea     r8, [rbp+1E0h+var_238]
0x14001801f  mov     r9d, 0Ah
0x140018025  mov     edx, 10BB094Dh
0x14001802a  call    cs:__imp_MsoFLoadWz
0x140018030  lea     rdx, [rsp+2E0h+var_2B0]
0x140018035  mov     [rsp+2E0h+var_2B0], 0
0x14001803d  lea     rcx, [rbp+1E0h+var_238]
0x140018041  call    cs:__imp_MsoParseUIntWz
0x140018047  mov     al, cs:byte_14025EB70
0x14001804d  test    al, al
0x14001804f  js      short loc_140018056
0x140018051  setnz   al
0x140018054  jmp     short loc_140018063
0x140018056  lea     rcx, byte_14025EB70
0x14001805d  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x140018063  test    al, al
0x140018065  jz      short loc_1400180E6
0x140018067  mov     eax, [rsp+2E0h+var_2B0]
0x14001806b  mov     ecx, [rsp+2E0h+var_2AC]
0x14001806f  cmp     eax, ecx
0x140018071  jz      loc_1400180F9
0x140018077  lea     rdx, ??_7ErrorData@Logging@Jot@@6BIStructuredTrace@1Mso@@@; const Jot::Logging::ErrorData::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x14001807e  mov     [rbp+1E0h+var_258], eax
0x140018081  mov     [rsp+2E0h+var_2A0], rdx
0x140018086  lea     rax, aInitpluggableu; "InitPluggableUILcidMismatch"
0x14001808d  lea     rdx, ??_7ErrorData@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::ErrorData::`vftable'{for `Mso::Telemetry::IDataField'}
0x140018094  mov     [rsp+2E0h+var_290], ecx
0x140018098  mov     [rsp+2E0h+var_298], rdx
0x14001809d  lea     rcx, [rbp+1E0h+var_248]
0x1400180a1  lea     rdx, [rsp+2E0h+var_2A8]
0x1400180a6  mov     [rsp+2E0h+var_288], 0
0x1400180ab  mov     [rbp+1E0h+var_260], 0
0x1400180af  mov     [rbp+1E0h+var_254], 1
0x1400180b3  mov     [rbp+1E0h+var_24C], 0
0x1400180b7  mov     [rsp+2E0h+var_2A8], rax
0x1400180bc  call    ?EventName@OneNote@Office@@YA?AU0Telemetry@Mso@@AEBUValidEventName@34@@Z; Office::OneNote::EventName(Mso::Telemetry::ValidEventName const &)
0x1400180c1  lea     r8, [rsp+2E0h+var_2A0]
0x1400180c6  mov     rdx, rax
0x1400180c9  mov     ecx, 1E043455h
0x1400180ce  call    cs:__imp_?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@AEBVErrorData@12@@Z; Jot::Logging::LogUnexpectedTag(ulong,Mso::Telemetry::EventName const &,Jot::Logging::ErrorData const &)
0x1400180d4  cmp     [rbp+1E0h+var_260], 0
0x1400180d8  jz      short loc_1400180F9
0x1400180da  lea     rcx, [rsp+2E0h+var_280]
0x1400180df  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400180e4  jmp     short loc_1400180F9
0x1400180e6  call    cs:__imp_?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ; MsoCF::CLangConfig::Instance(void)
0x1400180ec  mov     edx, [rsp+2E0h+var_2B0]
0x1400180f0  mov     rcx, rax
0x1400180f3  call    cs:__imp_?FixLcidUI@CLangConfig@MsoCF@@QEAAXK@Z; MsoCF::CLangConfig::FixLcidUI(ulong)
0x1400180f9  call    cs:__imp_?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ; MsoCF::CLangConfig::Instance(void)
0x1400180ff  mov     ecx, [rax+18h]
0x140018102  call    cs:__imp_MsoSetLocale
0x140018108  mov     rcx, [rbp+1E0h+var_10]
0x14001810f  xor     rcx, rsp; StackCookie
0x140018112  call    __security_check_cookie
0x140018117  lea     r11, [rsp+2E0h+var_s0]
0x14001811f  mov     rbx, [r11+18h]
0x140018123  mov     rdi, [r11+20h]
0x140018127  mov     rsp, r11
0x14001812a  pop     rbp
0x14001812b  retn
```
