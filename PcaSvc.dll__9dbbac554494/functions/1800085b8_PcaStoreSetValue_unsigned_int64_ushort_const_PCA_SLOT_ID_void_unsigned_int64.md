# PcaStoreSetValue(unsigned __int64,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)

- ea: `0x1800085b8`
- end: `0x180008e0e`
- name: `?PcaStoreSetValue@@YAK_KPEBGW4_PCA_SLOT_ID@@PEAX0@Z`
- size: `2134`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008e14`
- `0x18000e608`

## callees

- `0x180007d74`
- `0x180007ec0`
- `0x1800085b8`
- `0x18000f2f4`
- `0x180011178`
- `0x180012920`
- `0x180056256`
- `0x18007a9cf`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x1800087f8`
- `ntdll!RtlComputeCrc32` at `0x1800087f8`
- `ntdll!RtlFreeHeap` at `0x180008769`
- `ntdll!RtlFreeHeap` at `0x180008786`
- `ntdll!RtlFreeHeap` at `0x18000879e`
- `ntdll!RtlFreeHeap` at `0x1800087b4`
- `ntdll!RtlFreeHeap` at `0x180008769`
- `ntdll!RtlFreeHeap` at `0x180008786`
- `ntdll!RtlFreeHeap` at `0x18000879e`
- `ntdll!RtlFreeHeap` at `0x1800087b4`
- `ntdll!RtlReAllocateHeap` at `0x180008cb2`
- `ntdll!RtlReAllocateHeap` at `0x180008cc3`
- `ntdll!RtlReAllocateHeap` at `0x180008cd4`
- `ntdll!RtlReAllocateHeap` at `0x180008ce8`
- `ntdll!RtlReAllocateHeap` at `0x180008d17`
- `ntdll!RtlReAllocateHeap` at `0x180008cb2`
- `ntdll!RtlReAllocateHeap` at `0x180008cc3`
- `ntdll!RtlReAllocateHeap` at `0x180008cd4`
- `ntdll!RtlReAllocateHeap` at `0x180008ce8`
- `ntdll!RtlReAllocateHeap` at `0x180008d17`
- `ntdll!RtlAllocateHeap` at `0x180008665`
- `ntdll!RtlAllocateHeap` at `0x1800089ae`
- `ntdll!RtlAllocateHeap` at `0x180008a44`
- `ntdll!RtlAllocateHeap` at `0x180008aa4`
- `ntdll!RtlAllocateHeap` at `0x180008bfa`
- `ntdll!RtlAllocateHeap` at `0x180008c64`
- `ntdll!RtlAllocateHeap` at `0x180008665`
- `ntdll!RtlAllocateHeap` at `0x1800089ae`
- `ntdll!RtlAllocateHeap` at `0x180008a44`
- `ntdll!RtlAllocateHeap` at `0x180008aa4`
- `ntdll!RtlAllocateHeap` at `0x180008bfa`
- `ntdll!RtlAllocateHeap` at `0x180008c64`

## string_xrefs

