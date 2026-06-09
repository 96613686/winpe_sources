# CExtensionStateManager::_LoadSortedPinnedList(CCoSimpleArray<EXTENSION_STATE,4294967294,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>> *,IExtensionListItem *)

- ea: `0x18004ad3c`
- end: `0x18004af54`
- name: `?_LoadSortedPinnedList@CExtensionStateManager@@AEAAJPEAV?$CCoSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@@@PEAUIExtensionListItem@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(CExtensionStateManager *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800442b0`
- `0x180047160`

## callees

- `0x1800030b6`
- `0x1800107a0`
- `0x180010f20`
- `0x180011724`
- `0x18002b230`
- `0x18004368c`
- `0x180043870`
- `0x180048f88`
- `0x180049834`
- `0x18004ac1c`
- `0x18004ad3c`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ae0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ae0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af21`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004addf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004addf`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_LoadSortedPinnedList(
        CExtensionStateManager *this,
        __int64 a2,
        struct IExtensionListItem *a3)
{
  int ExtensionIdFromExtensionItem; // ebx
  DWORD v7; // esi
  HKEY v8; // rcx
  LSTATUS v9; // eax
  PCWSTR StringRawBuffer; // rax
  WCHAR *v11; // rcx
  signed __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  LPVOID *v18; // rsi
  unsigned int v19; // edx
  void *v20; // rcx
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v25[32]; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+268h] [rbp+168h]
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF

  CTSimpleArray<CProfferService::SERVICE_ITEM,4294967294,CTPolicyCoTaskMem<CProfferService::SERVICE_ITEM>,CSimpleArrayStandardCompareHelper<CProfferService::SERVICE_ITEM>,CSimpleArrayStandardMergeHelper<CProfferService::SERVICE_ITEM>>::RemoveAll(a2);
  if ( *((_QWORD *)this + 2) )
  {
    string = 0;
    ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(a3, (struct Windows::Internal::String *)&string);
    v7 = 0;
    while ( ExtensionIdFromExtensionItem >= 0 )
    {
      v8 = (HKEY)*((_QWORD *)this + 2);
      cchName[0] = 260;
      v9 = RegEnumKeyExW(v8, v7, Name, cchName, 0, 0, 0, 0);
      ExtensionIdFromExtensionItem = v9;
      if ( v9 > 0 )
        ExtensionIdFromExtensionItem = (unsigned __int16)v9 | 0x80070000;
      if ( ExtensionIdFromExtensionItem == -2147024637 )
      {
        ExtensionIdFromExtensionItem = 0;
        break;
      }
      if ( ExtensionIdFromExtensionItem >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v11 = Name;
        v12 = (char *)StringRawBuffer - (char *)Name;
        do
        {
          v13 = *(WCHAR *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( v14 )
        {
          memset_0(v25, 0, 0x210u);
          ExtensionIdFromExtensionItem = CExtensionStateManager::_LoadExtensionState(
                                           this,
                                           Name,
                                           (struct EXTENSION_STATE *)v25);
          if ( ExtensionIdFromExtensionItem >= 0 && (v26 & 1) != 0 )
          {
            v15 = *(_QWORD *)(a2 + 8);
            ExtensionIdFromExtensionItem = 0;
            if ( v15 != *(_QWORD *)(a2 + 24)
              || (ExtensionIdFromExtensionItem = CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_EnsureCapacity(
                                                   a2,
                                                   v15 + 1),
                  ExtensionIdFromExtensionItem >= 0) )
            {
              v16 = *(_QWORD *)(a2 + 8);
              *(_QWORD *)(a2 + 8) = v16 + 1;
              CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_InternalSetAtIndex<EXTENSION_STATE const &>(
                (_QWORD *)a2,
                v16,
                v25);
            }
          }
        }
      }
      ++v7;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v17 = *(_QWORD *)(a2 + 8);
      v22[0] = 0;
      if ( v17 > 1 )
      {
        v18 = (LPVOID *)(a2 + 16);
        *(_QWORD *)(a2 + 16) = 0;
        string = 0;
        if ( (int)ULongLongMult(v17 >> 1, 0x210u, (unsigned __int64 *)&string) >= 0
          && CTCoAllocPolicy::Realloc(v20, v19, 0, (unsigned __int64)string, (void **)(a2 + 16)) >= 0 )
        {
          CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_MergeSort<CExtensionStateManager::PinnedOrderCompare>(
            a2,
            (__int64)v22,
            0,
            *(_QWORD *)(a2 + 8));
          CoTaskMemFree(*v18);
          *v18 = 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)ExtensionIdFromExtensionItem;
}

```

## disassembly

```asm
0x18004ad3c  push    rbp
0x18004ad3e  push    rbx
0x18004ad3f  push    rsi
0x18004ad40  push    rdi
0x18004ad41  push    r14
0x18004ad43  lea     rbp, [rsp-390h]
0x18004ad4b  sub     rsp, 490h
0x18004ad52  mov     rax, cs:__security_cookie
0x18004ad59  xor     rax, rsp
0x18004ad5c  mov     [rbp+3B0h+var_30], rax
0x18004ad63  mov     r14, rcx
0x18004ad66  mov     rbx, r8
0x18004ad69  mov     rcx, rdx
0x18004ad6c  mov     rdi, rdx
0x18004ad6f  call    ?RemoveAll@?$CTSimpleArray@USERVICE_ITEM@CProfferService@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@USERVICE_ITEM@CProfferService@@@@V?$CSimpleArrayStandardCompareHelper@USERVICE_ITEM@CProfferService@@@@V?$CSimpleArrayStandardMergeHelper@USERVICE_ITEM@CProfferService@@@@@@QEAAXXZ; CTSimpleArray<CProfferService::SERVICE_ITEM,4294967294,CTPolicyCoTaskMem<CProfferService::SERVICE_ITEM>,CSimpleArrayStandardCompareHelper<CProfferService::SERVICE_ITEM>,CSimpleArrayStandardMergeHelper<CProfferService::SERVICE_ITEM>>::RemoveAll(void)
0x18004ad74  cmp     qword ptr [r14+10h], 0
0x18004ad79  jz      loc_18004AF30
0x18004ad7f  lea     rdx, [rsp+4B0h+string]; struct Windows::Internal::String *
0x18004ad84  mov     [rsp+4B0h+string], 0
0x18004ad8d  mov     rcx, rbx; struct IExtensionListItem *
0x18004ad90  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18004ad95  mov     ebx, eax
0x18004ad97  xor     esi, esi
0x18004ad99  test    ebx, ebx
0x18004ad9b  js      loc_18004AEAD
0x18004ada1  mov     rcx, [r14+10h]; hKey
0x18004ada5  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x18004adaa  mov     [rsp+4B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18004adb3  lea     r8, [rbp+3B0h+Name]; lpName
0x18004adba  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18004adc3  mov     edx, esi; dwIndex
0x18004adc5  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18004adce  mov     [rsp+4B0h+lpReserved], 0; lpReserved
0x18004add7  mov     [rsp+4B0h+cchName], 104h
0x18004addf  call    cs:__imp_RegEnumKeyExW
0x18004ade5  mov     ebx, eax
0x18004ade7  test    eax, eax
0x18004ade9  jle     short loc_18004ADF4
0x18004adeb  movzx   ebx, ax
0x18004adee  or      ebx, 80070000h
0x18004adf4  cmp     ebx, 80070103h
0x18004adfa  jz      loc_18004AEAB
0x18004ae00  test    ebx, ebx
0x18004ae02  js      loc_18004AEA4
0x18004ae08  mov     rcx, [rsp+4B0h+string]; string
0x18004ae0d  xor     edx, edx; length
0x18004ae0f  call    cs:__imp_WindowsGetStringRawBuffer
0x18004ae15  lea     rcx, [rbp+3B0h+Name]
0x18004ae1c  sub     rax, rcx
0x18004ae1f  movzx   edx, word ptr [rcx]
0x18004ae22  movzx   r8d, word ptr [rcx+rax]
0x18004ae27  sub     edx, r8d
0x18004ae2a  jnz     short loc_18004AE35
0x18004ae2c  add     rcx, 2
0x18004ae30  test    r8d, r8d
0x18004ae33  jnz     short loc_18004AE1F
0x18004ae35  test    edx, edx
0x18004ae37  jz      short loc_18004AEA4
0x18004ae39  xor     edx, edx; Val
0x18004ae3b  lea     rcx, [rsp+4B0h+var_450]; void *
0x18004ae40  mov     r8d, 210h; Size
0x18004ae46  call    memset_0
0x18004ae4b  lea     r8, [rsp+4B0h+var_450]; struct EXTENSION_STATE *
0x18004ae50  mov     rcx, r14; this
0x18004ae53  lea     rdx, [rbp+3B0h+Name]; unsigned __int16 *
0x18004ae5a  call    ?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z; CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)
0x18004ae5f  mov     ebx, eax
0x18004ae61  test    eax, eax
0x18004ae63  js      short loc_18004AEA4
0x18004ae65  test    [rbp+3B0h+var_248], 1
0x18004ae6c  jz      short loc_18004AEA4
0x18004ae6e  mov     rdx, [rdi+8]
0x18004ae72  xor     ebx, ebx
0x18004ae74  cmp     rdx, [rdi+18h]
0x18004ae78  jnz     short loc_18004AE8B
0x18004ae7a  inc     rdx
0x18004ae7d  mov     rcx, rdi
0x18004ae80  call    ?_EnsureCapacity@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAJ_K0@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004ae85  mov     ebx, eax
0x18004ae87  test    eax, eax
0x18004ae89  js      short loc_18004AEA4
0x18004ae8b  mov     rdx, [rdi+8]
0x18004ae8f  lea     r8, [rsp+4B0h+var_450]
0x18004ae94  mov     rcx, rdi
0x18004ae97  lea     rax, [rdx+1]
0x18004ae9b  mov     [rdi+8], rax
0x18004ae9f  call    ??$_InternalSetAtIndex@AEBUEXTENSION_STATE@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAX_KAEBUEXTENSION_STATE@@@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_InternalSetAtIndex<EXTENSION_STATE const &>(unsigned __int64,EXTENSION_STATE const &)
0x18004aea4  inc     esi
0x18004aea6  jmp     loc_18004AD99
0x18004aeab  xor     ebx, ebx
0x18004aead  lea     rcx, [rsp+4B0h+string]; this
0x18004aeb2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004aeb7  test    ebx, ebx
0x18004aeb9  js      short loc_18004AF35
0x18004aebb  mov     rcx, [rdi+8]
0x18004aebf  mov     [rsp+4B0h+var_470], 0
0x18004aec4  cmp     rcx, 1
0x18004aec8  jbe     short loc_18004AF35
0x18004aeca  lea     rsi, [rdi+10h]
0x18004aece  shr     rcx, 1; unsigned __int64
0x18004aed1  lea     r8, [rsp+4B0h+string]; unsigned __int64 *
0x18004aed6  mov     qword ptr [rsi], 0
0x18004aedd  mov     edx, 210h; unsigned __int64
0x18004aee2  mov     [rsp+4B0h+string], 0
0x18004aeeb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004aef0  test    eax, eax
0x18004aef2  js      short loc_18004AF35
0x18004aef4  mov     r9, [rsp+4B0h+string]; unsigned __int64
0x18004aef9  xor     r8d, r8d; void *
0x18004aefc  mov     [rsp+4B0h+lpReserved], rsi; void **
0x18004af01  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18004af06  test    eax, eax
0x18004af08  js      short loc_18004AF35
0x18004af0a  mov     r9, [rdi+8]
0x18004af0e  lea     rdx, [rsp+4B0h+var_470]
0x18004af13  xor     r8d, r8d
0x18004af16  mov     rcx, rdi
0x18004af19  call    ??$_MergeSort@VPinnedOrderCompare@CExtensionStateManager@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAXAEBVPinnedOrderCompare@CExtensionStateManager@@_K1@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_MergeSort<CExtensionStateManager::PinnedOrderCompare>(CExtensionStateManager::PinnedOrderCompare const &,unsigned __int64,unsigned __int64)
0x18004af1e  mov     rcx, [rsi]; pv
0x18004af21  call    cs:__imp_CoTaskMemFree
0x18004af27  mov     qword ptr [rsi], 0
0x18004af2e  jmp     short loc_18004AF35
0x18004af30  mov     ebx, 8000FFFFh
0x18004af35  mov     eax, ebx
0x18004af37  mov     rcx, [rbp+3B0h+var_30]
0x18004af3e  xor     rcx, rsp; StackCookie
0x18004af41  call    __security_check_cookie
0x18004af46  add     rsp, 490h
0x18004af4d  pop     r14
0x18004af4f  pop     rdi
0x18004af50  pop     rsi
0x18004af51  pop     rbx
0x18004af52  pop     rbp
0x18004af53  retn
```
