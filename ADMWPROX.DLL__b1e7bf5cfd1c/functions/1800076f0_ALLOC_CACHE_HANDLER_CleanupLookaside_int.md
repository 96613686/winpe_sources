# ALLOC_CACHE_HANDLER::CleanupLookaside(int)

- ea: `0x1800076f0`
- end: `0x18000780a`
- name: `?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z`
- size: `282`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007604`

## callees

- `0x180007234`
- `0x1800076f0`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x1800077ae`
- `KERNEL32!InterlockedPopEntrySList` at `0x1800077ae`
- `KERNEL32!QueryDepthSList` at `0x1800077de`
- `KERNEL32!QueryDepthSList` at `0x1800077de`
- `KERNEL32!HeapFree` at `0x1800077c5`
- `KERNEL32!HeapFree` at `0x1800077c5`

## string_xrefs

- `0x180007768`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18000775a`: `ALLOC_CACHE_HANDLER::CleanupLookaside`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::CleanupLookaside(ALLOC_CACHE_HANDLER *this, int a2)
{
  int v2; // edi
  _QWORD *v4; // r14
  unsigned int i; // ebp
  union _SLIST_HEADER *v6; // rsi
  __int32 v7; // eax
  int v8; // r12d
  PSLIST_ENTRY v9; // rax
  USHORT DepthSList; // ax
  int v11; // r15d

  v2 = a2;
  if ( *((_DWORD *)this + 3) )
  {
    if ( a2 )
      goto LABEL_5;
    if ( ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled )
    {
      v2 = 1;
      _InterlockedExchange((volatile __int32 *)this + 3, 0);
      goto LABEL_5;
    }
  }
  else if ( a2 )
  {
    goto LABEL_5;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
      0x27Au,
      "ALLOC_CACHE_HANDLER::CleanupLookaside",
      "AllocCalls = %ld, LastAllocCount = %ld\n",
      *((_DWORD *)this + 32));
  v7 = *((_DWORD *)this + 32);
  if ( v7 != *((_DWORD *)this + 2) )
  {
    _InterlockedExchange((volatile __int32 *)this + 2, v7);
    return;
  }
LABEL_5:
  v4 = (_QWORD *)*((_QWORD *)this + 3);
  for ( i = 0; (unsigned __int64)i < v4[2]; ++i )
  {
    v6 = (union _SLIST_HEADER *)(*v4 + v4[1] * i);
    do
    {
      DepthSList = QueryDepthSList(v6);
      v11 = DepthSList;
      if ( !DepthSList )
        break;
      v8 = 0;
      do
      {
        v9 = InterlockedPopEntrySList(v6);
        if ( !v9 )
          break;
        HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v9);
        _InterlockedDecrement((volatile signed __int32 *)this + 16);
        ++v8;
      }
      while ( v8 < v11 );
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x1800076f0  push    rbx
0x1800076f2  push    rbp
0x1800076f3  push    rsi
0x1800076f4  push    rdi
0x1800076f5  push    r12
0x1800076f7  push    r14
0x1800076f9  push    r15
0x1800076fb  sub     rsp, 40h
0x1800076ff  cmp     dword ptr [rcx+0Ch], 0
0x180007703  mov     edi, edx
0x180007705  mov     rbx, rcx
0x180007708  jz      short loc_18000773D
0x18000770a  test    edx, edx
0x18000770c  jnz     short loc_18000771E
0x18000770e  cmp     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x180007714  jz      short loc_180007741
0x180007716  xor     eax, eax
0x180007718  lea     edi, [rdx+1]
0x18000771b  xchg    eax, [rcx+0Ch]
0x18000771e  mov     r14, [rbx+18h]
0x180007722  xor     ebp, ebp
0x180007724  cmp     [r14+10h], rbp
0x180007728  jbe     loc_1800077FB
0x18000772e  mov     esi, ebp
0x180007730  imul    rsi, [r14+8]
0x180007735  add     rsi, [r14]
0x180007738  jmp     loc_1800077DB
0x18000773d  test    edx, edx
0x18000773f  jnz     short loc_18000771E
0x180007741  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180007747  test    al, 3
0x180007749  setnz   cl
0x18000774c  bt      eax, 18h
0x180007750  setb    al
0x180007753  test    al, cl
0x180007755  jz      short loc_180007794
0x180007757  mov     eax, [rbx+8]
0x18000775a  lea     r9, aAllocCacheHand_0; "ALLOC_CACHE_HANDLER::CleanupLookaside"
0x180007761  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180007768  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000776f  mov     [rsp+78h+var_48], eax
0x180007773  mov     r8d, 27Ah; unsigned int
0x180007779  mov     eax, [rbx+80h]
0x18000777f  mov     dword ptr [rsp+78h+var_50], eax; char
0x180007783  lea     rax, aAlloccallsLdLa; "AllocCalls = %ld, LastAllocCount = %ld"...
0x18000778a  mov     [rsp+78h+var_58], rax; char *
0x18000778f  call    PuDbgPrint
0x180007794  mov     eax, [rbx+80h]
0x18000779a  cmp     eax, [rbx+8]
0x18000779d  jz      loc_18000771E
0x1800077a3  xchg    eax, [rbx+8]
0x1800077a6  jmp     short loc_1800077FB
0x1800077a8  xor     r12d, r12d
0x1800077ab  mov     rcx, rsi; ListHead
0x1800077ae  call    cs:__imp_InterlockedPopEntrySList
0x1800077b4  test    rax, rax
0x1800077b7  jz      short loc_1800077D7
0x1800077b9  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x1800077c0  mov     r8, rax; lpMem
0x1800077c3  xor     edx, edx; dwFlags
0x1800077c5  call    cs:__imp_HeapFree
0x1800077cb  lock dec dword ptr [rbx+40h]
0x1800077cf  inc     r12d
0x1800077d2  cmp     r12d, r15d
0x1800077d5  jl      short loc_1800077AB
0x1800077d7  test    edi, edi
0x1800077d9  jz      short loc_1800077ED
0x1800077db  mov     rcx, rsi; ListHead
0x1800077de  call    cs:__imp_QueryDepthSList
0x1800077e4  movzx   r15d, ax
0x1800077e8  test    r15d, r15d
0x1800077eb  jnz     short loc_1800077A8
0x1800077ed  inc     ebp
0x1800077ef  mov     eax, ebp
0x1800077f1  cmp     rax, [r14+10h]
0x1800077f5  jb      loc_18000772E
0x1800077fb  add     rsp, 40h
0x1800077ff  pop     r15
0x180007801  pop     r14
0x180007803  pop     r12
0x180007805  pop     rdi
0x180007806  pop     rsi
0x180007807  pop     rbp
0x180007808  pop     rbx
0x180007809  retn
```
