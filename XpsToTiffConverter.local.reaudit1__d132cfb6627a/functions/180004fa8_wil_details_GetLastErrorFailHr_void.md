# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004fa8`
- end: `0x180004ff9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ab8`
- `0x180003e5c`
- `0x18000422c`

## callees

- `0x1800026b8`
- `0x180004fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180004fa8  push    rbx
0x180004faa  sub     rsp, 40h
0x180004fae  mov     rbx, [rsp+48h]
0x180004fb3  call    cs:__imp_GetLastError
0x180004fb9  test    eax, eax
0x180004fbb  jnz     short loc_180004FE7
0x180004fbd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004fc5  mov     [rsp+48h+var_20], rbx; __int64
0x180004fca  mov     [rsp+48h+var_28], 0; __int64
0x180004fd3  xor     r9d, r9d; int
0x180004fd6  xor     r8d, r8d; int
0x180004fd9  xor     edx, edx; int
0x180004fdb  xor     ecx, ecx; int
0x180004fdd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004fe2  mov     eax, 29Ch
0x180004fe7  test    eax, eax
0x180004fe9  jle     short loc_180004FF3
0x180004feb  movzx   eax, ax
0x180004fee  or      eax, 80070000h
0x180004ff3  add     rsp, 40h
0x180004ff7  pop     rbx
0x180004ff8  retn
```
