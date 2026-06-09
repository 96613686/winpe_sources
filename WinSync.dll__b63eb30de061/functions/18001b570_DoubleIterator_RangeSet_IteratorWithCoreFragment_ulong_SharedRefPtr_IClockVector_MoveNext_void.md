# DoubleIterator<RangeSet::IteratorWithCoreFragment,ulong,SharedRefPtr<IClockVector>>::MoveNext(void)

- ea: `0x18001b570`
- end: `0x18001bb0c`
- name: `?MoveNext@?$DoubleIterator@VIteratorWithCoreFragment@RangeSet@@KV?$SharedRefPtr@UIClockVector@@@@@@QEAAJXZ`
- size: `1436`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180013950`
- `0x18008f538`

## callees

- `0x180007584`
- `0x18000f810`
- `0x180011f60`
- `0x18001a1f0`
- `0x18001b354`
- `0x18001b570`
- `0x18001bb20`
- `0x18001bd6c`
- `0x18001bde4`
- `0x18001be90`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b66e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b66e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b68d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b68d`

## pseudocode

```c
__int64 __fastcall DoubleIterator<RangeSet::IteratorWithCoreFragment,unsigned long,SharedRefPtr<IClockVector>>::MoveNext(
        __int64 a1)
{
  int v2; // eax
  unsigned int v3; // edi
  int v4; // eax
  __int64 *v5; // r14
  __int64 v6; // rcx
  volatile signed __int32 *v7; // rax
  __int64 v8; // r15
  size_t v9; // rdx
  _DWORD *v10; // r12
  int v11; // esi
  int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rbp
  __int64 v16; // r8
  unsigned int *v17; // rcx
  int v18; // eax
  unsigned int *v19; // r9
  int v20; // r10d
  int v21; // r12d
  unsigned __int16 *v22; // r14
  _WORD *v23; // r11
  unsigned int *v24; // r11
  unsigned int v25; // edx
  unsigned int v26; // r8d
  size_t v27; // r8
  void *v28; // rdx
  __int64 *v29; // rbx
  __int64 v30; // rcx
  int v32; // ecx
  __int64 *v33; // rsi
  unsigned int v34; // edx
  unsigned int v35; // r8d
  __int64 v36; // rdi
  __int64 v37; // rbp
  volatile signed __int32 *v38; // rcx
  volatile signed __int32 *v39; // rax
  int v40; // ecx
  __int64 v41; // rax
  unsigned int v42; // eax
  unsigned __int8 *v43; // rsi
  unsigned __int8 *v44; // rcx
  unsigned __int8 *v45; // rdx
  unsigned __int8 *v46; // r9
  int v47; // r8d
  int v48; // r10d
  unsigned int v49; // eax
  _BYTE v50[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v51; // [rsp+34h] [rbp-44h]
  __int64 v52; // [rsp+38h] [rbp-40h]
  LPVOID lpMem; // [rsp+80h] [rbp+8h] BYREF
  size_t Size; // [rsp+88h] [rbp+10h]
  void *Src; // [rsp+90h] [rbp+18h]

  v2 = *(_DWORD *)(a1 + 68);
  if ( *(_DWORD *)(a1 + 64) )
  {
    v3 = 0;
    if ( v2 )
      return v3;
    v4 = *(unsigned __int16 *)(a1 + 76);
    v5 = (__int64 *)(a1 + 56);
    v6 = *(_QWORD *)(a1 + 56);
    LODWORD(lpMem) = v4;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *v5 = 0;
    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *, __int64 *))(**(_QWORD **)(a1 + 96) + 32LL))(
           *(_QWORD *)(a1 + 96),
           *(_QWORD *)(a1 + 112),
           &lpMem,
           v5);
    if ( !v3 )
    {
      if ( (*(_DWORD *)(a1 + 28) & 0x20000) == 0 )
      {
        v7 = *(volatile signed __int32 **)(a1 + 32);
        if ( v7 )
        {
          if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 )
            SeFree(*(void **)(a1 + 32));
        }
      }
      *(_DWORD *)(a1 + 28) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v8 = *(_QWORD *)(a1 + 104);
      if ( v8 )
      {
        v40 = *(_DWORD *)(v8 + 24) & 1;
        v51 = *(unsigned __int16 *)(v8 + 28);
        v3 = 0;
        v41 = *(_QWORD *)(a1 + 112);
        v51 = v51 & 0xFFFEFFFF | ((v40 | 2) << 16);
        v52 = v41;
        if ( !(unsigned __int8)HashTable<SyncId,int,DefaultHashTableContext>::LookupKey(v8, v50) )
        {
          v3 = SyncId::Promote((SyncId *)v50);
          if ( !v3 )
          {
            LODWORD(lpMem) = 1;
            v3 = HashTable<SyncId,int,DefaultHashTableContext>::AddItem(v8, v50, &lpMem);
            if ( !v3 )
              SyncId::operator=(a1 + 24, (__int64)v50);
          }
        }
        SyncId::~SyncId((SyncId *)v50);
      }
      else
      {
        Src = *(void **)(a1 + 112);
        ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
        Size = v9;
        v10 = HeapAlloc(hHeap, 0, v9 + 7);
        if ( lpMem )
          HeapFree(hHeap, 0, lpMem);
        if ( v10 )
        {
          v27 = Size;
          v3 = 0;
          v28 = Src;
          *(_QWORD *)(a1 + 32) = v10;
          *v10 = 1;
          memcpy_0((void *)(*(_QWORD *)(a1 + 32) + 4LL), v28, v27);
          *(_DWORD *)(a1 + 28) &= ~0x20000u;
          *(_DWORD *)(a1 + 28) ^= (*(_DWORD *)(a1 + 28) ^ (*(_DWORD *)(a1 + 72) << 16)) & 0x10000;
          *(_WORD *)(a1 + 28) = *(_WORD *)(a1 + 76);
        }
        else
        {
          v3 = -2147024882;
          SyncId::~SyncId((SyncId *)(a1 + 24));
          *(_DWORD *)(a1 + 28) = 0;
          *(_QWORD *)(a1 + 32) = 0;
        }
      }
    }
    if ( !v3 )
    {
      v29 = (__int64 *)(a1 + 48);
      if ( v29 == v5 )
        return v3;
      if ( *v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)*v29 + 16LL))(*v29);
      v30 = *v5;
      goto LABEL_38;
    }
    if ( v3 != 1 )
      return v3;
    *(_DWORD *)(a1 + 68) = 1;
    return 0;
  }
  if ( v2 )
  {
    v49 = RangeSet::IteratorWithCoreFragment::MoveLeft(
            (RangeSet::IteratorWithCoreFragment *)a1,
            (struct SyncId *)(a1 + 8),
            (unsigned int *)(a1 + 44));
    v3 = v49;
    if ( !v49 )
    {
      *(_DWORD *)(a1 + 40) = *(_DWORD *)(a1 + 44);
      return v3;
    }
    if ( v49 == 1 )
    {
      *(_DWORD *)(a1 + 64) = 1;
      return 0;
    }
  }
  else
  {
    v11 = 0;
    v12 = 1;
    if ( *(int *)a1 <= 0 )
    {
      ++*(_DWORD *)(a1 + 88);
      v13 = *(_QWORD *)(a1 + 80);
      v14 = *(unsigned int *)(a1 + 88);
      if ( (unsigned int)v14 < *(_DWORD *)(v13 + 8) )
      {
        v36 = a1 + 8;
        v37 = *(_QWORD *)(v13 + 24) + 24 * v14;
        if ( a1 + 8 != v37 )
        {
          if ( (*(_DWORD *)(a1 + 12) & 0x20000) == 0 )
          {
            v38 = *(volatile signed __int32 **)(a1 + 16);
            if ( v38 )
            {
              if ( _InterlockedExchangeAdd(v38, 0xFFFFFFFF) == 1 )
              {
                SeFree(*(void **)(v36 + 8));
                *(_QWORD *)(v36 + 8) = 0;
              }
            }
          }
          *(_DWORD *)(v36 + 4) = *(_DWORD *)(v37 + 4);
          v39 = *(volatile signed __int32 **)(v37 + 8);
          *(_QWORD *)(v36 + 8) = v39;
          if ( v39 )
            _InterlockedIncrement(v39);
        }
        *(_DWORD *)(a1 + 44) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL)
                                         + 24LL * *(unsigned int *)(a1 + 88)
                                         + 16);
      }
      else
      {
        *(_DWORD *)(a1 + 64) = 1;
      }
    }
    v3 = 0;
    if ( *(int *)a1 >= 0 )
    {
      v42 = RangeSet::IteratorWithCoreFragment::MoveRight(a1, a1 + 24, a1 + 56);
      v3 = v42;
      if ( v42 == 1 )
      {
        v3 = 0;
        *(_DWORD *)(a1 + 68) = 1;
      }
      else if ( v42 )
      {
        return v3;
      }
    }
    if ( *(_DWORD *)(a1 + 64) )
    {
      if ( *(_DWORD *)(a1 + 68) )
        return v3;
      *(_DWORD *)a1 = 1;
    }
    else if ( *(_DWORD *)(a1 + 68) )
    {
      *(_DWORD *)a1 = -1;
    }
    else
    {
      v15 = *(_QWORD *)(a1 + 16);
      v16 = *(_QWORD *)(a1 + 32);
      v17 = (unsigned int *)v15;
      v18 = *(_DWORD *)(a1 + 12);
      v19 = (unsigned int *)v16;
      v20 = *(_DWORD *)(a1 + 28);
      v21 = v18 & 0x20000;
      v22 = (unsigned __int16 *)(v15 + 4);
      v23 = (_WORD *)(v16 + 4);
      if ( (v18 & 0x20000) == 0 )
        v17 = (unsigned int *)(v15 + 4);
      if ( (v20 & 0x20000) == 0 )
        v19 = (unsigned int *)(v16 + 4);
      if ( v17 != v19 )
      {
        if ( (v18 & 0x10000) != 0 )
        {
          if ( v21 )
            v22 = *(unsigned __int16 **)(a1 + 16);
          v43 = (unsigned __int8 *)v17 + *v22;
          if ( (v20 & 0x10000) != 0 )
          {
            if ( (v20 & 0x20000) != 0 )
              v23 = *(_WORD **)(a1 + 32);
            LOWORD(v20) = *v23;
          }
          v44 = (unsigned __int8 *)v17 + 2;
          v45 = (unsigned __int8 *)v19 + (unsigned __int16)v20;
          v46 = (unsigned __int8 *)v19 + 2;
          while ( v44 < v43 )
          {
            if ( v46 >= v45 )
              goto LABEL_49;
            v47 = *v44;
            v48 = *v46;
            if ( v47 != v48 )
            {
              if ( (unsigned __int8)v47 <= (unsigned __int8)v48 )
                v12 = -1;
LABEL_49:
              v11 = v12;
              goto LABEL_50;
            }
            ++v44;
            ++v46;
          }
          v11 = -(v46 < v45);
        }
        else
        {
          v24 = &v17[(unsigned __int64)(unsigned __int16)v18 >> 2];
          while ( v17 < v24 )
          {
            v25 = *v19;
            v26 = *v17;
            if ( *v17 != *v19 )
            {
              if ( (unsigned __int8)v26 > (unsigned __int8)v25 )
                goto LABEL_49;
              if ( (unsigned __int8)v26 < (unsigned __int8)v25 || BYTE1(v26) < BYTE1(v25) )
                goto LABEL_79;
              if ( BYTE1(v26) > BYTE1(v25) || BYTE2(v26) > BYTE2(v25) )
                goto LABEL_49;
              if ( BYTE2(v26) < BYTE2(v25) )
                goto LABEL_79;
              v34 = HIBYTE(v25);
              v35 = HIBYTE(v26);
              if ( (unsigned __int8)v35 > (unsigned __int8)v34 )
                goto LABEL_49;
              if ( (unsigned __int8)v35 < (unsigned __int8)v34 )
              {
LABEL_79:
                v11 = -1;
                goto LABEL_50;
              }
            }
            ++v17;
            ++v19;
          }
          if ( (v18 & 3) != 0 )
          {
            if ( v21 )
              v22 = *(unsigned __int16 **)(a1 + 16);
            while ( v17 < (unsigned int *)((char *)v22 + (unsigned __int16)v18) )
            {
              if ( *(_BYTE *)v17 > *(_BYTE *)v19 )
                goto LABEL_49;
              if ( *(_BYTE *)v17 < *(_BYTE *)v19 )
                goto LABEL_79;
              v17 = (unsigned int *)((char *)v17 + 1);
              v19 = (unsigned int *)((char *)v19 + 1);
            }
          }
        }
      }
LABEL_50:
      *(_DWORD *)a1 = v11;
    }
    v32 = *(_DWORD *)a1;
    if ( *(int *)a1 <= 0 )
      *(_DWORD *)(a1 + 40) = *(_DWORD *)(a1 + 44);
    if ( v32 >= 0 )
    {
      v33 = (__int64 *)(a1 + 56);
      v29 = (__int64 *)(a1 + 48);
      if ( v29 != v33 )
      {
        if ( *v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)*v29 + 16LL))(*v29);
        v30 = *v33;
LABEL_38:
        *v29 = v30;
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001b570  mov     [rsp+arg_18], rbx
0x18001b575  push    rbp
0x18001b576  push    rsi
0x18001b577  push    rdi
0x18001b578  push    r12
0x18001b57a  push    r13
0x18001b57c  push    r14
0x18001b57e  push    r15
0x18001b580  sub     rsp, 40h
0x18001b584  cmp     dword ptr [rcx+40h], 0
0x18001b588  mov     rbx, rcx
0x18001b58b  mov     eax, [rcx+44h]
0x18001b58e  jz      loc_18001B6B6
0x18001b594  xor     esi, esi
0x18001b596  mov     edi, esi
0x18001b598  test    eax, eax
0x18001b59a  jnz     loc_18001B80A
0x18001b5a0  movzx   eax, word ptr [rcx+4Ch]
0x18001b5a4  lea     r14, [rcx+38h]
0x18001b5a8  mov     rcx, [rcx+38h]
0x18001b5ac  mov     dword ptr [rsp+78h+lpMem], eax
0x18001b5b3  test    rcx, rcx
0x18001b5b6  jz      short loc_18001B5C4
0x18001b5b8  mov     rax, [rcx]
0x18001b5bb  mov     rax, [rax+10h]
0x18001b5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c4  mov     [r14], rsi
0x18001b5c7  lea     r8, [rsp+78h+lpMem]
0x18001b5cf  mov     rcx, [rbx+60h]
0x18001b5d3  mov     r9, r14
0x18001b5d6  mov     rdx, [rbx+70h]
0x18001b5da  mov     rax, [rcx]
0x18001b5dd  mov     rax, [rax+20h]
0x18001b5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5e6  mov     edi, eax
0x18001b5e8  mov     r13d, 1
0x18001b5ee  test    eax, eax
0x18001b5f0  jnz     loc_18001B7C5
0x18001b5f6  test    dword ptr [rbx+1Ch], 20000h
0x18001b5fd  jnz     short loc_18001B61C
0x18001b5ff  mov     rax, [rbx+20h]
0x18001b603  test    rax, rax
0x18001b606  jz      short loc_18001B61C
0x18001b608  mov     r15d, 0FFFFFFFFh
0x18001b60e  lock xadd [rax], r15d
0x18001b613  cmp     r15d, r13d
0x18001b616  jz      loc_18001B9E6
0x18001b61c  mov     [rbx+1Ch], esi
0x18001b61f  mov     [rbx+20h], rsi
0x18001b623  mov     r15, [rbx+68h]
0x18001b627  test    r15, r15
0x18001b62a  jnz     loc_18001B93F
0x18001b630  mov     rax, [rbx+70h]
0x18001b634  mov     [rsp+78h+Src], rax
0x18001b63c  cmp     [rbx+48h], esi
0x18001b63f  jnz     loc_18001BAA6
0x18001b645  lea     rdx, [rbx+4Ch]
0x18001b649  movzx   edx, word ptr [rdx]
0x18001b64c  lea     rcx, [rsp+78h+lpMem]
0x18001b654  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18001b659  mov     rcx, cs:hHeap; hHeap
0x18001b660  lea     r8, [rdx+7]; dwBytes
0x18001b664  mov     [rsp+78h+Size], rdx
0x18001b66c  xor     edx, edx; dwFlags
0x18001b66e  call    cs:__imp_HeapAlloc
0x18001b674  mov     r8, [rsp+78h+lpMem]; lpMem
0x18001b67c  mov     r12, rax
0x18001b67f  test    r8, r8
0x18001b682  jz      short loc_18001B693
0x18001b684  mov     rcx, cs:hHeap; hHeap
0x18001b68b  xor     edx, edx; dwFlags
0x18001b68d  call    cs:__imp_HeapFree
0x18001b693  test    r12, r12
0x18001b696  jnz     loc_18001B77D
0x18001b69c  lea     rcx, [rbx+18h]; this
0x18001b6a0  mov     edi, 8007000Eh
0x18001b6a5  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18001b6aa  mov     [rbx+1Ch], esi
0x18001b6ad  mov     [rbx+20h], rsi
0x18001b6b1  jmp     loc_18001B7C5
0x18001b6b6  test    eax, eax
0x18001b6b8  jnz     loc_18001BAD0
0x18001b6be  xor     esi, esi
0x18001b6c0  mov     r13d, 1
0x18001b6c6  mov     r15d, 0FFFFFFFFh
0x18001b6cc  cmp     [rcx], esi
0x18001b6ce  jg      short loc_18001B6E7
0x18001b6d0  inc     dword ptr [rcx+58h]
0x18001b6d3  mov     rdx, [rcx+50h]
0x18001b6d7  mov     eax, [rcx+58h]
0x18001b6da  cmp     eax, [rdx+8]
0x18001b6dd  jb      loc_18001B8D7
0x18001b6e3  mov     [rcx+40h], r13d
0x18001b6e7  mov     edi, esi
0x18001b6e9  cmp     [rbx], esi
0x18001b6eb  jge     loc_18001B9C2
0x18001b6f1  cmp     [rbx+40h], esi
0x18001b6f4  jnz     loc_18001B9B1
0x18001b6fa  cmp     [rbx+44h], esi
0x18001b6fd  jnz     loc_18001B99B
0x18001b703  mov     rbp, [rbx+10h]
0x18001b707  mov     r8, [rbx+20h]
0x18001b70b  mov     rcx, rbp
0x18001b70e  mov     eax, [rbx+0Ch]
0x18001b711  mov     r9, r8
0x18001b714  mov     r10d, [rbx+1Ch]
0x18001b718  mov     r12d, eax
0x18001b71b  and     r12d, 20000h
0x18001b722  lea     r14, [rbp+4]
0x18001b726  mov     edx, r10d
0x18001b729  lea     r11, [r8+4]
0x18001b72d  cmovz   rcx, r14
0x18001b731  and     edx, 20000h
0x18001b737  cmovz   r9, r11
0x18001b73b  cmp     rcx, r9
0x18001b73e  jz      loc_18001B84A
0x18001b744  bt      eax, 10h
0x18001b748  jb      loc_18001BA5F
0x18001b74e  movzx   ebp, ax
0x18001b751  mov     eax, ebp
0x18001b753  shr     rax, 2
0x18001b757  lea     r11, [rcx+rax*4]
0x18001b75b  cmp     rcx, r11
0x18001b75e  jnb     loc_18001B824
0x18001b764  mov     edx, [r9]
0x18001b767  mov     r8d, [rcx]
0x18001b76a  cmp     r8d, edx
0x18001b76d  jnz     loc_18001B883
0x18001b773  add     rcx, 4
0x18001b777  add     r9, 4
0x18001b77b  jmp     short loc_18001B75B
0x18001b77d  mov     r8, [rsp+78h+Size]; Size
0x18001b785  mov     edi, esi
0x18001b787  mov     rdx, [rsp+78h+Src]; Src
0x18001b78f  mov     [rbx+20h], r12
0x18001b793  mov     [r12], r13d
0x18001b797  mov     rcx, [rbx+20h]
0x18001b79b  add     rcx, 4; void *
0x18001b79f  call    memcpy_0
0x18001b7a4  and     dword ptr [rbx+1Ch], 0FFFDFFFFh
0x18001b7ab  mov     ecx, [rbx+48h]
0x18001b7ae  shl     ecx, 10h
0x18001b7b1  xor     ecx, [rbx+1Ch]
0x18001b7b4  and     ecx, 10000h
0x18001b7ba  xor     [rbx+1Ch], ecx
0x18001b7bd  movzx   eax, word ptr [rbx+4Ch]
0x18001b7c1  mov     [rbx+1Ch], ax
0x18001b7c5  test    edi, edi
0x18001b7c7  jnz     short loc_18001B7FF
0x18001b7c9  add     rbx, 30h ; '0'
0x18001b7cd  cmp     rbx, r14
0x18001b7d0  jz      short loc_18001B80A
0x18001b7d2  mov     rcx, [rbx]
0x18001b7d5  test    rcx, rcx
0x18001b7d8  jz      short loc_18001B7E6
0x18001b7da  mov     rax, [rcx]
0x18001b7dd  mov     rax, [rax+10h]
0x18001b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7e6  mov     rcx, [r14]
0x18001b7e9  mov     [rbx], rcx
0x18001b7ec  test    rcx, rcx
0x18001b7ef  jz      short loc_18001B80A
0x18001b7f1  mov     rax, [rcx]
0x18001b7f4  mov     rax, [rax+8]
0x18001b7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7fd  jmp     short loc_18001B80A
0x18001b7ff  cmp     edi, r13d
0x18001b802  jnz     short loc_18001B80A
0x18001b804  mov     [rbx+44h], r13d
0x18001b808  mov     edi, esi
0x18001b80a  mov     rbx, [rsp+78h+arg_18]
0x18001b812  mov     eax, edi
0x18001b814  add     rsp, 40h
0x18001b818  pop     r15
0x18001b81a  pop     r14
0x18001b81c  pop     r13
0x18001b81e  pop     r12
0x18001b820  pop     rdi
0x18001b821  pop     rsi
0x18001b822  pop     rbp
0x18001b823  retn
0x18001b824  test    bpl, 3
0x18001b828  jz      short loc_18001B84A
0x18001b82a  test    r12d, r12d
0x18001b82d  cmovnz  r14, [rbx+10h]
0x18001b832  lea     r8, [r14+rbp]
0x18001b836  cmp     rcx, r8
0x18001b839  jnb     short loc_18001B84A
0x18001b83b  movzx   eax, byte ptr [r9]
0x18001b83f  cmp     [rcx], al
0x18001b841  jbe     loc_18001B9A3
0x18001b847  mov     esi, r13d
0x18001b84a  mov     [rbx], esi
0x18001b84c  mov     ecx, [rbx]
0x18001b84e  test    ecx, ecx
0x18001b850  jg      short loc_18001B858
0x18001b852  mov     eax, [rbx+2Ch]
0x18001b855  mov     [rbx+28h], eax
0x18001b858  js      short loc_18001B80A
0x18001b85a  lea     rsi, [rbx+38h]
0x18001b85e  add     rbx, 30h ; '0'
0x18001b862  cmp     rbx, rsi
0x18001b865  jz      short loc_18001B80A
0x18001b867  mov     rcx, [rbx]
0x18001b86a  test    rcx, rcx
0x18001b86d  jz      short loc_18001B87B
0x18001b86f  mov     rax, [rcx]
0x18001b872  mov     rax, [rax+10h]
0x18001b876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b87b  mov     rcx, [rsi]
0x18001b87e  jmp     loc_18001B7E9
0x18001b883  cmp     r8b, dl
0x18001b886  ja      short loc_18001B847
0x18001b888  jb      loc_18001B9A9
0x18001b88e  mov     eax, edx
0x18001b890  mov     r10d, r8d
0x18001b893  shr     eax, 8
0x18001b896  shr     r10d, 8
0x18001b89a  cmp     r10b, al
0x18001b89d  jb      loc_18001B9A9
0x18001b8a3  ja      short loc_18001B847
0x18001b8a5  mov     eax, edx
0x18001b8a7  mov     r10d, r8d
0x18001b8aa  shr     eax, 10h
0x18001b8ad  shr     r10d, 10h
0x18001b8b1  cmp     r10b, al
0x18001b8b4  ja      short loc_18001B847
0x18001b8b6  jb      loc_18001B9A9
0x18001b8bc  shr     edx, 18h
0x18001b8bf  shr     r8d, 18h
0x18001b8c3  cmp     r8b, dl
0x18001b8c6  ja      loc_18001B847
0x18001b8cc  jnb     loc_18001B773
0x18001b8d2  jmp     loc_18001B9A9
0x18001b8d7  lea     rdi, [rcx+8]
0x18001b8db  lea     rcx, [rax+rax*2]
0x18001b8df  mov     rax, [rdx+18h]
0x18001b8e3  lea     rbp, [rax+rcx*8]
0x18001b8e7  cmp     rdi, rbp
0x18001b8ea  jz      short loc_18001B924
0x18001b8ec  test    dword ptr [rdi+4], 20000h
0x18001b8f3  jnz     short loc_18001B90E
0x18001b8f5  mov     rcx, [rdi+8]
0x18001b8f9  test    rcx, rcx
0x18001b8fc  jz      short loc_18001B90E
0x18001b8fe  mov     eax, r15d
0x18001b901  lock xadd [rcx], eax
0x18001b905  cmp     eax, r13d
0x18001b908  jz      loc_18001B9FF
0x18001b90e  mov     eax, [rbp+4]
0x18001b911  mov     [rdi+4], eax
0x18001b914  mov     rax, [rbp+8]
0x18001b918  mov     [rdi+8], rax
0x18001b91c  test    rax, rax
0x18001b91f  jz      short loc_18001B924
0x18001b921  lock inc dword ptr [rax]
0x18001b924  mov     eax, [rbx+58h]
0x18001b927  lea     rdx, [rax+rax*2]
0x18001b92b  mov     rax, [rbx+50h]
0x18001b92f  mov     rcx, [rax+18h]
0x18001b933  mov     eax, [rcx+rdx*8+10h]
0x18001b937  mov     [rbx+2Ch], eax
0x18001b93a  jmp     loc_18001B6E7
0x18001b93f  movzx   eax, word ptr [r15+1Ch]
0x18001b944  lea     r8, [rbx+18h]
0x18001b948  mov     ecx, [r15+18h]
0x18001b94c  lea     rdx, [rsp+78h+var_48]
0x18001b951  and     ecx, r13d
0x18001b954  mov     [rsp+78h+var_44], esi
0x18001b958  mov     word ptr [rsp+78h+var_44], ax
0x18001b95d  or      ecx, 2
0x18001b960  mov     eax, [rsp+78h+var_44]
0x18001b964  mov     edi, esi
0x18001b966  shl     ecx, 10h
0x18001b969  btr     eax, 10h
0x18001b96d  or      ecx, eax
0x18001b96f  mov     rax, [rbx+70h]
0x18001b973  mov     [rsp+78h+var_44], ecx
0x18001b977  mov     rcx, r15
0x18001b97a  mov     [rsp+78h+var_40], rax
0x18001b97f  call    ?LookupKey@?$HashTable@VSyncId@@HVDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV2@@Z; HashTable<SyncId,int,DefaultHashTableContext>::LookupKey(SyncId const &,SyncId &)
0x18001b984  test    al, al
0x18001b986  jz      loc_18001BA11
0x18001b98c  lea     rcx, [rsp+78h+var_48]; this
0x18001b991  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18001b996  jmp     loc_18001B7C5
0x18001b99b  mov     [rbx], r15d
0x18001b99e  jmp     loc_18001B84C
0x18001b9a3  jnb     loc_18001BB01
0x18001b9a9  mov     esi, r15d
0x18001b9ac  jmp     loc_18001B84A
0x18001b9b1  cmp     [rbx+44h], esi
0x18001b9b4  jnz     loc_18001B80A
0x18001b9ba  mov     [rbx], r13d
0x18001b9bd  jmp     loc_18001B84C
0x18001b9c2  lea     r8, [rbx+38h]
0x18001b9c6  mov     rcx, rbx
0x18001b9c9  lea     rdx, [rbx+18h]
0x18001b9cd  call    ?MoveRight@IteratorWithCoreFragment@RangeSet@@QEAAJAEAVSyncId@@AEAV?$SharedRefPtr@UIClockVector@@@@@Z; RangeSet::IteratorWithCoreFragment::MoveRight(SyncId &,SharedRefPtr<IClockVector> &)
0x18001b9d2  mov     edi, eax
  ... truncated ...
```
