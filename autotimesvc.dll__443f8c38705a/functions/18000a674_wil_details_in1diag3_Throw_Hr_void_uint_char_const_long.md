# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000a674`
- end: `0x18000a68d`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007534`
- `0x18000d178`
- `0x18000e048`
- `0x18000e6f8`
- `0x18000fe60`
- `0x18000fed4`

## callees

- `0x180004334`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
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
0x18000a674  sub     rsp, 48h
0x18000a678  mov     rax, [rsp+48h]
0x18000a67d  mov     [rsp+48h+var_18], r9d
0x18000a682  mov     [rsp+48h+var_20], rax
0x18000a687  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
