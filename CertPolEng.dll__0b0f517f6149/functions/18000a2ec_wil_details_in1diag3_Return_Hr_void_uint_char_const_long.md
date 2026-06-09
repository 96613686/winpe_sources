# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000a2ec`
- end: `0x18000a30a`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180004da0`
- `0x180009ce8`
- `0x180009e54`
- `0x180009fc0`
- `0x18000f7d0`
- `0x180010438`
- `0x180010784`
- `0x1800108d4`
- `0x180011c60`

## callees

- `0x18000a310`

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
0x18000a2ec  sub     rsp, 48h
0x18000a2f0  mov     rax, [rsp+48h]
0x18000a2f5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000a2fa  mov     [rsp+48h+var_20], rax; __int64
0x18000a2ff  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a304  nop
0x18000a305  add     rsp, 48h
0x18000a309  retn
```
