# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000ce58`
- end: `0x18000ce82`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007510`
- `0x18000a450`
- `0x18000cad4`
- `0x18000edbc`
- `0x180010200`

## callees

- `0x180003a20`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((__int64)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x18000ce58  sub     rsp, 48h
0x18000ce5c  mov     rax, [rsp+48h]
0x18000ce61  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000ce66  mov     [rsp+48h+var_20], rax; __int64
0x18000ce6b  mov     [rsp+48h+var_28], 0; __int64
0x18000ce74  xor     r9d, r9d; int
0x18000ce77  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ce7c  nop
0x18000ce7d  add     rsp, 48h
0x18000ce81  retn
```
