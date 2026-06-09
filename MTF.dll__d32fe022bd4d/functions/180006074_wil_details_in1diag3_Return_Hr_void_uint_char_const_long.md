# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006074`
- end: `0x180006092`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `77`
- callee_count: `1`
- tags: ``

## callers

- `0x180004010`
- `0x1800043ec`
- `0x180005098`
- `0x18000697c`
- `0x180007730`
- `0x180007860`
- `0x1800078e0`
- `0x180009988`
- `0x180010750`
- `0x180010e80`
- `0x180011140`
- `0x180011740`
- `0x180012510`
- `0x1800127d0`
- `0x180012c90`
- `0x1800136a0`
- `0x180014c90`
- `0x1800150a0`
- `0x180015370`
- `0x180015580`
- `0x180015960`
- `0x180015b00`
- `0x180015c00`
- `0x180015ce0`
- `0x180015e80`
- `0x180016020`
- `0x180016150`
- `0x180016430`
- `0x180016750`
- `0x180016cf0`
- `0x180017a40`
- `0x1800189d0`
- `0x180018f80`
- `0x180019a28`
- `0x180019b00`
- `0x18001a150`
- `0x18001a450`
- `0x18001a800`
- `0x18001aa30`
- `0x18001aa70`
- `0x18001ae00`
- `0x18001af60`
- `0x18001afa0`
- `0x18001b040`
- `0x18001c680`
- `0x18001c770`
- `0x18001c840`
- `0x18001cae0`
- `0x18001cdd4`
- `0x18001cf68`

## callees

- `0x1800032c4`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180006074  sub     rsp, 48h
0x180006078  mov     rax, [rsp+48h]
0x18000607d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006082  mov     [rsp+48h+var_20], rax; __int64
0x180006087  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000608c  nop
0x18000608d  add     rsp, 48h
0x180006091  retn
```
