# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180011c0c`
- end: `0x180011c9c`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010838`
- `0x180015900`
- `0x18002a244`

## callees

- `0x180008128`
- `0x180011c0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011c5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011c5c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_18007E0F0 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_18007E0F0, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180011c0c  mov     [rsp+arg_0], rcx
0x180011c11  push    rbx
0x180011c12  sub     rsp, 30h
0x180011c16  cmp     cs:qword_18007E0F0, 0
0x180011c1e  jz      short loc_180011C2B
0x180011c20  xor     ebx, ebx
0x180011c22  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180011c29  jmp     short loc_180011C94
0x180011c2b  lea     rcx, [rsp+38h+arg_0]
0x180011c30  mov     [rsp+38h+arg_0], 0
0x180011c39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011c3e  xor     edx, edx; pUnkOuter
0x180011c40  lea     rax, [rsp+38h+arg_0]
0x180011c45  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011c4c  mov     [rsp+38h+ppv], rax; ppv
0x180011c51  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011c58  lea     r8d, [rdx+1]; dwClsContext
0x180011c5c  call    cs:__imp_CoCreateInstance
0x180011c62  mov     ebx, eax
0x180011c64  test    eax, eax
0x180011c66  js      short loc_180011C8A
0x180011c68  mov     rcx, [rsp+38h+arg_0]
0x180011c6d  xor     eax, eax
0x180011c6f  lock cmpxchg cs:qword_18007E0F0, rcx
0x180011c78  jnz     short loc_180011C83
0x180011c7a  mov     [rsp+38h+arg_0], 0
0x180011c83  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180011c8a  lea     rcx, [rsp+38h+arg_0]
0x180011c8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011c94  mov     eax, ebx
0x180011c96  add     rsp, 30h
0x180011c9a  pop     rbx
0x180011c9b  retn
```
