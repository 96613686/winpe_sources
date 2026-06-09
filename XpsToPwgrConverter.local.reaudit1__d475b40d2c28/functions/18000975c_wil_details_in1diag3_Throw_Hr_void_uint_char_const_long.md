# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000975c`
- end: `0x180009775`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ad8`
- `0x180008b34`
- `0x180008d60`
- `0x18000927c`
- `0x18000ae2c`
- `0x18000aef4`
- `0x18000afcc`
- `0x18000b094`
- `0x18000b170`
- `0x18000b238`
- `0x18000b498`
- `0x18000b74c`
- `0x18000ba80`
- `0x18000bd40`
- `0x18000c078`
- `0x18000dc78`
- `0x18000e494`
- `0x18000e7a0`

## callees

- `0x180008ea4`

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
0x18000975c  sub     rsp, 48h
0x180009760  mov     rax, [rsp+48h]
0x180009765  mov     [rsp+48h+var_18], r9d
0x18000976a  mov     [rsp+48h+var_20], rax
0x18000976f  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
