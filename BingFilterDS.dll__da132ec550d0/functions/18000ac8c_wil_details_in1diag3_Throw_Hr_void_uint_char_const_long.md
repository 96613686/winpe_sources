# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000ac8c`
- end: `0x18000aca5`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180008974`
- `0x18000904c`
- `0x180009250`
- `0x1800097dc`
- `0x1800099cc`
- `0x180009b54`
- `0x18000a05c`
- `0x18000a180`
- `0x18000a870`
- `0x18000a9a0`

## callees

- `0x180007e90`

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
0x18000ac8c  sub     rsp, 48h
0x18000ac90  mov     rax, [rsp+48h]
0x18000ac95  mov     [rsp+48h+var_18], r9d
0x18000ac9a  mov     [rsp+48h+var_20], rax
0x18000ac9f  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
