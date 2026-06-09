# wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x1800267d8`
- end: `0x1800267fd`
- name: `?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800265ec`

## callees

- `0x180015f60`

## string_xrefs

- `0x1800267e1`: `onecore\windows\directx\dxg\common\etwtracesession\traceeventinfo.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>(
    (_DWORD)this,
    28,
    (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\traceeventinfo.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800267d8  sub     rsp, 48h
0x1800267dc  mov     rax, [rsp+48h]
0x1800267e1  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\dxg\\common"...
0x1800267e8  mov     [rsp+48h+var_18], r9d
0x1800267ed  mov     edx, 1Ch
0x1800267f2  mov     [rsp+48h+var_20], rax
0x1800267f7  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
