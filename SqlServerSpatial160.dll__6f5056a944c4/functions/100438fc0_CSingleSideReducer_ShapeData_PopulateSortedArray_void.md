# CSingleSideReducer::ShapeData::PopulateSortedArray(void)

- ea: `0x100438fc0`
- end: `0x1004391a1`
- name: `?PopulateSortedArray@ShapeData@CSingleSideReducer@@QEAAJXZ`
- size: `481`
- prototype: `__int64 __fastcall(CSingleSideReducer::ShapeData *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100438550`

## callees

- `0x100401210`
- `0x100438fc0`
- `0x100439310`
- `0x10046985e`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043904e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043904e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004390a8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004390a8`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x100439153`
- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x100439153`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::ShapeData::PopulateSortedArray(CSingleSideReducer::ShapeData *this)
{
  __int64 result; // rax
  int v3; // ecx
  unsigned int v4; // eax
  unsigned int v5; // esi
  bool v6; // zf
  int v7; // edi
  void *v8; // rax
  void *v9; // rbp
  rsize_t v10; // r9
  size_t v11; // r8
  void *v12; // rcx
  char *v13; // r14
  unsigned int v14; // ebp
  unsigned int v15; // r15d
  int v16; // eax
  unsigned int v17; // r8d
  int v18; // ecx
  __int64 v19; // rcx
  __int64 v20; // rax
  int v21; // esi
  rsize_t v22; // rdi
  int v23; // eax
  int v24; // ecx

  result = CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(
             (char *)this + 40,
             *((unsigned int *)this + 2));
  _mm_lfence();
  if ( (int)result < 0 )
    return result;
  v3 = *((_DWORD *)this + 2);
  *((_DWORD *)this + 11) = v3;
  v4 = *((_DWORD *)this + 15);
  v5 = v3 + v4;
  if ( v3 + v4 < v4 )
  {
    v7 = -2147024362;
    goto LABEL_24;
  }
  if ( v5 > *((_DWORD *)this + 14) )
  {
    v6 = g_SOSHost == 0;
    _mm_lfence();
    if ( v6 )
    {
      v8 = malloc(v5);
      v7 = -2147024882;
    }
    else
    {
      v7 = -2147024882;
      v8 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, const char *, __int64))(*g_SOSMemObj + 120LL))(
                     g_SOSMemObj,
                     v5,
                     "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
                     54);
    }
    v9 = v8;
    if ( v8 )
      v7 = 0;
    if ( v7 >= 0 )
    {
      v10 = *((unsigned int *)this + 15);
      _mm_lfence();
      memcpy_s(v8, v5, *((const void *const *)this + 8), v10);
      if ( g_SOSHost )
      {
        if ( *((_QWORD *)this + 8) )
          (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
      }
      else
      {
        free(*((void **)this + 8));
      }
      *((_QWORD *)this + 8) = v9;
      *((_DWORD *)this + 14) = v5;
      goto LABEL_15;
    }
LABEL_24:
    _mm_lfence();
    return (unsigned int)v7;
  }
LABEL_15:
  _mm_lfence();
  v11 = *((unsigned int *)this + 2);
  v12 = (void *)*((_QWORD *)this + 8);
  *((_DWORD *)this + 15) = v11;
  memset_0(v12, 0, v11);
  v13 = (char *)*((_QWORD *)this + 6);
  v14 = 0;
  v15 = *((_DWORD *)this + 2);
  while ( 1 )
  {
    v16 = *((_DWORD *)this + 5);
    v17 = *((_DWORD *)this + 9);
    v18 = v16 - 1;
    if ( !v16 )
      v18 = 0;
    if ( v14 >= *((_DWORD *)this + 8) + v17 * v18 )
      break;
    v19 = 56LL * (v14 % v17);
    v20 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * (v14 / v17));
    v21 = *(_DWORD *)(v20 + v19 + 48);
    v22 = 16LL * v21;
    memcpy_s(v13, 16LL * v15, *(const void *const *)(v20 + v19 + 32), v22);
    v13 += v22;
    v15 -= v21;
    ++v14;
  }
  qsort(*((void **)this + 6), *((unsigned int *)this + 2), 0x10u, CompareT<double>);
  v23 = *((_DWORD *)this + 5);
  v24 = v23 - 1;
  if ( !v23 )
    v24 = 0;
  *((_DWORD *)this + 1) = *((_DWORD *)this + 8) + *((_DWORD *)this + 9) * v24;
  return 0;
}

```

## disassembly

