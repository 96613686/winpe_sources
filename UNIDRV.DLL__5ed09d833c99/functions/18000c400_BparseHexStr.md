# BparseHexStr

- ea: `0x18000c400`
- end: `0x18000c559`
- name: `BparseHexStr`
- size: `345`
- prototype: `__int64 __fastcall(__int64, int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c184`

## callees

- `0x180007150`
- `0x18000c400`
- `0x180049d00`
- `0x180076660`

## string_xrefs

- `0x18000c4ee`: `BwriteToHeap: out of heap - restarting.`
- `0x18000c4f5`: `BwriteToHeap`

## pseudocode

```c
__int64 __fastcall BparseHexStr(__int64 a1, int *a2, __int64 a3)
{
  unsigned int v6; // esi
  int v7; // edx
  __int64 v8; // rdi
  unsigned int v9; // ecx
  char v10; // al
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // eax
  _BYTE Src[40]; // [rsp+20h] [rbp-58h] BYREF

  v6 = 1;
  while ( 1 )
  {
    v7 = *(_DWORD *)(a1 + 8);
    if ( !v7 )
      break;
    v8 = 0;
    while ( v7 )
    {
      --v7;
      v9 = *(unsigned __int8 *)(*(_QWORD *)a1)++;
      *(_DWORD *)(a1 + 8) = v7;
      v10 = v9 - 48;
      if ( (unsigned __int8)(v9 - 48) <= 9u )
      {
LABEL_10:
        if ( v6 )
        {
          Src[v8] = 16 * v10;
          v6 = 0;
        }
        else
        {
          Src[v8] |= v10;
          v6 = 1;
          v8 = (unsigned int)(v8 + 1);
        }
        if ( (unsigned int)v8 >= 0x28 )
          break;
      }
      else
      {
        if ( (unsigned __int8)(v9 - 97) <= 5u )
        {
          v10 = v9 - 87;
          goto LABEL_10;
        }
        if ( (unsigned __int8)(v9 - 65) <= 5u )
        {
          v10 = v9 - 55;
          goto LABEL_10;
        }
        if ( (_BYTE)v9 != 32 && (_BYTE)v9 != 9 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"BparseHexStr",
            "syntax error:  illegal char found within hexsubstring: %c",
            v9);
          return 0;
        }
      }
    }
    v11 = *(unsigned int *)(a3 + 12);
    if ( (unsigned int)(v11 + v8) > *(_DWORD *)(a3 + 8) )
    {
      WriteDbgTraceErrorGpd((__int64)"BwriteToHeap", "BwriteToHeap: out of heap - restarting.");
      if ( *(int *)(a3 + 2220) < 2 )
      {
        *(_DWORD *)(a3 + 2220) = 2;
        *(_DWORD *)(a3 + 2224) = 2;
        *(_DWORD *)(a3 + 2216) = 0;
      }
      return 0;
    }
    memcpy_0((void *)(*(_QWORD *)a3 + v11), Src, (unsigned int)v8);
    v12 = *(_DWORD *)(a3 + 12);
    *(_DWORD *)(a3 + 12) = v12 + v8;
    v13 = *a2;
    if ( !*a2 )
      a2[1] = v12;
    *a2 = v8 + v13;
  }
  if ( !v6 )
    WriteDbgTraceErrorGpd((__int64)"BparseHexStr", "hex string contains odd number of hex digits.");
  return v6;
}

```

## disassembly

