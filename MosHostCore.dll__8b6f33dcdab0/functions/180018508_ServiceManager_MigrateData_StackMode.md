# ServiceManager::MigrateData(StackMode)

- ea: `0x180018508`
- end: `0x180018698`
- name: `?MigrateData@ServiceManager@@AEAAJW4StackMode@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18001e0ac`
- `0x18001e1ac`

## callees

- `0x180003410`
- `0x1800078d0`
- `0x18000828c`
- `0x18000ea5c`
- `0x180011b94`
- `0x180012220`
- `0x180013684`
- `0x180018508`
- `0x1800201d8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800185b0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800185b0`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001854d`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001854d`
- `MosStorage!MosQueryPackagesFromPath` at `0x180018583`
- `MosStorage!MosQueryPackagesFromPath` at `0x180018583`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800185f6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800185f6`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018569`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018569`

## string_xrefs

- `0x180018560`: `ServiceManager::MigrateData`
- `0x1800185ed`: `ServiceManager::MigrateData`

## pseudocode

```c
__int64 __fastcall ServiceManager::MigrateData(void *a1, unsigned int a2)
{
  int DataDirectory; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  int v7; // ebx
  DWORD FileAttributesW; // eax
  _BYTE v10[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE *v11; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE *v12; // [rsp+30h] [rbp-D0h]
  __int64 v13; // [rsp+38h] [rbp-C8h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>>>>>(&v11);
  DataDirectory = MosStorageGetDataDirectory(FileName, 0x104u);
  if ( DataDirectory < 0 )
  {
    v5 = 3962;
LABEL_3:
    v6 = ZTraceReportPropagation(DataDirectory, "ServiceManager::MigrateData", v5, a1);
    goto LABEL_20;
  }
  DataDirectory = MosQueryPackagesFromPath(FileName, &v11, a2);
  if ( DataDirectory < 0 )
  {
    v5 = 3963;
    goto LABEL_3;
  }
  CallingStateTracker::CallingStateTracker(v10);
  if ( !FileName[0] )
  {
    v7 = -2147418113;
LABEL_13:
    ZTraceReportIgnore(v7, "ServiceManager::MigrateData", 3971, a1);
    goto LABEL_14;
  }
  v7 = 0;
  FileAttributesW = GetFileAttributesW(FileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x400) == 0 )
    v7 = RecursiveScanDirectory(
           FileName,
           0,
           (__int64 (__fastcall *)(__int64, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))ForceDelete,
           0);
  if ( v7 < 0 )
    goto LABEL_13;
LABEL_14:
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v10);
  DataDirectory = ServiceManager::CleanupRegistryState((ServiceManager *)a1);
  if ( DataDirectory < 0 )
  {
    v5 = 3975;
    goto LABEL_3;
  }
  if ( v11 != v12 )
  {
    DataDirectory = PackageManager::AddPackagesToInstall((__int64)a1 + 3568, (v12 - v11) >> 2, (__int64)v11, 6);
    if ( DataDirectory < 0 )
    {
      v5 = 3982;
      goto LABEL_3;
    }
  }
  v6 = 0;
LABEL_20:
  if ( v11 )
    std::_Deallocate<16>(v11, (v13 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFFCuLL);
  return v6;
}

