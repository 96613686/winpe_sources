# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x18000672c`
- end: `0x18000674a`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `30`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `49`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021dc`
- `0x180002244`
- `0x18000230c`
- `0x18000237c`
- `0x1800023f0`
- `0x1800024a8`
- `0x180002524`
- `0x1800025a0`
- `0x180002608`
- `0x180002670`
- `0x1800026e0`
- `0x180002748`
- `0x180002814`
- `0x180002884`
- `0x1800028f4`
- `0x180002970`
- `0x180002a18`
- `0x180002a98`
- `0x180002b20`
- `0x180002be8`
- `0x180002c50`
- `0x180002cb8`
- `0x180002d20`
- `0x180002d88`
- `0x180002e04`
- `0x180002e8c`
- `0x180002efc`
- `0x18000a660`
- `0x18000aa64`
- `0x18000aacc`
- `0x18000b494`
- `0x18000b4fc`
- `0x18000b578`
- `0x18000b5e8`
- `0x18000b650`
- `0x18000b6b8`
- `0x18000b720`
- `0x18000b788`
- `0x18000b7f0`
- `0x18000b874`
- `0x18000b8ec`
- `0x18000b954`
- `0x18000b9bc`
- `0x18000ba24`
- `0x18000cbac`
- `0x18000cc10`
- `0x18000cc78`
- `0x18000cd0c`
- `0x18000d9e8`

## callees

- `0x180003a80`

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
0x18000672c  sub     rsp, 48h
0x180006730  mov     rax, [rsp+48h]
0x180006735  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000673a  mov     [rsp+48h+var_20], rax; __int64
0x18000673f  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x180006744  nop
0x180006745  add     rsp, 48h
0x180006749  retn
```
