# OobeEasyConnectTask::OnESimProfileUpdated(_GUID const &,SimSlot,ushort const *,ESimSettingProfileMetaData)

- ea: `0x180021df0`
- end: `0x18002205c`
- name: `?OnESimProfileUpdated@OobeEasyConnectTask@@UEAAJAEBU_GUID@@W4SimSlot@@PEBGUESimSettingProfileMetaData@@@Z`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000ad20`
- `0x18001a1b8`
- `0x18001ad74`
- `0x18001f34c`
- `0x18001f5b8`
- `0x180021df0`
- `0x180022a1c`
- `0x180022a3c`
- `0x180022e9c`
- `0x18002cd20`
- `0x18004921c`
- `0x18004c9d4`

## string_xrefs

- `0x180021e56`: `OobeEasyConnectTask::OnESimProfileUpdated`
- `0x180021f1b`: `OobeEasyConnectTask::OnESimProfileUpdated`
- `0x180021fd1`: `OobeEasyConnectTask::OnESimProfileUpdated`
- `0x18002200b`: `OobeEasyConnectTask::OnESimProfileUpdated`
- `0x180021fc5`: `Profile Added. profileId=%ls, profileName=%ls, serviceProviderName=%ls, Enabled=%hs`
- `0x180021eee`: `onecoreuap\net\ux\mbmediamanager\lib\oobeeasyconnecttask.cpp`
- `0x180021fff`: `Profile Removed. profileId=%ls, profileClass=%d, Enabled=%hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OobeEasyConnectTask::OnESimProfileUpdated(
        __int64 a1,
        _QWORD *a2,
        int a3,
        const wchar_t *a4,
        __int64 a5)
{
  __int64 v7; // rax
  __int64 result; // rax
  int v9; // ecx
  char v10; // al
  unsigned int IsBootstrapProfile; // ebx
  __int64 v12; // r9
  _QWORD *v13; // rbx
  __int64 v14; // r9
  _QWORD *v15; // rcx
  const char *v16; // rdx
  __int64 v17; // rdx
  const char *v18; // rdx
  const char *v19; // r9
  const char *v20; // [rsp+28h] [rbp-80h]
  char v21; // [rsp+40h] [rbp-68h]
  int v22; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v7 = *(_QWORD *)(a1 + 80) - *a2;
  if ( !v7 )
    v7 = *(_QWORD *)(a1 + 88) - a2[1];
  if ( v7 )
    return 0;
  if ( *(_DWORD *)(a1 + 116) == a3 )
  {
    wil::EnterCriticalSection(&v22, a1 + 24);
    try
    {
      v9 = *(_DWORD *)(a5 + 896);
      v10 = *(_BYTE *)(a5 + 888);
      if ( v9 )
      {
        v18 = "true";
        if ( !v10 )
          v18 = "false";
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::OnESimProfileUpdated",
          284,
          "Profile Removed. profileId=%ls, profileClass=%d, Enabled=%hs",
          a4,
          v9,
          v18);
      }
      else
      {
        if ( v10 )
        {
          std::wstring::wstring(v23, a4);
          IsBootstrapProfile = MBUtil::GetIsBootstrapProfile(v23, a1 + 168);
          std::wstring::_Tidy_deallocate(v23);
          if ( (int)(IsBootstrapProfile + 0x80000000) >= 0 && IsBootstrapProfile != -2147024894 )
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0xFE,
              (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
              (const char *)IsBootstrapProfile,
              (int)"GetIsBootstrapProfile failed",
              v20);
          MBSettingUXLogging::Info(
            "OobeEasyConnectTask::OnESimProfileUpdated",
            257,
            "Active profile detected. profileId=%ls. isBootstrapProfile=%d",
            a4,
            *(_BYTE *)(a1 + 168) != 0);
          v12 = -1;
          do
            ++v12;
          while ( a4[v12] );
          std::wstring::_Assign<unsigned short>(a1 + 176, a4);
        }
        else
        {
          v13 = (_QWORD *)(a1 + 176);
          v14 = -1;
          do
            ++v14;
          while ( a4[v14] );
          if ( *(_QWORD *)(a1 + 200) <= 7u )
            v15 = (_QWORD *)(a1 + 176);
          else
            v15 = (_QWORD *)*v13;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v15, *(_QWORD *)(a1 + 192), a4) )
          {
            *(_QWORD *)(a1 + 192) = 0;
            if ( *(_QWORD *)(a1 + 200) > 7u )
              v13 = (_QWORD *)*v13;
            *(_WORD *)v13 = 0;
          }
        }
        v16 = "true";
        if ( !*(_BYTE *)(a5 + 888) )
          v16 = "false";
        MBSettingUXLogging::Info(
          "OobeEasyConnectTask::OnESimProfileUpdated",
          275,
          "Profile Added. profileId=%ls, profileName=%ls, serviceProviderName=%ls, Enabled=%hs",
          a4,
          (const wchar_t *)(a5 + 42),
          (const wchar_t *)(a5 + 302),
          v16);
      }
      LOBYTE(v17) = v21;
      OobeEasyConnectTask::AttemptDiscovery(a1, v17);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v22);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x123,
                             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeeasyconnecttask.cpp",
                             v19);
    }
  }
  else
  {
    MBSettingUXLogging::Info(
      "OobeEasyConnectTask::OnESimProfileUpdated",
      240,
      "Discarding notification for slot %d",
      a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180021df0  mov     [rsp+arg_8], rbx
0x180021df5  push    rsi
0x180021df6  push    rdi
0x180021df7  push    r12
0x180021df9  push    r14
0x180021dfb  push    r15
0x180021dfd  sub     rsp, 80h
0x180021e04  mov     rax, cs:__security_cookie
0x180021e0b  xor     rax, rsp
0x180021e0e  mov     [rsp+0A8h+var_38], rax
0x180021e13  mov     rsi, r9
0x180021e16  mov     rdi, rcx
0x180021e19  mov     r15, [rsp+0A8h+arg_20]
0x180021e21  mov     rax, [rcx+50h]
0x180021e25  sub     rax, [rdx]
0x180021e28  jnz     short loc_180021E32
0x180021e2a  mov     rax, [rcx+58h]
0x180021e2e  sub     rax, [rdx+8]
0x180021e32  xor     r12d, r12d
0x180021e35  test    rax, rax
0x180021e38  jz      short loc_180021E41
0x180021e3a  xor     eax, eax
0x180021e3c  jmp     loc_180022036
0x180021e41  cmp     [rcx+74h], r8d
0x180021e45  jz      short loc_180021E69
0x180021e47  mov     r9d, r8d
0x180021e4a  lea     r8, aDiscardingNoti; "Discarding notification for slot %d"
0x180021e51  mov     edx, 0F0h; unsigned int
0x180021e56  lea     rcx, aOobeeasyconnec_2; "OobeEasyConnectTask::OnESimProfileUpdat"...
0x180021e5d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021e62  xor     eax, eax
0x180021e64  jmp     loc_180022036
0x180021e69  lea     rdx, [rcx+18h]
0x180021e6d  lea     rcx, [rsp+0A8h+var_60]
0x180021e72  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180021e77  nop
0x180021e78  mov     ecx, [r15+380h]
0x180021e7f  mov     al, [r15+378h]
0x180021e86  test    ecx, ecx
0x180021e88  jnz     loc_180021FDF
0x180021e8e  test    al, al
0x180021e90  jz      loc_180021F49
0x180021e96  mov     rdx, rsi
0x180021e99  lea     rcx, [rsp+0A8h+var_58]
0x180021e9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180021ea3  lea     r14, [rdi+0A8h]
0x180021eaa  mov     rdx, r14
0x180021ead  lea     rcx, [rsp+0A8h+var_58]
0x180021eb2  call    ?GetIsBootstrapProfile@MBUtil@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; MBUtil::GetIsBootstrapProfile(std::wstring const &,bool *)
0x180021eb7  mov     ebx, eax
0x180021eb9  lea     rcx, [rsp+0A8h+var_58]
0x180021ebe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021ec3  mov     eax, 80000000h
0x180021ec8  lea     ecx, [rbx+rax]
0x180021ecb  test    eax, ecx
0x180021ecd  jnz     short loc_180021EFF
0x180021ecf  cmp     ebx, 80070002h
0x180021ed5  jz      short loc_180021EFF
0x180021ed7  mov     rcx, [rsp+0A8h]; this
0x180021edf  lea     rax, aGetisbootstrap; "GetIsBootstrapProfile failed"
0x180021ee6  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180021eeb  mov     r9d, ebx; char *
0x180021eee  lea     r8, aOnecoreuapNetU_9; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180021ef5  mov     edx, 0FEh; void *
0x180021efa  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021eff  mov     eax, r12d
0x180021f02  cmp     [r14], r12b
0x180021f05  setnz   al
0x180021f08  mov     [rsp+0A8h+var_88], eax
0x180021f0c  mov     r9, rsi
0x180021f0f  lea     r8, aActiveProfileD_0; "Active profile detected. profileId=%ls."...
0x180021f16  mov     edx, 101h; unsigned int
0x180021f1b  lea     rcx, aOobeeasyconnec_2; "OobeEasyConnectTask::OnESimProfileUpdat"...
0x180021f22  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021f27  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021f2b  inc     r9
0x180021f2e  cmp     [rsi+r9*2], r12w
0x180021f33  jnz     short loc_180021F2B
0x180021f35  lea     rcx, [rdi+0B0h]
0x180021f3c  mov     r8, r9
0x180021f3f  mov     rdx, rsi
0x180021f42  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180021f47  jmp     short loc_180021F8F
0x180021f49  lea     rbx, [rdi+0B0h]
0x180021f50  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021f54  inc     r9
0x180021f57  cmp     [rsi+r9*2], r12w
0x180021f5c  jnz     short loc_180021F54
0x180021f5e  cmp     qword ptr [rbx+18h], 7
0x180021f63  jbe     short loc_180021F6A
0x180021f65  mov     rcx, [rbx]
0x180021f68  jmp     short loc_180021F6D
0x180021f6a  mov     rcx, rbx
0x180021f6d  mov     r8, rsi
0x180021f70  mov     rdx, [rbx+10h]
0x180021f74  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180021f79  test    al, al
0x180021f7b  jz      short loc_180021F8F
0x180021f7d  mov     [rbx+10h], r12
0x180021f81  cmp     qword ptr [rbx+18h], 7
0x180021f86  jbe     short loc_180021F8B
0x180021f88  mov     rbx, [rbx]
0x180021f8b  mov     [rbx], r12w
0x180021f8f  lea     r8, aFalse; "false"
0x180021f96  lea     rdx, aTrue; "true"
0x180021f9d  cmp     [r15+378h], r12b
0x180021fa4  cmovz   rdx, r8
0x180021fa8  lea     rax, [r15+12Eh]
0x180021faf  lea     rcx, [r15+2Ah]
0x180021fb3  mov     [rsp+0A8h+var_78], rdx
0x180021fb8  mov     [rsp+0A8h+var_80], rax
0x180021fbd  mov     qword ptr [rsp+0A8h+var_88], rcx
0x180021fc2  mov     r9, rsi
0x180021fc5  lea     r8, aProfileAddedPr; "Profile Added. profileId=%ls, profileNa"...
0x180021fcc  mov     edx, 113h; unsigned int
0x180021fd1  lea     rcx, aOobeeasyconnec_2; "OobeEasyConnectTask::OnESimProfileUpdat"...
0x180021fd8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180021fdd  jmp     short loc_180022017
0x180021fdf  lea     r8, aFalse; "false"
0x180021fe6  lea     rdx, aTrue; "true"
0x180021fed  test    al, al
0x180021fef  cmovz   rdx, r8
0x180021ff3  mov     [rsp+0A8h+var_80], rdx
0x180021ff8  mov     [rsp+0A8h+var_88], ecx
0x180021ffc  mov     r9, rsi
0x180021fff  lea     r8, aProfileRemoved_0; "Profile Removed. profileId=%ls, profile"...
0x180022006  mov     edx, 11Ch; unsigned int
0x18002200b  lea     rcx, aOobeeasyconnec_2; "OobeEasyConnectTask::OnESimProfileUpdat"...
0x180022012  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180022017  mov     dl, [rsp+0A8h+var_68]
0x18002201b  mov     rcx, rdi
0x18002201e  call    ?AttemptDiscovery@OobeEasyConnectTask@@AEAAXUwrite_lock_required@wil@@@Z; OobeEasyConnectTask::AttemptDiscovery(wil::write_lock_required)
0x180022023  nop
0x180022024  lea     rcx, [rsp+0A8h+var_60]
0x180022029  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002202e  xor     eax, eax
0x180022030  jmp     short loc_180022036
0x180022032  mov     eax, [rsp+0A8h+var_60]
0x180022036  mov     rcx, [rsp+0A8h+var_38]
0x18002203b  xor     rcx, rsp; StackCookie
0x18002203e  call    __security_check_cookie
0x180022043  mov     rbx, [rsp+0A8h+arg_8]
0x18002204b  add     rsp, 80h
0x180022052  pop     r15
0x180022054  pop     r14
0x180022056  pop     r12
0x180022058  pop     rdi
0x180022059  pop     rsi
0x18002205a  retn
```
