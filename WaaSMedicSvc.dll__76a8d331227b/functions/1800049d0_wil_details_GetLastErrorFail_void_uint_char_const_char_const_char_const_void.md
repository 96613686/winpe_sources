# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800049d0`
- end: `0x180004a31`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030a4`
- `0x180007334`
- `0x1800073ac`

## callees

- `0x180003234`
- `0x1800049d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049e7`

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
  int v7; // edi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
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
0x1800049d0  mov     [rsp+arg_0], rbx
0x1800049d5  mov     [rsp+arg_8], rsi
0x1800049da  push    rdi
0x1800049db  sub     rsp, 40h
0x1800049df  mov     rbx, r8
0x1800049e2  mov     edi, edx
0x1800049e4  mov     rsi, rcx
0x1800049e7  call    cs:__imp_GetLastError
0x1800049ed  test    eax, eax
0x1800049ef  jnz     short loc_180004A21
0x1800049f1  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800049f9  mov     rax, [rsp+48h+arg_28]
0x1800049fe  mov     [rsp+48h+var_20], rax; __int64
0x180004a03  mov     [rsp+48h+var_28], 0; __int64
0x180004a0c  xor     r9d, r9d; int
0x180004a0f  mov     r8, rbx; int
0x180004a12  mov     edx, edi; int
0x180004a14  mov     rcx, rsi; int
0x180004a17  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004a1c  mov     eax, 29Ch
0x180004a21  mov     rbx, [rsp+48h+arg_0]
0x180004a26  mov     rsi, [rsp+48h+arg_8]
0x180004a2b  add     rsp, 40h
0x180004a2f  pop     rdi
0x180004a30  retn
```
