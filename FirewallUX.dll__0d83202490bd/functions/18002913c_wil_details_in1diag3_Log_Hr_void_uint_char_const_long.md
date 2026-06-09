# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x18002913c`
- end: `0x180029173`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `55`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027268`

## callees

- `0x1800042b8`

## string_xrefs

- `0x18002915f`: `shellcommon\shell\networkux\firewallux\lib\utils.cpp`

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
    (int)a2,
    (__int64)"shellcommon\\shell\\networkux\\firewallux\\lib\\utils.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18002913c  push    rbx
0x18002913e  sub     rsp, 40h
0x180029142  mov     ebx, r9d
0x180029145  mov     rax, [rsp+48h]
0x18002914a  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x18002914e  mov     [rsp+48h+var_20], rax; __int64
0x180029153  mov     [rsp+48h+var_28], 0; __int64
0x18002915c  xor     r9d, r9d; int
0x18002915f  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\networkux\\firewall"...
0x180029166  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002916b  mov     eax, ebx
0x18002916d  add     rsp, 40h
0x180029171  pop     rbx
0x180029172  retn
```
