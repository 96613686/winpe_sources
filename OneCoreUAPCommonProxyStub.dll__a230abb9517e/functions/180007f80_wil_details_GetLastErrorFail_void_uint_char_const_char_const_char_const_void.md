# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180007f80`
- end: `0x180007fe1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006168`
- `0x1800061e8`
- `0x180006260`
- `0x180007fe8`

## callees

- `0x180006348`
- `0x180007f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f97`

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
0x180007f80  mov     [rsp+arg_0], rbx
0x180007f85  mov     [rsp+arg_8], rsi
0x180007f8a  push    rdi
0x180007f8b  sub     rsp, 40h
0x180007f8f  mov     rbx, r8
0x180007f92  mov     edi, edx
0x180007f94  mov     rsi, rcx
0x180007f97  call    cs:__imp_GetLastError
0x180007f9d  test    eax, eax
0x180007f9f  jnz     short loc_180007FD1
0x180007fa1  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180007fa9  mov     rax, [rsp+48h+arg_28]
0x180007fae  mov     [rsp+48h+var_20], rax; __int64
0x180007fb3  mov     [rsp+48h+var_28], 0; __int64
0x180007fbc  xor     r9d, r9d; int
0x180007fbf  mov     r8, rbx; int
0x180007fc2  mov     edx, edi; int
0x180007fc4  mov     rcx, rsi; int
0x180007fc7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007fcc  mov     eax, 29Ch
0x180007fd1  mov     rbx, [rsp+48h+arg_0]
0x180007fd6  mov     rsi, [rsp+48h+arg_8]
0x180007fdb  add     rsp, 40h
0x180007fdf  pop     rdi
0x180007fe0  retn
```
