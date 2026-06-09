# CTemplateCacheManager::FlushAll(int)

- ea: `0x180034264`
- end: `0x18003444e`
- name: `?FlushAll@CTemplateCacheManager@@QEAAXH@Z`
- size: `490`
- prototype: `void __fastcall(CTemplateCacheManager *__hidden this, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180009180`
- `0x18000ca50`
- `0x1800444b8`
- `0x1800631b0`

## callees

- `0x180005064`
- `0x180033e48`
- `0x180034264`
- `0x1800346e8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800342e7`
- `KERNEL32!HeapAlloc` at `0x1800342e7`
- `KERNEL32!LeaveCriticalSection` at `0x180034430`
- `KERNEL32!LeaveCriticalSection` at `0x18003443d`
- `KERNEL32!LeaveCriticalSection` at `0x180034430`
- `KERNEL32!LeaveCriticalSection` at `0x18003443d`
- `KERNEL32!WaitForMultipleObjects` at `0x180034325`
- `KERNEL32!WaitForMultipleObjects` at `0x180034325`
- `KERNEL32!CloseHandle` at `0x18003438b`
- `KERNEL32!CloseHandle` at `0x18003438b`
- `KERNEL32!CreateThread` at `0x18003435d`
- `KERNEL32!CreateThread` at `0x18003435d`
- `KERNEL32!EnterCriticalSection` at `0x1800342c5`
- `KERNEL32!EnterCriticalSection` at `0x1800342d2`
- `KERNEL32!EnterCriticalSection` at `0x1800342c5`
- `KERNEL32!EnterCriticalSection` at `0x1800342d2`
- `KERNEL32!GetTickCount` at `0x180034273`
- `KERNEL32!GetTickCount` at `0x180034273`
- `iisutil!PuDbgPrint` at `0x1800342b3`
- `iisutil!PuDbgPrint` at `0x1800343d0`
- `iisutil!PuDbgPrint` at `0x180034417`
- `iisutil!PuDbgPrint` at `0x1800342b3`
- `iisutil!PuDbgPrint` at `0x1800343d0`
- `iisutil!PuDbgPrint` at `0x180034417`

## string_xrefs

- `0x1800342ac`: `inetsrv\iis\svcs\cmp\asp\cachemgr.cpp`
- `0x1800343c9`: `inetsrv\iis\svcs\cmp\asp\cachemgr.cpp`
- `0x180034410`: `inetsrv\iis\svcs\cmp\asp\cachemgr.cpp`
- `0x180034293`: `Using new Cache Tag to Invalidate Template\n`
- `0x18003429a`: `CTemplateCacheManager::FlushAll`
- `0x1800343b7`: `CTemplateCacheManager::FlushAll`
- `0x1800343fe`: `CTemplateCacheManager::FlushAll`
- `0x1800343b0`: `[CTemplateCacheManager] Flushing entire cache on another thread.\n`
- `0x1800343f7`: `[CTemplateCacheManager] Flushing entire cache in place\n`

## pseudocode

```c
void __fastcall CTemplateCacheManager::FlushAll(CTemplateCacheManager *this, int a2)
{
  CTemplateCacheManager::CTemplateHashTable *v2; // rax
  CTemplateCacheManager::CTemplateHashTable *v3; // rsi
  DWORD v4; // ebx
  unsigned int v5; // edx
  HANDLE Thread; // rbp
  __int64 v7; // rdi
  bool v8; // zf

  if ( !a2 )
  {
    EnterCriticalSection(&stru_180079DF0);
    EnterCriticalSection(&g_IncFileMap);
    v2 = (CTemplateCacheManager::CTemplateHashTable *)HeapAlloc(g_hDenaliHeap, 0, 0x80u);
    if ( !v2 )
      goto LABEL_17;
    v3 = (CTemplateCacheManager::CTemplateHashTable *)CTemplateCacheManager::CTemplateHashTable::CTemplateHashTable(v2);
    if ( !v3 )
      goto LABEL_17;
    if ( dword_180079DE8 )
    {
      WaitForMultipleObjects(dword_180079DE8, &qword_180079CE8, 0, 0);
      v4 = dword_180079DE8;
      if ( dword_180079DE8 >= 0x20 )
      {
LABEL_16:
        CTemplateCacheManager::CTemplateHashTable::`scalar deleting destructor'(v3, v5);
