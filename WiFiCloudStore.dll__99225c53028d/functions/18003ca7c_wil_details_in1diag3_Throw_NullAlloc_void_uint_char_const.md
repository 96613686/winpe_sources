# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x18003ca7c`
- end: `0x18003ca9f`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002931c`

## callees

- `0x18002cda4`

## string_xrefs

- `0x18003ca85`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = -2147024882;
  wil::details::ReportFailure_Hr<0>(
    (int)this,
    (int)a2,
    (int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
    (int)a4,
    v4,
    retaddr,
    v5);
}

```

## disassembly

```asm
0x18003ca7c  sub     rsp, 48h
0x18003ca80  mov     rax, [rsp+48h]
0x18003ca85  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003ca8c  mov     dword ptr [rsp+48h+var_18], 8007000Eh; wil::details *
0x18003ca94  mov     [rsp+48h+var_20], rax; __int64
0x18003ca99  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
