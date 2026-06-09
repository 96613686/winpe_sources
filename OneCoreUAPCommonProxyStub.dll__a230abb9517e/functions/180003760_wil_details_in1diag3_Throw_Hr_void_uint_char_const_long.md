# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x180003760`
- end: `0x180003780`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001db0`
- `0x180002130`
- `0x180002670`
- `0x18000314c`
- `0x18000a500`

## callees

- `0x180003788`

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
    (_DWORD)a2,
    (unsigned int)"onecoreuap\\shell\\published\\inc\\call_as.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180003760  sub     rsp, 48h
0x180003764  mov     rax, [rsp+48h]
0x180003769  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\published\\inc\\call"...
0x180003770  mov     [rsp+48h+var_18], r9d
0x180003775  mov     [rsp+48h+var_20], rax
0x18000377a  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
