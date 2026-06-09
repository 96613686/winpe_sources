# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)

- ea: `0x180007130`
- end: `0x1800073d5`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `677`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180048090`
- `0x180048140`
- `0x1800481c0`
- `0x180048260`
- `0x1800487a0`
- `0x180048800`

## callees

- `0x180007130`
- `0x1800170b4`
- `0x1800170c0`
- `0x180017e20`
- `0x1800594bc`
- `0x1800594c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000723c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000723c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800071c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800073b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800073b2`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(__int64 a1, unsigned int *a2)
{
  int v2; // ebp
  int v5; // r8d
  unsigned int v6; // r10d
  __int64 v7; // rbx
  int v8; // r11d
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  int v13; // ebx
  unsigned int v14; // ebx
  char *v15; // r14
  __int64 v16; // rcx
  unsigned int v17; // edx
  __int64 k; // r10
  __int64 v19; // rbx
  __int64 result; // rax
  int i; // edx
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // rax
  bool v25; // zf
  bool v26; // cc
  int j; // r9d
  __int64 v28; // rcx
  __int64 v29; // rcx

  v2 = *(_DWORD *)(a1 + 60);
  v5 = v2;
  if ( v2 )
  {
    v6 = *a2;
    if ( v2 < 4 )
    {
      v23 = 0;
      while ( v23 < v2 )
      {
        v24 = *(_QWORD *)(a1 + 48);
        v25 = *(_DWORD *)(v24 + 40LL * v23) == v6;
        v26 = *(_DWORD *)(v24 + 40LL * v23) <= v6;
        v10 = v24 + 40LL * v23;
        if ( v25 )
        {
          v29 = *(_QWORD *)a2 - *(_QWORD *)v10;
          if ( *(_QWORD *)a2 == *(_QWORD *)v10 )
            v29 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v10 + 8);
          if ( !v29 )
            goto LABEL_9;
          ++v23;
        }
        else
        {
          if ( !v26 )
            break;
          ++v23;
        }
      }
    }
    else
    {
      v7 = *(_QWORD *)(a1 + 48);
      v8 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v9 = (v8 + v5) / 2;
          v10 = v7 + 40 * v9;
          if ( v6 >= *(_DWORD *)v10 )
            break;
          if ( (_DWORD)v9 == v8 )
            goto LABEL_10;
          v5 = (v8 + v5) / 2;
        }
        if ( v6 <= *(_DWORD *)(v7 + 40 * v9) )
          break;
        v8 = v9 + 1;
        if ( (_DWORD)v9 + 1 == v5 )
          goto LABEL_10;
      }
      v11 = *(_QWORD *)a2 - *(_QWORD *)v10;
      if ( *(_QWORD *)a2 == *(_QWORD *)v10 )
        v11 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v10 + 8);
      if ( v11 )
      {
        if ( (int)v9 > v8 )
        {
          for ( i = v9 - 1; i >= v8; --i )
          {
            v10 = v7 + 40LL * i;
            if ( v6 != *(_DWORD *)v10 )
              break;
            v22 = *(_QWORD *)a2 - *(_QWORD *)v10;
            if ( *(_QWORD *)a2 == *(_QWORD *)v10 )
              v22 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v10 + 8);
            if ( !v22 )
              goto LABEL_9;
          }
        }
        for ( j = v9 + 1; j < v5; ++j )
        {
          v10 = v7 + 40LL * j;
          if ( v6 != *(_DWORD *)v10 )
            break;
          v28 = *(_QWORD *)a2 - *(_QWORD *)v10;
          if ( *(_QWORD *)a2 == *(_QWORD *)v10 )
            v28 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v10 + 8);
          if ( !v28 )
            goto LABEL_9;
        }
      }
      else
      {
LABEL_9:
        v12 = v10 + 16;
        if ( v10 != -16 )
        {
          PropVariantClear((PROPVARIANT *)(v10 + 16));
          return v12;
        }
      }
    }
  }
LABEL_10:
  v13 = *(_DWORD *)(a1 + 56);
  if ( v2 == v13 )
  {
    v14 = 2 * v13 + 4;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    if ( v14 > *(_DWORD *)(a1 + 56) )
    {
      v15 = (char *)operator new[](saturated_mul(v14, 0x28u));
      if ( !v15 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        return 0;
      }
      memcpy_0(v15, *(const void **)(a1 + 48), 40LL * *(unsigned int *)(a1 + 60));
      operator delete(*(void **)(a1 + 48));
      v16 = *(unsigned int *)(a1 + 60);
      *(_DWORD *)(a1 + 56) = v14;
      *(_QWORD *)(a1 + 48) = v15;
      memset_0(&v15[40 * v16], 0, 40LL * (v14 - (unsigned int)v16));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  }
  v17 = *(_DWORD *)(a1 + 60);
  for ( k = 0; (unsigned int)k < v17; k = (unsigned int)(k + 1) )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 40 * k) >= *a2 )
      break;
  }
  v19 = 40 * k;
  memmove_0(
    (void *)(*(_QWORD *)(a1 + 48) + 40LL * (unsigned int)(k + 1)),
    (const void *)(40 * k + *(_QWORD *)(a1 + 48)),
    40LL * (v17 - (unsigned int)k));
  *(_OWORD *)(v19 + *(_QWORD *)(a1 + 48)) = *(_OWORD *)a2;
  result = v19 + *(_QWORD *)(a1 + 48) + 16LL;
  *(_OWORD *)result = 0;
  *(_QWORD *)(result + 16) = 0;
  ++*(_DWORD *)(a1 + 60);
  return result;
}

```

