# CExtensionStateManager::_LoadSortedPinnedList(CCoSimpleArray<EXTENSION_STATE,4294967294,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>> *,IExtensionListItem *)

- ea: `0x180069984`
- end: `0x180069b9c`
- name: `?_LoadSortedPinnedList@CExtensionStateManager@@AEAAJPEAV?$CCoSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@@@PEAUIExtensionListItem@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(CExtensionStateManager *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800630d0`
- `0x180065d20`

## callees

- `0x18002e020`
- `0x180032c3c`
- `0x180043c30`
- `0x1800446fc`
- `0x18005ed00`
- `0x180062224`
- `0x180062408`
- `0x180062ccc`
- `0x180067d64`
- `0x1800687a0`
- `0x180069864`
- `0x180069984`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180069a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069b69`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180069a27`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180069a27`

## pseudocode

```c
__int64 __fastcall CExtensionStateManager::_LoadSortedPinnedList(
        CExtensionStateManager *this,
        __int64 a2,
        struct IExtensionListItem *a3)
{
  signed int ExtensionIdFromExtensionItem; // ebx
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
  _BYTE v25[528]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF

  CTSimpleArray<ContextMenuRenderingData *,4294967294,CTPolicyCoTaskMem<ContextMenuRenderingData *>,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>,CSimpleArrayStandardMergeHelper<ContextMenuRenderingData *>>::RemoveAll(a2);
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
          memset_0(v25, 0, sizeof(v25));
          ExtensionIdFromExtensionItem = CExtensionStateManager::_LoadExtensionState(
                                           this,
                                           Name,
                                           (struct EXTENSION_STATE *)v25);
          if ( ExtensionIdFromExtensionItem >= 0 && (v25[520] & 1) != 0 )
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
                a2,
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
            v22,
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
0x180069984  push    rbp
0x180069986  push    rbx
0x180069987  push    rsi
0x180069988  push    rdi
0x180069989  push    r14
0x18006998b  lea     rbp, [rsp-390h]
0x180069993  sub     rsp, 490h
0x18006999a  mov     rax, cs:__security_cookie
0x1800699a1  xor     rax, rsp
0x1800699a4  mov     [rbp+3B0h+var_30], rax
0x1800699ab  mov     r14, rcx
0x1800699ae  mov     rbx, r8
0x1800699b1  mov     rcx, rdx
0x1800699b4  mov     rdi, rdx
0x1800699b7  call    ?RemoveAll@?$CTSimpleArray@PEAUContextMenuRenderingData@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUContextMenuRenderingData@@@@V?$CSimpleArrayStandardCompareHelper@PEAUContextMenuRenderingData@@@@V?$CSimpleArrayStandardMergeHelper@PEAUContextMenuRenderingData@@@@@@QEAAXXZ; CTSimpleArray<ContextMenuRenderingData *,4294967294,CTPolicyCoTaskMem<ContextMenuRenderingData *>,CSimpleArrayStandardCompareHelper<ContextMenuRenderingData *>,CSimpleArrayStandardMergeHelper<ContextMenuRenderingData *>>::RemoveAll(void)
0x1800699bc  cmp     qword ptr [r14+10h], 0
0x1800699c1  jz      loc_180069B78
0x1800699c7  lea     rdx, [rsp+4B0h+string]; struct Windows::Internal::String *
0x1800699cc  mov     [rsp+4B0h+string], 0
0x1800699d5  mov     rcx, rbx; struct IExtensionListItem *
0x1800699d8  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x1800699dd  mov     ebx, eax
0x1800699df  xor     esi, esi
0x1800699e1  test    ebx, ebx
0x1800699e3  js      loc_180069AF5
0x1800699e9  mov     rcx, [r14+10h]; hKey
0x1800699ed  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x1800699f2  mov     [rsp+4B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800699fb  lea     r8, [rbp+3B0h+Name]; lpName
0x180069a02  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x180069a0b  mov     edx, esi; dwIndex
0x180069a0d  mov     [rsp+4B0h+lpClass], 0; lpClass
0x180069a16  mov     [rsp+4B0h+lpReserved], 0; lpReserved
0x180069a1f  mov     [rsp+4B0h+cchName], 104h
0x180069a27  call    cs:__imp_RegEnumKeyExW
0x180069a2d  mov     ebx, eax
0x180069a2f  test    eax, eax
0x180069a31  jle     short loc_180069A3C
0x180069a33  movzx   ebx, ax
0x180069a36  or      ebx, 80070000h
0x180069a3c  cmp     ebx, 80070103h
0x180069a42  jz      loc_180069AF3
0x180069a48  test    ebx, ebx
0x180069a4a  js      loc_180069AEC
0x180069a50  mov     rcx, [rsp+4B0h+string]; string
0x180069a55  xor     edx, edx; length
0x180069a57  call    cs:__imp_WindowsGetStringRawBuffer
0x180069a5d  lea     rcx, [rbp+3B0h+Name]
0x180069a64  sub     rax, rcx
0x180069a67  movzx   edx, word ptr [rcx]
0x180069a6a  movzx   r8d, word ptr [rcx+rax]
0x180069a6f  sub     edx, r8d
0x180069a72  jnz     short loc_180069A7D
0x180069a74  add     rcx, 2
0x180069a78  test    r8d, r8d
0x180069a7b  jnz     short loc_180069A67
0x180069a7d  test    edx, edx
0x180069a7f  jz      short loc_180069AEC
0x180069a81  xor     edx, edx; Val
0x180069a83  lea     rcx, [rsp+4B0h+var_450]; void *
0x180069a88  mov     r8d, 210h; Size
0x180069a8e  call    memset_0
0x180069a93  lea     r8, [rsp+4B0h+var_450]; struct EXTENSION_STATE *
0x180069a98  mov     rcx, r14; this
0x180069a9b  lea     rdx, [rbp+3B0h+Name]; unsigned __int16 *
0x180069aa2  call    ?_LoadExtensionState@CExtensionStateManager@@AEAAJPEBGPEAUEXTENSION_STATE@@@Z; CExtensionStateManager::_LoadExtensionState(ushort const *,EXTENSION_STATE *)
0x180069aa7  mov     ebx, eax
0x180069aa9  test    eax, eax
0x180069aab  js      short loc_180069AEC
0x180069aad  test    [rbp+3B0h+var_248], 1
0x180069ab4  jz      short loc_180069AEC
0x180069ab6  mov     rdx, [rdi+8]
0x180069aba  xor     ebx, ebx
0x180069abc  cmp     rdx, [rdi+18h]
0x180069ac0  jnz     short loc_180069AD3
0x180069ac2  inc     rdx
0x180069ac5  mov     rcx, rdi
0x180069ac8  call    ?_EnsureCapacity@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAJ_K0@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180069acd  mov     ebx, eax
0x180069acf  test    eax, eax
0x180069ad1  js      short loc_180069AEC
0x180069ad3  mov     rdx, [rdi+8]
0x180069ad7  lea     r8, [rsp+4B0h+var_450]
0x180069adc  mov     rcx, rdi
0x180069adf  lea     rax, [rdx+1]
0x180069ae3  mov     [rdi+8], rax
0x180069ae7  call    ??$_InternalSetAtIndex@AEBUEXTENSION_STATE@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAX_KAEBUEXTENSION_STATE@@@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_InternalSetAtIndex<EXTENSION_STATE const &>(unsigned __int64,EXTENSION_STATE const &)
0x180069aec  inc     esi
0x180069aee  jmp     loc_1800699E1
0x180069af3  xor     ebx, ebx
0x180069af5  lea     rcx, [rsp+4B0h+string]; this
0x180069afa  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180069aff  test    ebx, ebx
0x180069b01  js      short loc_180069B7D
0x180069b03  mov     rcx, [rdi+8]
0x180069b07  mov     [rsp+4B0h+var_470], 0
0x180069b0c  cmp     rcx, 1
0x180069b10  jbe     short loc_180069B7D
0x180069b12  lea     rsi, [rdi+10h]
0x180069b16  shr     rcx, 1; unsigned __int64
0x180069b19  lea     r8, [rsp+4B0h+string]; unsigned __int64 *
0x180069b1e  mov     qword ptr [rsi], 0
0x180069b25  mov     edx, 210h; unsigned __int64
0x180069b2a  mov     [rsp+4B0h+string], 0
0x180069b33  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180069b38  test    eax, eax
0x180069b3a  js      short loc_180069B7D
0x180069b3c  mov     r9, [rsp+4B0h+string]; unsigned __int64
0x180069b41  xor     r8d, r8d; void *
0x180069b44  mov     [rsp+4B0h+lpReserved], rsi; void **
0x180069b49  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x180069b4e  test    eax, eax
0x180069b50  js      short loc_180069B7D
0x180069b52  mov     r9, [rdi+8]
0x180069b56  lea     rdx, [rsp+4B0h+var_470]
0x180069b5b  xor     r8d, r8d
0x180069b5e  mov     rcx, rdi
0x180069b61  call    ??$_MergeSort@VPinnedOrderCompare@CExtensionStateManager@@@?$CTSimpleArray@UEXTENSION_STATE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardCompareHelper@UEXTENSION_STATE@@@@V?$CSimpleArrayStandardMergeHelper@UEXTENSION_STATE@@@@@@QEAAXAEBVPinnedOrderCompare@CExtensionStateManager@@_K1@Z; CTSimpleArray<EXTENSION_STATE,4294967294,CTPolicyCoTaskMem<EXTENSION_STATE>,CSimpleArrayStandardCompareHelper<EXTENSION_STATE>,CSimpleArrayStandardMergeHelper<EXTENSION_STATE>>::_MergeSort<CExtensionStateManager::PinnedOrderCompare>(CExtensionStateManager::PinnedOrderCompare const &,unsigned __int64,unsigned __int64)
0x180069b66  mov     rcx, [rsi]; pv
0x180069b69  call    cs:__imp_CoTaskMemFree
0x180069b6f  mov     qword ptr [rsi], 0
0x180069b76  jmp     short loc_180069B7D
0x180069b78  mov     ebx, 8000FFFFh
0x180069b7d  mov     eax, ebx
0x180069b7f  mov     rcx, [rbp+3B0h+var_30]
0x180069b86  xor     rcx, rsp; StackCookie
0x180069b89  call    __security_check_cookie
0x180069b8e  add     rsp, 490h
0x180069b95  pop     r14
0x180069b97  pop     rdi
0x180069b98  pop     rsi
0x180069b99  pop     rbx
0x180069b9a  pop     rbp
0x180069b9b  retn
```
