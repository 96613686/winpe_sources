# wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)

- ea: `0x18002dcc8`
- end: `0x18002dced`
- name: `?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `37`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d9e4`

## callees

- `0x1800287e8`

## string_xrefs

- `0x18002dcd6`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<2>(
    (int)this,
    310,
    (int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x18002dcc8  sub     rsp, 38h
0x18002dccc  mov     rax, [rsp+38h]
0x18002dcd1  mov     [rsp+38h+var_10], rax; char *
0x18002dcd6  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002dcdd  mov     edx, 136h; int
0x18002dce2  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x18002dce7  nop
0x18002dce8  add     rsp, 38h
0x18002dcec  retn
```
