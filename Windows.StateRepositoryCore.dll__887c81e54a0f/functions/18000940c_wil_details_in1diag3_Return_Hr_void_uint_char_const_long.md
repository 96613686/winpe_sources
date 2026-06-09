# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000940c`
- end: `0x18000942a`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `70`
- callee_count: `1`
- tags: ``

## callers

- `0x180004378`
- `0x1800044e4`
- `0x1800046e0`
- `0x180006bc8`
- `0x180007534`
- `0x180007698`
- `0x180009ff8`
- `0x18000a07c`
- `0x18000bfac`
- `0x18000c05c`
- `0x18000c154`
- `0x18000c208`
- `0x18000c244`
- `0x18000c2e8`
- `0x18000c384`
- `0x18000c430`
- `0x18000c52c`
- `0x18000c698`
- `0x18000c7f0`
- `0x18000c8ac`
- `0x18000c950`
- `0x18000caa0`
- `0x18000cb60`
- `0x18000cc50`
- `0x18000cc90`
- `0x18000cd20`
- `0x18000cd60`
- `0x18000cda0`
- `0x18000cde0`
- `0x18000ce50`
- `0x18000ced0`
- `0x18000cf30`
- `0x18000cfa0`
- `0x18000d010`
- `0x18000d050`
- `0x18000d090`
- `0x18000d170`
- `0x18000d280`
- `0x18000d310`
- `0x18000d390`
- `0x18000d3d0`
- `0x18000d450`
- `0x18000d560`
- `0x18000d710`
- `0x18000d790`
- `0x18000d810`
- `0x18000d8b0`
- `0x18000d9d0`
- `0x18000da40`
- `0x18000dc7c`

## callees

- `0x180003054`

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
0x18000940c  sub     rsp, 48h
0x180009410  mov     rax, [rsp+48h]
0x180009415  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000941a  mov     [rsp+48h+var_20], rax; __int64
0x18000941f  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009424  nop
0x180009425  add     rsp, 48h
0x180009429  retn
```
