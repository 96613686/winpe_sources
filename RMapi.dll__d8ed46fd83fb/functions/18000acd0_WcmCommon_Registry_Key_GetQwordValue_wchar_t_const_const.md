# WcmCommon::Registry::Key::GetQwordValue(wchar_t const * const)

- ea: `0x18000acd0`
- end: `0x18000ad63`
- name: `?GetQwordValue@Key@Registry@WcmCommon@@QEBA_KQEB_W@Z`
- size: `147`
- prototype: `unsigned __int64(WcmCommon::Registry::Key *__hidden this, const wchar_t *const)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800135e0`
- `0x180020c90`
- `0x180021d48`
- `0x1800222d0`

## callees

- `0x18000acd0`
- `0x18000d2a0`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ad1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ad1c`

## string_xrefs

- `0x18000ad37`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
__int64 __fastcall WcmCommon::Registry::Key::GetQwordValue(HKEY *this, const WCHAR *a2)
{
  HKEY v2; // rcx
  int ValueW; // eax
  bool v4; // sf
  int v6; // [rsp+20h] [rbp-48h]
  DWORD v7; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = *this;
  v8 = 0;
  v7 = 8;
  ValueW = RegGetValueW(v2, 0, a2, 0x40u, 0, &v8, &v7);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = ValueW < 0;
  }
  if ( v4 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)ValueW,
      v6);
  return v8;
}

```

## disassembly

```asm
0x18000acd0  mov     r11, rsp
0x18000acd3  sub     rsp, 68h
0x18000acd7  mov     rax, cs:__security_cookie
0x18000acde  xor     rax, rsp
0x18000ace1  mov     [rsp+68h+var_18], rax
0x18000ace6  mov     rcx, [rcx]; hkey
0x18000ace9  lea     rax, [r11-28h]
0x18000aced  mov     [r11-38h], rax
0x18000acf1  mov     r8, rdx; lpValue
0x18000acf4  lea     rax, [r11-20h]
0x18000acf8  mov     qword ptr [r11-20h], 0
0x18000ad00  mov     [r11-40h], rax
0x18000ad04  mov     r9d, 40h ; '@'; dwFlags
0x18000ad0a  xor     edx, edx; lpSubKey
0x18000ad0c  mov     qword ptr [r11-48h], 0
0x18000ad14  mov     [rsp+68h+var_28], 8
0x18000ad1c  call    cs:__imp_RegGetValueW
0x18000ad22  test    eax, eax
0x18000ad24  jle     short loc_18000AD30
0x18000ad26  movzx   eax, ax
0x18000ad29  or      eax, 80070000h
0x18000ad2e  test    eax, eax
0x18000ad30  jns     short loc_18000AD4C
0x18000ad32  mov     rcx, [rsp+68h]; this
0x18000ad37  lea     r8, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18000ad3e  mov     r9d, eax; char *
0x18000ad41  mov     edx, 17Ch; void *
0x18000ad46  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ad4c  mov     rax, [rsp+68h+var_20]
0x18000ad51  mov     rcx, [rsp+68h+var_18]
0x18000ad56  xor     rcx, rsp; StackCookie
0x18000ad59  call    __security_check_cookie
0x18000ad5e  add     rsp, 68h
0x18000ad62  retn
```
