# TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::InitializeSupportForNavigationKeyedByLocalName(void)

- ea: `0x18000cdd0`
- end: `0x18000ceda`
- name: `?InitializeSupportForNavigationKeyedByLocalName@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAXXZ`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c470`

## callees

- `0x180001194`
- `0x18000573c`
- `0x18000c50c`
- `0x18000cdd0`
- `0x180012f3c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000ce28`
- `KERNEL32!GetProcessHeap` at `0x18000ce28`
- `KERNEL32!InitializeSRWLock` at `0x18000ce17`
- `KERNEL32!InitializeSRWLock` at `0x18000ce17`
- `KERNEL32!HeapAlloc` at `0x18000ce3c`
- `KERNEL32!HeapAlloc` at `0x18000ce3c`

## pseudocode

```c
__int64 __fastcall TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::InitializeSupportForNavigationKeyedByLocalName(
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
  result = ScopedPtr<PropertyNode>::Reset(a1 + 88);
  *(_QWORD *)(a1 + 88) = v2;
  if ( !v2 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v6 = 0;
  v7 = *(_QWORD *)(a1 + 48);
  if ( v7 )
  {
    do
    {
      TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(a1, v7, v6);
      v8 = *(_QWORD *)(v7 + 56) - 56LL;
      result = *(unsigned int *)(v7 + 8);
      if ( *(_DWORD *)(v8 + 8) <= (unsigned int)result )
        break;
      v6 = v7;
      v7 = *(_QWORD *)(v7 + 56) - 56LL;
    }
    while ( v8 );
  }
  return result;
}

```

## disassembly

```asm
0x18000cdd0  mov     [rsp+arg_0], rbx
0x18000cdd5  mov     [rsp+arg_18], rsi
0x18000cdda  push    rdi
0x18000cddb  sub     rsp, 20h
0x18000cddf  mov     rsi, rcx
0x18000cde2  mov     ecx, 20h ; ' '; Size
0x18000cde7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cdec  mov     rdi, rax
0x18000cdef  mov     [rsp+28h+arg_10], rax
0x18000cdf4  test    rax, rax
0x18000cdf7  jz      short loc_18000CE6A
0x18000cdf9  lea     rax, ??_7?$HASH_TABLE@VVDirMappingOwnerDescriptor@@PEBG@@6B@; const HASH_TABLE<VDirMappingOwnerDescriptor,ushort const *>::`vftable'
0x18000ce00  mov     [rdi], rax
0x18000ce03  mov     qword ptr [rdi+8], 0
0x18000ce0b  mov     qword ptr [rdi+10h], 0
0x18000ce13  lea     rcx, [rdi+18h]; SRWLock
0x18000ce17  call    cs:__imp_InitializeSRWLock
0x18000ce1d  nop
0x18000ce1e  lea     rax, ??_7?$NavigationNodeTable@VConfigPathTagNode@@@@6B@; const NavigationNodeTable<ConfigPathTagNode>::`vftable'
0x18000ce25  mov     [rdi], rax
0x18000ce28  call    cs:__imp_GetProcessHeap
0x18000ce2e  mov     rcx, rax; hHeap
0x18000ce31  mov     ebx, 8
0x18000ce36  lea     r8d, [rbx+38h]; dwBytes
0x18000ce3a  mov     edx, ebx; dwFlags
0x18000ce3c  call    cs:__imp_HeapAlloc
0x18000ce42  mov     [rdi+8], rax
0x18000ce46  test    rax, rax
0x18000ce49  jnz     short loc_18000CE65
0x18000ce4b  mov     [rsp+28h+pExceptionObject], 80070008h
0x18000ce53  lea     rdx, _TI1J; pThrowInfo
0x18000ce5a  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000ce5f  call    _CxxThrowException_0
0x18000ce65  mov     [rdi+10h], ebx
0x18000ce68  jmp     short loc_18000CE6C
0x18000ce6a  xor     edi, edi
0x18000ce6c  lea     rcx, [rsi+58h]
0x18000ce70  call    ?Reset@?$ScopedPtr@VPropertyNode@@@@QEAAXXZ; ScopedPtr<PropertyNode>::Reset(void)
0x18000ce75  mov     [rsi+58h], rdi
0x18000ce79  test    rdi, rdi
0x18000ce7c  jnz     short loc_18000CE98
0x18000ce7e  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x18000ce86  lea     rdx, _TI1J; pThrowInfo
0x18000ce8d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000ce92  call    _CxxThrowException_0
0x18000ce98  xor     r8d, r8d
0x18000ce9b  mov     rbx, [rsi+30h]
0x18000ce9f  test    rbx, rbx
0x18000cea2  jz      short loc_18000CECA
0x18000cea4  mov     rdx, rbx
0x18000cea7  mov     rcx, rsi
0x18000ceaa  call    ?AddChildToChildrenTable@?$TagNavigationNode@VConfigPathTagNode@@VConfigPathNode@@VConfigPathNavigationTree@@@@AEAAXPEAVConfigPathTagNode@@0@Z; TagNavigationNode<ConfigPathTagNode,ConfigPathNode,ConfigPathNavigationTree>::AddChildToChildrenTable(ConfigPathTagNode *,ConfigPathTagNode *)
0x18000ceaf  mov     rcx, [rbx+38h]
0x18000ceb3  add     rcx, 0FFFFFFFFFFFFFFC8h
0x18000ceb7  mov     eax, [rbx+8]
0x18000ceba  cmp     [rcx+8], eax
0x18000cebd  jbe     short loc_18000CECA
0x18000cebf  mov     r8, rbx
0x18000cec2  mov     rbx, rcx
0x18000cec5  test    rcx, rcx
0x18000cec8  jnz     short loc_18000CEA4
0x18000ceca  mov     rbx, [rsp+28h+arg_0]
0x18000cecf  mov     rsi, [rsp+28h+arg_18]
0x18000ced4  add     rsp, 20h
0x18000ced8  pop     rdi
0x18000ced9  retn
```