- `0x18000872d`: `Failed to write stream [%d]`
- `0x180008a19`: `Failed to write stream [%d]`
- `0x180008aff`: `Failed to write stream [%d]`
- `0x180008b1f`: `Failed to write stream [%d]`
- `0x180008d25`: `Failed to create stream [%d]`
- `0x180008967`: `Failed to read stream [%d]`
- `0x180008cff`: `Failed to compute checksum [%d]`
- `0x180008d87`: `Failed to compute checksum [%d]`
- `0x180008da6`: `Failed to compute checksum [%d]`
- `0x180008de6`: `Failed to write header [%d]`
- `0x180008867`: `Failed to write to registry [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PcaStoreSetValue(HKEY *a1, const unsigned __int16 *a2, unsigned int a3, const void *a4, size_t Size)
{
  unsigned int v5; // ebx
  PVOID ProcessHeap; // r15
  void *v7; // rsi
  _DWORD *Heap; // rax
  _DWORD *v9; // rdi
  SIZE_T v10; // rsi
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // r14
  size_t v13; // rdx
  SIZE_T v14; // rbx
  unsigned int v15; // ebx
  const char *v16; // r9
  int v17; // r8d
  ULONG v19; // r15d
  void *v20; // rax
  unsigned int v21; // eax
  char *v22; // r15
  unsigned int v23; // eax
  char *v24; // rax
  char *v25; // rdx
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // rcx
  void *v28; // r15
  _DWORD *v29; // rax
  _DWORD *v30; // r15
  _DWORD *v31; // rax
  _DWORD *v32; // rsi
  _DWORD *v33; // rax
  _DWORD *v34; // r13
  char *v35; // rbx
  PVOID v36; // rax
  SIZE_T v37; // r15
  _DWORD *v38; // rax
  _DWORD *v39; // r13
  __int64 v40; // [rsp+28h] [rbp-A1h]
  HANDLE HeapHandle; // [rsp+38h] [rbp-91h]
  size_t v42; // [rsp+48h] [rbp-81h] BYREF
  __int128 v43; // [rsp+50h] [rbp-79h] BYREF
  __int128 v44; // [rsp+60h] [rbp-69h]
  PVOID v45[2]; // [rsp+70h] [rbp-59h]
  unsigned __int64 v46; // [rsp+80h] [rbp-49h]
  PVOID P; // [rsp+88h] [rbp-41h] BYREF
  char *v48; // [rsp+90h] [rbp-39h]
  HANDLE v49[2]; // [rsp+98h] [rbp-31h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-21h]
  PVOID v51[2]; // [rsp+B8h] [rbp-11h]
  PVOID v52; // [rsp+C8h] [rbp-1h]
  char *v53; // [rsp+D0h] [rbp+7h]

  v5 = a3;
  v42 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  *(_OWORD *)v51 = 0;
  v49[0] = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v50 + 1) = 4096;
  v43 = 0;
  v44 = 0;
  *(_OWORD *)v45 = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  HeapHandle = ProcessHeap;
  *(_QWORD *)&v43 = ProcessHeap;
  *((_QWORD *)&v44 + 1) = 4096;
  v46 = 0;
  P = 0;
  v7 = 0;
  if ( !a2 || !*a2 )
  {
    v15 = 0;
    v9 = v45[1];
    goto LABEL_17;
  }
  Heap = RtlAllocateHeap(ProcessHeap, 0, 0x1000u);
  v9 = Heap;
  if ( !Heap )
  {
    v15 = -1073741801;
    AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 960, (unsigned int)"Failed to write header [%d]", -1073741801);
    v9 = v45[1];
    goto LABEL_22;
  }
  memset_0(Heap, 0, 0x1000u);
  v45[1] = v9;
  v10 = 4096;
  *(_QWORD *)&v44 = 4096;
  *v9 = 1346584915;
  *(_QWORD *)(v9 + 1) = 1;
  v11 = 12;
  v45[0] = (PVOID)12;
  v12 = *((_QWORD *)&v43 + 1);
  if ( *((_QWORD *)&v43 + 1) <= 0xCu )
    v12 = 12;
  *((_QWORD *)&v43 + 1) = v12;
  if ( !(unsigned int)PcaStoreGetValueAlloc(&P, &v42, a1, a2, -1) )
  {
    v23 = RtlMemoryStream::InitializeFromBuffer((RtlMemoryStream *)v49, P, v42);
    v15 = v23;
    if ( v23 )
    {
      v16 = "Failed to create stream [%d]";
      v17 = 977;
      goto LABEL_82;
    }
    v24 = (char *)v51[0];
    while ( 1 )
    {
      do
      {
        if ( v24 >= v49[1] )
        {
          ProcessHeap = HeapHandle;
          v5 = a3;
          goto LABEL_7;
        }
        v25 = v24 + 8;
        v53 = v24 + 8;
        if ( v24 + 8 < v24 || v25 > v49[1] )
        {
          v15 = 160;
          LODWORD(v40) = 160;
          AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 985, (unsigned int)"Failed to read stream [%d]", v40);
          goto LABEL_16;
        }
        v26 = *(_QWORD *)((char *)v51[1] + (unsigned __int64)v24);
        v46 = v26;
        v51[0] = v24 + 8;
        v27 = HIDWORD(v26);
        v42 = HIDWORD(v26);
        v24 = &v25[HIDWORD(v26)];
        v48 = v24;
        if ( v24 > v49[1] )
        {
          v15 = 160;
          LODWORD(v40) = 160;
          AslLogCallPrintf(
            1,
            (unsigned int)"PcaStoreSetValue",
            993,
            (unsigned int)"Failed to set stream position [%d]",
            v40);
          goto LABEL_16;
        }
        v51[0] = &v25[HIDWORD(v26)];
      }
      while ( (_DWORD)v46 == a3 );
      v28 = (void *)(v11 + 8);
      if ( v11 + 8 < v11 )
      {
        v15 = -1073741811;
        v23 = -1073741811;
LABEL_79:
        v16 = "Failed to write stream [%d]";
        v17 = 1011;
        goto LABEL_82;
      }
      if ( (unsigned __int64)v28 <= v10 )
        goto LABEL_77;
      if ( v11 + 4103 < v11 + 8 )
      {
        v23 = -1073741675;
      }
      else
      {
        if ( v9 )
        {
          v36 = RtlReAllocateHeap(HeapHandle, 0, v9, (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL);
        }
        else
        {
          v36 = RtlAllocateHeap(HeapHandle, 0, (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL);
          v52 = v36;
          if ( v36 )
          {
            memset_0(v36, 0, (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL);
            v36 = v52;
          }
        }
        v27 = v42;
        if ( v36 )
        {
          v9 = v36;
          v45[1] = v36;
          v10 = (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL;
          *(_QWORD *)&v44 = v10;
          v11 = (unsigned __int64)v45[0];
LABEL_77:
          *(_QWORD *)((char *)v9 + v11) = v26;
          if ( (unsigned __int64)v28 < v11 )
          {
            v45[0] = (PVOID)-1LL;
            v23 = -1073741675;
            v15 = -1073741675;
            goto LABEL_79;
          }
          v11 = (unsigned __int64)v28;
          v45[0] = v28;
          if ( v12 <= (unsigned __int64)v28 )
            v12 = (unsigned __int64)v28;
          *((_QWORD *)&v43 + 1) = v12;
          v23 = 0;
          goto LABEL_88;
        }
        v23 = -1073741801;
      }
      v11 = (unsigned __int64)v45[0];
LABEL_88:
      v15 = v23;
      if ( v23 )
        goto LABEL_79;
      v24 = v48;
      if ( v27 )
      {
        v35 = (char *)(v27 + v11);
        if ( v27 + v11 < v11 )
        {
          v15 = -1073741811;
          v23 = -1073741811;
LABEL_81:
          v16 = "Failed to write stream [%d]";
          v17 = 1017;
LABEL_82:
          LODWORD(v40) = v23;
LABEL_15:
          AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", v17, (_DWORD)v16, v40);
LABEL_16:
          v7 = 0;
          goto LABEL_17;
        }
        if ( (unsigned __int64)v35 > v10 )
        {
          if ( v35 + 4095 < v35 )
          {
            v23 = -1073741675;
            goto LABEL_96;
          }
          v37 = (unsigned __int64)(v35 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v9 )
          {
            v39 = RtlReAllocateHeap(HeapHandle, 0, v9, v37);
          }
          else
          {
            v38 = RtlAllocateHeap(HeapHandle, 0, v37);
            v39 = v38;
            if ( v38 )
              memset_0(v38, 0, v37);
          }
          if ( !v39 )
          {
            v23 = -1073741801;
            v11 = (unsigned __int64)v45[0];
            goto LABEL_96;
          }
          v9 = v39;
          v45[1] = v39;
          v10 = (unsigned __int64)(v35 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          *(_QWORD *)&v44 = v10;
          v11 = (unsigned __int64)v45[0];
        }
        memcpy_0((char *)v9 + v11, &v53[(_QWORD)P], v42);
        if ( (unsigned __int64)v35 < v11 )
        {
          v45[0] = (PVOID)-1LL;
          v23 = -1073741675;
          v15 = -1073741675;
          goto LABEL_81;
        }
        v11 = (unsigned __int64)v35;
        v45[0] = v35;
        if ( v12 <= (unsigned __int64)v35 )
          v12 = (unsigned __int64)v35;
        *((_QWORD *)&v43 + 1) = v12;
        v23 = 0;
LABEL_96:
        v15 = v23;
        if ( v23 )
          goto LABEL_81;
        v24 = v48;
      }
    }
  }
LABEL_7:
  v13 = Size;
  if ( Size && a4 )
  {
    v46 = __PAIR64__(Size, v5);
    v14 = v11 + 8;
    if ( v11 + 8 < v11 )
    {
      v15 = -1073741811;
LABEL_14:
      LODWORD(v40) = v15;
      v16 = "Failed to write stream [%d]";
      v17 = 1033;
      goto LABEL_15;
    }
    if ( v14 > v10 )
    {
      if ( v11 + 4103 < v11 + 8 )
        goto LABEL_13;
      v10 = (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL;
      if ( v9 )
      {
        v30 = RtlReAllocateHeap(ProcessHeap, 0, v9, v10);
      }
      else
      {
        v29 = RtlAllocateHeap(ProcessHeap, 0, v10);
        v30 = v29;
        if ( v29 )
          memset_0(v29, 0, v10);
      }
      if ( !v30 )
      {
        v15 = -1073741801;
        goto LABEL_14;
      }
      v9 = v30;
      v45[1] = v30;
      *(_QWORD *)&v44 = (v11 + 4103) & 0xFFFFFFFFFFFFF000uLL;
      v13 = Size;
    }
    *(_QWORD *)((char *)v9 + v11) = v46;
    if ( v14 >= v11 )
    {
      v45[0] = (PVOID)(v11 + 8);
      if ( v12 <= v14 )
        v12 = v11 + 8;
      *((_QWORD *)&v43 + 1) = v12;
      v22 = (char *)(v14 + v13);
      if ( v14 + v13 < v14 )
      {
        v15 = -1073741811;
LABEL_64:
        LODWORD(v40) = v15;
        AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 1039, (unsigned int)"Failed to write stream [%d]", v40);
        goto LABEL_16;
      }
      if ( (unsigned __int64)v22 > v10 )
      {
        if ( v22 + 4095 < v22 )
          goto LABEL_63;
        v10 = (unsigned __int64)(v22 + 4095) & 0xFFFFFFFFFFFFF000uLL;
        if ( v9 )
        {
          v34 = RtlReAllocateHeap(HeapHandle, 0, v9, v10);
        }
        else
        {
          v33 = RtlAllocateHeap(HeapHandle, 0, v10);
          v34 = v33;
          if ( v33 )
            memset_0(v33, 0, v10);
        }
        if ( !v34 )
        {
          v15 = -1073741801;
          goto LABEL_64;
        }
        v9 = v34;
        v45[1] = v34;
        *(_QWORD *)&v44 = (unsigned __int64)(v22 + 4095) & 0xFFFFFFFFFFFFF000uLL;
        v13 = Size;
      }
      memcpy_0((char *)v9 + v14, a4, v13);
      if ( (unsigned __int64)v22 < v14 )
      {
        v45[0] = (PVOID)-1LL;
LABEL_63:
        v15 = -1073741675;
        goto LABEL_64;
      }
      v45[0] = v22;
      if ( v12 <= (unsigned __int64)v22 )
        v12 = (unsigned __int64)v22;
      *((_QWORD *)&v43 + 1) = v12;
      goto LABEL_30;
    }
    v45[0] = (PVOID)-1LL;
LABEL_13:
    v15 = -1073741675;
    goto LABEL_14;
  }
LABEL_30:
  if ( v12 < 0xC )
  {
    v15 = 160;
    LODWORD(v40) = 160;
    AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 1052, (unsigned int)"Failed to compute checksum [%d]", v40);
    goto LABEL_16;
  }
  v19 = RtlComputeCrc32(0, (PUCHAR)v9 + 12, 0);
  v15 = 8;
  v45[0] = (PVOID)8;
  if ( v10 < 0xC )
  {
    if ( v9 )
    {
      v32 = RtlReAllocateHeap(HeapHandle, 0, v9, 0x1000u);
    }
    else
    {
      v31 = RtlAllocateHeap(HeapHandle, 0, 0x1000u);
      v32 = v31;
      if ( v31 )
        memset_0(v31, 0, 0x1000u);
    }
    if ( !v32 )
    {
      v15 = -1073741801;
      LODWORD(v40) = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 1064, (unsigned int)"Failed to compute checksum [%d]", v40);
      goto LABEL_16;
    }
    v9 = v32;
    v45[1] = v32;
    *(_QWORD *)&v44 = 4096;
  }
  v9[2] = v19;
  v45[0] = (PVOID)12;
  if ( v12 <= 0xC )
    v12 = 12;
  *((_QWORD *)&v43 + 1) = v12;
  v20 = PcaStreamAlloc((struct RtlMemoryStream *)&v43);
  v7 = v20;
  if ( v20 )
  {
    v21 = PcapStoreSetValueBinary(*a1, a2, v20, v12);
    v15 = v21;
    if ( v21 )
    {
      LODWORD(v40) = v21;
      AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 1084, (unsigned int)"Failed to write to registry [%d]", v40);
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"PcaStoreSetValue", 1075, (unsigned int)"Out of memory");
  }
LABEL_17:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  ProcessHeap = HeapHandle;
LABEL_22:
  if ( v9 )
    RtlFreeHeap(ProcessHeap, 0, v9);
  if ( v51[1] )
    RtlFreeHeap(v49[0], 0, v51[1]);
  return v15;
}

```

