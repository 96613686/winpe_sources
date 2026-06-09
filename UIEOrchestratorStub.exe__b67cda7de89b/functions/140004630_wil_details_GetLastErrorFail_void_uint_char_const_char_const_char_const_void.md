# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140004630`
- end: `0x140004691`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d70`
- `0x140006934`
- `0x1400069ac`

## callees

- `0x140002ee0`
- `0x140004630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004647`

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
0x140004630  mov     [rsp+arg_0], rbx
0x140004635  mov     [rsp+arg_8], rsi
0x14000463a  push    rdi
0x14000463b  sub     rsp, 40h
0x14000463f  mov     rbx, r8
0x140004642  mov     edi, edx
0x140004644  mov     rsi, rcx
0x140004647  call    cs:__imp_GetLastError
0x14000464d  test    eax, eax
0x14000464f  jnz     short loc_140004681
0x140004651  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140004659  mov     rax, [rsp+48h+arg_28]
0x14000465e  mov     [rsp+48h+var_20], rax; __int64
0x140004663  mov     [rsp+48h+var_28], 0; __int64
0x14000466c  xor     r9d, r9d; int
0x14000466f  mov     r8, rbx; int
0x140004672  mov     edx, edi; int
0x140004674  mov     rcx, rsi; int
0x140004677  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000467c  mov     eax, 29Ch
0x140004681  mov     rbx, [rsp+48h+arg_0]
0x140004686  mov     rsi, [rsp+48h+arg_8]
0x14000468b  add     rsp, 40h
0x14000468f  pop     rdi
0x140004690  retn
```
