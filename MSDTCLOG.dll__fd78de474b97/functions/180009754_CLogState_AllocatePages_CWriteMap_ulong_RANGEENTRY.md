# CLogState::_AllocatePages(CWriteMap &,ulong *,_RANGEENTRY *)

- ea: `0x180009754`
- end: `0x180009842`
- name: `?_AllocatePages@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CLogState *__hidden this, struct CWriteMap *, unsigned int *, struct _RANGEENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009298`

## callees

- `0x180009754`
- `0x180009934`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097eb`

## pseudocode

```c
__int64 __fastcall CLogState::_AllocatePages(
        CLogState *this,
        struct CWriteMap *a2,
        unsigned int *a3,
        struct _RANGEENTRY *a4)
{
  int v4; // r10d
  unsigned int v9; // r9d
  _DWORD *v10; // rax
  int v11; // ecx
  unsigned int v12; // edx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rax
  __int128 v16; // xmm1
  bool v18; // zf
  unsigned int v19; // eax
  int v20; // eax

  v4 = *a3;
  v9 = *((_DWORD *)this + 31);
  v10 = (_DWORD *)((char *)this + 80);
  v11 = 8160 * v9;
  v12 = *a3 / 0x1FE0;
  if ( *a3 <= 8160 * v9 )
  {
    v13 = 0;
    v11 = *v10 * v12;
  }
  else
  {
    v13 = 1;
  }
  *((_DWORD *)a4 + 1) = v11;
  *((_DWORD *)a4 + 7) = 1;
  if ( !v13 )
    v9 = v12;
  v14 = *v10 * v9;
  *((_DWORD *)a4 + 3) = v14;
  if ( v11 )
  {
    v15 = 32LL * *((unsigned int *)a2 + 20);
    v16 = *((_OWORD *)a4 + 1);
    *(_OWORD *)((char *)a2 + v15 + 84) = *(_OWORD *)a4;
    *(_OWORD *)((char *)a2 + v15 + 100) = v16;
    ++*((_DWORD *)a2 + 20);
  }
  *((_DWORD *)this + 4) -= v11;
  *a3 = v4 - v11;
  if ( v13 )
  {
    GetCurrentThreadId();
    CLogState::_DoWrapAround(this);
  }
  else
  {
    *((_DWORD *)this + 31) -= v12;
    *((_DWORD *)this + 30) += v14;
  }
  if ( !*a3 )
    return 1;
  *((_DWORD *)a4 + 2) += *((_DWORD *)a4 + 3);
  v18 = *((_DWORD *)this + 26) == 0;
  v19 = *((_DWORD *)a4 + 2);
  *(_DWORD *)a4 = 0;
  if ( !v18 && v19 >= *((_DWORD *)this + 14) )
  {
    v20 = *(_DWORD *)this;
    ++*((_DWORD *)a4 + 4);
    *((_DWORD *)a4 + 2) = v20;
  }
  return 0;
}

```

## disassembly

```asm
0x180009754  mov     [rsp+arg_0], rbx
0x180009759  mov     [rsp+arg_8], rsi
0x18000975e  push    rdi
0x18000975f  sub     rsp, 20h
0x180009763  mov     r10d, [r8]
0x180009766  mov     eax, 80808081h
0x18000976b  mov     r11, rdx
0x18000976e  mov     rbx, rcx
0x180009771  mul     r10d
0x180009774  mov     rdi, r9
0x180009777  mov     rsi, r8
0x18000977a  mov     r9d, [rcx+7Ch]
0x18000977e  lea     rax, [rbx+50h]
0x180009782  imul    ecx, r9d, 1FE0h
0x180009789  shr     edx, 0Ch
0x18000978c  cmp     r10d, ecx
0x18000978f  jbe     short loc_180009799
0x180009791  mov     r8d, 1
0x180009797  jmp     short loc_1800097A1
0x180009799  xor     r8d, r8d
0x18000979c  mov     ecx, edx
0x18000979e  imul    ecx, [rax]
0x1800097a1  test    r8d, r8d
0x1800097a4  mov     [rdi+4], ecx
0x1800097a7  mov     dword ptr [rdi+1Ch], 1
0x1800097ae  cmovz   r9d, edx
0x1800097b2  imul    r9d, [rax]
0x1800097b6  mov     [rdi+0Ch], r9d
0x1800097ba  test    ecx, ecx
0x1800097bc  jz      short loc_1800097DD
0x1800097be  mov     eax, [r11+50h]
0x1800097c2  movups  xmm0, xmmword ptr [rdi]
0x1800097c5  shl     rax, 5
0x1800097c9  movups  xmm1, xmmword ptr [rdi+10h]
0x1800097cd  movups  xmmword ptr [rax+r11+54h], xmm0
0x1800097d3  movups  xmmword ptr [rax+r11+64h], xmm1
0x1800097d9  inc     dword ptr [r11+50h]
0x1800097dd  sub     [rbx+10h], ecx
0x1800097e0  sub     r10d, ecx
0x1800097e3  mov     [rsi], r10d
0x1800097e6  test    r8d, r8d
0x1800097e9  jz      short loc_1800097FB
0x1800097eb  call    cs:__imp_GetCurrentThreadId
0x1800097f1  mov     rcx, rbx; this
0x1800097f4  call    ?_DoWrapAround@CLogState@@AEAAXXZ; CLogState::_DoWrapAround(void)
0x1800097f9  jmp     short loc_180009802
0x1800097fb  sub     [rbx+7Ch], edx
0x1800097fe  add     [rbx+78h], r9d
0x180009802  cmp     dword ptr [rsi], 0
0x180009805  jnz     short loc_18000980E
0x180009807  mov     eax, 1
0x18000980c  jmp     short loc_180009832
0x18000980e  mov     eax, [rdi+0Ch]
0x180009811  add     [rdi+8], eax
0x180009814  cmp     dword ptr [rbx+68h], 0
0x180009818  mov     eax, [rdi+8]
0x18000981b  mov     dword ptr [rdi], 0
0x180009821  jz      short loc_180009830
0x180009823  cmp     eax, [rbx+38h]
0x180009826  jb      short loc_180009830
0x180009828  mov     eax, [rbx]
0x18000982a  inc     dword ptr [rdi+10h]
0x18000982d  mov     [rdi+8], eax
0x180009830  xor     eax, eax
0x180009832  mov     rbx, [rsp+28h+arg_0]
0x180009837  mov     rsi, [rsp+28h+arg_8]
0x18000983c  add     rsp, 20h
0x180009840  pop     rdi
0x180009841  retn
```
