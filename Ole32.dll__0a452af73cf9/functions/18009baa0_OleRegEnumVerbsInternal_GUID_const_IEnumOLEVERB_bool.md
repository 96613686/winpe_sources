# OleRegEnumVerbsInternal(_GUID const &,IEnumOLEVERB * *,bool)

- ea: `0x18009baa0`
- end: `0x18009bf23`
- name: `?OleRegEnumVerbsInternal@@YAJAEBU_GUID@@PEAPEAUIEnumOLEVERB@@_N@Z`
- size: `1155`
- prototype: `HRESULT __fastcall(const _GUID *clsid, IEnumOLEVERB **ppenum, bool clsid)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180097df0`
- `0x18009c080`
- `0x18009f690`

## callees

- `0x18001248c`
- `0x1800185ec`
- `0x18001a3c8`
- `0x18001b0e4`
- `0x18001b810`
- `0x18001c1d0`
- `0x180029334`
- `0x1800478bc`
- `0x18004cb14`
- `0x180052390`
- `0x180052a10`
- `0x180053014`
- `0x180058824`
- `0x18009b928`
- `0x18009baa0`
- `0x18009c044`
- `0x1800c06ec`
- `0x1800c1a94`
- `0x1800c4645`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009bed8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009bed8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009be68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009be68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bdd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009be09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009be40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009bdd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009be09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009be40`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009bc19`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009bc19`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009bcf4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009bcf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bc60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bc95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bca3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bc60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bc95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bca3`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009bbfb`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009bbfb`

## string_xrefs

