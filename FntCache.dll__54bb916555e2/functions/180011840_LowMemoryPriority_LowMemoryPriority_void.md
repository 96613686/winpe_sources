# LowMemoryPriority::LowMemoryPriority(void)

- ea: `0x180011840`
- end: `0x1800118c8`
- name: `??0LowMemoryPriority@@QEAA@XZ`
- size: `136`
- prototype: `LowMemoryPriority *__fastcall(LowMemoryPriority *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001112c`
- `0x180011474`

## callees

- `0x180011840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011853`
- `ntdll!NtQueryInformationThread` at `0x18001187f`
- `ntdll!NtQueryInformationThread` at `0x18001187f`
- `ntdll!NtSetInformationThread` at `0x1800118aa`
- `ntdll!NtSetInformationThread` at `0x1800118aa`

## pseudocode

```c
LowMemoryPriority *__fastcall LowMemoryPriority::LowMemoryPriority(LowMemoryPriority *this)
{
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  unsigned int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)this = 0;
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v3 = CurrentThread;
  if ( NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0) >= 0
    && ThreadInformation > 2 )
  {
    v6 = 2;
    if ( NtSetInformationThread(v3, ThreadPagePriority, &v6, 4u) >= 0 )
      *(_DWORD *)this = ThreadInformation;
  }
  return this;
}

```

## disassembly

```asm
0x180011840  mov     [rsp+arg_10], rbx
0x180011845  push    rdi
0x180011846  sub     rsp, 30h
0x18001184a  mov     rbx, rcx
0x18001184d  mov     dword ptr [rcx], 0
0x180011853  call    cs:__imp_GetCurrentThread
0x180011859  mov     r9d, 4; ThreadInformationLength
0x18001185f  mov     [rsp+38h+ThreadInformation], 0
0x180011867  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x18001186c  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180011875  mov     rcx, rax; ThreadHandle
0x180011878  mov     rdi, rax
0x18001187b  lea     edx, [r9+14h]; ThreadInformationClass
0x18001187f  call    cs:__imp_NtQueryInformationThread
0x180011885  test    eax, eax
0x180011887  js      short loc_1800118BA
0x180011889  cmp     [rsp+38h+ThreadInformation], 2
0x18001188e  jbe     short loc_1800118BA
0x180011890  mov     r9d, 4; ThreadInformationLength
0x180011896  mov     [rsp+38h+arg_8], 2
0x18001189e  lea     r8, [rsp+38h+arg_8]; ThreadInformation
0x1800118a3  mov     rcx, rdi; ThreadHandle
0x1800118a6  lea     edx, [r9+14h]; ThreadInformationClass
0x1800118aa  call    cs:__imp_NtSetInformationThread
0x1800118b0  test    eax, eax
0x1800118b2  js      short loc_1800118BA
0x1800118b4  mov     eax, [rsp+38h+ThreadInformation]
0x1800118b8  mov     [rbx], eax
0x1800118ba  mov     rax, rbx
0x1800118bd  mov     rbx, [rsp+38h+arg_10]
0x1800118c2  add     rsp, 30h
0x1800118c6  pop     rdi
0x1800118c7  retn
```
