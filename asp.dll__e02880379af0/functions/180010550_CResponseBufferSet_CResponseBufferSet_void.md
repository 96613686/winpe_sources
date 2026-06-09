# CResponseBufferSet::~CResponseBufferSet(void)

- ea: `0x180010550`
- end: `0x180010623`
- name: `??1CResponseBufferSet@@QEAA@XZ`
- size: `211`
- prototype: `void __fastcall(CResponseBufferSet *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f0a0`
- `0x180050be4`

## callees

- `0x180010550`
- `0x180050b24`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002a9f4`
- `KERNEL32!HeapFree` at `0x18002aaef`
- `KERNEL32!HeapFree` at `0x18002ab61`
- `KERNEL32!HeapFree` at `0x18002a9f4`
- `KERNEL32!HeapFree` at `0x18002aaef`
- `KERNEL32!HeapFree` at `0x18002ab61`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800105dd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a9c8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002ab15`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800105dd`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002a9c8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002ab15`

## pseudocode

```c
void __fastcall CResponseBufferSet::~CResponseBufferSet(CResponseBufferSet *this)
{
  __int64 v2; // rbx
  unsigned int v3; // ebp
  unsigned int v4; // eax
  void *v5; // r8
  ALLOC_CACHE_HANDLER *v6; // rcx
  void *v7; // rbx
  unsigned int i; // ebx
  ALLOC_CACHE_HANDLER *v9; // rcx
  void *v10; // rdx
  __int64 v11; // rcx

  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    v3 = 0;
    if ( *(_DWORD *)(v2 + 2100) )
    {
      v9 = g_pachResponseBuffer;
      do
      {
        v10 = *(void **)(*(_QWORD *)(v2 + 2080) + 8LL * v3);
        if ( v10 && v9 )
        {
          ALLOC_CACHE_HANDLER::Free(v9, v10);
          v9 = g_pachResponseBuffer;
        }
        ++v3;
      }
      while ( v3 < *(_DWORD *)(v2 + 2100) );
    }
    if ( *(_DWORD *)(v2 + 2096) > 1u )
      HeapFree(g_hDenaliHeap, 0, *(LPVOID *)(v2 + 2080));
    v4 = *(_DWORD *)(v2 + 20);
    if ( (*(_BYTE *)(v2 + 24) & 1) != 0 )
      ++v4;
    if ( dword_18007E3F8 )
    {
      if ( v4 > 8 )
      {
        if ( v4 > 0x10 )
        {
          if ( v4 > 0x20 )
          {
            if ( v4 > 0x40 )
            {
              if ( v4 > 0x60 )
              {
                if ( v4 > 0x80 )
                {
                  if ( v4 > 0xC0 )
                  {
                    if ( v4 > 0x100 )
                    {
                      if ( v4 > 0x200 )
                      {
                        if ( v4 > 0x400 )
                        {
                          if ( v4 > 0x800 )
                          {
                            if ( v4 > 0x1000 )
                              _InterlockedIncrement(&dword_18007E3F4);
                            else
                              _InterlockedIncrement(&dword_18007E3F0);
                          }
                          else
                          {
                            _InterlockedIncrement(&dword_18007E3EC);
                          }
                        }
                        else
                        {
                          _InterlockedIncrement(&dword_18007E3E8);
                        }
                      }
                      else
                      {
                        _InterlockedIncrement(&dword_18007E3E4);
                      }
                    }
                    else
                    {
                      _InterlockedIncrement(&dword_18007E3E0);
                    }
                  }
                  else
                  {
                    _InterlockedIncrement(&dword_18007E3DC);
                  }
                }
                else
                {
                  _InterlockedIncrement(&dword_18007E3D8);
                }
              }
              else
              {
                _InterlockedIncrement(&dword_18007E3D4);
              }
            }
            else
            {
              _InterlockedIncrement(&dword_18007E3D0);
            }
          }
          else
          {
            _InterlockedIncrement(&dword_18007E3CC);
          }
        }
        else
        {
          _InterlockedIncrement(&dword_18007E3C8);
        }
      }
      else
      {
        _InterlockedIncrement(&dword_18007E3C4);
      }
    }
    v5 = *(void **)(v2 + 8);
    if ( v5 )
    {
      HeapFree(g_hDenaliHeap, 0, v5);
      *(_QWORD *)(v2 + 8) = 0;
    }
    *(_DWORD *)(v2 + 24) &= ~1u;
    v6 = CResponseBuffer::sm_pach;
    *(_QWORD *)(v2 + 16) = 0;
    *(_DWORD *)(v2 + 28) = 0;
    if ( v6 )
      ALLOC_CACHE_HANDLER::Free(v6, (void *)v2);
    *(_QWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    CResponseBuffer::~CResponseBuffer(*((CResponseBuffer **)this + 1));
    if ( CDebugResponseBuffer::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CDebugResponseBuffer::sm_pach, v7);
    *((_QWORD *)this + 1) = 0;
  }
  for ( i = 0; i < *((_DWORD *)this + 40); ++i )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 19) + 8LL * i);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 24) + 16LL))(v11 + 24);
  }
  if ( (*((_BYTE *)this + 168) & 2) != 0 )
    HeapFree(g_hDenaliHeap, 0, *((LPVOID *)this + 19));
}

```

