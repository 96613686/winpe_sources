# CNetworkItemEnumerator::_IsDefView(void)

- ea: `0x18000c930`
- end: `0x18000c97c`
- name: `?_IsDefView@CNetworkItemEnumerator@@AEAAHXZ`
- size: `76`
- prototype: `__int64 __fastcall(CNetworkItemEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003610`

## callees

- `0x18000c930`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000c954`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000c954`

## pseudocode

```c
__int64 __fastcall CNetworkItemEnumerator::_IsDefView(CNetworkItemEnumerator *this)
{
  IUnknown *v1; // rcx
  unsigned int v2; // ebx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF

  v1 = (IUnknown *)*((_QWORD *)this + 9);
  v2 = 0;
  ppvOut = 0;
  if ( IUnknown_QueryService(v1, &IID_IFolderView, &GUID_1af3a467_214f_4298_908e_06b03e0b39f9, &ppvOut) >= 0 )
  {
    v2 = 1;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c930  push    rbx
0x18000c932  sub     rsp, 20h
0x18000c936  mov     rcx, [rcx+48h]; punk
0x18000c93a  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x18000c93f  xor     ebx, ebx
0x18000c941  lea     r8, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9; riid
0x18000c948  lea     rdx, IID_IFolderView; guidService
0x18000c94f  mov     [rsp+28h+ppvOut], rbx
0x18000c954  call    cs:__imp_IUnknown_QueryService
0x18000c95a  test    eax, eax
0x18000c95c  js      short loc_18000C974
0x18000c95e  mov     rcx, [rsp+28h+ppvOut]
0x18000c963  mov     ebx, 1
0x18000c968  mov     rdx, [rcx]
0x18000c96b  mov     rax, [rdx+10h]
0x18000c96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c974  mov     eax, ebx
0x18000c976  add     rsp, 20h
0x18000c97a  pop     rbx
0x18000c97b  retn
```
