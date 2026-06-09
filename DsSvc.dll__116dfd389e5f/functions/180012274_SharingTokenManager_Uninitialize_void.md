# SharingTokenManager::Uninitialize(void)

- ea: `0x180012274`
- end: `0x180012309`
- name: `?Uninitialize@SharingTokenManager@@QEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(SharingTokenManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d860`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x180011548`
- `0x180012274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012291`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800122cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800122cd`

## string_xrefs

- `0x1800122ed`: `SharingTokenManager::Uninitialize`
- `0x1800122bb`: `SharingTokenDatabase::Uninitialize`

## pseudocode

```c
__int64 __fastcall SharingTokenManager::Uninitialize(struct _RTL_CRITICAL_SECTION *this)
{
  int v1; // ebx
  Database *p_LockCount; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // rcx
  int *v5; // rax
  __int64 v6; // rcx
  int *v7; // rax
  __int64 v9; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+20h] [rbp-18h]

  v1 = 0;
  if ( LODWORD(this->DebugInfo) )
  {
    LODWORD(this->DebugInfo) = 0;
    p_LockCount = (Database *)&this->LockCount;
    v3 = this + 3;
    EnterCriticalSection(this + 3);
    v1 = Database::Uninitialize(p_LockCount);
    if ( v1 < 0 )
    {
      v5 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v4);
      v10 = v1;
      DSLogger::LogError((DSLogger *)v5, L"SharingTokenDatabase::Uninitialize", 220, L"hr=0x%x.", v10);
    }
    LeaveCriticalSection(v3);
    if ( v1 < 0 )
    {
      v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v6);
      LODWORD(v9) = v1;
      DSLogger::LogError((DSLogger *)v7, L"SharingTokenManager::Uninitialize", 68, L"hr=0x%x.", v9);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180012274  mov     [rsp+arg_0], rbx
0x180012279  push    rdi
0x18001227a  sub     rsp, 30h
0x18001227e  xor     ebx, ebx
0x180012280  cmp     [rcx], ebx
0x180012282  jz      short loc_1800122FC
0x180012284  mov     [rcx], ebx
0x180012286  lea     rbx, [rcx+8]
0x18001228a  lea     rdi, [rbx+70h]
0x18001228e  mov     rcx, rdi; lpCriticalSection
0x180012291  call    cs:__imp_EnterCriticalSection
0x180012297  mov     rcx, rbx; this
0x18001229a  call    ?Uninitialize@Database@@QEAAJXZ; Database::Uninitialize(void)
0x18001229f  mov     ebx, eax
0x1800122a1  test    eax, eax
0x1800122a3  jns     short loc_1800122CA
0x1800122a5  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800122aa  lea     r9, aHr0xX; "hr=0x%x."
0x1800122b1  mov     dword ptr [rsp+38h+var_18], ebx
0x1800122b5  mov     r8d, 0DCh; unsigned int
0x1800122bb  lea     rdx, aSharingtokenda_1; "SharingTokenDatabase::Uninitialize"
0x1800122c2  mov     rcx, rax; this
0x1800122c5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800122ca  mov     rcx, rdi; lpCriticalSection
0x1800122cd  call    cs:__imp_LeaveCriticalSection
0x1800122d3  test    ebx, ebx
0x1800122d5  jns     short loc_1800122FC
0x1800122d7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800122dc  lea     r9, aHr0xX; "hr=0x%x."
0x1800122e3  mov     dword ptr [rsp+38h+var_18], ebx
0x1800122e7  mov     r8d, 44h ; 'D'; unsigned int
0x1800122ed  lea     rdx, aSharingtokenma_5; "SharingTokenManager::Uninitialize"
0x1800122f4  mov     rcx, rax; this
0x1800122f7  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800122fc  mov     eax, ebx
0x1800122fe  mov     rbx, [rsp+38h+arg_0]
0x180012303  add     rsp, 30h
0x180012307  pop     rdi
0x180012308  retn
```
