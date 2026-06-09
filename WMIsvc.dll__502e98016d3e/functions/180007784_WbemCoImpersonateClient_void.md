# WbemCoImpersonateClient(void)

- ea: `0x180007784`
- end: `0x1800077d7`
- name: `?WbemCoImpersonateClient@@YAJXZ`
- size: `83`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076e0`

## callees

- `0x180007784`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000779f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000779f`

## pseudocode

```c
__int64 WbemCoImpersonateClient(void)
{
  unsigned int v0; // ebx
  void *ppInterface; // [rsp+30h] [rbp+8h] BYREF

  ppInterface = 0;
  v0 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  if ( !v0 )
  {
    v0 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  }
  return v0;
}

```

## disassembly

```asm
0x180007784  push    rbx
0x180007786  sub     rsp, 20h
0x18000778a  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x18000778f  mov     [rsp+28h+ppInterface], 0
0x180007798  lea     rcx, IID_IServerSecurity; riid
0x18000779f  call    cs:__imp_CoGetCallContext
0x1800077a5  mov     ebx, eax
0x1800077a7  test    eax, eax
0x1800077a9  jnz     short loc_1800077CF
0x1800077ab  mov     rcx, [rsp+28h+ppInterface]
0x1800077b0  mov     rax, [rcx]
0x1800077b3  mov     rax, [rax+20h]
0x1800077b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077bc  mov     rcx, [rsp+28h+ppInterface]
0x1800077c1  mov     ebx, eax
0x1800077c3  mov     rax, [rcx]
0x1800077c6  mov     rax, [rax+10h]
0x1800077ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077cf  mov     eax, ebx
0x1800077d1  add     rsp, 20h
0x1800077d5  pop     rbx
0x1800077d6  retn
```
