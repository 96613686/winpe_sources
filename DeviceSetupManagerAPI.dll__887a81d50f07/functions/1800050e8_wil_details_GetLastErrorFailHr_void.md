# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800050e8`
- end: `0x180005139`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bf8`
- `0x180003f9c`
- `0x18000436c`

## callees

- `0x180002a1c`
- `0x1800050e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f3`

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
0x1800050e8  push    rbx
0x1800050ea  sub     rsp, 40h
0x1800050ee  mov     rbx, [rsp+48h]
0x1800050f3  call    cs:__imp_GetLastError
0x1800050f9  test    eax, eax
0x1800050fb  jnz     short loc_180005127
0x1800050fd  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005105  mov     [rsp+48h+var_20], rbx; __int64
0x18000510a  mov     [rsp+48h+var_28], 0; __int64
0x180005113  xor     r9d, r9d; int
0x180005116  xor     r8d, r8d; int
0x180005119  xor     edx, edx; int
0x18000511b  xor     ecx, ecx; int
0x18000511d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005122  mov     eax, 29Ch
0x180005127  test    eax, eax
0x180005129  jle     short loc_180005133
0x18000512b  movzx   eax, ax
0x18000512e  or      eax, 80070000h
0x180005133  add     rsp, 40h
0x180005137  pop     rbx
0x180005138  retn
```
