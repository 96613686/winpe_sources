# CfpExecuteAckDelete

- ea: `0x18000a234`
- end: `0x18000a4bf`
- name: `CfpExecuteAckDelete`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ba0`

## callees

- `0x180001a80`
- `0x180008c64`
- `0x18000a234`
- `0x18000ad34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a47e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a47e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a48c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a48c`
- `FLTLIB!FilterSendMessage` at `0x18000a467`
- `FLTLIB!FilterSendMessage` at `0x18000a467`

## pseudocode

```c
__int64 __fastcall CfpExecuteAckDelete(__int64 a1, __int64 a2)
{
  _BYTE *v2; // rdi
  unsigned int v3; // esi
  int MessageHeaderSize; // eax
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  HANDLE ProcessHeap; // rax
  HRESULT v10; // ebx
  int v11; // r15d
  int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  HANDLE v19; // rax
  DWORD BytesReturned[4]; // [rsp+30h] [rbp-158h] BYREF
  _BYTE InBuffer[256]; // [rsp+40h] [rbp-148h] BYREF

  v2 = InBuffer;
  v3 = 256;
  BytesReturned[0] = 0;
  MessageHeaderSize = CfpGetMessageHeaderSize();
  if ( ((MessageHeaderSize + 3) & 0xFFFFFFFC) + 12 < v7 )
    goto LABEL_8;
  v3 = ((CfpGetMessageHeaderSize() + 11) & 0xFFFFFFFC) + 4;
  if ( v3 <= v8 )
  {
    v10 = 87;
    if ( v3 < 0xC8 )
      goto LABEL_9;
    goto LABEL_8;
  }
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 0, v3);
  v10 = v2 == 0 ? 8 : 0;
  if ( !v2 )
    v10 |= 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_8:
    v10 = 0;
