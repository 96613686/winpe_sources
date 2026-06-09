# CAVIStream::CS::SetFormat(long,void *,long)

- ea: `0x18000bed0`
- end: `0x18000c25c`
- name: `?SetFormat@CS@CAVIStream@@UEAAJJPEAXJ@Z`
- size: `908`
- prototype: `__int64 __fastcall(CAVIStream::CS *this, int, int *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001460`
- `0x180001d0c`
- `0x18000bed0`
- `0x18000c410`
- `0x18001734d`
- `0x180017365`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000bfae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000bfae`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bfa5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000bfa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c226`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c226`
- `USER32!SetRect` at `0x18000c044`
- `USER32!SetRect` at `0x18000c044`
- `USER32!IsRectEmpty` at `0x18000c010`
- `USER32!IsRectEmpty` at `0x18000c010`

## pseudocode

```c
__int64 __fastcall CAVIStream::CS::SetFormat(CAVIStream::CS *this, int a2, int *a3, int a4)
{
  __int64 v4; // rsi
  SIZE_T v7; // r15
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rdx
  __int64 v11; // rbp
  HGLOBAL v12; // rax
  void *v13; // rax
  bool v14; // zf
  __int64 v15; // rax
  int v16; // r12d
  int v17; // r15d
  __int64 v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // eax
  int v22; // r12d
  unsigned __int16 v23; // cx
  __int64 v24; // rdx
  char *v25; // r15
  size_t v26; // rbp
  int v27; // edx
  unsigned int v28; // r8d
  int v29; // eax
  __int64 v30; // rcx
  char v31; // al
  unsigned int v32; // esi
  _BYTE v34[2]; // [rsp+50h] [rbp-458h] BYREF
  __int16 v35; // [rsp+52h] [rbp-456h]
  _BYTE v36[1036]; // [rsp+54h] [rbp-454h]

  v4 = *((_QWORD *)this + 1);
  v7 = a4;
  v8 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)(v4 + 272) + 1264LL);
  EnterCriticalSection(v8);
  memset_0(v34, 0, 0x404u);
  v9 = *(_QWORD *)(v4 + 272);
  if ( (*(_BYTE *)(v9 + 660) & 3) == 0 )
  {
    if ( v8 )
      LeaveCriticalSection(v8);
    return 2147762290LL;
  }
  v11 = *(_QWORD *)(v4 + 1336);
  if ( !v11 )
  {
    if ( *(int *)(v9 + 704) <= 0 || *(_DWORD *)(v4 + 1344) + 8 + *(_DWORD *)(v9 + 136) <= *(_DWORD *)(v9 + 672) )
    {
      *(_DWORD *)(v9 + 136) += v7 + 8;
      v12 = GlobalAlloc(0x2002u, v7);
      v13 = GlobalLock(v12);
      *(_QWORD *)(v4 + 1336) = v13;
      if ( !v13 )
      {
        if ( v8 )
          LeaveCriticalSection(v8);
        return 2147762279LL;
      }
      memmove_0(v13, a3, v7);
      v14 = *(_DWORD *)(v4 + 64) == 1935960438;
      *(_DWORD *)(v4 + 1344) = v7;
      if ( v14 )
      {
        v15 = *(_QWORD *)(v4 + 272);
        v16 = *(_DWORD *)(v15 + 116);
        v17 = *(_DWORD *)(v15 + 112);
        if ( IsRectEmpty((const RECT *)(v4 + 116))
          || *(_DWORD *)(v4 + 124) - *(_DWORD *)(v4 + 116) > v17
          || *(_DWORD *)(v4 + 128) - *(_DWORD *)(v4 + 120) > v16 )
        {
          SetRect((LPRECT)(v4 + 116), 0, 0, a3[1], a3[2]);
        }
        if ( a3[8] )
          memmove_0((void *)(v4 + 308), (char *)a3 + (unsigned int)*a3, 4LL * (unsigned int)a3[8]);
        v18 = *(_QWORD *)(v4 + 272);
        v19 = *(_DWORD *)(v18 + 112);
        if ( v19 <= *(_DWORD *)(v4 + 124) )
          v19 = *(_DWORD *)(v4 + 124);
        *(_DWORD *)(v18 + 112) = v19;
        v20 = *(_QWORD *)(v4 + 272);
        v21 = *(_DWORD *)(v20 + 116);
        if ( v21 <= *(_DWORD *)(v4 + 128) )
          v21 = *(_DWORD *)(v4 + 128);
        *(_DWORD *)(v20 + 116) = v21;
      }
      goto LABEL_36;
    }
    goto LABEL_47;
  }
  v22 = *(_DWORD *)(v4 + 1344);
  if ( (_DWORD)v7 == v22 && !memcmp_0(*(const void **)(v4 + 1336), a3, v7) )
    goto LABEL_36;
  if ( *(_DWORD *)(v4 + 64) != 1935960438
    || a2 < *(_DWORD *)(v4 + 92) + *(_DWORD *)(v4 + 96)
    || (v23 = *((_WORD *)a3 + 7), v23 > 8u)
    || !a3[8]
    || (_DWORD)v7 != v22
    || a3[4] != *(_DWORD *)(v11 + 16)
    || (v24 = (unsigned int)*a3, *(_QWORD *)a3 != *(_QWORD *)v11)
    || a3[2] != *(_DWORD *)(v11 + 8)
    || v23 != *(_WORD *)(v11 + 14) )
  {
LABEL_47:
    if ( v8 )
      LeaveCriticalSection(v8);
    return 2147762277LL;
  }
  v25 = (char *)a3 + v24;
  v26 = 4LL * (unsigned int)a3[8];
  if ( !memcmp_0((const void *)(v4 + 308), (char *)a3 + v24, v26) )
  {
LABEL_36:
    if ( v8 )
      LeaveCriticalSection(v8);
    return 0;
  }
  memmove_0((void *)(v4 + 308), v25, v26);
  *(_DWORD *)(v4 + 72) |= 0x10000u;
  v27 = 0;
  *(_DWORD *)(v4 + 304) = a2;
  v28 = a3[8];
  v34[1] = *((_BYTE *)a3 + 32);
  v34[0] = 0;
  v35 = 0;
  while ( 1 )
  {
    v29 = 256;
    if ( v28 < 0x100 )
      v29 = v28;
    if ( v27 >= v29 )
      break;
    v30 = v27++;
    v36[4 * v30] = v25[2];
    v36[4 * v30 + 1] = v25[1];
    v31 = *v25;
    v25 += 4;
    v36[4 * v30 + 2] = v31;
  }
  v32 = CAVIStream::CS::Write(this, a2, 0, v34, 4 * v28 + 4, 0x100u, 0, 0);
  if ( v8 )
    LeaveCriticalSection(v8);
  return v32;
}

