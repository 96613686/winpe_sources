# wil::details::GetLastErrorFailHr(void)

- ea: `0x140003e98`
- end: `0x140003ee6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000323c`
- `0x1400035e0`

## callees

- `0x14000293c`
- `0x140003e98`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003e9c`
- `KERNEL32!GetLastError` at `0x140003e9c`

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
0x140003e98  sub     rsp, 48h
0x140003e9c  call    cs:__imp_GetLastError
0x140003ea2  test    eax, eax
0x140003ea4  jnz     short loc_140003ED7
0x140003ea6  mov     rax, [rsp+48h]
0x140003eab  xor     r9d, r9d; int
0x140003eae  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003eb6  xor     r8d, r8d; int
0x140003eb9  mov     [rsp+48h+var_20], rax; __int64
0x140003ebe  xor     edx, edx; int
0x140003ec0  xor     ecx, ecx; int
0x140003ec2  mov     [rsp+48h+var_28], 0; __int64
0x140003ecb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003ed0  mov     eax, 29Ch
0x140003ed5  jmp     short loc_140003ED9
0x140003ed7  jle     short loc_140003EE1
0x140003ed9  movzx   eax, ax
0x140003edc  or      eax, 80070000h
0x140003ee1  add     rsp, 48h
0x140003ee5  retn
```
