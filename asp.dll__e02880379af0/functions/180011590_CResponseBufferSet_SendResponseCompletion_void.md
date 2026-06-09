# CResponseBufferSet::SendResponseCompletion(void *)

- ea: `0x180011590`
- end: `0x1800116ad`
- name: `?SendResponseCompletion@CResponseBufferSet@@SAXPEAX@Z`
- size: `285`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e460`
- `0x180012628`

## callees

- `0x180011590`
- `0x180050b24`
- `0x180064010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002b01c`
- `KERNEL32!HeapFree` at `0x18002b117`
- `KERNEL32!HeapFree` at `0x18002b189`
- `KERNEL32!HeapFree` at `0x18002b01c`
- `KERNEL32!HeapFree` at `0x18002b117`
- `KERNEL32!HeapFree` at `0x18002b189`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800115eb`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180011657`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800116a1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002b13d`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800115eb`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180011657`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800116a1`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18002b13d`

## pseudocode

```c
void __fastcall CResponseBufferSet::SendResponseCompletion(__int64 *a1)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  ALLOC_CACHE_HANDLER *v4; // rcx
  void *v5; // rdx
  unsigned int v6; // eax
  void *v7; // r8
  ALLOC_CACHE_HANDLER *v8; // rcx
  void *v9; // rbx
  unsigned int i; // ebx
  __int64 v11; // rcx

  if ( a1 )
  {
    v2 = *a1;
    if ( *a1 )
    {
      v3 = 0;
      if ( *(_DWORD *)(v2 + 2100) )
      {
        v4 = g_pachResponseBuffer;
        do
        {
          v5 = *(void **)(*(_QWORD *)(v2 + 2080) + 8LL * v3);
          if ( v5 && v4 )
          {
            ALLOC_CACHE_HANDLER::Free(v4, v5);
            v4 = g_pachResponseBuffer;
          }
          ++v3;
        }
        while ( v3 < *(_DWORD *)(v2 + 2100) );
      }
      if ( *(_DWORD *)(v2 + 2096) > 1u )
        HeapFree(g_hDenaliHeap, 0, *(LPVOID *)(v2 + 2080));
      v6 = *(_DWORD *)(v2 + 20);
      if ( (*(_BYTE *)(v2 + 24) & 1) != 0 )
        ++v6;
      if ( dword_18007E3F8 )
      {
        if ( v6 > 8 )
        {
          if ( v6 > 0x10 )
          {
            if ( v6 > 0x20 )
            {
              if ( v6 > 0x40 )
              {
                if ( v6 > 0x60 )
                {
                  if ( v6 > 0x80 )
                  {
                    if ( v6 > 0xC0 )
                    {
                      if ( v6 > 0x100 )
                      {
                        if ( v6 > 0x200 )
                        {
                          if ( v6 > 0x400 )
                          {
                            if ( v6 > 0x800 )
                            {
                              if ( v6 > 0x1000 )
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
      v7 = *(void **)(v2 + 8);
      if ( v7 )
      {
        HeapFree(g_hDenaliHeap, 0, v7);
        *(_QWORD *)(v2 + 8) = 0;
      }
      *(_DWORD *)(v2 + 24) &= ~1u;
      v8 = CResponseBuffer::sm_pach;
      *(_QWORD *)(v2 + 16) = 0;
      *(_DWORD *)(v2 + 28) = 0;
      if ( v8 )
        ALLOC_CACHE_HANDLER::Free(v8, (void *)v2);
      *a1 = 0;
    }
    v9 = (void *)a1[1];
    if ( v9 )
    {
      CResponseBuffer::~CResponseBuffer((CResponseBuffer *)a1[1]);
      if ( CDebugResponseBuffer::sm_pach )
        ALLOC_CACHE_HANDLER::Free(CDebugResponseBuffer::sm_pach, v9);
      a1[1] = 0;
    }
    for ( i = 0; i < *((_DWORD *)a1 + 40); ++i )
    {
      v11 = *(_QWORD *)(a1[19] + 8LL * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 24) + 16LL))(v11 + 24);
    }
    if ( (a1[21] & 2) != 0 )
      HeapFree(g_hDenaliHeap, 0, (LPVOID)a1[19]);
    if ( CResponseBufferSet::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CResponseBufferSet::sm_pach, a1);
  }
}

```

