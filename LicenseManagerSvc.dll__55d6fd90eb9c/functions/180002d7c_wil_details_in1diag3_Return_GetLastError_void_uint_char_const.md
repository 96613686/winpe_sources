# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180002d7c`
- end: `0x180002d95`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a44`
- `0x180001ea0`
- `0x180002908`
- `0x180005d80`

## callees

- `0x180001bb0`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180002d7c  sub     rsp, 38h
0x180002d80  mov     rax, [rsp+38h]
0x180002d85  mov     [rsp+38h+var_10], rax
0x180002d8a  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180002d8f  nop
0x180002d90  add     rsp, 38h
0x180002d94  retn
```
