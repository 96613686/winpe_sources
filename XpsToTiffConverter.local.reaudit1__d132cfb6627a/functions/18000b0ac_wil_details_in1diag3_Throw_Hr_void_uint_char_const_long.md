# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000b0ac`
- end: `0x18000b0c5`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f94`
- `0x18000a170`
- `0x18000a870`
- `0x18000ac30`
- `0x18000be40`
- `0x18000c3e8`
- `0x18000c690`

## callees

- `0x180009080`

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
0x18000b0ac  sub     rsp, 48h
0x18000b0b0  mov     rax, [rsp+48h]
0x18000b0b5  mov     [rsp+48h+var_18], r9d
0x18000b0ba  mov     [rsp+48h+var_20], rax
0x18000b0bf  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
