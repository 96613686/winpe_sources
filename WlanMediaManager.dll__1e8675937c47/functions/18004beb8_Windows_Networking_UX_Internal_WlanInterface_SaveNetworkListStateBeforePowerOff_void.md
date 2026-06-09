# Windows::Networking::UX::Internal::WlanInterface::_SaveNetworkListStateBeforePowerOff(void)

- ea: `0x18004beb8`
- end: `0x18004c06a`
- name: `?_SaveNetworkListStateBeforePowerOff@WlanInterface@Internal@UX@Networking@Windows@@IEAAXXZ`
- size: `434`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800454f8`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x180011a20`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001c044`
- `0x180037770`
- `0x18004beb8`
- `0x18004ff08`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c03b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004c03b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c01c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bfab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004c01c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Networking::UX::Internal::WlanInterface::_SaveNetworkListStateBeforePowerOff(
        Windows::Networking::UX::Internal::WlanInterface *this)
{
  Windows::Networking::UX::Internal::WlanInterface *v1; // r13
  char *v2; // r15
  __int64 v3; // rcx
  char *v4; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int i; // esi
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, HSTRING *); // rbx
  unsigned int v14; // [rsp+20h] [rbp-98h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-94h]
  HSTRING string; // [rsp+28h] [rbp-90h] BYREF
  __int64 v17; // [rsp+30h] [rbp-88h] BYREF
  Windows::Networking::UX::Internal::WlanInterface *v18; // [rsp+38h] [rbp-80h]
  char *v19; // [rsp+40h] [rbp-78h]
  char *v20; // [rsp+48h] [rbp-70h]
  _BYTE v21[8]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-60h] BYREF

  v1 = this;
  v18 = this;
  wil::EnterCriticalSection(v21, (char *)this + 1304);
  v2 = (char *)v1 + 1344;
  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
    v3,
    *((_QWORD *)v1 + 168));
  **(_QWORD **)v2 = *(_QWORD *)v2;
  *(_QWORD *)(*(_QWORD *)v2 + 8LL) = *(_QWORD *)v2;
  *((_QWORD *)v1 + 169) = 0;
  v14 = 0;
  v4 = (char *)v1 + 1296;
  if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v1 + 162) + 56LL))(*((_QWORD *)v1 + 162), &v14) >= 0 )
  {
    v20 = (char *)v1 + 1296;
    v19 = (char *)v1 + 1344;
    for ( i = 0; ; ++i )
    {
      v15 = i;
      if ( i >= v14 )
        break;
      v17 = 0;
      v8 = *(_QWORD *)v4;
      v9 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v4 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v5, v6);
      if ( v9(v8, i, &v17) >= 0 )
      {
        string = 0;
        v12 = v17;
        v13 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        if ( v13(v12, &string) >= 0 )
        {
          WindowsGetStringRawBuffer(string, 0);
          try
          {
            std::wstring::wstring(v22);
            std::list<std::wstring>::push_back(v2, v22);
            std::wstring::_Tidy_deallocate(v22);
          }
          catch ( std::bad_alloc )
          {
            i = v15;
            v1 = v18;
            v2 = v19;
            v4 = v20;
          }
        }
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v10, v11);
    }
  }
  GetSystemTimeAsFileTime((LPFILETIME)v1 + 170);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v21);
}

```

## disassembly

