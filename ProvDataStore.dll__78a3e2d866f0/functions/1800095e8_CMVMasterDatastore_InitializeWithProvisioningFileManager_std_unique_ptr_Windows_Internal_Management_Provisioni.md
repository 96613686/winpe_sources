# CMVMasterDatastore::InitializeWithProvisioningFileManager(std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager,std::default_delete<Windows::Internal::Management::Provisioning::IProvisioningFileManager>> &&)

- ea: `0x1800095e8`
- end: `0x180009747`
- name: `?InitializeWithProvisioningFileManager@CMVMasterDatastore@@QEAAJ$$QEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180009430`

## callees

- `0x180005644`
- `0x1800095e8`
- `0x18000a148`
- `0x18000b31c`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800096a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009708`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800096a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009708`

## string_xrefs

- `0x18000965b`: `masterdatastore.xml`

## pseudocode

```c
__int64 __fastcall CMVMasterDatastore::InitializeWithProvisioningFileManager(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rbx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int64 v7; // rcx
  __int64 *v8; // rdi
  __int64 *v9; // rbx
  __int64 *v10; // rsi
  const char *v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+20h] [rbp-38h]
  void *v13[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v15; // [rsp+68h] [rbp+10h]

  v3 = *a2;
  if ( *a2 )
  {
    v5 = a1 + 80;
    if ( (__int64 *)(a1 + 80) != a2 )
    {
      *a2 = 0;
      v6 = *(void (__fastcall ****)(_QWORD, __int64))v5;
      if ( v3 != *(_QWORD *)v5 )
      {
        if ( v6 )
          (**v6)(v6, 1);
        *(_QWORD *)v5 = v3;
      }
    }
    try
    {
      (*(void (**)(void))(**(_QWORD **)v5 + 8LL))();
      v8 = (__int64 *)ParseSettingsMasterDatastoreXML(v13, v15, *(unsigned int *)(a1 + 72));
      v9 = (__int64 *)(a1 + 16);
      if ( (__int64 *)(a1 + 16) != v8 )
      {
        v10 = (__int64 *)(a1 + 24);
        if ( *v9 )
        {
          std::vector<std::shared_ptr<CConfigSet>>::_Destroy(v7, *v9, *v10);
          operator delete((void *)*v9);
          *v9 = 0;
          *v10 = 0;
          v9[2] = 0;
        }
        *v9 = *v8;
        *v10 = v8[1];
        v9[2] = v8[2];
        *v8 = 0;
        v8[1] = 0;
        v8[2] = 0;
      }
      if ( v13[0] )
      {
        std::vector<std::shared_ptr<CConfigSet>>::_Destroy(v7, (__int64)v13[0], (__int64)v13[1]);
        operator delete(v13[0]);
      }
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(v11) = 0;
      return (unsigned int)wil::details::in1diag3::Return_CaughtExceptionMsg(
                             retaddr,
                             (void *)0x57,
                             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastore.cpp",
                             "InitializeWithProvisioningFileManager: %X",
                             v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastore.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800095e8  mov     [rsp+arg_0], rbx
0x1800095ed  mov     [rsp+arg_10], rsi
0x1800095f2  push    rdi
0x1800095f3  sub     rsp, 50h
0x1800095f7  mov     rsi, rcx
0x1800095fa  mov     rdi, [rdx]
0x1800095fd  test    rdi, rdi
0x180009600  jnz     short loc_180009625
0x180009602  mov     rcx, [rsp+58h]; this
0x180009607  mov     ebx, 80070057h
0x18000960c  mov     r9d, ebx; char *
0x18000960f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180009616  lea     edx, [rdi+43h]; void *
0x180009619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000961e  mov     eax, ebx
0x180009620  jmp     loc_180009737
0x180009625  lea     rbx, [rcx+50h]
0x180009629  cmp     rbx, rdx
0x18000962c  jz      short loc_180009655
0x18000962e  mov     qword ptr [rdx], 0
0x180009635  mov     rcx, [rbx]
0x180009638  cmp     rdi, rcx
0x18000963b  jz      short loc_180009655
0x18000963d  test    rcx, rcx
0x180009640  jz      short loc_180009652
0x180009642  mov     rax, [rcx]
0x180009645  mov     edx, 1
0x18000964a  mov     rax, [rax]
0x18000964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009652  mov     [rbx], rdi
0x180009655  mov     rcx, [rbx]
0x180009658  mov     rax, [rcx]
0x18000965b  lea     r8, ?gc_wszMasterDataStore@@3QBGB; "masterdatastore.xml"
0x180009662  lea     rdx, [rsp+58h+arg_8]
0x180009667  mov     rax, [rax+8]
0x18000966b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009670  nop
0x180009671  mov     r8d, [rsi+48h]
0x180009675  mov     rdx, [rsp+58h+arg_8]
0x18000967a  lea     rcx, [rsp+58h+var_28]
0x18000967f  call    ?ParseSettingsMasterDatastoreXML@@YA?AV?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@PEAUIStream@@W4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@@Z; ParseSettingsMasterDatastoreXML(IStream *,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003)
0x180009684  mov     rdi, rax
0x180009687  lea     rbx, [rsi+10h]
0x18000968b  cmp     rbx, rax
0x18000968e  jz      short loc_1800096EF
0x180009690  mov     rdx, [rbx]
0x180009693  lea     rsi, [rbx+8]
0x180009697  test    rdx, rdx
0x18000969a  jz      short loc_1800096C3
0x18000969c  mov     r8, [rsi]
0x18000969f  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x1800096a4  mov     rcx, [rbx]
0x1800096a7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800096ad  mov     qword ptr [rbx], 0
0x1800096b4  mov     qword ptr [rsi], 0
0x1800096bb  mov     qword ptr [rbx+10h], 0
0x1800096c3  mov     rax, [rdi]
0x1800096c6  mov     [rbx], rax
0x1800096c9  mov     rax, [rdi+8]
0x1800096cd  mov     [rsi], rax
0x1800096d0  mov     rax, [rdi+10h]
0x1800096d4  mov     [rbx+10h], rax
0x1800096d8  mov     qword ptr [rdi], 0
0x1800096df  mov     qword ptr [rdi+8], 0
0x1800096e7  mov     qword ptr [rdi+10h], 0
0x1800096ef  mov     rdx, [rsp+58h+var_28]
0x1800096f4  test    rdx, rdx
0x1800096f7  jz      short loc_18000970F
0x1800096f9  mov     r8, [rsp+58h+var_20]
0x1800096fe  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x180009703  mov     rcx, [rsp+58h+var_28]
0x180009708  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000970e  nop
0x18000970f  mov     rcx, [rsp+58h+arg_8]
0x180009714  test    rcx, rcx
0x180009717  jz      short loc_18000972F
0x180009719  mov     [rsp+58h+arg_8], 0
0x180009722  mov     rax, [rcx]
0x180009725  mov     rax, [rax+10h]
0x180009729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000972e  nop
0x18000972f  xor     eax, eax
0x180009731  jmp     short loc_180009737
0x180009733  mov     eax, dword ptr [rsp+58h+arg_8]
0x180009737  mov     rbx, [rsp+58h+arg_0]
0x18000973c  mov     rsi, [rsp+58h+arg_10]
0x180009741  add     rsp, 50h
0x180009745  pop     rdi
0x180009746  retn
```