## disassembly

```asm
0x180011590  test    rcx, rcx
0x180011593  jz      locret_1800116AC
0x180011599  push    rdi
0x18001159a  sub     rsp, 20h
0x18001159e  mov     [rsp+28h+arg_0], rbx
0x1800115a3  mov     rdi, rcx
0x1800115a6  mov     rbx, [rcx]
0x1800115a9  mov     [rsp+28h+arg_8], rbp
0x1800115ae  xor     ebp, ebp
0x1800115b0  test    rbx, rbx
0x1800115b3  jz      loc_180011660
0x1800115b9  mov     [rsp+28h+arg_10], rsi
0x1800115be  mov     esi, ebp
0x1800115c0  mov     [rsp+28h+arg_18], r14
0x1800115c5  cmp     [rbx+834h], ebp
0x1800115cb  jbe     short loc_180011602
0x1800115cd  mov     rcx, cs:?g_pachResponseBuffer@@3PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * g_pachResponseBuffer
0x1800115d4  mov     rax, [rbx+820h]
0x1800115db  mov     edx, esi
0x1800115dd  mov     rdx, [rax+rdx*8]
0x1800115e1  test    rdx, rdx
0x1800115e4  jz      short loc_1800115F8
0x1800115e6  test    rcx, rcx
0x1800115e9  jz      short loc_1800115F8
0x1800115eb  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800115f1  mov     rcx, cs:?g_pachResponseBuffer@@3PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * g_pachResponseBuffer
0x1800115f8  inc     esi
0x1800115fa  cmp     esi, [rbx+834h]
0x180011600  jb      short loc_1800115D4
0x180011602  cmp     dword ptr [rbx+830h], 1
0x180011609  mov     rsi, [rsp+28h+arg_10]
0x18001160e  ja      loc_18002B00C
0x180011614  test    byte ptr [rbx+18h], 1
0x180011618  mov     eax, [rbx+14h]
0x18001161b  mov     r14, [rsp+28h+arg_18]
0x180011620  jz      short loc_180011624
0x180011622  inc     eax
0x180011624  cmp     cs:dword_18007E3F8, ebp
0x18001162a  jnz     loc_18002B028
0x180011630  mov     r8, [rbx+8]; lpMem
0x180011634  test    r8, r8
0x180011637  jnz     loc_18002B10E
0x18001163d  and     dword ptr [rbx+18h], 0FFFFFFFEh
0x180011641  mov     rcx, cs:?sm_pach@CResponseBuffer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBuffer::sm_pach
0x180011648  mov     [rbx+10h], rbp
0x18001164c  mov     [rbx+1Ch], ebp
0x18001164f  test    rcx, rcx
0x180011652  jz      short loc_18001165D
0x180011654  mov     rdx, rbx
0x180011657  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001165d  mov     [rdi], rbp
0x180011660  mov     rbx, [rdi+8]
0x180011664  test    rbx, rbx
0x180011667  jnz     loc_18002B126
0x18001166d  mov     ebx, ebp
0x18001166f  mov     rbp, [rsp+28h+arg_8]
0x180011674  cmp     [rdi+0A0h], ebx
0x18001167a  ja      loc_18002B14C
0x180011680  test    byte ptr [rdi+0A8h], 2
0x180011687  mov     rbx, [rsp+28h+arg_0]
0x18001168c  jnz     loc_18002B179
0x180011692  mov     rcx, cs:?sm_pach@CResponseBufferSet@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CResponseBufferSet::sm_pach
0x180011699  test    rcx, rcx
0x18001169c  jz      short loc_1800116A7
0x18001169e  mov     rdx, rdi
0x1800116a1  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800116a7  add     rsp, 20h
0x1800116ab  pop     rdi
0x1800116ac  retn
0x18002b00c  mov     r8, [rbx+820h]; lpMem
0x18002b013  xor     edx, edx; dwFlags
0x18002b015  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002b01c  call    cs:__imp_HeapFree
0x18002b022  nop
0x18002b023  jmp     loc_180011614
0x18002b028  cmp     eax, 8
0x18002b02b  ja      short loc_18002B039
0x18002b02d  lock inc cs:dword_18007E3C4
0x18002b034  jmp     loc_180011630
0x18002b039  cmp     eax, 10h
0x18002b03c  ja      short loc_18002B04A
0x18002b03e  lock inc cs:dword_18007E3C8
0x18002b045  jmp     loc_180011630
0x18002b04a  cmp     eax, 20h ; ' '
0x18002b04d  ja      short loc_18002B05B
0x18002b04f  lock inc cs:dword_18007E3CC
0x18002b056  jmp     loc_180011630
0x18002b05b  cmp     eax, 40h ; '@'
0x18002b05e  ja      short loc_18002B06C
0x18002b060  lock inc cs:dword_18007E3D0
0x18002b067  jmp     loc_180011630
0x18002b06c  cmp     eax, 60h ; '`'
0x18002b06f  ja      short loc_18002B07D
0x18002b071  lock inc cs:dword_18007E3D4
0x18002b078  jmp     loc_180011630
0x18002b07d  cmp     eax, 80h
0x18002b082  ja      short loc_18002B090
0x18002b084  lock inc cs:dword_18007E3D8
0x18002b08b  jmp     loc_180011630
0x18002b090  cmp     eax, 0C0h
0x18002b095  ja      short loc_18002B0A3
0x18002b097  lock inc cs:dword_18007E3DC
0x18002b09e  jmp     loc_180011630
0x18002b0a3  cmp     eax, 100h
0x18002b0a8  ja      short loc_18002B0B6
0x18002b0aa  lock inc cs:dword_18007E3E0
0x18002b0b1  jmp     loc_180011630
0x18002b0b6  cmp     eax, 200h
0x18002b0bb  ja      short loc_18002B0C9
0x18002b0bd  lock inc cs:dword_18007E3E4
0x18002b0c4  jmp     loc_180011630
0x18002b0c9  cmp     eax, 400h
0x18002b0ce  ja      short loc_18002B0DC
0x18002b0d0  lock inc cs:dword_18007E3E8
0x18002b0d7  jmp     loc_180011630
0x18002b0dc  cmp     eax, 800h
0x18002b0e1  ja      short loc_18002B0EF
0x18002b0e3  lock inc cs:dword_18007E3EC
0x18002b0ea  jmp     loc_180011630
0x18002b0ef  cmp     eax, 1000h
0x18002b0f4  ja      short loc_18002B102
0x18002b0f6  lock inc cs:dword_18007E3F0
0x18002b0fd  jmp     loc_180011630
0x18002b102  lock inc cs:dword_18007E3F4
0x18002b109  jmp     loc_180011630
0x18002b10e  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002b115  xor     edx, edx; dwFlags
0x18002b117  call    cs:__imp_HeapFree
0x18002b11d  mov     [rbx+8], rbp
0x18002b121  jmp     loc_18001163D
0x18002b126  mov     rcx, rbx; this
0x18002b129  call    ??1CResponseBuffer@@QEAA@XZ; CResponseBuffer::~CResponseBuffer(void)
0x18002b12e  mov     rcx, cs:?sm_pach@CDebugResponseBuffer@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CDebugResponseBuffer::sm_pach
0x18002b135  test    rcx, rcx
0x18002b138  jz      short loc_18002B143
0x18002b13a  mov     rdx, rbx
0x18002b13d  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18002b143  mov     [rdi+8], rbp
0x18002b147  jmp     loc_18001166D
0x18002b14c  mov     rax, [rdi+98h]
0x18002b153  mov     ecx, ebx
0x18002b155  mov     rcx, [rax+rcx*8]
0x18002b159  mov     rax, [rcx+18h]
0x18002b15d  add     rcx, 18h
0x18002b161  mov     rax, [rax+10h]
0x18002b165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b16a  inc     ebx
0x18002b16c  cmp     ebx, [rdi+0A0h]
0x18002b172  jb      short loc_18002B14C
0x18002b174  jmp     loc_180011680
0x18002b179  mov     r8, [rdi+98h]; lpMem
0x18002b180  xor     edx, edx; dwFlags
0x18002b182  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002b189  call    cs:__imp_HeapFree
0x18002b18f  nop
0x18002b190  jmp     loc_180011692
```
