# Windows::Usage::SystemRequired(bool)

- ea: `0x180056d90`
- end: `0x180056f28`
- name: `?SystemRequired@Usage@Windows@@UEBA_N_N@Z`
- size: `408`
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
- `0x180056d90`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180056ef4`
- `OLEAUT32!__imp_SysFreeString` at `0x180056f08`
- `OLEAUT32!__imp_SysFreeString` at `0x180056ef4`
- `OLEAUT32!__imp_SysFreeString` at `0x180056f08`
- `POWRPROF!CallNtPowerInformation` at `0x180056de2`
- `POWRPROF!CallNtPowerInformation` at `0x180056de2`

## string_xrefs

- `0x180056df3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180056e6a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180056f16`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall Windows::Usage::SystemRequired(Windows::Usage *this, char a2)
{
  NTSTATUS v3; // eax
  bool v4; // bl
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  ULONG OutputBufferLength; // [rsp+20h] [rbp-60h]
  int OutputBuffer; // [rsp+30h] [rbp-50h] BYREF
  int v11; // [rsp+34h] [rbp-4Ch] BYREF
  BSTR v12; // [rsp+38h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
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
      (void *)0xC2,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)(unsigned int)v3,
      OutputBufferLength);
LABEL_3:
    v4 = 0;
    goto LABEL_4;
  }
  v4 = 1;
  if ( (OutputBuffer & 1) == 0 )
    goto LABEL_3;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(*v14 + 64))(v14, 1, &v11);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
      (const char *)(unsigned int)v6,
      OutputBufferLength);
    goto LABEL_3;
  }
  if ( !v11 )
    goto LABEL_3;
  if ( a2 )
  {
    v12 = 0;
    bstrString = 0;
    v7 = *v14;
    bstrString = 0;
    v12 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR *, BSTR *))(v7 + 56))(v14, &v12, &bstrString);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
        (const char *)(unsigned int)v8,
        OutputBufferLength);
    v4 = *(_QWORD *)(Windows::Strings::to_wstring(v15, &v12) + 16) != 0;
    std::wstring::_Tidy_deallocate(v15);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v12 )
      SysFreeString(v12);
  }
LABEL_4:
  if ( v14 )
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  return v4;
}

```

## disassembly

```asm
0x180056d90  mov     [rsp-8+arg_0], rbx
0x180056d95  mov     [rsp-8+arg_8], rdi
0x180056d9a  push    rbp
0x180056d9b  mov     rbp, rsp
0x180056d9e  sub     rsp, 80h
0x180056da5  mov     rax, cs:__security_cookie
0x180056dac  xor     rax, rsp
0x180056daf  mov     [rbp+var_10], rax
0x180056db3  mov     dil, dl
0x180056db6  lea     rcx, [rbp+var_38]
0x180056dba  call    ?GetDockedUsage@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedUsage@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedUsage(void)
0x180056dbf  nop
0x180056dc0  mov     [rbp+OutputBuffer], 0
0x180056dc7  mov     [rbp+var_4C], 0
0x180056dce  mov     [rsp+80h+OutputBufferLength], 4; int
0x180056dd6  lea     r9, [rbp+OutputBuffer]; OutputBuffer
0x180056dda  xor     r8d, r8d; InputBufferLength
0x180056ddd  xor     edx, edx; InputBuffer
0x180056ddf  lea     ecx, [rdx+10h]; InformationLevel
0x180056de2  call    cs:__imp_CallNtPowerInformation
0x180056de8  mov     rcx, [rbp+8]; this
0x180056dec  test    eax, eax
0x180056dee  jns     short loc_180056E3F
0x180056df0  mov     r9d, eax; char *
0x180056df3  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180056dfa  mov     edx, 0C2h; void *
0x180056dff  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180056e04  xor     bl, bl
0x180056e06  mov     rcx, [rbp+var_38]
0x180056e0a  test    rcx, rcx
0x180056e0d  jz      short loc_180056E1C
0x180056e0f  mov     rdx, [rcx]
0x180056e12  mov     rax, [rdx+10h]
0x180056e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e1b  nop
0x180056e1c  mov     al, bl
0x180056e1e  mov     rcx, [rbp+var_10]
0x180056e22  xor     rcx, rsp; StackCookie
0x180056e25  call    __security_check_cookie
0x180056e2a  lea     r11, [rsp+80h+var_s0]
0x180056e32  mov     rbx, [r11+10h]
0x180056e36  mov     rdi, [r11+18h]
0x180056e3a  mov     rsp, r11
0x180056e3d  pop     rbp
0x180056e3e  retn
0x180056e3f  mov     ebx, 1
0x180056e44  test    byte ptr [rbp+OutputBuffer], bl
0x180056e47  jz      short loc_180056E04
0x180056e49  mov     rcx, [rbp+var_38]
0x180056e4d  mov     rax, [rcx]
0x180056e50  lea     r8, [rbp+var_4C]
0x180056e54  mov     edx, ebx
0x180056e56  mov     rax, [rax+40h]
0x180056e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e5f  mov     rcx, [rbp+8]; this
0x180056e63  test    eax, eax
0x180056e65  jns     short loc_180056E7D
0x180056e67  mov     r9d, eax; char *
0x180056e6a  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180056e71  mov     edx, 0C4h; void *
0x180056e76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180056e7b  jmp     short loc_180056E04
0x180056e7d  cmp     [rbp+var_4C], 0
0x180056e81  jz      short loc_180056E04
0x180056e83  test    dil, dil
0x180056e86  jz      loc_180056E06
0x180056e8c  mov     [rbp+var_48], 0
0x180056e94  mov     [rbp+bstrString], 0
0x180056e9c  mov     rcx, [rbp+var_38]
0x180056ea0  mov     rax, [rcx]
0x180056ea3  mov     [rbp+bstrString], 0
0x180056eab  mov     [rbp+var_48], 0
0x180056eb3  lea     r8, [rbp+bstrString]
0x180056eb7  lea     rdx, [rbp+var_48]
0x180056ebb  mov     rax, [rax+38h]
0x180056ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ec4  mov     rcx, [rbp+8]; this
0x180056ec8  test    eax, eax
0x180056eca  js      short loc_180056F13
0x180056ecc  lea     rdx, [rbp+var_48]
0x180056ed0  lea     rcx, [rbp+var_30]
0x180056ed4  call    ?to_wstring@Strings@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Strings::to_wstring(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x180056ed9  cmp     qword ptr [rax+10h], 0
0x180056ede  setnz   bl
0x180056ee1  lea     rcx, [rbp+var_30]
0x180056ee5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180056eea  nop
0x180056eeb  mov     rcx, [rbp+bstrString]; bstrString
0x180056eef  test    rcx, rcx
0x180056ef2  jz      short loc_180056EFB
0x180056ef4  call    cs:__imp_SysFreeString
0x180056efa  nop
0x180056efb  mov     rcx, [rbp+var_48]; bstrString
0x180056eff  test    rcx, rcx
0x180056f02  jz      loc_180056E06
0x180056f08  call    cs:__imp_SysFreeString
0x180056f0e  jmp     loc_180056E06
0x180056f13  mov     r9d, eax; char *
0x180056f16  lea     r8, aOnecoreEnduser_6; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180056f1d  mov     edx, 0CAh; void *
0x180056f22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
