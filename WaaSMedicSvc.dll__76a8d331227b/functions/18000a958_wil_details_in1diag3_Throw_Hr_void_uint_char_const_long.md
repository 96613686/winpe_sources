# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000a958`
- end: `0x18000a97d`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b900`
- `0x18000b9d0`
- `0x18000bac0`

## callees

- `0x180007438`

## string_xrefs

- `0x18000a961`: `onecore\enduser\windowsupdate\undocked\stubdlls\UndockedDllForwarder.hpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    35,
    (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\UndockedDllForwarder.hpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000a958  sub     rsp, 48h
0x18000a95c  mov     rax, [rsp+48h]
0x18000a961  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\undock"...
0x18000a968  mov     [rsp+48h+var_18], r9d
0x18000a96d  mov     edx, 23h ; '#'
0x18000a972  mov     [rsp+48h+var_20], rax
0x18000a977  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
