# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180007d38`
- end: `0x180007d6e`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800077c4`

## callees

- `0x180003250`

## string_xrefs

- `0x180007d57`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    161,
    (__int64)"onecore\\internal\\com\\inc\\comservicehelper.h",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180007d38  sub     rsp, 48h
0x180007d3c  mov     rax, [rsp+48h]
0x180007d41  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180007d46  mov     [rsp+48h+var_20], rax; __int64
0x180007d4b  mov     [rsp+48h+var_28], 0; __int64
0x180007d54  xor     r9d, r9d; int
0x180007d57  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180007d5e  mov     edx, 0A1h; int
0x180007d63  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007d68  nop
0x180007d69  add     rsp, 48h
0x180007d6d  retn
```
