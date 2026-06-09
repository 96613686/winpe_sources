# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000ef78`
- end: `0x18000f191`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a500`

## callees

- `0x18000279c`
- `0x1800027c0`
- `0x18000d114`
- `0x18000ef78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f060`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f060`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f06e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f06e`

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
0x18000ef78  push    rbx
0x18000ef7a  push    rbp
0x18000ef7b  push    rsi
0x18000ef7c  push    rdi
0x18000ef7d  push    r12
0x18000ef7f  push    r13
0x18000ef81  push    r14
0x18000ef83  push    r15
0x18000ef85  sub     rsp, 28h
0x18000ef89  mov     [rcx+4], r8d
0x18000ef8d  xor     r13d, r13d
0x18000ef90  mov     eax, [rdx+8]
0x18000ef93  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000ef97  mov     [rcx+8], eax
0x18000ef9a  mov     rdi, rcx
0x18000ef9d  mov     [rcx+10h], r13
0x18000efa1  mov     r12, rdx
0x18000efa4  movzx   eax, word ptr [rdx+40h]
0x18000efa8  mov     [rcx+18h], ax
0x18000efac  mov     al, [rdx]
0x18000efae  mov     [rcx+1Ah], al
0x18000efb1  mov     [rcx+20h], r13
0x18000efb5  mov     rax, [rdx+88h]
0x18000efbc  mov     [rcx+28h], rax
0x18000efc0  mov     rax, [rdx+90h]
0x18000efc7  mov     [rcx+30h], rax
0x18000efcb  mov     [rcx+38h], r13
0x18000efcf  mov     rcx, [rdx+38h]
0x18000efd3  lea     edx, [rbp+2]
0x18000efd6  test    rcx, rcx
0x18000efd9  jnz     short loc_18000EFE0
0x18000efdb  mov     r8d, edx
0x18000efde  jmp     short loc_18000EFF0
0x18000efe0  mov     rax, rbp
0x18000efe3  inc     rax
0x18000efe6  cmp     [rcx+rax], r13b
0x18000efea  jnz     short loc_18000EFE3
0x18000efec  lea     r8, [rax+1]; unsigned __int64
0x18000eff0  mov     rcx, [r12+80h]
0x18000eff8  test    rcx, rcx
0x18000effb  jz      short loc_18000F00D
0x18000effd  mov     rax, rbp
0x18000f000  inc     rax
0x18000f003  cmp     [rcx+rax], r13b
0x18000f007  jnz     short loc_18000F000
0x18000f009  lea     rdx, [rax+1]
0x18000f00d  mov     rcx, [r12+18h]
0x18000f012  test    rcx, rcx
0x18000f015  jnz     short loc_18000F01C
0x18000f017  lea     eax, [rcx+2]
0x18000f01a  jmp     short loc_18000F031
0x18000f01c  mov     rax, rbp
0x18000f01f  inc     rax
0x18000f022  cmp     [rcx+rax*2], r13w
0x18000f027  jnz     short loc_18000F01F
0x18000f029  lea     rax, ds:2[rax*2]
0x18000f031  lea     r14, [rdx+rax]
0x18000f035  add     r14, r8
0x18000f038  lea     rsi, [rdi+48h]
0x18000f03c  cmp     [rdi+40h], r13
0x18000f040  jz      short loc_18000F047
0x18000f042  cmp     [rsi], r14
0x18000f045  jnb     short loc_18000F07B
0x18000f047  mov     rdx, r14; dwBytes
0x18000f04a  mov     ecx, 8; dwFlags
0x18000f04f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f054  mov     r15, rax
0x18000f057  test    rax, rax
0x18000f05a  jz      short loc_18000F07B
0x18000f05c  mov     rbx, [rdi+40h]
0x18000f060  call    cs:__imp_GetProcessHeap
0x18000f066  mov     r8, rbx; lpMem
0x18000f069  xor     edx, edx; dwFlags
0x18000f06b  mov     rcx, rax; hHeap
0x18000f06e  call    cs:__imp_HeapFree
0x18000f074  mov     [rdi+40h], r15
0x18000f078  mov     [rsi], r14
0x18000f07b  mov     rbx, [rdi+40h]
0x18000f07f  test    rbx, rbx
0x18000f082  jz      loc_18000F180
0x18000f088  mov     rdx, [rsi]; DestinationSize
0x18000f08b  lea     rsi, [rdx+rbx]
0x18000f08f  cmp     rbx, rsi
0x18000f092  jz      short loc_18000F0D2
0x18000f094  mov     r8, [r12+38h]; Source
0x18000f099  test    r8, r8
0x18000f09c  jz      short loc_18000F0D2
0x18000f09e  cmp     [r8], r13b
0x18000f0a1  jz      short loc_18000F0D2
0x18000f0a3  mov     rax, rbp
0x18000f0a6  inc     rax
0x18000f0a9  cmp     [r8+rax], r13b
0x18000f0ad  jnz     short loc_18000F0A6
0x18000f0af  lea     r14, [rax+1]
0x18000f0b3  cmp     rdx, r14
0x18000f0b6  jnb     short loc_18000F0BE
0x18000f0b8  mov     [rdi+10h], r13
0x18000f0bc  jmp     short loc_18000F0DB
0x18000f0be  mov     r9, r14; SourceSize
0x18000f0c1  mov     rcx, rbx; Destination
0x18000f0c4  call    memcpy_s
0x18000f0c9  mov     [rdi+10h], rbx
0x18000f0cd  add     rbx, r14
0x18000f0d0  jmp     short loc_18000F0D6
0x18000f0d2  mov     [rdi+10h], r13
0x18000f0d6  cmp     rbx, rsi
0x18000f0d9  jz      short loc_18000F122
0x18000f0db  mov     r8, [r12+80h]; Source
0x18000f0e3  test    r8, r8
0x18000f0e6  jz      short loc_18000F122
0x18000f0e8  cmp     [r8], r13b
0x18000f0eb  jz      short loc_18000F122
0x18000f0ed  mov     rax, rbp
0x18000f0f0  inc     rax
0x18000f0f3  cmp     [r8+rax], r13b
0x18000f0f7  jnz     short loc_18000F0F0
0x18000f0f9  mov     rdx, rsi
0x18000f0fc  lea     r14, [rax+1]
0x18000f100  sub     rdx, rbx; DestinationSize
0x18000f103  cmp     rdx, r14
0x18000f106  jnb     short loc_18000F10E
0x18000f108  mov     [rdi+20h], r13
0x18000f10c  jmp     short loc_18000F12B
0x18000f10e  mov     r9, r14; SourceSize
0x18000f111  mov     rcx, rbx; Destination
0x18000f114  call    memcpy_s
0x18000f119  mov     [rdi+20h], rbx
0x18000f11d  add     rbx, r14
0x18000f120  jmp     short loc_18000F126
0x18000f122  mov     [rdi+20h], r13
0x18000f126  cmp     rbx, rsi
0x18000f129  jz      short loc_18000F16C
0x18000f12b  mov     r8, [r12+18h]; Source
0x18000f130  test    r8, r8
0x18000f133  jz      short loc_18000F16C
0x18000f135  cmp     [r8], r13w
0x18000f139  jz      short loc_18000F16C
0x18000f13b  inc     rbp
0x18000f13e  cmp     [r8+rbp*2], r13w
0x18000f143  jnz     short loc_18000F13B
0x18000f145  mov     rdx, rsi
0x18000f148  lea     r14, ds:2[rbp*2]
0x18000f150  sub     rdx, rbx; DestinationSize
0x18000f153  cmp     rdx, r14
0x18000f156  jb      short loc_18000F16C
0x18000f158  mov     r9, r14; SourceSize
0x18000f15b  mov     rcx, rbx; Destination
0x18000f15e  call    memcpy_s
0x18000f163  mov     [rdi+38h], rbx
0x18000f167  add     rbx, r14
0x18000f16a  jmp     short loc_18000F170
0x18000f16c  mov     [rdi+38h], r13
0x18000f170  sub     rsi, rbx
0x18000f173  xor     edx, edx; Val
0x18000f175  mov     r8, rsi; Size
0x18000f178  mov     rcx, rbx; void *
0x18000f17b  call    memset_0
0x18000f180  add     rsp, 28h
0x18000f184  pop     r15
0x18000f186  pop     r14
0x18000f188  pop     r13
0x18000f18a  pop     r12
0x18000f18c  pop     rdi
0x18000f18d  pop     rsi
0x18000f18e  pop     rbp
0x18000f18f  pop     rbx
0x18000f190  retn
```
