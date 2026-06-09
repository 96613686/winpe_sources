# CDUIResourceManager::InitThread(uint,DUI_RESOURCE_MANAGER_INIT_FLAGS)

- ea: `0x180040c0c`
- end: `0x180040d4a`
- name: `?InitThread@CDUIResourceManager@@QEAAJIW4DUI_RESOURCE_MANAGER_INIT_FLAGS@@@Z`
- size: `318`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800408e8`
- `0x1800596e0`
- `0x18005baec`
- `0x18007094c`
- `0x1800724b8`
- `0x180080fe4`

## callees

- `0x180040c0c`
- `0x1800d09ac`
- `0x1800d0af0`
- `0x1800d0be8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040d39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040d39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040c1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040c1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180040ca9`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180040ca9`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040d06`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180040d06`
- `DUI70!UnInitProcessPriv` at `0x180040cce`
- `DUI70!UnInitProcessPriv` at `0x180040d25`
- `DUI70!UnInitProcessPriv` at `0x180040cce`
- `DUI70!UnInitProcessPriv` at `0x180040d25`
- `DUI70!UnInitThread` at `0x180040cf7`
- `DUI70!UnInitThread` at `0x180040cf7`
- `DUI70!InitThread` at `0x180040cd8`
- `DUI70!InitThread` at `0x180040cd8`
- `DUI70!InitProcessPriv` at `0x180040c4d`
- `DUI70!InitProcessPriv` at `0x180040c4d`

## pseudocode

