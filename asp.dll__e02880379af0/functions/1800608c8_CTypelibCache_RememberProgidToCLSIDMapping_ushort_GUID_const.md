# CTypelibCache::RememberProgidToCLSIDMapping(ushort *,_GUID const &)

- ea: `0x1800608c8`
- end: `0x180060a0b`
- name: `?RememberProgidToCLSIDMapping@CTypelibCache@@QEAAJPEAGAEBU_GUID@@@Z`
- size: `323`
- prototype: `int(CTypelibCache *__hidden this, unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005bfbc`

## callees

- `0x180006ed4`
- `0x180007228`
- `0x180060870`
- `0x1800608c8`
- `0x180064010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180060905`
- `KERNEL32!LeaveCriticalSection` at `0x1800609dc`
- `KERNEL32!LeaveCriticalSection` at `0x180060905`
- `KERNEL32!LeaveCriticalSection` at `0x1800609dc`
- `KERNEL32!EnterCriticalSection` at `0x1800608e0`
- `KERNEL32!EnterCriticalSection` at `0x1800609a1`
- `KERNEL32!EnterCriticalSection` at `0x1800608e0`
- `KERNEL32!EnterCriticalSection` at `0x1800609a1`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18006091e`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18006091e`

## pseudocode

```c
__int64 __fastcall CTypelibCache::RememberProgidToCLSIDMapping(
        CTypelibCache *this,
        unsigned __int16 *a2,
        const struct _GUID *a3)
{
  struct CLinkElem *Elem; // rbx
  char *v7; // rax
  struct CLinkElem *v8; // rbx
  int v9; // ebp
  BOOL v10; // edi
  int v11; // r8d

  EnterCriticalSection(&stru_18007D278);
  Elem = CHashTable::FindElem((CHashTable *)&qword_18007D178, a3, 16);
  LeaveCriticalSection(&stru_18007D278);
  if ( Elem )
    return 0;
  v7 = (char *)ALLOC_CACHE_HANDLER::Alloc(CTypelibCacheEntry::sm_pach);
  v8 = (struct CLinkElem *)v7;
  if ( !v7 )
    return 2147942414LL;
  *((_DWORD *)v7 + 10) &= 0xFFFFFFF8;
  *((_WORD *)v7 + 10) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 1) = 0;
  *((_DWORD *)v7 + 4) = 0;
  *(_QWORD *)v7 = &CTypelibCacheEntry::`vftable';
  *((_QWORD *)v7 + 6) = 0;
  *((_DWORD *)v7 + 18) = 0;
  *((_DWORD *)v7 + 19) = -1;
  *(GUID *)(v7 + 56) = GUID_NULL;
  *((_DWORD *)v7 + 20) = -1;
  *((_DWORD *)v7 + 21) = -1;
  v9 = CTypelibCacheEntry::InitByCLSID((CTypelibCacheEntry *)v7, a3, a2);
  if ( v9 < 0 )
    goto LABEL_8;
  v10 = 0;
  EnterCriticalSection(&stru_18007D278);
  if ( !CHashTable::FindElem((CHashTable *)&qword_18007D178, a3, 16) )
    v10 = CHashTable::AddElem((CHashTable *)&qword_18007D178, v8, v11) != 0;
  LeaveCriticalSection(&stru_18007D278);
  if ( !v10 )
