# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140009478`
- end: `0x140009694`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400059f0`

## callees

- `0x1400075c8`
- `0x140009478`
- `0x140015ac2`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000956e`
- `KERNEL32!HeapFree` at `0x14000956e`
- `KERNEL32!GetProcessHeap` at `0x140009560`
- `KERNEL32!GetProcessHeap` at `0x140009560`
- `msvcrt!memcpy_s` at `0x1400095c4`
- `msvcrt!memcpy_s` at `0x140009615`
- `msvcrt!memcpy_s` at `0x140009660`
- `msvcrt!memcpy_s` at `0x1400095c4`
- `msvcrt!memcpy_s` at `0x140009615`
- `msvcrt!memcpy_s` at `0x140009660`

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
0x140009478  push    rbx
0x14000947a  push    rbp
0x14000947b  push    rsi
0x14000947c  push    rdi
0x14000947d  push    r12
0x14000947f  push    r13
0x140009481  push    r14
0x140009483  push    r15
0x140009485  sub     rsp, 28h
0x140009489  mov     [rcx+4], r8d
0x14000948d  xor     r13d, r13d
0x140009490  mov     eax, [rdx+8]
0x140009493  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140009497  mov     [rcx+8], eax
0x14000949a  mov     rdi, rcx
0x14000949d  mov     [rcx+10h], r13
0x1400094a1  mov     r12, rdx
0x1400094a4  movzx   eax, word ptr [rdx+40h]
0x1400094a8  mov     [rcx+18h], ax
0x1400094ac  mov     al, [rdx]
0x1400094ae  mov     [rcx+1Ah], al
0x1400094b1  mov     [rcx+20h], r13
0x1400094b5  mov     rax, [rdx+88h]
0x1400094bc  mov     [rcx+28h], rax
0x1400094c0  mov     rax, [rdx+90h]
0x1400094c7  mov     [rcx+30h], rax
0x1400094cb  mov     [rcx+38h], r13
0x1400094cf  mov     rcx, [rdx+38h]
0x1400094d3  lea     edx, [rbp+2]
0x1400094d6  test    rcx, rcx
0x1400094d9  jnz     short loc_1400094E0
0x1400094db  mov     r8d, edx
0x1400094de  jmp     short loc_1400094F0
0x1400094e0  mov     rax, rbp
0x1400094e3  inc     rax
0x1400094e6  cmp     [rcx+rax], r13b
0x1400094ea  jnz     short loc_1400094E3
0x1400094ec  lea     r8, [rax+1]; unsigned __int64
0x1400094f0  mov     rcx, [r12+80h]
0x1400094f8  test    rcx, rcx
0x1400094fb  jz      short loc_14000950D
0x1400094fd  mov     rax, rbp
0x140009500  inc     rax
0x140009503  cmp     [rcx+rax], r13b
0x140009507  jnz     short loc_140009500
0x140009509  lea     rdx, [rax+1]
0x14000950d  mov     rcx, [r12+18h]
0x140009512  test    rcx, rcx
0x140009515  jnz     short loc_14000951C
0x140009517  lea     eax, [rcx+2]
0x14000951a  jmp     short loc_140009531
0x14000951c  mov     rax, rbp
0x14000951f  inc     rax
0x140009522  cmp     [rcx+rax*2], r13w
0x140009527  jnz     short loc_14000951F
0x140009529  lea     rax, ds:2[rax*2]
0x140009531  lea     r14, [rdx+rax]
0x140009535  add     r14, r8
0x140009538  lea     rsi, [rdi+48h]
0x14000953c  cmp     [rdi+40h], r13
0x140009540  jz      short loc_140009547
0x140009542  cmp     [rsi], r14
0x140009545  jnb     short loc_14000957B
0x140009547  mov     rdx, r14; dwBytes
0x14000954a  mov     ecx, 8; dwFlags
0x14000954f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009554  mov     r15, rax
0x140009557  test    rax, rax
0x14000955a  jz      short loc_14000957B
0x14000955c  mov     rbx, [rdi+40h]
0x140009560  call    cs:__imp_GetProcessHeap
0x140009566  mov     r8, rbx; lpMem
0x140009569  xor     edx, edx; dwFlags
0x14000956b  mov     rcx, rax; hHeap
0x14000956e  call    cs:__imp_HeapFree
0x140009574  mov     [rdi+40h], r15
0x140009578  mov     [rsi], r14
0x14000957b  mov     rbx, [rdi+40h]
0x14000957f  test    rbx, rbx
0x140009582  jz      loc_140009683
0x140009588  mov     rdx, [rsi]; DestinationSize
0x14000958b  lea     rsi, [rdx+rbx]
0x14000958f  cmp     rbx, rsi
0x140009592  jz      short loc_1400095D3
0x140009594  mov     r8, [r12+38h]; Source
0x140009599  test    r8, r8
0x14000959c  jz      short loc_1400095D3
0x14000959e  cmp     [r8], r13b
0x1400095a1  jz      short loc_1400095D3
0x1400095a3  mov     rax, rbp
0x1400095a6  inc     rax
0x1400095a9  cmp     [r8+rax], r13b
0x1400095ad  jnz     short loc_1400095A6
0x1400095af  lea     r14, [rax+1]
0x1400095b3  cmp     rdx, r14
0x1400095b6  jnb     short loc_1400095BE
0x1400095b8  mov     [rdi+10h], r13
0x1400095bc  jmp     short loc_1400095DC
0x1400095be  mov     r9, r14; SourceSize
0x1400095c1  mov     rcx, rbx; Destination
0x1400095c4  call    cs:__imp_memcpy_s
0x1400095ca  mov     [rdi+10h], rbx
0x1400095ce  add     rbx, r14
0x1400095d1  jmp     short loc_1400095D7
0x1400095d3  mov     [rdi+10h], r13
0x1400095d7  cmp     rbx, rsi
0x1400095da  jz      short loc_140009624
0x1400095dc  mov     r8, [r12+80h]; Source
0x1400095e4  test    r8, r8
0x1400095e7  jz      short loc_140009624
0x1400095e9  cmp     [r8], r13b
0x1400095ec  jz      short loc_140009624
0x1400095ee  mov     rax, rbp
0x1400095f1  inc     rax
0x1400095f4  cmp     [r8+rax], r13b
0x1400095f8  jnz     short loc_1400095F1
0x1400095fa  mov     rdx, rsi
0x1400095fd  lea     r14, [rax+1]
0x140009601  sub     rdx, rbx; DestinationSize
0x140009604  cmp     rdx, r14
0x140009607  jnb     short loc_14000960F
0x140009609  mov     [rdi+20h], r13
0x14000960d  jmp     short loc_14000962D
0x14000960f  mov     r9, r14; SourceSize
0x140009612  mov     rcx, rbx; Destination
0x140009615  call    cs:__imp_memcpy_s
0x14000961b  mov     [rdi+20h], rbx
0x14000961f  add     rbx, r14
0x140009622  jmp     short loc_140009628
0x140009624  mov     [rdi+20h], r13
0x140009628  cmp     rbx, rsi
0x14000962b  jz      short loc_14000966F
0x14000962d  mov     r8, [r12+18h]; Source
0x140009632  test    r8, r8
0x140009635  jz      short loc_14000966F
0x140009637  cmp     [r8], r13w
0x14000963b  jz      short loc_14000966F
0x14000963d  inc     rbp
0x140009640  cmp     [r8+rbp*2], r13w
0x140009645  jnz     short loc_14000963D
0x140009647  mov     rdx, rsi
0x14000964a  lea     r14, ds:2[rbp*2]
0x140009652  sub     rdx, rbx; DestinationSize
0x140009655  cmp     rdx, r14
0x140009658  jb      short loc_14000966F
0x14000965a  mov     r9, r14; SourceSize
0x14000965d  mov     rcx, rbx; Destination
0x140009660  call    cs:__imp_memcpy_s
0x140009666  mov     [rdi+38h], rbx
0x14000966a  add     rbx, r14
0x14000966d  jmp     short loc_140009673
0x14000966f  mov     [rdi+38h], r13
0x140009673  sub     rsi, rbx
0x140009676  xor     edx, edx; Val
0x140009678  mov     r8, rsi; Size
0x14000967b  mov     rcx, rbx; void *
0x14000967e  call    memset_0
0x140009683  add     rsp, 28h
0x140009687  pop     r15
0x140009689  pop     r14
0x14000968b  pop     r13
0x14000968d  pop     r12
0x14000968f  pop     rdi
0x140009690  pop     rsi
0x140009691  pop     rbp
0x140009692  pop     rbx
0x140009693  retn
```
