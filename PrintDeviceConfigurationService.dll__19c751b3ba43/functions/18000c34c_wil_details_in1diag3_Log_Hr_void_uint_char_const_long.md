# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000c34c`
- end: `0x18000c37d`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000bac8`
- `0x18000c4a0`

## callees

- `0x18000418c`

## string_xrefs

- `0x18000c36b`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\printdeviceconfigurationservice.cpp`

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
    (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000c34c  sub     rsp, 48h
0x18000c350  mov     rax, [rsp+48h]
0x18000c355  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000c35a  mov     [rsp+48h+var_20], rax; __int64
0x18000c35f  mov     [rsp+48h+var_28], 0; __int64
0x18000c368  xor     r9d, r9d; int
0x18000c36b  lea     r8, aPrintscanPrint_0; "printscan\\print\\spooler\\configuratio"...
0x18000c372  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c377  nop
0x18000c378  add     rsp, 48h
0x18000c37c  retn
```
