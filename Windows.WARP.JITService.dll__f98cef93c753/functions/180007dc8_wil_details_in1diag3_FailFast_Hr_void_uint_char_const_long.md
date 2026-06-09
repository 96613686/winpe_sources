# wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)

- ea: `0x180007dc8`
- end: `0x180007ded`
- name: `?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006670`

## callees

- `0x180002d04`

## string_xrefs

- `0x180007ddb`: `Microsoft.Direct3DUndocked\src\warp\service\linkdll\service.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<3>(
    (__int64)this,
    92,
    (__int64)"Microsoft.Direct3DUndocked\\src\\warp\\service\\linkdll\\service.cpp",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x180007dc8  sub     rsp, 48h
0x180007dcc  mov     rax, [rsp+48h]
0x180007dd1  mov     [rsp+48h+var_18], r9d
0x180007dd6  mov     [rsp+48h+var_20], rax
0x180007ddb  lea     r8, aMicrosoftDirec; "Microsoft.Direct3DUndocked\\src\\warp\\"...
0x180007de2  mov     edx, 5Ch ; '\'
0x180007de7  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
