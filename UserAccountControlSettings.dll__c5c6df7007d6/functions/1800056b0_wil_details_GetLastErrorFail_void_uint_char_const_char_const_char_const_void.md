# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800056b0`
- end: `0x180005711`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004330`
- `0x1800043a0`
- `0x180005718`

## callees

- `0x180004468`
- `0x1800056b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c7`

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
0x1800056b0  mov     [rsp+arg_0], rbx
0x1800056b5  mov     [rsp+arg_8], rsi
0x1800056ba  push    rdi
0x1800056bb  sub     rsp, 40h
0x1800056bf  mov     rbx, r8
0x1800056c2  mov     edi, edx
0x1800056c4  mov     rsi, rcx
0x1800056c7  call    cs:__imp_GetLastError
0x1800056cd  test    eax, eax
0x1800056cf  jnz     short loc_180005701
0x1800056d1  mov     rax, [rsp+48h+arg_28]
0x1800056d6  xor     r9d, r9d; int
0x1800056d9  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800056e1  mov     r8, rbx; int
0x1800056e4  mov     [rsp+48h+var_20], rax; __int64
0x1800056e9  mov     edx, edi; int
0x1800056eb  mov     rcx, rsi; int
0x1800056ee  mov     [rsp+48h+var_28], 0; __int64
0x1800056f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800056fc  mov     eax, 29Ch
0x180005701  mov     rbx, [rsp+48h+arg_0]
0x180005706  mov     rsi, [rsp+48h+arg_8]
0x18000570b  add     rsp, 40h
0x18000570f  pop     rdi
0x180005710  retn
```
