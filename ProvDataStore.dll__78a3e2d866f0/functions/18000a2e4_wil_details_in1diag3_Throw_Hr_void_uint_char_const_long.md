# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000a2e4`
- end: `0x18000a2fd`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180009430`
- `0x180009800`
- `0x18000b31c`
- `0x18000c160`
- `0x18000f65c`
- `0x18000fadc`
- `0x180010124`
- `0x180010750`
- `0x180010ae4`

## callees

- `0x180008058`

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
0x18000a2e4  sub     rsp, 48h
0x18000a2e8  mov     rax, [rsp+48h]
0x18000a2ed  mov     [rsp+48h+var_18], r9d
0x18000a2f2  mov     [rsp+48h+var_20], rax
0x18000a2f7  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
