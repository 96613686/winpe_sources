# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005614`
- end: `0x18000582d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800041f0`

## callees

- `0x180002ac8`
- `0x180005248`
- `0x180005614`
- `0x1800065b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000570a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000570a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056fc`

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
0x180005614  push    rbx
0x180005616  push    rbp
0x180005617  push    rsi
0x180005618  push    rdi
0x180005619  push    r12
0x18000561b  push    r13
0x18000561d  push    r14
0x18000561f  push    r15
0x180005621  sub     rsp, 28h
0x180005625  mov     [rcx+4], r8d
0x180005629  xor     r13d, r13d
0x18000562c  mov     eax, [rdx+8]
0x18000562f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005633  mov     [rcx+8], eax
0x180005636  mov     rdi, rcx
0x180005639  mov     [rcx+10h], r13
0x18000563d  mov     r12, rdx
0x180005640  movzx   eax, word ptr [rdx+40h]
0x180005644  mov     [rcx+18h], ax
0x180005648  mov     al, [rdx]
0x18000564a  mov     [rcx+1Ah], al
0x18000564d  mov     [rcx+20h], r13
0x180005651  mov     rax, [rdx+88h]
0x180005658  mov     [rcx+28h], rax
0x18000565c  mov     rax, [rdx+90h]
0x180005663  mov     [rcx+30h], rax
0x180005667  mov     [rcx+38h], r13
0x18000566b  mov     rcx, [rdx+38h]
0x18000566f  lea     edx, [rbp+2]
0x180005672  test    rcx, rcx
0x180005675  jnz     short loc_18000567C
0x180005677  mov     r8d, edx
0x18000567a  jmp     short loc_18000568C
0x18000567c  mov     rax, rbp
0x18000567f  inc     rax
0x180005682  cmp     [rcx+rax], r13b
0x180005686  jnz     short loc_18000567F
0x180005688  lea     r8, [rax+1]; unsigned __int64
0x18000568c  mov     rcx, [r12+80h]
0x180005694  test    rcx, rcx
0x180005697  jz      short loc_1800056A9
0x180005699  mov     rax, rbp
0x18000569c  inc     rax
0x18000569f  cmp     [rcx+rax], r13b
0x1800056a3  jnz     short loc_18000569C
0x1800056a5  lea     rdx, [rax+1]
0x1800056a9  mov     rcx, [r12+18h]
0x1800056ae  test    rcx, rcx
0x1800056b1  jnz     short loc_1800056B8
0x1800056b3  lea     eax, [rcx+2]
0x1800056b6  jmp     short loc_1800056CD
0x1800056b8  mov     rax, rbp
0x1800056bb  inc     rax
0x1800056be  cmp     [rcx+rax*2], r13w
0x1800056c3  jnz     short loc_1800056BB
0x1800056c5  lea     rax, ds:2[rax*2]
0x1800056cd  lea     r14, [rdx+rax]
0x1800056d1  add     r14, r8
0x1800056d4  lea     rsi, [rdi+48h]
0x1800056d8  cmp     [rdi+40h], r13
0x1800056dc  jz      short loc_1800056E3
0x1800056de  cmp     [rsi], r14
0x1800056e1  jnb     short loc_180005717
0x1800056e3  mov     rdx, r14; dwBytes
0x1800056e6  mov     ecx, 8; dwFlags
0x1800056eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800056f0  mov     r15, rax
0x1800056f3  test    rax, rax
0x1800056f6  jz      short loc_180005717
0x1800056f8  mov     rbx, [rdi+40h]
0x1800056fc  call    cs:__imp_GetProcessHeap
0x180005702  mov     r8, rbx; lpMem
0x180005705  xor     edx, edx; dwFlags
0x180005707  mov     rcx, rax; hHeap
0x18000570a  call    cs:__imp_HeapFree
0x180005710  mov     [rdi+40h], r15
0x180005714  mov     [rsi], r14
0x180005717  mov     rbx, [rdi+40h]
0x18000571b  test    rbx, rbx
0x18000571e  jz      loc_18000581C
0x180005724  mov     rdx, [rsi]; DestinationSize
0x180005727  lea     rsi, [rdx+rbx]
0x18000572b  cmp     rbx, rsi
0x18000572e  jz      short loc_18000576E
0x180005730  mov     r8, [r12+38h]; Source
0x180005735  test    r8, r8
0x180005738  jz      short loc_18000576E
0x18000573a  cmp     [r8], r13b
0x18000573d  jz      short loc_18000576E
0x18000573f  mov     rax, rbp
0x180005742  inc     rax
0x180005745  cmp     [r8+rax], r13b
0x180005749  jnz     short loc_180005742
0x18000574b  lea     r14, [rax+1]
0x18000574f  cmp     rdx, r14
0x180005752  jnb     short loc_18000575A
0x180005754  mov     [rdi+10h], r13
0x180005758  jmp     short loc_180005777
0x18000575a  mov     r9, r14; SourceSize
0x18000575d  mov     rcx, rbx; Destination
0x180005760  call    memcpy_s
0x180005765  mov     [rdi+10h], rbx
0x180005769  add     rbx, r14
0x18000576c  jmp     short loc_180005772
0x18000576e  mov     [rdi+10h], r13
0x180005772  cmp     rbx, rsi
0x180005775  jz      short loc_1800057BE
0x180005777  mov     r8, [r12+80h]; Source
0x18000577f  test    r8, r8
0x180005782  jz      short loc_1800057BE
0x180005784  cmp     [r8], r13b
0x180005787  jz      short loc_1800057BE
0x180005789  mov     rax, rbp
0x18000578c  inc     rax
0x18000578f  cmp     [r8+rax], r13b
0x180005793  jnz     short loc_18000578C
0x180005795  mov     rdx, rsi
0x180005798  lea     r14, [rax+1]
0x18000579c  sub     rdx, rbx; DestinationSize
0x18000579f  cmp     rdx, r14
0x1800057a2  jnb     short loc_1800057AA
0x1800057a4  mov     [rdi+20h], r13
0x1800057a8  jmp     short loc_1800057C7
0x1800057aa  mov     r9, r14; SourceSize
0x1800057ad  mov     rcx, rbx; Destination
0x1800057b0  call    memcpy_s
0x1800057b5  mov     [rdi+20h], rbx
0x1800057b9  add     rbx, r14
0x1800057bc  jmp     short loc_1800057C2
0x1800057be  mov     [rdi+20h], r13
0x1800057c2  cmp     rbx, rsi
0x1800057c5  jz      short loc_180005808
0x1800057c7  mov     r8, [r12+18h]; Source
0x1800057cc  test    r8, r8
0x1800057cf  jz      short loc_180005808
0x1800057d1  cmp     [r8], r13w
0x1800057d5  jz      short loc_180005808
0x1800057d7  inc     rbp
0x1800057da  cmp     [r8+rbp*2], r13w
0x1800057df  jnz     short loc_1800057D7
0x1800057e1  mov     rdx, rsi
0x1800057e4  lea     r14, ds:2[rbp*2]
0x1800057ec  sub     rdx, rbx; DestinationSize
0x1800057ef  cmp     rdx, r14
0x1800057f2  jb      short loc_180005808
0x1800057f4  mov     r9, r14; SourceSize
0x1800057f7  mov     rcx, rbx; Destination
0x1800057fa  call    memcpy_s
0x1800057ff  mov     [rdi+38h], rbx
0x180005803  add     rbx, r14
0x180005806  jmp     short loc_18000580C
0x180005808  mov     [rdi+38h], r13
0x18000580c  sub     rsi, rbx
0x18000580f  xor     edx, edx; Val
0x180005811  mov     r8, rsi; Size
0x180005814  mov     rcx, rbx; void *
0x180005817  call    memset_0
0x18000581c  add     rsp, 28h
0x180005820  pop     r15
0x180005822  pop     r14
0x180005824  pop     r13
0x180005826  pop     r12
0x180005828  pop     rdi
0x180005829  pop     rsi
0x18000582a  pop     rbp
0x18000582b  pop     rbx
0x18000582c  retn
```
