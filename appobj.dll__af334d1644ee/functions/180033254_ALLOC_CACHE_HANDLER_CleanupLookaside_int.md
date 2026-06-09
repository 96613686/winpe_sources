# ALLOC_CACHE_HANDLER::CleanupLookaside(int)

- ea: `0x180033254`
- end: `0x180033394`
- name: `?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z`
- size: `320`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800330d4`

## callees

- `0x180033008`
- `0x180033254`
- `0x180034218`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003334a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003334a`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180033333`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180033333`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180033364`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180033364`

## string_xrefs

- `0x1800332bb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x1800332ad`: `ALLOC_CACHE_HANDLER::CleanupLookaside`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::CleanupLookaside(ALLOC_CACHE_HANDLER *this, int a2)
{
  __int32 v3; // eax
  _QWORD *v4; // r14
  __int64 v5; // rax
  unsigned int v6; // edi
  __int64 v7; // r12
  int i; // r15d
  union _SLIST_HEADER *v9; // rbx
  int v10; // ebp
  PSLIST_ENTRY v11; // rax
  USHORT DepthSList; // ax
  int v13; // esi
  _BYTE v14[16]; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+88h] [rbp+10h] BYREF

  v15 = a2;
  if ( !*((_DWORD *)this + 3) )
  {
LABEL_5:
    if ( a2 )
      goto LABEL_10;
    goto LABEL_6;
  }
  if ( a2 )
    goto LABEL_10;
  if ( ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled )
  {
    a2 = 1;
    v15 = 1;
    _InterlockedExchange((volatile __int32 *)this + 3, 0);
    goto LABEL_5;
  }
LABEL_6:
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
      0x27Au,
      "ALLOC_CACHE_HANDLER::CleanupLookaside",
      "AllocCalls = %ld, LastAllocCount = %ld\n",
      *((_DWORD *)this + 32));
  v3 = *((_DWORD *)this + 32);
  if ( v3 != *((_DWORD *)this + 2) )
  {
    _InterlockedExchange((volatile __int32 *)this + 2, v3);
    return;
  }
LABEL_10:
  v4 = (_QWORD *)*((_QWORD *)this + 3);
  v5 = lambda_5cd0576cc4450a3357849dbab5e82274_::_lambda_5cd0576cc4450a3357849dbab5e82274_(v14, this, &v15);
  v6 = 0;
  v7 = *(_QWORD *)v5;
  for ( i = *(_DWORD *)(v5 + 8); (unsigned __int64)v6 < v4[2]; ++v6 )
  {
    v9 = (union _SLIST_HEADER *)(*v4 + v4[1] * v6);
    do
    {
      DepthSList = QueryDepthSList(v9);
      v13 = DepthSList;
      if ( !DepthSList )
        break;
      v10 = 0;
      do
      {
        v11 = InterlockedPopEntrySList(v9);
        if ( !v11 )
          break;
        HeapFree(ALLOC_CACHE_HANDLER::sm_hHeap, 0, v11);
        _InterlockedDecrement((volatile signed __int32 *)(v7 + 64));
        ++v10;
      }
      while ( v10 < v13 );
    }
    while ( i );
  }
}

