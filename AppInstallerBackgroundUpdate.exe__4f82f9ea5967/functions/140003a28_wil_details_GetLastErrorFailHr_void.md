# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003a28`
- end: `0x140003a79`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d18`
- `0x1400030e8`
- `0x140006064`

## callees

- `0x1400021bc`
- `0x140003a28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a33`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( !result )
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    result = 668;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140003a28  push    rbx
0x140003a2a  sub     rsp, 40h
0x140003a2e  mov     rbx, [rsp+48h]
0x140003a33  call    cs:__imp_GetLastError
0x140003a39  test    eax, eax
0x140003a3b  jnz     short loc_140003A67
0x140003a3d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003a45  mov     [rsp+48h+var_20], rbx; __int64
0x140003a4a  mov     [rsp+48h+var_28], 0; __int64
0x140003a53  xor     r9d, r9d; int
0x140003a56  xor     r8d, r8d; int
0x140003a59  xor     edx, edx; int
0x140003a5b  xor     ecx, ecx; int
0x140003a5d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003a62  mov     eax, 29Ch
0x140003a67  test    eax, eax
0x140003a69  jle     short loc_140003A73
0x140003a6b  movzx   eax, ax
0x140003a6e  or      eax, 80070000h
0x140003a73  add     rsp, 40h
0x140003a77  pop     rbx
0x140003a78  retn
```
