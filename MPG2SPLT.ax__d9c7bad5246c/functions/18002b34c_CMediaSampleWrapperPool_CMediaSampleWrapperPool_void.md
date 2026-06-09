# CMediaSampleWrapperPool::~CMediaSampleWrapperPool(void)

- ea: `0x18002b34c`
- end: `0x18002b45b`
- name: `??1CMediaSampleWrapperPool@@UEAA@XZ`
- size: `271`
- prototype: `void __fastcall(CMediaSampleWrapperPool *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002b4b0`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18002b34c`
- `0x180034010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002b400`
- `KERNEL32!CloseHandle` at `0x18002b400`
- `KERNEL32!DeleteCriticalSection` at `0x18002b39b`
- `KERNEL32!DeleteCriticalSection` at `0x18002b3d2`
- `KERNEL32!DeleteCriticalSection` at `0x18002b412`
- `KERNEL32!DeleteCriticalSection` at `0x18002b39b`
- `KERNEL32!DeleteCriticalSection` at `0x18002b3d2`
- `KERNEL32!DeleteCriticalSection` at `0x18002b412`

## pseudocode

```c
void __fastcall CMediaSampleWrapperPool::~CMediaSampleWrapperPool(CMediaSampleWrapperPool *this)
{
  unsigned int v1; // edi
  __int64 *v3; // rdx
  __int64 *v4; // rax
  char *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rdi
  void *v8; // rcx
  volatile signed __int32 *v9; // rbx

  v1 = 0;
  for ( *(_QWORD *)this = &CMediaSampleWrapperPool::`vftable'; v1 < *((_DWORD *)this + 12); ++v1 )
  {
    v3 = (__int64 *)*((_QWORD *)this + 4);
    v4 = (__int64 *)v3[1];
    v5 = (char *)(v3 - 18);
    v6 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v6 + 8) = v4;
    if ( v3 != (__int64 *)144 )
    {
      *(_QWORD *)v5 = &CMediaSampleWrapper::`vftable';
      DeleteCriticalSection((LPCRITICAL_SECTION)(v5 + 96));
      operator delete(v5, 0xA0u);
    }
  }
  v7 = *((_QWORD *)this + 16);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 40), 0xFFFFFFFF) == 1 && v7 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)v7);
    operator delete((void *)v7, 0x30u);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 14) + 24LL) + 16LL))(*((_QWORD *)this + 14) + 24LL);
  v8 = (void *)*((_QWORD *)this + 12);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 12) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *(_QWORD *)this = &CBufferSource::`vftable';
  v9 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( !_InterlockedDecrement(v9 + 10) )
  {
    if ( v9 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v9);
      operator delete((void *)v9, 0x2530u);
    }
  }
}

```

## disassembly

```asm
0x18002b34c  mov     [rsp+arg_8], rbx
0x18002b351  mov     [rsp+arg_10], rsi
0x18002b356  push    rdi
0x18002b357  sub     rsp, 20h
0x18002b35b  xor     edi, edi
0x18002b35d  lea     rax, ??_7CMediaSampleWrapperPool@@6B@; const CMediaSampleWrapperPool::`vftable'
0x18002b364  mov     rbx, rcx
0x18002b367  mov     [rcx], rax
0x18002b36a  cmp     [rcx+30h], edi
0x18002b36d  jbe     short loc_18002B3B5
0x18002b36f  mov     rdx, [rbx+20h]
0x18002b373  mov     rax, [rdx+8]
0x18002b377  lea     rsi, [rdx-90h]
0x18002b37e  mov     rcx, [rdx]
0x18002b381  mov     [rax], rcx
0x18002b384  mov     [rcx+8], rax
0x18002b388  test    rsi, rsi
0x18002b38b  jz      short loc_18002B3AE
0x18002b38d  lea     rax, ??_7CMediaSampleWrapper@@6B@; const CMediaSampleWrapper::`vftable'
0x18002b394  lea     rcx, [rsi+60h]; lpCriticalSection
0x18002b398  mov     [rsi], rax
0x18002b39b  call    cs:__imp_DeleteCriticalSection
0x18002b3a1  mov     edx, 0A0h; unsigned __int64
0x18002b3a6  mov     rcx, rsi; void *
0x18002b3a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b3ae  inc     edi
0x18002b3b0  cmp     edi, [rbx+30h]
0x18002b3b3  jb      short loc_18002B36F
0x18002b3b5  mov     rdi, [rbx+80h]
0x18002b3bc  or      esi, 0FFFFFFFFh
0x18002b3bf  mov     eax, esi
0x18002b3c1  lock xadd [rdi+28h], eax
0x18002b3c6  add     eax, esi
0x18002b3c8  jnz     short loc_18002B3E3
0x18002b3ca  test    rdi, rdi
0x18002b3cd  jz      short loc_18002B3E3
0x18002b3cf  mov     rcx, rdi; lpCriticalSection
0x18002b3d2  call    cs:__imp_DeleteCriticalSection
0x18002b3d8  lea     edx, [rsi+31h]; unsigned __int64
0x18002b3db  mov     rcx, rdi; void *
0x18002b3de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b3e3  mov     rcx, [rbx+70h]
0x18002b3e7  add     rcx, 18h
0x18002b3eb  mov     rax, [rcx]
0x18002b3ee  mov     rax, [rax+10h]
0x18002b3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f7  mov     rcx, [rbx+60h]; hObject
0x18002b3fb  test    rcx, rcx
0x18002b3fe  jz      short loc_18002B40E
0x18002b400  call    cs:__imp_CloseHandle
0x18002b406  mov     qword ptr [rbx+60h], 0
0x18002b40e  lea     rcx, [rbx+38h]; lpCriticalSection
0x18002b412  call    cs:__imp_DeleteCriticalSection
0x18002b418  lea     rax, ??_7CBufferSource@@6B@; const CBufferSource::`vftable'
0x18002b41f  mov     [rbx], rax
0x18002b422  mov     eax, esi
0x18002b424  mov     rbx, [rbx+10h]
0x18002b428  lock xadd [rbx+28h], eax
0x18002b42d  add     eax, esi
0x18002b42f  jnz     short loc_18002B44B
0x18002b431  test    rbx, rbx
0x18002b434  jz      short loc_18002B44B
0x18002b436  mov     rcx, rbx; this
0x18002b439  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002b43e  mov     edx, 2530h; unsigned __int64
0x18002b443  mov     rcx, rbx; void *
0x18002b446  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b44b  mov     rbx, [rsp+28h+arg_8]
0x18002b450  mov     rsi, [rsp+28h+arg_10]
0x18002b455  add     rsp, 20h
0x18002b459  pop     rdi
0x18002b45a  retn
```
