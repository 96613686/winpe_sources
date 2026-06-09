# SdbpGetMatchingTextAttributes

- ea: `0x14002fd64`
- end: `0x140030045`
- name: `SdbpGetMatchingTextAttributes`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14002f280`

## callees

- `0x1400063e8`
- `0x14002fd64`
- `0x14003d820`
- `0x14003e364`
- `0x14003ef10`
- `0x14003f570`
- `0x14004007c`
- `0x140040820`
- `0x140045d44`
- `0x14005498c`

## string_xrefs

- `0x14002fdd2`: `Failed to get MATCHING_TEXT file path`
- `0x14002ffec`: `Failed to read MATCHING_TEXT file path`
- `0x14002fe73`: `Failed to read text to match`
- `0x14002ff28`: `Failed to read matching text blob`
- `0x14002ff4c`: `Failed to read text encoding`
- `0x14002ff6f`: `Failed to read encoding type`

## pseudocode

```c
__int64 __fastcall SdbpGetMatchingTextAttributes(
        void *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  unsigned int FirstTag; // eax
  __int64 v9; // rcx
  __int128 v10; // kr00_16
  void *StringTagPtr; // rax

  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0x2000;
  FirstTag = SdbFindFirstTag(a1, a2, 24577);
  if ( FirstTag )
  {
    StringTagPtr = (void *)SdbGetStringTagPtr(a1, FirstTag);
    SdbpUmaInit_PCWSTR(StringTagPtr);
    v10 = 0;
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1862, "Failed to read MATCHING_TEXT file path", 0);
  }
  else
  {
    AslLogCallPrintf(1, "SdbpGetMatchingTextAttributes", 1850, "Failed to get MATCHING_TEXT file path", 0);
    v10 = 0u;
  }
  if ( (_QWORD)v10 && (_QWORD)v10 != *((_QWORD *)&v10 + 1) )
    AslFree(v9, (void *)v10);
  return 0;
}

