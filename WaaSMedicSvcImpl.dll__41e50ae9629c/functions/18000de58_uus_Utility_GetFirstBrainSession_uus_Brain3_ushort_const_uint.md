# uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)

- ea: `0x18000de58`
- end: `0x18000e097`
- name: `??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z`
- size: `575`
- prototype: ``
- caller_count: `8`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180017a60`
- `0x1800184b0`
- `0x18001ecdc`
- `0x1800487ec`
- `0x180055a10`
- `0x18005f600`
- `0x18005fa20`
- `0x180067bb0`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000db20`
- `0x18000dd4c`
- `0x18000de58`
- `0x18000e0a0`
- `0x180010db4`
- `0x180010e54`
- `0x1800112bc`
- `0x18001341c`
- `0x18001cd34`
- `0x18001d3ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000defa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000defa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df87`

## string_xrefs

- `0x18000e030`: `uusbrain.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall uus::Utility::GetFirstBrainSession<uus::Brain3>(__int64 a1, int a2)
{
  __int64 v2; // r8
  __int128 *v4; // rcx
  __int64 v5; // r8
  const unsigned __int16 *v6; // r8
  std::filesystem *v7; // rcx
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // r11
  const unsigned __int16 *v12; // r8
  unsigned __int64 v13; // rdx
  std::filesystem **v14; // rcx
  __int64 v15; // rbx
  LPVOID pv[3]; // [rsp+20h] [rbp-69h] BYREF
  int v17; // [rsp+38h] [rbp-51h]
  int v18; // [rsp+3Ch] [rbp-4Dh]
  struct HINSTANCE__ *v19; // [rsp+40h] [rbp-49h]
  __int64 v20; // [rsp+48h] [rbp-41h]
  _BYTE v21[32]; // [rsp+50h] [rbp-39h] BYREF
  char v22; // [rsp+70h] [rbp-19h]
  std::filesystem *v23[2]; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp-1h]
  unsigned __int64 v25; // [rsp+90h] [rbp+7h]
  __int128 v26; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+A8h] [rbp+1Fh]
  __int64 v28; // [rsp+B0h] [rbp+27h]
  _OWORD Src[2]; // [rsp+B8h] [rbp+2Fh] BYREF

  pv[2] = (LPVOID)32;
  v17 = 3;
  v18 = a2;
  v19 = &_ImageBase;
  v20 = a1;
  Src[0] = 0;
  Src[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  if ( (a2 & 8) != 0 )
  {
    wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(pv);
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)pv[0] + v5) );
    *(_OWORD *)v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v23, pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    v7 = (std::filesystem *)v23;
    if ( v25 > 7 )
      v7 = v23[0];
    for ( i = std::filesystem::_Find_root_name_end(v7, (const unsigned __int16 *const)v7 + v24, v6);
          i != v9 && (*i == 92 || *i == 47);
          ++i )
    {
      ;
    }
    if ( i != v9 )
    {
      do
      {
        v12 = v9 - 1;
        if ( *(v9 - 1) == 92 )
          break;
        if ( *v12 == 47 )
          break;
        --v9;
      }
      while ( i != v12 );
    }
    v13 = ((__int64)v9 - v10) >> 1;
    if ( v11 < v13 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    v24 = v13;
    v14 = v23;
    if ( v25 > 7 )
      v14 = (std::filesystem **)v23[0];
    *((_WORD *)v14 + v13) = 0;
    std::wstring::operator=(Src, v23);
    std::wstring::~wstring(v23);
    v26 = 0;
    v27 = 0;
    v28 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v26, L"uusbrain.dll", 12);
    std::filesystem::path::operator/=(Src, (std::filesystem *)&v26);
    v4 = &v26;
    goto LABEL_29;
  }
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
  v2 = -1;
  do
    ++v2;
  while ( *((_WORD *)pv[0] + v2) );
  v26 = 0;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v26, pv[0]);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(v21, &v26);
  std::wstring::~wstring(&v26);
  if ( !v22 )
  {
    std::wstring::~wstring(Src);
    return 0;
  }
  std::wstring::operator=(Src, v21);
  if ( v22 )
  {
    v4 = (__int128 *)v21;
LABEL_29:
    std::wstring::~wstring(v4);
  }
  v15 = uus::Utility::GetBrainSession<uus::Brain3>((char *)Src);
  std::wstring::~wstring(Src);
  return v15;
}

```

