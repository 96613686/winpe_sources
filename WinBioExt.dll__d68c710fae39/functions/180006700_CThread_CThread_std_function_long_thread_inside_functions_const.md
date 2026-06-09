# CThread::CThread(std::function<long (thread_inside_functions &)> const &)

- ea: `0x180006700`
- end: `0x1800068ac`
- name: `??0CThread@@AEAA@AEBV?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@@Z`
- size: `428`
- prototype: `char *__fastcall(char *lpParameter, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180006b40`

## callees

- `0x180001ec8`
- `0x180002090`
- `0x180006700`
- `0x1800068f8`
- `0x1800069e8`
- `0x180006edc`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800067ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800067ed`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000679c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800067a6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000679c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800067a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006775`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000678b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006775`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000678b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800067ca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006822`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006822`

## pseudocode

```c
char *__fastcall CThread::CThread(char *lpParameter, __int64 a2)
{
  DWORD *lpThreadId; // rsi
  char *v4; // rbx
  __int64 (__fastcall ***v5)(_QWORD, char *); // rcx
  HANDLE Thread; // rax
  _QWORD *v7; // rsi
  __int64 v8; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+40h] [rbp-28h] BYREF

  *(_DWORD *)lpParameter = 0;
  *((_QWORD *)lpParameter + 1) = 0;
  lpThreadId = (DWORD *)(lpParameter + 16);
  *((_DWORD *)lpParameter + 4) = 0;
  v4 = lpParameter + 24;
  *((_QWORD *)lpParameter + 10) = 0;
  v5 = *(__int64 (__fastcall ****)(_QWORD, char *))(a2 + 56);
  if ( v5 )
    *((_QWORD *)v4 + 7) = (**v5)(v5, v4);
  *((_QWORD *)lpParameter + 12) = 0;
  *((_DWORD *)lpParameter + 26) = 0;
  *((_QWORD *)lpParameter + 14) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)lpParameter + 15) = CreateEventW(0, 1, 0, 0);
  _InterlockedIncrement((volatile signed __int32 *)lpParameter);
  ResetEvent(*((HANDLE *)lpParameter + 14));
  ResetEvent(*((HANDLE *)lpParameter + 15));
  Thread = CreateThread(0, 0x100000u, CThread::ThreadStartup, lpParameter, 0x10004u, lpThreadId);
  *((_QWORD *)lpParameter + 1) = Thread;
  if ( !Thread )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  GetModuleHandleExW(4u, (LPCWSTR)CThread::Initialize, (HMODULE *)lpParameter + 11);
  v12 = 0;
  CThread::thread_list(&v12);
  v7 = (_QWORD *)v12;
  if ( *(_QWORD *)(v12 + 8) == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("list too long");
  v8 = *(_QWORD *)v12;
  pExceptionObject[0] = v12;
  pExceptionObject[1] = 0;
  v9 = operator new(0x18u);
  v9[2] = lpParameter;
  ++v7[1];
  v10 = *(_QWORD **)(v8 + 8);
  *v9 = v8;
  v9[1] = v10;
  *(_QWORD *)(v8 + 8) = v9;
  *v10 = v9;
  *((_QWORD *)lpParameter + 12) = *(_QWORD *)(*v7 + 8LL);
  *((_DWORD *)lpParameter + 26) = 1;
  locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(&v12);
  return lpParameter;
}

