# wil::details::GetLastErrorFailHr(void)

- ea: `0x180003b68`
- end: `0x180003bb9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f08`
- `0x1800032d8`

## callees

- `0x1800023ac`
- `0x180003b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b73`

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
0x180003b68  push    rbx
0x180003b6a  sub     rsp, 40h
0x180003b6e  mov     rbx, [rsp+48h]
0x180003b73  call    cs:__imp_GetLastError
0x180003b79  test    eax, eax
0x180003b7b  jnz     short loc_180003BA7
0x180003b7d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180003b85  mov     [rsp+48h+var_20], rbx; __int64
0x180003b8a  mov     [rsp+48h+var_28], 0; __int64
0x180003b93  xor     r9d, r9d; int
0x180003b96  xor     r8d, r8d; int
0x180003b99  xor     edx, edx; int
0x180003b9b  xor     ecx, ecx; int
0x180003b9d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003ba2  mov     eax, 29Ch
0x180003ba7  test    eax, eax
0x180003ba9  jle     short loc_180003BB3
0x180003bab  movzx   eax, ax
0x180003bae  or      eax, 80070000h
0x180003bb3  add     rsp, 40h
0x180003bb7  pop     rbx
0x180003bb8  retn
```