```

## disassembly

```asm
0x18000bed0  mov     [rsp+arg_8], rbx
0x18000bed5  push    rbp
0x18000bed6  push    rsi
0x18000bed7  push    rdi
0x18000bed8  push    r12
0x18000beda  push    r13
0x18000bedc  push    r14
0x18000bede  push    r15
0x18000bee0  sub     rsp, 470h
0x18000bee7  mov     rax, cs:__security_cookie
0x18000beee  xor     rax, rsp
0x18000bef1  mov     [rsp+4A8h+var_48], rax
0x18000bef9  mov     rsi, [rcx+8]
0x18000befd  mov     r14, r8
0x18000bf00  mov     [rsp+4A8h+var_468], rcx
0x18000bf05  mov     r13d, edx
0x18000bf08  movsxd  r15, r9d
0x18000bf0b  mov     rbx, [rsi+110h]
0x18000bf12  add     rbx, 4F0h
0x18000bf19  mov     rcx, rbx; lpCriticalSection
0x18000bf1c  call    cs:__imp_EnterCriticalSection
0x18000bf22  xor     edx, edx; Val
0x18000bf24  lea     rcx, [rsp+4A8h+var_458]; void *
0x18000bf29  mov     r8d, 404h; Size
0x18000bf2f  call    memset_0
0x18000bf34  mov     rdx, [rsi+110h]
0x18000bf3b  test    byte ptr [rdx+294h], 3
0x18000bf42  jnz     short loc_18000BF5C
0x18000bf44  test    rbx, rbx
0x18000bf47  jz      short loc_18000BF52
0x18000bf49  mov     rcx, rbx; lpCriticalSection
0x18000bf4c  call    cs:__imp_LeaveCriticalSection
0x18000bf52  mov     eax, 80044072h
0x18000bf57  jmp     loc_18000C231
0x18000bf5c  mov     rbp, [rsi+538h]
0x18000bf63  xor     edi, edi
0x18000bf65  test    rbp, rbp
0x18000bf68  jnz     loc_18000C09B
0x18000bf6e  cmp     [rdx+2C0h], edi
0x18000bf74  jle     short loc_18000BF93
0x18000bf76  mov     eax, [rsi+540h]
0x18000bf7c  mov     ecx, [rdx+88h]
0x18000bf82  add     eax, 8
0x18000bf85  add     ecx, eax
0x18000bf87  cmp     ecx, [rdx+2A0h]
0x18000bf8d  jg      loc_18000C21E
0x18000bf93  lea     eax, [r15+8]
0x18000bf97  mov     ecx, 2002h; uFlags
0x18000bf9c  add     [rdx+88h], eax
0x18000bfa2  mov     rdx, r15; dwBytes
0x18000bfa5  call    cs:__imp_GlobalAlloc
0x18000bfab  mov     rcx, rax; hMem
0x18000bfae  call    cs:__imp_GlobalLock
0x18000bfb4  mov     [rsi+538h], rax
0x18000bfbb  test    rax, rax
0x18000bfbe  jnz     short loc_18000BFD8
0x18000bfc0  test    rbx, rbx
0x18000bfc3  jz      short loc_18000BFCE
0x18000bfc5  mov     rcx, rbx; lpCriticalSection
0x18000bfc8  call    cs:__imp_LeaveCriticalSection
0x18000bfce  mov     eax, 80044067h
0x18000bfd3  jmp     loc_18000C231
0x18000bfd8  mov     r8, r15; Size
0x18000bfdb  mov     rdx, r14; Src
0x18000bfde  mov     rcx, rax; void *
0x18000bfe1  call    memmove_0
0x18000bfe6  cmp     dword ptr [rsi+40h], 73646976h
0x18000bfed  mov     [rsi+540h], r15d
0x18000bff4  jnz     loc_18000C15D
0x18000bffa  mov     rax, [rsi+110h]
0x18000c001  lea     rbp, [rsi+74h]
0x18000c005  mov     rcx, rbp; lprc
0x18000c008  mov     r12d, [rax+74h]
0x18000c00c  mov     r15d, [rax+70h]
0x18000c010  call    cs:__imp_IsRectEmpty
0x18000c016  test    eax, eax
0x18000c018  jnz     short loc_18000C030
0x18000c01a  mov     eax, [rbp+8]
0x18000c01d  sub     eax, [rbp+0]
0x18000c020  cmp     eax, r15d
0x18000c023  jg      short loc_18000C030
0x18000c025  mov     eax, [rbp+0Ch]
0x18000c028  sub     eax, [rbp+4]
0x18000c02b  cmp     eax, r12d
0x18000c02e  jle     short loc_18000C04A
0x18000c030  mov     eax, [r14+8]
0x18000c034  xor     r8d, r8d; yTop
0x18000c037  mov     r9d, [r14+4]; xRight
0x18000c03b  xor     edx, edx; xLeft
0x18000c03d  mov     rcx, rbp; lprc
0x18000c040  mov     [rsp+4A8h+yBottom], eax; yBottom
0x18000c044  call    cs:__imp_SetRect
0x18000c04a  cmp     [r14+20h], edi
0x18000c04e  jbe     short loc_18000C06A
0x18000c050  mov     r8d, [r14+20h]
0x18000c054  lea     rcx, [rsi+134h]; void *
0x18000c05b  mov     edx, [r14]
0x18000c05e  shl     r8, 2; Size
0x18000c062  add     rdx, r14; Src
0x18000c065  call    memmove_0
0x18000c06a  mov     rcx, [rsi+110h]
0x18000c071  mov     eax, [rcx+70h]
0x18000c074  cmp     eax, [rsi+7Ch]
0x18000c077  cmovbe  eax, [rsi+7Ch]
0x18000c07b  mov     [rcx+70h], eax
0x18000c07e  mov     edx, [rsi+80h]
0x18000c084  mov     rcx, [rsi+110h]
0x18000c08b  mov     eax, [rcx+74h]
0x18000c08e  cmp     eax, edx
0x18000c090  cmovbe  eax, edx
0x18000c093  mov     [rcx+74h], eax
0x18000c096  jmp     loc_18000C15D
0x18000c09b  mov     r12d, [rsi+540h]
0x18000c0a2  cmp     r15d, r12d
0x18000c0a5  jnz     short loc_18000C0BD
0x18000c0a7  mov     r8, r15; Size
0x18000c0aa  mov     rdx, r14; Buf2
0x18000c0ad  mov     rcx, rbp; Buf1
0x18000c0b0  call    memcmp_0
0x18000c0b5  test    eax, eax
0x18000c0b7  jz      loc_18000C15D
0x18000c0bd  cmp     dword ptr [rsi+40h], 73646976h
0x18000c0c4  jnz     loc_18000C21E
0x18000c0ca  mov     eax, [rsi+60h]
0x18000c0cd  add     eax, [rsi+5Ch]
0x18000c0d0  cmp     r13d, eax
0x18000c0d3  jl      loc_18000C21E
0x18000c0d9  movzx   ecx, word ptr [r14+0Eh]
0x18000c0de  cmp     cx, 8
0x18000c0e2  ja      loc_18000C21E
0x18000c0e8  cmp     [r14+20h], edi
0x18000c0ec  jz      loc_18000C21E
0x18000c0f2  cmp     r15d, r12d
0x18000c0f5  jnz     loc_18000C21E
0x18000c0fb  mov     eax, [rbp+10h]
0x18000c0fe  cmp     [r14+10h], eax
0x18000c102  jnz     loc_18000C21E
0x18000c108  mov     edx, [r14]
0x18000c10b  cmp     edx, [rbp+0]
0x18000c10e  jnz     loc_18000C21E
0x18000c114  mov     eax, [rbp+4]
0x18000c117  cmp     [r14+4], eax
0x18000c11b  jnz     loc_18000C21E
0x18000c121  mov     eax, [rbp+8]
0x18000c124  cmp     [r14+8], eax
0x18000c128  jnz     loc_18000C21E
0x18000c12e  cmp     cx, [rbp+0Eh]
0x18000c132  jnz     loc_18000C21E
0x18000c138  mov     ebp, [r14+20h]
0x18000c13c  lea     r15, [r14+rdx]
0x18000c140  shl     rbp, 2
0x18000c144  lea     r12, [rsi+134h]
0x18000c14b  mov     r8, rbp; Size
0x18000c14e  mov     rdx, r15; Buf2
0x18000c151  mov     rcx, r12; Buf1
0x18000c154  call    memcmp_0
0x18000c159  test    eax, eax
0x18000c15b  jnz     short loc_18000C172
0x18000c15d  test    rbx, rbx
0x18000c160  jz      short loc_18000C16B
0x18000c162  mov     rcx, rbx; lpCriticalSection
0x18000c165  call    cs:__imp_LeaveCriticalSection
0x18000c16b  xor     eax, eax
0x18000c16d  jmp     loc_18000C231
0x18000c172  mov     r8, rbp; Size
0x18000c175  mov     rdx, r15; Src
0x18000c178  mov     rcx, r12; void *
0x18000c17b  call    memmove_0
0x18000c180  bts     dword ptr [rsi+48h], 10h
0x18000c185  mov     edx, edi
0x18000c187  mov     [rsi+130h], r13d
0x18000c18e  mov     r9d, 100h
0x18000c194  mov     al, [r14+20h]
0x18000c198  mov     r8d, [r14+20h]
0x18000c19c  mov     [rsp+4A8h+var_457], al
0x18000c1a0  mov     [rsp+4A8h+var_458], dil
0x18000c1a5  mov     [rsp+4A8h+var_456], di
0x18000c1aa  cmp     r8d, r9d
0x18000c1ad  mov     eax, r9d
0x18000c1b0  cmovb   eax, r8d
0x18000c1b4  cmp     edx, eax
0x18000c1b6  jge     short loc_18000C1DA
0x18000c1b8  mov     al, [r15+2]
0x18000c1bc  movsxd  rcx, edx
0x18000c1bf  inc     edx
0x18000c1c1  mov     [rsp+rcx*4+4A8h+var_454], al
0x18000c1c5  mov     al, [r15+1]
0x18000c1c9  mov     [rsp+rcx*4+4A8h+var_453], al
0x18000c1cd  mov     al, [r15]
0x18000c1d0  add     r15, 4
0x18000c1d4  mov     [rsp+rcx*4+4A8h+var_452], al
0x18000c1d8  jmp     short loc_18000C1AA
0x18000c1da  mov     rcx, [rsp+4A8h+var_468]; this
0x18000c1df  lea     eax, ds:4[r8*4]
0x18000c1e7  mov     [rsp+4A8h+var_470], rdi; int *
0x18000c1ec  xor     r8d, r8d; int
0x18000c1ef  mov     [rsp+4A8h+var_478], rdi; int *
0x18000c1f4  mov     edx, r13d; int
0x18000c1f7  mov     [rsp+4A8h+var_480], r9d; unsigned int
0x18000c1fc  lea     r9, [rsp+4A8h+var_458]; void *
0x18000c201  mov     [rsp+4A8h+yBottom], eax; unsigned int
0x18000c205  call    ?Write@CS@CAVIStream@@UEAAJJJPEAXJKPEAJ1@Z; CAVIStream::CS::Write(long,long,void *,long,ulong,long *,long *)
0x18000c20a  mov     esi, eax
0x18000c20c  test    rbx, rbx
0x18000c20f  jz      short loc_18000C21A
0x18000c211  mov     rcx, rbx; lpCriticalSection
0x18000c214  call    cs:__imp_LeaveCriticalSection
0x18000c21a  mov     eax, esi
0x18000c21c  jmp     short loc_18000C231
0x18000c21e  test    rbx, rbx
0x18000c221  jz      short loc_18000C22C
0x18000c223  mov     rcx, rbx; lpCriticalSection
0x18000c226  call    cs:__imp_LeaveCriticalSection
0x18000c22c  mov     eax, 80044065h
0x18000c231  mov     rcx, [rsp+4A8h+var_48]
0x18000c239  xor     rcx, rsp; StackCookie
0x18000c23c  call    __security_check_cookie
0x18000c241  mov     rbx, [rsp+4A8h+arg_8]
0x18000c249  add     rsp, 470h
0x18000c250  pop     r15
0x18000c252  pop     r14
0x18000c254  pop     r13
0x18000c256  pop     r12
0x18000c258  pop     rdi
0x18000c259  pop     rsi
0x18000c25a  pop     rbp
0x18000c25b  retn
```
