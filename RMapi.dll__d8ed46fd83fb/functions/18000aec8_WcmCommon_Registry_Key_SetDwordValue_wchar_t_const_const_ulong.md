# WcmCommon::Registry::Key::SetDwordValue(wchar_t const * const,ulong)

- ea: `0x18000aec8`
- end: `0x18000af3e`
- name: `?SetDwordValue@Key@Registry@WcmCommon@@QEAAXQEB_WK@Z`
- size: `118`
- prototype: `void __fastcall(WcmCommon::Registry::Key *__hidden this, const wchar_t *const, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800233a4`
- `0x180023af0`

## callees

- `0x18000aec8`
- `0x18000d2a0`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aefc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aefc`

## string_xrefs

- `0x18000af17`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
void __fastcall WcmCommon::Registry::Key::SetDwordValue(HKEY *this, const wchar_t *const a2, int a3)
{
  int v3; // eax
  bool v4; // sf
  int v5; // [rsp+20h] [rbp-28h]
  BYTE v6[8]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)v6 = a3;
  v3 = RegSetValueExW(*this, 0, 0, 4u, v6, 4u);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = v3 < 0;
  }
  if ( v4 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)v3,
      v5);
}

```

## disassembly

```asm
0x18000aec8  mov     r11, rsp
0x18000aecb  sub     rsp, 48h
0x18000aecf  mov     rax, cs:__security_cookie
0x18000aed6  xor     rax, rsp
0x18000aed9  mov     [rsp+48h+var_10], rax
0x18000aede  mov     [r11-18h], r8d
0x18000aee2  lea     rax, [r11-18h]
0x18000aee6  mov     rcx, [rcx]; hKey
0x18000aee9  mov     r9d, 4; dwType
0x18000aeef  mov     [r11-20h], r9d
0x18000aef3  xor     r8d, r8d; Reserved
0x18000aef6  xor     edx, edx; lpValueName
0x18000aef8  mov     [r11-28h], rax
0x18000aefc  call    cs:__imp_RegSetValueExW
0x18000af02  test    eax, eax
0x18000af04  jle     short loc_18000AF10
0x18000af06  movzx   eax, ax
0x18000af09  or      eax, 80070000h
0x18000af0e  test    eax, eax
0x18000af10  jns     short loc_18000AF2C
0x18000af12  mov     rcx, [rsp+48h]; this
0x18000af17  lea     r8, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18000af1e  mov     r9d, eax; char *
0x18000af21  mov     edx, 10Eh; void *
0x18000af26  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000af2c  mov     rcx, [rsp+48h+var_10]
0x18000af31  xor     rcx, rsp; StackCookie
0x18000af34  call    __security_check_cookie
0x18000af39  add     rsp, 48h
0x18000af3d  retn
```
