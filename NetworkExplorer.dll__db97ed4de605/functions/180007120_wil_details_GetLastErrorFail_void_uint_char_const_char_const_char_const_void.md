# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180007120`
- end: `0x180007181`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, void *, unsigned int, const char *, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e9c`
- `0x180006ed0`
- `0x1800080a0`

## callees

- `0x180007120`
- `0x180008160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007137`

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
0x180007120  mov     [rsp+arg_0], rbx
0x180007125  mov     [rsp+arg_8], rsi
0x18000712a  push    rdi
0x18000712b  sub     rsp, 40h
0x18000712f  mov     rbx, r8
0x180007132  mov     edi, edx
0x180007134  mov     rsi, rcx
0x180007137  call    cs:__imp_GetLastError
0x18000713d  test    eax, eax
0x18000713f  jnz     short loc_180007171
0x180007141  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180007149  mov     rax, [rsp+48h+arg_28]
0x18000714e  mov     [rsp+48h+var_20], rax; __int64
0x180007153  mov     [rsp+48h+var_28], 0; __int64
0x18000715c  xor     r9d, r9d; int
0x18000715f  mov     r8, rbx; int
0x180007162  mov     edx, edi; int
0x180007164  mov     rcx, rsi; int
0x180007167  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000716c  mov     eax, 29Ch
0x180007171  mov     rbx, [rsp+48h+arg_0]
0x180007176  mov     rsi, [rsp+48h+arg_8]
0x18000717b  add     rsp, 40h
0x18000717f  pop     rdi
0x180007180  retn
```
