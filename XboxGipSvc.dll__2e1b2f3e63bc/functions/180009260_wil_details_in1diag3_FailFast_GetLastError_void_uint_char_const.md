# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x180009260`
- end: `0x180009274`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180007098`
- `0x1800071b4`
- `0x1800073b8`
- `0x180007790`
- `0x18000832c`
- `0x180008f3c`
- `0x18000bbf0`
- `0x18000bfb8`
- `0x18000c118`
- `0x18000e90c`
- `0x18000ee1c`
- `0x18000efec`
- `0x18000f530`
- `0x18000f5d4`
- `0x180010410`
- `0x180010a74`
- `0x180010e80`

## callees

- `0x180006b9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<3>((int)this, (int)a2, a3, (int)a4, v4, retaddr);
}

```

## disassembly

```asm
0x180009260  sub     rsp, 38h
0x180009264  mov     rax, [rsp+38h]
0x180009269  mov     [rsp+38h+var_10], rax; char *
0x18000926e  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
