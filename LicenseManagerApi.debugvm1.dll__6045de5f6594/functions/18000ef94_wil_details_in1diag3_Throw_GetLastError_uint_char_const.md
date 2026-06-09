# wil::details::in1diag3::_Throw_GetLastError(uint,char const *)

- ea: `0x18000ef94`
- end: `0x18000efad`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cb4`
- `0x18000762c`
- `0x180007858`
- `0x18000f060`

## callees

- `0x180006734`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        int a2,
        const char *a3,
        int a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>((int)this, (int)this, a2, a4, v4, retaddr);
}

```

## disassembly

```asm
0x18000ef94  sub     rsp, 38h
0x18000ef98  mov     rax, [rsp+38h]
0x18000ef9d  mov     r8, rdx; int
0x18000efa0  mov     edx, ecx; int
0x18000efa2  mov     [rsp+38h+var_10], rax; char *
0x18000efa7  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
