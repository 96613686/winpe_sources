# Container::Container(_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS)

- ea: `0x1800143e0`
- end: `0x180014647`
- name: `??0Container@@QEAA@AEBU_GUID@@W4DSM_INSTALL_BEHAVIOR_FLAGS@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(__int64, const GUID *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800160c0`

## callees

- `0x18000b740`
- `0x18000ce90`
- `0x18000e3cc`
- `0x18001370c`
- `0x180013c1c`
- `0x1800143e0`
- `0x180015d5c`
- `0x180015e18`
- `0x180015e74`
- `0x180015eec`
- `0x180022210`
- `0x1800227b8`
- `0x180023d24`
- `0x180023d50`
- `0x180025664`
- `0x180025f30`
- `0x180025fa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001453f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001453f`

## string_xrefs

- `0x180014551`: `onecoreuap\base\devices\setup\dsm\service\Container.h`

## pseudocode

```c
__int64 __fastcall Container::Container(__int64 a1, const GUID *a2, int a3)
{
  LPOLESTR *v6; // r14
  __int64 v7; // rcx
  HRESULT v8; // eax
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  std::_Ref_count_base *v12; // rcx
  _QWORD *v13; // rax
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  std::_Ref_count_base *v16; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v18; // [rsp+78h] [rbp+10h] BYREF
  int v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = a3;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(GUID *)(a1 + 16) = *a2;
  v6 = (LPOLESTR *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 44) = a3;
  std::wstring::wstring(a1 + 48);
  std::wstring::wstring(a1 + 80);
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  std::vector<std::vector<std::shared_ptr<Job>>>::_Construct_n<>();
  v18 = a1 + 176;
  *(_DWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  std::list<std::shared_ptr<Container>>::_Alloc_sentinel_and_proxy(a1 + 184);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>>>>>(a1 + 200);
  *(_QWORD *)(a1 + 224) = 7;
  *(_QWORD *)(a1 + 232) = 8;
  *(_DWORD *)(a1 + 176) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Job>>>>>>>::_Assign_grow(
    v7,
    16,
    *(_QWORD *)(a1 + 184));
  std::unordered_map<std::wstring,std::shared_ptr<Job>>::unordered_map<std::wstring,std::shared_ptr<Job>>(a1 + 240);
  std::unordered_map<std::wstring,std::shared_ptr<Job>>::unordered_map<std::wstring,std::shared_ptr<Job>>(a1 + 304);
  LODWORD(v18) = 0;
  std::_Hash<std::_Umap_traits<enum JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<enum JobType,std::hash<enum JobType>,std::equal_to<enum JobType>>,std::allocator<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::_Hash<std::_Umap_traits<enum JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<enum JobType,std::hash<enum JobType>,std::equal_to<enum JobType>>,std::allocator<std::pair<enum JobType const,std::vector<std::shared_ptr<Job>>>>,0>>(
    a1 + 368,
    &v18);
  *(_QWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 464) = 0;
  *(_BYTE *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  *(_WORD *)(a1 + 488) = 0;
  *(_DWORD *)(a1 + 496) = 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v6,
    0);
  v8 = StringFromCLSID(a2, v6);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\Container.h",
      (const char *)(unsigned int)v8,
      v15);
  if ( GetContainerUINT(*v6, &DEVPKEY_DeviceSetup_DeviceState) )
    *(_DWORD *)(a1 + 44) |= 0x10u;
  *(_BYTE *)(a1 + 40) = GetContainerBoolean(*v6, &DEVPKEY_DeviceContainer_IsLocalMachine);
  v9 = (__int64 *)std::make_shared<DsmSetupRecorder,_GUID const &>(&v15, a2);
  v10 = *v9;
  v11 = v9[1];
  *v9 = 0;
  v9[1] = 0;
  *(_QWORD *)(a1 + 128) = v10;
  v12 = *(std::_Ref_count_base **)(a1 + 136);
  *(_QWORD *)(a1 + 136) = v11;
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  DsmSetupRecorder::Initialize(*(DsmSetupRecorder **)(a1 + 128), a3 != 0);
  v13 = std::make_shared<CDsmTask,_GUID const &,enum DSM_INSTALL_BEHAVIOR_FLAGS &,DsmSetupRecorder &>(
          &v15,
          a2,
          &v19,
          *(_QWORD *)(a1 + 128));
  std::shared_ptr<CDsmTask>::operator=(a1 + 112, v13);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  if ( *(_BYTE *)(a1 + 40) )
    *(_BYTE *)(*(_QWORD *)(a1 + 112) + 348LL) = 1;
  return a1;
}

```

## disassembly