## disassembly

```asm
0x180010550  push    rdi
0x180010552  sub     rsp, 20h
0x180010556  mov     [rsp+28h+arg_0], rbx
0x18001055b  mov     rdi, rcx
0x18001055e  mov     rbx, [rcx]
0x180010561  mov     [rsp+28h+arg_18], r14
0x180010566  xor     r14d, r14d
0x180010569  test    rbx, rbx
0x18001056c  jz      short loc_1800105E6
0x18001056e  mov     [rsp+28h+arg_8], rbp
0x180010573  mov     ebp, r14d
0x180010576  mov     [rsp+28h+arg_10], rsi
0x18001057b  cmp     [rbx+834h], r14d
0x180010582  ja      loc_18002A9AA
0x180010588  cmp     dword ptr [rbx+830h], 1
0x18001058f  mov     rbp, [rsp+28h+arg_8]
0x180010594  ja      loc_18002A9E4
0x18001059a  test    byte ptr [rbx+18h], 1
0x18001059e  mov     eax, [rbx+14h]
0x1800105a1  mov     rsi, [rsp+28h+arg_10]
0x1800105a6  jnz     short loc_18001061F
0x1800105a8  cmp     cs:dword_18007E3F8, r14d
0x1800105af  jnz     loc_18002AA00
0x1800105b5  mov     r8, [rbx+8]; lpMem
0x1800105b9  test    r8, r8
0x1800105bc  jnz     loc_18002AAE6
0x1800105c2  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x1800105c6  mov     rcx, cs:?sm_pach@CResponseBuffer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBuffer::sm_pach
0x1800105cd  mov     [rbx+10h], r14
0x1800105d1  mov     [rbx+1Ch], r14d
0x1800105d5  test    rcx, rcx
0x1800105d8  jz      short loc_1800105E3
0x1800105da  mov     rdx, rbx
0x1800105dd  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800105e3  mov     [rdi], r14
0x1800105e6  mov     rbx, [rdi+8]
0x1800105ea  test    rbx, rbx
0x1800105ed  jnz     loc_18002AAFE
0x1800105f3  mov     ebx, r14d
0x1800105f6  mov     r14, [rsp+28h+arg_18]
0x1800105fb  cmp     [rdi+0A0h], ebx
0x180010601  ja      loc_18002AB24
0x180010607  test    byte ptr [rdi+0A8h], 2
0x18001060e  mov     rbx, [rsp+28h+arg_0]
0x180010613  jnz     loc_18002AB51
0x180010619  add     rsp, 20h
0x18001061d  pop     rdi
0x18001061e  retn
0x18001061f  inc     eax
0x180010621  jmp     short loc_1800105A8
0x18002a9aa  mov     rcx, cs:?g_pachResponseBuffer@@3PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * g_pachResponseBuffer
0x18002a9b1  mov     rax, [rbx+820h]
0x18002a9b8  mov     edx, ebp
0x18002a9ba  mov     rdx, [rax+rdx*8]
0x18002a9be  test    rdx, rdx
0x18002a9c1  jz      short loc_18002A9D5
0x18002a9c3  test    rcx, rcx
0x18002a9c6  jz      short loc_18002A9D5
0x18002a9c8  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002a9ce  mov     rcx, cs:?g_pachResponseBuffer@@3PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * g_pachResponseBuffer
0x18002a9d5  inc     ebp
0x18002a9d7  cmp     ebp, [rbx+834h]
0x18002a9dd  jb      short loc_18002A9B1
0x18002a9df  jmp     loc_180010588
0x18002a9e4  mov     r8, [rbx+820h]; lpMem
0x18002a9eb  xor     edx, edx; dwFlags
0x18002a9ed  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002a9f4  call    cs:__imp_HeapFree
0x18002a9fa  nop
0x18002a9fb  jmp     loc_18001059A
0x18002aa00  cmp     eax, 8
0x18002aa03  ja      short loc_18002AA11
0x18002aa05  lock inc cs:dword_18007E3C4
0x18002aa0c  jmp     loc_1800105B5
0x18002aa11  cmp     eax, 10h
0x18002aa14  ja      short loc_18002AA22
0x18002aa16  lock inc cs:dword_18007E3C8
0x18002aa1d  jmp     loc_1800105B5
0x18002aa22  cmp     eax, 20h ; ' '
0x18002aa25  ja      short loc_18002AA33
0x18002aa27  lock inc cs:dword_18007E3CC
0x18002aa2e  jmp     loc_1800105B5
0x18002aa33  cmp     eax, 40h ; '@'
0x18002aa36  ja      short loc_18002AA44
0x18002aa38  lock inc cs:dword_18007E3D0
0x18002aa3f  jmp     loc_1800105B5
0x18002aa44  cmp     eax, 60h ; '`'
0x18002aa47  ja      short loc_18002AA55
0x18002aa49  lock inc cs:dword_18007E3D4
0x18002aa50  jmp     loc_1800105B5
0x18002aa55  cmp     eax, 80h
0x18002aa5a  ja      short loc_18002AA68
0x18002aa5c  lock inc cs:dword_18007E3D8
0x18002aa63  jmp     loc_1800105B5
0x18002aa68  cmp     eax, 0C0h
0x18002aa6d  ja      short loc_18002AA7B
0x18002aa6f  lock inc cs:dword_18007E3DC
0x18002aa76  jmp     loc_1800105B5
0x18002aa7b  cmp     eax, 100h
0x18002aa80  ja      short loc_18002AA8E
0x18002aa82  lock inc cs:dword_18007E3E0
0x18002aa89  jmp     loc_1800105B5
0x18002aa8e  cmp     eax, 200h
0x18002aa93  ja      short loc_18002AAA1
0x18002aa95  lock inc cs:dword_18007E3E4
0x18002aa9c  jmp     loc_1800105B5
0x18002aaa1  cmp     eax, 400h
0x18002aaa6  ja      short loc_18002AAB4
0x18002aaa8  lock inc cs:dword_18007E3E8
0x18002aaaf  jmp     loc_1800105B5
0x18002aab4  cmp     eax, 800h
0x18002aab9  ja      short loc_18002AAC7
0x18002aabb  lock inc cs:dword_18007E3EC
0x18002aac2  jmp     loc_1800105B5
0x18002aac7  cmp     eax, 1000h
0x18002aacc  ja      short loc_18002AADA
0x18002aace  lock inc cs:dword_18007E3F0
0x18002aad5  jmp     loc_1800105B5
0x18002aada  lock inc cs:dword_18007E3F4
0x18002aae1  jmp     loc_1800105B5
0x18002aae6  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002aaed  xor     edx, edx; dwFlags
0x18002aaef  call    cs:__imp_HeapFree
0x18002aaf5  mov     [rbx+8], r14
0x18002aaf9  jmp     loc_1800105C2
0x18002aafe  mov     rcx, rbx; this
0x18002ab01  call    ??1CResponseBuffer@@QEAA@XZ; CResponseBuffer::~CResponseBuffer(void)
0x18002ab06  mov     rcx, cs:?sm_pach@CDebugResponseBuffer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CDebugResponseBuffer::sm_pach
0x18002ab0d  test    rcx, rcx
0x18002ab10  jz      short loc_18002AB1B
0x18002ab12  mov     rdx, rbx
0x18002ab15  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002ab1b  mov     [rdi+8], r14
0x18002ab1f  jmp     loc_1800105F3
0x18002ab24  mov     rax, [rdi+98h]
0x18002ab2b  mov     ecx, ebx
0x18002ab2d  mov     rcx, [rax+rcx*8]
0x18002ab31  mov     rax, [rcx+18h]
0x18002ab35  add     rcx, 18h
0x18002ab39  mov     rax, [rax+10h]
0x18002ab3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab42  inc     ebx
0x18002ab44  cmp     ebx, [rdi+0A0h]
0x18002ab4a  jb      short loc_18002AB24
0x18002ab4c  jmp     loc_180010607
0x18002ab51  mov     r8, [rdi+98h]; lpMem
0x18002ab58  xor     edx, edx; dwFlags
0x18002ab5a  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002ab61  call    cs:__imp_HeapFree
0x18002ab67  nop
0x18002ab68  jmp     loc_180010619
```
