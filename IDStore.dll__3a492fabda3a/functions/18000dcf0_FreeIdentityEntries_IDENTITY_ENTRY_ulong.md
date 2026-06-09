# FreeIdentityEntries(_IDENTITY_ENTRY *,ulong)

- ea: `0x18000dcf0`
- end: `0x18000dd7e`
- name: `?FreeIdentityEntries@@YAXPEAU_IDENTITY_ENTRY@@K@Z`
- size: `142`
- prototype: `void __fastcall(LPVOID *pv, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x18000dcf0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd68`

## pseudocode

```c
void __fastcall FreeIdentityEntries(LPVOID *pv, unsigned int a2)
{
  unsigned int v3; // ebp
  __int64 v5; // r14
  LPVOID v6; // rcx

  if ( pv )
  {
    v3 = 0;
    if ( a2 )
    {
      v5 = 0;
      do
      {
        CoTaskMemFree(pv[4 * v5]);
        CoTaskMemFree(pv[4 * v5 + 1]);
        v6 = pv[4 * v5 + 2];
        if ( v6 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
        ++v3;
        ++v5;
      }
      while ( v3 < a2 );
    }
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18000dcf0  test    rcx, rcx
0x18000dcf3  jz      locret_18000DD7D
0x18000dcf9  mov     [rsp+arg_18], rbx
0x18000dcfe  push    rsi
0x18000dcff  sub     rsp, 20h
0x18000dd03  mov     [rsp+28h+arg_0], rbp
0x18000dd08  mov     esi, edx
0x18000dd0a  xor     ebp, ebp
0x18000dd0c  mov     rbx, rcx
0x18000dd0f  test    edx, edx
0x18000dd11  jz      short loc_18000DD65
0x18000dd13  mov     [rsp+28h+arg_8], rdi
0x18000dd18  mov     [rsp+28h+arg_10], r14
0x18000dd1d  xor     r14d, r14d
0x18000dd20  mov     rdi, r14
0x18000dd23  shl     rdi, 5
0x18000dd27  mov     rcx, [rdi+rbx]; pv
0x18000dd2b  call    cs:__imp_CoTaskMemFree
0x18000dd31  mov     rcx, [rdi+rbx+8]; pv
0x18000dd36  call    cs:__imp_CoTaskMemFree
0x18000dd3c  mov     rcx, [rdi+rbx+10h]
0x18000dd41  test    rcx, rcx
0x18000dd44  jz      short loc_18000DD52
0x18000dd46  mov     rax, [rcx]
0x18000dd49  mov     rax, [rax+10h]
0x18000dd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd52  inc     ebp
0x18000dd54  inc     r14
0x18000dd57  cmp     ebp, esi
0x18000dd59  jb      short loc_18000DD20
0x18000dd5b  mov     r14, [rsp+28h+arg_10]
0x18000dd60  mov     rdi, [rsp+28h+arg_8]
0x18000dd65  mov     rcx, rbx; pv
0x18000dd68  call    cs:__imp_CoTaskMemFree
0x18000dd6e  mov     rbp, [rsp+28h+arg_0]
0x18000dd73  mov     rbx, [rsp+28h+arg_18]
0x18000dd78  add     rsp, 20h
0x18000dd7c  pop     rsi
0x18000dd7d  retn
```
