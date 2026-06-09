# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007150`
- end: `0x180007169`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x180005dc0`
- `0x180005e70`
- `0x180005f00`
- `0x180005f70`
- `0x180006690`
- `0x180006800`
- `0x180007d40`
- `0x180007dd0`
- `0x180007e50`
- `0x180008800`
- `0x180008ae0`
- `0x180009520`
- `0x18000b640`
- `0x18000ba9c`
- `0x18000ca44`
- `0x18000d740`
- `0x1800108a8`
- `0x180010a80`
- `0x180010bec`
- `0x180010d00`
- `0x180013484`
- `0x180014570`
- `0x180014ec4`
- `0x1800150c0`
- `0x180015370`
- `0x180016124`
- `0x180016730`
- `0x180017174`

## callees

- `0x180004938`

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
0x180007150  sub     rsp, 48h
0x180007154  mov     rax, [rsp+48h]
0x180007159  mov     [rsp+48h+var_18], r9d
0x18000715e  mov     [rsp+48h+var_20], rax
0x180007163  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
