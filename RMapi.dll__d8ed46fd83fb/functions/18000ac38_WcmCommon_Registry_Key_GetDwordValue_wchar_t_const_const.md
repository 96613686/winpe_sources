# WcmCommon::Registry::Key::GetDwordValue(wchar_t const * const)

- ea: `0x18000ac38`
- end: `0x18000acca`
- name: `?GetDwordValue@Key@Registry@WcmCommon@@QEBAKQEB_W@Z`
- size: `146`
- prototype: `unsigned int(WcmCommon::Registry::Key *__hidden this, const wchar_t *const)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009614`
- `0x180023c60`

## callees

- `0x18000ac38`
- `0x18000d2a0`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ac84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ac84`

## string_xrefs

- `0x18000ac9f`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
__int64 __fastcall WcmCommon::Registry::Key::GetDwordValue(HKEY *this, const WCHAR *a2)
{
  HKEY v2; // rcx
  int ValueW; // eax
  bool v4; // sf
  int v6; // [rsp+20h] [rbp-38h]
  unsigned int v7; // [rsp+40h] [rbp-18h] BYREF
  DWORD v8; // [rsp+44h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *this;
  v7 = 0;
  v8 = 4;
  ValueW = RegGetValueW(v2, 0, a2, 0x10u, 0, &v7, &v8);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = ValueW < 0;
  }
  if ( v4 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)ValueW,
      v6);
  return v7;
}

```

## disassembly

```asm
0x18000ac38  mov     r11, rsp
0x18000ac3b  sub     rsp, 58h
0x18000ac3f  mov     rax, cs:__security_cookie
0x18000ac46  xor     rax, rsp
0x18000ac49  mov     [rsp+58h+var_10], rax
0x18000ac4e  mov     rcx, [rcx]; hkey
0x18000ac51  lea     rax, [r11-14h]
0x18000ac55  mov     [r11-28h], rax
0x18000ac59  mov     r8, rdx; lpValue
0x18000ac5c  lea     rax, [r11-18h]
0x18000ac60  mov     [rsp+58h+var_18], 0
0x18000ac68  mov     [r11-30h], rax
0x18000ac6c  mov     r9d, 10h; dwFlags
0x18000ac72  xor     edx, edx; lpSubKey
0x18000ac74  mov     qword ptr [r11-38h], 0
0x18000ac7c  mov     [rsp+58h+var_14], 4
0x18000ac84  call    cs:__imp_RegGetValueW
0x18000ac8a  test    eax, eax
0x18000ac8c  jle     short loc_18000AC98
0x18000ac8e  movzx   eax, ax
0x18000ac91  or      eax, 80070000h
0x18000ac96  test    eax, eax
0x18000ac98  jns     short loc_18000ACB4
0x18000ac9a  mov     rcx, [rsp+58h]; this
0x18000ac9f  lea     r8, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18000aca6  mov     r9d, eax; char *
0x18000aca9  mov     edx, 174h; void *
0x18000acae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000acb4  mov     eax, [rsp+58h+var_18]
0x18000acb8  mov     rcx, [rsp+58h+var_10]
0x18000acbd  xor     rcx, rsp; StackCookie
0x18000acc0  call    __security_check_cookie
0x18000acc5  add     rsp, 58h
0x18000acc9  retn
```
