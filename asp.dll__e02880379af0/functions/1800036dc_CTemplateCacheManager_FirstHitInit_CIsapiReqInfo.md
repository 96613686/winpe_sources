# CTemplateCacheManager::FirstHitInit(CIsapiReqInfo *)

- ea: `0x1800036dc`
- end: `0x1800038a9`
- name: `?FirstHitInit@CTemplateCacheManager@@QEAAJPEAVCIsapiReqInfo@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(CTemplateCacheManager *this, struct _EXTENSION_CONTROL_BLOCK **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180002ae8`

## callees

- `0x1800036dc`
- `0x180019e7c`
- `0x180023dd0`
- `0x180034c90`
- `0x1800432d8`
- `0x1800491d8`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180003789`
- `msvcrt!sprintf_s` at `0x1800254f1`
- `msvcrt!sprintf_s` at `0x180003789`
- `msvcrt!sprintf_s` at `0x1800254f1`
- `msvcrt!strcpy_s` at `0x180003824`
- `msvcrt!strcpy_s` at `0x180003824`
- `ADVAPI32!SetThreadToken` at `0x180025585`
- `ADVAPI32!SetThreadToken` at `0x180025585`
- `ADVAPI32!RevertToSelf` at `0x1800254c0`
- `ADVAPI32!RevertToSelf` at `0x1800254c0`
- `ADVAPI32!OpenThreadToken` at `0x180003750`
- `ADVAPI32!OpenThreadToken` at `0x180003750`
- `KERNEL32!HeapFree` at `0x1800255b1`
- `KERNEL32!HeapFree` at `0x1800255b1`
- `KERNEL32!HeapAlloc` at `0x180003805`
- `KERNEL32!HeapAlloc` at `0x180003805`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800254b4`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x180025548`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x1800254b4`
- `KERNEL32!Wow64EnableWow64FsRedirection` at `0x180025548`
- `KERNEL32!GetCurrentProcess` at `0x180003715`
- `KERNEL32!GetCurrentProcess` at `0x180003715`
- `KERNEL32!IsWow64Process` at `0x180003723`
- `KERNEL32!IsWow64Process` at `0x180003723`
- `KERNEL32!CloseHandle` at `0x180025590`
- `KERNEL32!CloseHandle` at `0x180025590`
- `KERNEL32!CreateThread` at `0x180003841`
- `KERNEL32!CreateThread` at `0x180003841`
- `KERNEL32!GetFileAttributesA` at `0x1800037a3`
- `KERNEL32!GetFileAttributesA` at `0x1800037c8`
- `KERNEL32!GetFileAttributesA` at `0x1800037a3`
- `KERNEL32!GetFileAttributesA` at `0x1800037c8`
- `KERNEL32!GetCurrentProcessId` at `0x18000375e`
- `KERNEL32!GetCurrentProcessId` at `0x1800254d1`
- `KERNEL32!GetCurrentProcessId` at `0x18000375e`
- `KERNEL32!GetCurrentProcessId` at `0x1800254d1`
- `KERNEL32!GetLastError` at `0x18002551b`
- `KERNEL32!GetLastError` at `0x18002551b`
- `KERNEL32!MoveFileA` at `0x180025508`
- `KERNEL32!MoveFileA` at `0x180025508`
- `KERNEL32!CreateDirectoryA` at `0x1800037b7`
- `KERNEL32!CreateDirectoryA` at `0x1800037b7`
- `KERNEL32!GetCurrentThread` at `0x180003737`
- `KERNEL32!GetCurrentThread` at `0x180003737`

## pseudocode

