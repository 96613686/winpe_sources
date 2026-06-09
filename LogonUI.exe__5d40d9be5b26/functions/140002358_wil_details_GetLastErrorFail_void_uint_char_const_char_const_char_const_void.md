# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140002358`
- end: `0x1400023b9`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, void *, unsigned int, const char *, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400020dc`
- `0x140002110`
- `0x140003588`

## callees

- `0x140002358`
- `0x140003650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000236f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000236f`

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
0x140002358  mov     [rsp+arg_0], rbx
0x14000235d  mov     [rsp+arg_8], rsi
0x140002362  push    rdi
0x140002363  sub     rsp, 40h
0x140002367  mov     rbx, r8
0x14000236a  mov     edi, edx
0x14000236c  mov     rsi, rcx
0x14000236f  call    cs:__imp_GetLastError
0x140002375  test    eax, eax
0x140002377  jnz     short loc_1400023A9
0x140002379  mov     rax, [rsp+48h+arg_28]
0x14000237e  xor     r9d, r9d; int
0x140002381  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140002389  mov     r8, rbx; int
0x14000238c  mov     [rsp+48h+var_20], rax; __int64
0x140002391  mov     edx, edi; int
0x140002393  mov     rcx, rsi; int
0x140002396  mov     [rsp+48h+var_28], 0; __int64
0x14000239f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400023a4  mov     eax, 29Ch
0x1400023a9  mov     rbx, [rsp+48h+arg_0]
0x1400023ae  mov     rsi, [rsp+48h+arg_8]
0x1400023b3  add     rsp, 40h
0x1400023b7  pop     rdi
0x1400023b8  retn
```
