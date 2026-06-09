# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140004160`
- end: `0x1400041c1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022dc`
- `0x140002354`
- `0x1400041c8`

## callees

- `0x140002424`
- `0x140004160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004177`

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
0x140004160  mov     [rsp+arg_0], rbx
0x140004165  mov     [rsp+arg_8], rsi
0x14000416a  push    rdi
0x14000416b  sub     rsp, 40h
0x14000416f  mov     rbx, r8
0x140004172  mov     edi, edx
0x140004174  mov     rsi, rcx
0x140004177  call    cs:__imp_GetLastError
0x14000417d  test    eax, eax
0x14000417f  jnz     short loc_1400041B1
0x140004181  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140004189  mov     rax, [rsp+48h+arg_28]
0x14000418e  mov     [rsp+48h+var_20], rax; __int64
0x140004193  mov     [rsp+48h+var_28], 0; __int64
0x14000419c  xor     r9d, r9d; int
0x14000419f  mov     r8, rbx; int
0x1400041a2  mov     edx, edi; int
0x1400041a4  mov     rcx, rsi; int
0x1400041a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400041ac  mov     eax, 29Ch
0x1400041b1  mov     rbx, [rsp+48h+arg_0]
0x1400041b6  mov     rsi, [rsp+48h+arg_8]
0x1400041bb  add     rsp, 40h
0x1400041bf  pop     rdi
0x1400041c0  retn
```
