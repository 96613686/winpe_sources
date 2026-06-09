# SetDisplayLanguageCore

- ea: `0x18001fe10`
- end: `0x18001ff09`
- name: `SetDisplayLanguageCore`
- size: `249`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180002380`
- `0x180008294`
- `0x18000f35c`
- `0x18000f724`
- `0x180011a6c`
- `0x1800190bc`
- `0x180019a3c`
- `0x18001de84`
- `0x18001fe10`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x18001fe5c`
- `ntdll!RtlIsMultiSessionSku` at `0x18001fe5c`

## string_xrefs

- `0x18001fe84`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall SetDisplayLanguageCore(__int64 a1, unsigned int a2)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 v8; // rax
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-198h]
  unsigned int v13; // [rsp+20h] [rbp-198h]
  _BYTE v14[40]; // [rsp+28h] [rbp-190h] BYREF
  _QWORD v15[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "SetDisplayLanguageCoreActivity");
  v15[0] = &CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::`vftable';
  CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StartActivity((CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *)v15);
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    v5 = -2147024846;
    v6 = 979;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)v5,
      v12);
    CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *)v15);
    return v5;
  }
  if ( !a1 )
  {
    v5 = -2147467261;
    v6 = 982;
    goto LABEL_5;
  }
  try
  {
    v8 = std::wstring::wstring(v14, a1);
    v9 = SetDisplayLanguageInternal(v8, a2);
    std::wstring::_Tidy_deallocate(v14);
    CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *)v15);
    result = v9;
  }
  catch ( ... )
  {
    v13 = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x3DC, v10, v11);
    CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity((CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *)v15);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x18001fe10  mov     [rsp+arg_10], rbx
0x18001fe15  push    rdi
0x18001fe16  sub     rsp, 1B0h
0x18001fe1d  mov     rax, cs:__security_cookie
0x18001fe24  xor     rax, rsp
0x18001fe27  mov     [rsp+1B8h+var_18], rax
0x18001fe2f  mov     edi, edx
0x18001fe31  mov     rbx, rcx
0x18001fe34  lea     rdx, aSetdisplaylang_0; "SetDisplayLanguageCoreActivity"
0x18001fe3b  lea     rcx, [rsp+1B8h+var_168]
0x18001fe40  call    ??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fe45  lea     rax, ??_7SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::`vftable'
0x18001fe4c  mov     [rsp+1B8h+var_168], rax
0x18001fe51  lea     rcx, [rsp+1B8h+var_168]; this
0x18001fe56  call    ?StartActivity@SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAAXXZ; CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StartActivity(void)
0x18001fe5b  nop
0x18001fe5c  call    cs:__imp_RtlIsMultiSessionSku
0x18001fe62  test    al, al
0x18001fe64  jz      short loc_18001FE72
0x18001fe66  mov     ebx, 80070032h
0x18001fe6b  mov     edx, 3D3h
0x18001fe70  jmp     short loc_18001FE81
0x18001fe72  test    rbx, rbx
0x18001fe75  jnz     short loc_18001FEA7
0x18001fe77  mov     ebx, 80004003h
0x18001fe7c  mov     edx, 3D6h; void *
0x18001fe81  mov     r9d, ebx; char *
0x18001fe84  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001fe8b  mov     rcx, [rsp+1B8h]; this
0x18001fe93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe98  nop
0x18001fe99  lea     rcx, [rsp+1B8h+var_168]; this
0x18001fe9e  call    ??1SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity(void)
0x18001fea3  mov     eax, ebx
0x18001fea5  jmp     short loc_18001FEE8
0x18001fea7  mov     rdx, rbx
0x18001feaa  lea     rcx, [rsp+1B8h+var_190]
0x18001feaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001feb4  nop
0x18001feb5  mov     edx, edi
0x18001feb7  mov     rcx, rax
0x18001feba  call    ?SetDisplayLanguageInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4SET_DISPLAY_LANGUAGE_OPTIONS@Internal@Windows@@@Z; SetDisplayLanguageInternal(std::wstring const &,Windows::Internal::SET_DISPLAY_LANGUAGE_OPTIONS)
0x18001febf  mov     ebx, eax
0x18001fec1  lea     rcx, [rsp+1B8h+var_190]
0x18001fec6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fecb  nop
0x18001fecc  lea     rcx, [rsp+1B8h+var_168]; this
0x18001fed1  call    ??1SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity(void)
0x18001fed6  mov     eax, ebx
0x18001fed8  jmp     short loc_18001FEE8
0x18001feda  lea     rcx, [rsp+1B8h+var_168]; this
0x18001fedf  call    ??1SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAA@XZ; CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::~SetDisplayLanguageCoreActivity(void)
0x18001fee4  mov     eax, [rsp+1B8h+var_198]
0x18001fee8  mov     rcx, [rsp+1B8h+var_18]
0x18001fef0  xor     rcx, rsp; StackCookie
0x18001fef3  call    __security_check_cookie
0x18001fef8  mov     rbx, [rsp+1B8h+arg_10]
0x18001ff00  add     rsp, 1B0h
0x18001ff07  pop     rdi
0x18001ff08  retn
```
