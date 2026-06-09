# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140006224`
- end: `0x14000623d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003670`
- `0x140004f98`
- `0x140005b1c`
- `0x140006a1c`

## callees

- `0x1400024a0`

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
0x140006224  sub     rsp, 38h
0x140006228  mov     rax, [rsp+38h]
0x14000622d  mov     [rsp+38h+var_10], rax
0x140006232  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140006237  nop
0x140006238  add     rsp, 38h
0x14000623c  retn
```
