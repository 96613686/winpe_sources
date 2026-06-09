# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x1400064d0`
- end: `0x1400064e9`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bd4`
- `0x140007e3c`
- `0x140008628`
- `0x1400088ac`

## callees

- `0x1400030e4`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1400064d0  sub     rsp, 48h
0x1400064d4  mov     rax, [rsp+48h]
0x1400064d9  mov     [rsp+48h+var_18], r9d
0x1400064de  mov     [rsp+48h+var_20], rax
0x1400064e3  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
