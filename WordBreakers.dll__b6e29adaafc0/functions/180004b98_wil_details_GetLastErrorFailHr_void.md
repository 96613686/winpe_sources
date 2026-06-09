# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004b98`
- end: `0x180004be9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f90`
- `0x180004334`
- `0x180007dd8`

## callees

- `0x180003220`
- `0x180004b98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ba3`

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
0x180004b98  push    rbx
0x180004b9a  sub     rsp, 40h
0x180004b9e  mov     rbx, [rsp+48h]
0x180004ba3  call    cs:__imp_GetLastError
0x180004ba9  test    eax, eax
0x180004bab  jnz     short loc_180004BD7
0x180004bad  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004bb5  mov     [rsp+48h+var_20], rbx; __int64
0x180004bba  mov     [rsp+48h+var_28], 0; __int64
0x180004bc3  xor     r9d, r9d; int
0x180004bc6  xor     r8d, r8d; int
0x180004bc9  xor     edx, edx; int
0x180004bcb  xor     ecx, ecx; int
0x180004bcd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004bd2  mov     eax, 29Ch
0x180004bd7  test    eax, eax
0x180004bd9  jle     short loc_180004BE3
0x180004bdb  movzx   eax, ax
0x180004bde  or      eax, 80070000h
0x180004be3  add     rsp, 40h
0x180004be7  pop     rbx
0x180004be8  retn
```
