# wil::details::in1diag3::_Throw_Hr(uint,char const *,long)

- ea: `0x18000efb4`
- end: `0x18000efcf`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z`
- size: `27`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000762c`
- `0x18000e9e0`
- `0x18000eaec`
- `0x18000f060`
- `0x18000f7d0`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`

## callees

- `0x1800067a4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        __int64 a2,
        const char *a3,
        int a4)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)this, (_DWORD)a3, a4);
}

```

## disassembly

```asm
0x18000efb4  sub     rsp, 48h
0x18000efb8  mov     rax, [rsp+48h]
0x18000efbd  mov     edx, ecx
0x18000efbf  mov     [rsp+48h+var_18], r8d
0x18000efc4  mov     [rsp+48h+var_20], rax
0x18000efc9  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
