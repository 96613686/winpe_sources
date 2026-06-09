# SharingTokenDatabase::Initialize(ushort const *)

- ea: `0x180017a68`
- end: `0x180017ad9`
- name: `?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z`
- size: `113`
- prototype: `__int64 __fastcall(SharingTokenDatabase *this, Common *pszPathIn)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d21c`
- `0x1800163ec`
- `0x18001669c`
- `0x18001686c`
- `0x180017140`
- `0x180017318`
- `0x180017518`
- `0x180017c90`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x180010844`
- `0x180017a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017a81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ac1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017ac1`

## string_xrefs

- `0x180017a9d`: `SharingTokenDatabase::Initialize failed! hr=0x%x.`
- `0x180017aae`: `SharingTokenDatabase::Initialize`

## pseudocode

```c
__int64 __fastcall SharingTokenDatabase::Initialize(SharingTokenDatabase *this, Common *pszPathIn)
{
  int v4; // ebx
  DSLogger *v5; // rax
  int v7; // [rsp+20h] [rbp-18h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v4 = Database::Initialize(this, pszPathIn);
  if ( v4 < 0 )
  {
    v5 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v7 = v4;
    DSLogger::LogError(
      v5,
      L"SharingTokenDatabase::Initialize",
      0xC7u,
      L"SharingTokenDatabase::Initialize failed! hr=0x%x.",
      v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017a68  mov     [rsp+arg_0], rbx
0x180017a6d  mov     [rsp+arg_8], rsi
0x180017a72  push    rdi
0x180017a73  sub     rsp, 30h
0x180017a77  mov     rdi, rcx
0x180017a7a  mov     rbx, rdx
0x180017a7d  add     rcx, 70h ; 'p'; lpCriticalSection
0x180017a81  call    cs:__imp_EnterCriticalSection
0x180017a87  mov     rdx, rbx; pszPathIn
0x180017a8a  mov     rcx, rdi; this
0x180017a8d  call    ?Initialize@Database@@QEAAJPEBG@Z; Database::Initialize(ushort const *)
0x180017a92  mov     ebx, eax
0x180017a94  test    eax, eax
0x180017a96  jns     short loc_180017ABD
0x180017a98  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180017a9d  lea     r9, aSharingtokenda_4; "SharingTokenDatabase::Initialize failed"...
0x180017aa4  mov     [rsp+38h+var_18], ebx
0x180017aa8  mov     r8d, 0C7h; unsigned int
0x180017aae  lea     rdx, aSharingtokenda_2; "SharingTokenDatabase::Initialize"
0x180017ab5  mov     rcx, rax; this
0x180017ab8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180017abd  lea     rcx, [rdi+70h]; lpCriticalSection
0x180017ac1  call    cs:__imp_LeaveCriticalSection
0x180017ac7  mov     rsi, [rsp+38h+arg_8]
0x180017acc  mov     eax, ebx
0x180017ace  mov     rbx, [rsp+38h+arg_0]
0x180017ad3  add     rsp, 30h
0x180017ad7  pop     rdi
0x180017ad8  retn
```
