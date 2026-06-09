# winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UnblockAutomaticRebootAsync$_ResumeCoro$1

- ea: `0x180024f90`
- end: `0x180025224`
- name: `winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UnblockAutomaticRebootAsync$_ResumeCoro$1`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800252a8`

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
- `0x180021f44`
- `0x180022cd0`
- `0x1800233a4`
- `0x180024aa0`
- `0x180024eac`
- `0x180024f90`
- `0x1800257c8`
- `0x180025a40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180025142`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180025142`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002507e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18002507e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800250e5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800250e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::UnblockAutomaticRebootAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // rsi
  winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *v3; // r14
  const struct winrt::impl::slim_source_location *v4; // rax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  HKEY v13; // r8
  unsigned int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  unsigned int InfoKeyW; // eax
  unsigned int v18; // r8d
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-F8h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-F8h]
  _BYTE pExceptionObject[24]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v22[104]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_19;
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
        winrt::hresult_access_denied::hresult_access_denied((winrt::hresult_access_denied *)v22, v4);
        throw (winrt::hresult_access_denied *)v22;
      }
      *(_QWORD *)(a1 + 40) = 0;
      v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180042AD0);
      v6 = RegOpenKeyW(HKEY_LOCAL_MACHINE, v5, (PHKEY)(a1 + 40));
      if ( v6 )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x247, v7, (const char *)v6, lpcSubKeys);
      v8 = *(_QWORD *)(a1 + 144);
      if ( v8 )
        v9 = *(const unsigned __int16 **)(v8 + 16);
      else
        v9 = &qword_180034A88;
      v10 = std::wstring::wstring(a1 + 48, v9);
      winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageLockName(v11, a1 + 80, v10);
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 80);
      v14 = RegDeleteKeyW(v13, v12);
      if ( (v14 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32(retaddr, v15, v16, (const char *)v14, lpcSubKeys);
      *(_DWORD *)(a1 + 112) = 0;
      InfoKeyW = RegQueryInfoKeyW(*(HKEY *)(a1 + 40), 0, 0, 0, (LPDWORD)(a1 + 112), 0, 0, 0, 0, 0, 0, 0);
      if ( InfoKeyW )
        wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x253, v18, (const char *)InfoKeyW, lpcSubKeysa);
      if ( *(_DWORD *)(a1 + 112) )
      {
        *(_BYTE *)(a1 - 8) = 0;
      }
      else
      {
        winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(retaddr, 0);
        *(_BYTE *)(a1 - 8) = 1;
      }
      std::wstring::_Tidy_deallocate(a1 + 80);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(a1 + 40);
      *(_QWORD *)(a1 + 120) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_19:
        winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>((_QWORD *)(a1 - 112));
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
0x180024f90  mov     rax, rsp
0x180024f93  mov     [rax+8], rcx
0x180024f97  push    rbx
0x180024f98  push    rsi
0x180024f99  push    rdi
0x180024f9a  push    r12
0x180024f9c  push    r14
0x180024f9e  push    r15
0x180024fa0  sub     rsp, 0E8h
0x180024fa7  mov     rdi, rcx
0x180024faa  mov     [rsp+118h+var_B0], rcx
0x180024faf  lea     rsi, [rdi+8]
0x180024fb3  mov     [rsp+118h+var_98], rsi
0x180024fbb  movzx   eax, word ptr [rsi]
0x180024fbe  mov     [rsp+118h+var_B8], ax
0x180024fc3  inc     ax; switch 5 cases
0x180024fc6  cmp     ax, 4
0x180024fca  ja      def_180024FE5; jumptable 0000000180024FE5 default case, case 0
0x180024fd0  movsx   rax, ax
0x180024fd4  lea     rdx, __ImageBase
0x180024fdb  mov     ecx, ds:(jpt_180024FE5 - 180000000h)[rdx+rax*4]
0x180024fe2  add     rcx, rdx
0x180024fe5  jmp     rcx; switch jump
0x180024fe7  xor     ebx, ebx; jumptable 0000000180024FE5 case 3
0x180024fe9  jmp     loc_1800251CF
0x180024fee  mov     r14, [rsi+80h]; jumptable 0000000180024FE5 case 2
0x180024ff5  mov     rcx, r14; this
0x180024ff8  call    ?IsIotCoreEdition@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::IsIotCoreEdition(void)
0x180024ffd  xor     ebx, ebx
0x180024fff  test    al, al
0x180025001  jnz     short loc_180025024
0x180025003  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18002500b  call    ??0hresult_not_supported@factory_implementation@Update@System@Windows@winrt@@QEAA@XZ; winrt::Windows::System::Update::factory_implementation::hresult_not_supported::hresult_not_supported(void)
0x180025010  lea     rdx, _TI2?AUhresult_not_supported@factory_implementation@Update@System@Windows@winrt@@; pThrowInfo
0x180025017  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18002501f  call    _CxxThrowException_0
0x180025024  mov     rcx, r14; this
0x180025027  call    ?HasSystemManagementCapability@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA_NXZ; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::HasSystemManagementCapability(void)
0x18002502c  test    al, al
0x18002502e  jnz     short loc_18002505E
0x180025030  lea     rcx, [rdi+10h]
0x180025034  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180025039  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002503c  lea     rcx, [rsp+118h+var_68]; this
0x180025044  call    ??0hresult_access_denied@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::impl::slim_source_location const &)
0x180025049  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180025050  lea     rcx, [rsp+118h+var_68]; pExceptionObject
0x180025058  call    _CxxThrowException_0
0x18002505e  lea     r15, [rdi+28h]
0x180025062  mov     [r15], rbx
0x180025065  lea     rcx, qword_180042AD0
0x18002506c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180025071  mov     rdx, rax; lpSubKey
0x180025074  mov     r8, r15; phkResult
0x180025077  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002507e  call    cs:__imp_RegOpenKeyW
0x180025084  mov     rcx, [rsp+118h]; this
0x18002508c  test    eax, eax
0x18002508e  jz      short loc_18002509D
0x180025090  mov     r9d, eax; char *
0x180025093  mov     edx, 247h; void *
0x180025098  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002509d  lea     rcx, [rdi+30h]
0x1800250a1  mov     rax, [rdi+90h]
0x1800250a8  test    rax, rax
0x1800250ab  jz      short loc_1800250B3
0x1800250ad  mov     rdx, [rax+10h]
0x1800250b1  jmp     short loc_1800250BA
0x1800250b3  lea     rdx, qword_180034A88
0x1800250ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800250bf  lea     r14, [rdi+50h]
0x1800250c3  mov     r8, rax
0x1800250c6  mov     rdx, r14
0x1800250c9  call    ?GetPackageLockName@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V78@@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::GetPackageLockName(std::wstring)
0x1800250ce  nop
0x1800250cf  mov     r8, [r15]
0x1800250d2  mov     [rsp+118h+var_A0], r8
0x1800250d7  mov     rcx, r14
0x1800250da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800250df  mov     rdx, rax; lpSubKey
0x1800250e2  mov     rcx, r8; hKey
0x1800250e5  call    cs:__imp_RegDeleteKeyW
0x1800250eb  test    eax, 0FFFFFFFDh
0x1800250f0  jz      short loc_180025102
0x1800250f2  mov     rcx, [rsp+118h]; this
0x1800250fa  mov     r9d, eax; char *
0x1800250fd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180025102  lea     r12, [rdi+70h]
0x180025106  mov     [r12], ebx
0x18002510a  mov     rcx, [r15]; hKey
0x18002510d  mov     [rsp+118h+var_A0], rcx
0x180025112  mov     [rsp+118h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180025117  mov     [rsp+118h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18002511c  mov     [rsp+118h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180025121  mov     [rsp+118h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180025126  mov     [rsp+118h+lpcValues], rbx; lpcValues
0x18002512b  mov     [rsp+118h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180025130  mov     [rsp+118h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180025135  mov     [rsp+118h+lpcSubKeys], r12; unsigned int
0x18002513a  xor     r9d, r9d; lpReserved
0x18002513d  xor     r8d, r8d; lpcchClass
0x180025140  xor     edx, edx; lpClass
0x180025142  call    cs:__imp_RegQueryInfoKeyW
0x180025148  mov     rcx, [rsp+118h]; this
0x180025150  test    eax, eax
0x180025152  jz      short loc_180025161
0x180025154  mov     r9d, eax; char *
0x180025157  mov     edx, 253h; void *
0x18002515c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180025161  mov     eax, [r12]
0x180025165  mov     [rsp+118h+var_A8], eax
0x180025169  test    eax, eax
0x18002516b  jnz     short loc_18002518C
0x18002516d  xor     edx, edx; bool
0x18002516f  call    ?SetUSORebootBlock@SystemUpdateManager@factory_implementation@Update@System@Windows@winrt@@AEAAX_N@Z; winrt::Windows::System::Update::factory_implementation::SystemUpdateManager::SetUSORebootBlock(bool)
0x180025174  mov     byte ptr [rdi-8], 1
0x180025178  mov     rcx, r14
0x18002517b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025180  nop
0x180025181  mov     rcx, r15
0x180025184  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180025189  nop
0x18002518a  jmp     short loc_1800251B2
0x18002518c  mov     [rdi-8], bl
0x18002518f  mov     rcx, r14
0x180025192  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180025197  nop
0x180025198  mov     rcx, r15
0x18002519b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800251a0  nop
0x1800251a1  jmp     short loc_1800251B2
0x1800251a3  xor     ebx, ebx
0x1800251a5  mov     rsi, [rsp+118h+var_98]
0x1800251ad  mov     rdi, [rsp+118h+var_B0]
0x1800251b2  lea     rcx, [rdi+78h]
0x1800251b6  lea     rax, [rdi-70h]
0x1800251ba  mov     [rcx], rax
0x1800251bd  xor     eax, eax
0x1800251bf  mov     [rsi], ax
0x1800251c2  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x1800251c7  test    al, al
0x1800251c9  jz      short loc_1800251CF
0x1800251cb  jmp     short loc_1800251FB
0x1800251cd  xor     ebx, ebx; jumptable 0000000180024FE5 cases -1,1
0x1800251cf  lea     rcx, [rdi-70h]
0x1800251d3  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@PEAUSystemUpdateManager@factory_implementation@Update@System@34@Uhstring@4@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::System::Update::factory_implementation::SystemUpdateManager *,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>(void)
0x1800251d8  lea     rcx, [rdi+90h]
0x1800251df  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800251e4  cmp     [rdi+0Ah], bx
0x1800251e8  jz      short loc_1800251FB
0x1800251ea  mov     edx, 110h
0x1800251ef  lea     rcx, [rdi-70h]; Block
0x1800251f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800251f8  jmp     short loc_1800251FB
0x1800251fa  int     3; Trap to Debugger
0x1800251fb  add     rsp, 0E8h
0x180025202  pop     r15
0x180025204  pop     r14
0x180025206  pop     r12
0x180025208  pop     rdi
0x180025209  pop     rsi
0x18002520a  pop     rbx
0x18002520b  retn
```
