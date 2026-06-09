# ShieldProvider::SetOrRemoveDynamicWarningStateDismissal

- ea: `0x1800d1904`
- end: `0x1800d1a4e`
- name: `ShieldProvider::SetOrRemoveDynamicWarningStateDismissal`
- size: `330`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037568`
- `0x18006df60`
- `0x180076d54`
- `0x1800be7ac`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x1800d1174`
- `0x1800d141c`
- `0x1800d16f4`
- `0x1800d1904`
- `0x1800d1d40`
- `0x1800e1764`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d19b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800d19b3`
- `ole32!CoTaskMemFree` at `0x1800d19d7`
- `ole32!CoTaskMemFree` at `0x1800d19d7`

## pseudocode

```c
__int64 __fastcall ShieldProvider::SetOrRemoveDynamicWarningStateDismissal(
        unsigned __int16 **a1,
        char a2,
        unsigned __int16 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  char i; // al
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  _BYTE v13[8]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v14[24]; // [rsp+28h] [rbp-18h] BYREF
  char v15; // [rsp+58h] [rbp+18h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v15 = a2;
  String2 = 0;
  v3 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&String2, a1, a3);
  v4 = v3;
  if ( v3 >= 0 )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v14,
      ShieldProvider::g_aCSwarningStates);
    for ( i = 1; ; i = 0 )
    {
      v14[16] = i;
      if ( !i )
      {
        v4 = 0;
        goto LABEL_19;
      }
      if ( CommonUtil::CStdMap<unsigned short *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<unsigned short * const,bool>>>::LookupValue(
             v5,
             &String2) )
      {
        v8 = ShieldProvider::g_mapDynamicStates;
        v9 = *(_QWORD *)ShieldProvider::g_mapDynamicStates;
        v17 = *(_QWORD *)ShieldProvider::g_mapDynamicStates;
        while ( v9 != v8 )
        {
          if ( !_wcsicmp(*(const wchar_t **)(v9 + 32), String2) )
          {
            CoTaskMemFree(*(LPVOID *)(v9 + 32));
            std::_Tree<std::_Tmap_traits<unsigned short *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<unsigned short * const,bool>>,0>>::erase(
              v10,
              v13,
              v9);
            break;
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,bool>>>,std::_Iterator_base0>::operator++(&v17);
          v8 = ShieldProvider::g_mapDynamicStates;
          v9 = v17;
        }
      }
      v11 = CommonUtil::HrStdMapInsert<CommonUtil::CStdMap<unsigned short *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<unsigned short * const,bool>>>,bool,unsigned short *>(
              v7,
              &String2,
              &v15);
      v4 = v11;
      if ( v11 < 0 )
        break;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids,
        (unsigned int)v11);
LABEL_19:
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v14);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids, (unsigned int)v3);
  }
  return v4;
}

