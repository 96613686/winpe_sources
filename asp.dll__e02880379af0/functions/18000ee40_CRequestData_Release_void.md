# CRequestData::Release(void)

- ea: `0x18000ee40`
- end: `0x18000ef54`
- name: `?Release@CRequestData@@UEAAKXZ`
- size: `276`
- prototype: `unsigned int __fastcall(CRequestData *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000f7e0`

## callees

- `0x18000ee40`
- `0x18000f260`
- `0x18000f2d0`
- `0x18000f350`
- `0x18000f3d0`
- `0x18000f440`
- `0x18000f614`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180029dec`
- `KERNEL32!HeapFree` at `0x180029e01`
- `KERNEL32!HeapFree` at `0x180029e16`
- `KERNEL32!HeapFree` at `0x180029e2b`
- `KERNEL32!HeapFree` at `0x180029e40`
- `KERNEL32!HeapFree` at `0x180029e59`
- `KERNEL32!HeapFree` at `0x180029dec`
- `KERNEL32!HeapFree` at `0x180029e01`
- `KERNEL32!HeapFree` at `0x180029e16`
- `KERNEL32!HeapFree` at `0x180029e2b`
- `KERNEL32!HeapFree` at `0x180029e40`
- `KERNEL32!HeapFree` at `0x180029e59`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ef46`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000ef46`

## pseudocode

```c
__int64 __fastcall CRequestData::Release(CRequestData *this)
{
  bool v1; // zf
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // r8
  void *v7; // r8
  void *v8; // r8
  void *v9; // r8
  void *v10; // r8
  __int64 v11; // rdi

  v1 = (*((_DWORD *)this + 248))-- == 1;
  result = *((unsigned int *)this + 248);
  if ( v1 )
  {
    *(_QWORD *)this = &CRequestData::`vftable';
    v4 = *((_QWORD *)this + 10);
    if ( v4 )
    {
      do
      {
        v11 = *(_QWORD *)(v4 + 32);
        (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
        v4 = v11;
      }
      while ( v11 );
    }
    CHashTable::UnInit((CRequestData *)((char *)this + 64));
    v5 = *((_QWORD *)this + 52);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = (void *)*((_QWORD *)this + 44);
    if ( v6 )
      HeapFree(g_hDenaliHeap, 0, v6);
    v7 = (void *)*((_QWORD *)this + 46);
    if ( v7 )
      HeapFree(g_hDenaliHeap, 0, v7);
    v8 = (void *)*((_QWORD *)this + 47);
    if ( v8 )
      HeapFree(g_hDenaliHeap, 0, v8);
    v9 = (void *)*((_QWORD *)this + 49);
    if ( v9 )
      HeapFree(g_hDenaliHeap, 0, v9);
    v10 = (void *)*((_QWORD *)this + 51);
    if ( v10 )
      HeapFree(g_hDenaliHeap, 0, v10);
    CClCerts::~CClCerts((CRequestData *)((char *)this + 872));
    CCookies::~CCookies((CRequestData *)((char *)this + 752));
    CFormInputs::~CFormInputs((CRequestData *)((char *)this + 640));
    CServerVariables::~CServerVariables((CRequestData *)((char *)this + 536));
    CQueryString::~CQueryString((CRequestData *)((char *)this + 424));
    v1 = (*((_BYTE *)this + 72) & 2) == 0;
    *((_QWORD *)this + 8) = &CHashTable::`vftable';
    if ( !v1 )
      HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 12));
    if ( CRequestData::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CRequestData::sm_pach, this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ee40  push    rbx
0x18000ee42  sub     rsp, 20h
0x18000ee46  add     dword ptr [rcx+3E0h], 0FFFFFFFFh
0x18000ee4d  mov     rbx, rcx
0x18000ee50  mov     eax, [rcx+3E0h]
0x18000ee56  jnz     loc_18000EF4E
0x18000ee5c  lea     rax, ??_7CRequestData@@6B@; const CRequestData::`vftable'
0x18000ee63  mov     [rsp+28h+arg_0], rsi
0x18000ee68  mov     [rcx], rax
0x18000ee6b  mov     rcx, [rcx+50h]
0x18000ee6f  test    rcx, rcx
0x18000ee72  jnz     loc_180029DA6
0x18000ee78  lea     rcx, [rbx+40h]; this
0x18000ee7c  call    ?UnInit@CHashTable@@QEAAJXZ; CHashTable::UnInit(void)
0x18000ee81  mov     rcx, [rbx+1A0h]
0x18000ee88  test    rcx, rcx
0x18000ee8b  jnz     loc_180029DD1
0x18000ee91  mov     r8, [rbx+160h]; lpMem
0x18000ee98  test    r8, r8
0x18000ee9b  jnz     loc_180029DE3
0x18000eea1  mov     r8, [rbx+170h]; lpMem
0x18000eea8  test    r8, r8
0x18000eeab  jnz     loc_180029DF8
0x18000eeb1  mov     r8, [rbx+178h]; lpMem
0x18000eeb8  test    r8, r8
0x18000eebb  jnz     loc_180029E0D
0x18000eec1  mov     r8, [rbx+188h]; lpMem
0x18000eec8  test    r8, r8
0x18000eecb  jnz     loc_180029E22
0x18000eed1  mov     r8, [rbx+198h]; lpMem
0x18000eed8  test    r8, r8
0x18000eedb  jnz     loc_180029E37
0x18000eee1  lea     rcx, [rbx+368h]; this
0x18000eee8  call    ??1CClCerts@@QEAA@XZ; CClCerts::~CClCerts(void)
0x18000eeed  lea     rcx, [rbx+2F0h]; this
0x18000eef4  call    ??1CCookies@@QEAA@XZ; CCookies::~CCookies(void)
0x18000eef9  lea     rcx, [rbx+280h]; this
0x18000ef00  call    ??1CFormInputs@@QEAA@XZ; CFormInputs::~CFormInputs(void)
0x18000ef05  lea     rcx, [rbx+218h]; this
0x18000ef0c  call    ??1CServerVariables@@QEAA@XZ; CServerVariables::~CServerVariables(void)
0x18000ef11  lea     rcx, [rbx+1A8h]; this
0x18000ef18  call    ??1CQueryString@@QEAA@XZ; CQueryString::~CQueryString(void)
0x18000ef1d  test    byte ptr [rbx+48h], 2
0x18000ef21  lea     rax, ??_7CHashTable@@6B@; const CHashTable::`vftable'
0x18000ef28  mov     [rbx+40h], rax
0x18000ef2c  jnz     loc_180029E4C
0x18000ef32  mov     rcx, cs:?sm_pach@CRequestData@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CRequestData::sm_pach
0x18000ef39  mov     rsi, [rsp+28h+arg_0]
0x18000ef3e  test    rcx, rcx
0x18000ef41  jz      short loc_18000EF4C
0x18000ef43  mov     rdx, rbx
0x18000ef46  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000ef4c  xor     eax, eax
0x18000ef4e  add     rsp, 20h
0x18000ef52  pop     rbx
0x18000ef53  retn
0x180029da6  mov     [rsp+28h+arg_8], rdi
0x180029dab  mov     rax, [rcx]
0x180029dae  mov     edx, 1
0x180029db3  mov     rdi, [rcx+20h]
0x180029db7  mov     rax, [rax]
0x180029dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dbf  mov     rcx, rdi
0x180029dc2  test    rdi, rdi
0x180029dc5  jnz     short loc_180029DAB
0x180029dc7  mov     rdi, [rsp+28h+arg_8]
0x180029dcc  jmp     loc_18000EE78
0x180029dd1  mov     rax, [rcx]
0x180029dd4  mov     rax, [rax+10h]
0x180029dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ddd  nop
0x180029dde  jmp     loc_18000EE91
0x180029de3  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029dea  xor     edx, edx; dwFlags
0x180029dec  call    cs:__imp_HeapFree
0x180029df2  nop
0x180029df3  jmp     loc_18000EEA1
0x180029df8  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029dff  xor     edx, edx; dwFlags
0x180029e01  call    cs:__imp_HeapFree
0x180029e07  nop
0x180029e08  jmp     loc_18000EEB1
0x180029e0d  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029e14  xor     edx, edx; dwFlags
0x180029e16  call    cs:__imp_HeapFree
0x180029e1c  nop
0x180029e1d  jmp     loc_18000EEC1
0x180029e22  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029e29  xor     edx, edx; dwFlags
0x180029e2b  call    cs:__imp_HeapFree
0x180029e31  nop
0x180029e32  jmp     loc_18000EED1
0x180029e37  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029e3e  xor     edx, edx; dwFlags
0x180029e40  call    cs:__imp_HeapFree
0x180029e46  nop
0x180029e47  jmp     loc_18000EEE1
0x180029e4c  mov     r8, [rbx+60h]; lpMem
0x180029e50  xor     edx, edx; dwFlags
0x180029e52  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180029e59  call    cs:__imp_HeapFree
0x180029e5f  nop
0x180029e60  jmp     loc_18000EF32
```
