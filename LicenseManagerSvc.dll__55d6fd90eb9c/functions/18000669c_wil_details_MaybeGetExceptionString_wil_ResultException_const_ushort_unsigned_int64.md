# wil::details::MaybeGetExceptionString(wil::ResultException const &,ushort *,unsigned __int64)

- ea: `0x18000669c`
- end: `0x1800066bf`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVResultException@2@PEAG_K@Z`
- size: `35`
- prototype: `void(wil::details *__hidden this, const struct wil::ResultException *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180017684`
- `0x180017792`
- `0x180017922`
- `0x180017ac9`

## callees

- `0x180005794`
- `0x18000669c`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct wil::ResultException *a2,
        unsigned __int16 *a3)
{
  if ( a2 )
    wil::GetFailureLogString(a2, a3, (__int64)this + 24, (const struct wil::FailureInfo *)a3);
}

```

## disassembly

```asm
0x18000669c  sub     rsp, 28h
0x1800066a0  mov     r9, r8; struct wil::FailureInfo *
0x1800066a3  mov     rax, rdx
0x1800066a6  test    rdx, rdx
0x1800066a9  jz      short loc_1800066BA
0x1800066ab  lea     r8, [rcx+18h]; unsigned __int64
0x1800066af  mov     rdx, r9; unsigned __int16 *
0x1800066b2  mov     rcx, rax; this
0x1800066b5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800066ba  add     rsp, 28h
0x1800066be  retn
```
