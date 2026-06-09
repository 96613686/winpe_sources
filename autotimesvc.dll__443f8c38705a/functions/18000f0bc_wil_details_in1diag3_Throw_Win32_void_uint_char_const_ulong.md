# wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x18000f0bc`
- end: `0x18000f0d5`
- name: `?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e048`
- `0x18000e440`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000efb8`

## callees

- `0x18000d930`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Win32<0>((__int64)this, (int)a2, a3, (__int64)a4, v5, retaddr, (int)a4);
}

```

## disassembly

```asm
0x18000f0bc  sub     rsp, 48h
0x18000f0c0  mov     rax, [rsp+48h]
0x18000f0c5  mov     [rsp+48h+var_18], r9d
0x18000f0ca  mov     [rsp+48h+var_20], rax
0x18000f0cf  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