```

## disassembly

```asm
0x180033254  mov     rax, rsp
0x180033257  mov     [rax+8], rbx
0x18003325b  mov     [rax+18h], rbp
0x18003325f  mov     [rax+10h], edx
0x180033262  push    rsi
0x180033263  push    rdi
0x180033264  push    r12
0x180033266  push    r14
0x180033268  push    r15
0x18003326a  sub     rsp, 50h
0x18003326e  cmp     dword ptr [rcx+0Ch], 0
0x180033272  mov     rbx, rcx
0x180033275  jz      short loc_180033290
0x180033277  test    edx, edx
0x180033279  jnz     short loc_1800332FA
0x18003327b  cmp     cs:?sm_fPageHeapEnabled@ALLOC_CACHE_HANDLER@@0HA, edx; int ALLOC_CACHE_HANDLER::sm_fPageHeapEnabled
0x180033281  jz      short loc_180033294
0x180033283  mov     edx, 1
0x180033288  mov     [rax+10h], edx
0x18003328b  xor     eax, eax
0x18003328d  xchg    eax, [rcx+0Ch]
0x180033290  test    edx, edx
0x180033292  jnz     short loc_1800332FA
0x180033294  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18003329a  test    al, 3
0x18003329c  setnz   cl
0x18003329f  bt      eax, 18h
0x1800332a3  setb    al
0x1800332a6  test    al, cl
0x1800332a8  jz      short loc_1800332E7
0x1800332aa  mov     eax, [rbx+8]
0x1800332ad  lea     r9, aAllocCacheHand_0; "ALLOC_CACHE_HANDLER::CleanupLookaside"
0x1800332b4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800332bb  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800332c2  mov     [rsp+78h+var_48], eax
0x1800332c6  mov     r8d, 27Ah; unsigned int
0x1800332cc  mov     eax, [rbx+80h]
0x1800332d2  mov     dword ptr [rsp+78h+var_50], eax; char
0x1800332d6  lea     rax, aAlloccallsLdLa; "AllocCalls = %ld, LastAllocCount = %ld"...
0x1800332dd  mov     [rsp+78h+var_58], rax; char *
0x1800332e2  call    PuDbgPrint
0x1800332e7  mov     eax, [rbx+80h]
0x1800332ed  cmp     eax, [rbx+8]
0x1800332f0  jz      short loc_1800332FA
0x1800332f2  xchg    eax, [rbx+8]
0x1800332f5  jmp     loc_18003337B
0x1800332fa  mov     r14, [rbx+18h]
0x1800332fe  lea     r8, [rsp+78h+arg_8]
0x180033306  mov     rdx, rbx
0x180033309  lea     rcx, [rsp+78h+var_38]
0x18003330e  call    _lambda_5cd0576cc4450a3357849dbab5e82274____lambda_5cd0576cc4450a3357849dbab5e82274_
0x180033313  xor     edi, edi
0x180033315  mov     r12, [rax]
0x180033318  mov     r15d, [rax+8]
0x18003331c  cmp     [r14+10h], rdi
0x180033320  jbe     short loc_18003337B
0x180033322  mov     ebx, edi
0x180033324  imul    rbx, [r14+8]
0x180033329  add     rbx, [r14]
0x18003332c  jmp     short loc_180033361
0x18003332e  xor     ebp, ebp
0x180033330  mov     rcx, rbx; ListHead
0x180033333  call    cs:__imp_InterlockedPopEntrySList
0x180033339  test    rax, rax
0x18003333c  jz      short loc_18003335C
0x18003333e  mov     rcx, cs:?sm_hHeap@ALLOC_CACHE_HANDLER@@0PEAXEA; hHeap
0x180033345  mov     r8, rax; lpMem
0x180033348  xor     edx, edx; dwFlags
0x18003334a  call    cs:__imp_HeapFree
0x180033350  lock dec dword ptr [r12+40h]
0x180033356  inc     ebp
0x180033358  cmp     ebp, esi
0x18003335a  jl      short loc_180033330
0x18003335c  test    r15d, r15d
0x18003335f  jz      short loc_180033371
0x180033361  mov     rcx, rbx; ListHead
0x180033364  call    cs:__imp_QueryDepthSList
0x18003336a  movzx   esi, ax
0x18003336d  test    esi, esi
0x18003336f  jnz     short loc_18003332E
0x180033371  inc     edi
0x180033373  mov     eax, edi
0x180033375  cmp     rax, [r14+10h]
0x180033379  jb      short loc_180033322
0x18003337b  lea     r11, [rsp+78h+var_28]
0x180033380  mov     rbx, [r11+30h]
0x180033384  mov     rbp, [r11+40h]
0x180033388  mov     rsp, r11
0x18003338b  pop     r15
0x18003338d  pop     r14
0x18003338f  pop     r12
0x180033391  pop     rdi
0x180033392  pop     rsi
0x180033393  retn
```
