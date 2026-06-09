# ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)

- ea: `0x180007604`
- end: `0x1800076ae`
- name: `??1ALLOC_CACHE_HANDLER@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(ALLOC_CACHE_HANDLER *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007e44`
- `0x180007f80`

## callees

- `0x180007234`
- `0x180007604`
- `0x1800076f0`
- `0x180007b78`
- `0x180007bd4`

## import_xrefs

- `msvcrt!_aligned_free` at `0x180007695`
- `msvcrt!_aligned_free` at `0x180007695`

## string_xrefs

- `0x18000766a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18000767b`: `Items in look-aside lists = %u, Pending HeapFree calls = %u\n`
- `0x18000765f`: `ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER`

## pseudocode

```c
void __fastcall ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void **this)
{
  char DepthForAllSLists; // al

  if ( *(_DWORD *)this )
  {
    ALLOC_CACHE_HANDLER::RemoveItem((struct ALLOC_CACHE_HANDLER *)this);
    ALLOC_CACHE_HANDLER::CleanupLookaside((ALLOC_CACHE_HANDLER *)this, 1);
  }
  if ( *((_DWORD *)this + 1)
    && !g_fTestProcess
    && (g_dwDebugFlagsIISUtil & 3) != 0
    && (g_dwDebugFlagsIISUtil & 0x1000000) != 0 )
  {
    DepthForAllSLists = ALLOC_CACHE_HANDLER::QueryDepthForAllSLists((ALLOC_CACHE_HANDLER *)this);
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\acache.cxx",
      0x244u,
      "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER",
      "Items in look-aside lists = %u, Pending HeapFree calls = %u\n",
      DepthForAllSLists);
  }
  if ( *(_DWORD *)this )
  {
    _aligned_free(this[3]);
    this[3] = 0;
  }
}

```

## disassembly

```asm
0x180007604  mov     [rsp+arg_0], rbx
0x180007609  push    rdi
0x18000760a  sub     rsp, 40h
0x18000760e  cmp     dword ptr [rcx], 0
0x180007611  mov     rdi, rcx
0x180007614  jz      short loc_180007628
0x180007616  call    ?RemoveItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z; ALLOC_CACHE_HANDLER::RemoveItem(ALLOC_CACHE_HANDLER *)
0x18000761b  mov     edx, 1; int
0x180007620  mov     rcx, rdi; this
0x180007623  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x180007628  cmp     dword ptr [rdi+4], 0
0x18000762c  jz      short loc_18000768C
0x18000762e  cmp     cs:?g_fTestProcess@@3HA, 0; int g_fTestProcess
0x180007635  jnz     short loc_18000768C
0x180007637  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000763d  test    al, 3
0x18000763f  setnz   cl
0x180007642  bt      eax, 18h
0x180007646  setb    al
0x180007649  test    al, cl
0x18000764b  jz      short loc_18000768C
0x18000764d  mov     ebx, [rdi+40h]
0x180007650  mov     rcx, rdi; this
0x180007653  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x180007658  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000765f  lea     r9, aAllocCacheHand; "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDL"...
0x180007666  mov     [rsp+48h+var_18], ebx
0x18000766a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007671  mov     dword ptr [rsp+48h+var_20], eax; char
0x180007675  mov     r8d, 244h; unsigned int
0x18000767b  lea     rax, aItemsInLookAsi; "Items in look-aside lists = %u, Pending"...
0x180007682  mov     [rsp+48h+var_28], rax; char *
0x180007687  call    PuDbgPrint
0x18000768c  cmp     dword ptr [rdi], 0
0x18000768f  jz      short loc_1800076A3
0x180007691  mov     rcx, [rdi+18h]; Block
0x180007695  call    cs:__imp__aligned_free
0x18000769b  mov     qword ptr [rdi+18h], 0
0x1800076a3  mov     rbx, [rsp+48h+arg_0]
0x1800076a8  add     rsp, 40h
0x1800076ac  pop     rdi
0x1800076ad  retn
```
