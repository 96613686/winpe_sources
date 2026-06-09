# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140005684`
- end: `0x1400056a6`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `34`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004bd4`
- `0x140005f40`
- `0x14000a1dc`
- `0x140024fe0`
- `0x140025660`
- `0x140025b30`

## callees

- `0x140003404`

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
0x140005684  sub     rsp, 48h
0x140005688  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x140005691  mov     rax, [rsp+48h]
0x140005696  mov     [rsp+48h+var_20], rax
0x14000569b  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400056a0  nop
0x1400056a1  add     rsp, 48h
0x1400056a5  retn
```
