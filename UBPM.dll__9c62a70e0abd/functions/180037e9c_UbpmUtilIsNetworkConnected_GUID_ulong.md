# UbpmUtilIsNetworkConnected(_GUID *,ulong *)

- ea: `0x180037e9c`
- end: `0x180037f7d`
- name: `?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dda4`
- `0x18000e0a8`

## callees

- `0x180037e9c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037ee6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037ee6`

## pseudocode

```c
__int64 __fastcall UbpmUtilIsNetworkConnected(struct _GUID *a1, unsigned int *a2)
{
  HRESULT v4; // ebx
  _QWORD v6[3]; // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  ppv = 0;
  v6[0] = 0;
  v4 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &IID_INetworkListManagerPrivate, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD *))(*(_QWORD *)ppv + 48LL))(ppv, a1, v6);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v6[0] + 96LL))(v6[0], &v7);
      if ( v4 >= 0 )
      {
        *a2 = v7 & 1;
        v4 = 0;
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v6[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6[0] + 16LL))(v6[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180037e9c  mov     rax, rsp
0x180037e9f  mov     [rax+8], rbx
0x180037ea3  mov     [rax+10h], rsi
0x180037ea7  push    rdi
0x180037ea8  sub     rsp, 40h
0x180037eac  mov     rdi, rdx
0x180037eaf  mov     dword ptr [rax+18h], 0
0x180037eb6  xor     edx, edx; pUnkOuter
0x180037eb8  mov     qword ptr [rax+20h], 0
0x180037ec0  mov     qword ptr [rax-18h], 0
0x180037ec8  lea     rax, [rax+20h]
0x180037ecc  mov     rsi, rcx
0x180037ecf  mov     [rsp+48h+ppv], rax; ppv
0x180037ed4  lea     r9, IID_INetworkListManagerPrivate; riid
0x180037edb  lea     r8d, [rdx+4]; dwClsContext
0x180037edf  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180037ee6  call    cs:__imp_CoCreateInstance
0x180037eed  nop     dword ptr [rax+rax+00h]
0x180037ef2  mov     ebx, eax
0x180037ef4  test    eax, eax
0x180037ef6  js      short loc_180037F3E
0x180037ef8  mov     rcx, [rsp+48h+arg_18]
0x180037efd  lea     r8, [rsp+48h+var_18]
0x180037f02  mov     rdx, rsi
0x180037f05  mov     rax, [rcx]
0x180037f08  mov     rax, [rax+30h]
0x180037f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f11  mov     ebx, eax
0x180037f13  test    eax, eax
0x180037f15  js      short loc_180037F3E
0x180037f17  mov     rcx, [rsp+48h+var_18]
0x180037f1c  lea     rdx, [rsp+48h+arg_10]
0x180037f21  mov     rax, [rcx]
0x180037f24  mov     rax, [rax+60h]
0x180037f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f2d  mov     ebx, eax
0x180037f2f  test    eax, eax
0x180037f31  js      short loc_180037F3E
0x180037f33  mov     eax, [rsp+48h+arg_10]
0x180037f37  and     eax, 1
0x180037f3a  mov     [rdi], eax
0x180037f3c  xor     ebx, ebx
0x180037f3e  mov     rcx, [rsp+48h+arg_18]
0x180037f43  test    rcx, rcx
0x180037f46  jz      short loc_180037F54
0x180037f48  mov     rax, [rcx]
0x180037f4b  mov     rax, [rax+10h]
0x180037f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f54  mov     rcx, [rsp+48h+var_18]
0x180037f59  test    rcx, rcx
0x180037f5c  jz      short loc_180037F6A
0x180037f5e  mov     rax, [rcx]
0x180037f61  mov     rax, [rax+10h]
0x180037f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f6a  mov     rsi, [rsp+48h+arg_8]
0x180037f6f  mov     eax, ebx
0x180037f71  mov     rbx, [rsp+48h+arg_0]
0x180037f76  add     rsp, 40h
0x180037f7a  pop     rdi
0x180037f7b  retn
```
