# CLanguageComponentsInstallerHandler::IsInstallationBlockedByCTAPolicy(void)

- ea: `0x1800188a4`
- end: `0x180018a5c`
- name: `?IsInstallationBlockedByCTAPolicy@CLanguageComponentsInstallerHandler@@AEBA_NXZ`
- size: `440`
- prototype: `bool __fastcall(CLanguageComponentsInstallerHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d0f0`

## callees

- `0x180003520`
- `0x18000a7fc`
- `0x1800188a4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800188f5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800188f5`

## string_xrefs

- `0x180018a35`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x180018a49`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
bool __fastcall CLanguageComponentsInstallerHandler::IsInstallationBlockedByCTAPolicy(
        CLanguageComponentsInstallerHandler *this)
{
  HRESULT v1; // eax
  __int64 (__fastcall *v2)(LPVOID, const wchar_t *, __int64 *); // rdi
  int v3; // eax
  bool result; // al
  int v5; // [rsp+20h] [rbp-38h]
  __int64 v6; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF
  int v8; // [rsp+3Ch] [rbp-1Ch] BYREF
  LPVOID v9; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    if ( *((_BYTE *)this + 64) )
    {
      result = 0;
    }
    else
    {
      v6 = 0;
      v9 = 0;
      v1 = CoCreateInstance(
             &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
             0,
             4u,
             &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
             &v9);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
          (const char *)(unsigned int)v1,
          v5);
      v2 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v9 + 40LL);
      v6 = 0;
      v3 = v2(v9, L"Language", &v6);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
          (const char *)(unsigned int)v3,
          v5);
      v7 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 456LL))(v6, &v7) < 0
        || v7 != 1
        || (v8 = 1, (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 320LL))(v6, &v8) < 0)
        || v8 )
      {
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v9 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
        result = 0;
      }
      else
      {
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v9 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
        result = 1;
      }
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800188a4  mov     r11, rsp
0x1800188a7  mov     [r11+8], rbx
0x1800188ab  push    rdi
0x1800188ac  sub     rsp, 50h
0x1800188b0  mov     rax, cs:__security_cookie
0x1800188b7  xor     rax, rsp
0x1800188ba  mov     [rsp+58h+var_10], rax
0x1800188bf  cmp     byte ptr [rcx+40h], 0
0x1800188c3  jnz     loc_180018A14
0x1800188c9  mov     qword ptr [r11-28h], 0
0x1800188d1  mov     qword ptr [r11-18h], 0
0x1800188d9  lea     rax, [r11-18h]
0x1800188dd  mov     [r11-38h], rax
0x1800188e1  lea     r9, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a; riid
0x1800188e8  xor     edx, edx; pUnkOuter
0x1800188ea  lea     r8d, [rdx+4]; dwClsContext
0x1800188ee  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x1800188f5  call    cs:__imp_CoCreateInstance
0x1800188fb  mov     rcx, [rsp+58h]; this
0x180018900  test    eax, eax
0x180018902  js      loc_180018A32
0x180018908  mov     rbx, [rsp+58h+var_18]
0x18001890d  mov     rax, [rbx]
0x180018910  mov     rdi, [rax+28h]
0x180018914  mov     rcx, [rsp+58h+var_28]
0x180018919  mov     [rsp+58h+var_28], 0
0x180018922  test    rcx, rcx
0x180018925  jz      short loc_180018934
0x180018927  mov     rdx, [rcx]
0x18001892a  mov     rax, [rdx+10h]
0x18001892e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018933  nop
0x180018934  lea     r8, [rsp+58h+var_28]
0x180018939  lea     rdx, aLanguage; "Language"
0x180018940  mov     rcx, rbx
0x180018943  mov     rax, rdi
0x180018946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894b  mov     rcx, [rsp+58h]; this
0x180018950  test    eax, eax
0x180018952  js      loc_180018A46
0x180018958  mov     [rsp+58h+var_20], 0
0x180018960  mov     rcx, [rsp+58h+var_28]
0x180018965  mov     rax, [rcx]
0x180018968  lea     rdx, [rsp+58h+var_20]
0x18001896d  mov     rax, [rax+1C8h]
0x180018974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018979  test    eax, eax
0x18001897b  js      short loc_1800189E2
0x18001897d  cmp     [rsp+58h+var_20], 1
0x180018982  jnz     short loc_1800189E2
0x180018984  mov     [rsp+58h+var_1C], 1
0x18001898c  mov     rcx, [rsp+58h+var_28]
0x180018991  mov     rax, [rcx]
0x180018994  lea     rdx, [rsp+58h+var_1C]
0x180018999  mov     rax, [rax+140h]
0x1800189a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189a5  test    eax, eax
0x1800189a7  js      short loc_1800189E2
0x1800189a9  cmp     [rsp+58h+var_1C], 0
0x1800189ae  jnz     short loc_1800189E2
0x1800189b0  mov     rcx, [rsp+58h+var_28]
0x1800189b5  test    rcx, rcx
0x1800189b8  jz      short loc_1800189C7
0x1800189ba  mov     rax, [rcx]
0x1800189bd  mov     rax, [rax+10h]
0x1800189c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c6  nop
0x1800189c7  mov     rcx, [rsp+58h+var_18]
0x1800189cc  test    rcx, rcx
0x1800189cf  jz      short loc_1800189DE
0x1800189d1  mov     rdx, [rcx]
0x1800189d4  mov     rax, [rdx+10h]
0x1800189d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189dd  nop
0x1800189de  mov     al, 1
0x1800189e0  jmp     short loc_180018A1A
0x1800189e2  mov     rcx, [rsp+58h+var_28]
0x1800189e7  test    rcx, rcx
0x1800189ea  jz      short loc_1800189F9
0x1800189ec  mov     rax, [rcx]
0x1800189ef  mov     rax, [rax+10h]
0x1800189f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189f8  nop
0x1800189f9  mov     rcx, [rsp+58h+var_18]
0x1800189fe  test    rcx, rcx
0x180018a01  jz      short loc_180018A10
0x180018a03  mov     rax, [rcx]
0x180018a06  mov     rax, [rax+10h]
0x180018a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a0f  nop
0x180018a10  xor     al, al
0x180018a12  jmp     short loc_180018A1A
0x180018a14  xor     al, al
0x180018a16  jmp     short loc_180018A1A
0x180018a18  xor     al, al
0x180018a1a  mov     rcx, [rsp+58h+var_10]
0x180018a1f  xor     rcx, rsp; StackCookie
0x180018a22  call    __security_check_cookie
0x180018a27  mov     rbx, [rsp+58h+arg_0]
0x180018a2c  add     rsp, 50h
0x180018a30  pop     rdi
0x180018a31  retn
0x180018a32  mov     r9d, eax; char *
0x180018a35  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180018a3c  mov     edx, 15Ah; void *
0x180018a41  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018a46  mov     r9d, eax; char *
0x180018a49  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180018a50  mov     edx, 15Ch; void *
0x180018a55  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
