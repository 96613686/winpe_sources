# wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)

- ea: `0x140003320`
- end: `0x140003334`
- name: `?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d58`
- `0x14000455c`

## callees

- `0x140002260`

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
0x140003320  sub     rsp, 48h
0x140003324  mov     rax, [rsp+48h]
0x140003329  mov     [rsp+48h+var_20], rax
0x14000332e  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
