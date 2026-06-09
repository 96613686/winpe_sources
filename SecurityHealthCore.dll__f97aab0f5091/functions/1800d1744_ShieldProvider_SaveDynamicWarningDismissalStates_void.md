# ShieldProvider::SaveDynamicWarningDismissalStates(void)

- ea: `0x1800d1744`
- end: `0x1800d18fe`
- name: `?SaveDynamicWarningDismissalStates@ShieldProvider@@YAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(ShieldProvider *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010de8`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800cf6f8`
- `0x1800d1744`
- `0x1800d1d40`
- `0x1800dd4ec`
- `0x1800dd908`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d17b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d18e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d17b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d18e1`
- `ole32!CoTaskMemFree` at `0x1800d18ab`
- `ole32!CoTaskMemFree` at `0x1800d18ab`

## string_xrefs

- `0x1800d1767`: `SOFTWARE\Microsoft\Windows Security Health\State\Dynamic`

## pseudocode

```c
__int64 __fastcall ShieldProvider::SaveDynamicWarningDismissalStates(
        ShieldProvider *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 **a4)
{
  int Key; // eax
  unsigned int v5; // ebx
  unsigned int *v7; // r9
  __int64 v8; // rax
  HKEY v9; // rbx
  __int64 v10; // rdi
  bool v11; // zf
  HKEY v12; // r14
  int ValueDword; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r8
  __int64 v17; // rcx
  const void *v18; // [rsp+28h] [rbp-28h]
  _BYTE v19[16]; // [rsp+30h] [rbp-20h] BYREF
  char v20; // [rsp+40h] [rbp-10h]
  HKEY hKey; // [rsp+70h] [rbp+20h] BYREF
  char v22; // [rsp+78h] [rbp+28h] BYREF

  hKey = 0;
  Key = ShieldProvider::ShieldUtilRegCreateKey(
          (ShieldProvider *)&hKey,
          (HKEY *)L"SOFTWARE\\Microsoft\\Windows Security Health\\State\\Dynamic",
          (const unsigned __int16 *)0x2001F,
          a4);
  v5 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids,
        (unsigned int)Key);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v19,
    ShieldProvider::g_aCSwarningStates);
  v8 = ShieldProvider::g_mapDynamicStates;
  v9 = hKey;
  v20 = 1;
  v10 = *(_QWORD *)ShieldProvider::g_mapDynamicStates;
  while ( v10 != v8 )
  {
    v11 = *(_BYTE *)(v10 + 40) == 0;
    v12 = *(HKEY *)(v10 + 32);
    LODWORD(hKey) = 0;
    if ( v11 )
    {
      ValueDword = CommonUtil::UtilRegGetValueDword((CommonUtil *)v9, v12, (const unsigned __int16 *)&hKey, v7);
      if ( ValueDword < 0 )
      {
        if ( ValueDword != -2147024894 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 18;
            goto LABEL_24;
          }
        }
      }
      else
      {
        ValueDword = CommonUtil::UtilRegDeleteValue((CommonUtil *)v9, v12, v16);
        if ( ValueDword < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 17;
            goto LABEL_24;
          }
        }
      }
    }
    else
    {
      ValueDword = CommonUtil::UtilRegSetValueInternal(
                     (CommonUtil *)v9,
                     v12,
                     (const unsigned __int16 *)4,
                     4u,
                     (unsigned __int64)&hKey,
                     v18);
      if ( ValueDword < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 16;
LABEL_24:
          WPP_SF_d(v14[2], v15, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids, (unsigned int)ValueDword);
        }
      }
    }
    CoTaskMemFree(*(LPVOID *)(v10 + 32));
    v10 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned short *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<unsigned short * const,bool>>,0>>::erase(
                       v17,
                       &v22,
                       v10);
    v8 = ShieldProvider::g_mapDynamicStates;
  }
  v20 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
  if ( v9 )
    RegCloseKey(v9);
  return 0;
}

```

## disassembly

