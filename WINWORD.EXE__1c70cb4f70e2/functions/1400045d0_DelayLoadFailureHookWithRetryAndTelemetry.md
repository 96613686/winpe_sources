# DelayLoadFailureHookWithRetryAndTelemetry

- ea: `0x1400045d0`
- end: `0x14000471b`
- name: `DelayLoadFailureHookWithRetryAndTelemetry`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x1400044dc`
- `0x1400045d0`
- `0x1400049bc`
- `0x140004b00`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x14000465d`
- `KERNEL32!LoadLibraryExA` at `0x14000465d`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1400046c0`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x14000470f`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x1400046c0`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x14000470f`

## pseudocode

```c
HMODULE __fastcall DelayLoadFailureHookWithRetryAndTelemetry(int a1, struct DelayLoadInfo *a2)
{
  unsigned int v3; // ebx
  HMODULE Library; // rbp
  const char *v5; // r8
  Mso::Linker::RetryDelayLoad::Logging **p_szDll; // rdi
  const char *v7; // rdx
  Mso::Linker::RetryDelayLoad::Logging *v8; // r8
  Mso::Linker::RetryDelayLoad::Logging *v10; // r8
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  if ( a1 != 3 )
    return 0;
  ++g_retryDelayLoadStatistics;
  v3 = 1;
  while ( 1 )
  {
    if ( g_retryDelayLoadTestHook )
      g_retryDelayLoadTestHook(v3, 50, 0);
    if ( _pfnDliNotifyHook2 )
    {
      Library = (HMODULE)_pfnDliNotifyHook2(1u, a2);
      p_szDll = (Mso::Linker::RetryDelayLoad::Logging **)&a2->szDll;
      if ( Library )
        break;
    }
    p_szDll = (Mso::Linker::RetryDelayLoad::Logging **)&a2->szDll;
    if ( !*a2->szDll )
      __fastfail(5u);
    Library = LoadLibraryExA(a2->szDll, 0, 0x1000u);
    if ( Library )
      break;
    v11 = 10LL * v3;
    std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v11);
    if ( ++v3 > 0x32 )
    {
      Mso::Linker::RetryDelayLoad::Logging::LogRetryError(*p_szDll, v7);
      ++dword_140009B68;
      v8 = (Mso::Linker::RetryDelayLoad::Logging *)&word_140006CDE;
      if ( *p_szDll )
        v8 = *p_szDll;
      strncpy_s(Destination, 0x64u, (const char *)v8, 0xFFFFFFFFFFFFFFFFuLL);
      return 0;
    }
  }
  Mso::Linker::RetryDelayLoad::Logging::LogRetry((Mso::Linker::RetryDelayLoad::Logging *)v3, (unsigned int)*p_szDll, v5);
  ++dword_140009B64;
  v10 = (Mso::Linker::RetryDelayLoad::Logging *)&word_140006CDE;
  if ( *p_szDll )
    v10 = *p_szDll;
  strncpy_s(byte_140009B6C, 0x64u, (const char *)v10, 0xFFFFFFFFFFFFFFFFuLL);
  return Library;
}

```

## disassembly

