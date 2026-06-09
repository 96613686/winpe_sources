# Windows::Internal::Details::Git::Acquire(void)

- ea: `0x180015de4`
- end: `0x180015e89`
- name: `?Acquire@Git@Details@Internal@Windows@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(Windows::Internal::Details::Git *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015d40`
- `0x18002a7b0`

## callees

- `0x180003820`
- `0x180015de4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015e34`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015e34`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Details::Git::Acquire(Windows::Internal::Details::Git *this)
{
  HRESULT Instance; // ebx
  IGlobalInterfaceTable *ptr; // rcx
  Microsoft::WRL::ComPtr<IGlobalInterfaceTable> spGit; // [rsp+40h] [rbp+8h] BYREF

  spGit.ptr_ = (IGlobalInterfaceTable *)this;
  if ( Windows::Internal::Details::_git._spGit.ptr_ )
  {
    Instance = 0;
    _InterlockedIncrement((volatile signed __int32 *)&Windows::Internal::Details::_git);
  }
  else
  {
    spGit.ptr_ = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spGit);
    Instance = CoCreateInstance(
                 &CLSID_StdGlobalInterfaceTable,
                 0,
                 1u,
                 &GUID_00000146_0000_0000_c000_000000000046,
                 (LPVOID *)&spGit.ptr_);
    if ( Instance >= 0 )
    {
      if ( !_InterlockedCompareExchange64(
              (volatile signed __int64 *)&Windows::Internal::Details::_git._spGit.ptr_,
              (signed __int64)spGit.ptr_,
              0) )
        spGit.ptr_ = 0;
      _InterlockedIncrement((volatile signed __int32 *)&Windows::Internal::Details::_git);
    }
    ptr = spGit.ptr_;
    if ( spGit.ptr_ )
    {
      spGit.ptr_ = 0;
      ptr->Release(ptr);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180015de4  mov     [rsp+spGit.ptr_], rcx
0x180015de9  push    rbx
0x180015dea  sub     rsp, 30h
0x180015dee  cmp     cs:?_git@Details@Internal@Windows@@3VGit@123@A._spGit.ptr_, 0; Windows::Internal::Details::Git Windows::Internal::Details::_git ...
0x180015df6  jz      short loc_180015E03
0x180015df8  xor     ebx, ebx
0x180015dfa  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A._cAcquired; Windows::Internal::Details::Git Windows::Internal::Details::_git ...
0x180015e01  jmp     short loc_180015E81
0x180015e03  lea     rcx, [rsp+38h+spGit]; this
0x180015e08  mov     [rsp+38h+spGit.ptr_], 0
0x180015e11  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180015e16  xor     edx, edx; pUnkOuter
0x180015e18  lea     rax, [rsp+38h+spGit]
0x180015e1d  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180015e24  mov     [rsp+38h+ppv], rax; ppv
0x180015e29  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180015e30  lea     r8d, [rdx+1]; dwClsContext
0x180015e34  call    cs:__imp_CoCreateInstance
0x180015e3a  mov     ebx, eax
0x180015e3c  test    eax, eax
0x180015e3e  js      short loc_180015E62
0x180015e40  mov     rcx, [rsp+38h+spGit.ptr_]
0x180015e45  xor     eax, eax
0x180015e47  lock cmpxchg cs:?_git@Details@Internal@Windows@@3VGit@123@A._spGit.ptr_, rcx; Windows::Internal::Details::Git Windows::Internal::Details::_git ...
0x180015e50  jnz     short loc_180015E5B
0x180015e52  mov     [rsp+38h+spGit.ptr_], 0
0x180015e5b  lock inc cs:?_git@Details@Internal@Windows@@3VGit@123@A._cAcquired; Windows::Internal::Details::Git Windows::Internal::Details::_git ...
0x180015e62  mov     rcx, [rsp+38h+spGit.ptr_]
0x180015e67  test    rcx, rcx
0x180015e6a  jz      short loc_180015E81
0x180015e6c  mov     [rsp+38h+spGit.ptr_], 0
0x180015e75  mov     rax, [rcx]
0x180015e78  mov     rax, [rax+10h]
0x180015e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e81  mov     eax, ebx
0x180015e83  add     rsp, 30h
0x180015e87  pop     rbx
0x180015e88  retn
```
