# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180011010`
- end: `0x1800110a7`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f1c4`
- `0x1800148a0`

## callees

- `0x1800076ac`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011060`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011060`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_18006C5D8 )
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
      if ( !_InterlockedCompareExchange64(&qword_18006C5D8, (signed __int64)ppv, 0) )
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
0x180011010  mov     [rsp+arg_0], rcx
0x180011015  push    rbx
0x180011016  sub     rsp, 30h
0x18001101a  cmp     cs:qword_18006C5D8, 0
0x180011022  jz      short loc_18001102F
0x180011024  xor     ebx, ebx
0x180011026  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18001102d  jmp     short loc_18001109E
0x18001102f  lea     rcx, [rsp+38h+arg_0]
0x180011034  mov     [rsp+38h+arg_0], 0
0x18001103d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011042  xor     edx, edx; pUnkOuter
0x180011044  lea     rax, [rsp+38h+arg_0]
0x180011049  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011050  mov     [rsp+38h+ppv], rax; ppv
0x180011055  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001105c  lea     r8d, [rdx+1]; dwClsContext
0x180011060  call    cs:__imp_CoCreateInstance
0x180011067  nop     dword ptr [rax+rax+00h]
0x18001106c  mov     ebx, eax
0x18001106e  test    eax, eax
0x180011070  js      short loc_180011094
0x180011072  mov     rcx, [rsp+38h+arg_0]
0x180011077  xor     eax, eax
0x180011079  lock cmpxchg cs:qword_18006C5D8, rcx
0x180011082  jnz     short loc_18001108D
0x180011084  mov     [rsp+38h+arg_0], 0
0x18001108d  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180011094  lea     rcx, [rsp+38h+arg_0]
0x180011099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001109e  mov     eax, ebx
0x1800110a0  add     rsp, 30h
0x1800110a4  pop     rbx
0x1800110a5  retn
```
