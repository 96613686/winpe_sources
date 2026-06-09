# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180032a9c`
- end: `0x180032b2c`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b090`
- `0x18000c340`
- `0x18000d2f0`
- `0x180031ec8`

## callees

- `0x1800019c0`
- `0x180032a9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032aec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032aec`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_180072C08 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppv);
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_180072C08, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180032a9c  mov     [rsp+arg_0], rcx
0x180032aa1  push    rbx
0x180032aa2  sub     rsp, 30h
0x180032aa6  cmp     cs:qword_180072C08, 0
0x180032aae  jz      short loc_180032ABB
0x180032ab0  xor     ebx, ebx
0x180032ab2  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180032ab9  jmp     short loc_180032B24
0x180032abb  lea     rcx, [rsp+38h+arg_0]
0x180032ac0  mov     [rsp+38h+arg_0], 0
0x180032ac9  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180032ace  xor     edx, edx; pUnkOuter
0x180032ad0  lea     rax, [rsp+38h+arg_0]
0x180032ad5  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180032adc  mov     [rsp+38h+ppv], rax; ppv
0x180032ae1  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180032ae8  lea     r8d, [rdx+1]; dwClsContext
0x180032aec  call    cs:__imp_CoCreateInstance
0x180032af2  mov     ebx, eax
0x180032af4  test    eax, eax
0x180032af6  js      short loc_180032B1A
0x180032af8  mov     rcx, [rsp+38h+arg_0]
0x180032afd  xor     eax, eax
0x180032aff  lock cmpxchg cs:qword_180072C08, rcx
0x180032b08  jnz     short loc_180032B13
0x180032b0a  mov     [rsp+38h+arg_0], 0
0x180032b13  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180032b1a  lea     rcx, [rsp+38h+arg_0]
0x180032b1f  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180032b24  mov     eax, ebx
0x180032b26  add     rsp, 30h
0x180032b2a  pop     rbx
0x180032b2b  retn
```