```asm
0x1800d1744  mov     [rsp-18h+arg_10], rbx
0x1800d1749  mov     [rsp-18h+arg_18], rsi
0x1800d174e  push    rbp
0x1800d174f  push    rdi
0x1800d1750  push    r14
0x1800d1752  mov     rbp, rsp
0x1800d1755  sub     rsp, 50h
0x1800d1759  mov     r8d, 2001Fh; unsigned __int16 *
0x1800d175f  mov     [rbp+hKey], 0
0x1800d1767  lea     rdx, aSoftwareMicros_21; "SOFTWARE\\Microsoft\\Windows Security H"...
0x1800d176e  lea     rcx, [rbp+hKey]; this
0x1800d1772  call    ?ShieldUtilRegCreateKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegCreateKey(HKEY__ * *,ushort const *,ulong)
0x1800d1777  mov     ebx, eax
0x1800d1779  test    eax, eax
0x1800d177b  jns     short loc_1800D17C4
0x1800d177d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1784  lea     rsi, WPP_GLOBAL_Control
0x1800d178b  cmp     rcx, rsi
0x1800d178e  jz      short loc_1800D17AE
0x1800d1790  test    byte ptr [rcx+1Ch], 1
0x1800d1794  jz      short loc_1800D17AE
0x1800d1796  mov     rcx, [rcx+10h]
0x1800d179a  lea     r8, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids
0x1800d17a1  mov     edx, 0Fh
0x1800d17a6  mov     r9d, eax
0x1800d17a9  call    WPP_SF_d
0x1800d17ae  mov     rcx, [rbp+hKey]; hKey
0x1800d17b2  test    rcx, rcx
0x1800d17b5  jz      short loc_1800D17BD
0x1800d17b7  call    cs:__imp_RegCloseKey
0x1800d17bd  mov     eax, ebx
0x1800d17bf  jmp     loc_1800D18E9
0x1800d17c4  lea     rdx, ?g_aCSwarningStates@ShieldProvider@@3U?$CSimpleGlobalAtStartup2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@A; CommonUtil::CSimpleGlobalAtStartup2nd<CommonUtil::CMpCriticalSection> ShieldProvider::g_aCSwarningStates
0x1800d17cb  lea     rcx, [rbp+var_20]
0x1800d17cf  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800d17d4  mov     rax, cs:?g_mapDynamicStates@ShieldProvider@@3V?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@A; CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>> ShieldProvider::g_mapDynamicStates
0x1800d17db  lea     rsi, WPP_GLOBAL_Control
0x1800d17e2  mov     rbx, [rbp+hKey]
0x1800d17e6  mov     [rbp+var_10], 1
0x1800d17ea  mov     rdi, [rax]
0x1800d17ed  cmp     rdi, rax
0x1800d17f0  jz      loc_1800D18CC
0x1800d17f6  cmp     byte ptr [rdi+28h], 0
0x1800d17fa  mov     rcx, rbx; this
0x1800d17fd  mov     r14, [rdi+20h]
0x1800d1801  mov     rdx, r14; HKEY
0x1800d1804  mov     dword ptr [rbp+hKey], 0
0x1800d180b  jz      short loc_1800D1841
0x1800d180d  mov     r9d, 4; unsigned int
0x1800d1813  lea     rax, [rbp+hKey]
0x1800d1817  mov     r8d, r9d; unsigned __int16 *
0x1800d181a  mov     [rsp+50h+var_30], rax; unsigned __int64
0x1800d181f  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800d1824  test    eax, eax
0x1800d1826  jns     short loc_1800D18A7
0x1800d1828  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d182f  cmp     rcx, rsi
0x1800d1832  jz      short loc_1800D18A7
0x1800d1834  test    byte ptr [rcx+1Ch], 1
0x1800d1838  jz      short loc_1800D18A7
0x1800d183a  mov     edx, 10h
0x1800d183f  jmp     short loc_1800D1894
0x1800d1841  lea     r8, [rbp+hKey]; unsigned __int16 *
0x1800d1845  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800d184a  test    eax, eax
0x1800d184c  js      short loc_1800D1876
0x1800d184e  mov     rdx, r14; HKEY
0x1800d1851  mov     rcx, rbx; this
0x1800d1854  call    ?UtilRegDeleteValue@CommonUtil@@YAJPEAUHKEY__@@PEBG@Z; CommonUtil::UtilRegDeleteValue(HKEY__ *,ushort const *)
0x1800d1859  test    eax, eax
0x1800d185b  jns     short loc_1800D18A7
0x1800d185d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1864  cmp     rcx, rsi
0x1800d1867  jz      short loc_1800D18A7
0x1800d1869  test    byte ptr [rcx+1Ch], 1
0x1800d186d  jz      short loc_1800D18A7
0x1800d186f  mov     edx, 11h
0x1800d1874  jmp     short loc_1800D1894
0x1800d1876  cmp     eax, 80070002h
0x1800d187b  jz      short loc_1800D18A7
0x1800d187d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1884  cmp     rcx, rsi
0x1800d1887  jz      short loc_1800D18A7
0x1800d1889  test    byte ptr [rcx+1Ch], 1
0x1800d188d  jz      short loc_1800D18A7
0x1800d188f  mov     edx, 12h
0x1800d1894  mov     rcx, [rcx+10h]
0x1800d1898  lea     r8, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids
0x1800d189f  mov     r9d, eax
0x1800d18a2  call    WPP_SF_d
0x1800d18a7  mov     rcx, [rdi+20h]; pv
0x1800d18ab  call    cs:__imp_CoTaskMemFree
0x1800d18b1  mov     r8, rdi
0x1800d18b4  lea     rdx, [rbp+arg_8]
0x1800d18b8  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAG_N@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAG_N@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,bool>>>>)
0x1800d18bd  mov     rdi, [rax]
0x1800d18c0  mov     rax, cs:?g_mapDynamicStates@ShieldProvider@@3V?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@A; CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>> ShieldProvider::g_mapDynamicStates
0x1800d18c7  jmp     loc_1800D17ED
0x1800d18cc  lea     rcx, [rbp+var_20]
0x1800d18d0  mov     [rbp+var_10], 0
0x1800d18d4  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800d18d9  test    rbx, rbx
0x1800d18dc  jz      short loc_1800D18E7
0x1800d18de  mov     rcx, rbx; hKey
0x1800d18e1  call    cs:__imp_RegCloseKey
0x1800d18e7  xor     eax, eax
0x1800d18e9  lea     r11, [rsp+50h+var_s0]
0x1800d18ee  mov     rbx, [r11+30h]
0x1800d18f2  mov     rsi, [r11+38h]
0x1800d18f6  mov     rsp, r11
0x1800d18f9  pop     r14
0x1800d18fb  pop     rdi
0x1800d18fc  pop     rbp
0x1800d18fd  retn
```
