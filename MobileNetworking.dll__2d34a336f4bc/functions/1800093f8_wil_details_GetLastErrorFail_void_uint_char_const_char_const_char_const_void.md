# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800093f8`
- end: `0x180009459`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000917c`
- `0x1800091b0`
- `0x18000f3a4`

## callees

- `0x1800093f8`
- `0x18000f464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000940f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000940f`

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
0x1800093f8  mov     [rsp+arg_0], rbx
0x1800093fd  mov     [rsp+arg_8], rsi
0x180009402  push    rdi
0x180009403  sub     rsp, 40h
0x180009407  mov     rbx, r8
0x18000940a  mov     edi, edx
0x18000940c  mov     rsi, rcx
0x18000940f  call    cs:__imp_GetLastError
0x180009415  test    eax, eax
0x180009417  jnz     short loc_180009449
0x180009419  mov     rax, [rsp+48h+arg_28]
0x18000941e  xor     r9d, r9d; int
0x180009421  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180009429  mov     r8, rbx; int
0x18000942c  mov     [rsp+48h+var_20], rax; __int64
0x180009431  mov     edx, edi; int
0x180009433  mov     rcx, rsi; int
0x180009436  mov     [rsp+48h+var_28], 0; __int64
0x18000943f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009444  mov     eax, 29Ch
0x180009449  mov     rbx, [rsp+48h+arg_0]
0x18000944e  mov     rsi, [rsp+48h+arg_8]
0x180009453  add     rsp, 40h
0x180009457  pop     rdi
0x180009458  retn
```
