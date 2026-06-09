# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140006424`
- end: `0x140006446`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `34`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005a18`
- `0x140006f1c`
- `0x140010c94`
- `0x140011244`
- `0x140011440`
- `0x140011704`

## callees

- `0x1400039f8`

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
0x140006424  sub     rsp, 48h
0x140006428  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x140006431  mov     rax, [rsp+48h]
0x140006436  mov     [rsp+48h+var_20], rax
0x14000643b  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140006440  nop
0x140006441  add     rsp, 48h
0x140006445  retn
```
