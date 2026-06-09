# SdbpCheckMatchingCommandLine

- ea: `0x14002ed10`
- end: `0x14002ef34`
- name: `SdbpCheckMatchingCommandLine`
- size: `548`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, void *Src)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140004445`
- `0x1400063e8`
- `0x1400273f4`
- `0x14002ed10`
- `0x14003d820`
- `0x14003e364`
- `0x14003ef10`
- `0x14004102c`
- `0x140045d44`

## string_xrefs

- `0x14002ed4b`: `MatchingCommandLine matcher missing command line context.`
- `0x14002ed58`: `SdbpCheckMatchingCommandLine`
- `0x14002eda2`: `SdbpCheckMatchingCommandLine`
- `0x14002ee0c`: `SdbpCheckMatchingCommandLine`
- `0x14002ee3c`: `SdbpCheckMatchingCommandLine`
- `0x14002ed90`: `TAG_MATCHING_COMMAND_LINE missing child TAG_COMMAND_LINE (TagID: 0x%x)`
- `0x14002ee2c`: `Failed to read TAG_COMMAND_LINE string contents (TagID: 0x%x)`
- `0x14002ee96`: `Tailed to read TAG_ESCAPE_CHARACTER string contents (TagID: 0x%x)`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingCommandLine(
        _DWORD *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        void *Src)
{
  _DWORD *v8; // r14
  unsigned int FirstTag; // eax
  int v10; // r14d
  void *StringTagPtr; // rax

  v8 = a1;
  if ( Src )
  {
    FirstTag = SdbFindFirstTag(a3, a5, 24584);
    v10 = FirstTag;
    if ( FirstTag )
    {
      StringTagPtr = (void *)SdbGetStringTagPtr(a3, FirstTag);
      SdbpUmaInit_PCWSTR(StringTagPtr);
      SdbpUmaInit_PCWSTR(Src);
      AslLogCallPrintf(
        1,
        "SdbpCheckMatchingCommandLine",
        3307,
        "Failed to read TAG_COMMAND_LINE string contents (TagID: 0x%x)",
        v10);
    }
    else
    {
      AslLogCallPrintf(
        1,
        "SdbpCheckMatchingCommandLine",
        3291,
        "TAG_MATCHING_COMMAND_LINE missing child TAG_COMMAND_LINE (TagID: 0x%x)",
        a5);
    }
    v8 = a1;
  }
  else
  {
    AslLogCallPrintf(
      3,
      "SdbpCheckMatchingCommandLine",
      3285,
      "MatchingCommandLine matcher missing command line context.");
  }
  if ( a6 )
    *(_DWORD *)(a6 + 80) = 1;
  *v8 = 0;
  return 0;
}

```

## disassembly

