# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006560`
- end: `0x140006779`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400050a0`

## callees

- `0x14000369c`
- `0x1400061e4`
- `0x140006560`
- `0x140007618`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006648`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x140006560  push    rbx
0x140006562  push    rbp
0x140006563  push    rsi
0x140006564  push    rdi
0x140006565  push    r12
0x140006567  push    r13
0x140006569  push    r14
0x14000656b  push    r15
0x14000656d  sub     rsp, 28h
0x140006571  mov     [rcx+4], r8d
0x140006575  xor     r13d, r13d
0x140006578  mov     eax, [rdx+8]
0x14000657b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000657f  mov     [rcx+8], eax
0x140006582  mov     rdi, rcx
0x140006585  mov     [rcx+10h], r13
0x140006589  mov     r12, rdx
0x14000658c  movzx   eax, word ptr [rdx+40h]
0x140006590  mov     [rcx+18h], ax
0x140006594  mov     al, [rdx]
0x140006596  mov     [rcx+1Ah], al
0x140006599  mov     [rcx+20h], r13
0x14000659d  mov     rax, [rdx+88h]
0x1400065a4  mov     [rcx+28h], rax
0x1400065a8  mov     rax, [rdx+90h]
0x1400065af  mov     [rcx+30h], rax
0x1400065b3  mov     [rcx+38h], r13
0x1400065b7  mov     rcx, [rdx+38h]
0x1400065bb  lea     edx, [rbp+2]
0x1400065be  test    rcx, rcx
0x1400065c1  jnz     short loc_1400065C8
0x1400065c3  mov     r8d, edx
0x1400065c6  jmp     short loc_1400065D8
0x1400065c8  mov     rax, rbp
0x1400065cb  inc     rax
0x1400065ce  cmp     [rcx+rax], r13b
0x1400065d2  jnz     short loc_1400065CB
0x1400065d4  lea     r8, [rax+1]; unsigned __int64
0x1400065d8  mov     rcx, [r12+80h]
0x1400065e0  test    rcx, rcx
0x1400065e3  jz      short loc_1400065F5
0x1400065e5  mov     rax, rbp
0x1400065e8  inc     rax
0x1400065eb  cmp     [rcx+rax], r13b
0x1400065ef  jnz     short loc_1400065E8
0x1400065f1  lea     rdx, [rax+1]
0x1400065f5  mov     rcx, [r12+18h]
0x1400065fa  test    rcx, rcx
0x1400065fd  jnz     short loc_140006604
0x1400065ff  lea     eax, [rcx+2]
0x140006602  jmp     short loc_140006619
0x140006604  mov     rax, rbp
0x140006607  inc     rax
0x14000660a  cmp     [rcx+rax*2], r13w
0x14000660f  jnz     short loc_140006607
0x140006611  lea     rax, ds:2[rax*2]
0x140006619  lea     r14, [rdx+rax]
0x14000661d  add     r14, r8
0x140006620  lea     rsi, [rdi+48h]
0x140006624  cmp     [rdi+40h], r13
0x140006628  jz      short loc_14000662F
0x14000662a  cmp     [rsi], r14
0x14000662d  jnb     short loc_140006663
0x14000662f  mov     rdx, r14; dwBytes
0x140006632  mov     ecx, 8; dwFlags
0x140006637  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000663c  mov     r15, rax
0x14000663f  test    rax, rax
0x140006642  jz      short loc_140006663
0x140006644  mov     rbx, [rdi+40h]
0x140006648  call    cs:__imp_GetProcessHeap
0x14000664e  mov     r8, rbx; lpMem
0x140006651  xor     edx, edx; dwFlags
0x140006653  mov     rcx, rax; hHeap
0x140006656  call    cs:__imp_HeapFree
0x14000665c  mov     [rdi+40h], r15
0x140006660  mov     [rsi], r14
0x140006663  mov     rbx, [rdi+40h]
0x140006667  test    rbx, rbx
0x14000666a  jz      loc_140006768
0x140006670  mov     rdx, [rsi]; DestinationSize
0x140006673  lea     rsi, [rdx+rbx]
0x140006677  cmp     rbx, rsi
0x14000667a  jz      short loc_1400066BA
0x14000667c  mov     r8, [r12+38h]; Source
0x140006681  test    r8, r8
0x140006684  jz      short loc_1400066BA
0x140006686  cmp     [r8], r13b
0x140006689  jz      short loc_1400066BA
0x14000668b  mov     rax, rbp
0x14000668e  inc     rax
0x140006691  cmp     [r8+rax], r13b
0x140006695  jnz     short loc_14000668E
0x140006697  lea     r14, [rax+1]
0x14000669b  cmp     rdx, r14
0x14000669e  jnb     short loc_1400066A6
0x1400066a0  mov     [rdi+10h], r13
0x1400066a4  jmp     short loc_1400066C3
0x1400066a6  mov     r9, r14; SourceSize
0x1400066a9  mov     rcx, rbx; Destination
0x1400066ac  call    memcpy_s
0x1400066b1  mov     [rdi+10h], rbx
0x1400066b5  add     rbx, r14
0x1400066b8  jmp     short loc_1400066BE
0x1400066ba  mov     [rdi+10h], r13
0x1400066be  cmp     rbx, rsi
0x1400066c1  jz      short loc_14000670A
0x1400066c3  mov     r8, [r12+80h]; Source
0x1400066cb  test    r8, r8
0x1400066ce  jz      short loc_14000670A
0x1400066d0  cmp     [r8], r13b
0x1400066d3  jz      short loc_14000670A
0x1400066d5  mov     rax, rbp
0x1400066d8  inc     rax
0x1400066db  cmp     [r8+rax], r13b
0x1400066df  jnz     short loc_1400066D8
0x1400066e1  mov     rdx, rsi
0x1400066e4  lea     r14, [rax+1]
0x1400066e8  sub     rdx, rbx; DestinationSize
0x1400066eb  cmp     rdx, r14
0x1400066ee  jnb     short loc_1400066F6
0x1400066f0  mov     [rdi+20h], r13
0x1400066f4  jmp     short loc_140006713
0x1400066f6  mov     r9, r14; SourceSize
0x1400066f9  mov     rcx, rbx; Destination
0x1400066fc  call    memcpy_s
0x140006701  mov     [rdi+20h], rbx
0x140006705  add     rbx, r14
0x140006708  jmp     short loc_14000670E
0x14000670a  mov     [rdi+20h], r13
0x14000670e  cmp     rbx, rsi
0x140006711  jz      short loc_140006754
0x140006713  mov     r8, [r12+18h]; Source
0x140006718  test    r8, r8
0x14000671b  jz      short loc_140006754
0x14000671d  cmp     [r8], r13w
0x140006721  jz      short loc_140006754
0x140006723  inc     rbp
0x140006726  cmp     [r8+rbp*2], r13w
0x14000672b  jnz     short loc_140006723
0x14000672d  mov     rdx, rsi
0x140006730  lea     r14, ds:2[rbp*2]
0x140006738  sub     rdx, rbx; DestinationSize
0x14000673b  cmp     rdx, r14
0x14000673e  jb      short loc_140006754
0x140006740  mov     r9, r14; SourceSize
0x140006743  mov     rcx, rbx; Destination
0x140006746  call    memcpy_s
0x14000674b  mov     [rdi+38h], rbx
0x14000674f  add     rbx, r14
0x140006752  jmp     short loc_140006758
0x140006754  mov     [rdi+38h], r13
0x140006758  sub     rsi, rbx
0x14000675b  xor     edx, edx; Val
0x14000675d  mov     r8, rsi; Size
0x140006760  mov     rcx, rbx; void *
0x140006763  call    memset_0
0x140006768  add     rsp, 28h
0x14000676c  pop     r15
0x14000676e  pop     r14
0x140006770  pop     r13
0x140006772  pop     r12
0x140006774  pop     rdi
0x140006775  pop     rsi
0x140006776  pop     rbp
0x140006777  pop     rbx
0x140006778  retn
```
