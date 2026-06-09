# CHandlerCollectionInfo::FindHandlerInfo(CSyncMgrID const &,CHandlerInfo * *)

- ea: `0x180008eb4`
- end: `0x180008f9b`
- name: `?FindHandlerInfo@CHandlerCollectionInfo@@QEAAJAEBVCSyncMgrID@@PEAPEAVCHandlerInfo@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(CHandlerCollectionInfo *__hidden this, const struct CSyncMgrID *, struct CHandlerInfo **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000700c`
- `0x1800087dc`

## callees

- `0x180005d30`
- `0x180008eb4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008edd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008edd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008f5c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008f5c`

## pseudocode

```c
__int64 __fastcall CHandlerCollectionInfo::FindHandlerInfo(
        LPCRITICAL_SECTION *this,
        const WCHAR *a2,
        struct CHandlerInfo **a3)
{
  unsigned int v6; // r14d
  int *v7; // rax
  int v8; // ebp
  int i; // edi
  __int64 (__fastcall *v10)(LPCRITICAL_SECTION, _QWORD); // rax
  LPCRITICAL_SECTION v11; // rbx
  __int64 v12; // rbx

  *a3 = 0;
  v6 = -2147024894;
  EnterCriticalSection(this[6]);
  v7 = (int *)this[5];
  if ( v7 )
    v8 = *v7;
  else
    v8 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v10 = (__int64 (__fastcall *)(LPCRITICAL_SECTION, _QWORD))qword_1800701D0;
    v11 = this[5];
    if ( qword_1800701D0 == -1 )
    {
      GetProcFromComCtl32(&qword_1800701D0, 332);
      v10 = (__int64 (__fastcall *)(LPCRITICAL_SECTION, _QWORD))qword_1800701D0;
    }
    if ( v10 )
      v12 = v10(v11, i);
    else
      v12 = 0;
    if ( CompareStringW(0x7Fu, 1u, a2 + 8, -1, (PCNZWCH)(v12 + 116), -1) == 2 )
    {
      v6 = 0;
      *a3 = (struct CHandlerInfo *)v12;
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 2076));
      break;
    }
  }
  LeaveCriticalSection(this[6]);
  return v6;
}

```

## disassembly

```asm
0x180008eb4  push    rbx
0x180008eb6  push    rbp
0x180008eb7  push    rsi
0x180008eb8  push    rdi
0x180008eb9  push    r13
0x180008ebb  push    r14
0x180008ebd  push    r15
0x180008ebf  sub     rsp, 30h
0x180008ec3  mov     rsi, rcx
0x180008ec6  mov     qword ptr [r8], 0
0x180008ecd  mov     rcx, [rcx+30h]; lpCriticalSection
0x180008ed1  mov     r15, r8
0x180008ed4  mov     r13, rdx
0x180008ed7  mov     r14d, 80070002h
0x180008edd  call    cs:__imp_EnterCriticalSection
0x180008ee3  mov     rax, [rsi+28h]
0x180008ee7  test    rax, rax
0x180008eea  jz      short loc_180008EF0
0x180008eec  mov     ebp, [rax]
0x180008eee  jmp     short loc_180008EF2
0x180008ef0  xor     ebp, ebp
0x180008ef2  xor     edi, edi
0x180008ef4  cmp     edi, ebp
0x180008ef6  jge     loc_180008F7F
0x180008efc  mov     rax, cs:qword_1800701D0
0x180008f03  mov     rbx, [rsi+28h]
0x180008f07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008f0b  jnz     short loc_180008F25
0x180008f0d  mov     edx, 14Ch
0x180008f12  lea     rcx, qword_1800701D0
0x180008f19  call    _GetProcFromComCtl32
0x180008f1e  mov     rax, cs:qword_1800701D0
0x180008f25  test    rax, rax
0x180008f28  jz      short loc_180008F3A
0x180008f2a  movsxd  rdx, edi
0x180008f2d  mov     rcx, rbx
0x180008f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f35  mov     rbx, rax
0x180008f38  jmp     short loc_180008F3C
0x180008f3a  xor     ebx, ebx
0x180008f3c  or      r9d, 0FFFFFFFFh; cchCount1
0x180008f40  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180008f48  lea     rax, [rbx+74h]
0x180008f4c  lea     r8, [r13+10h]; lpString1
0x180008f50  mov     [rsp+68h+lpString2], rax; lpString2
0x180008f55  lea     edx, [r9+2]; dwCmpFlags
0x180008f59  lea     ecx, [rdx+7Eh]; Locale
0x180008f5c  call    cs:__imp_CompareStringW
0x180008f62  mov     ecx, eax
0x180008f64  sub     ecx, 1
0x180008f67  jz      short loc_180008F6E
0x180008f69  cmp     ecx, 1
0x180008f6c  jz      short loc_180008F72
0x180008f6e  inc     edi
0x180008f70  jmp     short loc_180008EF4
0x180008f72  xor     r14d, r14d
0x180008f75  mov     [r15], rbx
0x180008f78  lock inc dword ptr [rbx+81Ch]
0x180008f7f  mov     rcx, [rsi+30h]; lpCriticalSection
0x180008f83  call    cs:__imp_LeaveCriticalSection
0x180008f89  mov     eax, r14d
0x180008f8c  add     rsp, 30h
0x180008f90  pop     r15
0x180008f92  pop     r14
0x180008f94  pop     r13
0x180008f96  pop     rdi
0x180008f97  pop     rsi
0x180008f98  pop     rbp
0x180008f99  pop     rbx
0x180008f9a  retn
```
