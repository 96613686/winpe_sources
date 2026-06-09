# Common::StateSeparation::GetIsStateSeparationEnabled(bool *)

- ea: `0x18002b6d0`
- end: `0x18002b7a8`
- name: `?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b7b0`
- `0x18002bca4`

## callees

- `0x1800043b4`
- `0x18002b474`
- `0x18002b4ac`
- `0x18002b4cc`
- `0x18002b6d0`
- `0x18002bfb0`
- `0x18002bfe0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b746`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b746`

## string_xrefs

- `0x18002b739`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetIsStateSeparationEnabled(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  __int64 (*RtlIsStateSeparationEnabled)(void); // rax
  char v5; // al
  char v6; // al
  char v8; // [rsp+38h] [rbp+10h] BYREF

  wil::RtlAcquireSRWLockShared(&v8, &qword_18004C108);
  if ( byte_18004C110 )
  {
    *a1 = byte_18004C100;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
    wil::RtlAcquireSRWLockExclusive(&v8, &qword_18004C108);
    if ( byte_18004C110 )
    {
      *a1 = byte_18004C100;
    }
    else
    {
      Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v3 = Library;
      if ( Library && (RtlIsStateSeparationEnabled = GetProcAddress_0(Library, "RtlIsStateSeparationEnabled")) != 0 )
      {
        v5 = RtlIsStateSeparationEnabled();
        byte_18004C110 = 1;
        v6 = v5 != 0;
        byte_18004C100 = v6;
      }
      else
      {
        v6 = byte_18004C100;
      }
      *a1 = v6;
      Common::AutoHandleCloseModule<HINSTANCE__ *>(v3);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b6d0  mov     [rsp+arg_0], rbx
0x18002b6d5  push    rdi
0x18002b6d6  sub     rsp, 20h
0x18002b6da  mov     rdi, rcx
0x18002b6dd  lea     rdx, qword_18004C108
0x18002b6e4  lea     rcx, [rsp+28h+arg_8]
0x18002b6e9  call    ?RtlAcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002b6ee  cmp     cs:byte_18004C110, 0
0x18002b6f5  lea     rcx, [rsp+28h+arg_8]
0x18002b6fa  jz      short loc_18002B70E
0x18002b6fc  mov     al, cs:byte_18004C100
0x18002b702  mov     [rdi], al
0x18002b704  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b709  jmp     loc_18002B79B
0x18002b70e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b713  lea     rdx, qword_18004C108
0x18002b71a  lea     rcx, [rsp+28h+arg_8]
0x18002b71f  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18002b724  cmp     cs:byte_18004C110, 0
0x18002b72b  jz      short loc_18002B737
0x18002b72d  mov     al, cs:byte_18004C100
0x18002b733  mov     [rdi], al
0x18002b735  jmp     short loc_18002B791
0x18002b737  xor     edx, edx; hFile
0x18002b739  lea     rcx, ModuleName; "ntdll.dll"
0x18002b740  mov     r8d, 800h; dwFlags
0x18002b746  call    cs:__imp_LoadLibraryExW
0x18002b74c  mov     rbx, rax
0x18002b74f  test    rax, rax
0x18002b752  jz      short loc_18002B781
0x18002b754  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18002b75b  mov     rcx, rax; hModule
0x18002b75e  call    GetProcAddress_0
0x18002b763  test    rax, rax
0x18002b766  jz      short loc_18002B781
0x18002b768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b76d  test    al, al
0x18002b76f  mov     cs:byte_18004C110, 1
0x18002b776  setnz   al
0x18002b779  mov     cs:byte_18004C100, al
0x18002b77f  jmp     short loc_18002B787
0x18002b781  mov     al, cs:byte_18004C100
0x18002b787  mov     rcx, rbx
0x18002b78a  mov     [rdi], al
0x18002b78c  call    ??$AutoHandleCloseModule@PEAUHINSTANCE__@@@Common@@YAXPEAUHINSTANCE__@@@Z; Common::AutoHandleCloseModule<HINSTANCE__ *>(HINSTANCE__ *)
0x18002b791  lea     rcx, [rsp+28h+arg_8]
0x18002b796  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b79b  mov     rbx, [rsp+28h+arg_0]
0x18002b7a0  xor     eax, eax
0x18002b7a2  add     rsp, 20h
0x18002b7a6  pop     rdi
0x18002b7a7  retn
```
