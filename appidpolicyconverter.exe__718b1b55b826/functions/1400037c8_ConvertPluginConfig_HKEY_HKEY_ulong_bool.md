# ConvertPluginConfig(HKEY__ *,HKEY__ *,ulong &,bool *)

- ea: `0x1400037c8`
- end: `0x140003bb7`
- name: `?ConvertPluginConfig@@YAKPEAUHKEY__@@0AEAKPEA_N@Z`
- size: `1007`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14000458c`

## callees

- `0x14000157c`
- `0x1400024d4`
- `0x1400037c8`
- `0x140006154`
- `0x140006880`

## import_xrefs

- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400038d4`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x14000390d`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003940`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003979`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400039ea`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a23`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a56`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a8f`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003ad0`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b09`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b3c`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b75`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400038d4`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x14000390d`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003940`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003979`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x1400039ea`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a23`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a56`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003a8f`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003ad0`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b09`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b3c`
- `msvcp110_win!?_Orphan_all@_Container_base0@std@@QEAAXXZ` at `0x140003b75`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000384d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000384d`

## pseudocode

```c
__int64 __fastcall ConvertPluginConfig(HKEY hKey, HKEY a2, unsigned int *a3, bool *a4)
{
  LSTATUS v7; // eax
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  bool v13; // al
  __int64 v14; // rcx
  __int64 v15; // rcx
  void *Block[2]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v17; // [rsp+70h] [rbp-78h]
  void *v18[2]; // [rsp+78h] [rbp-70h] BYREF
  __int64 v19; // [rsp+88h] [rbp-60h]
  void *v20[2]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-48h]
  void *v22[2]; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp-30h]
  __int64 (__usercall *v24)@<rax>(HKEY@<rcx>, __int64, __int64, __int64); // [rsp+C0h] [rbp-28h]
  DWORD lpcSubKeys; // [rsp+F8h] [rbp+10h] BYREF
  int v26; // [rsp+FCh] [rbp+14h]

  v26 = HIDWORD(a2);
  lpcSubKeys = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  *(_OWORD *)Block = 0;
  v17 = 0;
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &lpcSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v8 = v7;
  if ( !v7 )
  {
    if ( !lpcSubKeys )
      goto LABEL_25;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v24 = (__int64 (__usercall *)@<rax>(HKEY@<rcx>, __int64, __int64, __int64))ConvertOnePlugin;
      v9 = ForEachSubKeyCount<unsigned long (*)(HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>> &,unsigned long &),std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>> &,unsigned long &>(
             hKey,
             (__int64)v20,
             (__int64)v18,
             (__int64)Block,
             (__int64)a3);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400039DC);
        if ( Block[0] )
        {
          std::_Container_base0::_Orphan_all((std::_Container_base0 *)Block);
          std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(
            v14,
            Block[0],
            Block[1]);
          operator delete(Block[0]);
          *(_OWORD *)Block = 0;
          v17 = 0;
        }
        if ( v18[0] )
        {
          std::_Container_base0::_Orphan_all((std::_Container_base0 *)v18);
          operator delete(v18[0]);
          *(_OWORD *)v18 = 0;
          v19 = 0;
        }
        if ( v20[0] )
        {
          std::_Container_base0::_Orphan_all((std::_Container_base0 *)v20);
          operator delete(v20[0]);
          *(_OWORD *)v20 = 0;
          v21 = 0;
        }
        if ( v22[0] )
        {
          std::_Container_base0::_Orphan_all((std::_Container_base0 *)v22);
          operator delete(v22[0]);
          *(_OWORD *)v22 = 0;
          v23 = 0;
        }
        return 14;
      }
    }
    v10 = v9;
    if ( v9 )
    {
      if ( Block[0] )
      {
        std::_Container_base0::_Orphan_all((std::_Container_base0 *)Block);
        std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(
          v11,
          Block[0],
          Block[1]);
        operator delete(Block[0]);
        *(_OWORD *)Block = 0;
        v17 = 0;
      }
      if ( v18[0] )
      {
        std::_Container_base0::_Orphan_all((std::_Container_base0 *)v18);
        operator delete(v18[0]);
        *(_OWORD *)v18 = 0;
        v19 = 0;
      }
      if ( v20[0] )
      {
        std::_Container_base0::_Orphan_all((std::_Container_base0 *)v20);
        operator delete(v20[0]);
        *(_OWORD *)v20 = 0;
        v21 = 0;
      }
      if ( v22[0] )
      {
        std::_Container_base0::_Orphan_all((std::_Container_base0 *)v22);
        operator delete(v22[0]);
        *(_OWORD *)v22 = 0;
        v23 = 0;
      }
      return v10;
    }
    v8 = WritePlugin((const void **)v22, (__int64)v20, (__int64)v18, Block);
    if ( lpcSubKeys )
      v13 = 1;
    else
