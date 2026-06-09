# EnumerateAndHashBufferType

- ea: `0x180063a78`
- end: `0x180063af7`
- name: `EnumerateAndHashBufferType`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180058a04`

## callees

- `0x18000ecb0`
- `0x180012a80`
- `0x1800173f0`
- `0x180063a78`

## string_xrefs

- `0x180063ad0`: `onecore\ds\security\cryptoapi\ncrypt\kdf\util.c`

## pseudocode

```c
__int64 __fastcall EnumerateAndHashBufferType(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int i; // ebx
  int ParameterList; // eax
  int v8; // ebx
  int v9; // eax
  unsigned int v10; // edi

  for ( i = 0; ; i = v8 + 1 )
  {
    ParameterList = QueryParameterList(a2, a3, i);
    v8 = ParameterList;
    if ( ParameterList < 0 )
      break;
    v9 = MSCryptHashData(
           a1,
           *(_QWORD *)(*(_QWORD *)(a2 + 8) + 16LL * ParameterList + 8),
           *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL * ParameterList),
           0);
    v10 = v9;
    if ( v9 < 0 )
    {
      DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\util.c", 52);
      return v10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180063a78  push    rbx
0x180063a7a  push    rbp
0x180063a7b  push    rsi
0x180063a7c  push    rdi
0x180063a7d  push    r14
0x180063a7f  sub     rsp, 20h
0x180063a83  mov     ebp, r8d
0x180063a86  mov     rsi, rdx
0x180063a89  mov     r14, rcx
0x180063a8c  xor     ebx, ebx
0x180063a8e  mov     r8d, ebx
0x180063a91  mov     edx, ebp
0x180063a93  mov     rcx, rsi
0x180063a96  call    QueryParameterList
0x180063a9b  movsxd  rbx, eax
0x180063a9e  test    eax, eax
0x180063aa0  js      short loc_180063AE7
0x180063aa2  mov     rdx, [rsi+8]
0x180063aa6  mov     rax, rbx
0x180063aa9  add     rax, rax
0x180063aac  xor     r9d, r9d
0x180063aaf  mov     rcx, r14
0x180063ab2  mov     r8d, [rdx+rax*8]
0x180063ab6  mov     rdx, [rdx+rax*8+8]
0x180063abb  call    MSCryptHashData
0x180063ac0  mov     edi, eax
0x180063ac2  test    eax, eax
0x180063ac4  js      short loc_180063ACA
0x180063ac6  inc     ebx
0x180063ac8  jmp     short loc_180063A8E
0x180063aca  mov     r9d, 34h ; '4'
0x180063ad0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180063ad7  lea     rdx, aStatus; "Status"
0x180063ade  mov     ecx, eax
0x180063ae0  call    DebugTraceError
0x180063ae5  jmp     short loc_180063AE9
0x180063ae7  xor     edi, edi
0x180063ae9  mov     eax, edi
0x180063aeb  add     rsp, 20h
0x180063aef  pop     r14
0x180063af1  pop     rdi
0x180063af2  pop     rsi
0x180063af3  pop     rbp
0x180063af4  pop     rbx
0x180063af5  retn
```
