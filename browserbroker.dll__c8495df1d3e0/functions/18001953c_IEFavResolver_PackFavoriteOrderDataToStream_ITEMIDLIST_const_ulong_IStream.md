# IEFavResolver::PackFavoriteOrderDataToStream(_ITEMIDLIST const *,ulong *,IStream * *)

- ea: `0x18001953c`
- end: `0x18001971b`
- name: `?PackFavoriteOrderDataToStream@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@PEAKPEAPEAUIStream@@@Z`
- size: `479`
- prototype: `int(IEFavResolver *__hidden this, const struct _ITEMIDLIST *, unsigned int *, struct IStream **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019984`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x180006cc4`
- `0x180015544`
- `0x18001953c`
- `0x18002505c`

## import_xrefs

- `iertutil!__imp_DPA_GetPtr` at `0x1800195ee`
- `iertutil!__imp_DPA_GetPtr` at `0x1800195ee`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001964c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001964c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800196b0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800196b0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180019694`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x180019694`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019588`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180019588`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001963c`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001963c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IEFavResolver::PackFavoriteOrderDataToStream(
        IEFavResolver *this,
        struct _ITEMIDLIST *a2,
        unsigned int *a3,
        struct IStream **a4)
{
  HRESULT FavoritesFolderOrder; // edi
  unsigned int v9; // r14d
  int v10; // esi
  HDPA v11; // rbx
  int v12; // eax
  _QWORD *Ptr; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  struct IStream *v17; // rax
  char v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-B8h] BYREF
  HDPA hdpa; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR *v23; // [rsp+60h] [rbp-A0h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v24; // [rsp+68h] [rbp-98h] BYREF
  __int64 CLSID; // [rsp+70h] [rbp-90h] BYREF
  WCHAR psz[264]; // [rsp+80h] [rbp-80h] BYREF

  ppstm = 0;
  FavoritesFolderOrder = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( FavoritesFolderOrder >= 0 )
  {
    v9 = 0;
    v22 = 0;
    hdpa = 0;
    FavoritesFolderOrder = GetFavoritesFolderOrder(a2, (unsigned __int16 *)this + 24);
    if ( FavoritesFolderOrder >= 0 )
    {
      v10 = 0;
      v11 = hdpa;
      while ( 1 )
      {
        v12 = v11 ? *(_DWORD *)v11 : 0;
        if ( v10 >= v12 )
          break;
        Ptr = DPA_GetPtr(v11, v10);
        if ( !Ptr )
        {
          FavoritesFolderOrder = -2147467259;
          break;
        }
        LODWORD(hdpa) = 0;
        FavoritesFolderOrder = DisplayNameOfW(v22, *Ptr, 0, psz);
        if ( FavoritesFolderOrder < 0 )
          break;
        if ( (unsigned int)dword_18003F000 > 5 )
        {
          v23 = psz;
          v19[0] = 1;
          v24 = GlobalThreadState();
          CLSID = IEConfiguration_GetCLSID(268435459);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
            v14,
            (__int64)byte_180035F4D,
            v15,
            v16,
            &CLSID,
            (__int64 *)&v24,
            (__int64)v19,
            (const WCHAR **)&v23);
        }
        FavoritesFolderOrder = IStream_WriteStr(ppstm, psz);
        if ( FavoritesFolderOrder < 0 )
          break;
        FavoritesFolderOrder = IStream_Write(ppstm, &hdpa, 4u);
        if ( FavoritesFolderOrder < 0 )
          break;
        ++v10;
        ++v9;
      }
    }
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(&v22);
    if ( FavoritesFolderOrder >= 0 )
    {
      *a3 = v9;
      v17 = ppstm;
      ppstm = 0;
      *a4 = v17;
    }
  }
  ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppstm);
  return (unsigned int)FavoritesFolderOrder;
}

