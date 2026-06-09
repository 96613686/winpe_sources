# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007484`
- end: `0x18000749d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042fc`
- `0x180005b40`
- `0x180005ec0`
- `0x180007ab0`
- `0x18000ace8`
- `0x18000c334`
- `0x18000cfd8`
- `0x18000e3f4`

## callees

- `0x1800035a0`

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
0x180007484  sub     rsp, 48h
0x180007488  mov     rax, [rsp+48h]
0x18000748d  mov     [rsp+48h+var_18], r9d
0x180007492  mov     [rsp+48h+var_20], rax
0x180007497  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
