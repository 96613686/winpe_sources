# I_TransactionManagerInitializeThreadPool(_TRANSACTION_MANAGER_STATE *)

- ea: `0x18002c480`
- end: `0x18002c524`
- name: `?I_TransactionManagerInitializeThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z`
- size: `164`
- prototype: `unsigned int __fastcall(struct _TRANSACTION_MANAGER_STATE *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c9e0`

## callees

- `0x18002c438`
- `0x18002c480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002c4dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002c4dd`

## pseudocode

```c
__int64 __fastcall I_TransactionManagerInitializeThreadPool(struct _TRANSACTION_MANAGER_STATE *a1)
{
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD LastError; // edi
  void *v4; // rcx

  *((_DWORD *)a1 + 4) = 3;
  *((_DWORD *)a1 + 19) = 1;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *((_QWORD *)a1 + 6) = 0;
  *((_QWORD *)a1 + 7) = 0;
  *((_QWORD *)a1 + 8) = 0;
  *((_DWORD *)a1 + 18) = 0;
  *((_DWORD *)a1 + 20) = 72;
  *((_DWORD *)a1 + 24) = 1;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)a1 + 11) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v4 = g_hInst;
    LastError = 0;
    *((_QWORD *)a1 + 5) = 0;
    *((_QWORD *)a1 + 4) = ThreadpoolCleanupGroup;
    *((_QWORD *)a1 + 6) = v4;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      I_TransactionManagerCloseThreadPool(a1);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002c480  mov     [rsp+arg_0], rbx
0x18002c485  push    rdi
0x18002c486  sub     rsp, 20h
0x18002c48a  mov     eax, 1
0x18002c48f  mov     dword ptr [rcx+10h], 3
0x18002c496  mov     [rcx+4Ch], eax
0x18002c499  mov     rbx, rcx
0x18002c49c  mov     qword ptr [rcx+18h], 0
0x18002c4a4  mov     qword ptr [rcx+20h], 0
0x18002c4ac  mov     qword ptr [rcx+28h], 0
0x18002c4b4  mov     qword ptr [rcx+30h], 0
0x18002c4bc  mov     qword ptr [rcx+38h], 0
0x18002c4c4  mov     qword ptr [rcx+40h], 0
0x18002c4cc  mov     dword ptr [rcx+48h], 0
0x18002c4d3  mov     dword ptr [rcx+50h], 48h ; 'H'
0x18002c4da  mov     [rcx+60h], eax
0x18002c4dd  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002c4e3  mov     [rbx+58h], rax
0x18002c4e7  test    rax, rax
0x18002c4ea  jnz     short loc_18002C502
0x18002c4ec  call    cs:__imp_GetLastError
0x18002c4f2  mov     edi, eax
0x18002c4f4  test    eax, eax
0x18002c4f6  jz      short loc_18002C517
0x18002c4f8  mov     rcx, rbx; struct _TRANSACTION_MANAGER_STATE *
0x18002c4fb  call    ?I_TransactionManagerCloseThreadPool@@YAKPEAU_TRANSACTION_MANAGER_STATE@@@Z; I_TransactionManagerCloseThreadPool(_TRANSACTION_MANAGER_STATE *)
0x18002c500  jmp     short loc_18002C517
0x18002c502  mov     rcx, cs:?g_hInst@@3PEAXEA; void * g_hInst
0x18002c509  xor     edi, edi
0x18002c50b  mov     [rbx+28h], rdi
0x18002c50f  mov     [rbx+20h], rax
0x18002c513  mov     [rbx+30h], rcx
0x18002c517  mov     rbx, [rsp+28h+arg_0]
0x18002c51c  mov     eax, edi
0x18002c51e  add     rsp, 20h
0x18002c522  pop     rdi
0x18002c523  retn
```
