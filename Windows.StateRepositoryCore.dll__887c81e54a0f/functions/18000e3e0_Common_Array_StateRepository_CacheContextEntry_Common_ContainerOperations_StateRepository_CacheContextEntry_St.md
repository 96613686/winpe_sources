# Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::~Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>(void)

- ea: `0x18000e3e0`
- end: `0x18000e42e`
- name: `??1?$Array@VCacheContextEntry@StateRepository@@V?$ContainerOperations@VCacheContextEntry@StateRepository@@V12@@Common@@GV?$ContainerOperations@GVCacheContextEntry@StateRepository@@@4@V?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@4@@Common@@QEAA@XZ`
- size: `78`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e488`

## callees

- `0x18000e3e0`
- `0x18000e45c`
- `0x18000e670`

## pseudocode

```c
__int64 __fastcall Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::~Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>(
        __int64 a1,
        unsigned int a2)
{
  unsigned __int64 i; // rdi
  StateRepository::CacheContextEntry *v4; // rcx
  __int64 result; // rax

  if ( *(_QWORD *)a1 )
  {
    if ( *(_BYTE *)(a1 + 24) )
    {
      for ( i = 0; i < *(_QWORD *)(a1 + 16); ++i )
      {
        v4 = *(StateRepository::CacheContextEntry **)(*(_QWORD *)a1 + 8 * i);
        if ( v4 )
          StateRepository::CacheContextEntry::`scalar deleting destructor'(v4, a2);
      }
    }
    return Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(*(PVOID *)a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000e3e0  mov     [rsp+arg_0], rbx
0x18000e3e5  push    rdi
0x18000e3e6  sub     rsp, 20h
0x18000e3ea  cmp     qword ptr [rcx], 0
0x18000e3ee  mov     rbx, rcx
0x18000e3f1  jz      short loc_18000E423
0x18000e3f3  cmp     byte ptr [rcx+18h], 0
0x18000e3f7  jz      short loc_18000E41B
0x18000e3f9  xor     edi, edi
0x18000e3fb  cmp     [rcx+10h], rdi
0x18000e3ff  jbe     short loc_18000E41B
0x18000e401  mov     rax, [rbx]
0x18000e404  mov     rcx, [rax+rdi*8]; this
0x18000e408  test    rcx, rcx
0x18000e40b  jz      short loc_18000E412
0x18000e40d  call    ??_GCacheContextEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::CacheContextEntry::`scalar deleting destructor'(uint)
0x18000e412  inc     rdi
0x18000e415  cmp     rdi, [rbx+10h]
0x18000e419  jb      short loc_18000E401
0x18000e41b  mov     rcx, [rbx]; P
0x18000e41e  call    ?MemFree@?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@Common@@SAXPEAPEAVCacheContextEntry@StateRepository@@@Z; Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>::MemFree(StateRepository::CacheContextEntry * *)
0x18000e423  mov     rbx, [rsp+28h+arg_0]
0x18000e428  add     rsp, 20h
0x18000e42c  pop     rdi
0x18000e42d  retn
```
