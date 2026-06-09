# ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)

- ea: `0x1800330d4`
- end: `0x18003317e`
- name: `??1ALLOC_CACHE_HANDLER@@QEAA@XZ`
- size: `170`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030180`

## callees

- `0x1800330d4`
- `0x180033254`
- `0x18003379c`
- `0x1800337f8`
- `0x180034218`

## import_xrefs

- `msvcrt!_aligned_free` at `0x180033165`
- `msvcrt!_aligned_free` at `0x180033165`

## string_xrefs

- `0x18003313a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\acache.cxx`
- `0x18003314b`: `Items in look-aside lists = %u, Pending HeapFree calls = %u\n`
- `0x18003312f`: `ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER`

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
0x1800330d4  mov     [rsp+arg_0], rbx
0x1800330d9  push    rdi
0x1800330da  sub     rsp, 40h
0x1800330de  cmp     dword ptr [rcx], 0
0x1800330e1  mov     rdi, rcx
0x1800330e4  jz      short loc_1800330F8
0x1800330e6  call    ?RemoveItem@ALLOC_CACHE_HANDLER@@SAXPEAV1@@Z; ALLOC_CACHE_HANDLER::RemoveItem(ALLOC_CACHE_HANDLER *)
0x1800330eb  mov     edx, 1; int
0x1800330f0  mov     rcx, rdi; this
0x1800330f3  call    ?CleanupLookaside@ALLOC_CACHE_HANDLER@@QEAAXH@Z; ALLOC_CACHE_HANDLER::CleanupLookaside(int)
0x1800330f8  cmp     dword ptr [rdi+4], 0
0x1800330fc  jz      short loc_18003315C
0x1800330fe  cmp     cs:?g_fTestProcess@@3HA, 0; int g_fTestProcess
0x180033105  jnz     short loc_18003315C
0x180033107  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18003310d  test    al, 3
0x18003310f  setnz   cl
0x180033112  bt      eax, 18h
0x180033116  setb    al
0x180033119  test    al, cl
0x18003311b  jz      short loc_18003315C
0x18003311d  mov     ebx, [rdi+40h]
0x180033120  mov     rcx, rdi; this
0x180033123  call    ?QueryDepthForAllSLists@ALLOC_CACHE_HANDLER@@AEAAKXZ; ALLOC_CACHE_HANDLER::QueryDepthForAllSLists(void)
0x180033128  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18003312f  lea     r9, aAllocCacheHand; "ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDL"...
0x180033136  mov     [rsp+48h+var_18], ebx
0x18003313a  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180033141  mov     dword ptr [rsp+48h+var_20], eax; char
0x180033145  mov     r8d, 244h; unsigned int
0x18003314b  lea     rax, aItemsInLookAsi; "Items in look-aside lists = %u, Pending"...
0x180033152  mov     [rsp+48h+var_28], rax; char *
0x180033157  call    PuDbgPrint
0x18003315c  cmp     dword ptr [rdi], 0
0x18003315f  jz      short loc_180033173
0x180033161  mov     rcx, [rdi+18h]; Block
0x180033165  call    cs:__imp__aligned_free
0x18003316b  mov     qword ptr [rdi+18h], 0
0x180033173  mov     rbx, [rsp+48h+arg_0]
0x180033178  add     rsp, 40h
0x18003317c  pop     rdi
0x18003317d  retn
```