- `0x18009bcd5`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009bd60`: `com\ole32\ole232\stdimpl\oregverb.cpp`
- `0x18009bcb3`: `CLSID\`

## pseudocode

```c
__int64 __fastcall OleRegEnumVerbsInternal(const _GUID *clsid, IEnumOLEVERB **ppenum, bool a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v8; // rcx
  IOleClassInfo *m_ptr; // rcx
  IMrtResourceManager *v10; // r8
  IResourceContext *v11; // r9
  HRESULT OleClassInfoVerbIterator; // eax
  unsigned int v13; // edx
  BOOL IsOle1Class; // r12d
  HRESULT VerbList; // eax
  HRESULT v16; // esi
  wchar_t *v17; // rsi
  int v18; // r15d
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned __int64 v21; // rsi
  CEnumVerb *v22; // rax
  IEnumOLEVERB *v23; // rax
  __int64 v24; // rbx
  unsigned int v26; // [rsp+28h] [rbp-D8h]
  RegistryKey classKey; // [rsp+30h] [rbp-D0h] BYREF
  wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy> verbIterator; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *pwszBase; // [rsp+40h] [rbp-C0h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *psz; // [rsp+50h] [rbp-B0h] BYREF
  VerbList *pVerbList; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t szClsid[40]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t szKey[256]; // [rsp+B0h] [rbp-50h] BYREF
  void *retaddr; // [rsp+2F8h] [rbp+1F8h]

  pVerbList = 0;
  memset_0(szKey, 0, sizeof(szKey));
  pwszBase = 0;
  oleClassInfo.m_ptr = 0;
  verbIterator.m_ptr = 0;
  if ( !IsValidPtrOut(ppenum, 8u) )
  {
    v5 = -2147024809;
    goto $errSafeRtn_0;
  }
  *ppenum = 0;
  v6 = _InterlockedExchange64((volatile __int64 *)&g_EnumCache, 0);
  if ( v6 )
  {
    if ( !memcmp_0(clsid, (const void *)(*(_QWORD *)(v6 + 16) + 4LL), 0x10u) )
    {
      if ( *(_DWORD *)(v6 + 8) == 1 )
      {
        *ppenum = (IEnumOLEVERB *)v6;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        lpVtbl = *(struct IUnknownVtbl **)v6;
        v8 = v6;
      }
      else
      {
        if ( (*(unsigned int (__fastcall **)(__int64, IEnumOLEVERB **))(*(_QWORD *)v6 + 48LL))(v6, ppenum) )
        {
LABEL_53:
          v24 = _InterlockedExchange64((volatile __int64 *)&g_EnumCache, v6);
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          v5 = *ppenum == 0 ? 0x8007000E : 0;
          goto $errSafeRtn_0;
        }
        v8 = (__int64)*ppenum;
        lpVtbl = (*ppenum)->lpVtbl;
      }
      ((void (__fastcall *)(__int64))lpVtbl[1].Release)(v8);
      goto LABEL_53;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  m_ptr = oleClassInfo.m_ptr;
  oleClassInfo.m_ptr = 0;
  if ( m_ptr )
    ((void (__fastcall *)(IOleClassInfo *))m_ptr->lpVtbl->Release)(m_ptr);
  if ( GetClassInfoWithInprocOrLocalServer(
         clsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
    OleClassInfoVerbIterator = GetOleClassInfoVerbIterator(oleClassInfo.m_ptr, &verbIterator.m_ptr, v10, v11);
    v5 = OleClassInfoVerbIterator;
    if ( OleClassInfoVerbIterator < 0 )
    {
      v13 = 264;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v13,
        "com\\ole32\\ole232\\stdimpl\\oregverb.cpp",
        OleClassInfoVerbIterator);
      goto $errSafeRtn_0;
    }
    goto LABEL_44;
  }
  IsOle1Class = CoIsOle1Class(clsid);
  if ( !IsOle1Class )
  {
    v16 = StringCchCopyW(szKey, 0x100u, L"CLSID\\");
    if ( v16 >= 0 )
    {
      StringFromGUID2(clsid, szClsid, 39);
      v16 = StringCchCatW(szKey, 0x100u, szClsid);
      if ( v16 >= 0 )
      {
        v16 = StringCchLengthW(szKey, 0x100u, (unsigned __int64 *)&pwszBase);
        if ( v16 >= 0 )
        {
          v17 = pwszBase;
          goto LABEL_32;
        }
        v19 = 311;
      }
      else
      {
        v19 = 310;
      }
    }
    else
    {
      v19 = 305;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v19, "com\\ole32\\ole232\\stdimpl\\oregverb.cpp", v16);
    goto LABEL_20;
  }
  psz = 0;
  VerbList = ProgIDFromCLSID(clsid, &psz);
  if ( VerbList )
    goto LABEL_45;
  classKey._hkey = 0;
  pwszBase = 0;
  v16 = StringCchCopyExW(szKey, 0x100u, psz, &pwszBase, (unsigned __int64 *)&classKey, v26);
  if ( v16 < 0 )
  {
    CoTaskMemFree(psz);
LABEL_20:
    v5 = v16;
    goto $errSafeRtn_0;
  }
  v17 = (wchar_t *)(256 - (unsigned __int64)classKey._hkey);
  v18 = StringCchCopyW(pwszBase, (unsigned __int64)classKey._hkey, STDFILE);
  if ( v18 < 0 )
  {
    CoTaskMemFree(psz);
    v5 = v18;
    goto $errSafeRtn_0;
  }
  CoTaskMemFree(psz);
LABEL_32:
  OleClassInfoVerbIterator = StringCchCatW(szKey, 0x100u, VERB);
  v5 = OleClassInfoVerbIterator;
  if ( OleClassInfoVerbIterator < 0 )
  {
    v13 = 315;
    goto LABEL_34;
  }
  wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
  pwszBase = szKey;
  if ( Microsoft::WRL::Details::MakeAndInitialize<RegistryVerbIterator,IOleVerbIterator,unsigned short const * &>(
         &verbIterator.m_ptr,
         (const wchar_t **)&pwszBase) >= 0 )
    goto LABEL_44;
  v21 = (unsigned __int64)v17;
  if ( v21 >= 256 )
    _report_rangecheckfailure();
  szKey[v21] = 0;
  classKey._hkey = 0;
  if ( RegistryKey::StaticOpenFromClassesRoot(szKey, v20, (HKEY__ **)&classKey._hkey) >= 0 )
  {
    if ( IsOle1Class )
    {
      wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(&verbIterator);
      if ( classKey._hkey )
      {
        RegCloseKey(classKey._hkey);
        classKey._hkey = 0;
      }
LABEL_44:
      VerbList = MakeVerbList(verbIterator.m_ptr, clsid, &pVerbList);
      if ( !VerbList )
      {
        v22 = (CEnumVerb *)HeapAlloc(g_hHeap, 0, 0x18u);
        if ( !v22 || (CEnumVerb::CEnumVerb(v22, pVerbList, 0), (v6 = (__int64)v23) == 0) )
        {
          HeapFree(g_hHeap, 0, pVerbList);
          v5 = -2147024882;
          goto $errSafeRtn_0;
        }
        *ppenum = v23;
        ((void (__fastcall *)(IEnumOLEVERB *))v23->lpVtbl->AddRef)(v23);
        goto LABEL_53;
      }
LABEL_45:
      v5 = VerbList;
      goto $errSafeRtn_0;
    }
    if ( classKey._hkey )
    {
      RegCloseKey(classKey._hkey);
      classKey._hkey = 0;
    }
    v5 = -2147221120;
  }
  else
  {
    if ( classKey._hkey )
    {
      RegCloseKey(classKey._hkey);
      classKey._hkey = 0;
    }
    v5 = -2147221164;
  }
$errSafeRtn_0:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&verbIterator);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return v5;
}

```

## disassembly

```asm
0x18009baa0  mov     [rsp-8+arg_10], rbx
0x18009baa5  push    rbp
0x18009baa6  push    rsi
0x18009baa7  push    rdi
0x18009baa8  push    r12
0x18009baaa  push    r13
0x18009baac  push    r14
0x18009baae  push    r15
0x18009bab0  lea     rbp, [rsp-1C0h]
0x18009bab8  sub     rsp, 2C0h
0x18009babf  mov     rax, cs:__security_cookie
0x18009bac6  xor     rax, rsp
0x18009bac9  mov     [rbp+1F0h+var_40], rax
0x18009bad0  mov     r14, ppenum
0x18009bad3  mov     rdi, clsid
0x18009bad6  xor     r13d, r13d
0x18009bad9  lea     clsid, [rbp+1F0h+szKey]; void *
0x18009badd  xor     edx, edx; Val
0x18009badf  mov     [rsp+2F0h+pVerbList], r13
0x18009bae4  mov     r8d, 200h; Size
0x18009baea  call    memset_0
0x18009baef  lea     edx, [r13+8]; cb
0x18009baf3  mov     [rsp+2F0h+pwszBase], r13
0x18009baf8  mov     clsid, r14; pv
0x18009bafb  mov     [rsp+2F0h+oleClassInfo.m_ptr], r13
0x18009bb00  mov     [rsp+2F0h+verbIterator.m_ptr], r13
0x18009bb05  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18009bb0a  test    eax, eax
0x18009bb0c  jnz     short loc_18009BB18
0x18009bb0e  mov     ebx, 80070057h
0x18009bb13  jmp     $errSafeRtn_0
0x18009bb18  mov     rbx, r13
0x18009bb1b  mov     [r14], r13
0x18009bb1e  xchg    rbx, cs:?g_EnumCache@@3UEnumVerbCache@@A.pEnum; EnumVerbCache g_EnumCache ...
0x18009bb25  test    rbx, rbx
0x18009bb28  jz      short loc_18009BB96
0x18009bb2a  mov     ppenum, [rbx+10h]
0x18009bb2e  mov     r8d, 10h; Size
0x18009bb34  add     ppenum, 4; Buf2
0x18009bb38  mov     clsid, rdi; Buf1
0x18009bb3b  call    memcmp_0
0x18009bb40  mov     clsid, rbx
0x18009bb43  test    eax, eax
0x18009bb45  jnz     short loc_18009BB8A
0x18009bb47  cmp     dword ptr [rbx+8], 1
0x18009bb4b  jnz     short loc_18009BB64
0x18009bb4d  mov     [r14], rbx
0x18009bb50  mov     rax, [rbx]
0x18009bb53  mov     rax, [rax+8]
0x18009bb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bb5c  mov     rax, [rbx]
0x18009bb5f  mov     clsid, rbx
0x18009bb62  jmp     short loc_18009BB81
0x18009bb64  mov     rax, [rbx]
0x18009bb67  mov     ppenum, r14
0x18009bb6a  mov     rax, [rax+30h]
0x18009bb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bb73  test    eax, eax
0x18009bb75  jnz     loc_18009BE9D
0x18009bb7b  mov     clsid, [r14]
0x18009bb7e  mov     rax, [clsid]
0x18009bb81  mov     rax, [rax+28h]
0x18009bb85  jmp     loc_18009BE98
0x18009bb8a  mov     rax, [rbx]
0x18009bb8d  mov     rax, [rax+10h]
0x18009bb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bb96  mov     clsid, [rsp+2F0h+oleClassInfo.m_ptr]
0x18009bb9b  mov     [rsp+2F0h+oleClassInfo.m_ptr], r13
0x18009bba0  test    clsid, clsid
0x18009bba3  jz      short loc_18009BBB1
0x18009bba5  mov     rax, [clsid]
0x18009bba8  mov     rax, [rax+10h]
0x18009bbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bbb1  lea     r9, [rsp+2F0h+oleClassInfo]; ppv
0x18009bbb6  xor     edx, edx; pComCatalog
0x18009bbb8  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18009bbbf  mov     clsid, rdi; clsid
0x18009bbc2  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18009bbc7  test    eax, eax
0x18009bbc9  js      short loc_18009BBF8
0x18009bbcb  lea     clsid, [rsp+2F0h+verbIterator]; this
0x18009bbd0  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009bbd5  mov     clsid, [rsp+2F0h+oleClassInfo.m_ptr]; oleClassInfo
0x18009bbda  lea     ppenum, [rsp+2F0h+verbIterator]; verbIterator
0x18009bbdf  call    ?GetOleClassInfoVerbIterator@@YAJPEAUIOleClassInfo@@PEAPEAUIOleVerbIterator@@PEAUIMrtResourceManager@@PEAUIResourceContext@@@Z; GetOleClassInfoVerbIterator(IOleClassInfo *,IOleVerbIterator * *,IMrtResourceManager *,IResourceContext *)
0x18009bbe4  mov     ebx, eax
0x18009bbe6  test    eax, eax
0x18009bbe8  jns     loc_18009BE14
0x18009bbee  mov     edx, 108h
0x18009bbf3  jmp     loc_18009BD59
0x18009bbf8  mov     clsid, rdi; rclsid
0x18009bbfb  call    cs:__imp_CoIsOle1Class
0x18009bc01  mov     r12d, eax
0x18009bc04  test    eax, eax
0x18009bc06  jz      loc_18009BCAE
0x18009bc0c  lea     ppenum, [rsp+2F0h+psz]; lplpszProgID
0x18009bc11  mov     [rsp+2F0h+psz], r13
0x18009bc16  mov     clsid, rdi; clsid
0x18009bc19  call    cs:__imp_ProgIDFromCLSID
0x18009bc1f  test    eax, eax
0x18009bc21  jnz     loc_18009BE2A
0x18009bc27  mov     r8, [rsp+2F0h+psz]; pszSrc
0x18009bc2c  lea     rax, [rsp+2F0h+classKey]
0x18009bc31  mov     ebx, 100h
0x18009bc36  mov     [rsp+2F0h+classKey._hkey], r13
0x18009bc3b  mov     edx, ebx; cchDest
0x18009bc3d  mov     [rsp+2F0h+pwszBase], r13
0x18009bc42  lea     r9, [rsp+2F0h+pwszBase]; ppszDestEnd
0x18009bc47  mov     [rsp+2F0h+pcchRemaining], rax; pcchRemaining
0x18009bc4c  lea     clsid, [rbp+1F0h+szKey]; pszDest
0x18009bc50  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18009bc55  mov     esi, eax
0x18009bc57  test    eax, eax
0x18009bc59  jns     short loc_18009BC6D
0x18009bc5b  mov     clsid, [rsp+2F0h+psz]; pv
0x18009bc60  call    cs:__imp_CoTaskMemFree
0x18009bc66  mov     ebx, esi
0x18009bc68  jmp     $errSafeRtn_0
0x18009bc6d  mov     ppenum, [rsp+2F0h+classKey._hkey]; cchDest
0x18009bc72  lea     r8, STDFILE; pszSrc
0x18009bc79  mov     clsid, [rsp+2F0h+pwszBase]; pszDest
0x18009bc7e  mov     rsi, rbx
0x18009bc81  sub     rsi, ppenum
0x18009bc84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009bc89  mov     clsid, [rsp+2F0h+psz]; pv
0x18009bc8e  mov     r15d, eax
0x18009bc91  test    eax, eax
0x18009bc93  jns     short loc_18009BCA3
0x18009bc95  call    cs:__imp_CoTaskMemFree
0x18009bc9b  mov     ebx, r15d
0x18009bc9e  jmp     $errSafeRtn_0
0x18009bca3  call    cs:__imp_CoTaskMemFree
0x18009bca9  jmp     loc_18009BD3B
0x18009bcae  mov     ebx, 100h
0x18009bcb3  lea     r8, aClsid_0; "CLSID\\"
0x18009bcba  mov     edx, ebx; cchDest
0x18009bcbc  lea     clsid, [rbp+1F0h+szKey]; pszDest
0x18009bcc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009bcc5  mov     esi, eax
0x18009bcc7  test    eax, eax
0x18009bcc9  jns     short loc_18009BCE6
0x18009bccb  lea     edx, [rbx+31h]; lineNumber
0x18009bcce  mov     clsid, [rbp+1F8h]; callerReturnAddress
0x18009bcd5  lea     r8, aComOle32Ole232_10; "com\\ole32\\ole232\\stdimpl\\oregverb.c"...
0x18009bcdc  mov     r9d, esi; hr
0x18009bcdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bce4  jmp     short loc_18009BC66
0x18009bce6  mov     r8d, 27h ; '''; cchMax
0x18009bcec  lea     ppenum, [rsp+2F0h+szClsid]; lpsz
0x18009bcf1  mov     clsid, rdi; rguid
0x18009bcf4  call    cs:__imp_StringFromGUID2
0x18009bcfa  lea     r8, [rsp+2F0h+szClsid]; pszSrc
0x18009bcff  mov     ppenum, rbx; cchDest
0x18009bd02  lea     clsid, [rbp+1F0h+szKey]; pszDest
0x18009bd06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009bd0b  mov     esi, eax
0x18009bd0d  test    eax, eax
0x18009bd0f  jns     short loc_18009BD18
0x18009bd11  mov     edx, 136h
0x18009bd16  jmp     short loc_18009BCCE
0x18009bd18  lea     r8, [rsp+2F0h+pwszBase]; pcchLength
0x18009bd1d  mov     ppenum, rbx; cchMax
0x18009bd20  lea     clsid, [rbp+1F0h+szKey]; psz
0x18009bd24  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009bd29  mov     esi, eax
0x18009bd2b  test    eax, eax
0x18009bd2d  jns     short loc_18009BD36
0x18009bd2f  mov     edx, 137h
0x18009bd34  jmp     short loc_18009BCCE
0x18009bd36  mov     rsi, [rsp+2F0h+pwszBase]
0x18009bd3b  lea     r8, VERB; pszSrc
0x18009bd42  mov     ppenum, rbx; cchDest
0x18009bd45  lea     clsid, [rbp+1F0h+szKey]; pszDest
0x18009bd49  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009bd4e  mov     ebx, eax
0x18009bd50  test    eax, eax
0x18009bd52  jns     short loc_18009BD74
0x18009bd54  mov     edx, 13Bh; lineNumber
0x18009bd59  mov     clsid, [rbp+1F8h]; callerReturnAddress
0x18009bd60  lea     r8, aComOle32Ole232_10; "com\\ole32\\ole232\\stdimpl\\oregverb.c"...
0x18009bd67  mov     r9d, eax; hr
0x18009bd6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bd6f  jmp     $errSafeRtn_0
0x18009bd74  lea     clsid, [rsp+2F0h+verbIterator]; this
0x18009bd79  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009bd7e  lea     rax, [rbp+1F0h+szKey]
0x18009bd82  lea     ppenum, [rsp+2F0h+pwszBase]; <args_0>
0x18009bd87  mov     [rsp+2F0h+pwszBase], rax
0x18009bd8c  lea     clsid, [rsp+2F0h+verbIterator]; result
0x18009bd91  call    ??$MakeAndInitialize@VRegistryVerbIterator@@UIOleVerbIterator@@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUIOleVerbIterator@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<RegistryVerbIterator,IOleVerbIterator,ushort const * &>(IOleVerbIterator * *,ushort const * &)
0x18009bd96  test    eax, eax
0x18009bd98  jns     short loc_18009BE14
0x18009bd9a  add     rsi, rsi
0x18009bd9d  cmp     rsi, 200h
0x18009bda4  jnb     loc_18009BE55
0x18009bdaa  mov     [rbp+rsi+1F0h+szKey], r13w
0x18009bdb0  lea     r8, [rsp+2F0h+classKey]; pszSubKeyPath
0x18009bdb5  lea     clsid, [rbp+1F0h+szKey]; pszSubKeyPath
0x18009bdb9  mov     [rsp+2F0h+classKey._hkey], r13
0x18009bdbe  call    ?StaticOpenFromClassesRoot@RegistryKey@@CAJPEBGKPEAPEAUHKEY__@@@Z; RegistryKey::StaticOpenFromClassesRoot(ushort const *,ulong,HKEY__ * *)
0x18009bdc3  test    eax, eax
0x18009bdc5  jns     short loc_18009BDEB
0x18009bdc7  mov     rax, [rsp+2F0h+classKey._hkey]
0x18009bdcc  test    rax, rax
0x18009bdcf  jz      short loc_18009BDE1
0x18009bdd1  mov     clsid, [rsp+2F0h+classKey._hkey]; hKey
0x18009bdd6  call    cs:__imp_RegCloseKey
0x18009bddc  mov     [rsp+2F0h+classKey._hkey], r13
0x18009bde1  mov     ebx, 80040154h
0x18009bde6  jmp     $errSafeRtn_0
0x18009bdeb  test    r12d, r12d
0x18009bdee  jz      short loc_18009BE31
0x18009bdf0  lea     clsid, [rsp+2F0h+verbIterator]; this
0x18009bdf5  call    ?reset@?$com_ptr_t@UIOleVerbIterator@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOleVerbIterator,wil::err_returncode_policy>::reset(void)
0x18009bdfa  mov     rax, [rsp+2F0h+classKey._hkey]
0x18009bdff  test    rax, rax
0x18009be02  jz      short loc_18009BE14
0x18009be04  mov     clsid, [rsp+2F0h+classKey._hkey]; hKey
0x18009be09  call    cs:__imp_RegCloseKey
0x18009be0f  mov     [rsp+2F0h+classKey._hkey], r13
0x18009be14  mov     clsid, [rsp+2F0h+verbIterator.m_ptr]; verbIterator
0x18009be19  lea     r8, [rsp+2F0h+pVerbList]; verbList
0x18009be1e  mov     ppenum, rdi; clsid
0x18009be21  call    ?MakeVerbList@@YAJPEAUIOleVerbIterator@@AEBU_GUID@@PEAPEAUVerbList@@@Z; MakeVerbList(IOleVerbIterator *,_GUID const &,VerbList * *)
0x18009be26  test    eax, eax
0x18009be28  jz      short loc_18009BE5B
0x18009be2a  mov     ebx, eax
0x18009be2c  jmp     $errSafeRtn_0
0x18009be31  mov     rax, [rsp+2F0h+classKey._hkey]
0x18009be36  test    rax, rax
0x18009be39  jz      short loc_18009BE4B
0x18009be3b  mov     clsid, [rsp+2F0h+classKey._hkey]; hKey
0x18009be40  call    cs:__imp_RegCloseKey
0x18009be46  mov     [rsp+2F0h+classKey._hkey], r13
0x18009be4b  mov     ebx, 80040180h
0x18009be50  jmp     $errSafeRtn_0
0x18009be55  call    __report_rangecheckfailure
0x18009be5b  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009be62  xor     edx, edx; dwFlags
0x18009be64  lea     r8d, [ppenum+18h]; dwBytes
0x18009be68  call    cs:__imp_HeapAlloc
0x18009be6e  test    rax, rax
0x18009be71  jz      short loc_18009BECA
0x18009be73  mov     ppenum, [rsp+2F0h+pVerbList]; pVerbs
0x18009be78  xor     r8d, r8d; iVerb
0x18009be7b  mov     clsid, rax; this
0x18009be7e  call    ??0CEnumVerb@@AEAA@PEAUVerbList@@J@Z; CEnumVerb::CEnumVerb(VerbList *,long)
0x18009be83  mov     rbx, rax
0x18009be86  test    rax, rax
0x18009be89  jz      short loc_18009BECA
0x18009be8b  mov     [r14], rax
0x18009be8e  mov     clsid, rbx
0x18009be91  mov     rax, [rax]
0x18009be94  mov     rax, [rax+8]
0x18009be98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be9d  xchg    rbx, cs:?g_EnumCache@@3UEnumVerbCache@@A.pEnum; EnumVerbCache g_EnumCache ...
0x18009bea4  test    rbx, rbx
0x18009bea7  jz      short $errRtn_150
0x18009bea9  mov     rax, [rbx]
0x18009beac  mov     clsid, rbx
0x18009beaf  mov     rax, [rax+10h]
0x18009beb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009beb8  mov     rax, [r14]
0x18009bebb  neg     rax
0x18009bebe  sbb     ebx, ebx
0x18009bec0  not     ebx
0x18009bec2  and     ebx, 8007000Eh
0x18009bec8  jmp     short $errSafeRtn_0
0x18009beca  mov     r8, [rsp+2F0h+pVerbList]; lpMem
0x18009becf  xor     edx, edx; dwFlags
0x18009bed1  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009bed8  call    cs:__imp_HeapFree
0x18009bede  mov     ebx, 8007000Eh
0x18009bee3  lea     clsid, [rsp+2F0h+verbIterator]; this
0x18009bee8  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009beed  lea     clsid, [rsp+2F0h+oleClassInfo]; this
0x18009bef2  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009bef7  mov     eax, ebx
0x18009bef9  mov     clsid, [rbp+1F0h+var_40]
0x18009bf00  xor     clsid, rsp; StackCookie
0x18009bf03  call    __security_check_cookie
0x18009bf08  mov     rbx, [rsp+2F0h+arg_10]
0x18009bf10  add     rsp, 2C0h
0x18009bf17  pop     r15
0x18009bf19  pop     r14
0x18009bf1b  pop     r13
0x18009bf1d  pop     r12
0x18009bf1f  pop     rdi
0x18009bf20  pop     rsi
0x18009bf21  pop     rbp
0x18009bf22  retn
```