```

## disassembly

```asm
0x14002fd64  mov     [rsp+arg_0], rbx
0x14002fd69  mov     [rsp+arg_18], r9
0x14002fd6e  mov     [rsp+arg_10], r8
0x14002fd73  push    rbp
0x14002fd74  push    rsi
0x14002fd75  push    rdi
0x14002fd76  push    r12
0x14002fd78  push    r13
0x14002fd7a  push    r14
0x14002fd7c  push    r15
0x14002fd7e  sub     rsp, 40h
0x14002fd82  mov     rax, [rsp+78h+arg_20]
0x14002fd8a  xor     ebx, ebx
0x14002fd8c  mov     [r8], rbx
0x14002fd8f  xorps   xmm0, xmm0
0x14002fd92  mov     r8d, 6001h
0x14002fd98  mov     [rsp+78h+var_58], ebx
0x14002fd9c  mov     r13d, edx
0x14002fd9f  mov     [r9], rbx
0x14002fda2  mov     [rax], ebx
0x14002fda4  mov     rsi, rcx
0x14002fda7  mov     rax, [rsp+78h+arg_28]
0x14002fdaf  mov     ebp, ebx
0x14002fdb1  mov     r14d, ebx
0x14002fdb4  movups  [rsp+78h+var_50], xmm0
0x14002fdb9  mov     [rax], ebx
0x14002fdbb  mov     rax, [rsp+78h+arg_30]
0x14002fdc3  mov     dword ptr [rax], 2000h
0x14002fdc9  call    SdbFindFirstTag
0x14002fdce  test    eax, eax
0x14002fdd0  jnz     short loc_14002FDFD
0x14002fdd2  lea     r9, aFailedToGetMat; "Failed to get MATCHING_TEXT file path"
0x14002fdd9  mov     r8d, 73Ah
0x14002fddf  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x14002fde6  lea     ecx, [rbx+1]
0x14002fde9  call    AslLogCallPrintf
0x14002fdee  mov     r15, qword ptr [rsp+78h+var_50+8]
0x14002fdf3  mov     rdi, qword ptr [rsp+78h+var_50]
0x14002fdf8  jmp     loc_14003000A
0x14002fdfd  mov     edx, eax
0x14002fdff  mov     rcx, rsi
0x14002fe02  call    SdbGetStringTagPtr
0x14002fe07  mov     rcx, rax; Src
0x14002fe0a  lea     rdx, [rsp+78h+var_50]
0x14002fe0f  call    SdbpUmaInit_PCWSTR
0x14002fe14  mov     rdi, qword ptr [rsp+78h+var_50]
0x14002fe19  mov     r15, qword ptr [rsp+78h+var_50+8]
0x14002fe1e  test    rdi, rdi
0x14002fe21  jnz     short loc_14002FE52
0x14002fe23  test    r15, r15
0x14002fe26  jz      short loc_14002FE49
0x14002fe28  lea     r9, aOutOfMemory; "Out of memory"
0x14002fe2f  mov     r8d, 740h
0x14002fe35  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x14002fe3c  lea     ecx, [rdi+1]
0x14002fe3f  call    AslLogCallPrintf
0x14002fe44  jmp     loc_140030029
0x14002fe49  test    rdi, rdi
0x14002fe4c  jz      loc_14002FFEC
0x14002fe52  cmp     [rdi], bx
0x14002fe55  jz      loc_14002FFEC
0x14002fe5b  mov     r8d, 9013h
0x14002fe61  mov     edx, r13d
0x14002fe64  mov     rcx, rsi
0x14002fe67  call    SdbFindFirstTag
0x14002fe6c  mov     r12d, eax
0x14002fe6f  test    eax, eax
0x14002fe71  jnz     short loc_14002FE85
0x14002fe73  lea     r9, aFailedToReadTe_0; "Failed to read text to match"
0x14002fe7a  mov     r8d, 74Fh
0x14002fe80  jmp     loc_14002FFF9
0x14002fe85  mov     edx, r12d
0x14002fe88  mov     rcx, rsi
0x14002fe8b  call    SdbGetTagDataSize
0x14002fe90  mov     r14d, eax
0x14002fe93  test    eax, eax
0x14002fe95  jnz     short loc_14002FEBD
0x14002fe97  lea     r9, aFailedToGetTex; "Failed to get text to match blob"
0x14002fe9e  mov     r8d, 755h
0x14002fea4  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x14002feab  mov     ecx, 1
0x14002feb0  call    AslLogCallPrintf
0x14002feb5  mov     r14d, ebx
0x14002feb8  jmp     loc_14003000A
0x14002febd  cmp     r14d, 20000000h
0x14002fec4  jnz     short loc_14002FED5
0x14002fec6  lea     r9, aFailedToGetTex_0; "Failed to get text size to match blob"
0x14002fecd  mov     r8d, 759h
0x14002fed3  jmp     short loc_14002FEA4
0x14002fed5  mov     ebx, 1
0x14002feda  lea     rdx, [r14+2]
0x14002fede  mov     r8d, ebx
0x14002fee1  call    AslAlloc
0x14002fee6  mov     rbp, rax
0x14002fee9  test    rax, rax
0x14002feec  jnz     short loc_14002FF13
0x14002feee  lea     r9, aFailedToAlloca; "Failed to allocate memory for text blob"
0x14002fef5  mov     r8d, 75Fh
0x14002fefb  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x14002ff02  mov     ecx, ebx
0x14002ff04  call    AslLogCallPrintf
0x14002ff09  mov     r14d, [rsp+78h+var_58]
0x14002ff0e  jmp     loc_14003000A
0x14002ff13  mov     r9d, r14d
0x14002ff16  mov     r8, rbp
0x14002ff19  mov     edx, r12d
0x14002ff1c  mov     rcx, rsi
0x14002ff1f  call    SdbReadBinaryTag
0x14002ff24  test    eax, eax
0x14002ff26  jnz     short loc_14002FF37
0x14002ff28  lea     r9, aFailedToReadMa_0; "Failed to read matching text blob"
0x14002ff2f  mov     r8d, 764h
0x14002ff35  jmp     short loc_14002FEFB
0x14002ff37  mov     r8d, 4053h
0x14002ff3d  mov     edx, r13d
0x14002ff40  mov     rcx, rsi
0x14002ff43  call    SdbFindFirstTag
0x14002ff48  test    eax, eax
0x14002ff4a  jnz     short loc_14002FF5B
0x14002ff4c  lea     r9, aFailedToReadTe; "Failed to read text encoding"
0x14002ff53  mov     r8d, 76Dh
0x14002ff59  jmp     short loc_14002FEFB
0x14002ff5b  xor     r8d, r8d
0x14002ff5e  mov     edx, eax
0x14002ff60  mov     rcx, rsi
0x14002ff63  call    SdbReadDWORDTag
0x14002ff68  mov     r12d, eax
0x14002ff6b  test    eax, eax
0x14002ff6d  jnz     short loc_14002FF81
0x14002ff6f  lea     r9, aFailedToReadEn; "Failed to read encoding type"
0x14002ff76  mov     r8d, 773h
0x14002ff7c  jmp     loc_14002FEFB
0x14002ff81  mov     r8d, 4001h
0x14002ff87  mov     edx, r13d
0x14002ff8a  mov     rcx, rsi
0x14002ff8d  call    SdbFindFirstTag
0x14002ff92  test    eax, eax
0x14002ff94  jz      short loc_14002FFAA
0x14002ff96  mov     r8d, 2000h
0x14002ff9c  mov     edx, eax
0x14002ff9e  mov     rcx, rsi
0x14002ffa1  call    SdbReadDWORDTag
0x14002ffa6  mov     ecx, eax
0x14002ffa8  jmp     short loc_14002FFAF
0x14002ffaa  mov     ecx, 2000h
0x14002ffaf  mov     rax, [rsp+78h+arg_10]
0x14002ffb7  mov     [rax], r15
0x14002ffba  mov     rax, [rsp+78h+arg_18]
0x14002ffc2  mov     [rax], rbp
0x14002ffc5  xor     ebp, ebp
0x14002ffc7  mov     rax, [rsp+78h+arg_20]
0x14002ffcf  mov     [rax], r14d
0x14002ffd2  mov     rax, [rsp+78h+arg_28]
0x14002ffda  mov     [rax], r12d
0x14002ffdd  mov     rax, [rsp+78h+arg_30]
0x14002ffe5  mov     [rax], ecx
0x14002ffe7  jmp     loc_14002FEB5
0x14002ffec  lea     r9, aFailedToReadMa_3; "Failed to read MATCHING_TEXT file path"
0x14002fff3  mov     r8d, 746h
0x14002fff9  lea     rdx, aSdbpgetmatchin; "SdbpGetMatchingTextAttributes"
0x140030000  mov     ecx, 1
0x140030005  call    AslLogCallPrintf
0x14003000a  test    rdi, rdi
0x14003000d  jz      short loc_14003001C
0x14003000f  cmp     rdi, r15
0x140030012  jz      short loc_14003001C
0x140030014  mov     rdx, rdi
0x140030017  call    AslFree
0x14003001c  test    rbp, rbp
0x14003001f  jz      short loc_140030029
0x140030021  mov     rdx, rbp
0x140030024  call    AslFree
0x140030029  mov     rbx, [rsp+78h+arg_0]
0x140030031  mov     eax, r14d
0x140030034  add     rsp, 40h
0x140030038  pop     r15
0x14003003a  pop     r14
0x14003003c  pop     r13
0x14003003e  pop     r12
0x140030040  pop     rdi
0x140030041  pop     rsi
0x140030042  pop     rbp
0x140030043  retn
```
