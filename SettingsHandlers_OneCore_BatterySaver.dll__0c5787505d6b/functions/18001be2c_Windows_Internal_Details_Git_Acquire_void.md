# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x18001be2c`
- end: `0x18001bebc`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019cf8`
- `0x180023450`
- `0x180023548`

## callees

- `0x18000cfa4`
- `0x18001be2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001be7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001be7c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_1800669C8 )
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
      if ( !_InterlockedCompareExchange64(&qword_1800669C8, (signed __int64)ppv, 0) )
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
0x18001be2c  mov     [rsp+arg_0], rcx
0x18001be31  push    rbx
0x18001be32  sub     rsp, 30h
0x18001be36  cmp     cs:qword_1800669C8, 0
0x18001be3e  jz      short loc_18001BE4B
0x18001be40  xor     ebx, ebx
0x18001be42  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18001be49  jmp     short loc_18001BEB4
0x18001be4b  lea     rcx, [rsp+38h+arg_0]
0x18001be50  mov     [rsp+38h+arg_0], 0
0x18001be59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001be5e  xor     edx, edx; pUnkOuter
0x18001be60  lea     rax, [rsp+38h+arg_0]
0x18001be65  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001be6c  mov     [rsp+38h+ppv], rax; ppv
0x18001be71  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18001be78  lea     r8d, [rdx+1]; dwClsContext
0x18001be7c  call    cs:__imp_CoCreateInstance
0x18001be82  mov     ebx, eax
0x18001be84  test    eax, eax
0x18001be86  js      short loc_18001BEAA
0x18001be88  mov     rcx, [rsp+38h+arg_0]
0x18001be8d  xor     eax, eax
0x18001be8f  lock cmpxchg cs:qword_1800669C8, rcx
0x18001be98  jnz     short loc_18001BEA3
0x18001be9a  mov     [rsp+38h+arg_0], 0
0x18001bea3  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18001beaa  lea     rcx, [rsp+38h+arg_0]
0x18001beaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001beb4  mov     eax, ebx
0x18001beb6  add     rsp, 30h
0x18001beba  pop     rbx
0x18001bebb  retn
```
