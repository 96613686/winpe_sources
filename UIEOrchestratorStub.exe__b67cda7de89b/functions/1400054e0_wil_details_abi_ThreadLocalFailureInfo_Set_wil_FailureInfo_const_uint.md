# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400054e0`
- end: `0x1400056f9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004120`

## callees

- `0x140002c58`
- `0x140005178`
- `0x1400054e0`
- `0x1400064c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400055c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400055d6`

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
0x1400054e0  push    rbx
0x1400054e2  push    rbp
0x1400054e3  push    rsi
0x1400054e4  push    rdi
0x1400054e5  push    r12
0x1400054e7  push    r13
0x1400054e9  push    r14
0x1400054eb  push    r15
0x1400054ed  sub     rsp, 28h
0x1400054f1  mov     [rcx+4], r8d
0x1400054f5  xor     r13d, r13d
0x1400054f8  mov     eax, [rdx+8]
0x1400054fb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400054ff  mov     [rcx+8], eax
0x140005502  mov     rdi, rcx
0x140005505  mov     [rcx+10h], r13
0x140005509  mov     r12, rdx
0x14000550c  movzx   eax, word ptr [rdx+40h]
0x140005510  mov     [rcx+18h], ax
0x140005514  mov     al, [rdx]
0x140005516  mov     [rcx+1Ah], al
0x140005519  mov     [rcx+20h], r13
0x14000551d  mov     rax, [rdx+88h]
0x140005524  mov     [rcx+28h], rax
0x140005528  mov     rax, [rdx+90h]
0x14000552f  mov     [rcx+30h], rax
0x140005533  mov     [rcx+38h], r13
0x140005537  mov     rcx, [rdx+38h]
0x14000553b  lea     edx, [rbp+2]
0x14000553e  test    rcx, rcx
0x140005541  jnz     short loc_140005548
0x140005543  mov     r8d, edx
0x140005546  jmp     short loc_140005558
0x140005548  mov     rax, rbp
0x14000554b  inc     rax
0x14000554e  cmp     [rcx+rax], r13b
0x140005552  jnz     short loc_14000554B
0x140005554  lea     r8, [rax+1]; unsigned __int64
0x140005558  mov     rcx, [r12+80h]
0x140005560  test    rcx, rcx
0x140005563  jz      short loc_140005575
0x140005565  mov     rax, rbp
0x140005568  inc     rax
0x14000556b  cmp     [rcx+rax], r13b
0x14000556f  jnz     short loc_140005568
0x140005571  lea     rdx, [rax+1]
0x140005575  mov     rcx, [r12+18h]
0x14000557a  test    rcx, rcx
0x14000557d  jnz     short loc_140005584
0x14000557f  lea     eax, [rcx+2]
0x140005582  jmp     short loc_140005599
0x140005584  mov     rax, rbp
0x140005587  inc     rax
0x14000558a  cmp     [rcx+rax*2], r13w
0x14000558f  jnz     short loc_140005587
0x140005591  lea     rax, ds:2[rax*2]
0x140005599  lea     r14, [rdx+rax]
0x14000559d  add     r14, r8
0x1400055a0  lea     rsi, [rdi+48h]
0x1400055a4  cmp     [rdi+40h], r13
0x1400055a8  jz      short loc_1400055AF
0x1400055aa  cmp     [rsi], r14
0x1400055ad  jnb     short loc_1400055E3
0x1400055af  mov     rdx, r14; dwBytes
0x1400055b2  mov     ecx, 8; dwFlags
0x1400055b7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400055bc  mov     r15, rax
0x1400055bf  test    rax, rax
0x1400055c2  jz      short loc_1400055E3
0x1400055c4  mov     rbx, [rdi+40h]
0x1400055c8  call    cs:__imp_GetProcessHeap
0x1400055ce  mov     r8, rbx; lpMem
0x1400055d1  xor     edx, edx; dwFlags
0x1400055d3  mov     rcx, rax; hHeap
0x1400055d6  call    cs:__imp_HeapFree
0x1400055dc  mov     [rdi+40h], r15
0x1400055e0  mov     [rsi], r14
0x1400055e3  mov     rbx, [rdi+40h]
0x1400055e7  test    rbx, rbx
0x1400055ea  jz      loc_1400056E8
0x1400055f0  mov     rdx, [rsi]; DestinationSize
0x1400055f3  lea     rsi, [rdx+rbx]
0x1400055f7  cmp     rbx, rsi
0x1400055fa  jz      short loc_14000563A
0x1400055fc  mov     r8, [r12+38h]; Source
0x140005601  test    r8, r8
0x140005604  jz      short loc_14000563A
0x140005606  cmp     [r8], r13b
0x140005609  jz      short loc_14000563A
0x14000560b  mov     rax, rbp
0x14000560e  inc     rax
0x140005611  cmp     [r8+rax], r13b
0x140005615  jnz     short loc_14000560E
0x140005617  lea     r14, [rax+1]
0x14000561b  cmp     rdx, r14
0x14000561e  jnb     short loc_140005626
0x140005620  mov     [rdi+10h], r13
0x140005624  jmp     short loc_140005643
0x140005626  mov     r9, r14; SourceSize
0x140005629  mov     rcx, rbx; Destination
0x14000562c  call    memcpy_s
0x140005631  mov     [rdi+10h], rbx
0x140005635  add     rbx, r14
0x140005638  jmp     short loc_14000563E
0x14000563a  mov     [rdi+10h], r13
0x14000563e  cmp     rbx, rsi
0x140005641  jz      short loc_14000568A
0x140005643  mov     r8, [r12+80h]; Source
0x14000564b  test    r8, r8
0x14000564e  jz      short loc_14000568A
0x140005650  cmp     [r8], r13b
0x140005653  jz      short loc_14000568A
0x140005655  mov     rax, rbp
0x140005658  inc     rax
0x14000565b  cmp     [r8+rax], r13b
0x14000565f  jnz     short loc_140005658
0x140005661  mov     rdx, rsi
0x140005664  lea     r14, [rax+1]
0x140005668  sub     rdx, rbx; DestinationSize
0x14000566b  cmp     rdx, r14
0x14000566e  jnb     short loc_140005676
0x140005670  mov     [rdi+20h], r13
0x140005674  jmp     short loc_140005693
0x140005676  mov     r9, r14; SourceSize
0x140005679  mov     rcx, rbx; Destination
0x14000567c  call    memcpy_s
0x140005681  mov     [rdi+20h], rbx
0x140005685  add     rbx, r14
0x140005688  jmp     short loc_14000568E
0x14000568a  mov     [rdi+20h], r13
0x14000568e  cmp     rbx, rsi
0x140005691  jz      short loc_1400056D4
0x140005693  mov     r8, [r12+18h]; Source
0x140005698  test    r8, r8
0x14000569b  jz      short loc_1400056D4
0x14000569d  cmp     [r8], r13w
0x1400056a1  jz      short loc_1400056D4
0x1400056a3  inc     rbp
0x1400056a6  cmp     [r8+rbp*2], r13w
0x1400056ab  jnz     short loc_1400056A3
0x1400056ad  mov     rdx, rsi
0x1400056b0  lea     r14, ds:2[rbp*2]
0x1400056b8  sub     rdx, rbx; DestinationSize
0x1400056bb  cmp     rdx, r14
0x1400056be  jb      short loc_1400056D4
0x1400056c0  mov     r9, r14; SourceSize
0x1400056c3  mov     rcx, rbx; Destination
0x1400056c6  call    memcpy_s
0x1400056cb  mov     [rdi+38h], rbx
0x1400056cf  add     rbx, r14
0x1400056d2  jmp     short loc_1400056D8
0x1400056d4  mov     [rdi+38h], r13
0x1400056d8  sub     rsi, rbx
0x1400056db  xor     edx, edx; Val
0x1400056dd  mov     r8, rsi; Size
0x1400056e0  mov     rcx, rbx; void *
0x1400056e3  call    memset_0
0x1400056e8  add     rsp, 28h
0x1400056ec  pop     r15
0x1400056ee  pop     r14
0x1400056f0  pop     r13
0x1400056f2  pop     r12
0x1400056f4  pop     rdi
0x1400056f5  pop     rsi
0x1400056f6  pop     rbp
0x1400056f7  pop     rbx
0x1400056f8  retn
```
