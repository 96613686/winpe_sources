# CProvisioningSingleton::InitializeProviderList(void)

- ea: `0x180023d44`
- end: `0x180023ef4`
- name: `?InitializeProviderList@CProvisioningSingleton@@QEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fe34`
- `0x180014870`

## callees

- `0x1800087ec`
- `0x18000e8e0`
- `0x18000f4fc`
- `0x180019c10`
- `0x18001fbfc`
- `0x18001fc64`
- `0x18002019c`
- `0x180023d44`
- `0x1800245c0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023e67`
- `msvcrt!_wcsicmp` at `0x180023e67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023d72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023d72`

## string_xrefs

- `0x180023db2`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CProvisioningSingleton::InitializeProviderList(CProvisioningSingleton *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  const char *v3; // r9
  __int64 result; // rax
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  const wchar_t *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-78h]
  unsigned int v13; // [rsp+20h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+28h] [rbp-70h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v16[32]; // [rsp+48h] [rbp-50h] BYREF
  _WORD v17[8]; // [rsp+68h] [rbp-30h] BYREF
  __int64 v18; // [rsp+78h] [rbp-20h]
  __int64 v19; // [rsp+80h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  EnterCriticalSection(&stru_18003EF28);
  v14 = &stru_18003EF28;
  std::vector<std::wstring>::clear(&xmmword_18003EF70);
  try
  {
    v1 = (**(__int64 (__fastcall ***)(__int64))qword_18003EF18)(qword_18003EF18);
    v2 = v1;
    if ( v1 >= 0 )
    {
      byte_18003EFB8 = 1;
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)qword_18003EF18 + 16LL))(qword_18003EF18, v15);
      v5 = v15[0];
      v6 = v15[1];
      while ( v5 != v6 )
      {
        v19 = 7;
        v18 = 0;
        v17[0] = 0;
        v7 = std::wstring::wstring(v16);
        v8 = v7;
        if ( *(_QWORD *)(v7 + 24) < 8u )
          v9 = (const wchar_t *)v7;
        else
          v9 = *(const wchar_t **)v7;
        if ( !_wcsicmp(v9, L"{FF1A3258-FC24-4168-B0E1-76E1EB1555A5}") )
          std::wstring::assign(v17, L"SystemSettingsProvisioningRemovableMedia");
        LOBYTE(v10) = 1;
        std::wstring::_Tidy(v8, v10, 0);
        std::vector<std::wstring>::emplace_back<std::wstring &>(&xmmword_18003EF70, v17);
        LOBYTE(v11) = 1;
        std::wstring::_Tidy(v17, v11, 0);
        v5 += 32;
      }
      std::vector<std::wstring>::_Tidy(v15);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
        (const char *)(unsigned int)v1,
        v12);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
      result = v2;
    }
  }
  catch ( ... )
  {
    v13 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x9B,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            v3);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180023d44  mov     [rsp+arg_0], rbx
