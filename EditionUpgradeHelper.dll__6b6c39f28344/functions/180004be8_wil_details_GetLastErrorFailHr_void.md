# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004be8`
- end: `0x180004c36`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036f4`
- `0x180003a98`
- `0x180003e68`

## callees

- `0x1800028b0`
- `0x180004be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bec`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    LOWORD(result) = 668;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x180004be8  sub     rsp, 48h
0x180004bec  call    cs:__imp_GetLastError
0x180004bf2  test    eax, eax
0x180004bf4  jnz     short loc_180004C27
0x180004bf6  mov     rax, [rsp+48h]
0x180004bfb  xor     r9d, r9d; int
0x180004bfe  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004c06  xor     r8d, r8d; int
0x180004c09  mov     [rsp+48h+var_20], rax; __int64
0x180004c0e  xor     edx, edx; int
0x180004c10  xor     ecx, ecx; int
0x180004c12  mov     [rsp+48h+var_28], 0; __int64
0x180004c1b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004c20  mov     eax, 29Ch
0x180004c25  jmp     short loc_180004C29
0x180004c27  jle     short loc_180004C31
0x180004c29  movzx   eax, ax
0x180004c2c  or      eax, 80070000h
0x180004c31  add     rsp, 48h
0x180004c35  retn
```
