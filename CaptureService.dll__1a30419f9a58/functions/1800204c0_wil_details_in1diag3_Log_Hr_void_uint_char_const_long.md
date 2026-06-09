# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x1800204c0`
- end: `0x1800204fc`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020504`

## callees

- `0x1800047a4`

## string_xrefs

- `0x1800204cb`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

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
    214,
    (int)"onecoreuap\\windows\\dwm\\common\\util\\utillib\\debugbreak.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800204c0  push    rbx
0x1800204c2  sub     rsp, 40h
0x1800204c6  mov     rax, [rsp+48h]
0x1800204cb  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\dwm\\common\\util"...
0x1800204d2  mov     ebx, r9d
0x1800204d5  mov     edx, 0D6h; int
0x1800204da  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x1800204de  xor     r9d, r9d; int
0x1800204e1  mov     [rsp+48h+var_20], rax; __int64
0x1800204e6  mov     [rsp+48h+var_28], 0; __int64
0x1800204ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800204f4  mov     eax, ebx
0x1800204f6  add     rsp, 40h
0x1800204fa  pop     rbx
0x1800204fb  retn
```
