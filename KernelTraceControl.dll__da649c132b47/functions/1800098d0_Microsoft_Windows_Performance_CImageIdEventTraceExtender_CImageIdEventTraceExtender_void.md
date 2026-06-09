# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x1800098d0`
- end: `0x180009e69`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1433`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000dc84`

## callees

- `0x18000139c`
- `0x1800056c8`
- `0x1800061c8`
- `0x1800098d0`
- `0x18000c048`
- `0x18000ce70`
- `0x18000d6e0`
- `0x18000d728`
- `0x18000d7e8`
- `0x18000d908`
- `0x18000e4d0`
- `0x18000fcec`
- `0x18000fdb0`
- `0x18000fe94`
- `0x180011024`
- `0x180011120`
- `0x180012df4`
- `0x1800130a8`
- `0x1800268f4`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `msvcrt!free` at `0x180009d59`
- `msvcrt!free` at `0x180009d86`
- `msvcrt!free` at `0x180009d59`
- `msvcrt!free` at `0x180009d86`
- `KERNEL32!GetLastError` at `0x180009da8`
- `KERNEL32!GetLastError` at `0x180009da8`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180009d9e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180009d9e`

## string_xrefs

- `0x180009b65`: `XPERF_EmbeddedPdbPath`
- `0x180009ba2`: `_NT_SYMBOL_PATH`
- `0x180009bde`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // edi
  char *v14; // rdx
  int v15; // eax
  _QWORD *v16; // rdx
  signed int LastError; // eax
  unsigned int v18; // ecx
  unsigned __int64 v19; // rax
  char *v20; // rdx
  volatile signed __int32 *v22; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-D0h] BYREF
  volatile signed __int32 *v25; // [rsp+40h] [rbp-C8h] BYREF
  void *v26[3]; // [rsp+48h] [rbp-C0h] BYREF
  void *v27; // [rsp+60h] [rbp-A8h]
  void *v28; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-88h]
  int v32; // [rsp+88h] [rbp-80h]
  __int64 v33; // [rsp+90h] [rbp-78h]
  int v34; // [rsp+98h] [rbp-70h] BYREF
  void *v35; // [rsp+A0h] [rbp-68h]
  __int64 v36; // [rsp+A8h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-58h]
  int v38; // [rsp+B8h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-48h]
  int v40; // [rsp+C8h] [rbp-40h]
  __int64 v41; // [rsp+D0h] [rbp-38h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v42; // [rsp+D8h] [rbp-30h]
  __int64 v43; // [rsp+E0h] [rbp-28h]
  __int64 v44; // [rsp+E8h] [rbp-20h]
  __int64 v45; // [rsp+F0h] [rbp-18h]
  WCHAR Buffer[264]; // [rsp+F8h] [rbp-10h] BYREF

  v41 = -2;
  v42 = this;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventTraceExtenderBase::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable';
  *((_DWORD *)this + 8) = 0;
  v43 = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  v25 = (volatile signed __int32 *)((char *)this + 64);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 20) = 7;
  *((_QWORD *)this + 19) = 0;
  *((_WORD *)this + 68) = 0;
  *((_QWORD *)this + 25) = 7;
  *((_QWORD *)this + 24) = 0;
  *((_WORD *)this + 88) = 0;
  *((_BYTE *)this + 208) = 0;
  *((_QWORD *)this + 27) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_WORD *)this + 112) = 0;
  v2 = (_QWORD *)((char *)this + 232);
  v25 = (volatile signed __int32 *)((char *)this + 232);
  *((_QWORD *)this + 30) = std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode();
  *((_QWORD *)this + 31) = 0;
  v22 = (volatile signed __int32 *)((char *)this + 256);
  v4 = std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(v3);
  *((_QWORD *)this + 33) = v4;
  *(_BYTE *)(v4 + 57) = 1;
  *(_QWORD *)(v2[4] + 8LL) = v2[4];
  *(_QWORD *)v2[4] = v2[4];
  *(_QWORD *)(v2[4] + 16LL) = v2[4];
  *((_QWORD *)this + 34) = 0;
  v22 = (volatile signed __int32 *)((char *)this + 280);
  v6 = std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Buynode(v5);
  *((_QWORD *)this + 36) = v6;
  *(_BYTE *)(v6 + 41) = 1;
  *(_QWORD *)(v2[7] + 8LL) = v2[7];
  *(_QWORD *)v2[7] = v2[7];
  *(_QWORD *)(v2[7] + 16LL) = v2[7];
  *((_QWORD *)this + 37) = 0;
  v22 = (volatile signed __int32 *)((char *)this + 304);
  v8 = std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Buynode(v7);
  *((_QWORD *)this + 39) = v8;
  *(_BYTE *)(v8 + 33) = 1;
  *(_QWORD *)(v2[10] + 8LL) = v2[10];
  *(_QWORD *)v2[10] = v2[10];
  *(_QWORD *)(v2[10] + 16LL) = v2[10];
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 86) = 0;
  *((_BYTE *)this + 352) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  v9 = (_QWORD *)((char *)this + 384);
  *((_QWORD *)this + 48) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 49) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  if ( !ATL::CAutoVectorPtr<_CVDD>::Allocate((_QWORD *)this + 50, 2u)
    || !ATL::CAutoVectorPtr<unsigned long>::Allocate((_QWORD *)this + 51, 2u)
    || !ATL::CAutoVectorPtr<unsigned __int64>::Allocate((_QWORD *)this + 52, 2u) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *((_DWORD *)this + 106) = 2;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 384,
                        L"XPERF_EmbeddedPdbPath")
    || !*(_DWORD *)(*v9 - 16LL) )
  {
    v22 = (volatile signed __int32 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v22,
                         L"_NT_SYMBOL_PATH") )
    {
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 1;
      v34 = 0;
      v10 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(
              &v34,
              L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})");
      if ( v10 )
      {
        if ( v10 != 1 )
          ATL::AtlThrowImpl(-2147024882);
        ATL::AtlThrowImpl(-2147024882);
      }
      v27 = 0;
      v28 = 0;
      Block = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      LODWORD(v26[0]) = 0;
      v33 = 0;
      if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&Block, 256) )
      {
        ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
        v30 = 256;
      }
      v26[1] = 0;
      v26[2] = 0;
      LODWORD(v23) = 0;
      v24 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      while ( 1 )
      {
        v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &v22,
                &v25,
                v11,
                &v23);
        v13 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                       &v24,
                                       v12)
                        - 16LL);
        v14 = (char *)(v25 - 6);
        if ( _InterlockedDecrement(v25 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
        if ( !v13 )
          break;
        if ( v24 )
          v15 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v34, v24, v26);
        else
          v15 = 0;
        if ( v15 )
        {
          if ( !LODWORD(v26[0]) )
            ATL::AtlThrowImpl(-2147467259);
          v44 = *(_QWORD *)v28;
          v45 = *((_QWORD *)v28 + 1);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 384, v44, (unsigned int)((v45 - v44) >> 1));
          break;
        }
      }
      v16 = (_QWORD *)(v24 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
      if ( Block )
        free(Block);
      operator delete(v28);
      v28 = 0;
      operator delete(v27);
      v27 = 0;
      if ( v35 )
        free(v35);
    }
    if ( !*(_DWORD *)(*v9 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        LastError = GetLastError();
        v18 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v18 = LastError;
        ATL::AtlThrowImpl(v18);
      }
      v19 = -1;
      do
        ++v19;
      while ( Buffer[v19] );
      if ( v19 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 384,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v20 = (char *)(v22 - 6);
    if ( _InterlockedDecrement(v22 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20);
  }
  return this;
}

```

