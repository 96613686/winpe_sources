# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180004bc4`
- end: `0x180004be2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180003018`
- `0x1800033e8`
- `0x180003fa4`
- `0x18000560c`
- `0x180007620`
- `0x180007700`
- `0x180007780`
- `0x180007aa0`
- `0x180007de0`
- `0x1800084e0`
- `0x180008550`
- `0x180008de0`
- `0x1800097b0`
- `0x1800097f0`
- `0x180009830`
- `0x180009870`
- `0x1800098b0`
- `0x1800098f0`
- `0x180009930`
- `0x180009970`

## callees

- `0x180002434`

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
0x180004bc4  sub     rsp, 48h
0x180004bc8  mov     rax, [rsp+48h]
0x180004bcd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180004bd2  mov     [rsp+48h+var_20], rax; __int64
0x180004bd7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004bdc  nop
0x180004bdd  add     rsp, 48h
0x180004be1  retn
```
