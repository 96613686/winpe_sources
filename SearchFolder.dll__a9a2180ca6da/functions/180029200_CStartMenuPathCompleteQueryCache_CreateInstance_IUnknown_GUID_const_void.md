# CStartMenuPathCompleteQueryCache_CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180029200`
- end: `0x180029298`
- name: `?CStartMenuPathCompleteQueryCache_CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `152`
- prototype: `int(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006924`
- `0x180029200`
- `0x18002f7b0`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18002927d`
- `SHLWAPI!__imp_QISearch` at `0x18002927d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002925c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002925c`

## pseudocode

```c
__int64 __fastcall CStartMenuPathCompleteQueryCache_CreateInstance(
        struct IUnknown *a1,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v5; // edi
  _QWORD *v6; // rax
  void *v7; // rbx

  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 1;
    *v6 = &CStartMenuPathCompleteQueryCache::`vftable';
    v6[3] = 0;
    v6[4] = 0;
    v6[2] = CreateMutexW(0, 0, 0);
    _InterlockedIncrement(&g_cDllRef);
    v5 = QISearch(v7, &stru_180054C90, a2, a3);
    CStartMenuPathCompleteQueryCache::Release((CStartMenuPathCompleteQueryCache *)v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180029200  push    rbx
0x180029202  push    rbp
0x180029203  push    rsi
0x180029204  push    rdi
0x180029205  sub     rsp, 28h
0x180029209  mov     rbp, rdx
0x18002920c  mov     qword ptr [r8], 0
0x180029213  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002921a  mov     ecx, 28h ; '('; unsigned __int64
0x18002921f  mov     rsi, r8
0x180029222  mov     edi, 8007000Eh
0x180029227  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002922c  mov     rbx, rax
0x18002922f  test    rax, rax
0x180029232  jz      short loc_18002928D
0x180029234  mov     dword ptr [rbx+8], 1
0x18002923b  lea     rax, ??_7CStartMenuPathCompleteQueryCache@@6B@; const CStartMenuPathCompleteQueryCache::`vftable'
0x180029242  mov     [rbx], rax
0x180029245  xor     r8d, r8d; lpName
0x180029248  mov     qword ptr [rbx+18h], 0
0x180029250  xor     edx, edx; bInitialOwner
0x180029252  xor     ecx, ecx; lpMutexAttributes
0x180029254  mov     qword ptr [rbx+20h], 0
0x18002925c  call    cs:__imp_CreateMutexW
0x180029262  mov     [rbx+10h], rax
0x180029266  lock inc cs:?g_cDllRef@@3JA; long g_cDllRef
0x18002926d  mov     r9, rsi; ppv
0x180029270  lea     rdx, stru_180054C90; pqit
0x180029277  mov     r8, rbp; riid
0x18002927a  mov     rcx, rbx; that
0x18002927d  call    cs:__imp_QISearch
0x180029283  mov     rcx, rbx; this
0x180029286  mov     edi, eax
0x180029288  call    ?Release@CStartMenuPathCompleteQueryCache@@UEAAKXZ; CStartMenuPathCompleteQueryCache::Release(void)
0x18002928d  mov     eax, edi
0x18002928f  add     rsp, 28h
0x180029293  pop     rdi
0x180029294  pop     rsi
0x180029295  pop     rbp
0x180029296  pop     rbx
0x180029297  retn
```
