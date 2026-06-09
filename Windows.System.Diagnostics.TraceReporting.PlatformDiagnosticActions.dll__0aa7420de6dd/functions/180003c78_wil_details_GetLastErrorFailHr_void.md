# wil::details::GetLastErrorFailHr(void)

- ea: `0x180003c78`
- end: `0x180003cc9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003018`
- `0x1800033e8`

## callees

- `0x18000248c`
- `0x180003c78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c83`

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
0x180003c78  push    rbx
0x180003c7a  sub     rsp, 40h
0x180003c7e  mov     rbx, [rsp+48h]
0x180003c83  call    cs:__imp_GetLastError
0x180003c89  test    eax, eax
0x180003c8b  jnz     short loc_180003CB7
0x180003c8d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003c95  mov     [rsp+48h+var_20], rbx; __int64
0x180003c9a  mov     [rsp+48h+var_28], 0; __int64
0x180003ca3  xor     r9d, r9d; int
0x180003ca6  xor     r8d, r8d; int
0x180003ca9  xor     edx, edx; int
0x180003cab  xor     ecx, ecx; int
0x180003cad  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003cb2  mov     eax, 29Ch
0x180003cb7  test    eax, eax
0x180003cb9  jle     short loc_180003CC3
0x180003cbb  movzx   eax, ax
0x180003cbe  or      eax, 80070000h
0x180003cc3  add     rsp, 40h
0x180003cc7  pop     rbx
0x180003cc8  retn
```
