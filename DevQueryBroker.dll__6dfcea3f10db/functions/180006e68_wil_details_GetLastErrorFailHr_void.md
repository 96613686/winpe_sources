# wil::details::GetLastErrorFailHr(void)

- ea: `0x180006e68`
- end: `0x180006eb6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000596c`
- `0x180005d10`
- `0x1800060e0`

## callees

- `0x180004b70`
- `0x180006e68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e6c`

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
0x180006e68  sub     rsp, 48h
0x180006e6c  call    cs:__imp_GetLastError
0x180006e72  test    eax, eax
0x180006e74  jnz     short loc_180006EA7
0x180006e76  mov     rax, [rsp+48h]
0x180006e7b  xor     r9d, r9d; int
0x180006e7e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180006e86  xor     r8d, r8d; int
0x180006e89  mov     [rsp+48h+var_20], rax; __int64
0x180006e8e  xor     edx, edx; int
0x180006e90  xor     ecx, ecx; int
0x180006e92  mov     [rsp+48h+var_28], 0; __int64
0x180006e9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ea0  mov     eax, 29Ch
0x180006ea5  jmp     short loc_180006EA9
0x180006ea7  jle     short loc_180006EB1
0x180006ea9  movzx   eax, ax
0x180006eac  or      eax, 80070000h
0x180006eb1  add     rsp, 48h
0x180006eb5  retn
```
