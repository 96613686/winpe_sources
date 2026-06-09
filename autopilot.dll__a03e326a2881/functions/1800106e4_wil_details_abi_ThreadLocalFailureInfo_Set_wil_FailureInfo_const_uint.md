# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800106e4`
- end: `0x1800108fd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d030`

## callees

- `0x180005374`
- `0x18000e6bc`
- `0x1800106e4`
- `0x1800134ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107da`

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
0x1800106e4  push    rbx
0x1800106e6  push    rbp
0x1800106e7  push    rsi
0x1800106e8  push    rdi
0x1800106e9  push    r12
0x1800106eb  push    r13
0x1800106ed  push    r14
0x1800106ef  push    r15
0x1800106f1  sub     rsp, 28h
0x1800106f5  mov     [rcx+4], r8d
0x1800106f9  xor     r13d, r13d
0x1800106fc  mov     eax, [rdx+8]
0x1800106ff  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180010703  mov     [rcx+8], eax
0x180010706  mov     rdi, rcx
0x180010709  mov     [rcx+10h], r13
0x18001070d  mov     r12, rdx
0x180010710  movzx   eax, word ptr [rdx+40h]
0x180010714  mov     [rcx+18h], ax
0x180010718  mov     al, [rdx]
0x18001071a  mov     [rcx+1Ah], al
0x18001071d  mov     [rcx+20h], r13
0x180010721  mov     rax, [rdx+88h]
0x180010728  mov     [rcx+28h], rax
0x18001072c  mov     rax, [rdx+90h]
0x180010733  mov     [rcx+30h], rax
0x180010737  mov     [rcx+38h], r13
0x18001073b  mov     rcx, [rdx+38h]
0x18001073f  lea     edx, [rbp+2]
0x180010742  test    rcx, rcx
0x180010745  jnz     short loc_18001074C
0x180010747  mov     r8d, edx
0x18001074a  jmp     short loc_18001075C
0x18001074c  mov     rax, rbp
0x18001074f  inc     rax
0x180010752  cmp     [rcx+rax], r13b
0x180010756  jnz     short loc_18001074F
0x180010758  lea     r8, [rax+1]; unsigned __int64
0x18001075c  mov     rcx, [r12+80h]
0x180010764  test    rcx, rcx
0x180010767  jz      short loc_180010779
0x180010769  mov     rax, rbp
0x18001076c  inc     rax
0x18001076f  cmp     [rcx+rax], r13b
0x180010773  jnz     short loc_18001076C
0x180010775  lea     rdx, [rax+1]
0x180010779  mov     rcx, [r12+18h]
0x18001077e  test    rcx, rcx
0x180010781  jnz     short loc_180010788
0x180010783  lea     eax, [rcx+2]
0x180010786  jmp     short loc_18001079D
0x180010788  mov     rax, rbp
0x18001078b  inc     rax
0x18001078e  cmp     [rcx+rax*2], r13w
0x180010793  jnz     short loc_18001078B
0x180010795  lea     rax, ds:2[rax*2]
0x18001079d  lea     r14, [rdx+rax]
0x1800107a1  add     r14, r8
0x1800107a4  lea     rsi, [rdi+48h]
0x1800107a8  cmp     [rdi+40h], r13
0x1800107ac  jz      short loc_1800107B3
0x1800107ae  cmp     [rsi], r14
0x1800107b1  jnb     short loc_1800107E7
0x1800107b3  mov     rdx, r14; dwBytes
0x1800107b6  mov     ecx, 8; dwFlags
0x1800107bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800107c0  mov     r15, rax
0x1800107c3  test    rax, rax
0x1800107c6  jz      short loc_1800107E7
0x1800107c8  mov     rbx, [rdi+40h]
0x1800107cc  call    cs:__imp_GetProcessHeap
0x1800107d2  mov     r8, rbx; lpMem
0x1800107d5  xor     edx, edx; dwFlags
0x1800107d7  mov     rcx, rax; hHeap
0x1800107da  call    cs:__imp_HeapFree
0x1800107e0  mov     [rdi+40h], r15
0x1800107e4  mov     [rsi], r14
0x1800107e7  mov     rbx, [rdi+40h]
0x1800107eb  test    rbx, rbx
0x1800107ee  jz      loc_1800108EC
0x1800107f4  mov     rdx, [rsi]; DestinationSize
0x1800107f7  lea     rsi, [rdx+rbx]
0x1800107fb  cmp     rbx, rsi
0x1800107fe  jz      short loc_18001083E
0x180010800  mov     r8, [r12+38h]; Source
0x180010805  test    r8, r8
0x180010808  jz      short loc_18001083E
0x18001080a  cmp     [r8], r13b
0x18001080d  jz      short loc_18001083E
0x18001080f  mov     rax, rbp
0x180010812  inc     rax
0x180010815  cmp     [r8+rax], r13b
0x180010819  jnz     short loc_180010812
0x18001081b  lea     r14, [rax+1]
0x18001081f  cmp     rdx, r14
0x180010822  jnb     short loc_18001082A
0x180010824  mov     [rdi+10h], r13
0x180010828  jmp     short loc_180010847
0x18001082a  mov     r9, r14; SourceSize
0x18001082d  mov     rcx, rbx; Destination
0x180010830  call    memcpy_s
0x180010835  mov     [rdi+10h], rbx
0x180010839  add     rbx, r14
0x18001083c  jmp     short loc_180010842
0x18001083e  mov     [rdi+10h], r13
0x180010842  cmp     rbx, rsi
0x180010845  jz      short loc_18001088E
0x180010847  mov     r8, [r12+80h]; Source
0x18001084f  test    r8, r8
0x180010852  jz      short loc_18001088E
0x180010854  cmp     [r8], r13b
0x180010857  jz      short loc_18001088E
0x180010859  mov     rax, rbp
0x18001085c  inc     rax
0x18001085f  cmp     [r8+rax], r13b
0x180010863  jnz     short loc_18001085C
0x180010865  mov     rdx, rsi
0x180010868  lea     r14, [rax+1]
0x18001086c  sub     rdx, rbx; DestinationSize
0x18001086f  cmp     rdx, r14
0x180010872  jnb     short loc_18001087A
0x180010874  mov     [rdi+20h], r13
0x180010878  jmp     short loc_180010897
0x18001087a  mov     r9, r14; SourceSize
0x18001087d  mov     rcx, rbx; Destination
0x180010880  call    memcpy_s
0x180010885  mov     [rdi+20h], rbx
0x180010889  add     rbx, r14
0x18001088c  jmp     short loc_180010892
0x18001088e  mov     [rdi+20h], r13
0x180010892  cmp     rbx, rsi
0x180010895  jz      short loc_1800108D8
0x180010897  mov     r8, [r12+18h]; Source
0x18001089c  test    r8, r8
0x18001089f  jz      short loc_1800108D8
0x1800108a1  cmp     [r8], r13w
0x1800108a5  jz      short loc_1800108D8
0x1800108a7  inc     rbp
0x1800108aa  cmp     [r8+rbp*2], r13w
0x1800108af  jnz     short loc_1800108A7
0x1800108b1  mov     rdx, rsi
0x1800108b4  lea     r14, ds:2[rbp*2]
0x1800108bc  sub     rdx, rbx; DestinationSize
0x1800108bf  cmp     rdx, r14
0x1800108c2  jb      short loc_1800108D8
0x1800108c4  mov     r9, r14; SourceSize
0x1800108c7  mov     rcx, rbx; Destination
0x1800108ca  call    memcpy_s
0x1800108cf  mov     [rdi+38h], rbx
0x1800108d3  add     rbx, r14
0x1800108d6  jmp     short loc_1800108DC
0x1800108d8  mov     [rdi+38h], r13
0x1800108dc  sub     rsi, rbx
0x1800108df  xor     edx, edx; Val
0x1800108e1  mov     r8, rsi; Size
0x1800108e4  mov     rcx, rbx; void *
0x1800108e7  call    memset_0
0x1800108ec  add     rsp, 28h
0x1800108f0  pop     r15
0x1800108f2  pop     r14
0x1800108f4  pop     r13
0x1800108f6  pop     r12
0x1800108f8  pop     rdi
0x1800108f9  pop     rsi
0x1800108fa  pop     rbp
0x1800108fb  pop     rbx
0x1800108fc  retn
```
