# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400062f4`
- end: `0x14000630c`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400059c0`
- `0x140006700`

## callees

- `0x1400040a4`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x1400062f4  sub     rsp, 38h
0x1400062f8  mov     rax, [rsp+38h]
0x1400062fd  mov     [rsp+38h+var_10], rax
0x140006302  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140006307  add     rsp, 38h
0x14000630b  retn
```