```c
__int64 __fastcall CDUIResourceManager::InitThread(__int64 a1, unsigned int a2)
{
  __int64 v4; // r8
  __int64 v5; // rcx
  int inited; // edi
  __int64 v7; // rsi
  int v8; // eax
  unsigned int i; // esi
  unsigned int v10; // edx
  DWORD v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // edx

  AcquireSRWLockExclusive((PSRWLOCK)a1);
  if ( !*(_DWORD *)(a1 + 12) )
  {
    LOBYTE(v4) = 1;
    inited = InitProcessPriv(14, &_ImageBase, v4);
    if ( inited < 0 )
      goto LABEL_24;
    v7 = 0;
    while ( (unsigned int)v7 < *(_DWORD *)(a1 + 40) )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 32) + 8 * v7))(v5);
      v7 = (unsigned int)(v7 + 1);
      inited = v8;
      if ( v8 < 0 )
        goto LABEL_16;
    }
    if ( *(_QWORD *)(a1 + 56) )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 64); ++i )
      {
        inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 56) + 16LL * i))(2LL * i);
        if ( inited < 0 )
        {
          v10 = i;
          goto LABEL_15;
        }
      }
    }
    v11 = TlsAlloc();
    *(_DWORD *)(a1 + 16) = v11;
    if ( v11 == -1 )
    {
      v10 = *(_DWORD *)(a1 + 64);
      inited = -2147467259;
LABEL_15:
      CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)a1, v10);
LABEL_16:
      UnInitProcessPriv(&_ImageBase);
      goto LABEL_24;
    }
  }
  inited = InitThread(a2);
  if ( inited >= 0 )
  {
    inited = CDUIResourceManager::_InitParserForThread((CDUIResourceManager *)a1);
    if ( inited >= 0 )
    {
      ++*(_DWORD *)(a1 + 12);
      SHKeepDUIInitializedForThread(a2);
      goto LABEL_24;
    }
    UnInitThread(v12);
  }
  if ( !*(_DWORD *)(a1 + 12) )
  {
    TlsFree(*(_DWORD *)(a1 + 16));
    v13 = *(_DWORD *)(a1 + 64);
    *(_DWORD *)(a1 + 16) = -1;
    CDUIResourceManager::_UnregisterElements((CDUIResourceManager *)a1, v13);
    UnInitProcessPriv(&_ImageBase);
  }
LABEL_24:
  ReleaseSRWLockExclusive((PSRWLOCK)a1);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180040c0c  push    rbx
0x180040c0e  push    rbp
0x180040c0f  push    rsi
0x180040c10  push    rdi
0x180040c11  sub     rsp, 38h
0x180040c15  mov     edi, r8d
0x180040c18  mov     ebp, edx
0x180040c1a  mov     rbx, rcx
0x180040c1d  call    cs:__imp_AcquireSRWLockExclusive
0x180040c23  cmp     dword ptr [rbx+0Ch], 0
0x180040c27  jnz     loc_180040CD6
0x180040c2d  shr     edi, 1
0x180040c2f  lea     rdx, __ImageBase
0x180040c36  mov     r9b, 1
0x180040c39  not     dil
0x180040c3c  and     dil, 1
0x180040c40  mov     r8b, r9b
0x180040c43  mov     ecx, 0Eh
0x180040c48  mov     [rsp+58h+var_38], dil
0x180040c4d  call    cs:__imp_InitProcessPriv
0x180040c53  mov     edi, eax
0x180040c55  test    eax, eax
0x180040c57  js      loc_180040D36
0x180040c5d  xor     esi, esi
0x180040c5f  cmp     esi, [rbx+28h]
0x180040c62  jnb     short loc_180040C7B
0x180040c64  mov     rax, [rbx+20h]
0x180040c68  mov     rax, [rax+rsi*8]
0x180040c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c71  inc     esi
0x180040c73  mov     edi, eax
0x180040c75  test    eax, eax
0x180040c77  jns     short loc_180040C5F
0x180040c79  jmp     short loc_180040CC7
0x180040c7b  cmp     qword ptr [rbx+38h], 0
0x180040c80  jz      short loc_180040CA9
0x180040c82  xor     esi, esi
0x180040c84  cmp     esi, [rbx+40h]
0x180040c87  jnb     short loc_180040CA9
0x180040c89  mov     rax, [rbx+38h]
0x180040c8d  mov     ecx, esi
0x180040c8f  add     rcx, rcx
0x180040c92  mov     rax, [rax+rcx*8]
0x180040c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c9b  mov     edi, eax
0x180040c9d  test    eax, eax
0x180040c9f  js      short loc_180040CA5
0x180040ca1  inc     esi
0x180040ca3  jmp     short loc_180040C84
0x180040ca5  mov     edx, esi
0x180040ca7  jmp     short loc_180040CBF
0x180040ca9  call    cs:__imp_TlsAlloc
0x180040caf  mov     [rbx+10h], eax
0x180040cb2  cmp     eax, 0FFFFFFFFh
0x180040cb5  jnz     short loc_180040CD6
0x180040cb7  mov     edx, [rbx+40h]; unsigned int
0x180040cba  mov     edi, 80004005h
0x180040cbf  mov     rcx, rbx; this
0x180040cc2  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x180040cc7  lea     rcx, __ImageBase
0x180040cce  call    cs:__imp_UnInitProcessPriv
0x180040cd4  jmp     short loc_180040D36
0x180040cd6  mov     ecx, ebp
0x180040cd8  call    cs:__imp_InitThread
0x180040cde  mov     edi, eax
0x180040ce0  test    eax, eax
0x180040ce2  js      short loc_180040CFD
0x180040ce4  mov     rcx, rbx; this
0x180040ce7  call    ?_InitParserForThread@CDUIResourceManager@@AEAAJXZ; CDUIResourceManager::_InitParserForThread(void)
0x180040cec  mov     edi, eax
0x180040cee  test    eax, eax
0x180040cf0  js      short loc_180040CF7
0x180040cf2  inc     dword ptr [rbx+0Ch]
0x180040cf5  jmp     short loc_180040D2F
0x180040cf7  call    cs:__imp_UnInitThread
0x180040cfd  cmp     dword ptr [rbx+0Ch], 0
0x180040d01  jnz     short loc_180040D36
0x180040d03  mov     ecx, [rbx+10h]; dwTlsIndex
0x180040d06  call    cs:__imp_TlsFree
0x180040d0c  mov     edx, [rbx+40h]; unsigned int
0x180040d0f  mov     rcx, rbx; this
0x180040d12  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180040d19  call    ?_UnregisterElements@CDUIResourceManager@@AEAAXI@Z; CDUIResourceManager::_UnregisterElements(uint)
0x180040d1e  lea     rcx, __ImageBase
0x180040d25  call    cs:__imp_UnInitProcessPriv
0x180040d2b  test    edi, edi
0x180040d2d  js      short loc_180040D36
0x180040d2f  mov     ecx, ebp; unsigned int
0x180040d31  call    ?SHKeepDUIInitializedForThread@@YAJI@Z; SHKeepDUIInitializedForThread(uint)
0x180040d36  mov     rcx, rbx; SRWLock
0x180040d39  call    cs:__imp_ReleaseSRWLockExclusive
0x180040d3f  mov     eax, edi
0x180040d41  add     rsp, 38h
0x180040d45  pop     rdi
0x180040d46  pop     rsi
0x180040d47  pop     rbp
0x180040d48  pop     rbx
0x180040d49  retn
```
