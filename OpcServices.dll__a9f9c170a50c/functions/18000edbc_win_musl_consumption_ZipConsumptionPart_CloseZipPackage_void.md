# win_musl::consumption::ZipConsumptionPart::CloseZipPackage(void)

- ea: `0x18000edbc`
- end: `0x18000ef1f`
- name: `?CloseZipPackage@ZipConsumptionPart@consumption@win_musl@@QEAAXXZ`
- size: `355`
- prototype: `void __fastcall(win_musl::consumption::ZipConsumptionPart *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000ecd8`

## callees

- `0x18000edbc`
- `0x18000ef28`
- `0x18000f008`
- `0x180015114`
- `0x18001a810`
- `0x1800460f0`
- `0x1800517a0`
- `0x1800654b0`
- `0x1800696e4`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ee53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000edfc`

## string_xrefs

- `0x18000ee88`: `The interleaved part is incomplete. %{part}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall win_musl::consumption::ZipConsumptionPart::CloseZipPackage(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v3; // dl
  win_dox *DebugInfo_high; // rcx
  __int64 v6; // rbx
  win_musl::Formatter *v7; // rax
  struct win_musl::TStringEllipseBase *v8; // rax
  _BYTE v9[40]; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v10[40]; // [rsp+78h] [rbp-140h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A0h] [rbp-118h] BYREF
  _BYTE v12[96]; // [rsp+140h] [rbp-78h] BYREF

  v2 = this + 4;
  EnterCriticalSection(this + 4);
  DebugInfo_high = (win_dox *)HIDWORD(v2[1].DebugInfo);
  HIDWORD(v2[1].DebugInfo) = (_DWORD)DebugInfo_high + 1;
  if ( !(_DWORD)DebugInfo_high )
    LODWORD(v2[1].DebugInfo) = GetCurrentThreadId();
  LOBYTE(DebugInfo_high) = this[5].OwningThread;
  win_dox::ThrowIfFailed(DebugInfo_high, v3);
  if ( win_musl::consumption::ZipConsumptionPart::HasCompleteSequence((win_musl::consumption::ZipConsumptionPart *)this) )
  {
    if ( !BYTE1(this[3].SpinCount) )
      win_musl::consumption::ZipConsumptionPart::AddPartToReceiver((win_musl::consumption::ZipConsumptionPart *)this, 0);
  }
  else if ( !*(_BYTE *)(this[2].SpinCount + 57) )
  {
    std::wstring::wstring(v9, L"The interleaved part is incomplete. %{part}");
    v6 = win_musl::Formatter::Formatter(v12, v9);
    std::wstring::wstring(v10, L"part");
    v7 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v6, v10, &this->OwningThread);
    v8 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x10Eu,
      0x80510017,
      v8);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( HIDWORD(v2[1].DebugInfo)-- == 1 )
    LODWORD(v2[1].DebugInfo) = 0;
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18000edbc  mov     rax, rsp
0x18000edbf  push    rdi
0x18000edc0  sub     rsp, 1B0h
0x18000edc7  mov     [rsp+1B8h+var_170], 0FFFFFFFFFFFFFFFEh
0x18000edd0  mov     [rax+10h], rbx
0x18000edd4  mov     [rax+18h], rsi
0x18000edd8  mov     rax, cs:__security_cookie
0x18000eddf  xor     rax, rsp
0x18000ede2  mov     [rsp+1B8h+var_18], rax
0x18000edea  mov     rdi, rcx
0x18000eded  lea     rbx, [rcx+0A0h]
0x18000edf4  mov     [rsp+1B8h+var_178], rbx
0x18000edf9  mov     rcx, rbx; lpCriticalSection
0x18000edfc  call    cs:__imp_EnterCriticalSection
0x18000ee02  mov     ecx, [rbx+2Ch]
0x18000ee05  lea     eax, [rcx+1]
0x18000ee08  mov     [rbx+2Ch], eax
0x18000ee0b  test    ecx, ecx
0x18000ee0d  jnz     short loc_18000EE18
0x18000ee0f  call    cs:__imp_GetCurrentThreadId
0x18000ee15  mov     [rbx+28h], eax
0x18000ee18  mov     cl, [rdi+0D8h]; this
0x18000ee1e  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18000ee23  mov     rcx, rdi; this
0x18000ee26  call    ?HasCompleteSequence@ZipConsumptionPart@consumption@win_musl@@AEBA_NXZ; win_musl::consumption::ZipConsumptionPart::HasCompleteSequence(void)
0x18000ee2b  test    al, al
0x18000ee2d  jz      short loc_18000EE7E
0x18000ee2f  cmp     byte ptr [rdi+99h], 0
0x18000ee36  jnz     short loc_18000EE43
0x18000ee38  xor     edx, edx; struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *
0x18000ee3a  mov     rcx, rdi; this
0x18000ee3d  call    ?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x18000ee42  nop
0x18000ee43  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x18000ee47  jnz     short loc_18000EE50
0x18000ee49  mov     dword ptr [rbx+28h], 0
0x18000ee50  mov     rcx, rbx; lpCriticalSection
0x18000ee53  call    cs:__imp_LeaveCriticalSection
0x18000ee59  mov     rcx, [rsp+1B8h+var_18]
0x18000ee61  xor     rcx, rsp; StackCookie
0x18000ee64  call    __security_check_cookie
0x18000ee69  lea     r11, [rsp+1B8h+var_8]
0x18000ee71  mov     rbx, [r11+18h]
0x18000ee75  mov     rsi, [r11+20h]
0x18000ee79  mov     rsp, r11
0x18000ee7c  pop     rdi
0x18000ee7d  retn
0x18000ee7e  mov     rax, [rdi+70h]
0x18000ee82  cmp     byte ptr [rax+39h], 0
0x18000ee86  jnz     short loc_18000EE43
0x18000ee88  lea     rdx, aTheInterleaved; "The interleaved part is incomplete. %{p"...
0x18000ee8f  lea     rcx, [rsp+1B8h+var_168]
0x18000ee94  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18000ee99  nop
0x18000ee9a  lea     rdx, [rsp+1B8h+var_168]
0x18000ee9f  lea     rcx, [rsp+1B8h+var_78]
0x18000eea7  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18000eeac  mov     rbx, rax
0x18000eeaf  lea     rdx, aPart_0; "part"
0x18000eeb6  lea     rcx, [rsp+1B8h+var_140]
0x18000eebb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18000eec0  nop
0x18000eec1  lea     r8, [rdi+10h]
0x18000eec5  lea     rdx, [rsp+1B8h+var_140]
0x18000eeca  mov     rcx, rbx
0x18000eecd  call    ??$insert@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@0@Z; win_musl::Formatter::insert<std::wstring>(std::wstring const &,std::wstring const &)
0x18000eed2  mov     rcx, rax; this
0x18000eed5  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18000eeda  mov     [rsp+1B8h+var_188], rax; struct win_musl::TStringEllipseBase *
0x18000eedf  mov     [rsp+1B8h+var_190], 80510017h; unsigned int
0x18000eee7  mov     [rsp+1B8h+var_198], 10Eh; unsigned int
0x18000eeef  lea     r9, word_18013A0B6
0x18000eef6  lea     r8, aNoFilename; "(no filename)"
0x18000eefd  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x18000ef05  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000ef0a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000ef11  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x18000ef19  call    _CxxThrowException_0
```
