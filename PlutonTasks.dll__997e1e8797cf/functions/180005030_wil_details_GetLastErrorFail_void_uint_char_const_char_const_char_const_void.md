# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180005030`
- end: `0x180005091`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002af4`
- `0x180002b6c`
- `0x180005098`

## callees

- `0x180002c34`
- `0x180005030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005047`

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
0x180005030  mov     [rsp+arg_0], rbx
0x180005035  mov     [rsp+arg_8], rsi
0x18000503a  push    rdi
0x18000503b  sub     rsp, 40h
0x18000503f  mov     rbx, r8
0x180005042  mov     edi, edx
0x180005044  mov     rsi, rcx
0x180005047  call    cs:__imp_GetLastError
0x18000504d  test    eax, eax
0x18000504f  jnz     short loc_180005081
0x180005051  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005059  mov     rax, [rsp+48h+arg_28]
0x18000505e  mov     [rsp+48h+var_20], rax; __int64
0x180005063  mov     [rsp+48h+var_28], 0; __int64
0x18000506c  xor     r9d, r9d; int
0x18000506f  mov     r8, rbx; int
0x180005072  mov     edx, edi; int
0x180005074  mov     rcx, rsi; int
0x180005077  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000507c  mov     eax, 29Ch
0x180005081  mov     rbx, [rsp+48h+arg_0]
0x180005086  mov     rsi, [rsp+48h+arg_8]
0x18000508b  add     rsp, 40h
0x18000508f  pop     rdi
0x180005090  retn
```
