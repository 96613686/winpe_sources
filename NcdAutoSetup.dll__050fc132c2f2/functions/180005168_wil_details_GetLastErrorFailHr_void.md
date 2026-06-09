# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005168`
- end: `0x1800051b6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a78`
- `0x180003e1c`
- `0x180004350`

## callees

- `0x1800029c4`
- `0x180005168`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000516c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000516c`

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
0x180005168  sub     rsp, 48h
0x18000516c  call    cs:__imp_GetLastError
0x180005172  test    eax, eax
0x180005174  jnz     short loc_1800051A7
0x180005176  mov     rax, [rsp+48h]
0x18000517b  xor     r9d, r9d; int
0x18000517e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005186  xor     r8d, r8d; int
0x180005189  mov     [rsp+48h+var_20], rax; __int64
0x18000518e  xor     edx, edx; int
0x180005190  xor     ecx, ecx; int
0x180005192  mov     [rsp+48h+var_28], 0; __int64
0x18000519b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800051a0  mov     eax, 29Ch
0x1800051a5  jmp     short loc_1800051A9
0x1800051a7  jle     short loc_1800051B1
0x1800051a9  movzx   eax, ax
0x1800051ac  or      eax, 80070000h
0x1800051b1  add     rsp, 48h
0x1800051b5  retn
```
