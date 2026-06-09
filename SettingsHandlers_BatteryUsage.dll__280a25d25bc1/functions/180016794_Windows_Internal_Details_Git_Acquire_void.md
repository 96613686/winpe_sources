# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180016794`
- end: `0x180016824`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800156f8`
- `0x18001a500`
- `0x18002d6f0`

## callees

- `0x180004cfc`
- `0x180016794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800167e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800167e4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_18007A9A0 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_18007A9A0, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180016794  mov     [rsp+arg_0], rcx
0x180016799  push    rbx
0x18001679a  sub     rsp, 30h
0x18001679e  cmp     cs:qword_18007A9A0, 0
0x1800167a6  jz      short loc_1800167B3
0x1800167a8  xor     ebx, ebx
0x1800167aa  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x1800167b1  jmp     short loc_18001681C
0x1800167b3  lea     rcx, [rsp+38h+arg_0]
0x1800167b8  mov     [rsp+38h+arg_0], 0
0x1800167c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800167c6  xor     edx, edx; pUnkOuter
0x1800167c8  lea     rax, [rsp+38h+arg_0]
0x1800167cd  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800167d4  mov     [rsp+38h+ppv], rax; ppv
0x1800167d9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800167e0  lea     r8d, [rdx+1]; dwClsContext
0x1800167e4  call    cs:__imp_CoCreateInstance
0x1800167ea  mov     ebx, eax
0x1800167ec  test    eax, eax
0x1800167ee  js      short loc_180016812
0x1800167f0  mov     rcx, [rsp+38h+arg_0]
0x1800167f5  xor     eax, eax
0x1800167f7  lock cmpxchg cs:qword_18007A9A0, rcx
0x180016800  jnz     short loc_18001680B
0x180016802  mov     [rsp+38h+arg_0], 0
0x18001680b  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180016812  lea     rcx, [rsp+38h+arg_0]
0x180016817  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001681c  mov     eax, ebx
0x18001681e  add     rsp, 30h
0x180016822  pop     rbx
0x180016823  retn
```