```asm
0x1400045d0  mov     [rsp+arg_0], rbx
0x1400045d5  mov     [rsp+arg_8], rbp
0x1400045da  push    rsi
0x1400045db  push    rdi
0x1400045dc  push    r14
0x1400045de  sub     rsp, 20h
0x1400045e2  mov     rsi, rdx
0x1400045e5  cmp     ecx, 3
0x1400045e8  jnz     loc_1400046C6
0x1400045ee  inc     cs:?g_retryDelayLoadStatistics@@3URetryDelayLoadStatistics@@A; RetryDelayLoadStatistics g_retryDelayLoadStatistics
0x1400045f4  mov     ebx, 1
0x1400045f9  mov     rax, cs:?g_retryDelayLoadTestHook@@3P6AXIIPEBD@_EEA
0x140004600  test    rax, rax
0x140004603  jz      short loc_140004615
0x140004605  xor     r8d, r8d
0x140004608  mov     edx, 32h ; '2'
0x14000460d  mov     ecx, ebx
0x14000460f  call    cs:__guard_dispatch_icall_fptr
0x140004615  mov     rax, cs:__pfnDliNotifyHook2
0x14000461c  test    rax, rax
0x14000461f  jz      short loc_14000463F
0x140004621  mov     rdx, rsi
0x140004624  mov     ecx, 1
0x140004629  call    cs:__guard_dispatch_icall_fptr
0x14000462f  mov     rbp, rax
0x140004632  lea     rdi, [rsi+18h]
0x140004636  test    rax, rax
0x140004639  jnz     loc_1400046DB
0x14000463f  lea     rdi, [rsi+18h]
0x140004643  mov     rax, [rdi]
0x140004646  cmp     byte ptr [rax], 0
0x140004649  jnz     short loc_140004652
0x14000464b  mov     ecx, 5
0x140004650  int     29h; Win8: RtlFailFast(ecx)
0x140004652  xor     edx, edx; hFile
0x140004654  mov     r8d, 1000h; dwFlags
0x14000465a  mov     rcx, rax; lpLibFileName
0x14000465d  call    cs:__imp_LoadLibraryExA
0x140004663  mov     rbp, rax
0x140004666  test    rax, rax
0x140004669  jnz     short loc_1400046DB
0x14000466b  mov     eax, ebx
0x14000466d  lea     rcx, [rax+rax*4]
0x140004671  add     rcx, rcx
0x140004674  mov     [rsp+38h+arg_10], rcx
0x140004679  lea     rcx, [rsp+38h+arg_10]
0x14000467e  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x140004683  inc     ebx
0x140004685  cmp     ebx, 32h ; '2'
0x140004688  jbe     loc_1400045F9
0x14000468e  mov     rcx, [rdi]; this
0x140004691  call    ?LogRetryError@Logging@RetryDelayLoad@Linker@Mso@@YAXPEBD@Z; Mso::Linker::RetryDelayLoad::Logging::LogRetryError(char const *)
0x140004696  inc     cs:dword_140009B68
0x14000469c  mov     rax, [rdi]
0x14000469f  lea     r8, word_140006CDE
0x1400046a6  test    rax, rax
0x1400046a9  cmovnz  r8, rax; Source
0x1400046ad  mov     edx, 64h ; 'd'; SizeInBytes
0x1400046b2  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400046b9  lea     rcx, Destination; Destination
0x1400046c0  call    cs:__imp_strncpy_s
0x1400046c6  xor     eax, eax
0x1400046c8  mov     rbx, [rsp+38h+arg_0]
0x1400046cd  mov     rbp, [rsp+38h+arg_8]
0x1400046d2  add     rsp, 20h
0x1400046d6  pop     r14
0x1400046d8  pop     rdi
0x1400046d9  pop     rsi
0x1400046da  retn
0x1400046db  mov     rdx, [rdi]; unsigned int
0x1400046de  mov     ecx, ebx; this
0x1400046e0  call    ?LogRetry@Logging@RetryDelayLoad@Linker@Mso@@YAXIPEBD@Z; Mso::Linker::RetryDelayLoad::Logging::LogRetry(uint,char const *)
0x1400046e5  inc     cs:dword_140009B64
0x1400046eb  mov     rax, [rdi]
0x1400046ee  lea     r8, word_140006CDE
0x1400046f5  test    rax, rax
0x1400046f8  cmovnz  r8, rax; Source
0x1400046fc  mov     edx, 64h ; 'd'; SizeInBytes
0x140004701  mov     r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140004708  lea     rcx, byte_140009B6C; Destination
0x14000470f  call    cs:__imp_strncpy_s
0x140004715  mov     rax, rbp
0x140004718  jmp     short loc_1400046C8
```
