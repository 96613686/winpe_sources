# CNetworkExplorerFolder::GetFactory(INetworkItemFactory * *)

- ea: `0x180002874`
- end: `0x1800028e6`
- name: `?GetFactory@CNetworkExplorerFolder@@QEAAJPEAPEAUINetworkItemFactory@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, struct INetworkItemFactory **)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c80`
- `0x180002570`
- `0x1800027b0`
- `0x180006030`
- `0x180006df0`
- `0x18000c690`

## callees

- `0x180002874`
- `0x180010010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x1800028d8`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800028d8`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetFactory(CNetworkExplorerFolder *this, struct INetworkItemFactory **a2)
{
  void **ppv; // rdi
  HRESULT Instance; // ebx

  ppv = (void **)((char *)this + 112);
  *a2 = 0;
  if ( *((_QWORD *)this + 14) )
  {
    Instance = 0;
  }
  else
  {
    Instance = SHCoCreateInstance(0, &CLSID_NetworkItemFactory, 0, &GUID_72400b6a_d4d1_4318_99f8_5201c05db416, ppv);
    if ( Instance < 0 )
      return (unsigned int)Instance;
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)*ppv + 8LL))(*ppv);
  *a2 = (struct INetworkItemFactory *)*ppv;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002874  mov     [rsp+arg_0], rbx
0x180002879  mov     [rsp+arg_8], rsi
0x18000287e  push    rdi
0x18000287f  sub     rsp, 30h
0x180002883  lea     rdi, [rcx+70h]
0x180002887  mov     qword ptr [rdx], 0
0x18000288e  cmp     qword ptr [rdi], 0
0x180002892  mov     rsi, rdx
0x180002895  jz      short loc_1800028C0
0x180002897  xor     ebx, ebx
0x180002899  mov     rcx, [rdi]
0x18000289c  mov     rdx, [rcx]
0x18000289f  mov     rax, [rdx+8]
0x1800028a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a8  mov     rcx, [rdi]
0x1800028ab  mov     [rsi], rcx
0x1800028ae  mov     rsi, [rsp+38h+arg_8]
0x1800028b3  mov     eax, ebx
0x1800028b5  mov     rbx, [rsp+38h+arg_0]
0x1800028ba  add     rsp, 30h
0x1800028be  pop     rdi
0x1800028bf  retn
0x1800028c0  lea     r9, _GUID_72400b6a_d4d1_4318_99f8_5201c05db416; riid
0x1800028c7  mov     [rsp+38h+ppv], rdi; ppv
0x1800028cc  xor     r8d, r8d; pUnkOuter
0x1800028cf  lea     rdx, CLSID_NetworkItemFactory; pclsid
0x1800028d6  xor     ecx, ecx; pszCLSID
0x1800028d8  call    cs:__imp_SHCoCreateInstance
0x1800028de  mov     ebx, eax
0x1800028e0  test    eax, eax
0x1800028e2  jns     short loc_180002899
0x1800028e4  jmp     short loc_1800028AE
```
