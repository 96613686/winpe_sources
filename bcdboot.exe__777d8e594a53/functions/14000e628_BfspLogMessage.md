# BfspLogMessage

- ea: `0x14000e628`
- end: `0x14000e795`
- name: `BfspLogMessage`
- size: `365`
- prototype: `__int64(int, const wchar_t *, ...)`
- caller_count: `62`
- callee_count: `4`
- tags: ``

## callers

- `0x140002a00`
- `0x140002c14`
- `0x1400030c0`
- `0x140003368`
- `0x140003d30`
- `0x140004080`
- `0x140004828`
- `0x140004a60`
- `0x140004e20`
- `0x140004e98`
- `0x140004f9c`
- `0x1400052bc`
- `0x14000583c`
- `0x1400058e4`
- `0x140005ae8`
- `0x140005b98`
- `0x140005e18`
- `0x140005fc4`
- `0x1400064c0`
- `0x1400065a0`
- `0x140006844`
- `0x140006a14`
- `0x140006b08`
- `0x140006cd8`
- `0x1400074f4`
- `0x140007780`
- `0x1400078f4`
- `0x140007c10`
- `0x140007cdc`
- `0x140008104`
- `0x140008400`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x140008e68`
- `0x140009170`
- `0x140009528`
- `0x140009658`
- `0x140009b80`
- `0x140009bdc`
- `0x140009fd4`
- `0x14000b57c`
- `0x14000bd28`
- `0x14000c024`
- `0x14000c5e0`
- `0x14000c8d8`
- `0x14000cc78`
- `0x14000cfc0`
- `0x14000d2b4`
- `0x14000d494`

## callees

- `0x140001b98`
- `0x14000e628`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `msvcrt!fwprintf` at `0x14000e718`
- `msvcrt!fwprintf` at `0x14000e766`
- `msvcrt!fwprintf` at `0x14000e718`
- `msvcrt!fwprintf` at `0x14000e766`
- `msvcrt!fflush` at `0x14000e721`
- `msvcrt!fflush` at `0x14000e773`
- `msvcrt!fflush` at `0x14000e721`
- `msvcrt!fflush` at `0x14000e773`
- `msvcrt!_vsnwprintf_s` at `0x14000e69e`
- `msvcrt!_vsnwprintf_s` at `0x14000e69e`

## pseudocode

```c
__int64 BfspLogMessage(int a1, const wchar_t *a2, ...)
{
  FILE *v3; // rax
  FILE *v4; // rdi
  const wchar_t *v5; // rdx
  const wchar_t *v6; // r8
  wchar_t Buffer[512]; // [rsp+40h] [rbp-428h] BYREF
  va_list va; // [rsp+480h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( LogEnabled && a1 >= FilterLevel && a1 < 5 || FileLoggingEnabled )
  {
    _vsnwprintf_s(Buffer, 0x200u, 0xFFFFFFFFFFFFFFFFuLL, a2, va);
    Buffer[511] = 0;
    if ( LogEnabled && a1 >= FilterLevel && a1 < 5 )
    {
      if ( LogMessageCallback )
      {
        LogMessageCallback((unsigned int)a1, Buffer);
      }
      else
      {
        v3 = _acrt_iob_func((unsigned int)(a1 >= 3) + 1);
        v4 = v3;
        if ( a1 == 3 )
        {
          fwprintf(v3, L"BFSVC Warning: %s\n", Buffer);
        }
        else
        {
          v5 = L"BFSVC Error: %s\n";
          if ( a1 != 4 )
            v5 = L"BFSVC: %s\n";
          fwprintf(v3, v5, Buffer);
        }
        fflush(v4);
      }
    }
    if ( FileLoggingEnabled )
    {
      if ( a1 == 3 )
      {
        v6 = L"WARNING";
      }
      else
      {
        v6 = L"ERROR";
        if ( a1 != 4 )
          v6 = L"INFO";
      }
      fwprintf(LogFileStream, L"%-10ws%ws\n", v6, Buffer);
      fflush(LogFileStream);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000e628  mov     [rsp+arg_8], rdx
0x14000e62d  mov     qword ptr [rsp+arg_10], r8
0x14000e632  mov     [rsp+arg_18], r9
0x14000e637  push    rbx
0x14000e638  push    rdi
0x14000e639  sub     rsp, 458h
0x14000e640  mov     rax, cs:__security_cookie
0x14000e647  xor     rax, rsp
0x14000e64a  mov     [rsp+468h+var_28], rax
0x14000e652  cmp     cs:LogEnabled, 0
0x14000e659  mov     ebx, ecx
0x14000e65b  mov     [rsp+468h+var_438], 0
0x14000e664  jz      short loc_14000E673
0x14000e666  cmp     ecx, cs:FilterLevel
0x14000e66c  jl      short loc_14000E673
0x14000e66e  cmp     ecx, 5
0x14000e671  jl      short loc_14000E680
0x14000e673  cmp     cs:FileLoggingEnabled, 0
0x14000e67a  jz      loc_14000E779
0x14000e680  lea     rax, [rsp+468h+arg_10]
0x14000e688  mov     r9, rdx; Format
0x14000e68b  mov     edx, 200h; BufferCount
0x14000e690  mov     [rsp+468h+ArgList], rax; ArgList
0x14000e695  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000e699  lea     rcx, [rsp+468h+Buffer]; Buffer
0x14000e69e  call    cs:__imp__vsnwprintf_s
0x14000e6a4  xor     eax, eax
0x14000e6a6  cmp     cs:LogEnabled, eax
0x14000e6ac  mov     [rsp+468h+var_2A], ax
0x14000e6b4  jz      short loc_14000E727
0x14000e6b6  cmp     ebx, cs:FilterLevel
0x14000e6bc  jl      short loc_14000E727
0x14000e6be  cmp     ebx, 5
0x14000e6c1  jge     short loc_14000E727
0x14000e6c3  mov     rax, cs:LogMessageCallback
0x14000e6ca  test    rax, rax
0x14000e6cd  jz      short loc_14000E6DD
0x14000e6cf  lea     rdx, [rsp+468h+Buffer]
0x14000e6d4  mov     ecx, ebx
0x14000e6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6db  jmp     short loc_14000E727
0x14000e6dd  xor     ecx, ecx
0x14000e6df  cmp     ebx, 3
0x14000e6e2  setnl   cl
0x14000e6e5  inc     ecx; Ix
0x14000e6e7  call    __acrt_iob_func
0x14000e6ec  mov     rdi, rax
0x14000e6ef  cmp     ebx, 3
0x14000e6f2  jnz     short loc_14000E6FD
0x14000e6f4  lea     rdx, aBfsvcWarningS; "BFSVC Warning: %s\n"
0x14000e6fb  jmp     short loc_14000E710
0x14000e6fd  lea     rdx, aBfsvcErrorS; "BFSVC Error: %s\n"
0x14000e704  cmp     ebx, 4
0x14000e707  jz      short loc_14000E710
0x14000e709  lea     rdx, aBfsvcS; "BFSVC: %s\n"
0x14000e710  lea     r8, [rsp+468h+Buffer]
0x14000e715  mov     rcx, rdi; Stream
0x14000e718  call    cs:__imp_fwprintf
0x14000e71e  mov     rcx, rdi; Stream
0x14000e721  call    cs:__imp_fflush
0x14000e727  cmp     cs:FileLoggingEnabled, 0
0x14000e72e  jz      short loc_14000E779
0x14000e730  cmp     ebx, 3
0x14000e733  jnz     short loc_14000E73E
0x14000e735  lea     r8, aWarning; "WARNING"
0x14000e73c  jmp     short loc_14000E753
0x14000e73e  cmp     ebx, 4
0x14000e741  lea     r8, aError; "ERROR"
0x14000e748  lea     rax, aInfo; "INFO"
0x14000e74f  cmovnz  r8, rax
0x14000e753  mov     rcx, cs:LogFileStream; Stream
0x14000e75a  lea     r9, [rsp+468h+Buffer]
0x14000e75f  lea     rdx, a10wsWs; "%-10ws%ws\n"
0x14000e766  call    cs:__imp_fwprintf
0x14000e76c  mov     rcx, cs:LogFileStream; Stream
0x14000e773  call    cs:__imp_fflush
0x14000e779  xor     eax, eax
0x14000e77b  mov     rcx, [rsp+468h+var_28]
0x14000e783  xor     rcx, rsp; StackCookie
0x14000e786  call    __security_check_cookie
0x14000e78b  add     rsp, 458h
0x14000e792  pop     rdi
0x14000e793  pop     rbx
0x14000e794  retn
```
