# Wallet::WalletDatabaseESE::Detach(void)

- ea: `0x18000e5e0`
- end: `0x18000e622`
- name: `?Detach@WalletDatabaseESE@Wallet@@UEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(Wallet::WalletDatabaseESE *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e5e0`
- `0x18000fe14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5ef`
- `ESENT!JetResetSessionContext` at `0x18000e5fe`
- `ESENT!JetResetSessionContext` at `0x18000e5fe`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDatabaseESE::Detach(Wallet::WalletDatabaseESE *this)
{
  JET_ERR v2; // edi

  v2 = 0;
  if ( *((_DWORD *)this + 9) == GetCurrentThreadId() )
  {
    v2 = JetResetSessionContext(*((_QWORD *)this + 3));
    if ( v2 >= 0 )
      *((_DWORD *)this + 9) = 0;
  }
  return Wallet::WalletDatabaseESE::JetErrToHR(v2);
}

```

## disassembly

```asm
0x18000e5e0  mov     [rsp+arg_0], rbx
0x18000e5e5  push    rdi
0x18000e5e6  sub     rsp, 20h
0x18000e5ea  mov     rbx, rcx
0x18000e5ed  xor     edi, edi
0x18000e5ef  call    cs:__imp_GetCurrentThreadId
0x18000e5f5  cmp     [rbx+24h], eax
0x18000e5f8  jnz     short loc_18000E611
0x18000e5fa  mov     rcx, [rbx+18h]; sesid
0x18000e5fe  call    cs:__imp_JetResetSessionContext
0x18000e604  mov     edi, eax
0x18000e606  test    eax, eax
0x18000e608  js      short loc_18000E611
0x18000e60a  mov     dword ptr [rbx+24h], 0
0x18000e611  mov     ecx, edi; int
0x18000e613  mov     rbx, [rsp+28h+arg_0]
0x18000e618  add     rsp, 20h
0x18000e61c  pop     rdi
0x18000e61d  jmp     ?JetErrToHR@WalletDatabaseESE@Wallet@@CAJJ@Z; Wallet::WalletDatabaseESE::JetErrToHR(long)
```