## disassembly

```asm
0x1800085b8  mov     rax, rsp
0x1800085bb  mov     [rax+20h], r9
0x1800085bf  mov     [rax+18h], r8d
0x1800085c3  mov     [rax+10h], rdx
0x1800085c7  mov     [rax+8], rcx
0x1800085cb  push    rbp
0x1800085cc  push    rbx
0x1800085cd  push    rsi
0x1800085ce  push    rdi
0x1800085cf  push    r12
0x1800085d1  push    r13
0x1800085d3  push    r14
0x1800085d5  push    r15
0x1800085d7  lea     rbp, [rax-57h]
0x1800085db  sub     rsp, 0D8h
0x1800085e2  mov     ebx, r8d
0x1800085e5  xor     edi, edi
0x1800085e7  mov     [rsp+110h+var_D0], rdi
0x1800085ec  xorps   xmm0, xmm0
0x1800085ef  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x1800085f3  movups  [rbp+4Fh+var_70], xmm0
0x1800085f7  movups  xmmword ptr [rbp+4Fh+var_60], xmm0
0x1800085fb  mov     rax, gs:60h
0x180008604  mov     r10, [rax+30h]
0x180008608  mov     [rbp+4Fh+var_80], r10
0x18000860c  mov     r14d, 1000h
0x180008612  mov     qword ptr [rbp+4Fh+var_70+8], r14
0x180008616  movups  [rbp+4Fh+var_C8], xmm0
0x18000861a  movups  [rbp+4Fh+var_B8], xmm0
0x18000861e  movups  xmmword ptr [rbp+4Fh+var_A8], xmm0
0x180008622  mov     rax, gs:60h
0x18000862b  mov     r15, [rax+30h]
0x18000862f  mov     [rsp+110h+HeapHandle], r15
0x180008634  mov     qword ptr [rbp+4Fh+var_C8], r15
0x180008638  mov     qword ptr [rbp+4Fh+var_B8+8], r14
0x18000863c  mov     [rbp+4Fh+var_98], rdi
0x180008640  mov     [rbp+4Fh+P], rdi
0x180008644  mov     esi, edi
0x180008646  mov     [rsp+110h+var_D8], rdi
0x18000864b  test    rdx, rdx
0x18000864e  jz      loc_180008714
0x180008654  cmp     [rdx], di
0x180008657  jz      loc_180008714
0x18000865d  mov     r8d, r14d; Size
0x180008660  xor     edx, edx; Flags
0x180008662  mov     rcx, r15; HeapHandle
0x180008665  call    cs:__imp_RtlAllocateHeap
0x18000866b  mov     rdi, rax
0x18000866e  test    rax, rax
0x180008671  jz      loc_180008DD9
0x180008677  mov     r8d, r14d; Size
0x18000867a  xor     edx, edx; Val
0x18000867c  mov     rcx, rax; void *
0x18000867f  call    memset_0
0x180008684  mov     [rbp+4Fh+var_A8+8], rdi
0x180008688  mov     esi, r14d
0x18000868b  mov     qword ptr [rbp+4Fh+var_B8], r14
0x18000868f  mov     dword ptr [rdi], 50434153h
0x180008695  mov     r12d, 1
0x18000869b  mov     [rdi+4], r12
0x18000869f  lea     eax, [r12+0Bh]
0x1800086a4  mov     r13d, eax
0x1800086a7  mov     [rbp+4Fh+var_A8], rax
0x1800086ab  mov     r14, qword ptr [rbp+4Fh+var_C8+8]
0x1800086af  cmp     r14, rax
0x1800086b2  cmovbe  r14, rax
0x1800086b6  mov     qword ptr [rbp+4Fh+var_C8+8], r14
0x1800086ba  mov     [rsp+110h+var_F0], 0FFFFFFFFh
0x1800086c2  mov     r9, [rbp+4Fh+arg_8]
0x1800086c6  mov     r8, [rbp+4Fh+arg_0]
0x1800086ca  lea     rdx, [rsp+110h+var_D0]
0x1800086cf  lea     rcx, [rbp+4Fh+P]
0x1800086d3  call    ?PcaStoreGetValueAlloc@@YAKPEAPEAXPEA_K_KPEBGW4_PCA_SLOT_ID@@@Z; PcaStoreGetValueAlloc(void * *,unsigned __int64 *,unsigned __int64,ushort const *,_PCA_SLOT_ID)
0x1800086d8  xor     r8d, r8d
0x1800086db  test    eax, eax
0x1800086dd  jz      loc_1800088CB
0x1800086e3  mov     rdx, [rbp+4Fh+Size]
0x1800086e7  test    rdx, rdx
0x1800086ea  jz      loc_1800087E0
0x1800086f0  cmp     [rbp+4Fh+Src], r8
0x1800086f4  jz      loc_1800087E0
0x1800086fa  mov     dword ptr [rbp+4Fh+var_98], ebx
0x1800086fd  mov     dword ptr [rbp+4Fh+var_98+4], edx
0x180008700  lea     rbx, [r13+8]
0x180008704  cmp     rbx, r13
0x180008707  jnb     loc_180008888
0x18000870d  mov     ebx, 0C000000Dh
0x180008712  jmp     short loc_180008729
0x180008714  mov     ebx, edi
0x180008716  mov     rdi, [rbp+4Fh+var_A8+8]
0x18000871a  jmp     short loc_18000874E
0x18000871c  mov     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x180008724  mov     ebx, 0C0000095h
0x180008729  mov     [rsp+110h+var_F0], ebx
0x18000872d  lea     r9, aFailedToWriteS; "Failed to write stream [%d]"
0x180008734  mov     r8d, 409h
0x18000873a  lea     rdx, aPcastoresetval; "PcaStoreSetValue"
0x180008741  mov     ecx, r12d
0x180008744  call    AslLogCallPrintf
0x180008749  mov     rsi, [rsp+110h+var_D8]
0x18000874e  mov     rax, [rbp+4Fh+P]
0x180008752  test    rax, rax
0x180008755  jz      short loc_18000876F
0x180008757  mov     rcx, gs:60h
0x180008760  mov     r8, rax; P
0x180008763  xor     edx, edx; Flags
0x180008765  mov     rcx, [rcx+30h]; HeapHandle
0x180008769  call    cs:__imp_RtlFreeHeap
0x18000876f  test    rsi, rsi
0x180008772  jz      short loc_18000878C
0x180008774  mov     rcx, gs:60h
0x18000877d  mov     r8, rsi; P
0x180008780  xor     edx, edx; Flags
0x180008782  mov     rcx, [rcx+30h]; HeapHandle
0x180008786  call    cs:__imp_RtlFreeHeap
0x18000878c  mov     r15, [rsp+110h+HeapHandle]
0x180008791  test    rdi, rdi
0x180008794  jz      short loc_1800087A5
0x180008796  mov     r8, rdi; P
0x180008799  xor     edx, edx; Flags
0x18000879b  mov     rcx, r15; HeapHandle
0x18000879e  call    cs:__imp_RtlFreeHeap
0x1800087a4  nop
0x1800087a5  mov     r8, [rbp+4Fh+var_60+8]; P
0x1800087a9  test    r8, r8
0x1800087ac  jz      short loc_1800087BB
0x1800087ae  xor     edx, edx; Flags
0x1800087b0  mov     rcx, [rbp+4Fh+var_80]; HeapHandle
0x1800087b4  call    cs:__imp_RtlFreeHeap
0x1800087ba  nop
0x1800087bb  mov     eax, ebx
0x1800087bd  add     rsp, 0D8h
0x1800087c4  pop     r15
0x1800087c6  pop     r14
0x1800087c8  pop     r13
0x1800087ca  pop     r12
0x1800087cc  pop     rdi
0x1800087cd  pop     rsi
0x1800087ce  pop     rbx
0x1800087cf  pop     rbp
0x1800087d0  retn
0x1800087d1  mov     [rbp+4Fh+var_A8], r15
0x1800087d5  cmp     r14, r15
0x1800087d8  cmovbe  r14, r15
0x1800087dc  mov     qword ptr [rbp+4Fh+var_C8+8], r14
0x1800087e0  mov     r13d, 0Ch
0x1800087e6  cmp     r14, r13
0x1800087e9  jb      loc_180008D7E
0x1800087ef  lea     rdx, [rdi+0Ch]; Buffer
0x1800087f3  xor     r8d, r8d; Length
0x1800087f6  xor     ecx, ecx; InitialCrc
0x1800087f8  call    cs:__imp_RtlComputeCrc32
0x1800087fe  mov     r15d, eax
0x180008801  lea     ebx, [r13-4]
0x180008805  cmp     r14, rbx
0x180008808  jb      loc_180008CF6
0x18000880e  mov     [rbp+4Fh+var_A8], rbx
0x180008812  cmp     rsi, r13
0x180008815  jb      loc_180008A2B
0x18000881b  mov     [rdi+8], r15d
0x18000881f  mov     [rbp+4Fh+var_A8], r13
0x180008823  cmp     r14, r13
0x180008826  cmovbe  r14, r13
0x18000882a  mov     qword ptr [rbp+4Fh+var_C8+8], r14
0x18000882e  lea     rcx, [rbp+4Fh+var_C8]; struct RtlMemoryStream *
0x180008832  call    ?PcaStreamAlloc@@YAPEAXAEAVRtlMemoryStream@@@Z; PcaStreamAlloc(RtlMemoryStream &)
0x180008837  mov     rsi, rax
0x18000883a  test    rax, rax
0x18000883d  jz      loc_180008DB8
0x180008843  mov     r9, r14; unsigned __int64
0x180008846  mov     r8, rax; void *
0x180008849  mov     rdx, [rbp+4Fh+arg_8]; unsigned __int16 *
0x18000884d  mov     rax, [rbp+4Fh+arg_0]
0x180008851  mov     rcx, [rax]; HKEY
0x180008854  call    ?PcapStoreSetValueBinary@@YAKPEAUHKEY__@@PEBGPEAX_K@Z; PcapStoreSetValueBinary(HKEY__ *,ushort const *,void *,unsigned __int64)
0x180008859  mov     ebx, eax
0x18000885b  test    eax, eax
0x18000885d  jz      loc_18000874E
0x180008863  mov     [rsp+110h+var_F0], eax
0x180008867  lea     r9, aFailedToWriteT_5; "Failed to write to registry [%d]"
0x18000886e  mov     r8d, 43Ch
0x180008874  lea     rdx, aPcastoresetval; "PcaStoreSetValue"
0x18000887b  mov     ecx, r12d
0x18000887e  call    AslLogCallPrintf
0x180008883  jmp     loc_18000874E
0x180008888  cmp     rbx, rsi
0x18000888b  ja      loc_180008986
0x180008891  mov     rcx, rsi
0x180008894  mov     rax, [rbp+4Fh+var_98]
0x180008898  mov     [rdi+r13], rax
0x18000889c  cmp     rbx, r13
0x18000889f  jb      loc_18000871C
0x1800088a5  mov     [rbp+4Fh+var_A8], rbx
0x1800088a9  cmp     r14, rbx
0x1800088ac  cmovbe  r14, rbx
0x1800088b0  mov     qword ptr [rbp+4Fh+var_C8+8], r14
0x1800088b4  lea     r15, [rbx+rdx]
0x1800088b8  cmp     r15, rbx
0x1800088bb  jnb     loc_1800089E6
0x1800088c1  mov     ebx, 0C000000Dh
0x1800088c6  jmp     loc_180008A15
0x1800088cb  mov     r8, [rsp+110h+var_D0]; unsigned __int64
0x1800088d0  mov     rdx, [rbp+4Fh+P]; void *
0x1800088d4  lea     rcx, [rbp+4Fh+var_80]; this
0x1800088d8  call    ?InitializeFromBuffer@RtlMemoryStream@@QEAAKQEAX_K@Z; RtlMemoryStream::InitializeFromBuffer(void * const,unsigned __int64)
0x1800088dd  mov     ebx, eax
0x1800088df  xor     r8d, r8d
0x1800088e2  test    eax, eax
0x1800088e4  jnz     loc_180008D25
0x1800088ea  mov     rax, [rbp+4Fh+var_60]
0x1800088ee  cmp     rax, [rbp+4Fh+var_80+8]
0x1800088f2  jnb     loc_180008979
0x1800088f8  lea     rdx, [rax+8]
0x1800088fc  mov     [rbp+4Fh+var_48], rdx
0x180008900  cmp     rdx, rax
0x180008903  jb      short loc_18000895E
0x180008905  cmp     rdx, [rbp+4Fh+var_80+8]
0x180008909  ja      short loc_18000895E
0x18000890b  mov     rbx, [rbp+4Fh+var_60+8]
0x18000890f  mov     rbx, [rbx+rax]
0x180008913  mov     [rbp+4Fh+var_98], rbx
0x180008917  mov     [rbp+4Fh+var_60], rdx
0x18000891b  mov     rcx, rbx
0x18000891e  shr     rcx, 20h
0x180008922  mov     [rsp+110h+var_D0], rcx
0x180008927  lea     rax, [rdx+rcx]
0x18000892b  mov     [rbp+4Fh+var_88], rax
0x18000892f  cmp     rax, [rbp+4Fh+var_80+8]
0x180008933  ja      loc_180008D4F
0x180008939  mov     [rbp+4Fh+var_60], rax
0x18000893d  mov     edx, [rbp+4Fh+arg_10]
0x180008940  cmp     dword ptr [rbp+4Fh+var_98], edx
0x180008943  jz      short loc_1800088EE
0x180008945  lea     r15, [r13+8]
0x180008949  cmp     r15, r13
0x18000894c  jnb     loc_180008ADC
0x180008952  mov     ebx, 0C000000Dh
0x180008957  mov     eax, ebx
0x180008959  jmp     loc_180008AFF
0x18000895e  mov     ebx, 0A0h
0x180008963  mov     [rsp+110h+var_F0], ebx
0x180008967  lea     r9, aFailedToReadSt_0; "Failed to read stream [%d]"
0x18000896e  mov     r8d, 3D9h
0x180008974  jmp     loc_18000873A
0x180008979  mov     r15, [rsp+110h+HeapHandle]
0x18000897e  mov     ebx, [rbp+4Fh+arg_10]
0x180008981  jmp     loc_1800086E3
0x180008986  lea     rsi, [rbx+0FFFh]
0x18000898d  cmp     rsi, rbx
0x180008990  jb      loc_180008724
0x180008996  and     rsi, 0FFFFFFFFFFFFF000h
0x18000899d  xor     edx, edx; Flags
0x18000899f  mov     rcx, r15; Heap
0x1800089a2  test    rdi, rdi
0x1800089a5  jnz     loc_180008CCE
0x1800089ab  mov     r8, rsi; Size
0x1800089ae  call    cs:__imp_RtlAllocateHeap
0x1800089b4  mov     r15, rax
0x1800089b7  test    rax, rax
0x1800089ba  jz      short loc_1800089C9
0x1800089bc  mov     r8, rsi; Size
0x1800089bf  xor     edx, edx; Val
0x1800089c1  mov     rcx, rax; void *
0x1800089c4  call    memset_0
0x1800089c9  test    r15, r15
0x1800089cc  jz      loc_180008D6A
0x1800089d2  mov     rdi, r15
0x1800089d5  mov     [rbp+4Fh+var_A8+8], r15
0x1800089d9  mov     qword ptr [rbp+4Fh+var_B8], rsi
0x1800089dd  mov     rdx, [rbp+4Fh+Size]
0x1800089e1  jmp     loc_180008891
0x1800089e6  cmp     r15, rcx
0x1800089e9  ja      loc_180008A7E
0x1800089ef  lea     rcx, [rdi+rbx]; void *
0x1800089f3  mov     r8, rdx; Size
0x1800089f6  mov     rdx, [rbp+4Fh+Src]; Src
0x1800089fa  call    memcpy_0
0x1800089ff  cmp     r15, rbx
0x180008a02  jnb     loc_1800087D1
0x180008a08  mov     [rbp+4Fh+var_A8], 0FFFFFFFFFFFFFFFFh
0x180008a10  mov     ebx, 0C0000095h
0x180008a15  mov     [rsp+110h+var_F0], ebx
0x180008a19  lea     r9, aFailedToWriteS; "Failed to write stream [%d]"
0x180008a20  mov     r8d, 40Fh
0x180008a26  jmp     loc_18000873A
0x180008a2b  mov     r13d, 1000h
0x180008a31  xor     edx, edx; Flags
0x180008a33  mov     rcx, [rsp+110h+HeapHandle]; Heap
0x180008a38  test    rdi, rdi
0x180008a3b  jnz     loc_180008D11
0x180008a41  mov     r8d, r13d; Size
0x180008a44  call    cs:__imp_RtlAllocateHeap
0x180008a4a  mov     rsi, rax
0x180008a4d  test    rax, rax
0x180008a50  jz      short loc_180008A5F
0x180008a52  mov     r8d, r13d; Size
0x180008a55  xor     edx, edx; Val
0x180008a57  mov     rcx, rax; void *
0x180008a5a  call    memset_0
0x180008a5f  test    rsi, rsi
  ... truncated ...
```
