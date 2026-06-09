# Wallet::WalletBackgroundAgentManager::GetBackgroundServicePid(ulong *)

- ea: `0x180024ba0`
- end: `0x180024bd0`
- name: `?GetBackgroundServicePid@WalletBackgroundAgentManager@Wallet@@UEAAJPEAK@Z`
- size: `48`
- prototype: `__int64 __fastcall(Wallet::WalletBackgroundAgentManager *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x180024ba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024bbb`

## pseudocode

```c
__int64 __fastcall Wallet::WalletBackgroundAgentManager::GetBackgroundServicePid(
        Wallet::WalletBackgroundAgentManager *this,
        unsigned int *a2)
{
  unsigned int v2; // ebx

  if ( a2 )
  {
    v2 = 0;
    *a2 = GetCurrentProcessId();
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v2;
}

```

## disassembly

```asm
0x180024ba0  mov     [rsp+arg_0], rbx
0x180024ba5  push    rdi
0x180024ba6  sub     rsp, 20h
0x180024baa  mov     rdi, rdx
0x180024bad  test    rdx, rdx
0x180024bb0  jnz     short loc_180024BB9
0x180024bb2  mov     ebx, 80004003h
0x180024bb7  jmp     short loc_180024BC3
0x180024bb9  xor     ebx, ebx
0x180024bbb  call    cs:__imp_GetCurrentProcessId
0x180024bc1  mov     [rdi], eax
0x180024bc3  mov     eax, ebx
0x180024bc5  mov     rbx, [rsp+28h+arg_0]
0x180024bca  add     rsp, 20h
0x180024bce  pop     rdi
0x180024bcf  retn
```
