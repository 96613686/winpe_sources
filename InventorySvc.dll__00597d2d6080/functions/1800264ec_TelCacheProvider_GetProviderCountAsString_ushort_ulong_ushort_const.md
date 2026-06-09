# TelCacheProvider::GetProviderCountAsString(ushort *,ulong,ushort const *)

- ea: `0x1800264ec`
- end: `0x1800266f1`
- name: `?GetProviderCountAsString@TelCacheProvider@@SAXPEAGKPEBG@Z`
- size: `517`
- prototype: `void __fastcall(wchar_t *Buffer, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180029a44`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x180010ad4`
- `0x1800152d0`
- `0x180020d94`
- `0x180021450`
- `0x180023fc4`
- `0x1800264ec`
- `0x1800272dc`
- `0x18002cc40`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026644`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026644`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002663a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002663a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026621`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026621`

## string_xrefs

- `0x180026547`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180026652`: `TelCacheProvider::GetItemCount failed [%#x]`
- `0x180026554`: `TelCacheProvider::GetProviderCountAsString`
- `0x18002665f`: `TelCacheProvider::GetProviderCountAsString`
- `0x1800266bc`: `TelCacheProvider::GetProviderCountAsString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TelCacheProvider::GetProviderCountAsString(wchar_t *Buffer, __int64 a2, const unsigned __int16 *a3)
{
  int ItemCount; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // [rsp+30h] [rbp-79h]
  unsigned int v10[4]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v11; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v12[80]; // [rsp+58h] [rbp-51h] BYREF
  __int64 v13; // [rsp+A8h] [rbp-1h]
  __int16 v14; // [rsp+B0h] [rbp+7h]
  HANDLE hHandle; // [rsp+B8h] [rbp+Fh] BYREF
  HANDLE hEvent[2]; // [rsp+C0h] [rbp+17h]
  _DWORD *v17; // [rsp+D0h] [rbp+27h]
  int v18; // [rsp+D8h] [rbp+2Fh]
  char v19; // [rsp+DCh] [rbp+33h]

  v10[0] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) )
  {
    memset_0(v12, 0, 0x4Eu);
    v14 = 0;
    hHandle = 0;
    *(_OWORD *)hEvent = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v13 = 0;
    v11 = 0;
    if ( (int)TelCacheProvider::Initialize(&v11, a3, 0, -1, 3, 3, 0x64u) < 0 )
      goto LABEL_17;
    if ( !v13 )
    {
      v6 = -2147467262;
LABEL_16:
      AslLogCallPrintf(
        1,
        "TelCacheProvider::GetProviderCountAsString",
        1497,
        "TelCacheProvider::GetItemCount failed [%#x]",
        v6);
      goto LABEL_17;
    }
    Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((Windows::Compat::Inventory::InventorySynchronization *)&hHandle);
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v13 + 32LL))(v13, v10);
    if ( v19 )
    {
      v7 = v17[1];
      if ( v7 == 1 )
        v19 = 0;
      --v17[1];
      if ( v7 != 1 )
      {
LABEL_15:
        if ( v6 < 0 )
          goto LABEL_16;
LABEL_17:
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v11);
        goto LABEL_18;
      }
    }
    else
    {
      if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
        goto LABEL_15;
      --*v17;
      --v18;
      ReleaseMutex(hHandle);
    }
    SetEvent(hEvent[1]);
    goto LABEL_15;
  }
  ItemCount = Windows::Compat::Inventory::SqliteInvCache::GetItemCount(a3, v10);
  if ( ItemCount < 0 )
    AslLogCallPrintf(
      1,
      "TelCacheProvider::GetProviderCountAsString",
      1485,
      "TelCacheProvider::GetItemCount failed [%#x]",
      ItemCount);
LABEL_18:
  LODWORD(v9) = v10[0];
  v8 = StringCchPrintfExW(Buffer, 8u, 0, 0, 0x800u, L"%d", v9);
  if ( v8 < 0 )
    AslLogCallPrintf(1, "TelCacheProvider::GetProviderCountAsString", 1505, "StringCchPrintfExW failed [%#x]", v8);
}

```

## disassembly

