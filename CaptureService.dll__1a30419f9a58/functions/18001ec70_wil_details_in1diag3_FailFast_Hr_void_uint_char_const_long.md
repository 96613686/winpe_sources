# wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)

- ea: `0x18001ec70`
- end: `0x18001ec90`
- name: `?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001e748`
- `0x18001f484`

## callees

- `0x180004808`

## string_xrefs

- `0x18001ec83`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::FailFast_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<3>(
    (_DWORD)this,
    (_DWORD)a2,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001ec70  sub     rsp, 48h
0x18001ec74  mov     rax, [rsp+48h]
0x18001ec79  mov     [rsp+48h+var_18], r9d
0x18001ec7e  mov     [rsp+48h+var_20], rax
0x18001ec83  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ec8a  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
