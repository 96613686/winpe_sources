# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x140007d78`
- end: `0x140007d91`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140008758`
- `0x140008bc4`
- `0x140008ec8`
- `0x140009310`
- `0x140009448`
- `0x1400095e4`
- `0x140009758`
- `0x140009918`
- `0x140009cd8`
- `0x14000a43c`
- `0x14000aa08`
- `0x14000b8c0`
- `0x14000bdcc`
- `0x14000d24c`
- `0x14000d884`

## callees

- `0x140007c08`

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
0x140007d78  sub     rsp, 48h
0x140007d7c  mov     rax, [rsp+48h]
0x140007d81  mov     [rsp+48h+var_18], r9d
0x140007d86  mov     [rsp+48h+var_20], rax
0x140007d8b  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
