# WcmCommon::Registry::Key::SetQwordValue(wchar_t const * const,unsigned __int64)

- ea: `0x18000b960`
- end: `0x18000b9c0`
- name: `?SetQwordValue@Key@Registry@WcmCommon@@QEAAXQEB_W_K@Z`
- size: `96`
- prototype: `void __fastcall(WcmCommon::Registry::Key *__hidden this, const wchar_t *const, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cda8`

## callees

- `0x18000b960`
- `0x18000b9c8`
- `0x18000d2a0`
- `0x180010f80`

## string_xrefs

- `0x18000b999`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
void __fastcall WcmCommon::Registry::Key::SetQwordValue(HKEY *this, const WCHAR *a2, __int64 a3)
{
  LSTATUS v3; // eax
  unsigned int v4; // [rsp+20h] [rbp-28h]
  unsigned __int8 v5[8]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)v5 = a3;
  v3 = WcmCommon::Registry::Key::SetValue(this, a2, 0xBu, v5, 8u);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)v3,
      v4);
}

```

## disassembly

```asm
0x18000b960  sub     rsp, 48h
0x18000b964  mov     rax, cs:__security_cookie
0x18000b96b  xor     rax, rsp
0x18000b96e  mov     [rsp+48h+var_10], rax
0x18000b973  mov     qword ptr [rsp+48h+var_18], r8
0x18000b978  lea     r9, [rsp+48h+var_18]; unsigned __int8 *
0x18000b97d  mov     r8d, 0Bh; unsigned int
0x18000b983  mov     [rsp+48h+var_28], 8; int
0x18000b98b  call    ?SetValue@Key@Registry@WcmCommon@@QEAAJQEB_WKPEBEK@Z; WcmCommon::Registry::Key::SetValue(wchar_t const * const,ulong,uchar const *,ulong)
0x18000b990  test    eax, eax
0x18000b992  jns     short loc_18000B9AE
0x18000b994  mov     rcx, [rsp+48h]; this
0x18000b999  lea     r8, aOnecorePrivate_0; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18000b9a0  mov     r9d, eax; char *
0x18000b9a3  mov     edx, 113h; void *
0x18000b9a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b9ae  mov     rcx, [rsp+48h+var_10]
0x18000b9b3  xor     rcx, rsp; StackCookie
0x18000b9b6  call    __security_check_cookie
0x18000b9bb  add     rsp, 48h
0x18000b9bf  retn
```
