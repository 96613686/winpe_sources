# ServiceManager::FindNearbyPackages(FindPackagesSearchParameters const &,ulong *,__MIDL_odmlapi_0008 * *)

- ea: `0x180015de0`
- end: `0x180015ec7`
- name: `?FindNearbyPackages@ServiceManager@@UEAAJAEBUFindPackagesSearchParameters@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, const struct FindPackagesSearchParameters *, unsigned int *, struct __MIDL_odmlapi_0008 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800078d0`
- `0x18000828c`
- `0x18000f700`
- `0x180015de0`
- `0x18001e520`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `MapsStore!MapsStore_FindNearbyPackages` at `0x180015e56`
- `MapsStore!MapsStore_FindNearbyPackages` at `0x180015e56`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015e30`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015e72`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015e30`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180015e72`

## string_xrefs

- `0x180015e27`: `ServiceManager::FindNearbyPackages`
- `0x180015e69`: `ServiceManager::FindNearbyPackages`

## pseudocode

```c
__int64 __fastcall ServiceManager::FindNearbyPackages(
        ServiceManager *this,
        const struct FindPackagesSearchParameters *a2,
        unsigned int *a3,
        struct __MIDL_odmlapi_0008 **a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int NearbyPackages; // eax
  int v11; // r8d
  _BYTE v13[16]; // [rsp+20h] [rbp-58h] BYREF
  void *v14[9]; // [rsp+30h] [rbp-48h] BYREF

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(v14);
  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v13);
  v8 = ServiceManager::WaitForOdmlInit(this);
  if ( v8 < 0 )
  {
    v9 = ZTraceReportPropagation(v8, "ServiceManager::FindNearbyPackages", 1391, this);
    RelockableGate::~RelockableGate((RelockableGate *)v13);
    goto LABEL_9;
  }
  RelockableGate::~RelockableGate((RelockableGate *)v13);
  NearbyPackages = MapsStore_FindNearbyPackages(a2, v14);
  if ( NearbyPackages < 0 )
  {
    v11 = 1394;
LABEL_5:
    v9 = ZTraceReportPropagation(NearbyPackages, "ServiceManager::FindNearbyPackages", v11, this);
    goto LABEL_9;
  }
  NearbyPackages = PackageManager::GetLeafPackages((char *)this + 3568, v14, a3, a4);
  if ( NearbyPackages < 0 )
  {
    v11 = 1397;
    goto LABEL_5;
  }
  v9 = 0;
LABEL_9:
  if ( v14[0] )
    std::_Deallocate<16>(v14[0], ((char *)v14[2] - (char *)v14[0]) & 0xFFFFFFFFFFFFFFFCuLL);
  return v9;
}

```

## disassembly

```asm
0x180015de0  push    rbx
0x180015de2  push    rbp
0x180015de3  push    rsi
0x180015de4  push    rdi
0x180015de5  sub     rsp, 58h
0x180015de9  mov     rsi, r9
0x180015dec  mov     rbp, r8
0x180015def  mov     rdi, rdx
0x180015df2  mov     rbx, rcx
0x180015df5  lea     rcx, [rsp+78h+var_48]
0x180015dfa  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180015dff  nop
0x180015e00  lea     rcx, [rbx+0D48h]
0x180015e07  lea     rdx, [rsp+78h+var_58]
0x180015e0c  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180015e11  nop
0x180015e12  mov     rcx, rbx; this
0x180015e15  call    ?WaitForOdmlInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForOdmlInit(void)
0x180015e1a  test    eax, eax
0x180015e1c  jns     short loc_180015E44
0x180015e1e  mov     r9, rbx
0x180015e21  mov     r8d, 56Fh
0x180015e27  lea     rdx, aServicemanager_39; "ServiceManager::FindNearbyPackages"
0x180015e2e  mov     ecx, eax
0x180015e30  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015e36  mov     ebx, eax
0x180015e38  lea     rcx, [rsp+78h+var_58]; this
0x180015e3d  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015e42  jmp     short loc_180015EA1
0x180015e44  lea     rcx, [rsp+78h+var_58]; this
0x180015e49  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015e4e  lea     rdx, [rsp+78h+var_48]
0x180015e53  mov     rcx, rdi
0x180015e56  call    cs:__imp_?MapsStore_FindNearbyPackages@@YAJAEBUFindPackagesSearchParameters@@PEAV?$vector@IV?$allocator@I@std@@@std@@@Z; MapsStore_FindNearbyPackages(FindPackagesSearchParameters const &,std::vector<uint> *)
0x180015e5c  test    eax, eax
0x180015e5e  jns     short loc_180015E7C
0x180015e60  mov     r8d, 572h
0x180015e66  mov     r9, rbx
0x180015e69  lea     rdx, aServicemanager_39; "ServiceManager::FindNearbyPackages"
0x180015e70  mov     ecx, eax
0x180015e72  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180015e78  mov     ebx, eax
0x180015e7a  jmp     short loc_180015EA1
0x180015e7c  lea     rcx, [rbx+0DF0h]
0x180015e83  mov     r9, rsi
0x180015e86  mov     r8, rbp
0x180015e89  lea     rdx, [rsp+78h+var_48]
0x180015e8e  call    ?GetLeafPackages@PackageManager@@QEAAJPEBV?$vector@IV?$allocator@I@std@@@std@@PEAKPEAPEAU__MIDL_odmlapi_0008@@@Z; PackageManager::GetLeafPackages(std::vector<uint> const *,ulong *,__MIDL_odmlapi_0008 * *)
0x180015e93  test    eax, eax
0x180015e95  jns     short loc_180015E9F
0x180015e97  mov     r8d, 575h
0x180015e9d  jmp     short loc_180015E66
0x180015e9f  xor     ebx, ebx
0x180015ea1  mov     rcx, [rsp+78h+var_48]
0x180015ea6  test    rcx, rcx
0x180015ea9  jz      short loc_180015EBC
0x180015eab  mov     rdx, [rsp+78h+var_38]
0x180015eb0  sub     rdx, rcx
0x180015eb3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180015eb7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015ebc  mov     eax, ebx
0x180015ebe  add     rsp, 58h
0x180015ec2  pop     rdi
0x180015ec3  pop     rsi
0x180015ec4  pop     rbp
0x180015ec5  pop     rbx
0x180015ec6  retn
```
