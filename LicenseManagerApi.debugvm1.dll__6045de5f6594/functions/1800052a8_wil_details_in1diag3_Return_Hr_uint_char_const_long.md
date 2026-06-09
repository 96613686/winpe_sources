# wil::details::in1diag3::Return_Hr(uint,char const *,long)

- ea: `0x1800052a8`
- end: `0x1800052cb`
- name: `?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z`
- size: `35`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, unsigned int, wil::details *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037a8`
- `0x180003b10`
- `0x1800046b8`
- `0x180005d2c`
- `0x180006ddc`
- `0x1800073e8`
- `0x18000e678`
- `0x18000e71c`
- `0x18000e920`
- `0x18000eaec`

## callees

- `0x180002bd0`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, int a2, wil::details *a3, int a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a3;
  wil::details::ReportFailure_Hr<1>((int)this, (int)this, a2, a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x1800052a8  sub     rsp, 48h
0x1800052ac  mov     rax, [rsp+48h]
0x1800052b1  mov     dword ptr [rsp+48h+var_18], r8d; wil::details *
0x1800052b6  mov     [rsp+48h+var_20], rax; __int64
0x1800052bb  mov     r8, rdx; int
0x1800052be  mov     edx, ecx; int
0x1800052c0  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800052c5  nop
0x1800052c6  add     rsp, 48h
0x1800052ca  retn
```
