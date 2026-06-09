# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400047b0`
- end: `0x140004818`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `104`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002484`
- `0x1400024fc`
- `0x140004820`

## callees

- `0x1400025c8`
- `0x1400047b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400047c7`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        int a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  int v7; // edi
  int v8; // esi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
  v8 = (int)this;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>(v8, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x1400047b0  mov     [rsp+arg_0], rbx
0x1400047b5  mov     [rsp+arg_8], rsi
0x1400047ba  push    rdi
0x1400047bb  sub     rsp, 40h
0x1400047bf  mov     rbx, r8
0x1400047c2  mov     edi, edx
0x1400047c4  mov     rsi, rcx
0x1400047c7  call    cs:__imp_GetLastError
0x1400047ce  nop     dword ptr [rax+rax+00h]
0x1400047d3  test    eax, eax
0x1400047d5  jnz     short loc_140004807
0x1400047d7  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400047df  mov     rax, [rsp+48h+arg_28]
0x1400047e4  mov     [rsp+48h+var_20], rax; __int64
0x1400047e9  mov     [rsp+48h+var_28], 0; __int64
0x1400047f2  xor     r9d, r9d; int
0x1400047f5  mov     r8, rbx; int
0x1400047f8  mov     edx, edi; int
0x1400047fa  mov     rcx, rsi; int
0x1400047fd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004802  mov     eax, 29Ch
0x140004807  mov     rbx, [rsp+48h+arg_0]
0x14000480c  mov     rsi, [rsp+48h+arg_8]
0x140004811  add     rsp, 40h
0x140004815  pop     rdi
0x140004816  retn
```