```asm
0x100438fc0  push    rbx
0x100438fc2  sub     rsp, 30h
0x100438fc6  mov     rbx, rcx
0x100438fc9  add     rcx, 28h ; '('
0x100438fcd  mov     edx, [rbx+8]
0x100438fd0  call    ?Reserve@?$CAutoArray@V?$CMglPoint@N@@$0A@V?$Default_Allocator@V?$CMglPoint@N@@@@@@QEAAJI@Z; CAutoArray<CMglPoint<double>,0,Default_Allocator<CMglPoint<double>>>::Reserve(uint)
0x100438fd5  lfence
0x100438fd8  test    eax, eax
0x100438fda  js      loc_10043919B
0x100438fe0  mov     ecx, [rbx+8]
0x100438fe3  mov     [rsp+38h+arg_0], rbp
0x100438fe8  mov     [rsp+38h+arg_8], rsi
0x100438fed  mov     [rsp+38h+arg_10], rdi
0x100438ff2  mov     [rbx+2Ch], ecx
0x100438ff5  mov     eax, [rbx+3Ch]
0x100438ff8  mov     [rsp+38h+arg_18], r12
0x100438ffd  mov     [rsp+38h+var_10], r14
0x100439002  lea     esi, [rcx+rax]
0x100439005  cmp     esi, eax
0x100439007  jb      loc_100439178
0x10043900d  xor     r12d, r12d
0x100439010  cmp     esi, [rbx+38h]
0x100439013  jbe     loc_1004390B5
0x100439019  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x100439020  mov     r14d, esi
0x100439023  lfence
0x100439026  jz      short loc_10043904B
0x100439028  mov     edi, 8007000Eh
0x10043902d  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100439034  lea     r9d, [r12+36h]
0x100439039  lea     r8, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100439040  mov     edx, r14d
0x100439043  mov     rax, [rcx]
0x100439046  call    qword ptr [rax+78h]
0x100439049  jmp     short loc_100439059
0x10043904b  mov     rcx, r14; Size
0x10043904e  call    cs:__imp_malloc
0x100439054  mov     edi, 8007000Eh
0x100439059  test    rax, rax
0x10043905c  mov     rbp, rax
0x10043905f  cmovnz  edi, r12d
0x100439063  test    edi, edi
0x100439065  js      loc_10043917D
0x10043906b  mov     r9d, [rbx+3Ch]; SourceSize
0x10043906f  lfence
0x100439072  mov     r8, [rbx+40h]; Source
0x100439076  mov     rdx, r14; DestinationSize
0x100439079  mov     rcx, rax; Destination
0x10043907c  call    memcpy_s
0x100439081  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x100439088  mov     rdx, [rbx+40h]
0x10043908c  jz      short loc_1004390A5
0x10043908e  test    rdx, rdx
0x100439091  jz      short loc_1004390AE
0x100439093  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043909a  mov     rax, [rcx]
0x10043909d  call    qword ptr [rax+80h]
0x1004390a3  jmp     short loc_1004390AE
0x1004390a5  mov     rcx, rdx; Block
0x1004390a8  call    cs:__imp_free
0x1004390ae  mov     [rbx+40h], rbp
0x1004390b2  mov     [rbx+38h], esi
0x1004390b5  mov     [rsp+38h+var_18], r15
0x1004390ba  lfence
0x1004390bd  mov     r8d, [rbx+8]; Size
0x1004390c1  xor     edx, edx; Val
0x1004390c3  mov     rcx, [rbx+40h]; void *
0x1004390c7  mov     [rbx+3Ch], r8d
0x1004390cb  call    memset_0
0x1004390d0  mov     r14, [rbx+30h]
0x1004390d4  mov     ebp, r12d
0x1004390d7  mov     r15d, [rbx+8]
0x1004390db  nop     dword ptr [rax+rax+00h]
0x1004390e0  mov     eax, [rbx+14h]
0x1004390e3  test    eax, eax
0x1004390e5  mov     r8d, [rbx+24h]
0x1004390e9  lea     ecx, [rax-1]
0x1004390ec  cmovz   ecx, r12d
0x1004390f0  imul    ecx, r8d
0x1004390f4  add     ecx, [rbx+20h]
0x1004390f7  cmp     ebp, ecx
0x1004390f9  jnb     short loc_10043913F
0x1004390fb  xor     edx, edx
0x1004390fd  mov     eax, ebp
0x1004390ff  div     r8d
0x100439102  mov     ecx, edx
0x100439104  imul    rcx, 38h ; '8'
0x100439108  mov     edx, eax
0x10043910a  mov     rax, [rbx+18h]
0x10043910e  mov     rax, [rax+rdx*8]
0x100439112  mov     edx, r15d
0x100439115  shl     rdx, 4; DestinationSize
0x100439119  movsxd  rsi, dword ptr [rax+rcx+30h]
0x10043911e  mov     r8, [rax+rcx+20h]; Source
0x100439123  mov     rdi, rsi
0x100439126  shl     rdi, 4
0x10043912a  mov     rcx, r14; Destination
0x10043912d  mov     r9, rdi; SourceSize
0x100439130  call    memcpy_s
0x100439135  add     r14, rdi
0x100439138  sub     r15d, esi
0x10043913b  inc     ebp
0x10043913d  jmp     short loc_1004390E0
0x10043913f  mov     edx, [rbx+8]; NumOfElements
0x100439142  lea     r9, ??$CompareT@N@@YAHPEBX0@Z; CompareFunction
0x100439149  mov     rcx, [rbx+30h]; Base
0x10043914d  mov     r8d, 10h; SizeOfElements
0x100439153  call    cs:__imp_qsort
0x100439159  mov     eax, [rbx+14h]
0x10043915c  test    eax, eax
0x10043915e  mov     r15, [rsp+38h+var_18]
0x100439163  lea     ecx, [rax-1]
0x100439166  cmovz   ecx, r12d
0x10043916a  imul    ecx, [rbx+24h]
0x10043916e  add     ecx, [rbx+20h]
0x100439171  mov     [rbx+4], ecx
0x100439174  xor     eax, eax
0x100439176  jmp     short loc_100439182
0x100439178  mov     edi, 80070216h
0x10043917d  lfence
0x100439180  mov     eax, edi
0x100439182  mov     r12, [rsp+38h+arg_18]
0x100439187  mov     rdi, [rsp+38h+arg_10]
0x10043918c  mov     rsi, [rsp+38h+arg_8]
0x100439191  mov     rbp, [rsp+38h+arg_0]
0x100439196  mov     r14, [rsp+38h+var_10]
0x10043919b  add     rsp, 30h
0x10043919f  pop     rbx
0x1004391a0  retn
```
