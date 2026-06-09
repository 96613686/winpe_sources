# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::BlockAutomaticRebootAsync$_ResumeCoro$1

- ea: `0x180020230`
- end: `0x180020444`
- name: `winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::BlockAutomaticRebootAsync$_ResumeCoro$1`
- size: `532`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800204c8`

## callees

- `0x1800032b0`
- `0x1800039d8`
- `0x180008a80`
- `0x180008adc`
- `0x180008cec`
- `0x180008e28`
- `0x1800191a8`
- `0x18001f214`
- `0x18001f318`
- `0x18001f578`
- `0x18001f6a8`
- `0x180020230`
- `0x180021f44`
- `0x180022cd0`
- `0x1800233a4`
- `0x180024aa0`
- `0x1800257c8`
- `0x180025a40`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002030f`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180020381`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18002030f`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180020381`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::BlockAutomaticRebootAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // rsi
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v3; // r14
  const struct winrt::impl::slim_source_location *v4; // rax
  const WCHAR *v5; // rax
  unsigned int KeyW; // eax
  unsigned int v7; // r8d
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  HKEY v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // [rsp+20h] [rbp-B8h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v18[112]; // [rsp+68h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  LOWORD(v16) = *(_WORD *)(a1 + 8);
  switch ( (__int16)v16 )
  {
    case -1:
    case 1:
    case 3:
      goto LABEL_14;
    case 2:
      v3 = *(winrt::Windows::System::Update::factory_implementation::SystemUpdateManager **)(a1 + 136);
      if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(v3) )
      {
        winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported((winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject);
        throw (winrt::Windows::System::Update::factory_implementation::hresult_not_supported *)pExceptionObject;
      }
      if ( !winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(v3) )
      {
        v4 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 16);
        winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v18, v4);
        throw (winrt::hresult_access_denied *)v18;
      }
      *(_QWORD *)(a1 + 40) = 0;
      v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AD0);
      KeyW = RegCreateKeyW(HKEY_LOCAL_MACHINE, v5, (PHKEY)(a1 + 40));
      if ( KeyW )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x22B, v7, (const char *)KeyW, v16);
      v8 = *(_QWORD *)(a1 + 144);
      if ( v8 )
        v9 = *(const unsigned __int16 **)(v8 + 16);
      else
        v9 = &qword_180034A88;
      v10 = std::wstring::wstring(a1 + 48, v9);
      winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageLockName(v11, a1 + 80, v10);
      *(_QWORD *)(a1 + 112) = 0;
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 80);
      v14 = RegCreateKeyW(v13, v12, (PHKEY)(a1 + 112));
      if ( v14 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x22F, v15, (const char *)v14, v16);
      winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(retaddr, 1);
      *(_BYTE *)(a1 - 8) = 1;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 112);
      std::wstring::_Tidy_deallocate(a1 + 80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 40);
      *(_QWORD *)(a1 + 120) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_14:
        winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>(a1 - 112);
        winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 144);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112));
      }
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180020230  mov     rax, rsp
0x180020233  mov     [rax+8], rcx
0x180020237  push    rbx
0x180020238  push    rsi
0x180020239  push    rdi
0x18002023a  push    r12
0x18002023c  push    r14
0x18002023e  push    r15
0x180020240  sub     rsp, 0A8h
0x180020247  mov     rbx, rcx
0x18002024a  mov     [rsp+0D8h+var_B0], rcx
0x18002024f  lea     rsi, [rbx+8]
0x180020253  mov     [rsp+0D8h+var_A8], rsi
0x180020258  movzx   eax, word ptr [rsi]
0x18002025b  mov     word ptr [rsp+0D8h+var_B8], ax; unsigned int
0x180020260  inc     ax; switch 5 cases
0x180020263  cmp     ax, 4
0x180020267  ja      def_180020282; jumptable 0000000180020282 default case, case 0
0x18002026d  movsx   rax, ax
0x180020271  lea     rdx, __ImageBase
0x180020278  mov     ecx, ds:(jpt_180020282 - 180000000h)[rdx+rax*4]
0x18002027f  add     rcx, rdx
0x180020282  jmp     rcx; switch jump
0x180020284  xor     edi, edi; jumptable 0000000180020282 case 3
0x180020286  jmp     loc_1800203F1
0x18002028b  mov     r14, [rsi+80h]; jumptable 0000000180020282 case 2
0x180020292  mov     rcx, r14; this
0x180020295  call    ?IsIotCoreEdition@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(void)
0x18002029a  xor     edi, edi
0x18002029c  test    al, al
0x18002029e  jnz     short loc_1800202BB
0x1800202a0  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x1800202a5  call    ??0hresult_not_supported@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported(void)
0x1800202aa  lea     rdx, _TI2?AUhresult_not_supported@factory_implementation@Update@System@Windows@winrt@@; pThrowInfo
0x1800202b1  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800202b6  call    _CxxThrowException_0
0x1800202bb  mov     rcx, r14; this
0x1800202be  call    ?HasSystemManagementCapability@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(void)
0x1800202c3  test    al, al
0x1800202c5  jnz     short loc_1800202EF
0x1800202c7  lea     rcx, [rbx+10h]
0x1800202cb  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800202d0  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800202d3  lea     rcx, [rsp+0D8h+var_70]; this
0x1800202d8  call    ??0hresult_access_denied@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::impl::slim_source_location const &)
0x1800202dd  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x1800202e4  lea     rcx, [rsp+0D8h+var_70]; pExceptionObject
0x1800202e9  call    _CxxThrowException_0
0x1800202ef  lea     r15, [rbx+28h]
0x1800202f3  mov     [r15], rdi
0x1800202f6  lea     rcx, qword_180042AD0
0x1800202fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020302  mov     rdx, rax; lpSubKey
0x180020305  mov     r8, r15; phkResult
0x180020308  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002030f  call    cs:__imp_RegCreateKeyW
0x180020315  mov     rcx, [rsp+0D8h]; this
0x18002031d  test    eax, eax
0x18002031f  jz      short loc_18002032E
0x180020321  mov     r9d, eax; char *
0x180020324  mov     edx, 22Bh; void *
0x180020329  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002032e  lea     rcx, [rbx+30h]
0x180020332  mov     rax, [rbx+90h]
0x180020339  test    rax, rax
0x18002033c  jz      short loc_180020344
0x18002033e  mov     rdx, [rax+10h]
0x180020342  jmp     short loc_18002034B
0x180020344  lea     rdx, qword_180034A88
0x18002034b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020350  lea     r14, [rbx+50h]
0x180020354  mov     r8, rax
0x180020357  mov     rdx, r14
0x18002035a  call    ?GetPackageLockName@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V78@@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageLockName(std::wstring)
0x18002035f  nop
0x180020360  lea     r12, [rbx+70h]
0x180020364  mov     [r12], rdi
0x180020368  mov     r9, [r15]
0x18002036b  mov     [rsp+0D8h+var_98], r9
0x180020370  mov     rcx, r14
0x180020373  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180020378  mov     rdx, rax; lpSubKey
0x18002037b  mov     r8, r12; phkResult
0x18002037e  mov     rcx, r9; hKey
0x180020381  call    cs:__imp_RegCreateKeyW
0x180020387  mov     rcx, [rsp+0D8h]; this
0x18002038f  test    eax, eax
0x180020391  jz      short loc_1800203A0
0x180020393  mov     r9d, eax; char *
0x180020396  mov     edx, 22Fh; void *
0x18002039b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800203a0  mov     dl, 1; bool
0x1800203a2  call    ?SetUSORebootBlock@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(bool)
0x1800203a7  mov     byte ptr [rbx-8], 1
0x1800203ab  mov     rcx, r12
0x1800203ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800203b3  nop
0x1800203b4  mov     rcx, r14
0x1800203b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800203bc  nop
0x1800203bd  mov     rcx, r15
0x1800203c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800203c5  nop
0x1800203c6  jmp     short loc_1800203D4
0x1800203c8  xor     edi, edi
0x1800203ca  mov     rbx, [rsp+0D8h+var_B0]
0x1800203cf  mov     rsi, [rsp+0D8h+var_A8]
0x1800203d4  lea     rcx, [rbx+78h]
0x1800203d8  lea     rax, [rbx-70h]
0x1800203dc  mov     [rcx], rax
0x1800203df  xor     eax, eax
0x1800203e1  mov     [rsi], ax
0x1800203e4  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1800203e9  test    al, al
0x1800203eb  jz      short loc_1800203F1
0x1800203ed  jmp     short loc_18002041D
0x1800203ef  xor     edi, edi; jumptable 0000000180020282 cases -1,1
0x1800203f1  lea     rcx, [rbx-70h]
0x1800203f5  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>(void)
0x1800203fa  lea     rcx, [rbx+90h]
0x180020401  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180020406  cmp     [rbx+0Ah], di
0x18002040a  jz      short loc_18002041D
0x18002040c  mov     edx, 110h
0x180020411  lea     rcx, [rbx-70h]; Block
0x180020415  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002041a  jmp     short loc_18002041D
0x18002041c  int     3; Trap to Debugger
0x18002041d  add     rsp, 0A8h
0x180020424  pop     r15
0x180020426  pop     r14
0x180020428  pop     r12
0x18002042a  pop     rdi
0x18002042b  pop     rsi
0x18002042c  pop     rbx
0x18002042d  retn
```
