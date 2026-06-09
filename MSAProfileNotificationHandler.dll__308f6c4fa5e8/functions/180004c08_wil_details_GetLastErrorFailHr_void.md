# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004c08`
- end: `0x180004c59`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ff8`
- `0x18000439c`

## callees

- `0x1800032a4`
- `0x180004c08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c13`

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
0x180004c08  push    rbx
0x180004c0a  sub     rsp, 40h
0x180004c0e  mov     rbx, [rsp+48h]
0x180004c13  call    cs:__imp_GetLastError
0x180004c19  test    eax, eax
0x180004c1b  jnz     short loc_180004C47
0x180004c1d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004c25  mov     [rsp+48h+var_20], rbx; __int64
0x180004c2a  mov     [rsp+48h+var_28], 0; __int64
0x180004c33  xor     r9d, r9d; int
0x180004c36  xor     r8d, r8d; int
0x180004c39  xor     edx, edx; int
0x180004c3b  xor     ecx, ecx; int
0x180004c3d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004c42  mov     eax, 29Ch
0x180004c47  test    eax, eax
0x180004c49  jle     short loc_180004C53
0x180004c4b  movzx   eax, ax
0x180004c4e  or      eax, 80070000h
0x180004c53  add     rsp, 40h
0x180004c57  pop     rbx
0x180004c58  retn
```
