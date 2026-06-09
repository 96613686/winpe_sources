# wil::details::PrintLoggingMessage(ushort *,unsigned __int64,char const *,char *)

- ea: `0x180006360`
- end: `0x180006408`
- name: `?PrintLoggingMessage@details@wil@@YAXPEAG_KPEBDPEAD@Z`
- size: `168`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned __int16 *, unsigned __int64, const char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006050`

## callees

- `0x180006360`
- `0x180006410`
- `0x180006980`
- `0x180006a10`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800063ce`
- `msvcrt!_vsnwprintf` at `0x1800063ce`

## pseudocode

```c
void __fastcall wil::details::PrintLoggingMessage(wil::details *this, unsigned __int16 *a2, __int64 a3, va_list a4)
{
  wchar_t Format[2048]; // [rsp+20h] [rbp-1018h] BYREF

  if ( a3 )
  {
    if ( a4 )
    {
      StringCchPrintfW(Format, 0x800u, L"%hs", a3);
      if ( (unsigned int)_vsnwprintf((wchar_t *)this, 0x7FFu, Format, a4) > 0x7FE )
        *((_WORD *)this + 2047) = 0;
    }
    else
    {
      StringCchPrintfW((unsigned __int16 *)this, 0x800u, L"%hs", a3);
    }
  }
  else
  {
    *(_WORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180006360  mov     [rsp+arg_8], rbx
0x180006365  push    rdi
0x180006366  mov     eax, 1030h
0x18000636b  call    _alloca_probe
0x180006370  sub     rsp, rax
0x180006373  mov     rax, cs:__security_cookie
0x18000637a  xor     rax, rsp
0x18000637d  mov     [rsp+1038h+var_18], rax
0x180006385  mov     rdi, r9
0x180006388  mov     rbx, rcx
0x18000638b  test    r8, r8
0x18000638e  jnz     short loc_180006397
0x180006390  xor     eax, eax
0x180006392  mov     [rcx], ax
0x180006395  jmp     short loc_1800063E7
0x180006397  mov     r9, r8
0x18000639a  lea     r8, aHs_1; "%hs"
0x1800063a1  mov     edx, 800h; unsigned __int64
0x1800063a6  test    rdi, rdi
0x1800063a9  jnz     short loc_1800063B2
0x1800063ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800063b0  jmp     short loc_1800063E7
0x1800063b2  lea     rcx, [rsp+1038h+Format]; unsigned __int16 *
0x1800063b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800063bc  mov     r9, rdi; Args
0x1800063bf  lea     r8, [rsp+1038h+Format]; Format
0x1800063c4  mov     edi, 7FFh
0x1800063c9  mov     rcx, rbx; Buffer
0x1800063cc  mov     edx, edi; BufferCount
0x1800063ce  call    cs:__imp__vsnwprintf
0x1800063d4  test    eax, eax
0x1800063d6  js      short loc_1800063DE
0x1800063d8  cmp     eax, edi
0x1800063da  ja      short loc_1800063DE
0x1800063dc  jnz     short loc_1800063E7
0x1800063de  xor     eax, eax
0x1800063e0  mov     [rbx+0FFEh], ax
0x1800063e7  mov     rcx, [rsp+1038h+var_18]
0x1800063ef  xor     rcx, rsp; StackCookie
0x1800063f2  call    __security_check_cookie
0x1800063f7  mov     rbx, [rsp+1038h+arg_8]
0x1800063ff  add     rsp, 1030h
0x180006406  pop     rdi
0x180006407  retn
```
