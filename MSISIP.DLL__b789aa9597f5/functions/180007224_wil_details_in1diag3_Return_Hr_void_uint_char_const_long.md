# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180007224`
- end: `0x18000724b`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007640`
- `0x1800077a8`
- `0x180007910`
- `0x180007b28`
- `0x18000983c`
- `0x180009990`
- `0x18000b6e4`
- `0x18000ca58`

## callees

- `0x18000a670`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-38h]
  wil::details *v5; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180007224  sub     rsp, 58h
0x180007228  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x180007231  mov     rax, [rsp+58h]
0x180007236  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x18000723b  mov     [rsp+58h+var_30], rax; __int64
0x180007240  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007245  nop
0x180007246  add     rsp, 58h
0x18000724a  retn
```
