# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x14001a970`
- end: `0x14001a998`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400187e0`

## callees

- `0x14000f678`

## string_xrefs

- `0x14001a979`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    87,
    (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x14001a970  sub     rsp, 48h
0x14001a974  mov     rax, [rsp+48h]
0x14001a979  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001a980  mov     [rsp+48h+var_18], 8007000Eh
0x14001a988  mov     edx, 57h ; 'W'
0x14001a98d  mov     [rsp+48h+var_20], rax
0x14001a992  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
