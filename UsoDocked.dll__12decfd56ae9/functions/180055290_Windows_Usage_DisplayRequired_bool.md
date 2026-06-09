# Windows::Usage::DisplayRequired(bool)

- ea: `0x180055290`
- end: `0x180055422`
- name: `?DisplayRequired@Usage@Windows@@UEBA_N_N@Z`
- size: `402`
- prototype: `bool __fastcall(Windows::Usage *__hidden this, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x1800209fc`
- `0x180020a9c`
- `0x1800239c4`
- `0x180045140`
- `0x180045278`
- `0x180055290`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800553ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180055402`
- `OLEAUT32!__imp_SysFreeString` at `0x1800553ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180055402`
- `POWRPROF!CallNtPowerInformation` at `0x1800552e2`
- `POWRPROF!CallNtPowerInformation` at `0x1800552e2`

## string_xrefs

- `0x1800552f3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180055366`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180055410`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall Windows::Usage::DisplayRequired(Windows::Usage *this, char a2)
{
  NTSTATUS v3; // eax
  bool v4; // bl
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  ULONG OutputBufferLength; // [rsp+20h] [rbp-60h]
  int OutputBuffer; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+34h] [rbp-4Ch] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-48h] BYREF
  BSTR v13; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v14; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  Windows::DockedHelpers::GetDockedUsage((Windows::DockedHelpers *)&v14);
  OutputBuffer = 0;
  v11 = 0;
  v3 = CallNtPowerInformation(SystemExecutionState, 0, 0, &OutputBuffer, 4u);
  if ( v3 < 0 )
  {
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)(unsigned int)v3,
      OutputBufferLength);
LABEL_3:
    v4 = 0;
    goto LABEL_4;
  }
  if ( (OutputBuffer & 2) == 0 )
    goto LABEL_3;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *))(*v14 + 64))(v14, 0, &v11);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)(unsigned int)v6,
      OutputBufferLength);
    goto LABEL_3;
  }
  if ( !v11 )
    goto LABEL_3;
  v4 = 1;
  if ( a2 )
  {
    v13 = 0;
    bstrString = 0;
    v7 = *v14;
    bstrString = 0;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR *, BSTR *))(v7 + 56))(v14, &v13, &bstrString);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
        (const char *)(unsigned int)v8,
        OutputBufferLength);
    v4 = *(_QWORD *)(Windows::Strings::to_wstring(v15, &bstrString) + 16) != 0;
    std::wstring::_Tidy_deallocate(v15);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v13 )
      SysFreeString(v13);
  }
LABEL_4:
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  return v4;
}

```

## disassembly

```asm
0x180055290  mov     [rsp-8+arg_0], rbx
0x180055295  mov     [rsp-8+arg_8], rdi
0x18005529a  push    rbp
0x18005529b  mov     rbp, rsp
0x18005529e  sub     rsp, 80h
0x1800552a5  mov     rax, cs:__security_cookie
0x1800552ac  xor     rax, rsp
0x1800552af  mov     [rbp+var_10], rax
0x1800552b3  mov     dil, dl
0x1800552b6  lea     rcx, [rbp+var_38]
0x1800552ba  call    ?GetDockedUsage@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedUsage@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedUsage(void)
0x1800552bf  nop
0x1800552c0  mov     [rbp+OutputBuffer], 0
0x1800552c7  mov     [rbp+var_4C], 0
0x1800552ce  mov     [rsp+80h+OutputBufferLength], 4; int
0x1800552d6  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x1800552da  xor     r8d, r8d; InputBufferLength
0x1800552dd  xor     edx, edx; InputBuffer
0x1800552df  lea     ecx, [rdx+10h]; InformationLevel
0x1800552e2  call    cs:__imp_CallNtPowerInformation
0x1800552e8  mov     rcx, [rbp+8]; this
0x1800552ec  test    eax, eax
0x1800552ee  jns     short loc_18005533F
0x1800552f0  mov     r9d, eax; char *
0x1800552f3  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800552fa  mov     edx, 0ACh; void *
0x1800552ff  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180055304  xor     bl, bl
0x180055306  mov     rcx, [rbp+var_38]
0x18005530a  test    rcx, rcx
0x18005530d  jz      short loc_18005531C
0x18005530f  mov     rdx, [rcx]
0x180055312  mov     rax, [rdx+10h]
0x180055316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005531b  nop
0x18005531c  mov     al, bl
0x18005531e  mov     rcx, [rbp+var_10]
0x180055322  xor     rcx, rsp; StackCookie
0x180055325  call    __security_check_cookie
0x18005532a  lea     r11, [rsp+80h+var_s0]
0x180055332  mov     rbx, [r11+10h]
0x180055336  mov     rdi, [r11+18h]
0x18005533a  mov     rsp, r11
0x18005533d  pop     rbp
0x18005533e  retn
0x18005533f  test    byte ptr [rbp+OutputBuffer], 2
0x180055343  jz      short loc_180055304
0x180055345  mov     rcx, [rbp+var_38]
0x180055349  mov     rax, [rcx]
0x18005534c  lea     r8, [rbp+var_4C]
0x180055350  xor     edx, edx
0x180055352  mov     rax, [rax+40h]
0x180055356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005535b  mov     rcx, [rbp+8]; this
0x18005535f  test    eax, eax
0x180055361  jns     short loc_180055379
0x180055363  mov     r9d, eax; char *
0x180055366  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005536d  mov     edx, 0AEh; void *
0x180055372  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180055377  jmp     short loc_180055304
0x180055379  cmp     [rbp+var_4C], 0
0x18005537d  jz      short loc_180055304
0x18005537f  mov     bl, 1
0x180055381  test    dil, dil
0x180055384  jz      short loc_180055306
0x180055386  mov     [rbp+var_40], 0
0x18005538e  mov     [rbp+bstrString], 0
0x180055396  mov     rcx, [rbp+var_38]
0x18005539a  mov     rax, [rcx]
0x18005539d  mov     [rbp+bstrString], 0
0x1800553a5  mov     [rbp+var_40], 0
0x1800553ad  lea     r8, [rbp+bstrString]
0x1800553b1  lea     rdx, [rbp+var_40]
0x1800553b5  mov     rax, [rax+38h]
0x1800553b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553be  mov     rcx, [rbp+8]; this
0x1800553c2  test    eax, eax
0x1800553c4  js      short loc_18005540D
0x1800553c6  lea     rdx, [rbp+bstrString]
0x1800553ca  lea     rcx, [rbp+var_30]
0x1800553ce  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Strings::to_wstring(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x1800553d3  cmp     qword ptr [rax+10h], 0
0x1800553d8  setnz   bl
0x1800553db  lea     rcx, [rbp+var_30]
0x1800553df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800553e4  nop
0x1800553e5  mov     rcx, [rbp+bstrString]; bstrString
0x1800553e9  test    rcx, rcx
0x1800553ec  jz      short loc_1800553F5
0x1800553ee  call    cs:__imp_SysFreeString
0x1800553f4  nop
0x1800553f5  mov     rcx, [rbp+var_40]; bstrString
0x1800553f9  test    rcx, rcx
0x1800553fc  jz      loc_180055306
0x180055402  call    cs:__imp_SysFreeString
0x180055408  jmp     loc_180055306
0x18005540d  mov     r9d, eax; char *
0x180055410  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180055417  mov     edx, 0B4h; void *
0x18005541c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
