# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x180034b00`
- end: `0x180034bd6`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `214`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017394`

## callees

- `0x180004167`
- `0x180004197`
- `0x180034aa4`
- `0x180034ac4`
- `0x180034b00`
- `0x180034c00`
- `0x180034c34`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034b69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034b69`

## string_xrefs

- `0x180034b62`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::StateSeparation::GetIsStateSeparationEnabled(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  unsigned __int8 (*ProcAddress)(void); // rax
  char v5; // al
  char v7; // [rsp+38h] [rbp+10h] BYREF
  HMODULE v8; // [rsp+40h] [rbp+18h]

  wil::RtlAcquireSRWLockShared(&v7);
  if ( byte_180083D11 )
  {
    *a1 = byte_180083D10;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
    wil::RtlAcquireSRWLockExclusive(&v7);
    if ( byte_180083D11 )
    {
      *a1 = byte_180083D10;
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v3 = Library;
      v8 = Library;
      if ( Library
        && (ProcAddress = (unsigned __int8 (*)(void))WINRT_IMPL_GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0 )
      {
        v5 = ProcAddress() != 0;
        byte_180083D10 = v5;
        byte_180083D11 = 1;
      }
      else
      {
        v5 = byte_180083D10;
      }
      *a1 = v5;
      if ( v3 )
        WINRT_IMPL_FreeLibrary(v3);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180034b00  mov     [rsp+arg_0], rbx
0x180034b05  push    rdi
0x180034b06  sub     rsp, 20h
0x180034b0a  mov     rdi, rcx
0x180034b0d  lea     rcx, [rsp+28h+arg_8]
0x180034b12  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x180034b17  lea     rcx, [rsp+28h+arg_8]
0x180034b1c  cmp     cs:byte_180083D11, 0
0x180034b23  jz      short loc_180034B37
0x180034b25  mov     al, cs:byte_180083D10
0x180034b2b  mov     [rdi], al
0x180034b2d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180034b32  jmp     loc_180034BC9
0x180034b37  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180034b3c  lea     rcx, [rsp+28h+arg_8]
0x180034b41  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180034b46  nop
0x180034b47  cmp     cs:byte_180083D11, 0
0x180034b4e  jz      short loc_180034B5A
0x180034b50  mov     al, cs:byte_180083D10
0x180034b56  mov     [rdi], al
0x180034b58  jmp     short loc_180034BBF
0x180034b5a  xor     edx, edx; hFile
0x180034b5c  mov     r8d, 800h; dwFlags
0x180034b62  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180034b69  call    cs:__imp_LoadLibraryExW
0x180034b6f  mov     rbx, rax
0x180034b72  mov     [rsp+28h+arg_10], rax
0x180034b77  test    rax, rax
0x180034b7a  jz      short loc_180034BA9
0x180034b7c  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x180034b83  mov     rcx, rax; hModule
0x180034b86  call    WINRT_IMPL_GetProcAddress
0x180034b8b  test    rax, rax
0x180034b8e  jz      short loc_180034BA9
0x180034b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b95  test    al, al
0x180034b97  setnz   al
0x180034b9a  mov     cs:byte_180083D10, al
0x180034ba0  mov     cs:byte_180083D11, 1
0x180034ba7  jmp     short loc_180034BAF
0x180034ba9  mov     al, cs:byte_180083D10
0x180034baf  mov     [rdi], al
0x180034bb1  test    rbx, rbx
0x180034bb4  jz      short loc_180034BBF
0x180034bb6  mov     rcx, rbx; hLibModule
0x180034bb9  call    WINRT_IMPL_FreeLibrary
0x180034bbe  nop
0x180034bbf  lea     rcx, [rsp+28h+arg_8]
0x180034bc4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180034bc9  xor     eax, eax
0x180034bcb  mov     rbx, [rsp+28h+arg_0]
0x180034bd0  add     rsp, 20h
0x180034bd4  pop     rdi
0x180034bd5  retn
```
