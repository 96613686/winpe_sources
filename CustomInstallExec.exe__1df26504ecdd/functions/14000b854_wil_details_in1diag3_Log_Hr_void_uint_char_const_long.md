# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x14000b854`
- end: `0x14000b87e`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a43c`
- `0x14000e1e8`
- `0x14000e4d0`
- `0x14000e54c`
- `0x14000e61c`
- `0x14000e708`
- `0x14000e780`
- `0x14000e7f8`
- `0x14000e8c4`
- `0x14000e940`

## callees

- `0x140004a74`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x14000b854  sub     rsp, 48h
0x14000b858  mov     rax, [rsp+48h]
0x14000b85d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000b862  mov     [rsp+48h+var_20], rax; __int64
0x14000b867  mov     [rsp+48h+var_28], 0; __int64
0x14000b870  xor     r9d, r9d; int
0x14000b873  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000b878  nop
0x14000b879  add     rsp, 48h
0x14000b87d  retn
```
