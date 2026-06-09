# CRTree::ComputeEnvelope(CRTree::Node &)

- ea: `0x10042f940`
- end: `0x10042fa1c`
- name: `?ComputeEnvelope@CRTree@@IEAAJAEAUNode@1@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CRTree *__hidden this, struct Node *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10042f230`
- `0x10042f940`

## callees

- `0x10042f940`

## pseudocode

```c
__int64 __fastcall CRTree::ComputeEnvelope(CRTree *this, struct Node *a2)
{
  __int64 result; // rax
  unsigned int v5; // edi
  __int64 v6; // rsi
  unsigned int lpVtbl_high; // eax
  struct Node *v8; // rbp
  struct Node *v9; // rsi

  if ( LOBYTE(a2[5].lpVtbl) )
  {
    result = (*(__int64 (__fastcall **)(CRTree *))(*(_QWORD *)this + 16LL))(this);
    v5 = result;
    if ( (int)result < 0 )
    {
      _mm_lfence();
      return result;
    }
    return v5;
  }
  v6 = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (unsigned int)(LODWORD(a2->lpVtbl) / *((_DWORD *)this + 37)))
     + 48LL * (unsigned int)(LODWORD(a2->lpVtbl) % *((_DWORD *)this + 37));
  result = CRTree::ComputeEnvelope(this, (struct Node *)v6);
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    lpVtbl_high = HIDWORD(a2->lpVtbl);
    v8 = a2 + 1;
    *(_OWORD *)&a2[1].lpVtbl = *(_OWORD *)(v6 + 8);
    *(_OWORD *)&a2[3].lpVtbl = *(_OWORD *)(v6 + 24);
    v9 = (struct Node *)(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (lpVtbl_high / *((_DWORD *)this + 37)))
                       + 48LL * (lpVtbl_high % *((_DWORD *)this + 37)));
    result = CRTree::ComputeEnvelope(this, v9);
    v5 = result;
    _mm_lfence();
    if ( (int)result >= 0 )
    {
      (*(void (__fastcall **)(CRTree *, struct Node *, struct Node *))(*(_QWORD *)this + 32LL))(this, v9 + 1, v8);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10042f940  mov     [rsp+arg_0], rbx
0x10042f945  mov     [rsp+arg_8], rbp
0x10042f94a  mov     [rsp+arg_10], rsi
0x10042f94f  push    rdi
0x10042f950  sub     rsp, 20h
0x10042f954  cmp     byte ptr [rdx+28h], 0
0x10042f958  mov     rdi, rdx
0x10042f95b  mov     rbx, rcx
0x10042f95e  jz      short loc_10042F978
0x10042f960  mov     rax, [rcx]
0x10042f963  call    qword ptr [rax+10h]
0x10042f966  mov     edi, eax
0x10042f968  test    eax, eax
0x10042f96a  jns     loc_10042FA05
0x10042f970  lfence
0x10042f973  jmp     loc_10042FA07
0x10042f978  mov     eax, [rdi]
0x10042f97a  xor     edx, edx
0x10042f97c  div     dword ptr [rcx+94h]
0x10042f982  mov     ecx, edx
0x10042f984  mov     edx, eax
0x10042f986  mov     rax, [rbx+88h]
0x10042f98d  lea     rsi, [rcx+rcx*2]
0x10042f991  mov     rcx, rbx; this
0x10042f994  shl     rsi, 4
0x10042f998  add     rsi, [rax+rdx*8]
0x10042f99c  mov     rdx, rsi; struct Node *
0x10042f99f  call    ?ComputeEnvelope@CRTree@@IEAAJAEAUNode@1@@Z; CRTree::ComputeEnvelope(CRTree::Node &)
0x10042f9a4  lfence
0x10042f9a7  test    eax, eax
0x10042f9a9  js      short loc_10042FA07
0x10042f9ab  movups  xmm0, xmmword ptr [rsi+8]
0x10042f9af  mov     eax, [rdi+4]
0x10042f9b2  lea     rbp, [rdi+8]
0x10042f9b6  xor     edx, edx
0x10042f9b8  movups  xmmword ptr [rbp+0], xmm0
0x10042f9bc  movups  xmm1, xmmword ptr [rsi+18h]
0x10042f9c0  movups  xmmword ptr [rbp+10h], xmm1
0x10042f9c4  div     dword ptr [rbx+94h]
0x10042f9ca  mov     ecx, edx
0x10042f9cc  mov     edx, eax
0x10042f9ce  mov     rax, [rbx+88h]
0x10042f9d5  lea     rsi, [rcx+rcx*2]
0x10042f9d9  mov     rcx, rbx; this
0x10042f9dc  shl     rsi, 4
0x10042f9e0  add     rsi, [rax+rdx*8]
0x10042f9e4  mov     rdx, rsi; struct Node *
0x10042f9e7  call    ?ComputeEnvelope@CRTree@@IEAAJAEAUNode@1@@Z; CRTree::ComputeEnvelope(CRTree::Node &)
0x10042f9ec  mov     edi, eax
0x10042f9ee  lfence
0x10042f9f1  test    eax, eax
0x10042f9f3  js      short loc_10042FA07
0x10042f9f5  mov     rax, [rbx]
0x10042f9f8  lea     rdx, [rsi+8]
0x10042f9fc  mov     r8, rbp
0x10042f9ff  mov     rcx, rbx
0x10042fa02  call    qword ptr [rax+20h]
0x10042fa05  mov     eax, edi
0x10042fa07  mov     rbx, [rsp+28h+arg_0]
0x10042fa0c  mov     rbp, [rsp+28h+arg_8]
0x10042fa11  mov     rsi, [rsp+28h+arg_10]
0x10042fa16  add     rsp, 20h
0x10042fa1a  pop     rdi
0x10042fa1b  retn
```
