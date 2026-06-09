# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800052d8`
- end: `0x180005329`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045b8`
- `0x180004988`
- `0x18000896c`
- `0x18000cad4`
- `0x180010444`

## callees

- `0x180003a20`
- `0x1800052d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052e3`

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
0x1800052d8  push    rbx
0x1800052da  sub     rsp, 40h
0x1800052de  mov     rbx, [rsp+48h]
0x1800052e3  call    cs:__imp_GetLastError
0x1800052e9  test    eax, eax
0x1800052eb  jnz     short loc_180005317
0x1800052ed  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800052f5  mov     [rsp+48h+var_20], rbx; __int64
0x1800052fa  mov     [rsp+48h+var_28], 0; __int64
0x180005303  xor     r9d, r9d; int
0x180005306  xor     r8d, r8d; int
0x180005309  xor     edx, edx; int
0x18000530b  xor     ecx, ecx; int
0x18000530d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005312  mov     eax, 29Ch
0x180005317  test    eax, eax
0x180005319  jle     short loc_180005323
0x18000531b  movzx   eax, ax
0x18000531e  or      eax, 80070000h
0x180005323  add     rsp, 40h
0x180005327  pop     rbx
0x180005328  retn
```