```c
__int64 __fastcall CTemplateCacheManager::FirstHitInit(
        CTemplateCacheManager *this,
        struct _EXTENSION_CONTROL_BLOCK **a2)
{
  DWORD LastError; // ebp
  int v4; // r15d
  char *v5; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  DWORD CurrentProcessId; // eax
  int v9; // eax
  DWORD FileAttributesA; // eax
  UINT v11; // ebx
  __int64 v12; // rax
  SIZE_T v13; // r14
  char *v14; // rax
  DWORD v16; // eax
  int v17; // eax
  const char *PszAppPoolIdA; // rax
  const struct _GUID *v19; // rdx
  BOOL Wow64Process; // [rsp+30h] [rbp-168h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-160h] BYREF
  char Buffer[272]; // [rsp+40h] [rbp-158h] BYREF

  LastError = 0;
  TokenHandle = 0;
  Wow64Process = 0;
  v4 = 0;
  v5 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process )
  {
    g_fIsWow64Process = 1;
    Wow64EnableWow64FsRedirection(0);
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    RevertToSelf();
    v4 = 1;
  }
  CurrentProcessId = GetCurrentProcessId();
  v9 = sprintf_s(&CTemplateCacheManager::m_szPersistCacheDir, 0x104u, "%s\\PID%d.TMP", Source, CurrentProcessId);
  if ( v9 <= 0 || (unsigned int)v9 >= 0x104 )
    goto LABEL_31;
  if ( GetFileAttributesA(&CTemplateCacheManager::m_szPersistCacheDir) == -1 )
    goto LABEL_9;
  v16 = GetCurrentProcessId();
  v17 = sprintf_s(Buffer, 0x104u, "%s\\PID0%d.TMP", Source, v16);
  if ( v17 <= 0 || (unsigned int)v17 >= 0x104 )
  {
LABEL_31:
    v11 = 119;
    goto LABEL_16;
  }
  if ( !MoveFileA(&CTemplateCacheManager::m_szPersistCacheDir, Buffer) )
    goto LABEL_28;
LABEL_9:
  if ( !CreateDirectoryA(&CTemplateCacheManager::m_szPersistCacheDir, 0) )
  {
LABEL_28:
    v11 = 120;
    LastError = GetLastError();
    goto LABEL_16;
  }
  FileAttributesA = GetFileAttributesA(&CTemplateCacheManager::m_szPersistCacheDir);
  if ( FileAttributesA == -1 || (FileAttributesA & 0x10) == 0 )
  {
    v11 = 121;
  }
  else
  {
    v11 = 0;
    v12 = -1;
    do
      ++v12;
    while ( Source[v12] );
    v13 = (unsigned int)(v12 + 1);
    v14 = (char *)HeapAlloc(g_hDenaliHeap, 0, v13);
    v5 = v14;
    if ( v14 )
    {
      strcpy_s(v14, (unsigned int)v13, Source);
      g_TemplateCache = CreateThread(0, 0, CTemplateCacheManager::OnInitCleanup, v5, 0, 0);
    }
    else
    {
      LastError = 8;
    }
  }
LABEL_16:
  if ( g_fIsWow64Process )
    Wow64EnableWow64FsRedirection(1u);
  if ( v11 )
  {
    PszAppPoolIdA = CIsapiReqInfo::QueryPszAppPoolIdA((CIsapiReqInfo *)a2);
    MSG_Error(0x72u, PszAppPoolIdA, v11, LastError);
    CTemplateCacheManager::m_fFailedToInitPersistCache = 1;
  }
  if ( v4 )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  if ( !g_TemplateCache && v5 )
    HeapFree(g_hDenaliHeap, 0, v5);
  if ( CTemplateCacheManager::m_fFailedToInitPersistCache
    && a2
    && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(a2[1], 2u) )
  {
    AspReqEvents::ASP_INIT_FAILURE::RaiseEvent(a2[1], v19, 2u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800036dc  push    rbx
0x1800036de  push    rbp
0x1800036df  push    rsi
0x1800036e0  push    rdi
0x1800036e1  push    r14
0x1800036e3  push    r15
0x1800036e5  sub     rsp, 168h
0x1800036ec  mov     rax, cs:__security_cookie
0x1800036f3  xor     rax, rsp
0x1800036f6  mov     [rsp+198h+var_48], rax
0x1800036fe  xor     ebp, ebp
0x180003700  mov     [rsp+198h+TokenHandle], 0
0x180003709  mov     [rsp+198h+Wow64Process], ebp
0x18000370d  mov     rsi, rdx
0x180003710  xor     r15d, r15d
0x180003713  xor     edi, edi
0x180003715  call    cs:__imp_GetCurrentProcess
0x18000371b  mov     rcx, rax; hProcess
0x18000371e  lea     rdx, [rsp+198h+Wow64Process]; Wow64Process
0x180003723  call    cs:__imp_IsWow64Process
0x180003729  test    eax, eax
0x18000372b  jz      short loc_180003737
0x18000372d  cmp     [rsp+198h+Wow64Process], edi
0x180003731  jnz     loc_1800254A8
0x180003737  call    cs:__imp_GetCurrentThread
0x18000373d  lea     r9, [rsp+198h+TokenHandle]; TokenHandle
0x180003742  mov     edx, 2000Ch; DesiredAccess
0x180003747  mov     rcx, rax; ThreadHandle
0x18000374a  mov     r8d, 1; OpenAsSelf
0x180003750  call    cs:__imp_OpenThreadToken
0x180003756  test    eax, eax
0x180003758  jnz     loc_1800254C0
0x18000375e  call    cs:__imp_GetCurrentProcessId
0x180003764  mov     r9, cs:Source
0x18000376b  lea     rbx, ?m_szPersistCacheDir@CTemplateCacheManager@@0PADA; char near * CTemplateCacheManager::m_szPersistCacheDir
0x180003772  mov     r14d, 104h
0x180003778  mov     [rsp+198h+dwCreationFlags], eax
0x18000377c  mov     edx, r14d; BufferCount
0x18000377f  lea     r8, Format; "%s\\PID%d.TMP"
0x180003786  mov     rcx, rbx; Buffer
0x180003789  call    cs:__imp_sprintf_s
0x18000378f  test    eax, eax
0x180003791  jle     loc_18002553C
0x180003797  cmp     eax, r14d
0x18000379a  jnb     loc_18002553C
0x1800037a0  mov     rcx, rbx; lpFileName
0x1800037a3  call    cs:__imp_GetFileAttributesA
0x1800037a9  cmp     eax, 0FFFFFFFFh
0x1800037ac  jnz     loc_1800254D1
0x1800037b2  xor     edx, edx; lpSecurityAttributes
0x1800037b4  mov     rcx, rbx; lpPathName
0x1800037b7  call    cs:__imp_CreateDirectoryA
0x1800037bd  test    eax, eax
0x1800037bf  jz      loc_180025516
0x1800037c5  mov     rcx, rbx; lpFileName
0x1800037c8  call    cs:__imp_GetFileAttributesA
0x1800037ce  cmp     eax, 0FFFFFFFFh
0x1800037d1  jz      loc_180025532
0x1800037d7  test    al, 10h
0x1800037d9  jz      loc_180025532
0x1800037df  mov     rcx, cs:Source
0x1800037e6  xor     ebx, ebx
0x1800037e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800037ec  inc     rax
0x1800037ef  cmp     [rcx+rax], bl
0x1800037f2  jnz     short loc_1800037EC
0x1800037f4  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800037fb  inc     eax
0x1800037fd  mov     r8d, eax; dwBytes
0x180003800  xor     edx, edx; dwFlags
0x180003802  mov     r14d, eax
0x180003805  call    cs:__imp_HeapAlloc
0x18000380b  mov     rdi, rax
0x18000380e  test    rax, rax
0x180003811  jz      loc_180025528
0x180003817  mov     r8, cs:Source; Source
0x18000381e  mov     edx, r14d; SizeInBytes
0x180003821  mov     rcx, rax; Destination
0x180003824  call    cs:__imp_strcpy_s
0x18000382a  mov     r9, rdi; lpParameter
0x18000382d  mov     [rsp+198h+lpThreadId], rbx; lpThreadId
0x180003832  lea     r8, ?OnInitCleanup@CTemplateCacheManager@@CAKPEAX@Z; lpStartAddress
0x180003839  mov     [rsp+198h+dwCreationFlags], ebx; dwCreationFlags
0x18000383d  xor     edx, edx; dwStackSize
0x18000383f  xor     ecx, ecx; lpThreadAttributes
0x180003841  call    cs:__imp_CreateThread
0x180003847  mov     cs:?g_TemplateCache@@3VCTemplateCacheManager@@A, rax; CTemplateCacheManager g_TemplateCache
0x18000384e  cmp     cs:?g_fIsWow64Process@@3HA, 0; int g_fIsWow64Process
0x180003855  jnz     loc_180025546
0x18000385b  test    ebx, ebx
0x18000385d  jnz     loc_180025554
0x180003863  test    r15d, r15d
0x180003866  jnz     loc_18002557E
0x18000386c  cmp     cs:?g_TemplateCache@@3VCTemplateCacheManager@@A, 0; CTemplateCacheManager g_TemplateCache
0x180003874  jz      loc_18002559C
0x18000387a  cmp     cs:?m_fFailedToInitPersistCache@CTemplateCacheManager@@0HA, 0; int CTemplateCacheManager::m_fFailedToInitPersistCache
0x180003881  jnz     loc_1800255BD
0x180003887  xor     eax, eax
0x180003889  mov     rcx, [rsp+198h+var_48]
0x180003891  xor     rcx, rsp; StackCookie
0x180003894  call    __security_check_cookie
0x180003899  add     rsp, 168h
0x1800038a0  pop     r15
0x1800038a2  pop     r14
0x1800038a4  pop     rdi
0x1800038a5  pop     rsi
0x1800038a6  pop     rbp
0x1800038a7  pop     rbx
0x1800038a8  retn
0x1800254a8  xor     ecx, ecx; Wow64FsEnableRedirection
0x1800254aa  mov     cs:?g_fIsWow64Process@@3HA, 1; int g_fIsWow64Process
0x1800254b4  call    cs:__imp_Wow64EnableWow64FsRedirection
0x1800254ba  nop
0x1800254bb  jmp     loc_180003737
0x1800254c0  call    cs:__imp_RevertToSelf
0x1800254c6  mov     r15d, 1
0x1800254cc  jmp     loc_18000375E
0x1800254d1  call    cs:__imp_GetCurrentProcessId
0x1800254d7  mov     r9, cs:Source
0x1800254de  lea     r8, aSPid0DTmp; "%s\\PID0%d.TMP"
0x1800254e5  mov     rdx, r14; BufferCount
0x1800254e8  mov     [rsp+198h+dwCreationFlags], eax
0x1800254ec  lea     rcx, [rsp+198h+Buffer]; Buffer
0x1800254f1  call    cs:__imp_sprintf_s
0x1800254f7  test    eax, eax
0x1800254f9  jle     short loc_18002553C
0x1800254fb  cmp     eax, r14d
0x1800254fe  jnb     short loc_18002553C
0x180025500  lea     rdx, [rsp+198h+Buffer]; lpNewFileName
0x180025505  mov     rcx, rbx; lpExistingFileName
0x180025508  call    cs:__imp_MoveFileA
0x18002550e  test    eax, eax
0x180025510  jnz     loc_1800037B2
0x180025516  mov     ebx, 78h ; 'x'
0x18002551b  call    cs:__imp_GetLastError
0x180025521  mov     ebp, eax
0x180025523  jmp     loc_18000384E
0x180025528  mov     ebp, 8
0x18002552d  jmp     loc_18000384E
0x180025532  mov     ebx, 79h ; 'y'
0x180025537  jmp     loc_18000384E
0x18002553c  mov     ebx, 77h ; 'w'
0x180025541  jmp     loc_18000384E
0x180025546  mov     cl, 1; Wow64FsEnableRedirection
0x180025548  call    cs:__imp_Wow64EnableWow64FsRedirection
0x18002554e  nop
0x18002554f  jmp     loc_18000385B
0x180025554  mov     rcx, rsi; this
0x180025557  call    ?QueryPszAppPoolIdA@CIsapiReqInfo@@QEAAPEADXZ; CIsapiReqInfo::QueryPszAppPoolIdA(void)
0x18002555c  mov     rdx, rax; Source
0x18002555f  mov     r9d, ebp; unsigned int
0x180025562  mov     r8d, ebx; UINT
0x180025565  mov     ecx, 72h ; 'r'; uID
0x18002556a  call    ?MSG_Error@@YAXIPEBDIK@Z; MSG_Error(uint,char const *,uint,ulong)
0x18002556f  mov     cs:?m_fFailedToInitPersistCache@CTemplateCacheManager@@0HA, 1; int CTemplateCacheManager::m_fFailedToInitPersistCache
0x180025579  jmp     loc_180003863
0x18002557e  mov     rdx, [rsp+198h+TokenHandle]; Token
0x180025583  xor     ecx, ecx; Thread
0x180025585  call    cs:__imp_SetThreadToken
0x18002558b  mov     rcx, [rsp+198h+TokenHandle]; hObject
0x180025590  call    cs:__imp_CloseHandle
0x180025596  nop
0x180025597  jmp     loc_18000386C
0x18002559c  test    rdi, rdi
0x18002559f  jz      loc_18000387A
0x1800255a5  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800255ac  mov     r8, rdi; lpMem
0x1800255af  xor     edx, edx; dwFlags
0x1800255b1  call    cs:__imp_HeapFree
0x1800255b7  nop
0x1800255b8  jmp     loc_18000387A
0x1800255bd  test    rsi, rsi
0x1800255c0  jz      loc_180003887
0x1800255c6  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x1800255ca  mov     ebx, 2
0x1800255cf  mov     edx, ebx; unsigned int
0x1800255d1  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x1800255d6  test    eax, eax
0x1800255d8  jz      loc_180003887
0x1800255de  mov     rcx, [rsi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x1800255e2  mov     r8d, ebx; unsigned int
0x1800255e5  call    ?RaiseEvent@ASP_INIT_FAILURE@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@K@Z; AspReqEvents::ASP_INIT_FAILURE::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ulong)
0x1800255ea  nop
0x1800255eb  jmp     loc_180003887
```
