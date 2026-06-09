# wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)

- ea: `0x1400050b8`
- end: `0x1400050db`
- name: `?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x140002258`

## string_xrefs

- `0x1400050c1`: `onecoreuap\inetcore\spartan\desktopbroker\mainloop.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_NullAlloc(
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
    0x8007000E);
}

```

## disassembly

```asm
0x1400050b8  sub     rsp, 48h
0x1400050bc  mov     rax, [rsp+48h]
0x1400050c1  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1400050c8  mov     [rsp+48h+var_18], 8007000Eh
0x1400050d0  mov     [rsp+48h+var_20], rax
0x1400050d5  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
