# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1400050e4`
- end: `0x140005107`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004e5c`
- `0x1400054fc`

## callees

- `0x140002258`

## string_xrefs

- `0x1400050ed`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    a2,
    (__int64)"onecoreuap\\inetcore\\spartan\\desktopbroker\\mainloop.cpp",
    (__int64)a4,
    v4,
    retaddr,
    0x8000FFFF);
}

```

## disassembly

```asm
0x1400050e4  sub     rsp, 48h
0x1400050e8  mov     rax, [rsp+48h]
0x1400050ed  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400050f4  mov     [rsp+48h+var_18], 8000FFFFh
0x1400050fc  mov     [rsp+48h+var_20], rax
0x140005101  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
