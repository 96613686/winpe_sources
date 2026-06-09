# CMVMasterDatastore::Initialize(ushort const *,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003)

- ea: `0x180009430`
- end: `0x1800095e2`
- name: `?Initialize@CMVMasterDatastore@@UEAAJPEBGW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64, void *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000108c`
- `0x1800018f4`
- `0x180009430`
- `0x1800095e8`
- `0x18000a2e4`
- `0x18000a540`
- `0x180010124`
- `0x180012010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800094d1`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x1800094d1`

## pseudocode

```c
__int64 __fastcall CMVMasterDatastore::Initialize(__int64 a1, void *a2, int a3)
{
  _QWORD *v6; // rbx
  void *v7; // rcx
  int v8; // esi
  __int64 v9; // rbx
  __int64 *v10; // rdi
  __int64 v11; // rcx
  void *v12; // rax
  int v13; // ebx
  __int64 result; // rax
  const char *v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  int v18[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-38h]
  __int64 v20; // [rsp+48h] [rbp-30h] BYREF
  char v21; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v23; // [rsp+80h] [rbp+8h]

  v6 = (_QWORD *)(a1 + 40);
  v7 = (void *)(a1 + 40);
  try
  {
    std::wstring::assign(v7, a2);
    *(_DWORD *)(a1 + 72) = a3;
    if ( (unsigned int)dword_180019000 > 4 )
    {
      if ( v6[3] >= 8u )
        v6 = (_QWORD *)*v6;
      *(_QWORD *)v18 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_180019000,
        (unsigned int)&word_18001554E,
        0,
        0,
        (__int64)v18);
    }
    v17 = 0;
    v19 = &v17;
    v20 = 0;
    v21 = 1;
    v8 = OpenProvisioningPackageForRead(a2, &v20);
    if ( v21 )
    {
      v9 = v20;
      v10 = v19;
      v11 = *v19;
      if ( v20 != *v19 )
      {
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 128LL))(v11);
        *v10 = v9;
      }
    }
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provisioningfilemanager.cpp",
        (const char *)(unsigned int)v8,
        v16);
    v12 = operator new(0x18u);
    *(_QWORD *)v18 = v12;
    if ( v12 )
      v12 = (void *)ProvisioningFileManager::ProvisioningFileManager(v12, &v17);
    *(_QWORD *)v18 = v12;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 128LL))(v17);
    v13 = CMVMasterDatastore::InitializeWithProvisioningFileManager(a1, v18);
    v23 = v13;
    if ( *(_QWORD *)v18 )
      (***(void (__fastcall ****)(_QWORD, __int64))v18)(*(_QWORD *)v18, 1);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastore.cpp",
        (const char *)(unsigned int)v13,
        v16);
    result = (unsigned int)v13;
  }
  catch ( ... )
  {
    LODWORD(v15) = v23;
    return (unsigned int)wil::details::in1diag3::Return_CaughtExceptionMsg(
                           retaddr,
                           (void *)0x37,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastore.cpp",
                           "InitMasterDatastoreFailed: %X",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180009430  mov     rax, rsp
0x180009433  mov     [rax+10h], rbx
0x180009437  push    rsi
0x180009438  push    rdi
0x180009439  push    r14
0x18000943b  sub     rsp, 60h
0x18000943f  mov     esi, r8d
0x180009442  mov     rdi, rdx
0x180009445  mov     r14, rcx
0x180009448  mov     dword ptr [rax+20h], 0
0x18000944f  mov     [rsp+78h+arg_0], 0
0x18000945a  lea     rbx, [rcx+28h]
0x18000945e  mov     rcx, rbx; void *
0x180009461  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180009466  mov     [r14+48h], esi
0x18000946a  mov     eax, cs:dword_180019000
0x180009470  cmp     eax, 4
0x180009473  jbe     short loc_1800094A8
0x180009475  cmp     qword ptr [rbx+18h], 8
0x18000947a  jb      short loc_18000947F
0x18000947c  mov     rbx, [rbx]
0x18000947f  mov     qword ptr [rsp+78h+var_40], rbx
0x180009484  lea     rax, [rsp+78h+var_40]
0x180009489  mov     qword ptr [rsp+78h+var_58], rax; int
0x18000948e  xor     r9d, r9d
0x180009491  xor     r8d, r8d
0x180009494  lea     rdx, word_18001554E
0x18000949b  lea     rcx, dword_180019000
0x1800094a2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800094a7  nop
0x1800094a8  mov     [rsp+78h+var_48], 0
0x1800094b1  lea     rax, [rsp+78h+var_48]
0x1800094b6  mov     [rsp+78h+var_38], rax
0x1800094bb  mov     [rsp+78h+var_30], 0
0x1800094c4  mov     [rsp+78h+var_28], 1
0x1800094c9  lea     rdx, [rsp+78h+var_30]
0x1800094ce  mov     rcx, rdi
0x1800094d1  call    cs:__imp_OpenProvisioningPackageForRead
0x1800094d7  mov     esi, eax
0x1800094d9  cmp     [rsp+78h+var_28], 0
0x1800094de  jz      short loc_180009509
0x1800094e0  mov     rbx, [rsp+78h+var_30]
0x1800094e5  mov     rdi, [rsp+78h+var_38]
0x1800094ea  mov     rcx, [rdi]
0x1800094ed  cmp     rbx, rcx
0x1800094f0  jz      short loc_180009509
0x1800094f2  test    rcx, rcx
0x1800094f5  jz      short loc_180009506
0x1800094f7  mov     rax, [rcx]
0x1800094fa  mov     rax, [rax+80h]
0x180009501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009506  mov     [rdi], rbx
0x180009509  mov     rcx, [rsp+78h]; this
0x18000950e  test    esi, esi
0x180009510  js      loc_1800095B7
0x180009516  mov     ecx, 18h; Size
0x18000951b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009520  mov     qword ptr [rsp+78h+var_40], rax
0x180009525  test    rax, rax
0x180009528  jz      short loc_180009538
0x18000952a  lea     rdx, [rsp+78h+var_48]
0x18000952f  mov     rcx, rax
0x180009532  call    ??0ProvisioningFileManager@@QEAA@$$QEAV?$unique_ptr@UIProvisioningPackage@@U?$ProvReleaser@UIProvisioningPackage@@@@@std@@@Z; ProvisioningFileManager::ProvisioningFileManager(std::unique_ptr<IProvisioningPackage,ProvReleaser<IProvisioningPackage>> &&)
0x180009537  nop
0x180009538  mov     qword ptr [rsp+78h+var_40], rax
0x18000953d  mov     [rsp+78h+arg_18], 1
0x180009548  mov     rcx, [rsp+78h+var_48]
0x18000954d  test    rcx, rcx
0x180009550  jz      short loc_180009562
0x180009552  mov     rax, [rcx]
0x180009555  mov     rax, [rax+80h]
0x18000955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009561  nop
0x180009562  lea     rdx, [rsp+78h+var_40]
0x180009567  mov     rcx, r14
0x18000956a  call    ?InitializeWithProvisioningFileManager@CMVMasterDatastore@@QEAAJ$$QEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z; CMVMasterDatastore::InitializeWithProvisioningFileManager(std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &&)
0x18000956f  mov     ebx, eax
0x180009571  mov     [rsp+78h+arg_0], eax
0x180009578  mov     rcx, qword ptr [rsp+78h+var_40]
0x18000957d  test    rcx, rcx
0x180009580  jz      short loc_180009592
0x180009582  mov     rax, [rcx]
0x180009585  mov     edx, 1
0x18000958a  mov     rax, [rax]
0x18000958d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009592  mov     rcx, [rsp+78h]; this
0x180009597  test    ebx, ebx
0x180009599  js      short loc_1800095CC
0x18000959b  mov     eax, ebx
0x18000959d  jmp     short loc_1800095A6
0x18000959f  mov     eax, [rsp+78h+arg_0]
0x1800095a6  mov     rbx, [rsp+78h+arg_8]
0x1800095ae  add     rsp, 60h
0x1800095b2  pop     r14
0x1800095b4  pop     rdi
0x1800095b5  pop     rsi
0x1800095b6  retn
0x1800095b7  mov     r9d, esi; char *
0x1800095ba  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\lib\\provision"...
0x1800095c1  mov     edx, 0D5h; void *
0x1800095c6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800095cc  mov     r9d, ebx; char *
0x1800095cf  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800095d6  mov     edx, 35h ; '5'; void *
0x1800095db  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
