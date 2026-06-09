# StateRepository::SRCacheContextCache::Get(ushort const *,SRCacheContext &)

- ea: `0x18000f880`
- end: `0x18000f953`
- name: `?Get@SRCacheContextCache@StateRepository@@QEAAPEAUSRCacheContext@@PEBGAEAU3@@Z`
- size: `211`
- prototype: `HKEY *__fastcall(StateRepository::SRCacheContextCache *this, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e4c0`

## callees

- `0x18000c928`
- `0x18000e45c`
- `0x18000f580`
- `0x18000f880`
- `0x18001007c`

## pseudocode

```c
HKEY *__fastcall StateRepository::SRCacheContextCache::Get(
        StateRepository::SRCacheContextCache *this,
        const unsigned __int16 *a2,
        HKEY *a3)
{
  StateRepository::SRCacheContextCache *v3; // rbx
  unsigned __int64 v6; // r8
  __int64 v7; // r11
  unsigned __int64 i; // r9
  const unsigned __int16 *v9; // rcx
  int v10; // edx
  int v11; // eax
  __int64 v12; // rdi
  __int64 *v13; // rcx

  v3 = StateRepository::SRCacheContextCacheSingleton::s_cache;
  v6 = *((_QWORD *)StateRepository::SRCacheContextCacheSingleton::s_cache + 2);
  if ( !v6 )
    goto LABEL_14;
  v7 = *(_QWORD *)StateRepository::SRCacheContextCacheSingleton::s_cache;
  for ( i = v6 - 1; ; --i )
  {
    v9 = a2;
    do
    {
      v10 = *(const unsigned __int16 *)((char *)v9 + **(_QWORD **)(v7 + 8 * i) - (_QWORD)a2);
      v11 = *v9 - v10;
      if ( v11 )
        break;
      ++v9;
    }
    while ( v10 );
    if ( !v11 )
      break;
    if ( !i )
      goto LABEL_14;
  }
  if ( i == 0x40000000 )
  {
LABEL_14:
    ++*((_QWORD *)StateRepository::SRCacheContextCacheSingleton::s_cache + 5);
    return 0;
  }
  else
  {
    ++*((_QWORD *)StateRepository::SRCacheContextCacheSingleton::s_cache + 4);
    if ( i < v6 )
    {
      v13 = (__int64 *)(v7 + 8 * i);
      v12 = *v13;
      memmove_0(v13, v13 + 1, 8 * (v6 - i) - 8);
      --*((_QWORD *)v3 + 2);
    }
    else
    {
      v12 = 0;
    }
    SRCacheContext::operator=(a3, (HKEY *)(v12 + 8));
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(v12);
    *(_QWORD *)(v12 + 16) = 0;
    StateRepository::CacheContextEntry::`scalar deleting destructor'((HKEY *)v12);
    return a3;
  }
}

```

## disassembly

```asm
0x18000f880  mov     [rsp+arg_0], rbx
0x18000f885  mov     [rsp+arg_8], rsi
0x18000f88a  push    rdi
0x18000f88b  sub     rsp, 20h
0x18000f88f  mov     rbx, cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000f896  mov     rsi, r8
0x18000f899  mov     rdi, rdx
0x18000f89c  mov     r8, [rbx+10h]
0x18000f8a0  test    r8, r8
0x18000f8a3  jz      loc_18000F93D
0x18000f8a9  mov     r11, [rbx]
0x18000f8ac  lea     r9, [r8-1]
0x18000f8b0  mov     rax, [r11+r9*8]
0x18000f8b4  mov     rcx, rdi
0x18000f8b7  mov     r10, [rax]
0x18000f8ba  sub     r10, rdi
0x18000f8bd  movzx   eax, word ptr [rcx]
0x18000f8c0  movzx   edx, word ptr [rcx+r10]
0x18000f8c5  sub     eax, edx
0x18000f8c7  jnz     short loc_18000F8D1
0x18000f8c9  add     rcx, 2
0x18000f8cd  test    edx, edx
0x18000f8cf  jnz     short loc_18000F8BD
0x18000f8d1  test    eax, eax
0x18000f8d3  jz      short loc_18000F8DF
0x18000f8d5  test    r9, r9
0x18000f8d8  jz      short loc_18000F93D
0x18000f8da  dec     r9
0x18000f8dd  jmp     short loc_18000F8B0
0x18000f8df  cmp     r9, 40000000h
0x18000f8e6  jz      short loc_18000F93D
0x18000f8e8  inc     qword ptr [rbx+20h]
0x18000f8ec  cmp     r9, r8
0x18000f8ef  jb      short loc_18000F8F5
0x18000f8f1  xor     edi, edi
0x18000f8f3  jmp     short loc_18000F914
0x18000f8f5  lea     rcx, [r11+r9*8]; void *
0x18000f8f9  sub     r8, r9
0x18000f8fc  mov     rdi, [rcx]
0x18000f8ff  lea     rdx, [rcx+8]; Src
0x18000f903  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x18000f90b  call    memmove_0
0x18000f910  dec     qword ptr [rbx+10h]
0x18000f914  lea     rdx, [rdi+8]
0x18000f918  mov     rcx, rsi
0x18000f91b  call    ??4SRCacheContext@@QEAAAEAU0@$$QEAU0@@Z; SRCacheContext::operator=(SRCacheContext &&)
0x18000f920  mov     rcx, rdi
0x18000f923  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000f928  mov     rcx, rdi; this
0x18000f92b  mov     qword ptr [rdi+10h], 0
0x18000f933  call    ??_GCacheContextEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::CacheContextEntry::`scalar deleting destructor'(uint)
0x18000f938  mov     rax, rsi
0x18000f93b  jmp     short loc_18000F943
0x18000f93d  inc     qword ptr [rbx+28h]
0x18000f941  xor     eax, eax
0x18000f943  mov     rbx, [rsp+28h+arg_0]
0x18000f948  mov     rsi, [rsp+28h+arg_8]
0x18000f94d  add     rsp, 20h
0x18000f951  pop     rdi
0x18000f952  retn
```
