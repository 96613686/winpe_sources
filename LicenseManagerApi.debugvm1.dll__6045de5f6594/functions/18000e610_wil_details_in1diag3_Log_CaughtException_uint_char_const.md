# wil::details::in1diag3::Log_CaughtException(uint,char const *)

- ea: `0x18000e610`
- end: `0x18000e62b`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJIPEBD@Z`
- size: `27`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, unsigned int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180012311`
- `0x180012348`
- `0x1800123c7`
- `0x18001240f`
- `0x180012457`
- `0x1800124b1`
- `0x18001251d`
- `0x180012577`

## callees

- `0x1800065e8`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_CaughtException(
        wil::details::in1diag3 *this,
        __int64 a2,
        const char *a3,
        int a4)
{
  return wil::details::ReportFailure_CaughtException<2>((_DWORD)this, (_DWORD)this, (_DWORD)a3, a4);
}

```

## disassembly

```asm
0x18000e610  sub     rsp, 48h
0x18000e614  mov     rax, [rsp+48h]
0x18000e619  mov     [rsp+48h+var_20], rax
0x18000e61e  mov     edx, ecx
0x18000e620  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x18000e625  nop
0x18000e626  add     rsp, 48h
0x18000e62a  retn
```
