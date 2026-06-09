# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x14000d4b8`
- end: `0x14000d4ee`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d4f4`

## callees

- `0x140002dac`

## string_xrefs

- `0x14000d4d7`: `shell\oobe\user\exe\useroobebroker.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    138,
    (int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x14000d4b8  sub     rsp, 48h
0x14000d4bc  mov     rax, [rsp+48h]
0x14000d4c1  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x14000d4c6  mov     [rsp+48h+var_20], rax; __int64
0x14000d4cb  mov     [rsp+48h+var_28], 0; __int64
0x14000d4d4  xor     r9d, r9d; int
0x14000d4d7  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000d4de  mov     edx, 8Ah; int
0x14000d4e3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000d4e8  nop
0x14000d4e9  add     rsp, 48h
0x14000d4ed  retn
```
