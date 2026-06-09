# wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x18002dbd8`
- end: `0x18002dbfd`
- name: `?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002da88`

## callees

- `0x1800288f0`

## string_xrefs

- `0x18002dbe1`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>(
    (_DWORD)this,
    70,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18002dbd8  sub     rsp, 48h
0x18002dbdc  mov     rax, [rsp+48h]
0x18002dbe1  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002dbe8  mov     [rsp+48h+var_18], r9d
0x18002dbed  mov     edx, 46h ; 'F'
0x18002dbf2  mov     [rsp+48h+var_20], rax
0x18002dbf7  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
