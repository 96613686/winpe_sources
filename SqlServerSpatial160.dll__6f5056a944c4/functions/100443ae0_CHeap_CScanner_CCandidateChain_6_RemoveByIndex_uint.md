# CHeap<CScanner::CCandidateChain,6>::RemoveByIndex(uint)

- ea: `0x100443ae0`
- end: `0x100443bd2`
- name: `?RemoveByIndex@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAXI@Z`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1004412e0`
- `0x100442350`

## callees

- `0x100443920`
- `0x100443ae0`
- `0x100443da0`

## pseudocode

```c
__int64 __fastcall CHeap<CScanner::CCandidateChain,6>::RemoveByIndex(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  __int64 v5; // r9
  __int64 v6; // r10
  unsigned int v7; // ecx
  __int64 v8; // rcx
  unsigned int v9; // ecx
  __int64 v10; // rcx

  result = *(_QWORD *)(a1 + 8);
  v5 = (unsigned int)(*(_DWORD *)(a1 + 4) - 1);
  v6 = 8LL * a2;
  *(_DWORD *)(*(_QWORD *)(result + v6) + 76LL) = 0;
  if ( a2 >= (unsigned int)v5 )
  {
    v9 = *(_DWORD *)(a1 + 4);
    if ( (unsigned int)v5 < v9 )
    {
      for ( ; (unsigned int)v5 < v9 - 1; v9 = *(_DWORD *)(a1 + 4) )
      {
        v10 = (unsigned int)v5;
        LODWORD(v5) = v5 + 1;
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v10) = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * (unsigned int)v5);
      }
      result = v9 - 1;
      *(_DWORD *)(a1 + 4) = result;
    }
  }
  else
  {
    _mm_lfence();
    *(_QWORD *)(v6 + *(_QWORD *)(a1 + 8)) = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v5);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * a2) + 76LL) = a2;
    v7 = *(_DWORD *)(a1 + 4);
    if ( (unsigned int)v5 < v7 )
    {
      for ( ; (unsigned int)v5 < v7 - 1; v7 = *(_DWORD *)(a1 + 4) )
      {
        v8 = (unsigned int)v5;
        LODWORD(v5) = v5 + 1;
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v8) = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * (unsigned int)v5);
      }
      *(_DWORD *)(a1 + 4) = v7 - 1;
    }
    result = CHeap<CScanner::CCandidateChain,6>::BubbleUp(a1);
    if ( (_DWORD)result == a2 )
    {
      _mm_lfence();
      return CHeap<CScanner::CCandidateChain,6>::PushDown(a1, (unsigned int)result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x100443ae0  mov     [rsp+arg_0], rbx
0x100443ae5  push    rdi
0x100443ae6  sub     rsp, 20h
0x100443aea  mov     rax, [rcx+8]
0x100443aee  mov     rbx, rcx
0x100443af1  mov     r9d, [rcx+4]
0x100443af5  mov     edi, edx
0x100443af7  dec     r9d
0x100443afa  lea     r10, ds:0[rdi*8]
0x100443b02  mov     r8, [rax+r10]
0x100443b06  mov     dword ptr [r8+4Ch], 0
0x100443b0e  cmp     edx, r9d
0x100443b11  jnb     short loc_100443B8C
0x100443b13  lfence
0x100443b16  mov     rdx, [rcx+8]
0x100443b1a  mov     rcx, [rdx+r9*8]
0x100443b1e  mov     [r10+rdx], rcx
0x100443b22  mov     rax, [rbx+8]
0x100443b26  mov     rcx, [rax+r10]
0x100443b2a  mov     [rcx+4Ch], edi
0x100443b2d  mov     ecx, [rbx+4]
0x100443b30  cmp     r9d, ecx
0x100443b33  jnb     short loc_100443B67
0x100443b35  lea     eax, [rcx-1]
0x100443b38  cmp     r9d, eax
0x100443b3b  jnb     short loc_100443B61
0x100443b3d  nop     dword ptr [rax]
0x100443b40  mov     rdx, [rbx+8]
0x100443b44  lea     r8d, [r9+1]
0x100443b48  mov     ecx, r9d
0x100443b4b  mov     r9d, r8d
0x100443b4e  mov     rax, [rdx+r8*8]
0x100443b52  mov     [rdx+rcx*8], rax
0x100443b56  mov     ecx, [rbx+4]
0x100443b59  lea     eax, [rcx-1]
0x100443b5c  cmp     r8d, eax
0x100443b5f  jb      short loc_100443B40
0x100443b61  lea     eax, [rcx-1]
0x100443b64  mov     [rbx+4], eax
0x100443b67  mov     edx, edi
0x100443b69  mov     rcx, rbx
0x100443b6c  call    ?BubbleUp@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAII@Z; CHeap<CScanner::CCandidateChain,6>::BubbleUp(uint)
0x100443b71  cmp     eax, edi
0x100443b73  jnz     short loc_100443BC7
0x100443b75  lfence
0x100443b78  mov     edx, eax
0x100443b7a  mov     rcx, rbx
0x100443b7d  mov     rbx, [rsp+28h+arg_0]
0x100443b82  add     rsp, 20h
0x100443b86  pop     rdi
0x100443b87  jmp     ?PushDown@?$CHeap@VCCandidateChain@CScanner@@$05@@AEAAXI@Z; CHeap<CScanner::CCandidateChain,6>::PushDown(uint)
0x100443b8c  mov     ecx, [rcx+4]
0x100443b8f  cmp     r9d, ecx
0x100443b92  jnb     short loc_100443BC7
0x100443b94  lea     eax, [rcx-1]
0x100443b97  cmp     r9d, eax
0x100443b9a  jnb     short loc_100443BC1
0x100443b9c  nop     dword ptr [rax+00h]
0x100443ba0  mov     rdx, [rbx+8]
0x100443ba4  lea     r8d, [r9+1]
0x100443ba8  mov     ecx, r9d
0x100443bab  mov     r9d, r8d
0x100443bae  mov     rax, [rdx+r8*8]
0x100443bb2  mov     [rdx+rcx*8], rax
0x100443bb6  mov     ecx, [rbx+4]
0x100443bb9  lea     eax, [rcx-1]
0x100443bbc  cmp     r8d, eax
0x100443bbf  jb      short loc_100443BA0
0x100443bc1  lea     eax, [rcx-1]
0x100443bc4  mov     [rbx+4], eax
0x100443bc7  mov     rbx, [rsp+28h+arg_0]
0x100443bcc  add     rsp, 20h
0x100443bd0  pop     rdi
0x100443bd1  retn
```
