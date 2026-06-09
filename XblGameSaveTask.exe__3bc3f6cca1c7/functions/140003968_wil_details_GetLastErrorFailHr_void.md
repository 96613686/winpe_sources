# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003968`
- end: `0x1400039b9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d58`
- `0x1400030fc`

## callees

- `0x1400021fc`
- `0x140003968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003973`

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
0x140003968  push    rbx
0x14000396a  sub     rsp, 40h
0x14000396e  mov     rbx, [rsp+48h]
0x140003973  call    cs:__imp_GetLastError
0x140003979  test    eax, eax
0x14000397b  jnz     short loc_1400039A7
0x14000397d  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003985  mov     [rsp+48h+var_20], rbx; __int64
0x14000398a  mov     [rsp+48h+var_28], 0; __int64
0x140003993  xor     r9d, r9d; int
0x140003996  xor     r8d, r8d; int
0x140003999  xor     edx, edx; int
0x14000399b  xor     ecx, ecx; int
0x14000399d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400039a2  mov     eax, 29Ch
0x1400039a7  test    eax, eax
0x1400039a9  jle     short loc_1400039B3
0x1400039ab  movzx   eax, ax
0x1400039ae  or      eax, 80070000h
0x1400039b3  add     rsp, 40h
0x1400039b7  pop     rbx
0x1400039b8  retn
```
