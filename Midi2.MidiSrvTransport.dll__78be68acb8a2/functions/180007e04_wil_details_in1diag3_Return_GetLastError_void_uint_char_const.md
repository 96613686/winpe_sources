# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180007e04`
- end: `0x180007e1d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fa4`
- `0x18000893c`
- `0x18000d504`
- `0x18000f144`
- `0x18000f570`
- `0x180010260`
- `0x180010b10`

## callees

- `0x180003194`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x180007e04  sub     rsp, 38h
0x180007e08  mov     rax, [rsp+38h]
0x180007e0d  mov     [rsp+38h+var_10], rax
0x180007e12  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180007e17  nop
0x180007e18  add     rsp, 38h
0x180007e1c  retn
```
