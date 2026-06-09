# HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::InsertRecord(VDirMappingOwnerDescriptor *)

- ea: `0x18000a2fc`
- end: `0x18000a421`
- name: `?InsertRecord@?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@QEAAJPEAVVDirMappingOwnerDescriptor@@@Z`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d54`
- `0x18000c50c`
- `0x18000c5a4`

## callees

- `0x180001194`
- `0x180004d20`
- `0x180004e08`
- `0x18000a2fc`
- `0x18000a50c`
- `0x180014010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18000a3f5`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000a3f5`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a37f`
- `KERNEL32!AcquireSRWLockShared` at `0x18000a37f`

## pseudocode

```c
__int64 __fastcall HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::InsertRecord(
        RTL_SRWLOCK *a1,
        __int64 a2)
{
  __int64 v4; // r15
  int v5; // eax
  int v6; // r14d
  _QWORD *v7; // rax
  signed __int64 *v8; // rdi
  signed __int64 v9; // rax
  volatile signed __int64 *v10; // rcx
  int v11; // edi
  signed __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  volatile signed __int64 *v14; // [rsp+70h] [rbp+18h] BYREF
  _QWORD *v15; // [rsp+78h] [rbp+20h]

  v4 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))a1->Ptr + 3))(a1);
  v5 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64))a1->Ptr + 4))(a1, v4);
  v13 = 0;
  v6 = v5;
  v14 = 0;
  v7 = operator new(0x18u);
  v15 = v7;
  v8 = v7;
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = a2;
    *((_DWORD *)v7 + 4) = v6;
    AcquireSRWLockShared(a1 + 3);
    do
    {
      if ( (unsigned int)HASH_TABLE<ConfigPathTagNode,unsigned short const *>::FindNodeInternal(
                           (_DWORD)a1,
                           v4,
                           v6,
                           (unsigned int)&v13,
                           (__int64)&v14) )
      {
        v8[1] = 0;
        HASH_TABLE<FileSystemTagNode,unsigned short const *>::DeleteNode(a1, v8);
        v11 = -2147024713;
        goto LABEL_9;
      }
      v9 = v13;
      v10 = v14;
      *v8 = v13;
    }
    while ( v9 != _InterlockedCompareExchange64(v10, (signed __int64)v8, v9) );
    v11 = 0;
    if ( a2 )
      (*((void (__fastcall **)(RTL_SRWLOCK *, __int64))a1->Ptr + 1))(a1, a2);
    _InterlockedIncrement((volatile signed __int32 *)&a1[2].Ptr + 1);
LABEL_9:
    ReleaseSRWLockShared(a1 + 3);
    if ( v11 >= 0 )
      HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::RehashTableIfNeeded(a1);
  }
  else
  {
    return (unsigned int)-2147024888;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a2fc  mov     [rsp+arg_8], rbx
0x18000a301  push    rbp
0x18000a302  push    rsi
0x18000a303  push    rdi
0x18000a304  push    r14
0x18000a306  push    r15
0x18000a308  sub     rsp, 30h
0x18000a30c  mov     rax, [rcx]
0x18000a30f  mov     rsi, rdx
0x18000a312  mov     rbx, rcx
0x18000a315  mov     rax, [rax+18h]
0x18000a319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31e  mov     r8, [rbx]
0x18000a321  mov     r15, rax
0x18000a324  mov     rdx, rax
0x18000a327  mov     rcx, rbx
0x18000a32a  mov     rax, [r8+20h]
0x18000a32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a333  mov     ecx, 18h; Size
0x18000a338  mov     [rsp+58h+arg_0], 0
0x18000a341  mov     r14d, eax
0x18000a344  mov     [rsp+58h+arg_10], 0
0x18000a34d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a352  mov     [rsp+58h+arg_18], rax
0x18000a357  mov     rdi, rax
0x18000a35a  test    rax, rax
0x18000a35d  jz      loc_18000A409
0x18000a363  mov     qword ptr [rax], 0
0x18000a36a  mov     [rax+8], rsi
0x18000a36e  mov     [rax+10h], r14d
0x18000a372  test    rax, rax
0x18000a375  jz      loc_18000A409
0x18000a37b  lea     rcx, [rbx+18h]; SRWLock
0x18000a37f  call    cs:__imp_AcquireSRWLockShared
0x18000a385  lea     rax, [rsp+58h+arg_10]
0x18000a38a  mov     r8d, r14d
0x18000a38d  lea     r9, [rsp+58h+arg_0]
0x18000a392  mov     [rsp+58h+var_38], rax
0x18000a397  mov     rdx, r15
0x18000a39a  mov     rcx, rbx
0x18000a39d  call    ?FindNodeInternal@?$HASH_TABLE@VConfigPathTagNode@@PEBG@@AEAAHPEBGKPEAPEAV?$HASH_NODE@VConfigPathTagNode@@@@PEAPEAPEAV2@@Z; HASH_TABLE<ConfigPathTagNode,ushort const *>::FindNodeInternal(ushort const *,ulong,HASH_NODE<ConfigPathTagNode> * *,HASH_NODE<ConfigPathTagNode> * * *)
0x18000a3a2  test    eax, eax
0x18000a3a4  jnz     short loc_18000A3D9
0x18000a3a6  mov     rax, [rsp+58h+arg_0]
0x18000a3ab  mov     rcx, [rsp+58h+arg_10]
0x18000a3b0  mov     [rdi], rax
0x18000a3b3  lock cmpxchg [rcx], rdi
0x18000a3b8  jnz     short loc_18000A385
0x18000a3ba  xor     edi, edi
0x18000a3bc  test    rsi, rsi
0x18000a3bf  jz      short loc_18000A3D3
0x18000a3c1  mov     rax, [rbx]
0x18000a3c4  mov     rdx, rsi
0x18000a3c7  mov     rcx, rbx
0x18000a3ca  mov     rax, [rax+8]
0x18000a3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d3  lock inc dword ptr [rbx+14h]
0x18000a3d7  jmp     short loc_18000A3F1
0x18000a3d9  mov     rdx, rdi
0x18000a3dc  mov     qword ptr [rdi+8], 0
0x18000a3e4  mov     rcx, rbx
0x18000a3e7  call    ?DeleteNode@?$HASH_TABLE@VFileSystemTagNode@@PEBG@@AEAAXPEAV?$HASH_NODE@VFileSystemTagNode@@@@@Z; HASH_TABLE<FileSystemTagNode,ushort const *>::DeleteNode(HASH_NODE<FileSystemTagNode> *)
0x18000a3ec  mov     edi, 800700B7h
0x18000a3f1  lea     rcx, [rbx+18h]; SRWLock
0x18000a3f5  call    cs:__imp_ReleaseSRWLockShared
0x18000a3fb  test    edi, edi
0x18000a3fd  js      short loc_18000A40E
0x18000a3ff  mov     rcx, rbx
0x18000a402  call    ?RehashTableIfNeeded@?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@AEAAXXZ; HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::RehashTableIfNeeded(void)
0x18000a407  jmp     short loc_18000A40E
0x18000a409  mov     edi, 80070008h
0x18000a40e  mov     rbx, [rsp+58h+arg_8]
0x18000a413  mov     eax, edi
0x18000a415  add     rsp, 30h
0x18000a419  pop     r15
0x18000a41b  pop     r14
0x18000a41d  pop     rdi
0x18000a41e  pop     rsi
0x18000a41f  pop     rbp
0x18000a420  retn
```
