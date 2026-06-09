# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x1800037e4`
- end: `0x1800037f8`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003168`
- `0x180004a4c`
- `0x180005e08`
- `0x1800069e8`
- `0x180006da0`
- `0x180007824`
- `0x180008750`
- `0x1800090c0`
- `0x18000926c`

## callees

- `0x180002644`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
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
0x1800037e4  sub     rsp, 48h
0x1800037e8  mov     rax, [rsp+48h]
0x1800037ed  mov     [rsp+48h+var_20], rax
0x1800037f2  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
