# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x18000989c`
- end: `0x1800098bb`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `31`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008948`
- `0x180008a9c`
- `0x180008d10`
- `0x1800095fc`
- `0x18000d4b0`

## callees

- `0x180007304`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_Win32(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x18000989c  sub     rsp, 48h
0x1800098a0  mov     rax, [rsp+48h]
0x1800098a5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800098aa  mov     [rsp+48h+var_20], rax; __int64
0x1800098af  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x1800098b4  nop
0x1800098b5  add     rsp, 48h
0x1800098b9  retn
```
