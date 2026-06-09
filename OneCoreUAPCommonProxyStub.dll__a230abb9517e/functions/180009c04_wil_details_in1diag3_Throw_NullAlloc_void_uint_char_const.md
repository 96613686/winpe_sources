# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x180009c04`
- end: `0x180009c20`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000314c`
- `0x180006f14`
- `0x180006f64`

## callees

- `0x180003788`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180009c04  sub     rsp, 48h
0x180009c08  mov     rax, [rsp+48h]
0x180009c0d  mov     [rsp+48h+var_18], 8007000Eh
0x180009c15  mov     [rsp+48h+var_20], rax
0x180009c1a  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