## disassembly

```asm
0x180007130  push    rbx
0x180007132  push    rbp
0x180007133  push    rsi
0x180007134  push    rdi
0x180007135  sub     rsp, 28h
0x180007139  mov     ebp, [rcx+3Ch]
0x18000713c  mov     rsi, rdx
0x18000713f  mov     rdi, rcx
0x180007142  mov     r8d, ebp
0x180007145  test    ebp, ebp
0x180007147  jz      short loc_1800071A6
0x180007149  mov     r10d, [rdx]
0x18000714c  cmp     ebp, 4
0x18000714f  jl      loc_180007304
0x180007155  mov     rbx, [rcx+30h]
0x180007159  xor     r11d, r11d
0x18000715c  lea     eax, [r11+r8]
0x180007160  cdq
0x180007161  sub     eax, edx
0x180007163  sar     eax, 1
0x180007165  movsxd  r9, eax
0x180007168  lea     rdx, [r9+r9*4]
0x18000716c  cmp     r10d, [rbx+rdx*8]
0x180007170  lea     rax, [rbx+rdx*8]
0x180007174  jb      loc_18000738C
0x18000717a  ja      loc_18000739D
0x180007180  mov     rcx, [rsi]
0x180007183  sub     rcx, [rax]
0x180007186  jnz     short loc_180007190
0x180007188  mov     rcx, [rsi+8]
0x18000718c  sub     rcx, [rax+8]
0x180007190  test    rcx, rcx
0x180007193  jnz     loc_1800072C8
0x180007199  lea     rbx, [rax+10h]
0x18000719d  test    rbx, rbx
0x1800071a0  jnz     loc_1800073AF
0x1800071a6  mov     ebx, [rdi+38h]
0x1800071a9  mov     [rsp+48h+arg_0], r14
0x1800071ae  cmp     ebp, ebx
0x1800071b0  jnz     loc_180007242
0x1800071b6  lea     rcx, [rdi+8]; lpCriticalSection
0x1800071ba  lea     ebx, ds:4[rbx*2]
0x1800071c1  call    cs:__imp_EnterCriticalSection
0x1800071c7  cmp     ebx, [rdi+38h]
0x1800071ca  jbe     short loc_180007238
0x1800071cc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800071d3  mov     edx, ebx
0x1800071d5  mov     eax, 28h ; '('
0x1800071da  mul     rdx
0x1800071dd  cmovb   rax, rcx
0x1800071e1  mov     rcx, rax; unsigned __int64
0x1800071e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800071e9  mov     r14, rax
0x1800071ec  test    rax, rax
0x1800071ef  jz      loc_1800073C4
0x1800071f5  mov     eax, [rdi+3Ch]
0x1800071f8  mov     rcx, r14; void *
0x1800071fb  mov     rdx, [rdi+30h]; Src
0x1800071ff  lea     r8, [rax+rax*4]
0x180007203  shl     r8, 3; Size
0x180007207  call    memcpy_0
0x18000720c  mov     rcx, [rdi+30h]; Block
0x180007210  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007215  mov     ecx, [rdi+3Ch]
0x180007218  xor     edx, edx; Val
0x18000721a  mov     [rdi+38h], ebx
0x18000721d  sub     ebx, ecx
0x18000721f  mov     [rdi+30h], r14
0x180007223  lea     rax, [rcx+rcx*4]
0x180007227  lea     r8, [rbx+rbx*4]
0x18000722b  shl     r8, 3; Size
0x18000722f  lea     rcx, [r14+rax*8]; void *
0x180007233  call    memset_0
0x180007238  lea     rcx, [rdi+8]; lpCriticalSection
0x18000723c  call    cs:__imp_LeaveCriticalSection
0x180007242  mov     edx, [rdi+3Ch]
0x180007245  xor     r10d, r10d
0x180007248  test    edx, edx
0x18000724a  jz      short loc_180007265
0x18000724c  mov     r8d, [rsi]
0x18000724f  mov     r9, [rdi+30h]
0x180007253  lea     rcx, [r10+r10*4]
0x180007257  cmp     [r9+rcx*8], r8d
0x18000725b  jnb     short loc_180007265
0x18000725d  inc     r10d
0x180007260  cmp     r10d, edx
0x180007263  jb      short loc_180007253
0x180007265  mov     r9, [rdi+30h]
0x180007269  lea     rcx, [r10+r10*4]
0x18000726d  sub     edx, r10d
0x180007270  lea     rbx, ds:0[rcx*8]
0x180007278  lea     eax, [r10+1]
0x18000727c  lea     rax, [rax+rax*4]
0x180007280  lea     rcx, [r9+rax*8]; void *
0x180007284  lea     r8, [rdx+rdx*4]
0x180007288  shl     r8, 3; Size
0x18000728c  lea     rdx, [rbx+r9]; Src
0x180007290  call    memmove_0
0x180007295  movups  xmm0, xmmword ptr [rsi]
0x180007298  mov     rax, [rdi+30h]
0x18000729c  xor     ecx, ecx
0x18000729e  movups  xmmword ptr [rbx+rax], xmm0
0x1800072a2  mov     rax, [rdi+30h]
0x1800072a6  add     rax, 10h
0x1800072aa  xorps   xmm0, xmm0
0x1800072ad  add     rax, rbx
0x1800072b0  movups  xmmword ptr [rax], xmm0
0x1800072b3  mov     [rax+10h], rcx
0x1800072b7  inc     dword ptr [rdi+3Ch]
0x1800072ba  mov     r14, [rsp+48h+arg_0]
0x1800072bf  add     rsp, 28h
0x1800072c3  pop     rdi
0x1800072c4  pop     rsi
0x1800072c5  pop     rbp
0x1800072c6  pop     rbx
0x1800072c7  retn
0x1800072c8  cmp     r9d, r11d
0x1800072cb  jle     short loc_18000732D
0x1800072cd  lea     edx, [r9-1]
0x1800072d1  cmp     edx, r11d
0x1800072d4  jl      short loc_18000732D
0x1800072d6  movsxd  rax, edx
0x1800072d9  lea     rcx, [rax+rax*4]
0x1800072dd  cmp     r10d, [rbx+rcx*8]
0x1800072e1  lea     rax, [rbx+rcx*8]
0x1800072e5  jnz     short loc_18000732D
0x1800072e7  mov     rcx, [rsi]
0x1800072ea  sub     rcx, [rax]
0x1800072ed  jnz     short loc_1800072F7
0x1800072ef  mov     rcx, [rsi+8]
0x1800072f3  sub     rcx, [rax+8]
0x1800072f7  test    rcx, rcx
0x1800072fa  jz      loc_180007199
0x180007300  dec     edx
0x180007302  jmp     short loc_1800072D1
0x180007304  xor     edx, edx
0x180007306  cmp     edx, ebp
0x180007308  jge     loc_1800071A6
0x18000730e  movsxd  rax, edx
0x180007311  lea     rcx, [rax+rax*4]
0x180007315  mov     rax, [rdi+30h]
0x180007319  cmp     [rax+rcx*8], r10d
0x18000731d  lea     rax, [rax+rcx*8]
0x180007321  jz      short loc_18000736C
0x180007323  ja      loc_1800071A6
0x180007329  inc     edx
0x18000732b  jmp     short loc_180007306
0x18000732d  inc     r9d
0x180007330  cmp     r9d, r8d
0x180007333  jge     loc_1800071A6
0x180007339  movsxd  rax, r9d
0x18000733c  lea     rcx, [rax+rax*4]
0x180007340  cmp     r10d, [rbx+rcx*8]
0x180007344  lea     rax, [rbx+rcx*8]
0x180007348  jnz     loc_1800071A6
0x18000734e  mov     rcx, [rsi]
0x180007351  sub     rcx, [rax]
0x180007354  jnz     short loc_18000735E
0x180007356  mov     rcx, [rsi+8]
0x18000735a  sub     rcx, [rax+8]
0x18000735e  test    rcx, rcx
0x180007361  jz      loc_180007199
0x180007367  inc     r9d
0x18000736a  jmp     short loc_180007330
0x18000736c  mov     rcx, [rsi]
0x18000736f  sub     rcx, [rax]
0x180007372  jnz     short loc_18000737C
0x180007374  mov     rcx, [rsi+8]
0x180007378  sub     rcx, [rax+8]
0x18000737c  test    rcx, rcx
0x18000737f  jz      loc_180007199
0x180007385  inc     edx
0x180007387  jmp     loc_180007306
0x18000738c  cmp     r9d, r11d
0x18000738f  jz      loc_1800071A6
0x180007395  mov     r8d, r9d
0x180007398  jmp     loc_18000715C
0x18000739d  lea     r11d, [r9+1]
0x1800073a1  cmp     r11d, r8d
0x1800073a4  jnz     loc_18000715C
0x1800073aa  jmp     loc_1800071A6
0x1800073af  mov     rcx, rbx; pvar
0x1800073b2  call    cs:__imp_PropVariantClear
0x1800073b8  mov     rax, rbx
0x1800073bb  add     rsp, 28h
0x1800073bf  pop     rdi
0x1800073c0  pop     rsi
0x1800073c1  pop     rbp
0x1800073c2  pop     rbx
0x1800073c3  retn
0x1800073c4  lea     rcx, [rdi+8]; lpCriticalSection
0x1800073c8  call    cs:__imp_LeaveCriticalSection
0x1800073ce  xor     eax, eax
0x1800073d0  jmp     loc_1800072BA
```
