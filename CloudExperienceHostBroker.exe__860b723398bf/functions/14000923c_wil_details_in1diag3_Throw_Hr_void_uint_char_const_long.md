# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x14000923c`
- end: `0x140009255`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400079b4`
- `0x140007b80`
- `0x140008010`
- `0x140008ed0`

## callees

- `0x140006ff4`

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
0x14000923c  sub     rsp, 48h
0x140009240  mov     rax, [rsp+48h]
0x140009245  mov     [rsp+48h+var_18], r9d
0x14000924a  mov     [rsp+48h+var_20], rax
0x14000924f  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
