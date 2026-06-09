# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x180010c70`
- end: `0x180010cac`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `60`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007e10`
- `0x1800108d0`
- `0x180010cb0`

## callees

- `0x180002ab0`

## string_xrefs

- `0x180010c93`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.142\inc\wil\opensource\wil\result.h`

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
    (__int64)this,
    958,
    (__int64)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.142\\inc\\wil\\opensource\\wil\\result.h",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180010c70  push    rbx
0x180010c72  sub     rsp, 40h
0x180010c76  mov     ebx, r9d
0x180010c79  mov     rax, [rsp+48h]
0x180010c7e  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x180010c82  mov     [rsp+48h+var_20], rax; __int64
0x180010c87  mov     [rsp+48h+var_28], 0; __int64
0x180010c90  xor     r9d, r9d; int
0x180010c93  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180010c9a  mov     edx, 3BEh; int
0x180010c9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180010ca4  mov     eax, ebx
0x180010ca6  add     rsp, 40h
0x180010caa  pop     rbx
0x180010cab  retn
```
