# VfsProcessLinkName

- ea: `0x14000c100`
- end: `0x14000c1ac`
- name: `VfsProcessLinkName`
- size: `172`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001690`

## callees

- `0x14000c100`
- `0x14000f058`
- `0x14000f124`

## pseudocode

```c
__int64 __fastcall VfsProcessLinkName(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  int v10; // [rsp+40h] [rbp+18h] BYREF
  int v11; // [rsp+44h] [rbp+1Ch]

  v11 = HIDWORD(a3);
  v10 = 0;
  v3 = *(_QWORD *)(a1 + 16);
  v9 = 0;
  v5 = *(_QWORD *)(v3 + 40);
  v6 = *(_QWORD *)(*(_QWORD *)(v3 + 56) + 8LL);
  if ( !(unsigned __int8)VfsDecodeFileObject(*(_QWORD *)(a2 + 32), 0, 0)
    && (!v5 || !(unsigned __int8)VfsDecodeFileObject(v5, 0, 0)) )
  {
    if ( !v6 )
      return 1;
    LOBYTE(v7) = *(_BYTE *)(a1 + 80);
    if ( !(unsigned __int8)VfsDecodeFileHandle(v6, v7, &v10, &v9) )
      return 1;
  }
  *(_DWORD *)(a1 + 24) = -1073741637;
  result = 4;
  *(_QWORD *)(a1 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x14000c100  mov     rax, rsp
0x14000c103  mov     [rax+10h], rbx
0x14000c107  mov     [rax+20h], rsi
0x14000c10b  mov     [rax+18h], r8
0x14000c10f  push    rdi
0x14000c110  sub     rsp, 20h
0x14000c114  mov     dword ptr [rax+18h], 0
0x14000c11b  mov     r9, rdx
0x14000c11e  mov     rax, [rcx+10h]
0x14000c122  mov     rbx, rcx
0x14000c125  xor     r8d, r8d
0x14000c128  mov     [rsp+28h+arg_0], 0
0x14000c131  xor     edx, edx
0x14000c133  mov     rcx, [r9+20h]
0x14000c137  mov     rdi, [rax+28h]
0x14000c13b  mov     rax, [rax+38h]
0x14000c13f  mov     rsi, [rax+8]
0x14000c143  call    VfsDecodeFileObject
0x14000c148  test    al, al
0x14000c14a  jnz     short loc_14000C187
0x14000c14c  test    rdi, rdi
0x14000c14f  jz      short loc_14000C162
0x14000c151  xor     r8d, r8d
0x14000c154  xor     edx, edx
0x14000c156  mov     rcx, rdi
0x14000c159  call    VfsDecodeFileObject
0x14000c15e  test    al, al
0x14000c160  jnz     short loc_14000C187
0x14000c162  test    rsi, rsi
0x14000c165  jz      short loc_14000C180
0x14000c167  mov     dl, [rbx+50h]
0x14000c16a  lea     r9, [rsp+28h+arg_0]
0x14000c16f  lea     r8, [rsp+28h+arg_10]
0x14000c174  mov     rcx, rsi
0x14000c177  call    VfsDecodeFileHandle
0x14000c17c  test    al, al
0x14000c17e  jnz     short loc_14000C187
0x14000c180  mov     eax, 1
0x14000c185  jmp     short loc_14000C19B
0x14000c187  mov     dword ptr [rbx+18h], 0C00000BBh
0x14000c18e  mov     eax, 4
0x14000c193  mov     qword ptr [rbx+20h], 0
0x14000c19b  mov     rbx, [rsp+28h+arg_8]
0x14000c1a0  mov     rsi, [rsp+28h+arg_18]
0x14000c1a5  add     rsp, 20h
0x14000c1a9  pop     rdi
0x14000c1aa  retn
```