LABEL_25:
      v13 = 0;
    *a4 = v13;
  }
  if ( Block[0] )
  {
    std::_Container_base0::_Orphan_all((std::_Container_base0 *)Block);
    std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::_Destroy(
      v15,
      Block[0],
      Block[1]);
    operator delete(Block[0]);
    *(_OWORD *)Block = 0;
    v17 = 0;
  }
  if ( v18[0] )
  {
    std::_Container_base0::_Orphan_all((std::_Container_base0 *)v18);
    operator delete(v18[0]);
    *(_OWORD *)v18 = 0;
    v19 = 0;
  }
  if ( v20[0] )
  {
    std::_Container_base0::_Orphan_all((std::_Container_base0 *)v20);
    operator delete(v20[0]);
    *(_OWORD *)v20 = 0;
    v21 = 0;
  }
  if ( v22[0] )
  {
    std::_Container_base0::_Orphan_all((std::_Container_base0 *)v22);
    operator delete(v22[0]);
    *(_OWORD *)v22 = 0;
    v23 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1400037c8  mov     rax, rsp
0x1400037cb  mov     [rax+8], rbx
0x1400037cf  mov     [rax+18h], rsi
0x1400037d3  mov     [rax+10h], rdx
0x1400037d7  push    rdi
0x1400037d8  push    r14
0x1400037da  push    r15
0x1400037dc  sub     rsp, 0D0h
0x1400037e3  mov     rsi, r9
0x1400037e6  mov     r15, r8
0x1400037e9  mov     r14, rcx
0x1400037ec  xor     ebx, ebx
0x1400037ee  mov     [rax+10h], ebx
0x1400037f1  xorps   xmm0, xmm0
0x1400037f4  movdqu  xmmword ptr [rax-40h], xmm0
0x1400037f9  mov     [rax-30h], rbx
0x1400037fd  movdqu  xmmword ptr [rax-58h], xmm0
0x140003802  mov     [rax-48h], rbx
0x140003806  movdqu  xmmword ptr [rax-70h], xmm0
0x14000380b  mov     [rax-60h], rbx
0x14000380f  movdqu  xmmword ptr [rsp+0E8h+Block], xmm0
0x140003815  mov     [rax-78h], rbx
0x140003819  mov     [rsp+0E8h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x14000381e  mov     [rsp+0E8h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x140003823  mov     [rsp+0E8h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x140003828  mov     [rsp+0E8h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x14000382d  mov     [rsp+0E8h+lpcValues], rbx; lpcValues
0x140003832  mov     [rsp+0E8h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x140003837  mov     [rsp+0E8h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x14000383c  lea     rax, [rax+10h]
0x140003840  mov     [rsp+0E8h+lpcSubKeys], rax; lpcSubKeys
0x140003845  xor     r9d, r9d; lpReserved
0x140003848  xor     r8d, r8d; lpcchClass
0x14000384b  xor     edx, edx; lpClass
0x14000384d  call    cs:__imp_RegQueryInfoKeyW
0x140003853  mov     edi, eax
0x140003855  test    eax, eax
0x140003857  jnz     loc_140003AC4
0x14000385d  cmp     [rsp+0E8h+arg_8], ebx
0x140003864  jbe     loc_140003AC0
0x14000386a  lea     rax, ?ConvertOnePlugin@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@3@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@3@AEAK@Z; ConvertOnePlugin(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> &,ulong &)
0x140003871  mov     [rsp+0E8h+var_28], rax
0x140003879  mov     [rsp+0E8h+lpcValues], r15; __int64
0x14000387e  lea     rax, [rsp+0E8h+Block]
0x140003883  mov     [rsp+0E8h+lpcbMaxClassLen], rax; __int64
0x140003888  lea     rax, [rsp+0E8h+var_70]
0x14000388d  mov     [rsp+0E8h+lpcbMaxSubKeyLen], rax; __int64
0x140003892  lea     rax, [rsp+0E8h+var_58]
0x14000389a  mov     [rsp+0E8h+lpcSubKeys], rax; __int64
0x14000389f  lea     r9, [rsp+0E8h+var_40]
0x1400038a7  lea     r8, [rsp+0E8h+var_28]
0x1400038af  mov     edx, [rsp+0E8h+arg_8]
0x1400038b6  mov     rcx, r14; hKey
0x1400038b9  call    ??$ForEachSubKeyCount@P6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@3@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@3@AEAK@ZAEAV43@AEAV53@AEAV63@AEAV73@AEAK@@YAKPEAUHKEY__@@KAEBQ6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@2@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@2@AEAK@Z23456@Z; ForEachSubKeyCount<ulong (*)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> &,ulong &),std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> &,ulong &>(HKEY__ *,ulong,ulong (*const &)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> &,ulong &),std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> &,ulong &)
0x1400038be  mov     edi, eax
0x1400038c0  test    eax, eax
0x1400038c2  jz      loc_1400039A7
0x1400038c8  cmp     [rsp+0E8h+Block], rbx
0x1400038cd  jz      short loc_140003901
0x1400038cf  lea     rcx, [rsp+0E8h+Block]
0x1400038d4  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x1400038da  mov     r8, [rsp+0E8h+Block+8]
0x1400038df  mov     rdx, [rsp+0E8h+Block]
0x1400038e4  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)
0x1400038e9  mov     rcx, [rsp+0E8h+Block]; Block
0x1400038ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400038f3  xorps   xmm0, xmm0
0x1400038f6  movdqu  xmmword ptr [rsp+0E8h+Block], xmm0
0x1400038fc  mov     [rsp+0E8h+var_78], rbx
0x140003901  cmp     [rsp+0E8h+var_70], rbx
0x140003906  jz      short loc_14000392E
0x140003908  lea     rcx, [rsp+0E8h+var_70]
0x14000390d  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003913  mov     rcx, [rsp+0E8h+var_70]; Block
0x140003918  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000391d  xorps   xmm0, xmm0
0x140003920  movdqu  xmmword ptr [rsp+0E8h+var_70], xmm0
0x140003926  mov     [rsp+0E8h+var_60], rbx
0x14000392e  cmp     [rsp+0E8h+var_58], rbx
0x140003936  jz      short loc_140003967
0x140003938  lea     rcx, [rsp+0E8h+var_58]
0x140003940  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003946  mov     rcx, [rsp+0E8h+var_58]; Block
0x14000394e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003953  xorps   xmm0, xmm0
0x140003956  movdqu  xmmword ptr [rsp+0E8h+var_58], xmm0
0x14000395f  mov     [rsp+0E8h+var_48], rbx
0x140003967  cmp     [rsp+0E8h+var_40], rbx
0x14000396f  jz      short loc_1400039A0
0x140003971  lea     rcx, [rsp+0E8h+var_40]
0x140003979  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x14000397f  mov     rcx, [rsp+0E8h+var_40]; Block
0x140003987  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000398c  xorps   xmm0, xmm0
0x14000398f  movdqu  xmmword ptr [rsp+0E8h+var_40], xmm0
0x140003998  mov     [rsp+0E8h+var_30], rbx
0x1400039a0  mov     eax, edi
0x1400039a2  jmp     loc_140003B9E
0x1400039a7  lea     r9, [rsp+0E8h+Block]
0x1400039ac  lea     r8, [rsp+0E8h+var_70]
0x1400039b1  lea     rdx, [rsp+0E8h+var_58]
0x1400039b9  lea     rcx, [rsp+0E8h+var_40]
0x1400039c1  call    ?WritePlugin@@YAKAEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@AEBV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEBV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@2@@Z; WritePlugin(std::vector<APPID_PLUGIN_> &,std::vector<APPID_EXECUTION_CATEGORY_> const &,std::vector<_GUID> const &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>> const &)
0x1400039c6  mov     edi, eax
0x1400039c8  cmp     [rsp+0E8h+arg_8], ebx
0x1400039cf  jbe     loc_140003AC0
0x1400039d5  mov     al, 1
0x1400039d7  jmp     loc_140003AC2
0x1400039dc  xor     ebx, ebx
0x1400039de  cmp     [rsp+0E8h+Block], rbx
0x1400039e3  jz      short loc_140003A17
0x1400039e5  lea     rcx, [rsp+0E8h+Block]
0x1400039ea  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x1400039f0  mov     r8, [rsp+0E8h+Block+8]
0x1400039f5  mov     rdx, [rsp+0E8h+Block]
0x1400039fa  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)
0x1400039ff  mov     rcx, [rsp+0E8h+Block]; Block
0x140003a04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003a09  xorps   xmm0, xmm0
0x140003a0c  movdqu  xmmword ptr [rsp+0E8h+Block], xmm0
0x140003a12  mov     [rsp+0E8h+var_78], rbx
0x140003a17  cmp     [rsp+0E8h+var_70], rbx
0x140003a1c  jz      short loc_140003A44
0x140003a1e  lea     rcx, [rsp+0E8h+var_70]
0x140003a23  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003a29  mov     rcx, [rsp+0E8h+var_70]; Block
0x140003a2e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003a33  xorps   xmm0, xmm0
0x140003a36  movdqu  xmmword ptr [rsp+0E8h+var_70], xmm0
0x140003a3c  mov     [rsp+0E8h+var_60], rbx
0x140003a44  cmp     [rsp+0E8h+var_58], rbx
0x140003a4c  jz      short loc_140003A7D
0x140003a4e  lea     rcx, [rsp+0E8h+var_58]
0x140003a56  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003a5c  mov     rcx, [rsp+0E8h+var_58]; Block
0x140003a64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003a69  xorps   xmm0, xmm0
0x140003a6c  movdqu  xmmword ptr [rsp+0E8h+var_58], xmm0
0x140003a75  mov     [rsp+0E8h+var_48], rbx
0x140003a7d  cmp     [rsp+0E8h+var_40], rbx
0x140003a85  jz      short loc_140003AB6
0x140003a87  lea     rcx, [rsp+0E8h+var_40]
0x140003a8f  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003a95  mov     rcx, [rsp+0E8h+var_40]; Block
0x140003a9d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003aa2  xorps   xmm0, xmm0
0x140003aa5  movdqu  xmmword ptr [rsp+0E8h+var_40], xmm0
0x140003aae  mov     [rsp+0E8h+var_30], rbx
0x140003ab6  mov     eax, 0Eh
0x140003abb  jmp     loc_140003B9E
0x140003ac0  mov     al, bl
0x140003ac2  mov     [rsi], al
0x140003ac4  cmp     [rsp+0E8h+Block], rbx
0x140003ac9  jz      short loc_140003AFD
0x140003acb  lea     rcx, [rsp+0E8h+Block]
0x140003ad0  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003ad6  mov     r8, [rsp+0E8h+Block+8]
0x140003adb  mov     rdx, [rsp+0E8h+Block]
0x140003ae0  call    ?_Destroy@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@0@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::_Destroy(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> *)
0x140003ae5  mov     rcx, [rsp+0E8h+Block]; Block
0x140003aea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003aef  xorps   xmm0, xmm0
0x140003af2  movdqu  xmmword ptr [rsp+0E8h+Block], xmm0
0x140003af8  mov     [rsp+0E8h+var_78], rbx
0x140003afd  cmp     [rsp+0E8h+var_70], rbx
0x140003b02  jz      short loc_140003B2A
0x140003b04  lea     rcx, [rsp+0E8h+var_70]
0x140003b09  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003b0f  mov     rcx, [rsp+0E8h+var_70]; Block
0x140003b14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003b19  xorps   xmm0, xmm0
0x140003b1c  movdqu  xmmword ptr [rsp+0E8h+var_70], xmm0
0x140003b22  mov     [rsp+0E8h+var_60], rbx
0x140003b2a  cmp     [rsp+0E8h+var_58], rbx
0x140003b32  jz      short loc_140003B63
0x140003b34  lea     rcx, [rsp+0E8h+var_58]
0x140003b3c  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003b42  mov     rcx, [rsp+0E8h+var_58]; Block
0x140003b4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003b4f  xorps   xmm0, xmm0
0x140003b52  movdqu  xmmword ptr [rsp+0E8h+var_58], xmm0
0x140003b5b  mov     [rsp+0E8h+var_48], rbx
0x140003b63  cmp     [rsp+0E8h+var_40], rbx
0x140003b6b  jz      short loc_140003B9C
0x140003b6d  lea     rcx, [rsp+0E8h+var_40]
0x140003b75  call    cs:__imp_?_Orphan_all@_Container_base0@std@@QEAAXXZ; std::_Container_base0::_Orphan_all(void)
0x140003b7b  mov     rcx, [rsp+0E8h+var_40]; Block
0x140003b83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140003b88  xorps   xmm0, xmm0
0x140003b8b  movdqu  xmmword ptr [rsp+0E8h+var_40], xmm0
0x140003b94  mov     [rsp+0E8h+var_30], rbx
0x140003b9c  mov     eax, edi
0x140003b9e  lea     r11, [rsp+0E8h+var_18]
0x140003ba6  mov     rbx, [r11+20h]
0x140003baa  mov     rsi, [r11+30h]
0x140003bae  mov     rsp, r11
0x140003bb1  pop     r15
0x140003bb3  pop     r14
0x140003bb5  pop     rdi
0x140003bb6  retn
```