```asm
0x18004beb8  push    rbx
0x18004beba  push    rsi
0x18004bebb  push    rdi
0x18004bebc  push    r12
0x18004bebe  push    r13
0x18004bec0  push    r15
0x18004bec2  sub     rsp, 88h
0x18004bec9  mov     rax, cs:__security_cookie
0x18004bed0  xor     rax, rsp
0x18004bed3  mov     [rsp+0B8h+var_40], rax
0x18004bed8  mov     r13, rcx
0x18004bedb  mov     [rsp+0B8h+var_80], rcx
0x18004bee0  lea     rdx, [rcx+518h]
0x18004bee7  lea     rcx, [rsp+0B8h+var_68]
0x18004beec  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004bef1  nop
0x18004bef2  lea     r15, [r13+540h]
0x18004bef9  mov     rdx, [r15]
0x18004befc  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18004bf01  mov     rax, [r15]
0x18004bf04  mov     [rax], rax
0x18004bf07  mov     rax, [r15]
0x18004bf0a  mov     [rax+8], rax
0x18004bf0e  mov     qword ptr [r15+8], 0
0x18004bf16  mov     [rsp+0B8h+var_98], 0
0x18004bf1e  lea     r12, [r13+510h]
0x18004bf25  mov     rcx, [r12]
0x18004bf29  mov     rax, [rcx]
0x18004bf2c  lea     rdx, [rsp+0B8h+var_98]
0x18004bf31  mov     rax, [rax+38h]
0x18004bf35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf3a  test    eax, eax
0x18004bf3c  js      loc_18004C034
0x18004bf42  mov     [rsp+0B8h+var_70], r12
0x18004bf47  mov     [rsp+0B8h+var_78], r15
0x18004bf4c  xor     esi, esi
0x18004bf4e  mov     [rsp+0B8h+var_94], esi
0x18004bf52  cmp     esi, [rsp+0B8h+var_98]
0x18004bf56  jnb     loc_18004C034
0x18004bf5c  mov     [rsp+0B8h+var_88], 0
0x18004bf65  mov     rdi, [r12]
0x18004bf69  mov     rax, [rdi]
0x18004bf6c  mov     rbx, [rax+30h]
0x18004bf70  lea     rcx, [rsp+0B8h+var_88]
0x18004bf75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004bf7a  lea     r8, [rsp+0B8h+var_88]
0x18004bf7f  mov     edx, esi
0x18004bf81  mov     rcx, rdi
0x18004bf84  mov     rax, rbx
0x18004bf87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf8c  test    eax, eax
0x18004bf8e  js      loc_18004C023
0x18004bf94  mov     [rsp+0B8h+string], 0
0x18004bf9d  mov     rdi, [rsp+0B8h+var_88]
0x18004bfa2  mov     rax, [rdi]
0x18004bfa5  mov     rbx, [rax+30h]
0x18004bfa9  xor     ecx, ecx; string
0x18004bfab  call    cs:__imp_WindowsDeleteString
0x18004bfb1  mov     [rsp+0B8h+string], 0
0x18004bfba  lea     rdx, [rsp+0B8h+string]
0x18004bfbf  mov     rcx, rdi
0x18004bfc2  mov     rax, rbx
0x18004bfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfca  test    eax, eax
0x18004bfcc  js      short loc_18004C017
0x18004bfce  xor     edx, edx; length
0x18004bfd0  mov     rcx, [rsp+0B8h+string]; string
0x18004bfd5  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bfdb  mov     rdx, rax
0x18004bfde  lea     rcx, [rsp+0B8h+var_60]
0x18004bfe3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004bfe8  nop
0x18004bfe9  lea     rdx, [rsp+0B8h+var_60]
0x18004bfee  mov     rcx, r15
0x18004bff1  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x18004bff6  nop
0x18004bff7  lea     rcx, [rsp+0B8h+var_60]
0x18004bffc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004c001  nop
0x18004c002  jmp     short loc_18004C017
0x18004c004  mov     esi, [rsp+0B8h+var_94]
0x18004c008  mov     r13, [rsp+0B8h+var_80]
0x18004c00d  mov     r15, [rsp+0B8h+var_78]
0x18004c012  mov     r12, [rsp+0B8h+var_70]
0x18004c017  mov     rcx, [rsp+0B8h+string]; string
0x18004c01c  call    cs:__imp_WindowsDeleteString
0x18004c022  nop
0x18004c023  lea     rcx, [rsp+0B8h+var_88]
0x18004c028  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004c02d  inc     esi
0x18004c02f  jmp     loc_18004BF4E
0x18004c034  lea     rcx, [r13+550h]; lpSystemTimeAsFileTime
0x18004c03b  call    cs:__imp_GetSystemTimeAsFileTime
0x18004c041  nop
0x18004c042  lea     rcx, [rsp+0B8h+var_68]
0x18004c047  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004c04c  mov     rcx, [rsp+0B8h+var_40]
0x18004c051  xor     rcx, rsp; StackCookie
0x18004c054  call    __security_check_cookie
0x18004c059  add     rsp, 88h
0x18004c060  pop     r15
0x18004c062  pop     r13
0x18004c064  pop     r12
0x18004c066  pop     rdi
0x18004c067  pop     rsi
0x18004c068  pop     rbx
0x18004c069  retn
```
