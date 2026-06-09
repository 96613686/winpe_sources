# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x180008130`
- end: `0x180008149`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a48`
- `0x180003b08`
- `0x180004210`
- `0x1800048d0`
- `0x1800087a0`
- `0x180008f80`

## callees

- `0x1800021b0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180008130  sub     rsp, 48h
0x180008134  mov     rax, [rsp+48h]
0x180008139  mov     [rsp+48h+var_18], r9d
0x18000813e  mov     [rsp+48h+var_20], rax
0x180008143  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