```

## disassembly

```asm
0x1800d1904  mov     [rsp-8+arg_0], rbx
0x1800d1909  mov     [rsp-8+arg_8], dl
0x1800d190d  push    rbp
0x1800d190e  mov     rbp, rsp
0x1800d1911  sub     rsp, 40h
0x1800d1915  mov     rdx, rcx; unsigned __int16 **
0x1800d1918  mov     [rbp+String2], 0
0x1800d1920  lea     rcx, [rbp+String2]; this
0x1800d1924  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800d1929  mov     ebx, eax
0x1800d192b  test    eax, eax
0x1800d192d  jns     short loc_1800D196D
0x1800d192f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1936  lea     rdx, WPP_GLOBAL_Control
0x1800d193d  cmp     rcx, rdx
0x1800d1940  jz      loc_1800D1A41
0x1800d1946  test    byte ptr [rcx+1Ch], 1
0x1800d194a  jz      loc_1800D1A41
0x1800d1950  mov     rcx, [rcx+10h]
0x1800d1954  lea     r8, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids
0x1800d195b  mov     edx, 13h
0x1800d1960  mov     r9d, eax
0x1800d1963  call    WPP_SF_d
0x1800d1968  jmp     loc_1800D1A41
0x1800d196d  lea     rdx, ?g_aCSwarningStates@ShieldProvider@@3U?$CSimpleGlobalAtStartup2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@A; CommonUtil::CSimpleGlobalAtStartup2nd<CommonUtil::CMpCriticalSection> ShieldProvider::g_aCSwarningStates
0x1800d1974  lea     rcx, [rbp+var_18]
0x1800d1978  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800d197d  mov     al, 1
0x1800d197f  mov     [rbp+var_8], al
0x1800d1982  test    al, al
0x1800d1984  jz      loc_1800D1A36
0x1800d198a  lea     rdx, [rbp+String2]
0x1800d198e  call    ?LookupValue@?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@QEAAPEA_NAEBQEAG@Z; CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>>::LookupValue(ushort * const &)
0x1800d1993  test    rax, rax
0x1800d1996  jz      short loc_1800D19E9
0x1800d1998  mov     rax, cs:?g_mapDynamicStates@ShieldProvider@@3V?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@A; CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>> ShieldProvider::g_mapDynamicStates
0x1800d199f  mov     rbx, [rax]
0x1800d19a2  mov     [rbp+arg_18], rbx
0x1800d19a6  cmp     rbx, rax
0x1800d19a9  jz      short loc_1800D19E9
0x1800d19ab  mov     rdx, [rbp+String2]; String2
0x1800d19af  mov     rcx, [rbx+20h]; String1
0x1800d19b3  call    cs:__imp__wcsicmp
0x1800d19b9  test    eax, eax
0x1800d19bb  jz      short loc_1800D19D3
0x1800d19bd  lea     rcx, [rbp+arg_18]
0x1800d19c1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAG_N@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,bool>>>,std::_Iterator_base0>::operator++(void)
0x1800d19c6  mov     rax, cs:?g_mapDynamicStates@ShieldProvider@@3V?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@A; CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>> ShieldProvider::g_mapDynamicStates
0x1800d19cd  mov     rbx, [rbp+arg_18]
0x1800d19d1  jmp     short loc_1800D19A6
0x1800d19d3  mov     rcx, [rbx+20h]; pv
0x1800d19d7  call    cs:__imp_CoTaskMemFree
0x1800d19dd  mov     r8, rbx
0x1800d19e0  lea     rdx, [rbp+var_20]
0x1800d19e4  call    ?erase@?$_Tree@V?$_Tmap_traits@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAG_N@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAG_N@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,bool>>>>)
0x1800d19e9  lea     r8, [rbp+arg_8]
0x1800d19ed  lea     rdx, [rbp+String2]
0x1800d19f1  call    ??$HrStdMapInsert@V?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@CommonUtil@@_NPEAG@CommonUtil@@YAJAEAV?$CStdMap@PEAG_NUCStdWideStringNoCaseCompareLess@CommonUtil@@V?$allocator@U?$pair@QEAG_N@std@@@std@@@0@AEBQEAGAEB_N@Z; CommonUtil::HrStdMapInsert<CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>>,bool,ushort *>(CommonUtil::CStdMap<ushort *,bool,CommonUtil::CStdWideStringNoCaseCompareLess,std::allocator<std::pair<ushort * const,bool>>> &,ushort * const &,bool const &)
0x1800d19f6  mov     ebx, eax
0x1800d19f8  test    eax, eax
0x1800d19fa  js      short loc_1800D1A03
0x1800d19fc  xor     al, al
0x1800d19fe  jmp     loc_1800D197F
0x1800d1a03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1a0a  lea     rdx, WPP_GLOBAL_Control
0x1800d1a11  cmp     rcx, rdx
0x1800d1a14  jz      short loc_1800D1A38
0x1800d1a16  test    byte ptr [rcx+1Ch], 1
0x1800d1a1a  jz      short loc_1800D1A38
0x1800d1a1c  mov     rcx, [rcx+10h]
0x1800d1a20  lea     r8, WPP_06de2d10d53637a781e094dd7c64d71e_Traceguids
0x1800d1a27  mov     edx, 14h
0x1800d1a2c  mov     r9d, eax
0x1800d1a2f  call    WPP_SF_d
0x1800d1a34  jmp     short loc_1800D1A38
0x1800d1a36  xor     ebx, ebx
0x1800d1a38  lea     rcx, [rbp+var_18]
0x1800d1a3c  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800d1a41  mov     eax, ebx
0x1800d1a43  mov     rbx, [rsp+40h+arg_0]
0x1800d1a48  add     rsp, 40h
0x1800d1a4c  pop     rbp
0x1800d1a4d  retn
```
