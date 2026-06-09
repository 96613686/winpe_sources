# tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)

- ea: `0x18000f384`
- end: `0x18000f462`
- name: `?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ`
- size: `222`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800083c0`
- `0x18000ceb4`
- `0x18000d21c`
- `0x18000d68c`
- `0x18000d7b8`
- `0x18000d860`
- `0x18000da68`
- `0x18000f740`
- `0x1800134f4`

## callees

- `0x1800041a0`
- `0x1800044cc`
- `0x18000f384`
- `0x180010058`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f3b0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f3b0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f449`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f449`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000f419`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000f419`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000f42b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000f42b`

## pseudocode

```c
__int64 *__fastcall tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(
        __int64 a1)
{
  __int64 *v1; // rbx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&SharingTokenManagerSingleton, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    SharedObjectPool<DbSession>::SharedObjectPool<DbSession>(&qword_18002B4C8);
    dword_18002B4F0 = 0;
    qword_18002B4F8 = -1;
    qword_18002B500 = -1;
    qword_18002B4C8 = (__int64)&Database::`vftable';
    byte_18002B4F4 = 0;
    dword_18002B508 = -1;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(qword_18002B510);
    InitializeSRWLock(&stru_18002B530);
    InitializeCriticalSectionEx(&CriticalSection, 0, 0);
    v3 = 0;
    v1 = &qword_18002B4C0;
    InitOnceComplete(&SharingTokenManagerSingleton, 0, &qword_18002B4C0);
    tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f384  mov     rax, rsp
0x18000f387  mov     [rax+8], rcx
0x18000f38b  push    rbx
0x18000f38c  sub     rsp, 20h
0x18000f390  lea     r9, [rax+10h]; lpContext
0x18000f394  mov     dword ptr [rax+8], 0
0x18000f39b  lea     r8, [rax+8]; fPending
0x18000f39f  mov     qword ptr [rax+10h], 0
0x18000f3a7  xor     edx, edx; dwFlags
0x18000f3a9  lea     rcx, ?SharingTokenManagerSingleton@@3V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@tlx@@A; lpInitOnce
0x18000f3b0  call    cs:__imp_InitOnceBeginInitialize
0x18000f3b6  mov     rbx, [rsp+28h+arg_8]
0x18000f3bb  test    rbx, rbx
0x18000f3be  jnz     loc_18000F459
0x18000f3c4  lea     rcx, qword_18002B4C8
0x18000f3cb  call    ??0?$SharedObjectPool@VDbSession@@@@IEAA@XZ; SharedObjectPool<DbSession>::SharedObjectPool<DbSession>(void)
0x18000f3d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f3d4  mov     cs:dword_18002B4F0, ebx
0x18000f3da  lea     r8, ??_7Database@@6B@; const Database::`vftable'
0x18000f3e1  mov     cs:qword_18002B4F8, rax
0x18000f3e8  lea     rcx, qword_18002B510
0x18000f3ef  mov     cs:qword_18002B500, rax
0x18000f3f6  mov     cs:qword_18002B4C8, r8
0x18000f3fd  mov     cs:byte_18002B4F4, bl
0x18000f403  mov     cs:dword_18002B508, 0FFFFFFFFh
0x18000f40d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000f412  lea     rcx, stru_18002B530; SRWLock
0x18000f419  call    cs:__imp_InitializeSRWLock
0x18000f41f  xor     r8d, r8d; Flags
0x18000f422  lea     rcx, CriticalSection; lpCriticalSection
0x18000f429  xor     edx, edx; dwSpinCount
0x18000f42b  call    cs:__imp_InitializeCriticalSectionEx
0x18000f431  mov     [rsp+28h+arg_0], rbx
0x18000f436  lea     rcx, ?SharingTokenManagerSingleton@@3V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@tlx@@A; lpInitOnce
0x18000f43d  lea     rbx, qword_18002B4C0
0x18000f444  xor     edx, edx; dwFlags
0x18000f446  mov     r8, rbx; lpContext
0x18000f449  call    cs:__imp_InitOnceComplete
0x18000f44f  lea     rcx, [rsp+28h+arg_0]
0x18000f454  call    ??1_Initializer@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(void)
0x18000f459  mov     rax, rbx
0x18000f45c  add     rsp, 20h
0x18000f460  pop     rbx
0x18000f461  retn
```
