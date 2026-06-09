# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009810`
- end: `0x180009a29`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ef0`

## callees

- `0x1800046a0`
- `0x1800083fc`
- `0x180009810`
- `0x18000ab48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009906`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009906`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098f8`

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
0x180009810  push    rbx
0x180009812  push    rbp
0x180009813  push    rsi
0x180009814  push    rdi
0x180009815  push    r12
0x180009817  push    r13
0x180009819  push    r14
0x18000981b  push    r15
0x18000981d  sub     rsp, 28h
0x180009821  mov     [rcx+4], r8d
0x180009825  xor     r13d, r13d
0x180009828  mov     eax, [rdx+8]
0x18000982b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000982f  mov     [rcx+8], eax
0x180009832  mov     rdi, rcx
0x180009835  mov     [rcx+10h], r13
0x180009839  mov     r12, rdx
0x18000983c  movzx   eax, word ptr [rdx+40h]
0x180009840  mov     [rcx+18h], ax
0x180009844  mov     al, [rdx]
0x180009846  mov     [rcx+1Ah], al
0x180009849  mov     [rcx+20h], r13
0x18000984d  mov     rax, [rdx+88h]
0x180009854  mov     [rcx+28h], rax
0x180009858  mov     rax, [rdx+90h]
0x18000985f  mov     [rcx+30h], rax
0x180009863  mov     [rcx+38h], r13
0x180009867  mov     rcx, [rdx+38h]
0x18000986b  lea     edx, [rbp+2]
0x18000986e  test    rcx, rcx
0x180009871  jnz     short loc_180009878
0x180009873  mov     r8d, edx
0x180009876  jmp     short loc_180009888
0x180009878  mov     rax, rbp
0x18000987b  inc     rax
0x18000987e  cmp     [rcx+rax], r13b
0x180009882  jnz     short loc_18000987B
0x180009884  lea     r8, [rax+1]; unsigned __int64
0x180009888  mov     rcx, [r12+80h]
0x180009890  test    rcx, rcx
0x180009893  jz      short loc_1800098A5
0x180009895  mov     rax, rbp
0x180009898  inc     rax
0x18000989b  cmp     [rcx+rax], r13b
0x18000989f  jnz     short loc_180009898
0x1800098a1  lea     rdx, [rax+1]
0x1800098a5  mov     rcx, [r12+18h]
0x1800098aa  test    rcx, rcx
0x1800098ad  jnz     short loc_1800098B4
0x1800098af  lea     eax, [rcx+2]
0x1800098b2  jmp     short loc_1800098C9
0x1800098b4  mov     rax, rbp
0x1800098b7  inc     rax
0x1800098ba  cmp     [rcx+rax*2], r13w
0x1800098bf  jnz     short loc_1800098B7
0x1800098c1  lea     rax, ds:2[rax*2]
0x1800098c9  lea     r14, [rdx+rax]
0x1800098cd  add     r14, r8
0x1800098d0  lea     rsi, [rdi+48h]
0x1800098d4  cmp     [rdi+40h], r13
0x1800098d8  jz      short loc_1800098DF
0x1800098da  cmp     [rsi], r14
0x1800098dd  jnb     short loc_180009913
0x1800098df  mov     rdx, r14; dwBytes
0x1800098e2  mov     ecx, 8; dwFlags
0x1800098e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800098ec  mov     r15, rax
0x1800098ef  test    rax, rax
0x1800098f2  jz      short loc_180009913
0x1800098f4  mov     rbx, [rdi+40h]
0x1800098f8  call    cs:__imp_GetProcessHeap
0x1800098fe  mov     r8, rbx; lpMem
0x180009901  xor     edx, edx; dwFlags
0x180009903  mov     rcx, rax; hHeap
0x180009906  call    cs:__imp_HeapFree
0x18000990c  mov     [rdi+40h], r15
0x180009910  mov     [rsi], r14
0x180009913  mov     rbx, [rdi+40h]
0x180009917  test    rbx, rbx
0x18000991a  jz      loc_180009A18
0x180009920  mov     rdx, [rsi]; DestinationSize
0x180009923  lea     rsi, [rdx+rbx]
0x180009927  cmp     rbx, rsi
0x18000992a  jz      short loc_18000996A
0x18000992c  mov     r8, [r12+38h]; Source
0x180009931  test    r8, r8
0x180009934  jz      short loc_18000996A
0x180009936  cmp     [r8], r13b
0x180009939  jz      short loc_18000996A
0x18000993b  mov     rax, rbp
0x18000993e  inc     rax
0x180009941  cmp     [r8+rax], r13b
0x180009945  jnz     short loc_18000993E
0x180009947  lea     r14, [rax+1]
0x18000994b  cmp     rdx, r14
0x18000994e  jnb     short loc_180009956
0x180009950  mov     [rdi+10h], r13
0x180009954  jmp     short loc_180009973
0x180009956  mov     r9, r14; SourceSize
0x180009959  mov     rcx, rbx; Destination
0x18000995c  call    memcpy_s
0x180009961  mov     [rdi+10h], rbx
0x180009965  add     rbx, r14
0x180009968  jmp     short loc_18000996E
0x18000996a  mov     [rdi+10h], r13
0x18000996e  cmp     rbx, rsi
0x180009971  jz      short loc_1800099BA
0x180009973  mov     r8, [r12+80h]; Source
0x18000997b  test    r8, r8
0x18000997e  jz      short loc_1800099BA
0x180009980  cmp     [r8], r13b
0x180009983  jz      short loc_1800099BA
0x180009985  mov     rax, rbp
0x180009988  inc     rax
0x18000998b  cmp     [r8+rax], r13b
0x18000998f  jnz     short loc_180009988
0x180009991  mov     rdx, rsi
0x180009994  lea     r14, [rax+1]
0x180009998  sub     rdx, rbx; DestinationSize
0x18000999b  cmp     rdx, r14
0x18000999e  jnb     short loc_1800099A6
0x1800099a0  mov     [rdi+20h], r13
0x1800099a4  jmp     short loc_1800099C3
0x1800099a6  mov     r9, r14; SourceSize
0x1800099a9  mov     rcx, rbx; Destination
0x1800099ac  call    memcpy_s
0x1800099b1  mov     [rdi+20h], rbx
0x1800099b5  add     rbx, r14
0x1800099b8  jmp     short loc_1800099BE
0x1800099ba  mov     [rdi+20h], r13
0x1800099be  cmp     rbx, rsi
0x1800099c1  jz      short loc_180009A04
0x1800099c3  mov     r8, [r12+18h]; Source
0x1800099c8  test    r8, r8
0x1800099cb  jz      short loc_180009A04
0x1800099cd  cmp     [r8], r13w
0x1800099d1  jz      short loc_180009A04
0x1800099d3  inc     rbp
0x1800099d6  cmp     [r8+rbp*2], r13w
0x1800099db  jnz     short loc_1800099D3
0x1800099dd  mov     rdx, rsi
0x1800099e0  lea     r14, ds:2[rbp*2]
0x1800099e8  sub     rdx, rbx; DestinationSize
0x1800099eb  cmp     rdx, r14
0x1800099ee  jb      short loc_180009A04
0x1800099f0  mov     r9, r14; SourceSize
0x1800099f3  mov     rcx, rbx; Destination
0x1800099f6  call    memcpy_s
0x1800099fb  mov     [rdi+38h], rbx
0x1800099ff  add     rbx, r14
0x180009a02  jmp     short loc_180009A08
0x180009a04  mov     [rdi+38h], r13
0x180009a08  sub     rsi, rbx
0x180009a0b  xor     edx, edx; Val
0x180009a0d  mov     r8, rsi; Size
0x180009a10  mov     rcx, rbx; void *
0x180009a13  call    memset_0
0x180009a18  add     rsp, 28h
0x180009a1c  pop     r15
0x180009a1e  pop     r14
0x180009a20  pop     r13
0x180009a22  pop     r12
0x180009a24  pop     rdi
0x180009a25  pop     rsi
0x180009a26  pop     rbp
0x180009a27  pop     rbx
0x180009a28  retn
```
