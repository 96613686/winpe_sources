# BparseHexStr

- ea: `0x18000c408`
- end: `0x18000c560`
- name: `BparseHexStr`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c190`

## callees

- `0x180007220`
- `0x18000c408`
- `0x1800487e0`
- `0x180074580`

## string_xrefs

- `0x18000c4f6`: `BwriteToHeap: out of heap - restarting.`
- `0x18000c4fd`: `BwriteToHeap`

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
          WriteDbgTraceErrorGpd("BparseHexStr", "syntax error:  illegal char found within hexsubstring: %c", v9);
          return 0;
        }
      }
    }
    v11 = *(unsigned int *)(a3 + 12);
    if ( (unsigned int)(v11 + v8) > *(_DWORD *)(a3 + 8) )
    {
      WriteDbgTraceErrorGpd("BwriteToHeap", "BwriteToHeap: out of heap - restarting.");
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
    WriteDbgTraceErrorGpd("BparseHexStr", "hex string contains odd number of hex digits.");
  return v6;
}

```

## disassembly

```asm
0x18000c408  push    rbx
0x18000c40a  push    rsi
0x18000c40b  push    rdi
0x18000c40c  push    r14
0x18000c40e  push    r15
0x18000c410  sub     rsp, 50h
0x18000c414  mov     rax, cs:__security_cookie
0x18000c41b  xor     rax, rsp
0x18000c41e  mov     [rsp+78h+var_30], rax
0x18000c423  mov     rbx, r8
0x18000c426  mov     r15, rdx
0x18000c429  mov     r14, rcx
0x18000c42c  mov     esi, 1
0x18000c431  mov     edx, [r14+8]
0x18000c435  test    edx, edx
0x18000c437  jz      loc_18000C52E
0x18000c43d  xor     edi, edi
0x18000c43f  test    edx, edx
0x18000c441  jz      short loc_18000C491
0x18000c443  mov     rax, [r14]
0x18000c446  dec     edx
0x18000c448  movzx   ecx, byte ptr [rax]
0x18000c44b  inc     rax
0x18000c44e  mov     [r14], rax
0x18000c451  mov     [r14+8], edx
0x18000c455  lea     eax, [rcx-30h]
0x18000c458  cmp     al, 9
0x18000c45a  jbe     short loc_18000C472
0x18000c45c  lea     eax, [rcx-61h]
0x18000c45f  cmp     al, 5
0x18000c461  ja      short loc_18000C468
0x18000c463  lea     eax, [rcx-57h]
0x18000c466  jmp     short loc_18000C472
0x18000c468  lea     eax, [rcx-41h]
0x18000c46b  cmp     al, 5
0x18000c46d  ja      short loc_18000C4CA
0x18000c46f  lea     eax, [rcx-37h]
0x18000c472  test    esi, esi
0x18000c474  jz      short loc_18000C481
0x18000c476  shl     al, 4
0x18000c479  mov     [rsp+rdi+78h+Src], al
0x18000c47d  xor     esi, esi
0x18000c47f  jmp     short loc_18000C48C
0x18000c481  or      [rsp+rdi+78h+Src], al
0x18000c485  mov     esi, 1
0x18000c48a  inc     edi
0x18000c48c  cmp     edi, 28h ; '('
0x18000c48f  jb      short loc_18000C43F
0x18000c491  mov     ecx, [rbx+0Ch]
0x18000c494  lea     eax, [rcx+rdi]
0x18000c497  cmp     eax, [rbx+8]
0x18000c49a  ja      short loc_18000C4F6
0x18000c49c  add     rcx, [rbx]; void *
0x18000c49f  lea     rdx, [rsp+78h+Src]; Src
0x18000c4a4  mov     r8d, edi; Size
0x18000c4a7  call    memcpy_0
0x18000c4ac  mov     ecx, [rbx+0Ch]
0x18000c4af  lea     eax, [rcx+rdi]
0x18000c4b2  mov     [rbx+0Ch], eax
0x18000c4b5  mov     eax, [r15]
0x18000c4b8  test    eax, eax
0x18000c4ba  jnz     short loc_18000C4C0
0x18000c4bc  mov     [r15+4], ecx
0x18000c4c0  add     eax, edi
0x18000c4c2  mov     [r15], eax
0x18000c4c5  jmp     loc_18000C431
0x18000c4ca  cmp     cl, 20h ; ' '
0x18000c4cd  jz      loc_18000C43F
0x18000c4d3  cmp     cl, 9
0x18000c4d6  jz      loc_18000C43F
0x18000c4dc  mov     r8d, ecx
0x18000c4df  lea     rdx, aSyntaxErrorIll; "syntax error:  illegal char found withi"...
0x18000c4e6  lea     rcx, aBparsehexstr; "BparseHexStr"
0x18000c4ed  call    WriteDbgTraceErrorGpd
0x18000c4f2  xor     eax, eax
0x18000c4f4  jmp     short loc_18000C547
0x18000c4f6  lea     rdx, aBwritetoheapOu; "BwriteToHeap: out of heap - restarting."
0x18000c4fd  lea     rcx, aBwritetoheap; "BwriteToHeap"
0x18000c504  call    WriteDbgTraceErrorGpd
0x18000c509  mov     eax, 2
0x18000c50e  cmp     [rbx+8ACh], eax
0x18000c514  jge     short loc_18000C4F2
0x18000c516  mov     [rbx+8ACh], eax
0x18000c51c  mov     [rbx+8B0h], eax
0x18000c522  mov     dword ptr [rbx+8A8h], 0
0x18000c52c  jmp     short loc_18000C4F2
0x18000c52e  test    esi, esi
0x18000c530  jnz     short loc_18000C545
0x18000c532  lea     rdx, aHexStringConta; "hex string contains odd number of hex d"...
0x18000c539  lea     rcx, aBparsehexstr; "BparseHexStr"
0x18000c540  call    WriteDbgTraceErrorGpd
0x18000c545  mov     eax, esi
0x18000c547  mov     rcx, [rsp+78h+var_30]
0x18000c54c  xor     rcx, rsp; StackCookie
0x18000c54f  call    __security_check_cookie
0x18000c554  add     rsp, 50h
0x18000c558  pop     r15
0x18000c55a  pop     r14
0x18000c55c  pop     rdi
0x18000c55d  pop     rsi
0x18000c55e  pop     rbx
0x18000c55f  retn
```
