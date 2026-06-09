# wil::details::GetLastErrorFailHr(void)

- ea: `0x180006378`
- end: `0x1800063c9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003eb0`
- `0x180004254`
- `0x1800046b0`

## callees

- `0x180002854`
- `0x180006378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006383`

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
0x180006378  push    rbx
0x18000637a  sub     rsp, 40h
0x18000637e  mov     rbx, [rsp+48h]
0x180006383  call    cs:__imp_GetLastError
0x180006389  test    eax, eax
0x18000638b  jnz     short loc_1800063B7
0x18000638d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180006395  mov     [rsp+48h+var_20], rbx; __int64
0x18000639a  mov     [rsp+48h+var_28], 0; __int64
0x1800063a3  xor     r9d, r9d; int
0x1800063a6  xor     r8d, r8d; int
0x1800063a9  xor     edx, edx; int
0x1800063ab  xor     ecx, ecx; int
0x1800063ad  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800063b2  mov     eax, 29Ch
0x1800063b7  test    eax, eax
0x1800063b9  jle     short loc_1800063C3
0x1800063bb  movzx   eax, ax
0x1800063be  or      eax, 80070000h
0x1800063c3  add     rsp, 40h
0x1800063c7  pop     rbx
0x1800063c8  retn
```
