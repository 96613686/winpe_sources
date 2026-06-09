# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800042b8`
- end: `0x180004309`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034b8`
- `0x180003888`

## callees

- `0x180002870`
- `0x1800042b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042c3`

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
0x1800042b8  push    rbx
0x1800042ba  sub     rsp, 40h
0x1800042be  mov     rbx, [rsp+48h]
0x1800042c3  call    cs:__imp_GetLastError
0x1800042c9  test    eax, eax
0x1800042cb  jnz     short loc_1800042F7
0x1800042cd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800042d5  mov     [rsp+48h+var_20], rbx; __int64
0x1800042da  mov     [rsp+48h+var_28], 0; __int64
0x1800042e3  xor     r9d, r9d; int
0x1800042e6  xor     r8d, r8d; int
0x1800042e9  xor     edx, edx; int
0x1800042eb  xor     ecx, ecx; int
0x1800042ed  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800042f2  mov     eax, 29Ch
0x1800042f7  test    eax, eax
0x1800042f9  jle     short loc_180004303
0x1800042fb  movzx   eax, ax
0x1800042fe  or      eax, 80070000h
0x180004303  add     rsp, 40h
0x180004307  pop     rbx
0x180004308  retn
```
