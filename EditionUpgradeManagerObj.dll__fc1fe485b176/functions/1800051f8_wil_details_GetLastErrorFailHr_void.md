# wil::details::GetLastErrorFailHr(void)

- ea: `0x1800051f8`
- end: `0x180005246`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bc4`
- `0x180003f94`
- `0x18000438c`
- `0x180017b1c`

## callees

- `0x180002c3c`
- `0x1800051f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051fc`

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
0x1800051f8  sub     rsp, 48h
0x1800051fc  call    cs:__imp_GetLastError
0x180005202  test    eax, eax
0x180005204  jnz     short loc_180005237
0x180005206  mov     rax, [rsp+48h]
0x18000520b  xor     r9d, r9d; int
0x18000520e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005216  xor     r8d, r8d; int
0x180005219  mov     [rsp+48h+var_20], rax; __int64
0x18000521e  xor     edx, edx; int
0x180005220  xor     ecx, ecx; int
0x180005222  mov     [rsp+48h+var_28], 0; __int64
0x18000522b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005230  mov     eax, 29Ch
0x180005235  jmp     short loc_180005239
0x180005237  jle     short loc_180005241
0x180005239  movzx   eax, ax
0x18000523c  or      eax, 80070000h
0x180005241  add     rsp, 48h
0x180005245  retn
```
