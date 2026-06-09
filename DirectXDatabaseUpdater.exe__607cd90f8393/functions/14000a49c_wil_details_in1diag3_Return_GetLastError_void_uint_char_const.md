# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x14000a49c`
- end: `0x14000a4b5`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140006c80`
- `0x140007980`
- `0x140007ad8`
- `0x14000b0cc`
- `0x14000d0bc`
- `0x14000fa90`
- `0x14000ff7c`
- `0x1400100e0`
- `0x140011418`
- `0x1400122f8`
- `0x140014be4`

## callees

- `0x140004460`

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
0x14000a49c  sub     rsp, 38h
0x14000a4a0  mov     rax, [rsp+38h]
0x14000a4a5  mov     [rsp+38h+var_10], rax
0x14000a4aa  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x14000a4af  nop
0x14000a4b0  add     rsp, 38h
0x14000a4b4  retn
```
