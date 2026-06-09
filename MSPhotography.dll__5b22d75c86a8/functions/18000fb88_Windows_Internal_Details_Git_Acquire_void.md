# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x18000fb88`
- end: `0x18000fc18`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e14c`

## callees

- `0x180005660`
- `0x18000fb88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbd8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fbd8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_180160A38 )
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
      if ( !_InterlockedCompareExchange64(&qword_180160A38, (signed __int64)ppv, 0) )
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
0x18000fb88  mov     [rsp+arg_0], rcx
0x18000fb8d  push    rbx
0x18000fb8e  sub     rsp, 30h
0x18000fb92  cmp     cs:qword_180160A38, 0
0x18000fb9a  jz      short loc_18000FBA7
0x18000fb9c  xor     ebx, ebx
0x18000fb9e  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18000fba5  jmp     short loc_18000FC10
0x18000fba7  lea     rcx, [rsp+38h+arg_0]
0x18000fbac  mov     [rsp+38h+arg_0], 0
0x18000fbb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fbba  xor     edx, edx; pUnkOuter
0x18000fbbc  lea     rax, [rsp+38h+arg_0]
0x18000fbc1  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000fbc8  mov     [rsp+38h+ppv], rax; ppv
0x18000fbcd  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000fbd4  lea     r8d, [rdx+1]; dwClsContext
0x18000fbd8  call    cs:__imp_CoCreateInstance
0x18000fbde  mov     ebx, eax
0x18000fbe0  test    eax, eax
0x18000fbe2  js      short loc_18000FC06
0x18000fbe4  mov     rcx, [rsp+38h+arg_0]
0x18000fbe9  xor     eax, eax
0x18000fbeb  lock cmpxchg cs:qword_180160A38, rcx
0x18000fbf4  jnz     short loc_18000FBFF
0x18000fbf6  mov     [rsp+38h+arg_0], 0
0x18000fbff  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x18000fc06  lea     rcx, [rsp+38h+arg_0]
0x18000fc0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fc10  mov     eax, ebx
0x18000fc12  add     rsp, 30h
0x18000fc16  pop     rbx
0x18000fc17  retn
```
