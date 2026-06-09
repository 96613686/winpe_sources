# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003c60`
- end: `0x140003cc1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002834`
- `0x1400028b4`
- `0x140003cc8`

## callees

- `0x140002994`
- `0x140003c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c77`

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
0x140003c60  mov     [rsp+arg_0], rbx
0x140003c65  mov     [rsp+arg_8], rsi
0x140003c6a  push    rdi
0x140003c6b  sub     rsp, 40h
0x140003c6f  mov     rbx, r8
0x140003c72  mov     edi, edx
0x140003c74  mov     rsi, rcx
0x140003c77  call    cs:__imp_GetLastError
0x140003c7d  test    eax, eax
0x140003c7f  jnz     short loc_140003CB1
0x140003c81  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003c89  mov     rax, [rsp+48h+arg_28]
0x140003c8e  mov     [rsp+48h+var_20], rax; __int64
0x140003c93  mov     [rsp+48h+var_28], 0; __int64
0x140003c9c  xor     r9d, r9d; int
0x140003c9f  mov     r8, rbx; int
0x140003ca2  mov     edx, edi; int
0x140003ca4  mov     rcx, rsi; int
0x140003ca7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003cac  mov     eax, 29Ch
0x140003cb1  mov     rbx, [rsp+48h+arg_0]
0x140003cb6  mov     rsi, [rsp+48h+arg_8]
0x140003cbb  add     rsp, 40h
0x140003cbf  pop     rdi
0x140003cc0  retn
```
