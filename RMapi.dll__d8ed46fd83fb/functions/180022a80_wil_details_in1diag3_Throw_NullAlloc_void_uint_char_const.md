# wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)

- ea: `0x180022a80`
- end: `0x180022aa3`
- name: `?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001df88`
- `0x18001ecb0`

## callees

- `0x1800109b0`

## string_xrefs

- `0x180022a89`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

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
    (_DWORD)a2,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x180022a80  sub     rsp, 48h
0x180022a84  mov     rax, [rsp+48h]
0x180022a89  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180022a90  mov     [rsp+48h+var_18], 8007000Eh
0x180022a98  mov     [rsp+48h+var_20], rax
0x180022a9d  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
