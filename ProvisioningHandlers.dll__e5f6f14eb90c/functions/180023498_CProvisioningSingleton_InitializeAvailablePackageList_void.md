# CProvisioningSingleton::InitializeAvailablePackageList(void)

- ea: `0x180023498`
- end: `0x1800235d6`
- name: `?InitializeAvailablePackageList@CProvisioningSingleton@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CProvisioningSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800140f0`

## callees

- `0x1800087ec`
- `0x18000f4fc`
- `0x180019c10`
- `0x18001fbfc`
- `0x180023398`
- `0x180023498`
- `0x1800245ec`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800234be`

## string_xrefs

- `0x180023562`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CProvisioningSingleton::InitializeAvailablePackageList(CProvisioningSingleton *this)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 (__fastcall *v3)(__int64, __int64, char *); // rdi
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-68h]
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v12[32]; // [rsp+30h] [rbp-58h] BYREF
  _WORD v13[8]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  EnterCriticalSection(&stru_18003EF28);
  v11 = &stru_18003EF28;
  if ( byte_18003EFB8 )
  {
    std::vector<std::unique_ptr<ProvPackageInfo>>::clear((char *)&xmmword_18003EF80 + 8);
    v15 = 7;
    v14 = 0;
    v13[0] = 0;
    v1 = std::wstring::wstring(v12);
    GetProviderIdFromResourceId(v1, v13);
    v2 = qword_18003EF18;
    v3 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)qword_18003EF18 + 24LL);
    v4 = std::wstring::wstring(v12);
    v5 = v3(v2, v4, (char *)&xmmword_18003EF80 + 8);
    v7 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
        (const char *)(unsigned int)v5,
        v10);
      LOBYTE(v8) = 1;
      std::wstring::_Tidy(v13, v8, 0);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v11);
      return v7;
    }
    LOBYTE(v6) = 1;
    std::wstring::_Tidy(v13, v6, 0);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180023498  mov     [rsp+arg_0], rbx
0x18002349d  push    rdi
0x18002349e  sub     rsp, 80h
0x1800234a5  mov     rax, cs:__security_cookie
0x1800234ac  xor     rax, rsp
0x1800234af  mov     [rsp+88h+var_18], rax
0x1800234b4  lea     rbx, stru_18003EF28
0x1800234bb  mov     rcx, rbx; lpCriticalSection
0x1800234be  call    cs:__imp_EnterCriticalSection
0x1800234c5  nop     dword ptr [rax+rax+00h]
0x1800234ca  mov     [rsp+88h+var_60], rbx
0x1800234cf  cmp     cs:byte_18003EFB8, 0
0x1800234d6  jz      loc_1800235A9
0x1800234dc  lea     rcx, xmmword_18003EF80+8
0x1800234e3  call    ?clear@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<ProvPackageInfo>>::clear(void)
0x1800234e8  mov     [rsp+88h+var_20], 7
0x1800234f1  mov     [rsp+88h+var_28], 0
0x1800234fa  xor     eax, eax
0x1800234fc  mov     [rsp+88h+var_38], ax
0x180023501  lea     rdx, word_18003EF50
0x180023508  lea     rcx, [rsp+88h+var_58]
0x18002350d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023512  lea     rdx, [rsp+88h+var_38]
0x180023517  mov     rcx, rax
0x18002351a  call    GetProviderIdFromResourceId
0x18002351f  mov     rbx, cs:qword_18003EF18
0x180023526  mov     rax, [rbx]
0x180023529  mov     rdi, [rax+18h]
0x18002352d  lea     rdx, [rsp+88h+var_38]
0x180023532  lea     rcx, [rsp+88h+var_58]
0x180023537  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002353c  lea     r8, xmmword_18003EF80+8
0x180023543  mov     rdx, rax
0x180023546  mov     rcx, rbx
0x180023549  mov     rax, rdi
0x18002354c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023551  mov     ebx, eax
0x180023553  test    eax, eax
0x180023555  jns     short loc_180023592
0x180023557  mov     rcx, [rsp+88h]; this
0x18002355f  mov     r9d, eax; char *
0x180023562  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023569  mov     edx, 0C9h; void *
0x18002356e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023573  nop
0x180023574  xor     r8d, r8d
0x180023577  mov     dl, 1
0x180023579  lea     rcx, [rsp+88h+var_38]
0x18002357e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180023583  nop
0x180023584  lea     rcx, [rsp+88h+var_60]; this
0x180023589  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18002358e  mov     eax, ebx
0x180023590  jmp     short loc_1800235B7
0x180023592  xor     r8d, r8d
0x180023595  mov     dl, 1
0x180023597  lea     rcx, [rsp+88h+var_38]
0x18002359c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800235a1  jmp     short loc_1800235A9
0x1800235a3  mov     ebx, [rsp+88h+var_68]
0x1800235a7  jmp     short loc_1800235AB
0x1800235a9  xor     ebx, ebx
0x1800235ab  lea     rcx, [rsp+88h+var_60]; this
0x1800235b0  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800235b5  mov     eax, ebx
0x1800235b7  mov     rcx, [rsp+88h+var_18]
0x1800235bc  xor     rcx, rsp; StackCookie
0x1800235bf  call    __security_check_cookie
0x1800235c4  mov     rbx, [rsp+88h+arg_0]
0x1800235cc  add     rsp, 80h
0x1800235d3  pop     rdi
0x1800235d4  retn
```
