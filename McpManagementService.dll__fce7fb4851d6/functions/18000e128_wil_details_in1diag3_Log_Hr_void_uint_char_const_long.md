# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000e128`
- end: `0x18000e15e`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d58c`

## callees

- `0x180005f1c`

## string_xrefs

- `0x18000e147`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    161,
    (int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000e128  sub     rsp, 48h
0x18000e12c  mov     rax, [rsp+48h]
0x18000e131  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000e136  mov     [rsp+48h+var_20], rax; __int64
0x18000e13b  mov     [rsp+48h+var_28], 0; __int64
0x18000e144  xor     r9d, r9d; int
0x18000e147  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000e14e  mov     edx, 0A1h; int
0x18000e153  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e158  nop
0x18000e159  add     rsp, 48h
0x18000e15d  retn
```
