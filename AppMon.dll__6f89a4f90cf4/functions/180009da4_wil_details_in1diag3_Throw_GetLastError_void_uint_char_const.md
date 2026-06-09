# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x180009da4`
- end: `0x180009db8`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089e0`
- `0x180008a94`
- `0x180008d9c`
- `0x18000b558`
- `0x18000bafc`
- `0x18000c0cc`
- `0x18000c234`
- `0x18000df00`
- `0x18000e038`
- `0x18000e0e4`

## callees

- `0x180007c9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>((int)this, (int)a2, a3, (int)a4, v4, retaddr);
}

```

## disassembly

```asm
0x180009da4  sub     rsp, 38h
0x180009da8  mov     rax, [rsp+38h]
0x180009dad  mov     [rsp+38h+var_10], rax; char *
0x180009db2  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
