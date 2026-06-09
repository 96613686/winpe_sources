# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18009d730`
- end: `0x18009d801`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180098fe4`
- `0x18009d730`
- `0x1800b0460`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009d787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d7d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009d7d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d75c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d75c`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  unsigned int v8; // ebx
  __int64 Item; // rsi
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v8 = 0;
  Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      memmove(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v8 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x18009d730  mov     [rsp+arg_0], rbx
0x18009d735  mov     [rsp+arg_8], rbp
0x18009d73a  mov     [rsp+arg_10], rsi
0x18009d73f  push    rdi
0x18009d740  push    r12
0x18009d742  push    r13
0x18009d744  push    r14
0x18009d746  push    r15
0x18009d748  sub     rsp, 20h
0x18009d74c  mov     rdi, rcx
0x18009d74f  mov     r15d, r9d
0x18009d752  add     rcx, 8; lpCriticalSection
0x18009d756  mov     r13, r8
0x18009d759  mov     r12, rdx
0x18009d75c  call    cs:__imp_EnterCriticalSection
0x18009d763  nop     dword ptr [rax+rax+00h]
0x18009d768  mov     rdx, r12
0x18009d76b  mov     rcx, rdi
0x18009d76e  call    ?CreateItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18009d773  xor     ebx, ebx
0x18009d775  mov     rsi, rax
0x18009d778  test    rax, rax
0x18009d77b  jnz     short loc_18009D784
0x18009d77d  mov     ebx, 8007000Eh
0x18009d782  jmp     short loc_18009D7D1
0x18009d784  mov     rcx, r15; cb
0x18009d787  call    cs:__imp_CoTaskMemAlloc
0x18009d78e  nop     dword ptr [rax+rax+00h]
0x18009d793  mov     [rsi+10h], rax
0x18009d797  test    rax, rax
0x18009d79a  jnz     short loc_18009D7B3
0x18009d79c  mov     rax, [rdi]
0x18009d79f  mov     rdx, r12
0x18009d7a2  mov     rcx, rdi
0x18009d7a5  mov     rax, [rax+98h]
0x18009d7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7b1  jmp     short loc_18009D77D
0x18009d7b3  mov     r8, r15; Size
0x18009d7b6  mov     rdx, r13; Src
0x18009d7b9  mov     rcx, rax; void *
0x18009d7bc  call    memmove
0x18009d7c1  mov     word ptr [rsi], 1011h
0x18009d7c6  mov     [rsi+8], r15d
0x18009d7ca  mov     dword ptr [rdi+40h], 1
0x18009d7d1  lea     rcx, [rdi+8]; lpCriticalSection
0x18009d7d5  call    cs:__imp_LeaveCriticalSection
0x18009d7dc  nop     dword ptr [rax+rax+00h]
0x18009d7e1  mov     rbp, [rsp+48h+arg_8]
0x18009d7e6  mov     eax, ebx
0x18009d7e8  mov     rbx, [rsp+48h+arg_0]
0x18009d7ed  mov     rsi, [rsp+48h+arg_10]
0x18009d7f2  add     rsp, 20h
0x18009d7f6  pop     r15
0x18009d7f8  pop     r14
0x18009d7fa  pop     r13
0x18009d7fc  pop     r12
0x18009d7fe  pop     rdi
0x18009d7ff  retn
```
