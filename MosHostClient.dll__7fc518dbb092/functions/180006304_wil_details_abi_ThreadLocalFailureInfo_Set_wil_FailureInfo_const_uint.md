# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006304`
- end: `0x18000651d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049f0`

## callees

- `0x180002fc4`
- `0x180005bac`
- `0x180006304`
- `0x1800073cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063ec`

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
0x180006304  push    rbx
0x180006306  push    rbp
0x180006307  push    rsi
0x180006308  push    rdi
0x180006309  push    r12
0x18000630b  push    r13
0x18000630d  push    r14
0x18000630f  push    r15
0x180006311  sub     rsp, 28h
0x180006315  mov     [rcx+4], r8d
0x180006319  xor     r13d, r13d
0x18000631c  mov     eax, [rdx+8]
0x18000631f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180006323  mov     [rcx+8], eax
0x180006326  mov     rdi, rcx
0x180006329  mov     [rcx+10h], r13
0x18000632d  mov     r12, rdx
0x180006330  movzx   eax, word ptr [rdx+40h]
0x180006334  mov     [rcx+18h], ax
0x180006338  mov     al, [rdx]
0x18000633a  mov     [rcx+1Ah], al
0x18000633d  mov     [rcx+20h], r13
0x180006341  mov     rax, [rdx+88h]
0x180006348  mov     [rcx+28h], rax
0x18000634c  mov     rax, [rdx+90h]
0x180006353  mov     [rcx+30h], rax
0x180006357  mov     [rcx+38h], r13
0x18000635b  mov     rcx, [rdx+38h]
0x18000635f  lea     edx, [rbp+2]
0x180006362  test    rcx, rcx
0x180006365  jnz     short loc_18000636C
0x180006367  mov     r8d, edx
0x18000636a  jmp     short loc_18000637C
0x18000636c  mov     rax, rbp
0x18000636f  inc     rax
0x180006372  cmp     [rcx+rax], r13b
0x180006376  jnz     short loc_18000636F
0x180006378  lea     r8, [rax+1]; unsigned __int64
0x18000637c  mov     rcx, [r12+80h]
0x180006384  test    rcx, rcx
0x180006387  jz      short loc_180006399
0x180006389  mov     rax, rbp
0x18000638c  inc     rax
0x18000638f  cmp     [rcx+rax], r13b
0x180006393  jnz     short loc_18000638C
0x180006395  lea     rdx, [rax+1]
0x180006399  mov     rcx, [r12+18h]
0x18000639e  test    rcx, rcx
0x1800063a1  jnz     short loc_1800063A8
0x1800063a3  lea     eax, [rcx+2]
0x1800063a6  jmp     short loc_1800063BD
0x1800063a8  mov     rax, rbp
0x1800063ab  inc     rax
0x1800063ae  cmp     [rcx+rax*2], r13w
0x1800063b3  jnz     short loc_1800063AB
0x1800063b5  lea     rax, ds:2[rax*2]
0x1800063bd  lea     r14, [rdx+rax]
0x1800063c1  add     r14, r8
0x1800063c4  lea     rsi, [rdi+48h]
0x1800063c8  cmp     [rdi+40h], r13
0x1800063cc  jz      short loc_1800063D3
0x1800063ce  cmp     [rsi], r14
0x1800063d1  jnb     short loc_180006407
0x1800063d3  mov     rdx, r14; dwBytes
0x1800063d6  mov     ecx, 8; dwFlags
0x1800063db  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800063e0  mov     r15, rax
0x1800063e3  test    rax, rax
0x1800063e6  jz      short loc_180006407
0x1800063e8  mov     rbx, [rdi+40h]
0x1800063ec  call    cs:__imp_GetProcessHeap
0x1800063f2  mov     r8, rbx; lpMem
0x1800063f5  xor     edx, edx; dwFlags
0x1800063f7  mov     rcx, rax; hHeap
0x1800063fa  call    cs:__imp_HeapFree
0x180006400  mov     [rdi+40h], r15
0x180006404  mov     [rsi], r14
0x180006407  mov     rbx, [rdi+40h]
0x18000640b  test    rbx, rbx
0x18000640e  jz      loc_18000650C
0x180006414  mov     rdx, [rsi]; DestinationSize
0x180006417  lea     rsi, [rdx+rbx]
0x18000641b  cmp     rbx, rsi
0x18000641e  jz      short loc_18000645E
0x180006420  mov     r8, [r12+38h]; Source
0x180006425  test    r8, r8
0x180006428  jz      short loc_18000645E
0x18000642a  cmp     [r8], r13b
0x18000642d  jz      short loc_18000645E
0x18000642f  mov     rax, rbp
0x180006432  inc     rax
0x180006435  cmp     [r8+rax], r13b
0x180006439  jnz     short loc_180006432
0x18000643b  lea     r14, [rax+1]
0x18000643f  cmp     rdx, r14
0x180006442  jnb     short loc_18000644A
0x180006444  mov     [rdi+10h], r13
0x180006448  jmp     short loc_180006467
0x18000644a  mov     r9, r14; SourceSize
0x18000644d  mov     rcx, rbx; Destination
0x180006450  call    memcpy_s
0x180006455  mov     [rdi+10h], rbx
0x180006459  add     rbx, r14
0x18000645c  jmp     short loc_180006462
0x18000645e  mov     [rdi+10h], r13
0x180006462  cmp     rbx, rsi
0x180006465  jz      short loc_1800064AE
0x180006467  mov     r8, [r12+80h]; Source
0x18000646f  test    r8, r8
0x180006472  jz      short loc_1800064AE
0x180006474  cmp     [r8], r13b
0x180006477  jz      short loc_1800064AE
0x180006479  mov     rax, rbp
0x18000647c  inc     rax
0x18000647f  cmp     [r8+rax], r13b
0x180006483  jnz     short loc_18000647C
0x180006485  mov     rdx, rsi
0x180006488  lea     r14, [rax+1]
0x18000648c  sub     rdx, rbx; DestinationSize
0x18000648f  cmp     rdx, r14
0x180006492  jnb     short loc_18000649A
0x180006494  mov     [rdi+20h], r13
0x180006498  jmp     short loc_1800064B7
0x18000649a  mov     r9, r14; SourceSize
0x18000649d  mov     rcx, rbx; Destination
0x1800064a0  call    memcpy_s
0x1800064a5  mov     [rdi+20h], rbx
0x1800064a9  add     rbx, r14
0x1800064ac  jmp     short loc_1800064B2
0x1800064ae  mov     [rdi+20h], r13
0x1800064b2  cmp     rbx, rsi
0x1800064b5  jz      short loc_1800064F8
0x1800064b7  mov     r8, [r12+18h]; Source
0x1800064bc  test    r8, r8
0x1800064bf  jz      short loc_1800064F8
0x1800064c1  cmp     [r8], r13w
0x1800064c5  jz      short loc_1800064F8
0x1800064c7  inc     rbp
0x1800064ca  cmp     [r8+rbp*2], r13w
0x1800064cf  jnz     short loc_1800064C7
0x1800064d1  mov     rdx, rsi
0x1800064d4  lea     r14, ds:2[rbp*2]
0x1800064dc  sub     rdx, rbx; DestinationSize
0x1800064df  cmp     rdx, r14
0x1800064e2  jb      short loc_1800064F8
0x1800064e4  mov     r9, r14; SourceSize
0x1800064e7  mov     rcx, rbx; Destination
0x1800064ea  call    memcpy_s
0x1800064ef  mov     [rdi+38h], rbx
0x1800064f3  add     rbx, r14
0x1800064f6  jmp     short loc_1800064FC
0x1800064f8  mov     [rdi+38h], r13
0x1800064fc  sub     rsi, rbx
0x1800064ff  xor     edx, edx; Val
0x180006501  mov     r8, rsi; Size
0x180006504  mov     rcx, rbx; void *
0x180006507  call    memset_0
0x18000650c  add     rsp, 28h
0x180006510  pop     r15
0x180006512  pop     r14
0x180006514  pop     r13
0x180006516  pop     r12
0x180006518  pop     rdi
0x180006519  pop     rsi
0x18000651a  pop     rbp
0x18000651b  pop     rbx
0x18000651c  retn
```