```

## disassembly

```asm
0x18001953c  push    rbp
0x18001953e  push    rbx
0x18001953f  push    rsi
0x180019540  push    rdi
0x180019541  push    r12
0x180019543  push    r14
0x180019545  push    r15
0x180019547  lea     rbp, [rsp-1A0h]
0x18001954f  sub     rsp, 2A0h
0x180019556  mov     rax, cs:__security_cookie
0x18001955d  xor     rax, rsp
0x180019560  mov     [rbp+1D0h+var_40], rax
0x180019567  mov     r12, r9
0x18001956a  mov     r15, r8
0x18001956d  mov     rsi, rdx
0x180019570  mov     rbx, rcx
0x180019573  mov     [rsp+2D0h+ppstm], 0
0x18001957c  lea     r8, [rsp+2D0h+ppstm]; ppstm
0x180019581  mov     edx, 1; fDeleteOnRelease
0x180019586  xor     ecx, ecx; hGlobal
0x180019588  call    cs:__imp_CreateStreamOnHGlobal
0x18001958e  mov     edi, eax
0x180019590  test    eax, eax
0x180019592  js      loc_1800196EE
0x180019598  xor     r14d, r14d
0x18001959b  mov     [rsp+2D0h+var_278], r14
0x1800195a0  mov     [rsp+2D0h+hdpa], r14
0x1800195a5  lea     rax, [rbx+30h]
0x1800195a9  mov     [rsp+2D0h+var_2B0], rax; unsigned __int16 *
0x1800195ae  lea     r9, [rsp+2D0h+hdpa]
0x1800195b3  lea     r8, [rsp+2D0h+var_278]
0x1800195b8  lea     edx, [r14+60h]
0x1800195bc  mov     rcx, rsi; struct _ITEMIDLIST *
0x1800195bf  call    ?GetFavoritesFolderOrder@@YAJPEFBU_ITEMIDLIST@@KPEAPEAUIShellFolder@@PEAV?$CDPA@U__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@@@PEBG@Z; GetFavoritesFolderOrder(_ITEMIDLIST const *,ulong,IShellFolder * *,CDPA<__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001> *,ushort const *)
0x1800195c4  mov     edi, eax
0x1800195c6  test    eax, eax
0x1800195c8  js      loc_1800196CB
0x1800195ce  xor     esi, esi
0x1800195d0  mov     rbx, [rsp+2D0h+hdpa]
0x1800195d5  test    rbx, rbx
0x1800195d8  jz      short loc_1800195DE
0x1800195da  mov     eax, [rbx]
0x1800195dc  jmp     short loc_1800195E0
0x1800195de  xor     eax, eax
0x1800195e0  cmp     esi, eax
0x1800195e2  jge     loc_1800196CB
0x1800195e8  movsxd  rdx, esi; i
0x1800195eb  mov     rcx, rbx; hdpa
0x1800195ee  call    cs:__imp_DPA_GetPtr
0x1800195f4  test    rax, rax
0x1800195f7  jz      loc_1800196C6
0x1800195fd  mov     dword ptr [rsp+2D0h+hdpa], 0
0x180019605  lea     r9, [rbp+1D0h+psz]
0x180019609  xor     r8d, r8d
0x18001960c  mov     rdx, [rax]
0x18001960f  mov     rcx, [rsp+2D0h+var_278]
0x180019614  call    DisplayNameOfW
0x180019619  mov     edi, eax
0x18001961b  test    eax, eax
0x18001961d  js      loc_1800196CB
0x180019623  mov     eax, cs:dword_18003F000
0x180019629  cmp     eax, 5
0x18001962c  jbe     short loc_18001968B
0x18001962e  lea     rax, [rbp+1D0h+psz]
0x180019632  mov     [rsp+2D0h+var_270], rax
0x180019637  mov     [rsp+2D0h+var_290], 1
0x18001963c  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180019642  mov     [rsp+2D0h+var_268], rax
0x180019647  mov     ecx, 10000003h
0x18001964c  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180019652  mov     [rsp+2D0h+var_260], rax
0x180019657  lea     rax, [rsp+2D0h+var_270]
0x18001965c  mov     [rsp+2D0h+var_298], rax
0x180019661  lea     rax, [rsp+2D0h+var_290]
0x180019666  mov     [rsp+2D0h+var_2A0], rax
0x18001966b  lea     rax, [rsp+2D0h+var_268]
0x180019670  mov     [rsp+2D0h+var_2A8], rax
0x180019675  lea     rax, [rsp+2D0h+var_260]
0x18001967a  mov     [rsp+2D0h+var_2B0], rax
0x18001967f  lea     rdx, byte_180035F4D
0x180019686  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18001968b  lea     rdx, [rbp+1D0h+psz]; psz
0x18001968f  mov     rcx, [rsp+2D0h+ppstm]; pstm
0x180019694  call    cs:__imp_IStream_WriteStr
0x18001969a  mov     edi, eax
0x18001969c  test    eax, eax
0x18001969e  js      short loc_1800196CB
0x1800196a0  mov     r8d, 4; cb
0x1800196a6  lea     rdx, [rsp+2D0h+hdpa]; pv
0x1800196ab  mov     rcx, [rsp+2D0h+ppstm]; pstm
0x1800196b0  call    cs:__imp_IStream_Write
0x1800196b6  mov     edi, eax
0x1800196b8  test    eax, eax
0x1800196ba  js      short loc_1800196CB
0x1800196bc  inc     esi
0x1800196be  inc     r14d
0x1800196c1  jmp     loc_1800195D5
0x1800196c6  mov     edi, 80004005h
0x1800196cb  lea     rcx, [rsp+2D0h+var_278]
0x1800196d0  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x1800196d5  test    edi, edi
0x1800196d7  js      short loc_1800196EE
0x1800196d9  mov     [r15], r14d
0x1800196dc  mov     rax, [rsp+2D0h+ppstm]
0x1800196e1  mov     [rsp+2D0h+ppstm], 0
0x1800196ea  mov     [r12], rax
0x1800196ee  lea     rcx, [rsp+2D0h+ppstm]
0x1800196f3  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x1800196f8  mov     eax, edi
0x1800196fa  mov     rcx, [rbp+1D0h+var_40]
0x180019701  xor     rcx, rsp; StackCookie
0x180019704  call    __security_check_cookie
0x180019709  add     rsp, 2A0h
0x180019710  pop     r15
0x180019712  pop     r14
0x180019714  pop     r12
0x180019716  pop     rdi
0x180019717  pop     rsi
0x180019718  pop     rbx
0x180019719  pop     rbp
0x18001971a  retn
```
