# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18001ff24`
- end: `0x18001ff49`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001df88`

## callees

- `0x1800109b0`

## string_xrefs

- `0x18001ff2d`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    1890,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001ff24  sub     rsp, 48h
0x18001ff28  mov     rax, [rsp+48h]
0x18001ff2d  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001ff34  mov     [rsp+48h+var_18], r9d
0x18001ff39  mov     edx, 762h
0x18001ff3e  mov     [rsp+48h+var_20], rax
0x18001ff43  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
