# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x14000fbb0`
- end: `0x14000fbc9`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x1400083ac`
- `0x140008450`
- `0x1400084f4`
- `0x140008594`
- `0x140008634`
- `0x1400086d4`
- `0x140008774`
- `0x140009738`
- `0x1400097ec`
- `0x140009844`
- `0x14000a934`
- `0x14000ad34`
- `0x14000ae54`
- `0x14000afec`
- `0x14000b114`
- `0x14000bc30`
- `0x14000bef8`
- `0x14000c33c`
- `0x14000c3ec`
- `0x14000c78c`
- `0x14000c848`
- `0x14000cc94`
- `0x14000cf8c`
- `0x14000ed9c`
- `0x14000f2a4`
- `0x14000f3b8`
- `0x14000fdc0`

## callees

- `0x140008cf4`

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
0x14000fbb0  sub     rsp, 48h
0x14000fbb4  mov     rax, [rsp+48h]
0x14000fbb9  mov     [rsp+48h+var_18], r9d
0x14000fbbe  mov     [rsp+48h+var_20], rax
0x14000fbc3  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
