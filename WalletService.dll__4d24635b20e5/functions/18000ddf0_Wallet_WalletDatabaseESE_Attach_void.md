# Wallet::WalletDatabaseESE::Attach(void)

- ea: `0x18000ddf0`
- end: `0x18000de37`
- name: `?Attach@WalletDatabaseESE@Wallet@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(JET_API_PTR ulContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ddf0`
- `0x18000fe14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ddff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000de1d`
- `ESENT!JetSetSessionContext` at `0x18000de11`
- `ESENT!JetSetSessionContext` at `0x18000de11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Wallet::WalletDatabaseESE::Attach(JET_API_PTR ulContext)
{
  JET_ERR v2; // edi

  v2 = 0;
  if ( *(_DWORD *)(ulContext + 36) != GetCurrentThreadId() )
  {
    v2 = JetSetSessionContext(*(_QWORD *)(ulContext + 24), ulContext);
    if ( v2 >= 0 )
      *(_DWORD *)(ulContext + 36) = GetCurrentThreadId();
  }
  return Wallet::WalletDatabaseESE::JetErrToHR(v2);
}

```

## disassembly

```asm
0x18000ddf0  mov     [rsp+arg_0], rbx
0x18000ddf5  push    rdi
0x18000ddf6  sub     rsp, 20h
0x18000ddfa  mov     rbx, rcx
0x18000ddfd  xor     edi, edi
0x18000ddff  call    cs:__imp_GetCurrentThreadId
0x18000de05  cmp     [rbx+24h], eax
0x18000de08  jz      short loc_18000DE26
0x18000de0a  mov     rcx, [rbx+18h]; sesid
0x18000de0e  mov     rdx, rbx; ulContext
0x18000de11  call    cs:__imp_JetSetSessionContext
0x18000de17  mov     edi, eax
0x18000de19  test    eax, eax
0x18000de1b  js      short loc_18000DE26
0x18000de1d  call    cs:__imp_GetCurrentThreadId
0x18000de23  mov     [rbx+24h], eax
0x18000de26  mov     ecx, edi; int
0x18000de28  mov     rbx, [rsp+28h+arg_0]
0x18000de2d  add     rsp, 20h
0x18000de31  pop     rdi
0x18000de32  jmp     ?JetErrToHR@WalletDatabaseESE@Wallet@@CAJJ@Z; Wallet::WalletDatabaseESE::JetErrToHR(long)
```
