# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140005d30`
- end: `0x140005d91`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000492c`
- `0x140004998`
- `0x140005d98`
- `0x140007f74`
- `0x14000c010`
- `0x14000c0b8`

## callees

- `0x140004a74`
- `0x140005d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d47`

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
0x140005d30  mov     [rsp+arg_0], rbx
0x140005d35  mov     [rsp+arg_8], rsi
0x140005d3a  push    rdi
0x140005d3b  sub     rsp, 40h
0x140005d3f  mov     rbx, r8
0x140005d42  mov     edi, edx
0x140005d44  mov     rsi, rcx
0x140005d47  call    cs:__imp_GetLastError
0x140005d4d  test    eax, eax
0x140005d4f  jnz     short loc_140005D81
0x140005d51  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140005d59  mov     rax, [rsp+48h+arg_28]
0x140005d5e  mov     [rsp+48h+var_20], rax; __int64
0x140005d63  mov     [rsp+48h+var_28], 0; __int64
0x140005d6c  xor     r9d, r9d; int
0x140005d6f  mov     r8, rbx; int
0x140005d72  mov     edx, edi; int
0x140005d74  mov     rcx, rsi; int
0x140005d77  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005d7c  mov     eax, 29Ch
0x140005d81  mov     rbx, [rsp+48h+arg_0]
0x140005d86  mov     rsi, [rsp+48h+arg_8]
0x140005d8b  add     rsp, 40h
0x140005d8f  pop     rdi
0x140005d90  retn
```
