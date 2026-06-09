# CMFTSimpleBase::~CMFTSimpleBase(void)

- ea: `0x180001ff4`
- end: `0x1800020fe`
- name: `??1CMFTSimpleBase@@UEAA@XZ`
- size: `266`
- prototype: `void __fastcall(CMFTSimpleBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001f78`

## callees

- `0x180001144`
- `0x180001ff4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002005`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002005`

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
0x180001ff4  push    rbx
0x180001ff6  push    rsi
0x180001ff7  push    rdi
0x180001ff8  push    r14
0x180001ffa  sub     rsp, 28h
0x180001ffe  mov     rbx, rcx
0x180002001  add     rcx, 68h ; 'h'; lpCriticalSection
0x180002005  call    cs:__imp_DeleteCriticalSection
0x18000200b  xor     esi, esi
0x18000200d  lea     rdi, [rbx+10h]
0x180002011  cmp     [rbx+8], esi
0x180002014  jbe     short loc_180002046
0x180002016  mov     r14d, esi
0x180002019  add     r14, r14
0x18000201c  mov     rax, [rdi]
0x18000201f  mov     rcx, [rax+r14*8]
0x180002023  test    rcx, rcx
0x180002026  jz      short loc_18000203F
0x180002028  mov     rax, [rcx]
0x18000202b  mov     rax, [rax+10h]
0x18000202f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002034  mov     rax, [rdi]
0x180002037  mov     qword ptr [rax+r14*8], 0
0x18000203f  inc     esi
0x180002041  cmp     esi, [rbx+8]
0x180002044  jb      short loc_180002016
0x180002046  mov     rcx, [rdi]; Block
0x180002049  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000204e  mov     dword ptr [rbx+8], 0
0x180002055  xor     edi, edi
0x180002057  cmp     [rbx+18h], edi
0x18000205a  jbe     short loc_18000208D
0x18000205c  mov     esi, edi
0x18000205e  add     rsi, rsi
0x180002061  mov     rax, [rbx+20h]
0x180002065  mov     rcx, [rax+rsi*8]
0x180002069  test    rcx, rcx
0x18000206c  jz      short loc_180002086
0x18000206e  mov     rax, [rcx]
0x180002071  mov     rax, [rax+10h]
0x180002075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000207a  mov     rax, [rbx+20h]
0x18000207e  mov     qword ptr [rax+rsi*8], 0
0x180002086  inc     edi
0x180002088  cmp     edi, [rbx+18h]
0x18000208b  jb      short loc_18000205C
0x18000208d  mov     rcx, [rbx+20h]; Block
0x180002091  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002096  mov     dword ptr [rbx+18h], 0
0x18000209d  mov     rcx, [rbx+28h]
0x1800020a1  test    rcx, rcx
0x1800020a4  jz      short loc_1800020BA
0x1800020a6  mov     rax, [rcx]
0x1800020a9  mov     rax, [rax+10h]
0x1800020ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020b2  mov     qword ptr [rbx+28h], 0
0x1800020ba  mov     rcx, [rbx+50h]
0x1800020be  test    rcx, rcx
0x1800020c1  jz      short loc_1800020D7
0x1800020c3  mov     rax, [rcx]
0x1800020c6  mov     rax, [rax+10h]
0x1800020ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cf  mov     qword ptr [rbx+50h], 0
0x1800020d7  mov     rcx, [rbx+48h]
0x1800020db  test    rcx, rcx
0x1800020de  jz      short loc_1800020F4
0x1800020e0  mov     rax, [rcx]
0x1800020e3  mov     rax, [rax+10h]
0x1800020e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ec  mov     qword ptr [rbx+48h], 0
0x1800020f4  add     rsp, 28h
0x1800020f8  pop     r14
0x1800020fa  pop     rdi
0x1800020fb  pop     rsi
0x1800020fc  pop     rbx
0x1800020fd  retn
```
