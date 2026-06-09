# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180011e70`
- end: `0x180011ea1`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x180002ab0`

## string_xrefs

- `0x180011e8f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.Private.CacheManagement\ModelCacheManager.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (__int64)this,
    (int)a2,
    (__int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Private.CacheManagement\\ModelCacheManager.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180011e70  sub     rsp, 48h
0x180011e74  mov     rax, [rsp+48h]
0x180011e79  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180011e7e  mov     [rsp+48h+var_20], rax; __int64
0x180011e83  mov     [rsp+48h+var_28], 0; __int64
0x180011e8c  xor     r9d, r9d; int
0x180011e8f  lea     r8, aCW1SProductApi; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180011e96  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180011e9b  nop
0x180011e9c  add     rsp, 48h
0x180011ea0  retn
```