## disassembly

```asm
0x1800098d0  mov     rax, rsp
0x1800098d3  push    rbp
0x1800098d4  push    r12
0x1800098d6  push    r13
0x1800098d8  push    r14
0x1800098da  push    r15
0x1800098dc  lea     rbp, [rax-238h]
0x1800098e3  sub     rsp, 310h
0x1800098ea  mov     [rbp+230h+var_268], 0FFFFFFFFFFFFFFFEh
0x1800098f2  mov     [rax+10h], rbx
0x1800098f6  mov     [rax+18h], rsi
0x1800098fa  mov     [rax+20h], rdi
0x1800098fe  mov     rax, cs:__security_cookie
0x180009905  xor     rax, rsp
0x180009908  mov     [rbp+230h+var_30], rax
0x18000990f  mov     rsi, rcx
0x180009912  mov     [rbp+230h+var_260], rcx
0x180009916  xor     r15d, r15d
0x180009919  mov     [rcx+18h], r15d
0x18000991d  lea     rax, ??_7CEventTraceExtenderBase@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventTraceExtenderBase::`vftable'
0x180009924  mov     [rcx], rax
0x180009927  mov     [rcx+8], r15
0x18000992b  mov     [rcx+10h], r15
0x18000992f  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x180009936  mov     [rcx], rax
0x180009939  mov     [rcx+20h], r15d
0x18000993d  xor     eax, eax
0x18000993f  mov     [rbp+230h+var_258], rax
0x180009943  mov     [rcx+28h], rax
0x180009947  mov     [rcx+30h], r15d
0x18000994b  mov     [rcx+38h], r15
0x18000994f  lea     rax, [rcx+40h]
0x180009953  mov     [rsp+330h+var_2F8], rax
0x180009958  mov     [rax+8], r15
0x18000995c  mov     [rax+10h], r15
0x180009960  mov     [rax+18h], r15
0x180009964  mov     [rax+28h], r15
0x180009968  mov     [rax+30h], r15
0x18000996c  mov     [rax+38h], r15
0x180009970  lea     ecx, [r15+7]
0x180009974  mov     [rax+60h], rcx
0x180009978  mov     [rax+58h], r15
0x18000997c  mov     [rax+48h], r15w
0x180009981  mov     [rax+88h], rcx
0x180009988  mov     [rax+80h], r15
0x18000998f  mov     [rax+70h], r15w
0x180009994  mov     [rax+90h], r15b
0x18000999b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800099a2  lea     r13, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800099a9  mov     rcx, r13
0x1800099ac  mov     rax, [rax+18h]
0x1800099b0  call    cs:__guard_dispatch_icall_fptr
0x1800099b6  add     rax, 18h
0x1800099ba  mov     [rsi+0D8h], rax
0x1800099c1  mov     [rsi+0E0h], r15w
0x1800099c9  lea     rdi, [rsi+0E8h]
0x1800099d0  mov     [rsp+330h+var_2F8], rdi
0x1800099d5  call    ?_Buynode@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@XZ; std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode(void)
0x1800099da  mov     [rdi+8], rax
0x1800099de  mov     [rdi+10h], r15
0x1800099e2  lea     rbx, [rdi+18h]
0x1800099e6  mov     [rsp+330h+var_310], rbx
0x1800099eb  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(void)
0x1800099f0  mov     [rbx+8], rax
0x1800099f4  mov     byte ptr [rax+39h], 1
0x1800099f8  mov     rax, [rbx+8]
0x1800099fc  mov     [rax+8], rax
0x180009a00  mov     rax, [rbx+8]
0x180009a04  mov     [rax], rax
0x180009a07  mov     rax, [rbx+8]
0x180009a0b  mov     [rax+10h], rax
0x180009a0f  mov     [rbx+10h], r15
0x180009a13  lea     rbx, [rdi+30h]
0x180009a17  mov     [rsp+330h+var_310], rbx
0x180009a1c  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@2@XZ; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Buynode(void)
0x180009a21  mov     [rbx+8], rax
0x180009a25  mov     byte ptr [rax+29h], 1
0x180009a29  mov     rax, [rbx+8]
0x180009a2d  mov     [rax+8], rax
0x180009a31  mov     rax, [rbx+8]
0x180009a35  mov     [rax], rax
0x180009a38  mov     rax, [rbx+8]
0x180009a3c  mov     [rax+10h], rax
0x180009a40  mov     [rbx+10h], r15
0x180009a44  lea     rbx, [rdi+48h]
0x180009a48  mov     [rsp+330h+var_310], rbx
0x180009a4d  call    ?_Buynode@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@2@XZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Buynode(void)
0x180009a52  mov     [rbx+8], rax
0x180009a56  mov     byte ptr [rax+21h], 1
0x180009a5a  mov     rax, [rbx+8]
0x180009a5e  mov     [rax+8], rax
0x180009a62  mov     rax, [rbx+8]
0x180009a66  mov     [rax], rax
0x180009a69  mov     rax, [rbx+8]
0x180009a6d  mov     [rax+10h], rax
0x180009a71  mov     [rbx+10h], r15
0x180009a75  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009a7c  mov     rcx, r13
0x180009a7f  mov     rax, [rax+18h]
0x180009a83  call    cs:__guard_dispatch_icall_fptr
0x180009a89  add     rax, 18h
0x180009a8d  mov     [rsi+148h], rax
0x180009a94  mov     [rsi+150h], r15
0x180009a9b  mov     [rsi+158h], r15d
0x180009aa2  mov     [rsi+160h], r15b
0x180009aa9  mov     [rsi+168h], r15
0x180009ab0  mov     [rsi+170h], r15
0x180009ab7  mov     [rsi+178h], r15
0x180009abe  lea     rbx, [rsi+180h]
0x180009ac5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009acc  mov     rcx, r13
0x180009acf  mov     rax, [rax+18h]
0x180009ad3  call    cs:__guard_dispatch_icall_fptr
0x180009ad9  add     rax, 18h
0x180009add  mov     [rbx], rax
0x180009ae0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009ae7  mov     rcx, r13
0x180009aea  mov     rax, [rax+18h]
0x180009aee  call    cs:__guard_dispatch_icall_fptr
0x180009af4  add     rax, 18h
0x180009af8  mov     [rsi+188h], rax
0x180009aff  lea     rcx, [rsi+190h]
0x180009b06  mov     [rcx], r15
0x180009b09  lea     rdi, [rsi+198h]
0x180009b10  mov     [rdi], r15
0x180009b13  lea     r14, [rsi+1A0h]
0x180009b1a  mov     [r14], r15
0x180009b1d  mov     [rsi+1A8h], r15
0x180009b24  lea     r12d, [r15+2]
0x180009b28  mov     edx, r12d
0x180009b2b  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180009b30  test    al, al
0x180009b32  jz      loc_180009E2E
0x180009b38  mov     edx, r12d
0x180009b3b  mov     rcx, rdi
0x180009b3e  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180009b43  test    al, al
0x180009b45  jz      loc_180009E2E
0x180009b4b  mov     edx, r12d
0x180009b4e  mov     rcx, r14
0x180009b51  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180009b56  test    al, al
0x180009b58  jz      loc_180009E2E
0x180009b5e  mov     [rsi+1A8h], r12d
0x180009b65  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x180009b6c  mov     rcx, rbx
0x180009b6f  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180009b74  test    eax, eax
0x180009b76  jz      short loc_180009B85
0x180009b78  mov     rax, [rbx]
0x180009b7b  cmp     [rax-10h], r15d
0x180009b7f  jnz     loc_180009E29
0x180009b85  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009b8c  mov     rcx, r13
0x180009b8f  mov     rax, [rax+18h]
0x180009b93  call    cs:__guard_dispatch_icall_fptr
0x180009b99  add     rax, 18h
0x180009b9d  mov     [rsp+330h+var_310], rax
0x180009ba2  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x180009ba9  lea     rcx, [rsp+330h+var_310]
0x180009bae  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180009bb3  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009bb7  test    eax, eax
0x180009bb9  jz      loc_180009D8C
0x180009bbf  mov     [rbp+230h+var_298], r15
0x180009bc3  mov     [rbp+230h+var_290], r15
0x180009bc7  mov     [rbp+230h+var_288], r15
0x180009bcb  mov     [rbp+230h+var_280], r15d
0x180009bcf  mov     [rbp+230h+var_278], r15
0x180009bd3  mov     [rbp+230h+var_270], 1
0x180009bda  mov     [rbp+230h+var_2A0], r15d
0x180009bde  lea     rdx, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180009be5  lea     rcx, [rbp+230h+var_2A0]
0x180009be9  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180009bee  test    eax, eax
0x180009bf0  jz      short loc_180009C08
0x180009bf2  mov     ecx, 8007000Eh; int
0x180009bf7  cmp     eax, 1
0x180009bfa  jz      short loc_180009C02
0x180009bfc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009c02  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009c08  mov     [rsp+330h+var_2D8], r15
0x180009c0d  mov     [rsp+330h+var_2D0], r15
0x180009c12  mov     [rsp+330h+Block], r15
0x180009c17  mov     [rsp+330h+var_2C0], r15
0x180009c1c  mov     [rsp+330h+var_2B8], r15
0x180009c21  mov     [rbp+230h+var_2B0], r15d
0x180009c25  mov     dword ptr [rsp+330h+var_2F0], r15d
0x180009c2a  mov     [rbp+230h+var_2A8], r15
0x180009c2e  mov     edi, 100h
0x180009c33  mov     edx, edi
0x180009c35  lea     rcx, [rsp+330h+Block]
0x180009c3a  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x180009c3f  test    al, al
0x180009c41  jz      short loc_180009C4D
0x180009c43  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x180009c48  mov     [rsp+330h+var_2C0], rdi
0x180009c4d  mov     [rsp+330h+var_2E8], r15
0x180009c52  mov     [rsp+330h+var_2E0], r15
0x180009c57  mov     dword ptr [rsp+330h+var_308], r15d
0x180009c5c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180009c63  mov     rcx, r13
0x180009c66  mov     rax, [rax+18h]
0x180009c6a  call    cs:__guard_dispatch_icall_fptr
0x180009c70  add     rax, 18h
0x180009c74  mov     [rsp+330h+var_300], rax
0x180009c79  lea     r9, [rsp+330h+var_308]
0x180009c7e  lea     rdx, [rsp+330h+var_2F8]
0x180009c83  lea     rcx, [rsp+330h+var_310]
0x180009c88  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180009c8d  nop
0x180009c8e  mov     rdx, rax
0x180009c91  lea     rcx, [rsp+330h+var_300]
0x180009c96  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180009c9b  mov     rcx, [rax]
0x180009c9e  mov     edi, [rcx-10h]
0x180009ca1  mov     rdx, [rsp+330h+var_2F8]
0x180009ca6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180009caa  mov     eax, r14d
0x180009cad  lock xadd [rdx+10h], eax
0x180009cb2  add     eax, r14d
0x180009cb5  test    eax, eax
0x180009cb7  jg      short loc_180009CC9
0x180009cb9  mov     rcx, [rdx]
0x180009cbc  mov     rax, [rcx]
0x180009cbf  mov     rax, [rax+8]
0x180009cc3  call    cs:__guard_dispatch_icall_fptr
0x180009cc9  test    edi, edi
0x180009ccb  jz      short loc_180009D26
0x180009ccd  mov     rdx, [rsp+330h+var_300]
0x180009cd2  test    rdx, rdx
0x180009cd5  jz      short loc_180009CE7
0x180009cd7  lea     r8, [rsp+330h+var_2F0]
0x180009cdc  lea     rcx, [rbp+230h+var_2A0]
0x180009ce0  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x180009ce5  jmp     short loc_180009CEA
0x180009ce7  mov     eax, r15d
0x180009cea  test    eax, eax
0x180009cec  jz      short loc_180009C79
0x180009cee  cmp     dword ptr [rsp+330h+var_2F0], r15d
0x180009cf3  ja      short loc_180009D00
0x180009cf5  mov     ecx, 80004005h; int
0x180009cfa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009d00  mov     rax, [rsp+330h+var_2D0]
0x180009d05  mov     rdx, [rax]
0x180009d08  mov     [rbp+230h+var_250], rdx
0x180009d0c  mov     rcx, [rax+8]
0x180009d10  mov     [rbp+230h+var_248], rcx
0x180009d14  sub     rcx, rdx
0x180009d17  sar     rcx, 1
0x180009d1a  mov     r8d, ecx
0x180009d1d  mov     rcx, rbx
0x180009d20  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009d25  nop
0x180009d26  mov     rdx, [rsp+330h+var_300]
0x180009d2b  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180009d2f  mov     eax, r14d
0x180009d32  lock xadd [rdx+10h], eax
0x180009d37  add     eax, r14d
0x180009d3a  test    eax, eax
0x180009d3c  jg      short loc_180009D4F
0x180009d3e  mov     rcx, [rdx]
0x180009d41  mov     rax, [rcx]
0x180009d44  mov     rax, [rax+8]
0x180009d48  call    cs:__guard_dispatch_icall_fptr
0x180009d4e  nop
0x180009d4f  mov     rcx, [rsp+330h+Block]; Block
0x180009d54  test    rcx, rcx
0x180009d57  jz      short loc_180009D5F
0x180009d59  call    cs:__imp_free
0x180009d5f  mov     rcx, [rsp+330h+var_2D0]; Block
0x180009d64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d69  mov     [rsp+330h+var_2D0], r15
0x180009d6e  mov     rcx, [rsp+330h+var_2D8]; Block
0x180009d73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d78  mov     [rsp+330h+var_2D8], r15
0x180009d7d  mov     rcx, [rbp+230h+var_298]; Block
0x180009d81  test    rcx, rcx
0x180009d84  jz      short loc_180009D8C
0x180009d86  call    cs:__imp_free
0x180009d8c  mov     rax, [rbx]
0x180009d8f  cmp     [rax-10h], r15d
0x180009d93  jnz     short loc_180009E00
0x180009d95  mov     edx, 105h; uSize
0x180009d9a  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x180009d9e  call    cs:__imp_GetSystemWindowsDirectoryW
0x180009da4  test    eax, eax
0x180009da6  jnz     short loc_180009DC2
0x180009da8  call    cs:__imp_GetLastError
0x180009dae  movzx   ecx, ax
0x180009db1  or      ecx, 80070000h
0x180009db7  test    eax, eax
0x180009db9  cmovle  ecx, eax; int
0x180009dbc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009dc2  lea     rcx, [rbp+230h+Buffer]
0x180009dc6  mov     rax, r14
0x180009dc9  inc     rax
0x180009dcc  cmp     [rcx+rax*2], r15w
0x180009dd1  jnz     short loc_180009DC9
0x180009dd3  cmp     rax, r12
  ... truncated ...
```
