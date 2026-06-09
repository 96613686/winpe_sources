# MsUmeRegisterDeviceContext

- ea: `0x140087610`
- end: `0x140087695`
- name: `MsUmeRegisterDeviceContext`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006f5e0`

## callees

- `0x140087610`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x140087644`
- `ntdll!RtlGetLastNtStatus` at `0x140087644`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140087633`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140087670`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140087633`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140087670`

## pseudocode

```c
NTSTATUS __fastcall MsUmeRegisterDeviceContext(__int64 a1)
{
  void *v2; // rcx
  HANDLE *v4; // rbx
  HANDLE *v5; // rdi

  v2 = *(void **)a1;
  if ( v2 && !CreateIoCompletionPort(v2, ExistingCompletionPort, 1u, 0) )
    return RtlGetLastNtStatus();
  v4 = *(HANDLE **)(a1 + 32);
  v5 = *(HANDLE **)(a1 + 40);
  while ( v4 != v5 )
  {
    if ( !CreateIoCompletionPort(*v4, ExistingCompletionPort, 1u, 0) )
      return RtlGetLastNtStatus();
    ++v4;
  }
  return 0;
}

```

## disassembly

```asm
0x140087610  mov     [rsp+arg_0], rbx
0x140087615  push    rdi
0x140087616  sub     rsp, 20h
0x14008761a  mov     rdi, rcx
0x14008761d  mov     rcx, [rcx]; FileHandle
0x140087620  test    rcx, rcx
0x140087623  jz      short loc_140087652
0x140087625  mov     rdx, cs:ExistingCompletionPort; ExistingCompletionPort
0x14008762c  xor     r9d, r9d; NumberOfConcurrentThreads
0x14008762f  lea     r8d, [r9+1]; CompletionKey
0x140087633  call    cs:__imp_CreateIoCompletionPort
0x14008763a  nop     dword ptr [rax+rax+00h]
0x14008763f  test    rax, rax
0x140087642  jnz     short loc_140087652
0x140087644  call    cs:__imp_RtlGetLastNtStatus
0x14008764b  nop     dword ptr [rax+rax+00h]
0x140087650  jmp     short loc_140087689
0x140087652  mov     rbx, [rdi+20h]
0x140087656  mov     rdi, [rdi+28h]
0x14008765a  cmp     rbx, rdi
0x14008765d  jz      short loc_140087687
0x14008765f  mov     rdx, cs:ExistingCompletionPort; ExistingCompletionPort
0x140087666  xor     r9d, r9d; NumberOfConcurrentThreads
0x140087669  mov     rcx, [rbx]; FileHandle
0x14008766c  lea     r8d, [r9+1]; CompletionKey
0x140087670  call    cs:__imp_CreateIoCompletionPort
0x140087677  nop     dword ptr [rax+rax+00h]
0x14008767c  test    rax, rax
0x14008767f  jz      short loc_140087644
0x140087681  add     rbx, 8
0x140087685  jmp     short loc_14008765A
0x140087687  xor     eax, eax
0x140087689  mov     rbx, [rsp+28h+arg_0]
0x14008768e  add     rsp, 20h
0x140087692  pop     rdi
0x140087693  retn
```