```asm
0x1800264ec  mov     [rsp-8+arg_8], rbx
0x1800264f1  mov     [rsp-8+arg_18], rsi
0x1800264f6  push    rbp
0x1800264f7  push    rdi
0x1800264f8  push    r15
0x1800264fa  lea     rbp, [rsp-47h]
0x1800264ff  sub     rsp, 0F0h
0x180026506  mov     rax, cs:__security_cookie
0x18002650d  xor     rax, rsp
0x180026510  mov     [rbp+57h+var_20], rax
0x180026514  mov     rbx, r8
0x180026517  mov     rdi, rcx
0x18002651a  xor     esi, esi
0x18002651c  mov     [rbp+57h+var_C0], esi
0x18002651f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180026526  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x18002652b  test    al, al
0x18002652d  jz      short loc_180026568
0x18002652f  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x180026533  mov     rcx, rbx; unsigned __int16 *
0x180026536  call    ?GetItemCount@SqliteInvCache@Inventory@Compat@Windows@@SAJPEBGAEAKH@Z; Windows::Compat::Inventory::SqliteInvCache::GetItemCount(ushort const *,ulong &,int)
0x18002653b  test    eax, eax
0x18002653d  jns     loc_18002667A
0x180026543  mov     [rsp+100h+var_E0], eax
0x180026547  lea     r9, aTelcacheprovid_3; "TelCacheProvider::GetItemCount failed ["...
0x18002654e  mov     r8d, 5CDh
0x180026554  lea     rdx, aTelcacheprovid_10; "TelCacheProvider::GetProviderCountAsStr"...
0x18002655b  lea     ecx, [rsi+1]
0x18002655e  call    AslLogCallPrintf
0x180026563  jmp     loc_18002667A
0x180026568  xor     edx, edx; Val
0x18002656a  lea     r8d, [rdx+4Eh]; Size
0x18002656e  lea     rcx, [rbp+57h+var_A8]; void *
0x180026572  call    memset_0
0x180026577  mov     [rbp+57h+var_50], si
0x18002657b  mov     [rbp+57h+hHandle], rsi
0x18002657f  xorps   xmm0, xmm0
0x180026582  movdqa  xmmword ptr [rbp+57h+hEvent], xmm0
0x180026587  mov     [rbp+57h+var_30], rsi
0x18002658b  mov     [rbp+57h+var_28], esi
0x18002658e  mov     [rbp+57h+var_24], sil
0x180026592  mov     [rbp+57h+var_58], rsi
0x180026596  mov     [rbp+57h+var_B0], rsi
0x18002659a  mov     [rsp+100h+var_D0], 64h ; 'd'
0x1800265a2  mov     eax, 3
0x1800265a7  mov     dword ptr [rsp+100h+var_D8], eax
0x1800265ab  mov     [rsp+100h+var_E0], eax
0x1800265af  or      r15d, 0FFFFFFFFh
0x1800265b3  mov     r9d, r15d
0x1800265b6  xor     r8d, r8d
0x1800265b9  mov     rdx, rbx
0x1800265bc  lea     rcx, [rbp+57h+var_B0]
0x1800265c0  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x1800265c5  test    eax, eax
0x1800265c7  js      loc_180026671
0x1800265cd  cmp     [rbp+57h+var_58], rsi
0x1800265d1  jnz     short loc_1800265DA
0x1800265d3  mov     ebx, 80004002h
0x1800265d8  jmp     short loc_18002664E
0x1800265da  lea     rcx, [rbp+57h+hHandle]; this
0x1800265de  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x1800265e3  mov     rcx, [rbp+57h+var_58]
0x1800265e7  mov     rax, [rcx]
0x1800265ea  lea     rdx, [rbp+57h+var_C0]
0x1800265ee  mov     rax, [rax+20h]
0x1800265f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265f7  mov     ebx, eax
0x1800265f9  cmp     [rbp+57h+var_24], sil
0x1800265fd  jz      short loc_18002661A
0x1800265ff  mov     rcx, [rbp+57h+var_30]
0x180026603  mov     eax, [rcx+4]
0x180026606  cmp     eax, 1
0x180026609  jnz     short loc_18002660F
0x18002660b  mov     [rbp+57h+var_24], sil
0x18002660f  add     [rcx+4], r15d
0x180026613  cmp     eax, 1
0x180026616  jnz     short loc_18002664A
0x180026618  jmp     short loc_180026640
0x18002661a  mov     edx, r15d; dwMilliseconds
0x18002661d  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180026621  call    cs:__imp_WaitForSingleObject
0x180026627  test    eax, eax
0x180026629  jnz     short loc_18002664A
0x18002662b  mov     rax, [rbp+57h+var_30]
0x18002662f  add     [rax], r15d
0x180026632  add     [rbp+57h+var_28], r15d
0x180026636  mov     rcx, [rbp+57h+hHandle]; hMutex
0x18002663a  call    cs:__imp_ReleaseMutex
0x180026640  mov     rcx, [rbp+57h+hEvent+8]; hEvent
0x180026644  call    cs:__imp_SetEvent
0x18002664a  test    ebx, ebx
0x18002664c  jns     short loc_180026671
0x18002664e  mov     [rsp+100h+var_E0], ebx
0x180026652  lea     r9, aTelcacheprovid_3; "TelCacheProvider::GetItemCount failed ["...
0x180026659  mov     r8d, 5D9h
0x18002665f  lea     rdx, aTelcacheprovid_10; "TelCacheProvider::GetProviderCountAsStr"...
0x180026666  mov     ecx, 1
0x18002666b  call    AslLogCallPrintf
0x180026670  nop
0x180026671  lea     rcx, [rbp+57h+var_B0]; this
0x180026675  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18002667a  mov     eax, [rbp+57h+var_C0]
0x18002667d  mov     [rsp+100h+var_D0], eax
0x180026681  lea     rax, aD; "%d"
0x180026688  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x18002668d  mov     [rsp+100h+var_E0], 800h; unsigned int
0x180026695  xor     r9d, r9d; unsigned __int64 *
0x180026698  xor     r8d, r8d; unsigned __int16 **
0x18002669b  lea     edx, [r9+8]; unsigned __int64
0x18002669f  mov     rcx, rdi; Buffer
0x1800266a2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800266a7  test    eax, eax
0x1800266a9  jns     short loc_1800266CD
0x1800266ab  mov     [rsp+100h+var_E0], eax
0x1800266af  lea     r9, aStringcchprint_0; "StringCchPrintfExW failed [%#x]"
0x1800266b6  mov     r8d, 5E1h
0x1800266bc  lea     rdx, aTelcacheprovid_10; "TelCacheProvider::GetProviderCountAsStr"...
0x1800266c3  mov     ecx, 1
0x1800266c8  call    AslLogCallPrintf
0x1800266cd  mov     rcx, [rbp+57h+var_20]
0x1800266d1  xor     rcx, rsp; StackCookie
0x1800266d4  call    __security_check_cookie
0x1800266d9  lea     r11, [rsp+100h+var_10]
0x1800266e1  mov     rbx, [r11+28h]
0x1800266e5  mov     rsi, [r11+38h]
0x1800266e9  mov     rsp, r11
0x1800266ec  pop     r15
0x1800266ee  pop     rdi
0x1800266ef  pop     rbp
0x1800266f0  retn
```
