# CProvisioningSingleton::GetAvailablePackageList(std::vector<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>,std::allocator<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>>> &)

- ea: `0x180022f8c`
- end: `0x180023061`
- name: `?GetAvailablePackageList@CProvisioningSingleton@@QEAAJAEAV?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@@Z`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800140f0`
- `0x180017c00`

## callees

- `0x1800034b8`
- `0x180010238`
- `0x180019c10`
- `0x18001ec4c`
- `0x18001fbb8`
- `0x1800227b4`
- `0x180022f8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180022fa5`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180022fa5`

## string_xrefs

- `0x18002300d`: `onecoreuap\admin\prov\systemsettingshandlers\lib\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProvisioningSingleton::GetAvailablePackageList(ProvPackageInfo *a1, __int64 a2)
{
  const struct ProvPackageInfo **v3; // rbx
  const struct ProvPackageInfo **v4; // rdi
  ProvPackageInfo *v5; // rax
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ProvPackageInfo *v10; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v11; // [rsp+50h] [rbp+18h] BYREF
  ProvPackageInfo *v12; // [rsp+58h] [rbp+20h]

  v10 = a1;
  v11 = (unsigned __int64)&stru_18003EF28 & -(__int64)TryEnterCriticalSection(&stru_18003EF28);
  if ( v11 )
  {
    v3 = (const struct ProvPackageInfo **)*((_QWORD *)&xmmword_18003EF80 + 1);
    v4 = (const struct ProvPackageInfo **)xmmword_18003EF90;
    while ( v3 != v4 )
    {
      v5 = (ProvPackageInfo *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
      try
      {
        v12 = v5;
        if ( v5 )
          v5 = ProvPackageInfo::ProvPackageInfo(v5, *v3);
        v10 = v5;
        if ( !v5 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xDB,
            (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
            v6);
        std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(a2, &v10);
        std::unique_ptr<ProvPackageInfo>::_Delete(&v10);
        ++v3;
      }
      catch ( ... )
      {
        LODWORD(v10) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0xDF,
                         (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                         v7);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v11);
        return (unsigned int)v10;
      }
    }
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v11);
  return 0;
}

```

## disassembly

```asm
0x180022f8c  mov     [rsp+arg_0], rcx
0x180022f91  push    rbx
0x180022f92  push    rsi
0x180022f93  push    rdi
0x180022f94  sub     rsp, 20h
0x180022f98  mov     rsi, rdx
0x180022f9b  lea     rbx, stru_18003EF28
0x180022fa2  mov     rcx, rbx; lpCriticalSection
0x180022fa5  call    cs:__imp_TryEnterCriticalSection
0x180022fac  nop     dword ptr [rax+rax+00h]
0x180022fb1  neg     eax
0x180022fb3  sbb     rcx, rcx
0x180022fb6  and     rcx, rbx
0x180022fb9  mov     [rsp+38h+arg_10], rcx
0x180022fbe  jz      loc_18002304C
0x180022fc4  mov     rbx, qword ptr cs:xmmword_18003EF80+8
0x180022fcb  mov     rdi, qword ptr cs:xmmword_18003EF90
0x180022fd2  cmp     rbx, rdi
0x180022fd5  jz      short loc_18002304C
0x180022fd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022fde  mov     ecx, 60h ; '`'; unsigned __int64
0x180022fe3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022fe8  mov     [rsp+38h+arg_18], rax
0x180022fed  test    rax, rax
0x180022ff0  jz      short loc_180022FFE
0x180022ff2  mov     rdx, [rbx]; struct ProvPackageInfo *
0x180022ff5  mov     rcx, rax; this
0x180022ff8  call    ??0ProvPackageInfo@@QEAA@AEBV0@@Z; ProvPackageInfo::ProvPackageInfo(ProvPackageInfo const &)
0x180022ffd  nop
0x180022ffe  mov     [rsp+38h+arg_0], rax
0x180023003  mov     rcx, [rsp+38h]; this
0x180023008  test    rax, rax
0x18002300b  jnz     short loc_18002301E
0x18002300d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\systemsettings"...
0x180023014  mov     edx, 0DBh; void *
0x180023019  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002301e  lea     rdx, [rsp+38h+arg_0]
0x180023023  mov     rcx, rsi
0x180023026  call    ??$emplace_back@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@1@@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(std::unique_ptr<ProvPackageInfo> &&)
0x18002302b  nop
0x18002302c  lea     rcx, [rsp+38h+arg_0]
0x180023031  call    ?_Delete@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@AEAAXXZ; std::unique_ptr<ProvPackageInfo>::_Delete(void)
0x180023036  add     rbx, 8
0x18002303a  jmp     short loc_180022FD2
0x18002303c  lea     rcx, [rsp+38h+arg_10]; this
0x180023041  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023046  mov     eax, dword ptr [rsp+38h+arg_0]
0x18002304a  jmp     short loc_180023058
0x18002304c  lea     rcx, [rsp+38h+arg_10]; this
0x180023051  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023056  xor     eax, eax
0x180023058  add     rsp, 20h
0x18002305c  pop     rdi
0x18002305d  pop     rsi
0x18002305e  pop     rbx
0x18002305f  retn
```
