# LowMemoryPriority::~LowMemoryPriority(void)

- ea: `0x18008f4dc`
- end: `0x18008f50d`
- name: `??1LowMemoryPriority@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(LowMemoryPriority *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001112c`
- `0x1800dd345`
- `0x1800dd357`

## callees

- `0x18008f4dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f4ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f4ea`
- `ntdll!NtSetInformationThread` at `0x18008f502`
- `ntdll!NtSetInformationThread` at `0x18008f502`

## pseudocode

```c
void __fastcall LowMemoryPriority::~LowMemoryPriority(LowMemoryPriority *this)
{
  HANDLE CurrentThread; // rax
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_DWORD *)this )
  {
    ThreadInformation = *(_DWORD *)this;
    CurrentThread = GetCurrentThread();
    NtSetInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u);
  }
}

```

## disassembly

```asm
0x18008f4dc  sub     rsp, 28h
0x18008f4e0  mov     eax, [rcx]
0x18008f4e2  test    eax, eax
0x18008f4e4  jz      short loc_18008F508
0x18008f4e6  mov     [rsp+28h+ThreadInformation], eax
0x18008f4ea  call    cs:__imp_GetCurrentThread
0x18008f4f0  mov     r9d, 4; ThreadInformationLength
0x18008f4f6  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18008f4fb  mov     rcx, rax; ThreadHandle
0x18008f4fe  lea     edx, [r9+14h]; ThreadInformationClass
0x18008f502  call    cs:__imp_NtSetInformationThread
0x18008f508  add     rsp, 28h
0x18008f50c  retn
```