```

## disassembly

```asm
0x180006700  mov     rax, rsp
0x180006703  mov     [rax+18h], rbx
0x180006707  mov     [rax+20h], rsi
0x18000670b  mov     [rax+8], rcx
0x18000670f  push    rdi
0x180006710  sub     rsp, 60h
0x180006714  mov     rdi, rcx
0x180006717  mov     dword ptr [rcx], 0
0x18000671d  mov     qword ptr [rcx+8], 0
0x180006725  lea     rsi, [rcx+10h]
0x180006729  mov     dword ptr [rsi], 0
0x18000672f  lea     rbx, [rcx+18h]
0x180006733  mov     [rax+10h], rbx
0x180006737  mov     qword ptr [rbx+38h], 0
0x18000673f  mov     rcx, [rdx+38h]
0x180006743  test    rcx, rcx
0x180006746  jz      short loc_18000675A
0x180006748  mov     rax, [rcx]
0x18000674b  mov     rdx, rbx
0x18000674e  mov     rax, [rax]
0x180006751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006756  mov     [rbx+38h], rax
0x18000675a  mov     qword ptr [rdi+60h], 0
0x180006762  mov     dword ptr [rdi+68h], 0
0x180006769  xor     r9d, r9d; lpName
0x18000676c  xor     r8d, r8d; bInitialState
0x18000676f  lea     edx, [r9+1]; bManualReset
0x180006773  xor     ecx, ecx; lpEventAttributes
0x180006775  call    cs:__imp_CreateEventW
0x18000677b  mov     [rdi+70h], rax
0x18000677f  xor     r9d, r9d; lpName
0x180006782  xor     r8d, r8d; bInitialState
0x180006785  lea     edx, [r9+1]; bManualReset
0x180006789  xor     ecx, ecx; lpEventAttributes
0x18000678b  call    cs:__imp_CreateEventW
0x180006791  mov     [rdi+78h], rax
0x180006795  lock inc dword ptr [rdi]
0x180006798  mov     rcx, [rdi+70h]; hEvent
0x18000679c  call    cs:__imp_ResetEvent
0x1800067a2  mov     rcx, [rdi+78h]; hEvent
0x1800067a6  call    cs:__imp_ResetEvent
0x1800067ac  mov     [rsp+68h+lpThreadId], rsi; lpThreadId
0x1800067b1  mov     [rsp+68h+dwCreationFlags], 10004h; dwCreationFlags
0x1800067b9  mov     r9, rdi; lpParameter
0x1800067bc  lea     r8, ?ThreadStartup@CThread@@CAKPEAX@Z; lpStartAddress
0x1800067c3  mov     edx, 100000h; dwStackSize
0x1800067c8  xor     ecx, ecx; lpThreadAttributes
0x1800067ca  call    cs:__imp_CreateThread
0x1800067d0  mov     [rdi+8], rax
0x1800067d4  test    rax, rax
0x1800067d7  jz      loc_180006890
0x1800067dd  lea     r8, [rdi+58h]; phModule
0x1800067e1  lea     rdx, ?Initialize@CThread@@SAJXZ; lpModuleName
0x1800067e8  mov     ecx, 4; dwFlags
0x1800067ed  call    cs:__imp_GetModuleHandleExW
0x1800067f3  xorps   xmm0, xmm0
0x1800067f6  movdqu  [rsp+68h+var_38], xmm0
0x1800067fc  lea     rcx, [rsp+68h+var_38]
0x180006801  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z; CThread::thread_list(locked_pointer<std::list<CThread *>> *)
0x180006806  mov     rsi, qword ptr [rsp+68h+var_38]
0x18000680b  mov     rax, 0AAAAAAAAAAAAAAAh
0x180006815  cmp     [rsi+8], rax
0x180006819  jnz     short loc_180006829
0x18000681b  lea     rcx, aListTooLong; "list too long"
0x180006822  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180006829  mov     rbx, [rsi]
0x18000682c  mov     [rsp+68h+pExceptionObject], rsi
0x180006831  mov     [rsp+68h+var_20], 0
0x18000683a  mov     ecx, 18h; Size
0x18000683f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006844  mov     [rax+10h], rdi
0x180006848  inc     qword ptr [rsi+8]
0x18000684c  mov     rcx, [rbx+8]
0x180006850  mov     [rax], rbx
0x180006853  mov     [rax+8], rcx
0x180006857  mov     [rbx+8], rax
0x18000685b  mov     [rcx], rax
0x18000685e  mov     rax, [rsi]
0x180006861  mov     rcx, [rax+8]
0x180006865  mov     [rdi+60h], rcx
0x180006869  mov     dword ptr [rdi+68h], 1
0x180006870  lea     rcx, [rsp+68h+var_38]
0x180006875  call    ??1?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ; locked_pointer<std::list<CThread *>>::~locked_pointer<std::list<CThread *>>(void)
0x18000687a  nop
0x18000687b  mov     rax, rdi
0x18000687e  lea     r11, [rsp+68h+var_8]
0x180006883  mov     rbx, [r11+20h]
0x180006887  mov     rsi, [r11+28h]
0x18000688b  mov     rsp, r11
0x18000688e  pop     rdi
0x18000688f  retn
0x180006890  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180006895  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000689a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800068a1  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800068a6  call    _CxxThrowException_0
```
