# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400030a0`
- end: `0x140003101`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b50`

## callees

- `0x140001cb8`
- `0x1400030a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400030b7`
- `KERNEL32!GetLastError` at `0x1400030b7`

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
0x1400030a0  mov     [rsp+arg_0], rbx
0x1400030a5  mov     [rsp+arg_8], rsi
0x1400030aa  push    rdi
0x1400030ab  sub     rsp, 40h
0x1400030af  mov     rbx, r8
0x1400030b2  mov     edi, edx
0x1400030b4  mov     rsi, rcx
0x1400030b7  call    cs:__imp_GetLastError
0x1400030bd  test    eax, eax
0x1400030bf  jnz     short loc_1400030F1
0x1400030c1  mov     rax, [rsp+48h+arg_28]
0x1400030c6  xor     r9d, r9d; int
0x1400030c9  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400030d1  mov     r8, rbx; int
0x1400030d4  mov     [rsp+48h+var_20], rax; __int64
0x1400030d9  mov     edx, edi; int
0x1400030db  mov     rcx, rsi; int
0x1400030de  mov     [rsp+48h+var_28], 0; __int64
0x1400030e7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400030ec  mov     eax, 29Ch
0x1400030f1  mov     rbx, [rsp+48h+arg_0]
0x1400030f6  mov     rsi, [rsp+48h+arg_8]
0x1400030fb  add     rsp, 40h
0x1400030ff  pop     rdi
0x140003100  retn
```
