# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000a4cc`
- end: `0x18000a4fd`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800081ac`
- `0x180009bb8`

## callees

- `0x180004268`

## string_xrefs

- `0x18000a4eb`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000a4cc  sub     rsp, 48h
0x18000a4d0  mov     rax, [rsp+48h]
0x18000a4d5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000a4da  mov     [rsp+48h+var_20], rax; __int64
0x18000a4df  mov     [rsp+48h+var_28], 0; __int64
0x18000a4e8  xor     r9d, r9d; int
0x18000a4eb  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x18000a4f2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a4f7  nop
0x18000a4f8  add     rsp, 48h
0x18000a4fc  retn
```
