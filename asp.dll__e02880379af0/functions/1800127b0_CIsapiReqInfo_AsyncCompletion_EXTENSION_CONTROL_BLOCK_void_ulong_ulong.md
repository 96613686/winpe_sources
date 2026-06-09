# CIsapiReqInfo::AsyncCompletion(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)

- ea: `0x1800127b0`
- end: `0x180012808`
- name: `?AsyncCompletion@CIsapiReqInfo@@SAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z`
- size: `88`
- prototype: `static void(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012628`
- `0x1800127b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002b5e7`
- `KERNEL32!HeapFree` at `0x18002b625`
- `KERNEL32!HeapFree` at `0x18002b5e7`
- `KERNEL32!HeapFree` at `0x18002b625`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800127f7`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800127f7`

## pseudocode

```c
void __fastcall CIsapiReqInfo::AsyncCompletion(struct _EXTENSION_CONTROL_BLOCK *a1, _DWORD *a2, __int64 a3, int a4)
{
  __int64 i; // rdi
  void *v6; // r8
  void *v7; // r8
  HANDLE v8; // rcx

  if ( a4 )
    a2[307] = a4;
  if ( *((_QWORD *)a2 + 159) )
  {
    for ( i = 0; (unsigned int)i < a2[317]; i = (unsigned int)(i + 1) )
    {
      v6 = *(void **)(8 * i + *((_QWORD *)a2 + 159));
      if ( v6 )
      {
        HeapFree(g_hDenaliHeap, 0, v6);
        *(_QWORD *)(8 * i + *((_QWORD *)a2 + 159)) = 0;
      }
    }
    v7 = (void *)*((_QWORD *)a2 + 159);
    v8 = g_hDenaliHeap;
    a2[317] = 0;
    HeapFree(v8, 0, v7);
    *((_QWORD *)a2 + 159) = 0;
  }
  if ( _InterlockedExchangeAdd(a2, 0xFFFFFFFF) == 1 )
  {
    CIsapiReqInfo::~CIsapiReqInfo((CIsapiReqInfo *)a2);
    if ( CIsapiReqInfo::sm_pach )
      ALLOC_CACHE_HANDLER::Free(CIsapiReqInfo::sm_pach, a2);
  }
}

```

## disassembly

```asm
0x1800127b0  push    rbx
0x1800127b2  sub     rsp, 20h
0x1800127b6  mov     rbx, rdx
0x1800127b9  test    r9d, r9d
0x1800127bc  jnz     short loc_1800127FF
0x1800127be  cmp     qword ptr [rdx+4F8h], 0
0x1800127c6  jnz     loc_18002B5B2
0x1800127cc  mov     eax, 0FFFFFFFFh
0x1800127d1  lock xadd [rbx], eax
0x1800127d5  cmp     eax, 1
0x1800127d8  jz      short loc_1800127E0
0x1800127da  add     rsp, 20h
0x1800127de  pop     rbx
0x1800127df  retn
0x1800127e0  mov     rcx, rbx; this
0x1800127e3  call    ??1CIsapiReqInfo@@QEAA@XZ; CIsapiReqInfo::~CIsapiReqInfo(void)
0x1800127e8  mov     rcx, cs:?sm_pach@CIsapiReqInfo@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CIsapiReqInfo::sm_pach
0x1800127ef  test    rcx, rcx
0x1800127f2  jz      short loc_1800127DA
0x1800127f4  mov     rdx, rbx
0x1800127f7  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800127fd  jmp     short loc_1800127DA
0x1800127ff  mov     [rdx+4CCh], r9d
0x180012806  jmp     short loc_1800127BE
0x18002b5b2  mov     [rsp+28h+arg_8], rdi
0x18002b5b7  xor     edi, edi
0x18002b5b9  cmp     [rdx+4F4h], edi
0x18002b5bf  jbe     short loc_18002B60B
0x18002b5c1  mov     [rsp+28h+arg_0], rsi
0x18002b5c6  mov     rax, [rbx+4F8h]
0x18002b5cd  lea     rsi, ds:0[rdi*8]
0x18002b5d5  mov     r8, [rsi+rax]; lpMem
0x18002b5d9  test    r8, r8
0x18002b5dc  jz      short loc_18002B5FC
0x18002b5de  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002b5e5  xor     edx, edx; dwFlags
0x18002b5e7  call    cs:__imp_HeapFree
0x18002b5ed  mov     rax, [rbx+4F8h]
0x18002b5f4  mov     qword ptr [rsi+rax], 0
0x18002b5fc  inc     edi
0x18002b5fe  cmp     edi, [rbx+4F4h]
0x18002b604  jb      short loc_18002B5C6
0x18002b606  mov     rsi, [rsp+28h+arg_0]
0x18002b60b  mov     r8, [rbx+4F8h]; lpMem
0x18002b612  xor     edx, edx; dwFlags
0x18002b614  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x18002b61b  mov     dword ptr [rbx+4F4h], 0
0x18002b625  call    cs:__imp_HeapFree
0x18002b62b  mov     rdi, [rsp+28h+arg_8]
0x18002b630  mov     qword ptr [rbx+4F8h], 0
0x18002b63b  jmp     loc_1800127CC
```
