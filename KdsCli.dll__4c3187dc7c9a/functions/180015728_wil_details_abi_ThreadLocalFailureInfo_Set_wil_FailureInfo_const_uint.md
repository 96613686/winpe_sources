# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180015728`
- end: `0x180015941`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800131c0`

## callees

- `0x180001f4c`
- `0x180001f7c`
- `0x18000c600`
- `0x180015728`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001581e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001581e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015810`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015810`

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
0x180015728  push    rbx
0x18001572a  push    rbp
0x18001572b  push    rsi
0x18001572c  push    rdi
0x18001572d  push    r12
0x18001572f  push    r13
0x180015731  push    r14
0x180015733  push    r15
0x180015735  sub     rsp, 28h
0x180015739  mov     [rcx+4], r8d
0x18001573d  xor     r13d, r13d
0x180015740  mov     eax, [rdx+8]
0x180015743  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180015747  mov     [rcx+8], eax
0x18001574a  mov     rdi, rcx
0x18001574d  mov     [rcx+10h], r13
0x180015751  mov     r12, rdx
0x180015754  movzx   eax, word ptr [rdx+40h]
0x180015758  mov     [rcx+18h], ax
0x18001575c  mov     al, [rdx]
0x18001575e  mov     [rcx+1Ah], al
0x180015761  mov     [rcx+20h], r13
0x180015765  mov     rax, [rdx+88h]
0x18001576c  mov     [rcx+28h], rax
0x180015770  mov     rax, [rdx+90h]
0x180015777  mov     [rcx+30h], rax
0x18001577b  mov     [rcx+38h], r13
0x18001577f  mov     rcx, [rdx+38h]
0x180015783  lea     edx, [rbp+2]
0x180015786  test    rcx, rcx
0x180015789  jnz     short loc_180015790
0x18001578b  mov     r8d, edx
0x18001578e  jmp     short loc_1800157A0
0x180015790  mov     rax, rbp
0x180015793  inc     rax
0x180015796  cmp     [rcx+rax], r13b
0x18001579a  jnz     short loc_180015793
0x18001579c  lea     r8, [rax+1]; unsigned __int64
0x1800157a0  mov     rcx, [r12+80h]
0x1800157a8  test    rcx, rcx
0x1800157ab  jz      short loc_1800157BD
0x1800157ad  mov     rax, rbp
0x1800157b0  inc     rax
0x1800157b3  cmp     [rcx+rax], r13b
0x1800157b7  jnz     short loc_1800157B0
0x1800157b9  lea     rdx, [rax+1]
0x1800157bd  mov     rcx, [r12+18h]
0x1800157c2  test    rcx, rcx
0x1800157c5  jnz     short loc_1800157CC
0x1800157c7  lea     eax, [rcx+2]
0x1800157ca  jmp     short loc_1800157E1
0x1800157cc  mov     rax, rbp
0x1800157cf  inc     rax
0x1800157d2  cmp     [rcx+rax*2], r13w
0x1800157d7  jnz     short loc_1800157CF
0x1800157d9  lea     rax, ds:2[rax*2]
0x1800157e1  lea     r14, [rdx+rax]
0x1800157e5  add     r14, r8
0x1800157e8  lea     rsi, [rdi+48h]
0x1800157ec  cmp     [rdi+40h], r13
0x1800157f0  jz      short loc_1800157F7
0x1800157f2  cmp     [rsi], r14
0x1800157f5  jnb     short loc_18001582B
0x1800157f7  mov     rdx, r14; dwBytes
0x1800157fa  mov     ecx, 8; dwFlags
0x1800157ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015804  mov     r15, rax
0x180015807  test    rax, rax
0x18001580a  jz      short loc_18001582B
0x18001580c  mov     rbx, [rdi+40h]
0x180015810  call    cs:__imp_GetProcessHeap
0x180015816  mov     r8, rbx; lpMem
0x180015819  xor     edx, edx; dwFlags
0x18001581b  mov     rcx, rax; hHeap
0x18001581e  call    cs:__imp_HeapFree
0x180015824  mov     [rdi+40h], r15
0x180015828  mov     [rsi], r14
0x18001582b  mov     rbx, [rdi+40h]
0x18001582f  test    rbx, rbx
0x180015832  jz      loc_180015930
0x180015838  mov     rdx, [rsi]; DestinationSize
0x18001583b  lea     rsi, [rdx+rbx]
0x18001583f  cmp     rbx, rsi
0x180015842  jz      short loc_180015882
0x180015844  mov     r8, [r12+38h]; Source
0x180015849  test    r8, r8
0x18001584c  jz      short loc_180015882
0x18001584e  cmp     [r8], r13b
0x180015851  jz      short loc_180015882
0x180015853  mov     rax, rbp
0x180015856  inc     rax
0x180015859  cmp     [r8+rax], r13b
0x18001585d  jnz     short loc_180015856
0x18001585f  lea     r14, [rax+1]
0x180015863  cmp     rdx, r14
0x180015866  jnb     short loc_18001586E
0x180015868  mov     [rdi+10h], r13
0x18001586c  jmp     short loc_18001588B
0x18001586e  mov     r9, r14; SourceSize
0x180015871  mov     rcx, rbx; Destination
0x180015874  call    memcpy_s
0x180015879  mov     [rdi+10h], rbx
0x18001587d  add     rbx, r14
0x180015880  jmp     short loc_180015886
0x180015882  mov     [rdi+10h], r13
0x180015886  cmp     rbx, rsi
0x180015889  jz      short loc_1800158D2
0x18001588b  mov     r8, [r12+80h]; Source
0x180015893  test    r8, r8
0x180015896  jz      short loc_1800158D2
0x180015898  cmp     [r8], r13b
0x18001589b  jz      short loc_1800158D2
0x18001589d  mov     rax, rbp
0x1800158a0  inc     rax
0x1800158a3  cmp     [r8+rax], r13b
0x1800158a7  jnz     short loc_1800158A0
0x1800158a9  mov     rdx, rsi
0x1800158ac  lea     r14, [rax+1]
0x1800158b0  sub     rdx, rbx; DestinationSize
0x1800158b3  cmp     rdx, r14
0x1800158b6  jnb     short loc_1800158BE
0x1800158b8  mov     [rdi+20h], r13
0x1800158bc  jmp     short loc_1800158DB
0x1800158be  mov     r9, r14; SourceSize
0x1800158c1  mov     rcx, rbx; Destination
0x1800158c4  call    memcpy_s
0x1800158c9  mov     [rdi+20h], rbx
0x1800158cd  add     rbx, r14
0x1800158d0  jmp     short loc_1800158D6
0x1800158d2  mov     [rdi+20h], r13
0x1800158d6  cmp     rbx, rsi
0x1800158d9  jz      short loc_18001591C
0x1800158db  mov     r8, [r12+18h]; Source
0x1800158e0  test    r8, r8
0x1800158e3  jz      short loc_18001591C
0x1800158e5  cmp     [r8], r13w
0x1800158e9  jz      short loc_18001591C
0x1800158eb  inc     rbp
0x1800158ee  cmp     [r8+rbp*2], r13w
0x1800158f3  jnz     short loc_1800158EB
0x1800158f5  mov     rdx, rsi
0x1800158f8  lea     r14, ds:2[rbp*2]
0x180015900  sub     rdx, rbx; DestinationSize
0x180015903  cmp     rdx, r14
0x180015906  jb      short loc_18001591C
0x180015908  mov     r9, r14; SourceSize
0x18001590b  mov     rcx, rbx; Destination
0x18001590e  call    memcpy_s
0x180015913  mov     [rdi+38h], rbx
0x180015917  add     rbx, r14
0x18001591a  jmp     short loc_180015920
0x18001591c  mov     [rdi+38h], r13
0x180015920  sub     rsi, rbx
0x180015923  xor     edx, edx; Val
0x180015925  mov     r8, rsi; Size
0x180015928  mov     rcx, rbx; void *
0x18001592b  call    memset_0
0x180015930  add     rsp, 28h
0x180015934  pop     r15
0x180015936  pop     r14
0x180015938  pop     r13
0x18001593a  pop     r12
0x18001593c  pop     rdi
0x18001593d  pop     rsi
0x18001593e  pop     rbp
0x18001593f  pop     rbx
0x180015940  retn
```