LABEL_17:
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr.cpp",
            779,
            "CTemplateCacheManager::FlushAll",
            "[CTemplateCacheManager] Flushing entire cache in place\n");
        CTemplateCacheManager::FlushHashTable(lpParameter);
        goto LABEL_20;
      }
    }
    else
    {
      v4 = 0;
    }
    Thread = CreateThread(0, 0, CTemplateCacheManager::FlushHashTableThread, lpParameter, 0, 0);
    if ( Thread )
    {
      v7 = 8LL * v4;
      if ( v4 >= dword_180079DE8 )
        ++dword_180079DE8;
      else
        CloseHandle(*(HANDLE *)((char *)&g_TemplateCache + v7 + 8));
      v8 = (g_dwDebugFlags & 3) == 0;
      *(HANDLE *)((char *)&g_TemplateCache + v7 + 8) = Thread;
      if ( !v8 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr.cpp",
          759,
          "CTemplateCacheManager::FlushAll",
          "[CTemplateCacheManager] Flushing entire cache on another thread.\n");
      lpParameter = v3;
LABEL_20:
      LeaveCriticalSection(&stru_180079DF0);
      LeaveCriticalSection(&g_IncFileMap);
      return;
    }
    goto LABEL_16;
  }
  dword_180079E20 = GetTickCount();
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr.cpp",
      678,
      "CTemplateCacheManager::FlushAll",
      "Using new Cache Tag to Invalidate Template\n");
}