0x180023d49  mov     [rsp+arg_8], rsi
0x180023d4e  push    rdi
0x180023d4f  sub     rsp, 90h
0x180023d56  mov     rax, cs:__security_cookie
0x180023d5d  xor     rax, rsp
0x180023d60  mov     [rsp+98h+var_10], rax
0x180023d68  lea     rbx, stru_18003EF28
0x180023d6f  mov     rcx, rbx; lpCriticalSection
0x180023d72  call    cs:__imp_EnterCriticalSection
0x180023d79  nop     dword ptr [rax+rax+00h]
0x180023d7e  mov     [rsp+98h+var_70], rbx
0x180023d83  lea     rcx, xmmword_18003EF70
0x180023d8a  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180023d8f  mov     rcx, cs:qword_18003EF18
0x180023d96  mov     rax, [rcx]
0x180023d99  mov     rax, [rax]
0x180023d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023da1  mov     ebx, eax
0x180023da3  test    eax, eax
0x180023da5  jns     short loc_180023DD5
0x180023da7  mov     rcx, [rsp+98h]; this
0x180023daf  mov     r9d, eax; char *
0x180023db2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023db9  mov     edx, 91h; void *
0x180023dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023dc3  nop
0x180023dc4  lea     rcx, [rsp+98h+var_70]; this
0x180023dc9  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023dce  mov     eax, ebx
0x180023dd0  jmp     loc_180023ECE
0x180023dd5  mov     cs:byte_18003EFB8, 1
0x180023ddc  mov     rcx, cs:qword_18003EF18
0x180023de3  mov     rax, [rcx]
0x180023de6  lea     rdx, [rsp+98h+var_68]
0x180023deb  mov     rax, [rax+10h]
0x180023def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023df4  nop
0x180023df5  mov     rbx, [rsp+98h+var_68]
0x180023dfa  mov     rdi, [rsp+98h+var_60]
0x180023dff  cmp     rbx, rdi
0x180023e02  jnz     short loc_180023E20
0x180023e04  lea     rcx, [rsp+98h+var_68]
0x180023e09  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180023e0e  nop
0x180023e0f  lea     rcx, [rsp+98h+var_70]; this
0x180023e14  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023e19  xor     eax, eax
0x180023e1b  jmp     loc_180023ECE
0x180023e20  mov     [rsp+98h+var_18], 7
0x180023e2c  mov     [rsp+98h+var_20], 0
0x180023e35  xor     eax, eax
0x180023e37  mov     [rsp+98h+var_30], ax
0x180023e3c  mov     rdx, rbx
0x180023e3f  lea     rcx, [rsp+98h+var_50]
0x180023e44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023e49  mov     rsi, rax
0x180023e4c  mov     [rsp+98h+var_78], rax
0x180023e51  cmp     qword ptr [rax+18h], 8
0x180023e56  jb      short loc_180023E5D
0x180023e58  mov     rcx, [rax]
0x180023e5b  jmp     short loc_180023E60
0x180023e5d  mov     rcx, rsi; String1
0x180023e60  lea     rdx, aFf1a3258Fc2441; "{FF1A3258-FC24-4168-B0E1-76E1EB1555A5}"
0x180023e67  call    cs:__imp__wcsicmp
0x180023e6e  nop     dword ptr [rax+rax+00h]
0x180023e73  test    eax, eax
0x180023e75  jnz     short loc_180023E89
0x180023e77  lea     rdx, aSystemsettings_12; "SystemSettingsProvisioningRemovableMedi"...
0x180023e7e  lea     rcx, [rsp+98h+var_30]
0x180023e83  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180023e88  nop
0x180023e89  xor     r8d, r8d
0x180023e8c  mov     dl, 1
0x180023e8e  mov     rcx, rsi
0x180023e91  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180023e96  lea     rdx, [rsp+98h+var_30]
0x180023e9b  lea     rcx, xmmword_18003EF70
0x180023ea2  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace_back<std::wstring &>(std::wstring &)
0x180023ea7  nop
0x180023ea8  xor     r8d, r8d
0x180023eab  mov     dl, 1
0x180023ead  lea     rcx, [rsp+98h+var_30]
0x180023eb2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180023eb7  add     rbx, 20h ; ' '
0x180023ebb  jmp     loc_180023DFF
0x180023ec0  lea     rcx, [rsp+98h+var_70]; this
0x180023ec5  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023eca  mov     eax, dword ptr [rsp+98h+var_78]
0x180023ece  mov     rcx, [rsp+98h+var_10]
0x180023ed6  xor     rcx, rsp; StackCookie
0x180023ed9  call    __security_check_cookie
0x180023ede  lea     r11, [rsp+98h+var_8]
0x180023ee6  mov     rbx, [r11+10h]
0x180023eea  mov     rsi, [r11+18h]
0x180023eee  mov     rsp, r11
0x180023ef1  pop     rdi
0x180023ef2  retn
```
