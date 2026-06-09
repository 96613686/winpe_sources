# Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(void)

- ea: `0x180008bbc`
- end: `0x180008c0e`
- name: `?Close@?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAAXXZ`
- size: `82`
- prototype: `void __fastcall(__int64)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000841c`
- `0x18000853c`
- `0x1800085f0`
- `0x180008608`
- `0x180008af4`
- `0x1800090b4`
- `0x180009274`
- `0x18000a150`
- `0x18000a424`
- `0x180010150`
- `0x180010638`
- `0x180010758`
- `0x180011a88`
- `0x180011e74`
- `0x180011ebc`
- `0x180012044`
- `0x180012304`
- `0x18001f5e0`

## callees

- `0x180008bbc`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bdb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008bf9`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::Close(__int64 a1)
{
  int LastError; // eax

  if ( *(_QWORD *)(a1 + 8) )
  {
    if ( !(**(unsigned __int8 (__fastcall ***)(__int64))a1)(a1) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180008bbc  push    rbx
0x180008bbe  sub     rsp, 20h
0x180008bc2  cmp     qword ptr [rcx+8], 0
0x180008bc7  mov     rbx, rcx
0x180008bca  jz      short loc_180008C08
0x180008bcc  mov     rax, [rcx]
0x180008bcf  mov     rax, [rax]
0x180008bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd7  test    al, al
0x180008bd9  jnz     short loc_180008C00
0x180008bdb  call    cs:__imp_GetLastError
0x180008be1  test    eax, eax
0x180008be3  jle     short loc_180008BED
0x180008be5  movzx   eax, ax
0x180008be8  or      eax, 80070000h
0x180008bed  xor     r9d, r9d; lpArguments
0x180008bf0  xor     r8d, r8d; nNumberOfArguments
0x180008bf3  mov     ecx, eax; dwExceptionCode
0x180008bf5  lea     edx, [r9+1]; dwExceptionFlags
0x180008bf9  call    cs:__imp_RaiseException
0x180008bff  int     3; Trap to Debugger
0x180008c00  mov     qword ptr [rbx+8], 0
0x180008c08  add     rsp, 20h
0x180008c0c  pop     rbx
0x180008c0d  retn
```
