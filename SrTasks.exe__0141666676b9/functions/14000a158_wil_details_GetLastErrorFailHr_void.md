# wil::details::GetLastErrorFailHr(void)

- ea: `0x14000a158`
- end: `0x14000a1a6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008c5c`
- `0x140009000`
- `0x1400093d0`

## callees

- `0x140007e60`
- `0x14000a158`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a15c`
- `KERNEL32!GetLastError` at `0x14000a15c`

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
0x14000a158  sub     rsp, 48h
0x14000a15c  call    cs:__imp_GetLastError
0x14000a162  test    eax, eax
0x14000a164  jnz     short loc_14000A197
0x14000a166  mov     rax, [rsp+48h]
0x14000a16b  xor     r9d, r9d; int
0x14000a16e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x14000a176  xor     r8d, r8d; int
0x14000a179  mov     [rsp+48h+var_20], rax; __int64
0x14000a17e  xor     edx, edx; int
0x14000a180  xor     ecx, ecx; int
0x14000a182  mov     [rsp+48h+var_28], 0; __int64
0x14000a18b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a190  mov     eax, 29Ch
0x14000a195  jmp     short loc_14000A199
0x14000a197  jle     short loc_14000A1A1
0x14000a199  movzx   eax, ax
0x14000a19c  or      eax, 80070000h
0x14000a1a1  add     rsp, 48h
0x14000a1a5  retn
```
