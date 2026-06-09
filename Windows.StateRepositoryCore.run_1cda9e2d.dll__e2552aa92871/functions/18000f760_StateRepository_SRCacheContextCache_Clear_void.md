# StateRepository::SRCacheContextCache::Clear(void)

- ea: `0x18000f760`
- end: `0x18000f7b7`
- name: `?Clear@SRCacheContextCache@StateRepository@@QEAAJXZ`
- size: `87`
- prototype: `__int64 __fastcall(StateRepository::SRCacheContextCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e4b4`

## callees

- `0x18000e45c`
- `0x18000e69c`
- `0x18000f760`

## pseudocode

```c
__int64 __fastcall StateRepository::SRCacheContextCache::Clear(StateRepository::SRCacheContextCache *this)
{
  StateRepository::SRCacheContextCache *v1; // rbx
  unsigned __int64 v2; // rdi

  v1 = StateRepository::SRCacheContextCacheSingleton::s_cache;
  if ( *((_BYTE *)StateRepository::SRCacheContextCacheSingleton::s_cache + 24) )
  {
    v2 = 0;
    if ( *((_QWORD *)StateRepository::SRCacheContextCacheSingleton::s_cache + 2) )
    {
      do
      {
        this = *(StateRepository::SRCacheContextCache **)(*(_QWORD *)v1 + 8 * v2);
        if ( this )
          StateRepository::CacheContextEntry::`scalar deleting destructor'(this);
        ++v2;
      }
      while ( v2 < *((_QWORD *)v1 + 2) );
    }
  }
  *((_QWORD *)v1 + 2) = 0;
  *((_QWORD *)v1 + 6) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(this);
  return 0;
}

```

## disassembly

```asm
0x18000f760  mov     [rsp+arg_0], rbx
0x18000f765  push    rdi
0x18000f766  sub     rsp, 20h
0x18000f76a  mov     rbx, cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000f771  cmp     byte ptr [rbx+18h], 0
0x18000f775  jz      short loc_18000F799
0x18000f777  xor     edi, edi
0x18000f779  cmp     [rbx+10h], rdi
0x18000f77d  jbe     short loc_18000F799
0x18000f77f  mov     rax, [rbx]
0x18000f782  mov     rcx, [rax+rdi*8]; this
0x18000f786  test    rcx, rcx
0x18000f789  jz      short loc_18000F790
0x18000f78b  call    ??_GCacheContextEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::CacheContextEntry::`scalar deleting destructor'(uint)
0x18000f790  inc     rdi
0x18000f793  cmp     rdi, [rbx+10h]
0x18000f797  jb      short loc_18000F77F
0x18000f799  mov     qword ptr [rbx+10h], 0
0x18000f7a1  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18000f7a6  mov     [rbx+30h], rax
0x18000f7aa  xor     eax, eax
0x18000f7ac  mov     rbx, [rsp+28h+arg_0]
0x18000f7b1  add     rsp, 20h
0x18000f7b5  pop     rdi
0x18000f7b6  retn
```
