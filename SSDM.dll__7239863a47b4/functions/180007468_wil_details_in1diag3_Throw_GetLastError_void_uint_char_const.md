# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x180007468`
- end: `0x18000747c`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800051cc`
- `0x18000c334`
- `0x18000c9a8`
- `0x18000cd88`
- `0x18000cfd8`
- `0x18000d400`

## callees

- `0x180003360`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180007468  sub     rsp, 38h
0x18000746c  mov     rax, [rsp+38h]
0x180007471  mov     [rsp+38h+var_10], rax
0x180007476  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
