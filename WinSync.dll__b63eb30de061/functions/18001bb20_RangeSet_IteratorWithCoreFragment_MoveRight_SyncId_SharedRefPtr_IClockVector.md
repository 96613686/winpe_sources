# RangeSet::IteratorWithCoreFragment::MoveRight(SyncId &,SharedRefPtr<IClockVector> &)

- ea: `0x18001bb20`
- end: `0x18001bd66`
- name: `?MoveRight@IteratorWithCoreFragment@RangeSet@@QEAAJAEAVSyncId@@AEAV?$SharedRefPtr@UIClockVector@@@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001b570`

## callees

- `0x180007584`
- `0x18000f810`
- `0x180011f60`
- `0x18001a1f0`
- `0x18001b354`
- `0x18001bb20`
- `0x18001bd6c`
- `0x18001be90`
- `0x180093232`
- `0x180094010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001bc03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc22`

## pseudocode

```c
__int64 __fastcall RangeSet::IteratorWithCoreFragment::MoveRight(__int64 a1, __int64 a2, __int64 *a3)
{
  int v3; // eax
  __int64 v5; // rcx
  __int64 result; // rax
  volatile signed __int32 *v9; // rcx
  __int64 v10; // rsi
  const void *v11; // r12
  __int64 v12; // rdx
  size_t v13; // rbp
  _DWORD *v14; // r14
  unsigned int v15; // esi
  int v16; // ecx
  __int64 v17; // rax
  unsigned int v18; // edi
  _BYTE v19[4]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-34h]
  __int64 v21; // [rsp+38h] [rbp-30h]
  LPVOID lpMem; // [rsp+88h] [rbp+20h] BYREF

  v3 = *(unsigned __int16 *)(a1 + 76);
  v5 = *a3;
  LODWORD(lpMem) = v3;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *a3 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *, __int64 *))(**(_QWORD **)(a1 + 96) + 32LL))(
             *(_QWORD *)(a1 + 96),
             *(_QWORD *)(a1 + 112),
             &lpMem,
             a3);
  if ( !(_DWORD)result )
  {
    if ( (*(_DWORD *)(a2 + 4) & 0x20000) == 0 )
    {
      v9 = *(volatile signed __int32 **)(a2 + 8);
      if ( v9 )
      {
        if ( _InterlockedExchangeAdd(v9, 0xFFFFFFFF) == 1 )
          SeFree(*(void **)(a2 + 8));
      }
    }
    *(_DWORD *)(a2 + 4) = 0;
    *(_QWORD *)(a2 + 8) = 0;
    v10 = *(_QWORD *)(a1 + 104);
    if ( v10 )
    {
      v16 = *(_DWORD *)(v10 + 24) & 1;
      v20 = *(unsigned __int16 *)(v10 + 28);
      v17 = *(_QWORD *)(a1 + 112);
      v20 = v20 & 0xFFFEFFFF | ((v16 | 2) << 16);
      v18 = 0;
      v21 = v17;
      if ( !(unsigned __int8)HashTable<SyncId,int,DefaultHashTableContext>::LookupKey(v10, v19) )
      {
        v18 = SyncId::Promote((SyncId *)v19);
        if ( !v18 )
        {
          LODWORD(lpMem) = 1;
          v18 = HashTable<SyncId,int,DefaultHashTableContext>::AddItem(v10, v19, &lpMem);
          if ( !v18 )
            SyncId::operator=(a2, (__int64)v19);
        }
      }
      SyncId::~SyncId((SyncId *)v19);
      return v18;
    }
    else
    {
      v11 = *(const void **)(a1 + 112);
      ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
      v13 = (unsigned int)v12;
      v14 = HeapAlloc(hHeap, 0, v12 + 7);
      if ( lpMem )
        HeapFree(hHeap, 0, lpMem);
      if ( v14 )
      {
        *(_QWORD *)(a2 + 8) = v14;
        *v14 = 1;
        v15 = 0;
        memcpy_0((void *)(*(_QWORD *)(a2 + 8) + 4LL), v11, v13);
        *(_DWORD *)(a2 + 4) &= ~0x20000u;
        *(_DWORD *)(a2 + 4) ^= (*(_DWORD *)(a2 + 4) ^ (*(_DWORD *)(a1 + 72) << 16)) & 0x10000;
        *(_WORD *)(a2 + 4) = *(_WORD *)(a1 + 76);
      }
      else
      {
        v15 = -2147024882;
        SyncId::~SyncId((SyncId *)a2);
        *(_DWORD *)(a2 + 4) = 0;
        *(_QWORD *)(a2 + 8) = 0;
      }
      return v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001bb20  push    rbx
0x18001bb22  push    rsi
0x18001bb23  push    rdi
0x18001bb24  push    r13
0x18001bb26  sub     rsp, 48h
0x18001bb2a  movzx   eax, word ptr [rcx+4Ch]
0x18001bb2e  mov     rdi, rcx
0x18001bb31  mov     rcx, [r8]
0x18001bb34  mov     rsi, r8
0x18001bb37  mov     dword ptr [rsp+68h+lpMem], eax
0x18001bb3e  mov     rbx, rdx
0x18001bb41  test    rcx, rcx
0x18001bb44  jz      short loc_18001BB52
0x18001bb46  mov     rax, [rcx]
0x18001bb49  mov     rax, [rax+10h]
0x18001bb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb52  xor     r13d, r13d
0x18001bb55  lea     r8, [rsp+68h+lpMem]
0x18001bb5d  mov     [rsi], r13
0x18001bb60  mov     r9, rsi
0x18001bb63  mov     rcx, [rdi+60h]
0x18001bb67  mov     rdx, [rdi+70h]
0x18001bb6b  mov     rax, [rcx]
0x18001bb6e  mov     rax, [rax+20h]
0x18001bb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb77  test    eax, eax
0x18001bb79  jnz     loc_18001BC88
0x18001bb7f  test    dword ptr [rbx+4], 20000h
0x18001bb86  jnz     short loc_18001BBA3
0x18001bb88  mov     rcx, [rbx+8]
0x18001bb8c  test    rcx, rcx
0x18001bb8f  jz      short loc_18001BBA3
0x18001bb91  mov     eax, 0FFFFFFFFh
0x18001bb96  lock xadd [rcx], eax
0x18001bb9a  cmp     eax, 1
0x18001bb9d  jz      loc_18001BD07
0x18001bba3  mov     [rbx+4], r13d
0x18001bba7  mov     [rbx+8], r13
0x18001bbab  mov     rsi, [rdi+68h]
0x18001bbaf  test    rsi, rsi
0x18001bbb2  jnz     loc_18001BCA9
0x18001bbb8  mov     [rsp+68h+arg_0], rbp
0x18001bbbd  mov     [rsp+68h+arg_8], r12
0x18001bbc2  mov     r12, [rdi+70h]
0x18001bbc6  mov     [rsp+68h+arg_10], r14
0x18001bbce  mov     [rsp+68h+var_28], r15
0x18001bbd3  cmp     [rdi+48h], r13d
0x18001bbd7  jnz     loc_18001BD5A
0x18001bbdd  lea     rdx, [rdi+4Ch]
0x18001bbe1  mov     r15, rdx
0x18001bbe4  movzx   edx, word ptr [rdx]
0x18001bbe7  lea     rcx, [rsp+68h+lpMem]
0x18001bbef  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x18001bbf4  mov     rcx, cs:hHeap; hHeap
0x18001bbfb  lea     r8, [rdx+7]; dwBytes
0x18001bbff  mov     ebp, edx
0x18001bc01  xor     edx, edx; dwFlags
0x18001bc03  call    cs:__imp_HeapAlloc
0x18001bc09  mov     r8, [rsp+68h+lpMem]; lpMem
0x18001bc11  mov     r14, rax
0x18001bc14  test    r8, r8
0x18001bc17  jz      short loc_18001BC28
0x18001bc19  mov     rcx, cs:hHeap; hHeap
0x18001bc20  xor     edx, edx; dwFlags
0x18001bc22  call    cs:__imp_HeapFree
0x18001bc28  test    r14, r14
0x18001bc2b  jz      short loc_18001BC92
0x18001bc2d  mov     [rbx+8], r14
0x18001bc31  mov     r8, rbp; Size
0x18001bc34  mov     dword ptr [r14], 1
0x18001bc3b  mov     rdx, r12; Src
0x18001bc3e  mov     rcx, [rbx+8]
0x18001bc42  mov     esi, r13d
0x18001bc45  add     rcx, 4; void *
0x18001bc49  call    memcpy_0
0x18001bc4e  and     dword ptr [rbx+4], 0FFFDFFFFh
0x18001bc55  mov     ecx, [rdi+48h]
0x18001bc58  shl     ecx, 10h
0x18001bc5b  xor     ecx, [rbx+4]
0x18001bc5e  and     ecx, 10000h
0x18001bc64  xor     [rbx+4], ecx
0x18001bc67  movzx   eax, word ptr [r15]
0x18001bc6b  mov     [rbx+4], ax
0x18001bc6f  mov     r15, [rsp+68h+var_28]
0x18001bc74  mov     eax, esi
0x18001bc76  mov     r14, [rsp+68h+arg_10]
0x18001bc7e  mov     r12, [rsp+68h+arg_8]
0x18001bc83  mov     rbp, [rsp+68h+arg_0]
0x18001bc88  add     rsp, 48h
0x18001bc8c  pop     r13
0x18001bc8e  pop     rdi
0x18001bc8f  pop     rsi
0x18001bc90  pop     rbx
0x18001bc91  retn
0x18001bc92  mov     rcx, rbx; this
0x18001bc95  mov     esi, 8007000Eh
0x18001bc9a  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18001bc9f  mov     [rbx+4], r13d
0x18001bca3  mov     [rbx+8], r13
0x18001bca7  jmp     short loc_18001BC6F
0x18001bca9  movzx   eax, word ptr [rsi+1Ch]
0x18001bcad  lea     rdx, [rsp+68h+var_38]
0x18001bcb2  mov     ecx, [rsi+18h]
0x18001bcb5  mov     r8, rbx
0x18001bcb8  and     ecx, 1
0x18001bcbb  mov     [rsp+68h+var_34], r13d
0x18001bcc0  mov     word ptr [rsp+68h+var_34], ax
0x18001bcc5  or      ecx, 2
0x18001bcc8  mov     eax, [rsp+68h+var_34]
0x18001bccc  shl     ecx, 10h
0x18001bccf  btr     eax, 10h
0x18001bcd3  or      ecx, eax
0x18001bcd5  mov     rax, [rdi+70h]
0x18001bcd9  mov     [rsp+68h+var_34], ecx
0x18001bcdd  mov     edi, r13d
0x18001bce0  mov     rcx, rsi
0x18001bce3  mov     [rsp+68h+var_30], rax
0x18001bce8  call    ?LookupKey@?$HashTable@VSyncId@@HVDefaultHashTableContext@@@@QEBA_NAEBVSyncId@@AEAV2@@Z; HashTable<SyncId,int,DefaultHashTableContext>::LookupKey(SyncId const &,SyncId &)
0x18001bced  test    al, al
0x18001bcef  jz      short loc_18001BD15
0x18001bcf1  lea     rcx, [rsp+68h+var_38]; this
0x18001bcf6  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18001bcfb  mov     eax, edi
0x18001bcfd  add     rsp, 48h
0x18001bd01  pop     r13
0x18001bd03  pop     rdi
0x18001bd04  pop     rsi
0x18001bd05  pop     rbx
0x18001bd06  retn
0x18001bd07  mov     rcx, [rbx+8]; void *
0x18001bd0b  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18001bd10  jmp     loc_18001BBA3
0x18001bd15  lea     rcx, [rsp+68h+var_38]; this
0x18001bd1a  call    ?Promote@SyncId@@QEAAJXZ; SyncId::Promote(void)
0x18001bd1f  mov     edi, eax
0x18001bd21  test    eax, eax
0x18001bd23  jnz     short loc_18001BCF1
0x18001bd25  lea     r8, [rsp+68h+lpMem]
0x18001bd2d  mov     dword ptr [rsp+68h+lpMem], 1
0x18001bd38  lea     rdx, [rsp+68h+var_38]
0x18001bd3d  mov     rcx, rsi
0x18001bd40  call    ?AddItem@?$HashTable@VSyncId@@HVDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBH@Z; HashTable<SyncId,int,DefaultHashTableContext>::AddItem(SyncId const &,int const &)
0x18001bd45  mov     edi, eax
0x18001bd47  test    eax, eax
0x18001bd49  jnz     short loc_18001BCF1
0x18001bd4b  lea     rdx, [rsp+68h+var_38]
0x18001bd50  mov     rcx, rbx
0x18001bd53  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18001bd58  jmp     short loc_18001BCF1
0x18001bd5a  mov     rdx, r12
0x18001bd5d  lea     r15, [rdi+4Ch]
0x18001bd61  jmp     loc_18001BBE4
```
