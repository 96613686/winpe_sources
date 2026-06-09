# wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)

- ea: `0x180029764`
- end: `0x180029789`
- name: `?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z`
- size: `37`
- prototype: `unsigned int __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180029170`

## callees

- `0x1800287e8`

## string_xrefs

- `0x180029772`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastError<2>(
           (int)this,
           148,
           (int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uisetti"
                "ngscontroller.cpp",
           (int)a4,
           v5,
           retaddr);
}

```

## disassembly

```asm
0x180029764  sub     rsp, 38h
0x180029768  mov     rax, [rsp+38h]
0x18002976d  mov     [rsp+38h+var_10], rax; char *
0x180029772  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180029779  mov     edx, 94h; int
0x18002977e  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x180029783  nop
0x180029784  add     rsp, 38h
0x180029788  retn
```
