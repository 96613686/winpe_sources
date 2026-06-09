# CMFTSimpleBase::~CMFTSimpleBase(void)

- ea: `0x18001b34c`
- end: `0x18001b456`
- name: `??1CMFTSimpleBase@@UEAA@XZ`
- size: `266`
- prototype: `void __fastcall(CMFTSimpleBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001b45c`
- `0x180022f76`

## callees

- `0x180001434`
- `0x18001b34c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b35d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b35d`

## pseudocode

```c
void __fastcall CMFTSimpleBase::~CMFTSimpleBase(CMFTSimpleBase *this)
{
  unsigned int v2; // esi
  void **i; // rdi
  __int64 v4; // rcx
  unsigned int j; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v2 = 0;
  for ( i = (void **)((char *)this + 16); v2 < *((_DWORD *)this + 2); ++v2 )
  {
    v4 = *((_QWORD *)*i + 2 * v2);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_QWORD *)*i + 2 * v2) = 0;
    }
  }
  operator delete(*i);
  *((_DWORD *)this + 2) = 0;
  for ( j = 0; j < *((_DWORD *)this + 6); ++j )
  {
    v6 = *(_QWORD *)(*((_QWORD *)this + 4) + 16LL * j);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL * j) = 0;
    }
  }
  operator delete(*((void **)this + 4));
  *((_DWORD *)this + 6) = 0;
  v7 = *((_QWORD *)this + 5);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 5) = 0;
  }
  v8 = *((_QWORD *)this + 10);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 10) = 0;
  }
  v9 = *((_QWORD *)this + 9);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x18001b34c  push    rbx
0x18001b34e  push    rsi
0x18001b34f  push    rdi
0x18001b350  push    r14
0x18001b352  sub     rsp, 28h
0x18001b356  mov     rbx, rcx
0x18001b359  add     rcx, 68h ; 'h'; lpCriticalSection
0x18001b35d  call    cs:__imp_DeleteCriticalSection
0x18001b363  xor     esi, esi
0x18001b365  lea     rdi, [rbx+10h]
0x18001b369  cmp     [rbx+8], esi
0x18001b36c  jbe     short loc_18001B39E
0x18001b36e  mov     r14d, esi
0x18001b371  add     r14, r14
0x18001b374  mov     rax, [rdi]
0x18001b377  mov     rcx, [rax+r14*8]
0x18001b37b  test    rcx, rcx
0x18001b37e  jz      short loc_18001B397
0x18001b380  mov     rax, [rcx]
0x18001b383  mov     rax, [rax+10h]
0x18001b387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b38c  mov     rax, [rdi]
0x18001b38f  mov     qword ptr [rax+r14*8], 0
0x18001b397  inc     esi
0x18001b399  cmp     esi, [rbx+8]
0x18001b39c  jb      short loc_18001B36E
0x18001b39e  mov     rcx, [rdi]; Block
0x18001b3a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b3a6  mov     dword ptr [rbx+8], 0
0x18001b3ad  xor     edi, edi
0x18001b3af  cmp     [rbx+18h], edi
0x18001b3b2  jbe     short loc_18001B3E5
0x18001b3b4  mov     esi, edi
0x18001b3b6  add     rsi, rsi
0x18001b3b9  mov     rax, [rbx+20h]
0x18001b3bd  mov     rcx, [rax+rsi*8]
0x18001b3c1  test    rcx, rcx
0x18001b3c4  jz      short loc_18001B3DE
0x18001b3c6  mov     rax, [rcx]
0x18001b3c9  mov     rax, [rax+10h]
0x18001b3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d2  mov     rax, [rbx+20h]
0x18001b3d6  mov     qword ptr [rax+rsi*8], 0
0x18001b3de  inc     edi
0x18001b3e0  cmp     edi, [rbx+18h]
0x18001b3e3  jb      short loc_18001B3B4
0x18001b3e5  mov     rcx, [rbx+20h]; Block
0x18001b3e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b3ee  mov     dword ptr [rbx+18h], 0
0x18001b3f5  mov     rcx, [rbx+28h]
0x18001b3f9  test    rcx, rcx
0x18001b3fc  jz      short loc_18001B412
0x18001b3fe  mov     rax, [rcx]
0x18001b401  mov     rax, [rax+10h]
0x18001b405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b40a  mov     qword ptr [rbx+28h], 0
0x18001b412  mov     rcx, [rbx+50h]
0x18001b416  test    rcx, rcx
0x18001b419  jz      short loc_18001B42F
0x18001b41b  mov     rax, [rcx]
0x18001b41e  mov     rax, [rax+10h]
0x18001b422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b427  mov     qword ptr [rbx+50h], 0
0x18001b42f  mov     rcx, [rbx+48h]
0x18001b433  test    rcx, rcx
0x18001b436  jz      short loc_18001B44C
0x18001b438  mov     rax, [rcx]
0x18001b43b  mov     rax, [rax+10h]
0x18001b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b444  mov     qword ptr [rbx+48h], 0
0x18001b44c  add     rsp, 28h
0x18001b450  pop     r14
0x18001b452  pop     rdi
0x18001b453  pop     rsi
0x18001b454  pop     rbx
0x18001b455  retn
```