```asm
0x14002ed10  mov     [rsp-40h+arg_0], rcx
0x14002ed15  push    rbp
0x14002ed16  push    rbx
0x14002ed17  push    rsi
0x14002ed18  push    rdi
0x14002ed19  push    r12
0x14002ed1b  push    r13
0x14002ed1d  push    r14
0x14002ed1f  push    r15
0x14002ed21  mov     rbp, rsp
0x14002ed24  sub     rsp, 58h
0x14002ed28  mov     rbx, [rbp+Src]
0x14002ed2c  xor     r12d, r12d
0x14002ed2f  xor     r13d, r13d
0x14002ed32  xorps   xmm0, xmm0
0x14002ed35  xorps   xmm1, xmm1
0x14002ed38  mov     rsi, r8
0x14002ed3b  mov     r14, rcx
0x14002ed3e  movups  [rbp+var_28], xmm0
0x14002ed42  movups  [rbp+var_18], xmm1
0x14002ed46  test    rbx, rbx
0x14002ed49  jnz     short loc_14002ED74
0x14002ed4b  lea     r9, aMatchingcomman; "MatchingCommandLine matcher missing com"...
0x14002ed52  mov     r8d, 0CD5h
0x14002ed58  lea     rdx, aSdbpcheckmatch_1; "SdbpCheckMatchingCommandLine"
0x14002ed5f  lea     ecx, [rbx+3]
0x14002ed62  call    AslLogCallPrintf
0x14002ed67  mov     rbx, qword ptr [rbp+var_28]
0x14002ed6b  mov     rdi, qword ptr [rbp+var_18]
0x14002ed6f  jmp     loc_14002EEE6
0x14002ed74  mov     r15d, [rbp+arg_20]
0x14002ed78  mov     r8d, 6008h
0x14002ed7e  mov     edx, r15d
0x14002ed81  mov     rcx, rsi
0x14002ed84  call    SdbFindFirstTag
0x14002ed89  mov     r14d, eax
0x14002ed8c  test    eax, eax
0x14002ed8e  jnz     short loc_14002EDBE
0x14002ed90  lea     r9, aTagMatchingCom; "TAG_MATCHING_COMMAND_LINE missing child"...
0x14002ed97  mov     [rsp+58h+var_38], r15d
0x14002ed9c  mov     r8d, 0CDBh
0x14002eda2  lea     rdx, aSdbpcheckmatch_1; "SdbpCheckMatchingCommandLine"
0x14002eda9  lea     ecx, [rax+1]
0x14002edac  call    AslLogCallPrintf
0x14002edb1  mov     rbx, qword ptr [rbp+var_28]
0x14002edb5  mov     rdi, qword ptr [rbp+var_18]
0x14002edb9  jmp     loc_14002EEE2
0x14002edbe  mov     edx, r14d
0x14002edc1  mov     rcx, rsi
0x14002edc4  call    SdbGetStringTagPtr
0x14002edc9  mov     rcx, rax; Src
0x14002edcc  lea     rdx, [rbp+var_28]
0x14002edd0  call    SdbpUmaInit_PCWSTR
0x14002edd5  lea     rdx, [rbp+var_18]
0x14002edd9  mov     rcx, rbx; Src
0x14002eddc  call    SdbpUmaInit_PCWSTR
0x14002ede1  mov     rbx, qword ptr [rbp+var_28]
0x14002ede5  mov     rdi, qword ptr [rbp+var_18]
0x14002ede9  test    rbx, rbx
0x14002edec  jnz     short loc_14002EDF4
0x14002edee  cmp     qword ptr [rbp+var_28+8], r12
0x14002edf2  jnz     short loc_14002EDFF
0x14002edf4  test    rdi, rdi
0x14002edf7  jnz     short loc_14002EE22
0x14002edf9  cmp     qword ptr [rbp+var_18+8], r12
0x14002edfd  jz      short loc_14002EE22
0x14002edff  lea     r9, aOutOfMemory; "Out of memory"
0x14002ee06  mov     r8d, 0CE4h
0x14002ee0c  lea     rdx, aSdbpcheckmatch_1; "SdbpCheckMatchingCommandLine"
0x14002ee13  mov     ecx, 1
0x14002ee18  call    AslLogCallPrintf
0x14002ee1d  jmp     loc_14002EEE2
0x14002ee22  test    rbx, rbx
0x14002ee25  jnz     short loc_14002EE4D
0x14002ee27  mov     [rsp+58h+var_38], r14d
0x14002ee2c  lea     r9, aFailedToReadTa_0; "Failed to read TAG_COMMAND_LINE string "...
0x14002ee33  mov     r8d, 0CEBh
0x14002ee39  lea     ecx, [rbx+1]
0x14002ee3c  lea     rdx, aSdbpcheckmatch_1; "SdbpCheckMatchingCommandLine"
0x14002ee43  call    AslLogCallPrintf
0x14002ee48  jmp     loc_14002EEE2
0x14002ee4d  mov     r8d, 1017h
0x14002ee53  mov     edx, r15d
0x14002ee56  mov     rcx, rsi
0x14002ee59  xor     r14d, r14d
0x14002ee5c  call    SdbFindFirstTag
0x14002ee61  test    eax, eax
0x14002ee63  mov     r8d, 603Dh
0x14002ee69  mov     edx, r15d
0x14002ee6c  mov     rcx, rsi
0x14002ee6f  setnz   byte ptr [rbp+Src]
0x14002ee73  call    SdbFindFirstTag
0x14002ee78  mov     r15d, eax
0x14002ee7b  test    eax, eax
0x14002ee7d  jz      short loc_14002EEC6
0x14002ee7f  mov     edx, eax
0x14002ee81  mov     rcx, rsi
0x14002ee84  call    SdbGetStringTagPtr
0x14002ee89  mov     rsi, rax
0x14002ee8c  test    rax, rax
0x14002ee8f  jnz     short loc_14002EEA8
0x14002ee91  mov     [rsp+58h+var_38], r15d
0x14002ee96  lea     r9, aTailedToReadTa; "Tailed to read TAG_ESCAPE_CHARACTER str"...
0x14002ee9d  mov     r8d, 0CF7h
0x14002eea3  lea     ecx, [rax+3]
0x14002eea6  jmp     short loc_14002EE3C
0x14002eea8  mov     rcx, rsi
0x14002eeab  call    MmIsUserAddress_0
0x14002eeb0  test    al, al
0x14002eeb2  jz      short loc_14002EEC2
0x14002eeb4  mov     rcx, rsi
0x14002eeb7  call    RtlReadUShortFromUser
0x14002eebc  movzx   r14d, ax
0x14002eec0  jmp     short loc_14002EEC6
0x14002eec2  movzx   r14d, word ptr [rsi]
0x14002eec6  mov     r8b, byte ptr [rbp+Src]
0x14002eeca  movzx   r9d, r14w
0x14002eece  mov     rdx, rdi
0x14002eed1  mov     rcx, rbx
0x14002eed4  call    AslStringPatternMatchExW
0x14002eed9  mov     r13d, eax
0x14002eedc  mov     r12d, 1
0x14002eee2  mov     r14, [rbp+arg_0]
0x14002eee6  test    rbx, rbx
0x14002eee9  jz      short loc_14002EEF9
0x14002eeeb  cmp     rbx, qword ptr [rbp+var_28+8]
0x14002eeef  jz      short loc_14002EEF9
0x14002eef1  mov     rdx, rbx
0x14002eef4  call    AslFree
0x14002eef9  test    rdi, rdi
0x14002eefc  jz      short loc_14002EF0C
0x14002eefe  cmp     rdi, qword ptr [rbp+var_18+8]
0x14002ef02  jz      short loc_14002EF0C
0x14002ef04  mov     rdx, rdi
0x14002ef07  call    AslFree
0x14002ef0c  mov     rcx, [rbp+arg_28]
0x14002ef10  test    rcx, rcx
0x14002ef13  jz      short loc_14002EF1C
0x14002ef15  mov     dword ptr [rcx+50h], 1
0x14002ef1c  mov     [r14], r13d
0x14002ef1f  mov     eax, r12d
0x14002ef22  add     rsp, 58h
0x14002ef26  pop     r15
0x14002ef28  pop     r14
0x14002ef2a  pop     r13
0x14002ef2c  pop     r12
0x14002ef2e  pop     rdi
0x14002ef2f  pop     rsi
0x14002ef30  pop     rbx
0x14002ef31  pop     rbp
0x14002ef32  retn
```
