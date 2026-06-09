# CDUIResourceManager::UninitThread(void)

- ea: `0x1800d0a5c`
- end: `0x1800d0ae9`
- name: `?UninitThread@CDUIResourceManager@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(CDUIResourceManager *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18003732c`
- `0x18004eafc`
- `0x180070eb8`
- `0x180080fe4`
- `0x18008c370`

## callees

- `0x180048814`
- `0x1800d07b8`
- `0x1800d0a5c`
- `0x1800d0be8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d0ae2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d0aa1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d0aa1`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800d0ab0`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800d0ab0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800d0a92`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800d0a92`
- `DUI70!UnInitProcessPriv` at `0x1800d0acf`
- `DUI70!UnInitProcessPriv` at `0x1800d0acf`
- `DUI70!UnInitThread` at `0x1800d0a98`
- `DUI70!UnInitThread` at `0x1800d0a98`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d0a7f`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800d0a7f`

## pseudocode

```c
void __fastcall CDUIResourceManager::UninitThread(DWORD *this)
{
  struct CDUIResourceManager::REFCOUNTEDPARSER *RefCountedParserForThread; // rax
  __int64 v3; // rcx
  struct CDUIResourceManager::REFCOUNTEDPARSER *v4; // rdi
  bool v5; // zf
  unsigned int v6; // edx

  RefCountedParserForThread = CDUIResourceManager::_GetRefCountedParserForThread((CDUIResourceManager *)this);
  v4 = RefCountedParserForThread;
  if ( RefCountedParserForThread )
  {
    v5 = (*((_DWORD *)RefCountedParserForThread + 2))-- == 1;
    if ( v5 )
    {
      DirectUI::DUIXmlParser::Destroy(*(DirectUI::DUIXmlParser **)RefCountedParserForThread);
      CZeroInitNew::operator delete(v4);
      TlsSetValue(this[4], 0);
    }
  }
  UnInitThread(v3);
  AcquireSRWLockExclusive((PSRWLOCK)this);
  v5 = this[3]-- == 1;
  if ( v5 )
  {
    TlsFree(this[4]);
    v6 = this[16];
    this[4] = -1;
    CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)this, v6);
    UnInitProcessPriv(&_ImageBase);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this);
}

```

## disassembly

```asm
0x1800d0a5c  mov     [rsp+arg_8], rbx
0x1800d0a61  push    rdi
0x1800d0a62  sub     rsp, 20h
0x1800d0a66  mov     rbx, rcx
0x1800d0a69  call    ?_GetRefCountedParserForThread@CDUIResourceManager@@AEBAPEAUREFCOUNTEDPARSER@1@XZ; CDUIResourceManager::_GetRefCountedParserForThread(void)
0x1800d0a6e  mov     rdi, rax
0x1800d0a71  test    rax, rax
0x1800d0a74  jz      short loc_1800D0A98
0x1800d0a76  sub     dword ptr [rax+8], 1
0x1800d0a7a  jnz     short loc_1800D0A98
0x1800d0a7c  mov     rcx, [rax]
0x1800d0a7f  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800d0a85  mov     rcx, rdi; lpMem
0x1800d0a88  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x1800d0a8d  mov     ecx, [rbx+10h]; dwTlsIndex
0x1800d0a90  xor     edx, edx; lpTlsValue
0x1800d0a92  call    cs:__imp_TlsSetValue
0x1800d0a98  call    cs:__imp_UnInitThread
0x1800d0a9e  mov     rcx, rbx; SRWLock
0x1800d0aa1  call    cs:__imp_AcquireSRWLockExclusive
0x1800d0aa7  sub     dword ptr [rbx+0Ch], 1
0x1800d0aab  jnz     short loc_1800D0AD5
0x1800d0aad  mov     ecx, [rbx+10h]; dwTlsIndex
0x1800d0ab0  call    cs:__imp_TlsFree
0x1800d0ab6  mov     edx, [rbx+40h]; unsigned int
0x1800d0ab9  mov     rcx, rbx; this
0x1800d0abc  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800d0ac3  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x1800d0ac8  lea     rcx, __ImageBase
0x1800d0acf  call    cs:__imp_UnInitProcessPriv
0x1800d0ad5  mov     rcx, rbx
0x1800d0ad8  mov     rbx, [rsp+28h+arg_8]
0x1800d0add  add     rsp, 20h
0x1800d0ae1  pop     rdi
0x1800d0ae2  jmp     cs:__imp_ReleaseSRWLockExclusive
```
