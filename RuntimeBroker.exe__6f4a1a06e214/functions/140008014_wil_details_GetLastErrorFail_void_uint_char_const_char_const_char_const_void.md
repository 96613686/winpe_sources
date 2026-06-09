# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140008014`
- end: `0x140008075`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, void *, unsigned int, const char *, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f58`
- `0x140007f8c`
- `0x14000a38c`

## callees

- `0x140008014`
- `0x14000a460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000802b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000802b`

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
  unsigned int v7; // edi
  int v8; // esi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (unsigned int)a2;
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
0x140008014  mov     [rsp+arg_0], rbx
0x140008019  mov     [rsp+arg_8], rsi
0x14000801e  push    rdi
0x14000801f  sub     rsp, 40h
0x140008023  mov     rbx, r8
0x140008026  mov     edi, edx
0x140008028  mov     rsi, rcx
0x14000802b  call    cs:__imp_GetLastError
0x140008031  test    eax, eax
0x140008033  jnz     short loc_140008065
0x140008035  mov     rax, [rsp+48h+arg_28]
0x14000803a  xor     r9d, r9d; int
0x14000803d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140008045  mov     r8, rbx; int
0x140008048  mov     [rsp+48h+var_20], rax; __int64
0x14000804d  mov     edx, edi; int
0x14000804f  mov     rcx, rsi; int
0x140008052  mov     [rsp+48h+var_28], 0; __int64
0x14000805b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140008060  mov     eax, 29Ch
0x140008065  mov     rbx, [rsp+48h+arg_0]
0x14000806a  mov     rsi, [rsp+48h+arg_8]
0x14000806f  add     rsp, 40h
0x140008073  pop     rdi
0x140008074  retn
```
