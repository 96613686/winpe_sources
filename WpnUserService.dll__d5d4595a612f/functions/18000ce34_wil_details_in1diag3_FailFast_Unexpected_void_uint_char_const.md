# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000ce34`
- end: `0x18000ce50`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `28`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000acd4`
- `0x18000c12c`
- `0x18000e9e8`
- `0x180010444`

## callees

- `0x180003a84`

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
0x18000ce34  sub     rsp, 48h
0x18000ce38  mov     rax, [rsp+48h]
0x18000ce3d  mov     [rsp+48h+var_18], 8000FFFFh
0x18000ce45  mov     [rsp+48h+var_20], rax
0x18000ce4a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
