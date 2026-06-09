# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800075b8`
- end: `0x180007609`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060bc`
- `0x180006460`
- `0x180006830`

## callees

- `0x180004f70`
- `0x1800075b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075c3`

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
0x1800075b8  push    rbx
0x1800075ba  sub     rsp, 40h
0x1800075be  mov     rbx, [rsp+48h]
0x1800075c3  call    cs:__imp_GetLastError
0x1800075c9  test    eax, eax
0x1800075cb  jnz     short loc_1800075F7
0x1800075cd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800075d5  mov     [rsp+48h+var_20], rbx; __int64
0x1800075da  mov     [rsp+48h+var_28], 0; __int64
0x1800075e3  xor     r9d, r9d; int
0x1800075e6  xor     r8d, r8d; int
0x1800075e9  xor     edx, edx; int
0x1800075eb  xor     ecx, ecx; int
0x1800075ed  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800075f2  mov     eax, 29Ch
0x1800075f7  test    eax, eax
0x1800075f9  jle     short loc_180007603
0x1800075fb  movzx   eax, ax
0x1800075fe  or      eax, 80070000h
0x180007603  add     rsp, 40h
0x180007607  pop     rbx
0x180007608  retn
```
