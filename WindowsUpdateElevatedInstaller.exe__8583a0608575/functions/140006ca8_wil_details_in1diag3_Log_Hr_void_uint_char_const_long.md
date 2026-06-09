# wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)

- ea: `0x140006ca8`
- end: `0x140006ce3`
- name: `?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z`
- size: `59`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007574`

## callees

- `0x1400021b8`

## string_xrefs

- `0x140006ccb`: `onecore\enduser\windowsupdate\muse\orchestrator\common\lib\usocommon\registrymanager.cpp`

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
    44,
    (__int64)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\common\\lib\\usocommon\\registrymanager.cpp",
    0,
    0,
    retaddr,
    v6);
  return v4;
}

```

## disassembly

```asm
0x140006ca8  push    rbx
0x140006caa  sub     rsp, 40h
0x140006cae  mov     ebx, r9d
0x140006cb1  mov     rax, [rsp+48h]
0x140006cb6  mov     dword ptr [rsp+48h+var_18], ebx; wil::details *
0x140006cba  mov     [rsp+48h+var_20], rax; __int64
0x140006cbf  mov     [rsp+48h+var_28], 0; __int64
0x140006cc8  xor     r9d, r9d; int
0x140006ccb  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x140006cd2  lea     edx, [r9+2Ch]; int
0x140006cd6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006cdb  mov     eax, ebx
0x140006cdd  add     rsp, 40h
0x140006ce1  pop     rbx
0x140006ce2  retn
```
