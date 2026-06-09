# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x14001a9a0`
- end: `0x14001a9c5`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400192a0`

## callees

- `0x140006090`

## string_xrefs

- `0x14001a9a9`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>(
    (_DWORD)this,
    1159,
    (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x14001a9a0  sub     rsp, 48h
0x14001a9a4  mov     rax, [rsp+48h]
0x14001a9a9  lea     r8, aOnecoreVmCommo_3; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x14001a9b0  mov     [rsp+48h+var_18], r9d
0x14001a9b5  mov     edx, 487h
0x14001a9ba  mov     [rsp+48h+var_20], rax
0x14001a9bf  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
