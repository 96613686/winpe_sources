# TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::InitializeSupportForNavigationKeyedByLocalName(void)

- ea: `0x18000a1ec`
- end: `0x18000a2f6`
- name: `?InitializeSupportForNavigationKeyedByLocalName@?$TagNavigationNode@VConfigTagNode@@VConfigNavigationNode@@VConfigTreeBase@@@@AEAAXXZ`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009cb8`

## callees

- `0x180001194`
- `0x18000573c`
- `0x180009d54`
- `0x18000a1ec`
- `0x180012f3c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a244`
- `KERNEL32!GetProcessHeap` at `0x18000a244`
- `KERNEL32!InitializeSRWLock` at `0x18000a233`
- `KERNEL32!InitializeSRWLock` at `0x18000a233`
- `KERNEL32!HeapAlloc` at `0x18000a258`
- `KERNEL32!HeapAlloc` at `0x18000a258`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TagNavigationNode<ConfigTagNode,ConfigNavigationNode,ConfigTreeBase>::InitializeSupportForNavigationKeyedByLocalName(
        __int64 a1)
{
  RTL_SRWLOCK *v2; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v4; // rax
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  __int64 v8; // rcx
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+18h]

  v2 = (RTL_SRWLOCK *)operator new(0x20u);
  v10 = v2;
  if ( v2 )
  {
    v2->Ptr = &HASH_TABLE<VDirMappingOwnerDescriptor,unsigned short const *>::`vftable';
    v2[1].Ptr = 0;
    v2[2].Ptr = 0;
    InitializeSRWLock(v2 + 3);
    v2->Ptr = &NavigationNodeTable<ConfigPathTagNode>::`vftable';
    ProcessHeap = GetProcessHeap();
    v4 = HeapAlloc(ProcessHeap, 8u, 0x40u);
    v2[1].Ptr = v4;
    if ( !v4 )
    {
      pExceptionObject = -2147024888;
      throw (long *)&pExceptionObject;
    }
    LODWORD(v2[2].Ptr) = 8;
  }
  else
  {
    v2 = 0;
  }
  result = ScopedPtr<PropertyNode>::Reset(a1 + 72);
  *(_QWORD *)(a1 + 72) = v2;
  if ( !v2 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v6 = 0;
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    do
    {
      TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChildToChildrenTable(a1, v7, v6);
      v8 = *(_QWORD *)(v7 + 40) - 40LL;
      result = *(unsigned int *)(v7 + 8);
      if ( *(_DWORD *)(v8 + 8) <= (unsigned int)result )
        break;
      v6 = v7;
      v7 = *(_QWORD *)(v7 + 40) - 40LL;
    }
    while ( v8 );
  }
  return result;
}

```

## disassembly

```asm
0x18000a1ec  mov     [rsp+arg_0], rbx
0x18000a1f1  mov     [rsp+arg_18], rsi
0x18000a1f6  push    rdi
0x18000a1f7  sub     rsp, 20h
0x18000a1fb  mov     rsi, rcx
0x18000a1fe  mov     ecx, 20h ; ' '; Size
0x18000a203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a208  mov     rdi, rax
0x18000a20b  mov     [rsp+28h+arg_10], rax
0x18000a210  test    rax, rax
0x18000a213  jz      short loc_18000A286
0x18000a215  lea     rax, ??_7?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@6B@; const HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::`vftable'
0x18000a21c  mov     [rdi], rax
0x18000a21f  mov     qword ptr [rdi+8], 0
0x18000a227  mov     qword ptr [rdi+10h], 0
0x18000a22f  lea     rcx, [rdi+18h]; SRWLock
0x18000a233  call    cs:__imp_InitializeSRWLock
0x18000a239  nop
0x18000a23a  lea     rax, ??_7?$NavigationNodeTable@VConfigPathTagNode@@@@6B@; const NavigationNodeTable<ConfigPathTagNode>::`vftable'
0x18000a241  mov     [rdi], rax
0x18000a244  call    cs:__imp_GetProcessHeap
0x18000a24a  mov     rcx, rax; hHeap
0x18000a24d  mov     ebx, 8
0x18000a252  lea     r8d, [rbx+38h]; dwBytes
0x18000a256  mov     edx, ebx; dwFlags
0x18000a258  call    cs:__imp_HeapAlloc
0x18000a25e  mov     [rdi+8], rax
0x18000a262  test    rax, rax
0x18000a265  jnz     short loc_18000A281
0x18000a267  mov     [rsp+28h+pExceptionObject], 80070008h
0x18000a26f  lea     rdx, _TI1J; pThrowInfo
0x18000a276  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000a27b  call    _CxxThrowException_0
0x18000a281  mov     [rdi+10h], ebx
0x18000a284  jmp     short loc_18000A288
0x18000a286  xor     edi, edi
0x18000a288  lea     rcx, [rsi+48h]
0x18000a28c  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000a291  mov     [rsi+48h], rdi
0x18000a295  test    rdi, rdi
0x18000a298  jnz     short loc_18000A2B4
0x18000a29a  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x18000a2a2  lea     rdx, _TI1J; pThrowInfo
0x18000a2a9  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000a2ae  call    _CxxThrowException_0
0x18000a2b4  xor     r8d, r8d
0x18000a2b7  mov     rbx, [rsi+20h]
0x18000a2bb  test    rbx, rbx
0x18000a2be  jz      short loc_18000A2E6
0x18000a2c0  mov     rdx, rbx
0x18000a2c3  mov     rcx, rsi
0x18000a2c6  call    ?AddChildToChildrenTable@?$TagNavigationNode@VFileSystemTagNode@@VFileSystemNode@@VFileSystemTree@@@@AEAAXPEAVFileSystemTagNode@@0@Z; TagNavigationNode<FileSystemTagNode,FileSystemNode,FileSystemTree>::AddChildToChildrenTable(FileSystemTagNode *,FileSystemTagNode *)
0x18000a2cb  mov     rcx, [rbx+28h]
0x18000a2cf  add     rcx, 0FFFFFFFFFFFFFFD8h
0x18000a2d3  mov     eax, [rbx+8]
0x18000a2d6  cmp     [rcx+8], eax
0x18000a2d9  jbe     short loc_18000A2E6
0x18000a2db  mov     r8, rbx
0x18000a2de  mov     rbx, rcx
0x18000a2e1  test    rcx, rcx
0x18000a2e4  jnz     short loc_18000A2C0
0x18000a2e6  mov     rbx, [rsp+28h+arg_0]
0x18000a2eb  mov     rsi, [rsp+28h+arg_18]
0x18000a2f0  add     rsp, 20h
0x18000a2f4  pop     rdi
0x18000a2f5  retn
```
