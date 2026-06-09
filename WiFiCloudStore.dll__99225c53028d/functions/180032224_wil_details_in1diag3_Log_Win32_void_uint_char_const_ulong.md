# wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)

- ea: `0x180032224`
- end: `0x18003224e`
- name: `?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `42`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010e7c`

## callees

- `0x180024590`

## string_xrefs

- `0x180032237`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Win32(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Win32<2>(
    (int)this,
    455,
    (int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
    (int)a4,
    v4,
    retaddr,
    v5);
}

```

## disassembly

```asm
0x180032224  sub     rsp, 48h
0x180032228  mov     rax, [rsp+48h]
0x18003222d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180032232  mov     [rsp+48h+var_20], rax; __int64
0x180032237  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003223e  mov     edx, 1C7h; int
0x180032243  call    ??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x180032248  nop
0x180032249  add     rsp, 48h
0x18003224d  retn
```
