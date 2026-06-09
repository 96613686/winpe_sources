# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x18000a304`
- end: `0x18000a32c`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `40`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009800`
- `0x18000f65c`

## callees

- `0x180008058`

## string_xrefs

- `0x18000a30d`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_NullAlloc(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    63,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000a304  sub     rsp, 48h
0x18000a308  mov     rax, [rsp+48h]
0x18000a30d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a314  mov     [rsp+48h+var_18], 8007000Eh
0x18000a31c  mov     edx, 3Fh ; '?'
0x18000a321  mov     [rsp+48h+var_20], rax
0x18000a326  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
