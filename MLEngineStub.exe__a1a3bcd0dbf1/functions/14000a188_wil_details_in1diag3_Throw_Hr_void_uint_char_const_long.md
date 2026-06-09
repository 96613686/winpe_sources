# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x14000a188`
- end: `0x14000a1a1`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400065bc`
- `0x1400067e8`
- `0x14000a678`

## callees

- `0x140006a38`

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
0x14000a188  sub     rsp, 48h
0x14000a18c  mov     rax, [rsp+48h]
0x14000a191  mov     [rsp+48h+var_18], r9d
0x14000a196  mov     [rsp+48h+var_20], rax
0x14000a19b  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
