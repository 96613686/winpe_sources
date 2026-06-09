# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003bc0`
- end: `0x180003c28`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `104`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002470`
- `0x1800024f0`
- `0x180003c30`

## callees

- `0x1800025d0`
- `0x180003bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd7`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  unsigned int v7; // edi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (unsigned int)a2;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>((__int64)this, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_0], rbx
0x180003bc5  mov     [rsp+arg_8], rsi
0x180003bca  push    rdi
0x180003bcb  sub     rsp, 40h
0x180003bcf  mov     rbx, r8
0x180003bd2  mov     edi, edx
0x180003bd4  mov     rsi, rcx
0x180003bd7  call    cs:__imp_GetLastError
0x180003bde  nop     dword ptr [rax+rax+00h]
0x180003be3  test    eax, eax
0x180003be5  jnz     short loc_180003C17
0x180003be7  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003bef  mov     rax, [rsp+48h+arg_28]
0x180003bf4  mov     [rsp+48h+var_20], rax; __int64
0x180003bf9  mov     [rsp+48h+var_28], 0; __int64
0x180003c02  xor     r9d, r9d; int
0x180003c05  mov     r8, rbx; int
0x180003c08  mov     edx, edi; int
0x180003c0a  mov     rcx, rsi; int
0x180003c0d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003c12  mov     eax, 29Ch
0x180003c17  mov     rbx, [rsp+48h+arg_0]
0x180003c1c  mov     rsi, [rsp+48h+arg_8]
0x180003c21  add     rsp, 40h
0x180003c25  pop     rdi
0x180003c26  retn
```
