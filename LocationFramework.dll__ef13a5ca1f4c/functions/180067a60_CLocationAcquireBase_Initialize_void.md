# CLocationAcquireBase::Initialize(void)

- ea: `0x180067a60`
- end: `0x180067af2`
- name: `?Initialize@CLocationAcquireBase@@UEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180078d48`
- `0x180081fac`
- `0x1800891e0`
- `0x18008db04`
- `0x18008e5a4`

## callees

- `0x180067a60`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180067aae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180067aae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067a77`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067a90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067a77`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180067a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067abd`

## pseudocode

```c
__int64 __fastcall CLocationAcquireBase::Initialize(_QWORD *pv)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  signed int v4; // ebx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax

  EventW = CreateEventW(0, 0, 0, 0);
  pv[1] = EventW;
  if ( !EventW
    || (v3 = CreateEventW(0, 0, 0, 0), (pv[2] = v3) == 0)
    || (v4 = 0,
        ThreadpoolWork = CreateThreadpoolWork(CLocationAcquireBase::AcquireLocationThreadProc, pv, 0),
        (pv[12] = ThreadpoolWork) == 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      (*(void (__fastcall **)(_QWORD *))(*pv + 48LL))(pv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180067a60  mov     [rsp+arg_0], rbx
0x180067a65  push    rdi
0x180067a66  sub     rsp, 20h
0x180067a6a  mov     rdi, rcx
0x180067a6d  xor     r9d, r9d; lpName
0x180067a70  xor     ecx, ecx; lpEventAttributes
0x180067a72  xor     r8d, r8d; bInitialState
0x180067a75  xor     edx, edx; bManualReset
0x180067a77  call    cs:__imp_CreateEventW
0x180067a7d  mov     [rdi+8], rax
0x180067a81  test    rax, rax
0x180067a84  jz      short loc_180067ABD
0x180067a86  xor     r9d, r9d; lpName
0x180067a89  xor     r8d, r8d; bInitialState
0x180067a8c  xor     edx, edx; bManualReset
0x180067a8e  xor     ecx, ecx; lpEventAttributes
0x180067a90  call    cs:__imp_CreateEventW
0x180067a96  mov     [rdi+10h], rax
0x180067a9a  test    rax, rax
0x180067a9d  jz      short loc_180067ABD
0x180067a9f  xor     r8d, r8d; pcbe
0x180067aa2  lea     rcx, ?AcquireLocationThreadProc@CLocationAcquireBase@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180067aa9  mov     rdx, rdi; pv
0x180067aac  xor     ebx, ebx
0x180067aae  call    cs:__imp_CreateThreadpoolWork
0x180067ab4  mov     [rdi+60h], rax
0x180067ab8  test    rax, rax
0x180067abb  jnz     short loc_180067AE5
0x180067abd  call    cs:__imp_GetLastError
0x180067ac3  mov     ebx, eax
0x180067ac5  test    eax, eax
0x180067ac7  jle     short loc_180067AD2
0x180067ac9  movzx   ebx, ax
0x180067acc  or      ebx, 80070000h
0x180067ad2  test    ebx, ebx
0x180067ad4  jns     short loc_180067AE5
0x180067ad6  mov     rcx, [rdi]
0x180067ad9  mov     rax, [rcx+30h]
0x180067add  mov     rcx, rdi
0x180067ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ae5  mov     eax, ebx
0x180067ae7  mov     rbx, [rsp+28h+arg_0]
0x180067aec  add     rsp, 20h
0x180067af0  pop     rdi
0x180067af1  retn
```
