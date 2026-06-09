# SetUserDisplayLanguageCore

- ea: `0x18001ff10`
- end: `0x18001fffe`
- name: `SetUserDisplayLanguageCore`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002380`
- `0x180008294`
- `0x18000f35c`
- `0x18000f724`
- `0x180011a98`
- `0x1800190bc`
- `0x180019afc`
- `0x18001de84`
- `0x18001ff10`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18001ff56`
- `ntdll!RtlIsMultiSessionSku` at `0x18001ff56`

## string_xrefs

- `0x18001ff7e`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetUserDisplayLanguageCore(__int64 a1)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 result; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-198h]
  unsigned int v11; // [rsp+20h] [rbp-198h]
  _BYTE v12[40]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v13[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v13,
    (__int64)"SetUserDisplayLanguageCoreActivity");
  v13[0] = &CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::`vftable';
  CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StartActivity((CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *)v13);
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    v3 = -2147024846;
    v4 = 1001;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)v3,
      v10);
    CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *)v13);
    return v3;
  }
  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = 1004;
    goto LABEL_5;
  }
  try
  {
    v6 = std::wstring::wstring((__int64)v12, a1);
    v7 = SetDisplayLanguageInternal(v6, 3u);
    std::wstring::_Tidy_deallocate(v12);
    CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *)v13);
    result = v7;
  }
  catch ( ... )
  {
    v11 = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3F4, v8, v9);
    CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *)v13);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18001ff10  push    rbx
0x18001ff12  sub     rsp, 1B0h
0x18001ff19  mov     rax, cs:__security_cookie
0x18001ff20  xor     rax, rsp
0x18001ff23  mov     [rsp+1B8h+var_18], rax
0x18001ff2b  mov     rbx, rcx
0x18001ff2e  lea     rdx, aSetuserdisplay_0; "SetUserDisplayLanguageCoreActivity"
0x18001ff35  lea     rcx, [rsp+1B8h+var_168]
0x18001ff3a  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ff3f  lea     rax, ??_7SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::`vftable'
0x18001ff46  mov     [rsp+1B8h+var_168], rax
0x18001ff4b  lea     rcx, [rsp+1B8h+var_168]; this
0x18001ff50  call    ?StartActivity@SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StartActivity(void)
0x18001ff55  nop
0x18001ff56  call    cs:__imp_RtlIsMultiSessionSku
0x18001ff5c  test    al, al
0x18001ff5e  jz      short loc_18001FF6C
0x18001ff60  mov     ebx, 80070032h
0x18001ff65  mov     edx, 3E9h
0x18001ff6a  jmp     short loc_18001FF7B
0x18001ff6c  test    rbx, rbx
0x18001ff6f  jnz     short loc_18001FFA1
0x18001ff71  mov     ebx, 80004003h
0x18001ff76  mov     edx, 3ECh; void *
0x18001ff7b  mov     r9d, ebx; char *
0x18001ff7e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001ff85  mov     rcx, [rsp+1B8h]; this
0x18001ff8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff92  nop
0x18001ff93  lea     rcx, [rsp+1B8h+var_168]; this
0x18001ff98  call    ??1SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity(void)
0x18001ff9d  mov     eax, ebx
0x18001ff9f  jmp     short loc_18001FFE5
0x18001ffa1  mov     rdx, rbx
0x18001ffa4  lea     rcx, [rsp+1B8h+var_190]
0x18001ffa9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ffae  nop
0x18001ffaf  mov     edx, 3
0x18001ffb4  mov     rcx, rax
0x18001ffb7  call    ?SetDisplayLanguageInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SET_DISPLAY_LANGUAGE_OPTIONS@Internal@Windows@@@Z; SetDisplayLanguageInternal(std::wstring const &,Windows::Internal::SET_DISPLAY_LANGUAGE_OPTIONS)
0x18001ffbc  mov     ebx, eax
0x18001ffbe  lea     rcx, [rsp+1B8h+var_190]
0x18001ffc3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ffc8  nop
0x18001ffc9  lea     rcx, [rsp+1B8h+var_168]; this
0x18001ffce  call    ??1SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity(void)
0x18001ffd3  mov     eax, ebx
0x18001ffd5  jmp     short loc_18001FFE5
0x18001ffd7  lea     rcx, [rsp+1B8h+var_168]; this
0x18001ffdc  call    ??1SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::~SetUserDisplayLanguageCoreActivity(void)
0x18001ffe1  mov     eax, [rsp+1B8h+var_198]
0x18001ffe5  mov     rcx, [rsp+1B8h+var_18]
0x18001ffed  xor     rcx, rsp; StackCookie
0x18001fff0  call    __security_check_cookie
0x18001fff5  add     rsp, 1B0h
0x18001fffc  pop     rbx
0x18001fffd  retn
```
