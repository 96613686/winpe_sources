# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800040cc`
- end: `0x1800040e0`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003648`
- `0x1800059b8`

## callees

- `0x180002860`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1800040cc  sub     rsp, 48h
0x1800040d0  mov     rax, [rsp+48h]
0x1800040d5  mov     [rsp+48h+var_20], rax
0x1800040da  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