```asm
0x18000c400  push    rbx
0x18000c402  push    rsi
0x18000c403  push    rdi
0x18000c404  push    r14
0x18000c406  push    r15
0x18000c408  sub     rsp, 50h
0x18000c40c  mov     rax, cs:__security_cookie
0x18000c413  xor     rax, rsp
0x18000c416  mov     [rsp+78h+var_30], rax
0x18000c41b  mov     rbx, r8
0x18000c41e  mov     r15, rdx
0x18000c421  mov     r14, rcx
0x18000c424  mov     esi, 1
0x18000c429  mov     edx, [r14+8]
0x18000c42d  test    edx, edx
0x18000c42f  jz      loc_18000C526
0x18000c435  xor     edi, edi
0x18000c437  test    edx, edx
0x18000c439  jz      short loc_18000C489
0x18000c43b  mov     rax, [r14]
0x18000c43e  dec     edx
0x18000c440  movzx   ecx, byte ptr [rax]
0x18000c443  inc     rax
0x18000c446  mov     [r14], rax
0x18000c449  mov     [r14+8], edx
0x18000c44d  lea     eax, [rcx-30h]
0x18000c450  cmp     al, 9
0x18000c452  jbe     short loc_18000C46A
0x18000c454  lea     eax, [rcx-61h]
0x18000c457  cmp     al, 5
0x18000c459  ja      short loc_18000C460
0x18000c45b  lea     eax, [rcx-57h]
0x18000c45e  jmp     short loc_18000C46A
0x18000c460  lea     eax, [rcx-41h]
0x18000c463  cmp     al, 5
0x18000c465  ja      short loc_18000C4C2
0x18000c467  lea     eax, [rcx-37h]
0x18000c46a  test    esi, esi
0x18000c46c  jz      short loc_18000C479
0x18000c46e  shl     al, 4
0x18000c471  mov     [rsp+rdi+78h+Src], al
0x18000c475  xor     esi, esi
0x18000c477  jmp     short loc_18000C484
0x18000c479  or      [rsp+rdi+78h+Src], al
0x18000c47d  mov     esi, 1
0x18000c482  inc     edi
0x18000c484  cmp     edi, 28h ; '('
0x18000c487  jb      short loc_18000C437
0x18000c489  mov     ecx, [rbx+0Ch]
0x18000c48c  lea     eax, [rcx+rdi]
0x18000c48f  cmp     eax, [rbx+8]
0x18000c492  ja      short loc_18000C4EE
0x18000c494  add     rcx, [rbx]; void *
0x18000c497  lea     rdx, [rsp+78h+Src]; Src
0x18000c49c  mov     r8d, edi; Size
0x18000c49f  call    memcpy_0
0x18000c4a4  mov     ecx, [rbx+0Ch]
0x18000c4a7  lea     eax, [rcx+rdi]
0x18000c4aa  mov     [rbx+0Ch], eax
0x18000c4ad  mov     eax, [r15]
0x18000c4b0  test    eax, eax
0x18000c4b2  jnz     short loc_18000C4B8
0x18000c4b4  mov     [r15+4], ecx
0x18000c4b8  add     eax, edi
0x18000c4ba  mov     [r15], eax
0x18000c4bd  jmp     loc_18000C429
0x18000c4c2  cmp     cl, 20h ; ' '
0x18000c4c5  jz      loc_18000C437
0x18000c4cb  cmp     cl, 9
0x18000c4ce  jz      loc_18000C437
0x18000c4d4  mov     r8d, ecx
0x18000c4d7  lea     rdx, aSyntaxErrorIll; "syntax error:  illegal char found withi"...
0x18000c4de  lea     rcx, aBparsehexstr; "BparseHexStr"
0x18000c4e5  call    WriteDbgTraceErrorGpd
0x18000c4ea  xor     eax, eax
0x18000c4ec  jmp     short loc_18000C53F
0x18000c4ee  lea     rdx, aBwritetoheapOu; "BwriteToHeap: out of heap - restarting."
0x18000c4f5  lea     rcx, aBwritetoheap; "BwriteToHeap"
0x18000c4fc  call    WriteDbgTraceErrorGpd
0x18000c501  mov     eax, 2
0x18000c506  cmp     [rbx+8ACh], eax
0x18000c50c  jge     short loc_18000C4EA
0x18000c50e  mov     [rbx+8ACh], eax
0x18000c514  mov     [rbx+8B0h], eax
0x18000c51a  mov     dword ptr [rbx+8A8h], 0
0x18000c524  jmp     short loc_18000C4EA
0x18000c526  test    esi, esi
0x18000c528  jnz     short loc_18000C53D
0x18000c52a  lea     rdx, aHexStringConta; "hex string contains odd number of hex d"...
0x18000c531  lea     rcx, aBparsehexstr; "BparseHexStr"
0x18000c538  call    WriteDbgTraceErrorGpd
0x18000c53d  mov     eax, esi
0x18000c53f  mov     rcx, [rsp+78h+var_30]
0x18000c544  xor     rcx, rsp; StackCookie
0x18000c547  call    __security_check_cookie
0x18000c54c  add     rsp, 50h
0x18000c550  pop     r15
0x18000c552  pop     r14
0x18000c554  pop     rdi
0x18000c555  pop     rsi
0x18000c556  pop     rbx
0x18000c557  retn
```
