# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x1800383a4`
- end: `0x180038434`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039c18`

## callees

- `0x18001055c`
- `0x1800383a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800383f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800383f4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  if ( qword_180081C18 )
  {
    v1 = 0;
    _InterlockedIncrement(&Windows::Internal::Details::_git);
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    v1 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v1 >= 0 )
    {
      if ( !_InterlockedCompareExchange64(&qword_180081C18, (signed __int64)ppv, 0) )
        ppv = 0;
      _InterlockedIncrement(&Windows::Internal::Details::_git);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800383a4  mov     [rsp+arg_0], rcx
0x1800383a9  push    rbx
0x1800383aa  sub     rsp, 30h
0x1800383ae  cmp     cs:qword_180081C18, 0
0x1800383b6  jz      short loc_1800383C3
0x1800383b8  xor     ebx, ebx
0x1800383ba  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x1800383c1  jmp     short loc_18003842C
0x1800383c3  lea     rcx, [rsp+38h+arg_0]
0x1800383c8  mov     [rsp+38h+arg_0], 0
0x1800383d1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800383d6  xor     edx, edx; pUnkOuter
0x1800383d8  lea     rax, [rsp+38h+arg_0]
0x1800383dd  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800383e4  mov     [rsp+38h+ppv], rax; ppv
0x1800383e9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800383f0  lea     r8d, [rdx+1]; dwClsContext
0x1800383f4  call    cs:__imp_CoCreateInstance
0x1800383fa  mov     ebx, eax
0x1800383fc  test    eax, eax
0x1800383fe  js      short loc_180038422
0x180038400  mov     rcx, [rsp+38h+arg_0]
0x180038405  xor     eax, eax
0x180038407  lock cmpxchg cs:qword_180081C18, rcx
0x180038410  jnz     short loc_18003841B
0x180038412  mov     [rsp+38h+arg_0], 0
0x18003841b  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A; Windows::Internal::Details::Git Windows::Internal::Details::_git
0x180038422  lea     rcx, [rsp+38h+arg_0]
0x180038427  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003842c  mov     eax, ebx
0x18003842e  add     rsp, 30h
0x180038432  pop     rbx
0x180038433  retn
```