LABEL_9:
    if ( v10 )
      v10 |= 0x80070000;
    if ( v10 < 0 )
      goto LABEL_31;
    v11 = *(_DWORD *)(a2 + 12);
    v12 = *(_DWORD *)(a2 + 8);
    v10 = CfpBuildMessageHeader(v2, v3, a1, 513);
    if ( v10 < 0 )
      goto LABEL_31;
    if ( v3 >= 0x18 )
    {
      if ( *((_WORD *)v2 + 7) <= 0xAu )
        goto LABEL_16;
      if ( v3 < 0x68 )
        goto LABEL_14;
      v13 = *((unsigned int *)v2 + 2);
      if ( ((v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v3 )
        goto LABEL_14;
      v14 = ((_DWORD)v13 + 3) & 0xFFFFFFFC;
      *((_DWORD *)v2 + 2) = v14;
      if ( *((_WORD *)v2 + 48) )
        *((_WORD *)v2 + 6) |= 1u;
      *((_DWORD *)v2 + 25) = v14;
      *((_DWORD *)v2 + 24) = 262154;
      *(_DWORD *)&v2[v14] = v11;
      *((_DWORD *)v2 + 2) += 4;
      if ( *((_WORD *)v2 + 7) <= 5u )
        goto LABEL_16;
      v15 = *((unsigned int *)v2 + 2);
      if ( ((v15 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v3 )
        goto LABEL_14;
      v16 = ((_DWORD)v15 + 3) & 0xFFFFFFFC;
      *((_DWORD *)v2 + 2) = v16;
      if ( *((_WORD *)v2 + 28) )
        *((_WORD *)v2 + 6) |= 1u;
      *((_DWORD *)v2 + 15) = v16;
      *((_DWORD *)v2 + 14) = 262154;
      *(_DWORD *)&v2[v16] = v12;
      *((_DWORD *)v2 + 2) += 4;
      if ( *((_WORD *)v2 + 7) <= 0xDu )
      {
LABEL_16:
        v10 = -1073741811;
        goto LABEL_31;
      }
      if ( v3 >= 0x80 )
      {
        v17 = *((unsigned int *)v2 + 2);
        if ( ((v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v3 )
        {
          v18 = ((_DWORD)v17 + 3) & 0xFFFFFFFC;
          *((_DWORD *)v2 + 2) = v18;
          if ( *((_WORD *)v2 + 60) )
            *((_WORD *)v2 + 6) |= 1u;
          *((_DWORD *)v2 + 31) = v18;
          *((_DWORD *)v2 + 30) = 262154;
          *(_DWORD *)&v2[v18] = 4;
          *((_DWORD *)v2 + 2) += 4;
          *((_WORD *)v2 + 6) &= ~2u;
          *((_DWORD *)v2 + 1) = 0;
          v10 = FilterSendMessage(hPort, v2, *((_DWORD *)v2 + 2), 0, 0, BytesReturned);
          goto LABEL_31;
        }
      }
    }
LABEL_14:
    v10 = -1073741789;
  }
LABEL_31:
  if ( v2 && v2 != InBuffer )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v2);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a234  mov     [rsp+arg_10], rbx
0x18000a239  push    rbp
0x18000a23a  push    rsi
0x18000a23b  push    rdi
0x18000a23c  push    r12
0x18000a23e  push    r13
0x18000a240  push    r14
0x18000a242  push    r15
0x18000a244  sub     rsp, 150h
0x18000a24b  mov     rax, cs:__security_cookie
0x18000a252  xor     rax, rsp
0x18000a255  mov     [rsp+188h+var_48], rax
0x18000a25d  mov     r8d, 100h
0x18000a263  lea     rdi, [rsp+188h+InBuffer]
0x18000a268  xor     r12d, r12d
0x18000a26b  mov     esi, r8d
0x18000a26e  mov     [rsp+188h+BytesReturned], r12d
0x18000a273  mov     r14, rdx
0x18000a276  mov     rbp, rcx
0x18000a279  call    CfpGetMessageHeaderSize
0x18000a27e  add     eax, 3
0x18000a281  mov     r13d, 0FFFFFFFCh
0x18000a287  and     eax, r13d
0x18000a28a  mov     r15d, 80070000h
0x18000a290  add     eax, 0Ch
0x18000a293  cmp     eax, r8d
0x18000a296  jb      short loc_18000A2ED
0x18000a298  call    CfpGetMessageHeaderSize
0x18000a29d  lea     esi, [rax+0Bh]
0x18000a2a0  and     esi, r13d
0x18000a2a3  add     esi, 4
0x18000a2a6  cmp     esi, r8d
0x18000a2a9  jbe     short loc_18000A2E0
0x18000a2ab  call    cs:__imp_GetProcessHeap
0x18000a2b1  mov     r8d, esi; dwBytes
0x18000a2b4  xor     edx, edx; dwFlags
0x18000a2b6  mov     rcx, rax; hHeap
0x18000a2b9  call    cs:__imp_HeapAlloc
0x18000a2bf  mov     rdi, rax
0x18000a2c2  neg     rax
0x18000a2c5  sbb     ebx, ebx
0x18000a2c7  not     ebx
0x18000a2c9  and     ebx, 8
0x18000a2cc  mov     eax, ebx
0x18000a2ce  or      eax, r15d
0x18000a2d1  test    rdi, rdi
0x18000a2d4  cmovz   ebx, eax
0x18000a2d7  test    ebx, ebx
0x18000a2d9  jns     short loc_18000A2ED
0x18000a2db  jmp     loc_18000A46F
0x18000a2e0  mov     ebx, 57h ; 'W'
0x18000a2e5  cmp     esi, 0C8h
0x18000a2eb  jb      short loc_18000A2F0
0x18000a2ed  mov     ebx, r12d
0x18000a2f0  mov     eax, ebx
0x18000a2f2  or      eax, r15d
0x18000a2f5  test    ebx, ebx
0x18000a2f7  cmovnz  ebx, eax
0x18000a2fa  test    ebx, ebx
0x18000a2fc  js      loc_18000A46F
0x18000a302  mov     r15d, [r14+0Ch]
0x18000a306  mov     r9d, 201h
0x18000a30c  mov     r14d, [r14+8]
0x18000a310  mov     r8, rbp
0x18000a313  mov     edx, esi
0x18000a315  mov     rcx, rdi
0x18000a318  call    CfpBuildMessageHeader
0x18000a31d  mov     ebx, eax
0x18000a31f  test    eax, eax
0x18000a321  js      loc_18000A46F
0x18000a327  cmp     esi, 18h
0x18000a32a  jnb     short loc_18000A336
0x18000a32c  mov     ebx, 0C0000023h
0x18000a331  jmp     loc_18000A46F
0x18000a336  mov     r9d, 0Ah
0x18000a33c  cmp     r9w, [rdi+0Eh]
0x18000a341  jb      short loc_18000A34D
0x18000a343  mov     ebx, 0C000000Dh
0x18000a348  jmp     loc_18000A46F
0x18000a34d  cmp     esi, 68h ; 'h'
0x18000a350  jb      short loc_18000A32C
0x18000a352  mov     edx, [rdi+8]
0x18000a355  mov     r8d, 4
0x18000a35b  mov     eax, esi
0x18000a35d  lea     rcx, [rdx+3]
0x18000a361  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000a365  add     rcx, r8
0x18000a368  cmp     rcx, rax
0x18000a36b  ja      short loc_18000A32C
0x18000a36d  lea     eax, [rdx+3]
0x18000a370  and     eax, r13d
0x18000a373  mov     [rdi+8], eax
0x18000a376  cmp     [rdi+60h], r12w
0x18000a37b  jz      short loc_18000A382
0x18000a37d  or      word ptr [rdi+0Ch], 1
0x18000a382  mov     [rdi+64h], eax
0x18000a385  mov     dword ptr [rdi+60h], 4000Ah
0x18000a38c  mov     [rax+rdi], r15d
0x18000a390  mov     eax, 5
0x18000a395  add     [rdi+8], r8d
0x18000a399  cmp     ax, [rdi+0Eh]
0x18000a39d  jnb     short loc_18000A343
0x18000a39f  mov     edx, [rdi+8]
0x18000a3a2  mov     eax, esi
0x18000a3a4  lea     rcx, [rdx+3]
0x18000a3a8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000a3ac  add     rcx, r8
0x18000a3af  cmp     rcx, rax
0x18000a3b2  ja      loc_18000A32C
0x18000a3b8  lea     eax, [rdx+3]
0x18000a3bb  and     eax, r13d
0x18000a3be  mov     [rdi+8], eax
0x18000a3c1  cmp     [rdi+38h], r12w
0x18000a3c6  jz      short loc_18000A3CD
0x18000a3c8  or      word ptr [rdi+0Ch], 1
0x18000a3cd  mov     [rdi+3Ch], eax
0x18000a3d0  mov     dword ptr [rdi+38h], 4000Ah
0x18000a3d7  mov     [rax+rdi], r14d
0x18000a3db  mov     eax, 0Dh
0x18000a3e0  add     [rdi+8], r8d
0x18000a3e4  cmp     ax, [rdi+0Eh]
0x18000a3e8  jnb     loc_18000A343
0x18000a3ee  cmp     esi, 80h
0x18000a3f4  jb      loc_18000A32C
0x18000a3fa  mov     edx, [rdi+8]
0x18000a3fd  mov     eax, esi
0x18000a3ff  lea     rcx, [rdx+3]
0x18000a403  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18000a407  add     rcx, r8
0x18000a40a  cmp     rcx, rax
0x18000a40d  ja      loc_18000A32C
0x18000a413  lea     eax, [rdx+3]
0x18000a416  and     eax, r13d
0x18000a419  mov     [rdi+8], eax
0x18000a41c  cmp     [rdi+78h], r12w
0x18000a421  jz      short loc_18000A428
0x18000a423  or      word ptr [rdi+0Ch], 1
0x18000a428  mov     [rdi+7Ch], eax
0x18000a42b  mov     dword ptr [rdi+78h], 4000Ah
0x18000a432  mov     [rax+rdi], r8d
0x18000a436  mov     eax, 0FFFDh
0x18000a43b  add     [rdi+8], r8d
0x18000a43f  and     [rdi+0Ch], ax
0x18000a443  mov     [rdi+4], r12d
0x18000a447  mov     r8d, [rdi+8]; dwInBufferSize
0x18000a44b  lea     rax, [rsp+188h+BytesReturned]
0x18000a450  mov     rcx, qword ptr cs:hPort; hPort
0x18000a457  xor     r9d, r9d; lpOutBuffer
0x18000a45a  mov     [rsp+188h+lpBytesReturned], rax; lpBytesReturned
0x18000a45f  mov     rdx, rdi; lpInBuffer
0x18000a462  mov     [rsp+188h+dwOutBufferSize], r12d; dwOutBufferSize
0x18000a467  call    cs:__imp_FilterSendMessage
0x18000a46d  mov     ebx, eax
0x18000a46f  test    rdi, rdi
0x18000a472  jz      short loc_18000A492
0x18000a474  lea     rax, [rsp+188h+InBuffer]
0x18000a479  cmp     rdi, rax
0x18000a47c  jz      short loc_18000A492
0x18000a47e  call    cs:__imp_GetProcessHeap
0x18000a484  mov     r8, rdi; lpMem
0x18000a487  xor     edx, edx; dwFlags
0x18000a489  mov     rcx, rax; hHeap
0x18000a48c  call    cs:__imp_HeapFree
0x18000a492  mov     eax, ebx
0x18000a494  mov     rcx, [rsp+188h+var_48]
0x18000a49c  xor     rcx, rsp; StackCookie
0x18000a49f  call    __security_check_cookie
0x18000a4a4  mov     rbx, [rsp+188h+arg_10]
0x18000a4ac  add     rsp, 150h
0x18000a4b3  pop     r15
0x18000a4b5  pop     r14
0x18000a4b7  pop     r13
0x18000a4b9  pop     r12
0x18000a4bb  pop     rdi
0x18000a4bc  pop     rsi
0x18000a4bd  pop     rbp
0x18000a4be  retn
```
