# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x18002d450`
- end: `0x18002d46b`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `27`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028198`
- `0x1800282c0`
- `0x180028afc`
- `0x180028bac`
- `0x180030284`

## callees

- `0x18000e36c`

## string_xrefs

- `0x18002d459`: `onecoreuap\termsrv\rdp_bin\win\common/inc/ThreadPoolWait.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    (int)a2,
    (int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/ThreadPoolWait.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x18002d450  sub     rsp, 38h
0x18002d454  mov     rax, [rsp+38h]
0x18002d459  lea     r8, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002d460  mov     [rsp+38h+var_10], rax; char *
0x18002d465  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