## disassembly

```asm
0x18000de58  mov     [rsp-8+arg_10], rbx
0x18000de5d  push    rbp
0x18000de5e  lea     rbp, [rsp-57h]
0x18000de63  sub     rsp, 0E0h
0x18000de6a  mov     rax, cs:__security_cookie
0x18000de71  xor     rax, rsp
0x18000de74  mov     [rbp+57h+var_8], rax
0x18000de78  xor     ebx, ebx
0x18000de7a  mov     [rbp+57h+var_B0], 20h ; ' '
0x18000de82  mov     [rbp+57h+var_A8], 3
0x18000de89  mov     [rbp+57h+var_A4], edx
0x18000de8c  lea     r8, __ImageBase
0x18000de93  mov     [rbp+57h+var_A0], r8
0x18000de97  mov     [rbp+57h+var_98], rcx
0x18000de9b  and     edx, 8
0x18000de9e  xorps   xmm0, xmm0
0x18000dea1  movups  [rbp+57h+Src], xmm0
0x18000dea5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000dead  movdqu  [rbp+57h+var_18], xmm1
0x18000deb2  mov     word ptr [rbp+57h+Src], bx
0x18000deb6  lea     rcx, [rbp+57h+pv]
0x18000deba  jnz     loc_18000DF4D
0x18000dec0  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18000dec5  nop
0x18000dec6  mov     rdx, [rbp+57h+pv]
0x18000deca  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000dece  inc     r8
0x18000ded1  cmp     [rdx+r8*2], bx
0x18000ded6  jnz     short loc_18000DECE
0x18000ded8  xorps   xmm0, xmm0
0x18000dedb  movups  [rbp+57h+var_48], xmm0
0x18000dedf  mov     [rbp+57h+var_38], rbx
0x18000dee3  mov     [rbp+57h+var_30], rbx
0x18000dee7  lea     rcx, [rbp+57h+var_48]
0x18000deeb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000def0  nop
0x18000def1  mov     rcx, [rbp+57h+pv]; pv
0x18000def5  test    rcx, rcx
0x18000def8  jz      short loc_18000DF01
0x18000defa  call    cs:__imp_CoTaskMemFree
0x18000df00  nop
0x18000df01  lea     rdx, [rbp+57h+var_48]
0x18000df05  lea     rcx, [rbp+57h+var_90]
0x18000df09  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x18000df0e  nop
0x18000df0f  lea     rcx, [rbp+57h+var_48]; void *
0x18000df13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df18  cmp     [rbp+57h+var_70], bl
0x18000df1b  jnz     short loc_18000DF2D
0x18000df1d  lea     rcx, [rbp+57h+Src]; void *
0x18000df21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000df26  xor     eax, eax
0x18000df28  jmp     loc_18000E074
0x18000df2d  lea     rdx, [rbp+57h+var_90]
0x18000df31  lea     rcx, [rbp+57h+Src]
0x18000df35  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000df3a  nop
0x18000df3b  cmp     [rbp+57h+var_70], bl
0x18000df3e  jz      loc_18000E058
0x18000df44  lea     rcx, [rbp+57h+var_90]
0x18000df48  jmp     loc_18000E053
0x18000df4d  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18000df52  nop
0x18000df53  mov     rdx, [rbp+57h+pv]
0x18000df57  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000df5b  inc     r8
0x18000df5e  cmp     [rdx+r8*2], bx
0x18000df63  jnz     short loc_18000DF5B
0x18000df65  xorps   xmm0, xmm0
0x18000df68  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18000df6c  mov     [rbp+57h+var_58], rbx
0x18000df70  mov     [rbp+57h+var_50], rbx
0x18000df74  lea     rcx, [rbp+57h+var_68]
0x18000df78  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000df7d  nop
0x18000df7e  mov     rcx, [rbp+57h+pv]; pv
0x18000df82  test    rcx, rcx
0x18000df85  jz      short loc_18000DF8E
0x18000df87  call    cs:__imp_CoTaskMemFree
0x18000df8d  nop
0x18000df8e  lea     rcx, [rbp+57h+var_68]
0x18000df92  cmp     [rbp+57h+var_50], 7
0x18000df97  cmova   rcx, [rbp+57h+var_68]; this
0x18000df9c  mov     r11, [rbp+57h+var_58]
0x18000dfa0  lea     rdx, [rcx+r11*2]; unsigned __int16 *
0x18000dfa4  call    ?_Find_root_name_end@filesystem@std@@YAPEBGQEBG0@Z; std::filesystem::_Find_root_name_end(ushort const * const,ushort const * const)
0x18000dfa9  jmp     short loc_18000DFBB
0x18000dfab  cmp     word ptr [rax], 5Ch ; '\'
0x18000dfaf  jz      short loc_18000DFB7
0x18000dfb1  cmp     word ptr [rax], 2Fh ; '/'
0x18000dfb5  jnz     short loc_18000DFC0
0x18000dfb7  add     rax, 2
0x18000dfbb  cmp     rax, rdx
0x18000dfbe  jnz     short loc_18000DFAB
0x18000dfc0  cmp     rax, rdx
0x18000dfc3  jz      short loc_18000DFDF
0x18000dfc5  lea     r8, [rdx-2]
0x18000dfc9  cmp     word ptr [r8], 5Ch ; '\'
0x18000dfce  jz      short loc_18000DFDF
0x18000dfd0  cmp     word ptr [r8], 2Fh ; '/'
0x18000dfd5  jz      short loc_18000DFDF
0x18000dfd7  mov     rdx, r8
0x18000dfda  cmp     rax, r8
0x18000dfdd  jnz     short loc_18000DFC5
0x18000dfdf  sub     rdx, rcx
0x18000dfe2  sar     rdx, 1
0x18000dfe5  cmp     r11, rdx
0x18000dfe8  jb      loc_18000E091
0x18000dfee  mov     [rbp+57h+var_58], rdx
0x18000dff2  lea     rcx, [rbp+57h+var_68]
0x18000dff6  cmp     [rbp+57h+var_50], 7
0x18000dffb  cmova   rcx, [rbp+57h+var_68]
0x18000e000  mov     [rcx+rdx*2], bx
0x18000e004  lea     rdx, [rbp+57h+var_68]
0x18000e008  lea     rcx, [rbp+57h+Src]
0x18000e00c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000e011  nop
0x18000e012  lea     rcx, [rbp+57h+var_68]; void *
0x18000e016  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e01b  xorps   xmm0, xmm0
0x18000e01e  movups  [rbp+57h+var_48], xmm0
0x18000e022  mov     [rbp+57h+var_38], rbx
0x18000e026  mov     [rbp+57h+var_30], rbx
0x18000e02a  mov     r8d, 0Ch
0x18000e030  lea     rdx, aUusbrainDll; "uusbrain.dll"
0x18000e037  lea     rcx, [rbp+57h+var_48]
0x18000e03b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e040  nop
0x18000e041  lea     rdx, [rbp+57h+var_48]; this
0x18000e045  lea     rcx, [rbp+57h+Src]; Src
0x18000e049  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000e04e  nop
0x18000e04f  lea     rcx, [rbp+57h+var_48]; void *
0x18000e053  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e058  lea     rdx, [rbp+57h+var_B0]
0x18000e05c  lea     rcx, [rbp+57h+Src]
0x18000e060  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x18000e065  mov     rbx, rax
0x18000e068  lea     rcx, [rbp+57h+Src]; void *
0x18000e06c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e071  mov     rax, rbx
0x18000e074  mov     rcx, [rbp+57h+var_8]
0x18000e078  xor     rcx, rsp; StackCookie
0x18000e07b  call    __security_check_cookie
0x18000e080  mov     rbx, [rsp+0E0h+arg_10]
0x18000e088  add     rsp, 0E0h
0x18000e08f  pop     rbp
0x18000e090  retn
0x18000e091  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
