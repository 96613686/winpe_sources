# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x1800088f0`
- end: `0x180008927`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `55`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800085b0`
- `0x18000b5dc`

## callees

- `0x180002cc4`

## string_xrefs

- `0x1800088fb`: `shell\deviceux\contexthandlers\removedevice\src\contexthandler.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  unsigned int v4; // ebx
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  v4 = (unsigned int)a4;
  LODWORD(v6) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"shell\\deviceux\\contexthandlers\\removedevice\\src\\contexthandler.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800088f0  push    rbx
0x1800088f2  sub     rsp, 40h
0x1800088f6  mov     rax, [rsp+48h]
0x1800088fb  lea     r8, aShellDeviceuxC; "shell\\deviceux\\contexthandlers\\remov"...
0x180008902  mov     ebx, r9d
0x180008905  xor     r9d, r9d; int
0x180008908  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18000890c  mov     [rsp+48h+var_20], rax; __int64
0x180008911  mov     [rsp+48h+var_28], 0; __int64
0x18000891a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000891f  mov     eax, ebx
0x180008921  add     rsp, 40h
0x180008925  pop     rbx
0x180008926  retn
```