```

## disassembly

```asm
0x180018508  mov     [rsp-8+arg_10], rbx
0x18001850d  mov     [rsp-8+arg_18], rdi
0x180018512  push    rbp
0x180018513  lea     rbp, [rsp-160h]
0x18001851b  sub     rsp, 260h
0x180018522  mov     rax, cs:__security_cookie
0x180018529  xor     rax, rsp
0x18001852c  mov     [rbp+160h+var_10], rax
0x180018533  mov     ebx, edx
0x180018535  mov     rdi, rcx
0x180018538  lea     rcx, [rsp+260h+var_238]
0x18001853d  call    ??$?0AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>>>>>(std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>> const &)
0x180018542  nop
0x180018543  mov     edx, 104h
0x180018548  lea     rcx, [rsp+260h+FileName]
0x18001854d  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180018553  test    eax, eax
0x180018555  jns     short loc_180018576
0x180018557  mov     r8d, 0F7Ah
0x18001855d  mov     r9, rdi
0x180018560  lea     rdx, aServicemanager_48; "ServiceManager::MigrateData"
0x180018567  mov     ecx, eax
0x180018569  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001856f  mov     ebx, eax
0x180018571  jmp     loc_180018657
0x180018576  mov     r8d, ebx
0x180018579  lea     rdx, [rsp+260h+var_238]
0x18001857e  lea     rcx, [rsp+260h+FileName]
0x180018583  call    cs:__imp_?MosQueryPackagesFromPath@@YAJPEBGPEAV?$vector@IV?$allocator@I@std@@@std@@W4StackMode@@@Z; MosQueryPackagesFromPath(ushort const *,std::vector<uint> *,StackMode)
0x180018589  test    eax, eax
0x18001858b  jns     short loc_180018595
0x18001858d  mov     r8d, 0F7Bh
0x180018593  jmp     short loc_18001855D
0x180018595  lea     rcx, [rsp+260h+var_240]
0x18001859a  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18001859f  nop
0x1800185a0  xor     eax, eax
0x1800185a2  cmp     ax, [rsp+260h+FileName]
0x1800185a7  jz      short loc_1800185DF
0x1800185a9  xor     ebx, ebx
0x1800185ab  lea     rcx, [rsp+260h+FileName]; lpFileName
0x1800185b0  call    cs:__imp_GetFileAttributesW
0x1800185b6  cmp     eax, 0FFFFFFFFh
0x1800185b9  jz      short loc_1800185D9
0x1800185bb  bt      eax, 0Ah
0x1800185bf  jb      short loc_1800185D9
0x1800185c1  xor     r9d, r9d; void *
0x1800185c4  lea     r8, ForceDelete; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x1800185cb  xor     edx, edx; int
0x1800185cd  lea     rcx, [rsp+260h+FileName]; unsigned __int16 *
0x1800185d2  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x1800185d7  mov     ebx, eax
0x1800185d9  test    ebx, ebx
0x1800185db  jns     short loc_1800185FD
0x1800185dd  jmp     short loc_1800185E4
0x1800185df  mov     ebx, 8000FFFFh
0x1800185e4  mov     r9, rdi
0x1800185e7  mov     r8d, 0F83h
0x1800185ed  lea     rdx, aServicemanager_48; "ServiceManager::MigrateData"
0x1800185f4  mov     ecx, ebx
0x1800185f6  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800185fc  nop
0x1800185fd  lea     rcx, [rsp+260h+var_240]; this
0x180018602  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180018607  mov     rcx, rdi; this
0x18001860a  call    ?CleanupRegistryState@ServiceManager@@AEAAJXZ; ServiceManager::CleanupRegistryState(void)
0x18001860f  test    eax, eax
0x180018611  jns     short loc_18001861E
0x180018613  mov     r8d, 0F87h
0x180018619  jmp     loc_18001855D
0x18001861e  mov     rdx, [rsp+260h+var_230]
0x180018623  mov     r8, [rsp+260h+var_238]
0x180018628  cmp     r8, rdx
0x18001862b  jz      short loc_180018655
0x18001862d  sub     rdx, r8
0x180018630  sar     rdx, 2
0x180018634  lea     rcx, [rdi+0DF0h]
0x18001863b  mov     r9d, 6
0x180018641  call    ?AddPackagesToInstall@PackageManager@@QEAAJKPEBIW4MapsOperationTrigger@@@Z; PackageManager::AddPackagesToInstall(ulong,uint const *,MapsOperationTrigger)
0x180018646  test    eax, eax
0x180018648  jns     short loc_180018655
0x18001864a  mov     r8d, 0F8Eh
0x180018650  jmp     loc_18001855D
0x180018655  xor     ebx, ebx
0x180018657  mov     rcx, [rsp+260h+var_238]
0x18001865c  test    rcx, rcx
0x18001865f  jz      short loc_180018672
0x180018661  mov     rdx, [rsp+260h+var_228]
0x180018666  sub     rdx, rcx
0x180018669  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18001866d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018672  mov     eax, ebx
0x180018674  mov     rcx, [rbp+160h+var_10]
0x18001867b  xor     rcx, rsp; StackCookie
0x18001867e  call    __security_check_cookie
0x180018683  lea     r11, [rsp+260h+var_s0]
0x18001868b  mov     rbx, [r11+20h]
0x18001868f  mov     rdi, [r11+28h]
0x180018693  mov     rsp, r11
0x180018696  pop     rbp
0x180018697  retn
```