```

## disassembly

```asm
0x180034264  push    rbx
0x180034266  push    rbp
0x180034267  push    rsi
0x180034268  push    rdi
0x180034269  push    r12
0x18003426b  sub     rsp, 30h
0x18003426f  test    edx, edx
0x180034271  jz      short loc_1800342BE
0x180034273  call    cs:__imp_GetTickCount
0x180034279  test    byte ptr cs:g_dwDebugFlags, 3
0x180034280  mov     cs:dword_180079E20, eax
0x180034286  jz      loc_180034443
0x18003428c  mov     rcx, cs:g_pDebug
0x180034293  lea     rax, aUsingNewCacheT; "Using new Cache Tag to Invalidate Templ"...
0x18003429a  lea     r9, aCtemplatecache; "CTemplateCacheManager::FlushAll"
0x1800342a1  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800342a6  mov     r8d, 2A6h
0x1800342ac  lea     rdx, aInetsrvIisSvcs_5; "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr."...
0x1800342b3  call    cs:__imp_PuDbgPrint
0x1800342b9  jmp     loc_180034443
0x1800342be  lea     rcx, stru_180079DF0; lpCriticalSection
0x1800342c5  call    cs:__imp_EnterCriticalSection
0x1800342cb  lea     rcx, ?g_IncFileMap@@3VCIncFileMap@@A; lpCriticalSection
0x1800342d2  call    cs:__imp_EnterCriticalSection
0x1800342d8  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800342df  xor     edx, edx; dwFlags
0x1800342e1  mov     r8d, 80h; dwBytes
0x1800342e7  call    cs:__imp_HeapAlloc
0x1800342ed  test    rax, rax
0x1800342f0  jz      loc_1800343E7
0x1800342f6  mov     rcx, rax; this
0x1800342f9  call    ??0CTemplateHashTable@CTemplateCacheManager@@QEAA@XZ; CTemplateCacheManager::CTemplateHashTable::CTemplateHashTable(void)
0x1800342fe  mov     rsi, rax
0x180034301  test    rax, rax
0x180034304  jz      loc_1800343E7
0x18003430a  mov     ecx, cs:dword_180079DE8; nCount
0x180034310  test    ecx, ecx
0x180034312  jnz     short loc_180034318
0x180034314  xor     ebx, ebx
0x180034316  jmp     short loc_18003433A
0x180034318  xor     r9d, r9d; dwMilliseconds
0x18003431b  lea     rdx, qword_180079CE8; lpHandles
0x180034322  xor     r8d, r8d; bWaitAll
0x180034325  call    cs:__imp_WaitForMultipleObjects
0x18003432b  mov     ebx, cs:dword_180079DE8
0x180034331  cmp     ebx, 20h ; ' '
0x180034334  jnb     loc_1800343DF
0x18003433a  mov     r9, cs:lpParameter; lpParameter
0x180034341  lea     r8, ?FlushHashTableThread@CTemplateCacheManager@@CAKPEAX@Z; lpStartAddress
0x180034348  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180034351  xor     edx, edx; dwStackSize
0x180034353  xor     ecx, ecx; lpThreadAttributes
0x180034355  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18003435d  call    cs:__imp_CreateThread
0x180034363  mov     rbp, rax
0x180034366  test    rax, rax
0x180034369  jz      short loc_1800343DF
0x18003436b  mov     eax, cs:dword_180079DE8
0x180034371  lea     r12, ?g_TemplateCache@@3VCTemplateCacheManager@@A; CTemplateCacheManager g_TemplateCache
0x180034378  mov     ecx, ebx
0x18003437a  lea     rdi, ds:0[rcx*8]
0x180034382  cmp     ebx, eax
0x180034384  jnb     short loc_180034393
0x180034386  mov     rcx, [rdi+r12+8]; hObject
0x18003438b  call    cs:__imp_CloseHandle
0x180034391  jmp     short loc_18003439B
0x180034393  inc     eax
0x180034395  mov     cs:dword_180079DE8, eax
0x18003439b  test    byte ptr cs:g_dwDebugFlags, 3
0x1800343a2  mov     [rdi+r12+8], rbp
0x1800343a7  jz      short loc_1800343D6
0x1800343a9  mov     rcx, cs:g_pDebug
0x1800343b0  lea     rax, aCtemplatecache_2; "[CTemplateCacheManager] Flushing entire"...
0x1800343b7  lea     r9, aCtemplatecache; "CTemplateCacheManager::FlushAll"
0x1800343be  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x1800343c3  mov     r8d, 2F7h
0x1800343c9  lea     rdx, aInetsrvIisSvcs_5; "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr."...
0x1800343d0  call    cs:__imp_PuDbgPrint
0x1800343d6  mov     cs:lpParameter, rsi
0x1800343dd  jmp     short loc_180034429
0x1800343df  mov     rcx, rsi; this
0x1800343e2  call    ??_GCTemplateHashTable@CTemplateCacheManager@@QEAAPEAXI@Z; CTemplateCacheManager::CTemplateHashTable::`scalar deleting destructor'(uint)
0x1800343e7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800343ee  jz      short loc_18003441D
0x1800343f0  mov     rcx, cs:g_pDebug
0x1800343f7  lea     rax, aCtemplatecache_1; "[CTemplateCacheManager] Flushing entire"...
0x1800343fe  lea     r9, aCtemplatecache; "CTemplateCacheManager::FlushAll"
0x180034405  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x18003440a  mov     r8d, 30Bh
0x180034410  lea     rdx, aInetsrvIisSvcs_5; "inetsrv\\iis\\svcs\\cmp\\asp\\cachemgr."...
0x180034417  call    cs:__imp_PuDbgPrint
0x18003441d  mov     rcx, cs:lpParameter; struct CTemplateCacheManager::CTemplateHashTable *
0x180034424  call    ?FlushHashTable@CTemplateCacheManager@@CAXPEAVCTemplateHashTable@1@@Z; CTemplateCacheManager::FlushHashTable(CTemplateCacheManager::CTemplateHashTable *)
0x180034429  lea     rcx, stru_180079DF0; lpCriticalSection
0x180034430  call    cs:__imp_LeaveCriticalSection
0x180034436  lea     rcx, ?g_IncFileMap@@3VCIncFileMap@@A; lpCriticalSection
0x18003443d  call    cs:__imp_LeaveCriticalSection
0x180034443  add     rsp, 30h
0x180034447  pop     r12
0x180034449  pop     rdi
0x18003444a  pop     rsi
0x18003444b  pop     rbp
0x18003444c  pop     rbx
0x18003444d  retn
```
