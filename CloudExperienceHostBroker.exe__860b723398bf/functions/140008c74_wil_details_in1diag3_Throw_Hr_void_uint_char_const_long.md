# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x140008c74`
- end: `0x140008c99`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007b80`

## callees

- `0x140006ff4`

## string_xrefs

- `0x140008c7d`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    43,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x140008c74  sub     rsp, 48h
0x140008c78  mov     rax, [rsp+48h]
0x140008c7d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140008c84  mov     [rsp+48h+var_18], r9d
0x140008c89  mov     edx, 2Bh ; '+'
0x140008c8e  mov     [rsp+48h+var_20], rax
0x140008c93  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
