# ATL::CComObject<CIdentityStore>::~CComObject<CIdentityStore>(void)

- ea: `0x18000ae70`
- end: `0x18000afa3`
- name: `??1?$CComObject@VCIdentityStore@@@ATL@@UEAA@XZ`
- size: `307`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ae30`

## callees

- `0x18000ae70`
- `0x18000b0a0`
- `0x1800191ac`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000af52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeb5`

## pseudocode

```c
void __fastcall ATL::CComObject<CIdentityStore>::~CComObject<CIdentityStore>(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // r8
  CIdentityProfileHandler *v4; // rcx
  void *v5; // rsi
  HANDLE ProcessHeap; // rax
  HKEY v7; // rcx

  *(_DWORD *)(a1 + 24) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore2'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'};
  v2 = *(void **)(a1 + 136);
  if ( v2 )
    CloseHandle(v2);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, "CIdentityStore::~CIdentityStore");
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x400) != 0 )
      WPP_SF_s(*((_QWORD *)v4 + 2), 12, v3, "CIdentityStore::~CIdentityStore");
  }
  CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll(a1 + 112);
  v5 = *(void **)(a1 + 112);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *(_QWORD *)(a1 + 112) = 0;
    *(_QWORD *)(a1 + 120) = 0;
  }
  v7 = *(HKEY *)(a1 + 96);
  if ( v7 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(v7);
    *(_QWORD *)(a1 + 96) = -1;
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    *(_BYTE *)(a1 + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  }
}

```

## disassembly

```asm
0x18000ae70  mov     [rsp+arg_0], rbx
0x18000ae75  mov     [rsp+arg_8], rsi
0x18000ae7a  push    rdi
0x18000ae7b  sub     rsp, 20h
0x18000ae7f  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStore@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore'}
0x18000ae86  mov     dword ptr [rcx+18h], 0C0000001h
0x18000ae8d  mov     [rcx], rax
0x18000ae90  mov     rbx, rcx
0x18000ae93  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStore2@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStore2'}
0x18000ae9a  mov     [rcx+8], rax
0x18000ae9e  lea     rax, ??_7?$CComObject@VCIdentityStore@@@ATL@@6BIIdentityStoreEx@@@; const ATL::CComObject<CIdentityStore>::`vftable'{for `IIdentityStoreEx'}
0x18000aea5  mov     [rcx+10h], rax
0x18000aea9  mov     rcx, [rcx+88h]; hObject
0x18000aeb0  test    rcx, rcx
0x18000aeb3  jz      short loc_18000AEBB
0x18000aeb5  call    cs:__imp_CloseHandle
0x18000aebb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000aec2  mov     rax, [rcx]
0x18000aec5  mov     rax, [rax+10h]
0x18000aec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aece  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aed5  lea     rdi, WPP_GLOBAL_Control
0x18000aedc  cmp     rcx, rdi
0x18000aedf  jz      short loc_18000AEFC
0x18000aee1  test    dword ptr [rcx+1Ch], 400h
0x18000aee8  jnz     short loc_18000AF68
0x18000aeea  cmp     rcx, rdi
0x18000aeed  jz      short loc_18000AEFC
0x18000aeef  test    dword ptr [rcx+1Ch], 400h
0x18000aef6  jnz     loc_18000AF89
0x18000aefc  lea     rcx, [rbx+70h]
0x18000af00  call    ?RemoveAll@?$CPtrArrayTemplate@VCProviderInfo@@U?$AutoPtrTraits@VCProviderInfo@@@@@@QEAAXXZ; CPtrArrayTemplate<CProviderInfo,AutoPtrTraits<CProviderInfo>>::RemoveAll(void)
0x18000af05  mov     rsi, [rbx+70h]
0x18000af09  test    rsi, rsi
0x18000af0c  jz      short loc_18000AF2C
0x18000af0e  call    cs:__imp_GetProcessHeap
0x18000af14  mov     r8, rsi; lpMem
0x18000af17  xor     edx, edx; dwFlags
0x18000af19  mov     rcx, rax; hHeap
0x18000af1c  call    cs:__imp_HeapFree
0x18000af22  xor     eax, eax
0x18000af24  mov     [rbx+70h], rax
0x18000af28  mov     [rbx+78h], rax
0x18000af2c  mov     rcx, [rbx+60h]; hKey
0x18000af30  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000af34  jz      short loc_18000AF44
0x18000af36  call    cs:__imp_RegCloseKey
0x18000af3c  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x18000af44  cmp     byte ptr [rbx+48h], 0
0x18000af48  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000af4c  jz      short loc_18000AF58
0x18000af4e  mov     byte ptr [rcx+28h], 0
0x18000af52  call    cs:__imp_DeleteCriticalSection
0x18000af58  mov     rbx, [rsp+28h+arg_0]
0x18000af5d  mov     rsi, [rsp+28h+arg_8]
0x18000af62  add     rsp, 20h
0x18000af66  pop     rdi
0x18000af67  retn
0x18000af68  mov     rcx, [rcx+10h]
0x18000af6c  lea     r9, aCidentitystore_6; "CIdentityStore::~CIdentityStore"
0x18000af73  mov     edx, 0Ah
0x18000af78  call    WPP_SF_s
0x18000af7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af84  jmp     loc_18000AEEA
0x18000af89  mov     rcx, [rcx+10h]
0x18000af8d  lea     r9, aCidentitystore_6; "CIdentityStore::~CIdentityStore"
0x18000af94  mov     edx, 0Ch
0x18000af99  call    WPP_SF_s
0x18000af9e  jmp     loc_18000AEFC
```
