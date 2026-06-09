# CProvisioningSingleton::GetInstalledPackageList(std::vector<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>,std::allocator<std::unique_ptr<ProvPackageInfo,std::default_delete<ProvPackageInfo>>>> &)

- ea: `0x1800232d8`
- end: `0x180023391`
- name: `?GetInstalledPackageList@CProvisioningSingleton@@QEAAJAEAV?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014640`

## callees

- `0x1800020d0`
- `0x180010238`
- `0x180019c10`
- `0x18001ec4c`
- `0x1800227b4`
- `0x1800232d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800232f7`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800232f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProvisioningSingleton::GetInstalledPackageList(ProvPackageInfo *a1, _QWORD *a2)
{
  const struct ProvPackageInfo **v3; // rbx
  const struct ProvPackageInfo **v4; // rdi
  unsigned int v5; // esi
  ProvPackageInfo *v6; // rax
  ProvPackageInfo *v7; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ProvPackageInfo *v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v11 = a1;
  v12 = (unsigned __int64)&stru_18003EF28 & -(__int64)TryEnterCriticalSection(&stru_18003EF28);
  if ( v12 )
  {
    v4 = (const struct ProvPackageInfo **)*((_QWORD *)&xmmword_18003EFA0 + 1);
    v3 = (const struct ProvPackageInfo **)xmmword_18003EFA0;
    v5 = 0;
    while ( v3 != v4 )
    {
      try
      {
        v6 = (ProvPackageInfo *)operator new(0x60u);
        v11 = v6;
        if ( v6 )
          v7 = ProvPackageInfo::ProvPackageInfo(v6, *v3);
        else
          v7 = 0;
        v11 = v7;
        std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(
          a2,
          (__int64 *)&v11);
        std::unique_ptr<ProvPackageInfo>::_Delete(&v11);
        ++v3;
      }
      catch ( ... )
      {
        LODWORD(v11) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x123,
                         (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\common.cpp",
                         v8);
        v5 = (unsigned int)v11;
        break;
      }
    }
  }
  else
  {
    v5 = 0;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v12);
  return v5;
}

```

## disassembly

```asm
0x1800232d8  mov     [rsp+arg_8], rbx
0x1800232dd  mov     [rsp+arg_0], rcx
0x1800232e2  push    rsi
0x1800232e3  push    rdi
0x1800232e4  push    r14
0x1800232e6  sub     rsp, 20h
0x1800232ea  mov     r14, rdx
0x1800232ed  lea     rbx, stru_18003EF28
0x1800232f4  mov     rcx, rbx; lpCriticalSection
0x1800232f7  call    cs:__imp_TryEnterCriticalSection
0x1800232fe  nop     dword ptr [rax+rax+00h]
0x180023303  neg     eax
0x180023305  sbb     rcx, rcx
0x180023308  and     rcx, rbx
0x18002330b  mov     [rsp+38h+arg_10], rcx
0x180023310  jz      short loc_180023374
0x180023312  mov     rbx, qword ptr cs:xmmword_18003EFA0
0x180023319  mov     rdi, qword ptr cs:xmmword_18003EFA0+8
0x180023320  xor     esi, esi
0x180023322  cmp     rbx, rdi
0x180023325  jz      short loc_180023376
0x180023327  mov     ecx, 60h ; '`'; Size
0x18002332c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023331  mov     [rsp+38h+arg_0], rax
0x180023336  test    rax, rax
0x180023339  jz      short loc_180023348
0x18002333b  mov     rdx, [rbx]; struct ProvPackageInfo *
0x18002333e  mov     rcx, rax; this
0x180023341  call    ??0ProvPackageInfo@@QEAA@AEBV0@@Z; ProvPackageInfo::ProvPackageInfo(ProvPackageInfo const &)
0x180023346  jmp     short loc_18002334B
0x180023348  mov     rax, rsi
0x18002334b  mov     [rsp+38h+arg_0], rax
0x180023350  lea     rdx, [rsp+38h+arg_0]
0x180023355  mov     rcx, r14
0x180023358  call    ??$emplace_back@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@1@@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::emplace_back<std::unique_ptr<ProvPackageInfo>>(std::unique_ptr<ProvPackageInfo> &&)
0x18002335d  nop
0x18002335e  lea     rcx, [rsp+38h+arg_0]
0x180023363  call    ?_Delete@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@AEAAXXZ; std::unique_ptr<ProvPackageInfo>::_Delete(void)
0x180023368  add     rbx, 8
0x18002336c  jmp     short loc_180023322
0x18002336e  mov     esi, dword ptr [rsp+38h+arg_0]
0x180023372  jmp     short loc_180023376
0x180023374  xor     esi, esi
0x180023376  lea     rcx, [rsp+38h+arg_10]; this
0x18002337b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180023380  mov     eax, esi
0x180023382  mov     rbx, [rsp+38h+arg_8]
0x180023387  add     rsp, 20h
0x18002338b  pop     r14
0x18002338d  pop     rdi
0x18002338e  pop     rsi
0x18002338f  retn
```
