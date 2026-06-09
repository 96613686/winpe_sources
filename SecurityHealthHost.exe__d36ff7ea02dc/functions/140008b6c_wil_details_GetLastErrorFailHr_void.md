# wil::details::GetLastErrorFailHr(void)

- ea: `0x140008b6c`
- end: `0x140008bbd`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400078ec`
- `0x140007cbc`
- `0x1400080b4`

## callees

- `0x1400057b8`
- `0x140008b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b77`

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
0x140008b6c  push    rbx
0x140008b6e  sub     rsp, 40h
0x140008b72  mov     rbx, [rsp+48h]
0x140008b77  call    cs:__imp_GetLastError
0x140008b7d  test    eax, eax
0x140008b7f  jnz     short loc_140008BAB
0x140008b81  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140008b89  mov     [rsp+48h+var_20], rbx; __int64
0x140008b8e  mov     [rsp+48h+var_28], 0; __int64
0x140008b97  xor     r9d, r9d; int
0x140008b9a  xor     r8d, r8d; int
0x140008b9d  xor     edx, edx; int
0x140008b9f  xor     ecx, ecx; int
0x140008ba1  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140008ba6  mov     eax, 29Ch
0x140008bab  test    eax, eax
0x140008bad  jle     short loc_140008BB7
0x140008baf  movzx   eax, ax
0x140008bb2  or      eax, 80070000h
0x140008bb7  add     rsp, 40h
0x140008bbb  pop     rbx
0x140008bbc  retn
```
