# wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)

- ea: `0x180009e78`
- end: `0x180009e91`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c557`
- `0x18000c5b1`
- `0x18000c5e7`
- `0x18000c69c`

## callees

- `0x180007c2c`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  return wil::details::ReportFailure_CaughtException<2>((int)this, (int)a2, a3, (__int64)a4, v5, retaddr);
}

```

## disassembly

```asm
0x180009e78  sub     rsp, 48h
0x180009e7c  mov     rax, [rsp+48h]
0x180009e81  mov     [rsp+48h+var_20], rax
0x180009e86  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x180009e8b  nop
0x180009e8c  add     rsp, 48h
0x180009e90  retn
```
