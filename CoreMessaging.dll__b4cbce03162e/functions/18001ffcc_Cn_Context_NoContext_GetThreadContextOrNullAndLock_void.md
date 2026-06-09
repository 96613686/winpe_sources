# Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)

- ea: `0x18001ffcc`
- end: `0x180020061`
- name: `?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ`
- size: `149`
- prototype: `struct Cn::Context *(void)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180007230`
- `0x1800077a0`
- `0x18000870c`
- `0x18001e220`
- `0x18001e270`
- `0x18001e760`
- `0x18001ef10`
- `0x18001f3b0`
- `0x18001f9b0`
- `0x1800200b0`
- `0x1800208e0`
- `0x180020e70`
- `0x180021200`
- `0x180021540`

## callees

- `0x18001ffcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ffe6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020012`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ffff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ffff`

## pseudocode

```c
struct Cn::Context *Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
{
  Cn::Engine::Lock *v0; // rbx
  int v1; // ecx
  DWORD CurrentThreadId; // eax
  struct Cn::Context *i; // rdi

  v0 = Cn::Context::s_lockType;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)Cn::Context::s_lockType + 16));
  v1 = *((_DWORD *)v0 + 15);
  *((_DWORD *)v0 + 15) = v1 + 1;
  if ( !v1 )
  {
    *((_QWORD *)v0 + 8) = TlsGetValue(Cn::Context::s_tlsStorage);
    *((_DWORD *)v0 + 18) = GetCurrentThreadId();
  }
  CurrentThreadId = GetCurrentThreadId();
  for ( i = Cn::Context::s_pctxHead;
        i && *((_DWORD *)i + 10) != CurrentThreadId;
        i = (struct Cn::Context *)*((_QWORD *)i + 13) )
  {
    ;
  }
  if ( (*((_DWORD *)v0 + 15))-- == 1 )
  {
    *((_QWORD *)v0 + 8) = 0;
    *((_DWORD *)v0 + 18) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v0 + 16));
  return i;
}

```

## disassembly

```asm
0x18001ffcc  mov     [rsp+arg_8], rbx
0x18001ffd1  mov     [rsp+arg_10], rsi
0x18001ffd6  push    rdi
0x18001ffd7  sub     rsp, 20h
0x18001ffdb  mov     rbx, cs:?s_lockType@Context@Cn@@0V?$SmartPtr@VLock@Engine@Cn@@@CFlat@@A; CFlat::SmartPtr<Cn::Engine::Lock> Cn::Context::s_lockType
0x18001ffe2  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001ffe6  call    cs:__imp_EnterCriticalSection
0x18001ffec  mov     ecx, [rbx+3Ch]
0x18001ffef  lea     eax, [rcx+1]
0x18001fff2  mov     [rbx+3Ch], eax
0x18001fff5  test    ecx, ecx
0x18001fff7  jnz     short loc_180020012
0x18001fff9  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001ffff  call    cs:__imp_TlsGetValue
0x180020005  mov     [rbx+40h], rax
0x180020009  call    cs:__imp_GetCurrentThreadId
0x18002000f  mov     [rbx+48h], eax
0x180020012  call    cs:__imp_GetCurrentThreadId
0x180020018  mov     rdi, cs:?s_pctxHead@Context@Cn@@0PEAV12@EA; Cn::Context * Cn::Context::s_pctxHead
0x18002001f  test    rdi, rdi
0x180020022  jz      short loc_18002002F
0x180020024  cmp     [rdi+28h], eax
0x180020027  jz      short loc_18002002F
0x180020029  mov     rdi, [rdi+68h]
0x18002002d  jmp     short loc_18002001F
0x18002002f  add     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x180020033  jnz     short loc_180020044
0x180020035  mov     qword ptr [rbx+40h], 0
0x18002003d  mov     dword ptr [rbx+48h], 0
0x180020044  lea     rcx, [rbx+10h]; lpCriticalSection
0x180020048  call    cs:__imp_LeaveCriticalSection
0x18002004e  mov     rbx, [rsp+28h+arg_8]
0x180020053  mov     rax, rdi
0x180020056  mov     rsi, [rsp+28h+arg_10]
0x18002005b  add     rsp, 20h
0x18002005f  pop     rdi
0x180020060  retn
```
