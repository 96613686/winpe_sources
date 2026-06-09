# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003ae0`
- end: `0x180003b41`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002918`
- `0x180002990`
- `0x180003b48`
- `0x180007c9c`

## callees

- `0x180002a58`
- `0x180003ae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003af7`

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
0x180003ae0  mov     [rsp+arg_0], rbx
0x180003ae5  mov     [rsp+arg_8], rsi
0x180003aea  push    rdi
0x180003aeb  sub     rsp, 40h
0x180003aef  mov     rbx, r8
0x180003af2  mov     edi, edx
0x180003af4  mov     rsi, rcx
0x180003af7  call    cs:__imp_GetLastError
0x180003afd  test    eax, eax
0x180003aff  jnz     short loc_180003B31
0x180003b01  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003b09  mov     rax, [rsp+48h+arg_28]
0x180003b0e  mov     [rsp+48h+var_20], rax; __int64
0x180003b13  mov     [rsp+48h+var_28], 0; __int64
0x180003b1c  xor     r9d, r9d; int
0x180003b1f  mov     r8, rbx; int
0x180003b22  mov     edx, edi; int
0x180003b24  mov     rcx, rsi; int
0x180003b27  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003b2c  mov     eax, 29Ch
0x180003b31  mov     rbx, [rsp+48h+arg_0]
0x180003b36  mov     rsi, [rsp+48h+arg_8]
0x180003b3b  add     rsp, 40h
0x180003b3f  pop     rdi
0x180003b40  retn
```