```asm
0x1800143e0  mov     [rsp+arg_18], rbx
0x1800143e5  mov     [rsp+arg_10], r8d
0x1800143ea  mov     [rsp+arg_0], rcx
0x1800143ef  push    rbp
0x1800143f0  push    rsi
0x1800143f1  push    rdi
0x1800143f2  push    r12
0x1800143f4  push    r13
0x1800143f6  push    r14
0x1800143f8  push    r15
0x1800143fa  sub     rsp, 30h
0x1800143fe  mov     r12d, r8d
0x180014401  mov     rbp, rdx
0x180014404  mov     rsi, rcx
0x180014407  xor     r13d, r13d
0x18001440a  mov     [rcx], r13
0x18001440d  mov     [rcx+8], r13
0x180014411  movups  xmm0, xmmword ptr [rdx]
0x180014414  movdqu  xmmword ptr [rcx+10h], xmm0
0x180014419  lea     r14, [rcx+20h]
0x18001441d  mov     [r14], r13
0x180014420  mov     [rcx+2Ch], r8d
0x180014424  add     rcx, 30h ; '0'
0x180014428  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001442d  nop
0x18001442e  lea     rcx, [rsi+50h]
0x180014432  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180014437  nop
0x180014438  lea     r15, [rsi+70h]
0x18001443c  mov     [r15], r13
0x18001443f  mov     [r15+8], r13
0x180014443  mov     [rsi+80h], r13
0x18001444a  mov     [rsi+88h], r13
0x180014451  xor     eax, eax
0x180014453  mov     [rsi+90h], rax
0x18001445a  lea     rcx, [rsi+98h]
0x180014461  mov     [rcx], r13
0x180014464  mov     [rcx+8], r13
0x180014468  mov     [rcx+10h], r13
0x18001446c  call    ??$_Construct_n@$$V@?$vector@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@V?$allocator@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::vector<std::shared_ptr<Job>>>::_Construct_n<>(unsigned __int64)
0x180014471  nop
0x180014472  lea     rdi, [rsi+0B0h]
0x180014479  mov     [rsp+68h+arg_8], rdi
0x18001447e  mov     [rdi], r13d
0x180014481  lea     rbx, [rdi+8]
0x180014485  mov     [rbx], r13
0x180014488  mov     [rbx+8], r13
0x18001448c  mov     rcx, rbx
0x18001448f  call    ?_Alloc_sentinel_and_proxy@?$list@V?$shared_ptr@VContainer@@@std@@V?$allocator@V?$shared_ptr@VContainer@@@std@@@2@@std@@AEAAXXZ; std::list<std::shared_ptr<Container>>::_Alloc_sentinel_and_proxy(void)
0x180014494  nop
0x180014495  lea     rcx, [rdi+18h]
0x180014499  call    ??$?0AEBV?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>>>>>(std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>> const &)
0x18001449e  nop
0x18001449f  mov     qword ptr [rdi+30h], 7
0x1800144a7  mov     qword ptr [rdi+38h], 8
0x1800144af  mov     dword ptr [rdi], 3F800000h
0x1800144b5  mov     r8, [rbx]
0x1800144b8  lea     edx, [r13+10h]
0x1800144bc  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Job>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Job>>>>>)
0x1800144c1  nop
0x1800144c2  lea     rcx, [rsi+0F0h]
0x1800144c9  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::shared_ptr<Job>>::unordered_map<std::wstring,std::shared_ptr<Job>>(void)
0x1800144ce  nop
0x1800144cf  lea     rcx, [rsi+130h]
0x1800144d6  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VJob@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::shared_ptr<Job>>::unordered_map<std::wstring,std::shared_ptr<Job>>(void)
0x1800144db  nop
0x1800144dc  lea     rcx, [rsi+170h]
0x1800144e3  mov     dword ptr [rsp+68h+arg_8], r13d
0x1800144e8  lea     rdx, [rsp+68h+arg_8]
0x1800144ed  call    ??0?$_Hash@V?$_Umap_traits@W4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@V?$_Uhash_compare@W4JobType@@U?$hash@W4JobType@@@std@@U?$equal_to@W4JobType@@@3@@3@V?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@W4JobType@@U?$hash@W4JobType@@@std@@U?$equal_to@W4JobType@@@3@@1@AEBV?$allocator@U?$pair@$$CBW4JobType@@V?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<JobType,std::hash<JobType>,std::equal_to<JobType>>,std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>,0>>::_Hash<std::_Umap_traits<JobType,std::vector<std::shared_ptr<Job>>,std::_Uhash_compare<JobType,std::hash<JobType>,std::equal_to<JobType>>,std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>>,0>>(std::_Uhash_compare<JobType,std::hash<JobType>,std::equal_to<JobType>> const &,std::allocator<std::pair<JobType const,std::vector<std::shared_ptr<Job>>>> const &)
0x1800144f2  nop
0x1800144f3  mov     [rsi+1B0h], r13
0x1800144fa  mov     [rsi+1C0h], r13
0x180014501  mov     [rsi+1D0h], r13
0x180014508  mov     [rsi+1D8h], r13b
0x18001450f  mov     [rsi+1B8h], r13
0x180014516  mov     [rsi+1E0h], r13
0x18001451d  mov     [rsi+1E8h], r13w
0x180014525  mov     dword ptr [rsi+1F0h], 1
0x18001452f  xor     edx, edx
0x180014531  mov     rcx, r14
0x180014534  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014539  mov     rdx, r14; lplpsz
0x18001453c  mov     rcx, rbp; rclsid
0x18001453f  call    cs:__imp_StringFromCLSID
0x180014545  mov     rcx, [rsp+68h]; this
0x18001454a  test    eax, eax
0x18001454c  jns     short loc_180014562
0x18001454e  mov     r9d, eax; char *
0x180014551  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180014558  lea     edx, [r13+20h]; void *
0x18001455c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014562  lea     rdx, DEVPKEY_DeviceSetup_DeviceState; struct _DEVPROPKEY *
0x180014569  mov     rcx, [r14]; unsigned __int16 *
0x18001456c  call    ?GetContainerUINT@@YAIPEBGAEBU_DEVPROPKEY@@@Z; GetContainerUINT(ushort const *,_DEVPROPKEY const &)
0x180014571  test    eax, eax
0x180014573  jz      short loc_180014579
0x180014575  or      dword ptr [rsi+2Ch], 10h
0x180014579  lea     rdx, DEVPKEY_DeviceContainer_IsLocalMachine; struct _DEVPROPKEY *
0x180014580  mov     rcx, [r14]; unsigned __int16 *
0x180014583  call    ?GetContainerBoolean@@YA_NPEBGAEBU_DEVPROPKEY@@@Z; GetContainerBoolean(ushort const *,_DEVPROPKEY const &)
0x180014588  mov     [rsi+28h], al
0x18001458b  mov     rdx, rbp
0x18001458e  lea     rcx, [rsp+68h+var_48]
0x180014593  call    ??$make_shared@VDsmSetupRecorder@@AEBU_GUID@@@std@@YA?AV?$shared_ptr@VDsmSetupRecorder@@@0@AEBU_GUID@@@Z; std::make_shared<DsmSetupRecorder,_GUID const &>(_GUID const &)
0x180014598  mov     rcx, [rax]
0x18001459b  mov     rdx, [rax+8]
0x18001459f  mov     [rax], r13
0x1800145a2  mov     [rax+8], r13
0x1800145a6  mov     [rsi+80h], rcx
0x1800145ad  mov     rcx, [rsi+88h]; this
0x1800145b4  mov     [rsi+88h], rdx
0x1800145bb  test    rcx, rcx
0x1800145be  jz      short loc_1800145C5
0x1800145c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800145c5  mov     rcx, [rsp+68h+var_40]; this
0x1800145ca  test    rcx, rcx
0x1800145cd  jz      short loc_1800145D4
0x1800145cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800145d4  test    r12d, r12d
0x1800145d7  setnz   dl; bool
0x1800145da  mov     rcx, [rsi+80h]; this
0x1800145e1  call    ?Initialize@DsmSetupRecorder@@QEAAX_N@Z; DsmSetupRecorder::Initialize(bool)
0x1800145e6  mov     r9, [rsi+80h]
0x1800145ed  lea     r8, [rsp+68h+arg_10]
0x1800145f5  mov     rdx, rbp
0x1800145f8  lea     rcx, [rsp+68h+var_48]
0x1800145fd  call    ??$make_shared@VCDsmTask@@AEBU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEAVDsmSetupRecorder@@@std@@YA?AV?$shared_ptr@VCDsmTask@@@0@AEBU_GUID@@AEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@AEAVDsmSetupRecorder@@@Z; std::make_shared<CDsmTask,_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS &,DsmSetupRecorder &>(_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS &,DsmSetupRecorder &)
0x180014602  mov     rdx, rax
0x180014605  mov     rcx, r15
0x180014608  call    ??4?$shared_ptr@VCDsmTask@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CDsmTask>::operator=(std::shared_ptr<CDsmTask> &&)
0x18001460d  mov     rcx, [rsp+68h+var_40]; this
0x180014612  test    rcx, rcx
0x180014615  jz      short loc_18001461C
0x180014617  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001461c  cmp     [rsi+28h], r13b
0x180014620  jz      short loc_18001462C
0x180014622  mov     rax, [r15]
0x180014625  mov     byte ptr [rax+15Ch], 1
0x18001462c  mov     rax, rsi
0x18001462f  mov     rbx, [rsp+68h+arg_18]
0x180014637  add     rsp, 30h
0x18001463b  pop     r15
0x18001463d  pop     r14
0x18001463f  pop     r13
0x180014641  pop     r12
0x180014643  pop     rdi
0x180014644  pop     rsi
0x180014645  pop     rbp
0x180014646  retn
```