LABEL_8:
    (**(void (__fastcall ***)(struct CLinkElem *, __int64))v8)(v8, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800608c8  push    rbx
0x1800608ca  push    rbp
0x1800608cb  push    rsi
0x1800608cc  push    rdi
0x1800608cd  push    r13
0x1800608cf  sub     rsp, 20h
0x1800608d3  lea     rcx, stru_18007D278; lpCriticalSection
0x1800608da  mov     rsi, r8
0x1800608dd  mov     rdi, rdx
0x1800608e0  call    cs:__imp_EnterCriticalSection
0x1800608e6  mov     r8d, 10h; int
0x1800608ec  lea     rcx, qword_18007D178; this
0x1800608f3  mov     rdx, rsi; void *
0x1800608f6  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x1800608fb  lea     rcx, stru_18007D278; lpCriticalSection
0x180060902  mov     rbx, rax
0x180060905  call    cs:__imp_LeaveCriticalSection
0x18006090b  test    rbx, rbx
0x18006090e  jz      short loc_180060917
0x180060910  xor     eax, eax
0x180060912  jmp     loc_180060A00
0x180060917  mov     rcx, cs:?sm_pach@CTypelibCacheEntry@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CTypelibCacheEntry::sm_pach
0x18006091e  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180060924  mov     rbx, rax
0x180060927  test    rax, rax
0x18006092a  jz      loc_1800609FB
0x180060930  and     dword ptr [rbx+28h], 0FFFFFFF8h
0x180060934  xor     ecx, ecx
0x180060936  mov     [rax+14h], cx
0x18006093a  mov     r8, rdi; unsigned __int16 *
0x18006093d  mov     [rax+18h], rcx
0x180060941  mov     rdx, rsi; struct _GUID *
0x180060944  mov     [rax+20h], rcx
0x180060948  mov     qword ptr [rax+8], 0
0x180060950  mov     dword ptr [rax+10h], 0
0x180060957  lea     rax, ??_7CTypelibCacheEntry@@6B@; const CTypelibCacheEntry::`vftable'
0x18006095e  mov     [rbx], rax
0x180060961  or      eax, 0FFFFFFFFh
0x180060964  mov     [rbx+30h], rcx
0x180060968  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006096f  mov     [rbx+48h], ecx
0x180060972  mov     rcx, rbx; this
0x180060975  mov     [rbx+4Ch], eax
0x180060978  movdqu  xmmword ptr [rbx+38h], xmm0
0x18006097d  mov     [rbx+50h], eax
0x180060980  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x180060987  call    ?InitByCLSID@CTypelibCacheEntry@@AEAAJAEBU_GUID@@PEAG@Z; CTypelibCacheEntry::InitByCLSID(_GUID const &,ushort *)
0x18006098c  mov     ebp, eax
0x18006098e  mov     r13d, 1
0x180060994  test    eax, eax
0x180060996  js      short loc_1800609E6
0x180060998  lea     rcx, stru_18007D278; lpCriticalSection
0x18006099f  xor     edi, edi
0x1800609a1  call    cs:__imp_EnterCriticalSection
0x1800609a7  lea     r8d, [r13+0Fh]; int
0x1800609ab  mov     rdx, rsi; void *
0x1800609ae  lea     rcx, qword_18007D178; this
0x1800609b5  call    ?FindElem@CHashTable@@QEAAPEAUCLinkElem@@PEBXH@Z; CHashTable::FindElem(void const *,int)
0x1800609ba  test    rax, rax
0x1800609bd  jnz     short loc_1800609D5
0x1800609bf  mov     rdx, rbx; struct CLinkElem *
0x1800609c2  lea     rcx, qword_18007D178; this
0x1800609c9  call    ?AddElem@CHashTable@@QEAAPEAUCLinkElem@@PEAU2@H@Z; CHashTable::AddElem(CLinkElem *,int)
0x1800609ce  test    rax, rax
0x1800609d1  cmovnz  edi, r13d
0x1800609d5  lea     rcx, stru_18007D278; lpCriticalSection
0x1800609dc  call    cs:__imp_LeaveCriticalSection
0x1800609e2  test    edi, edi
0x1800609e4  jnz     short loc_1800609F7
0x1800609e6  mov     rax, [rbx]
0x1800609e9  mov     edx, r13d
0x1800609ec  mov     rcx, rbx
0x1800609ef  mov     rax, [rax]
0x1800609f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609f7  mov     eax, ebp
0x1800609f9  jmp     short loc_180060A00
0x1800609fb  mov     eax, 8007000Eh
0x180060a00  add     rsp, 20h
0x180060a04  pop     r13
0x180060a06  pop     rdi
0x180060a07  pop     rsi
0x180060a08  pop     rbp
0x180060a09  pop     rbx
0x180060a0a  retn
```
