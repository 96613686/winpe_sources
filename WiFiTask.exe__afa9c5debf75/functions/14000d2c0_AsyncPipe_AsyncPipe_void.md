# AsyncPipe::~AsyncPipe(void)

- ea: `0x14000d2c0`
- end: `0x14000d368`
- name: `??1AsyncPipe@@EEAA@XZ`
- size: `168`
- prototype: `void __fastcall(AsyncPipe *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d370`

## callees

- `0x14000d1f4`
- `0x14000d2c0`
- `0x14000e1b4`
- `0x14000e3d8`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000d2da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000d2da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d2e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d2f4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d2e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000d2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d32e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d32e`

## pseudocode

```c
void __fastcall AsyncPipe::~AsyncPipe(AsyncPipe *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  DWORD LastError; // eax
  const char *v6; // rcx

  *(_QWORD *)this = &AsyncPipe::`vftable';
  CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 193));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 != (void *)-1LL && !CloseHandle(v4) )
  {
    LastError = GetLastError();
    __FatalError(v6, 0x62u, "CloseHandle", LastError);
  }
  std::deque<std::vector<unsigned char> *,std::allocator<std::vector<unsigned char> *>>::~deque<std::vector<unsigned char> *,std::allocator<std::vector<unsigned char> *>>((char *)this + 48);
  SynchronizedObject::~SynchronizedObject(this);
}

```

## disassembly

```asm
0x14000d2c0  push    rbx
0x14000d2c2  sub     rsp, 20h
0x14000d2c6  mov     rbx, rcx
0x14000d2c9  lea     rax, ??_7AsyncPipe@@6B@; const AsyncPipe::`vftable'
0x14000d2d0  mov     [rcx], rax
0x14000d2d3  mov     rcx, [rcx+608h]; ptpcg
0x14000d2da  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14000d2e0  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x14000d2e7  call    cs:__imp_DeleteCriticalSection
0x14000d2ed  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x14000d2f4  call    cs:__imp_DeleteCriticalSection
0x14000d2fa  mov     rcx, [rbx+28h]
0x14000d2fe  test    rcx, rcx
0x14000d301  jz      short loc_14000D30F
0x14000d303  mov     rax, [rcx]
0x14000d306  mov     rax, [rax+10h]
0x14000d30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d30f  mov     rcx, [rbx+20h]
0x14000d313  test    rcx, rcx
0x14000d316  jz      short loc_14000D324
0x14000d318  mov     rax, [rcx]
0x14000d31b  mov     rax, [rax+10h]
0x14000d31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d324  mov     rcx, [rbx+18h]; hObject
0x14000d328  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000d32c  jz      short loc_14000D352
0x14000d32e  call    cs:__imp_CloseHandle
0x14000d334  test    eax, eax
0x14000d336  jnz     short loc_14000D352
0x14000d338  call    cs:__imp_GetLastError
0x14000d33e  mov     r9d, eax; unsigned int
0x14000d341  lea     r8, aClosehandle; "CloseHandle"
0x14000d348  mov     edx, 62h ; 'b'; unsigned int
0x14000d34d  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d352  lea     rcx, [rbx+30h]
0x14000d356  call    ??1?$deque@PEAV?$vector@EV?$allocator@E@std@@@std@@V?$allocator@PEAV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>::~deque<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>(void)
0x14000d35b  mov     rcx, rbx; this
0x14000d35e  add     rsp, 20h
0x14000d362  pop     rbx
0x14000d363  jmp     ??1SynchronizedObject@@MEAA@XZ; SynchronizedObject::~SynchronizedObject(void)
```
