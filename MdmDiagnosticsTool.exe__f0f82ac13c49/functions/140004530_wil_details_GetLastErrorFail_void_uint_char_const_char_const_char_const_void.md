# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140004530`
- end: `0x140004591`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002428`
- `0x1400024a0`
- `0x140004598`

## callees

- `0x14000256c`
- `0x140004530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004547`

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
0x140004530  mov     [rsp+arg_0], rbx
0x140004535  mov     [rsp+arg_8], rsi
0x14000453a  push    rdi
0x14000453b  sub     rsp, 40h
0x14000453f  mov     rbx, r8
0x140004542  mov     edi, edx
0x140004544  mov     rsi, rcx
0x140004547  call    cs:__imp_GetLastError
0x14000454d  test    eax, eax
0x14000454f  jnz     short loc_140004581
0x140004551  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140004559  mov     rax, [rsp+48h+arg_28]
0x14000455e  mov     [rsp+48h+var_20], rax; __int64
0x140004563  mov     [rsp+48h+var_28], 0; __int64
0x14000456c  xor     r9d, r9d; int
0x14000456f  mov     r8, rbx; int
0x140004572  mov     edx, edi; int
0x140004574  mov     rcx, rsi; int
0x140004577  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000457c  mov     eax, 29Ch
0x140004581  mov     rbx, [rsp+48h+arg_0]
0x140004586  mov     rsi, [rsp+48h+arg_8]
0x14000458b  add     rsp, 40h
0x14000458f  pop     rdi
0x140004590  retn
```
