# IEFavResolver::PostOrderChangedEventToEdge(_ITEMIDLIST const *)

- ea: `0x180019984`
- end: `0x180019b85`
- name: `?PostOrderChangedEventToEdge@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(IEFavResolver *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018aac`

## callees

- `0x180001e20`
- `0x180002ce0`
- `0x180006cc4`
- `0x180018080`
- `0x18001953c`
- `0x180019984`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800199f7`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800199f7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019ac9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x180019ac9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180019ae3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180019ae3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x180019a7c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Size` at `0x180019a7c`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180019b40`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x180019b40`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180019ab6`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x180019ab6`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180019b50`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x180019b50`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800199e7`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800199e7`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800199bf`
- `ext-ms-win-shell-shell32-l1-2-1!SHGetPathFromIDListW` at `0x1800199bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IEFavResolver::PostOrderChangedEventToEdge(IEFavResolver *this, struct _ITEMIDLIST *a2)
{
  int UnifiedFolderPath; // edi
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  IStream *v8; // rbx
  char v10[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-BCh] BYREF
  struct _IsoMessage *CLSID; // [rsp+48h] [rbp-B8h] BYREF
  ULARGE_INTEGER pui; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-A8h] BYREF
  IStream *pstm[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  UnifiedFolderPath = -2147467259;
  if ( SHGetPathFromIDListW(a2, pszPath) )
  {
    if ( (unsigned int)dword_18003F000 > 5 )
    {
      pstm[0] = (IStream *)pszPath;
      v10[0] = 1;
      pui.QuadPart = (ULONGLONG)GlobalThreadState();
      CLSID = (struct _IsoMessage *)IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)&byte_180035FCF,
        v6,
        v7,
        (__int64 *)&CLSID,
        (__int64 *)&pui,
        (__int64)v10,
        (const WCHAR **)pstm);
    }
    v14 = 0;
    pstm[0] = 0;
    UnifiedFolderPath = IEFavResolver::PackFavoriteOrderDataToStream(this, a2, &v14, pstm);
    if ( UnifiedFolderPath >= 0 )
    {
      pui.QuadPart = 0;
      v8 = pstm[0];
      UnifiedFolderPath = IStream_Size(pstm[0], &pui);
      if ( UnifiedFolderPath >= 0 )
      {
        v11 = 0;
        CLSID = 0;
        UnifiedFolderPath = IsoAllocMessageBuffer(*((_DWORD *)this + 2), &v11, pui.LowPart + 564, &CLSID);
        if ( UnifiedFolderPath >= 0 )
        {
          IStream_Reset(v8);
          UnifiedFolderPath = IStream_Read(v8, (char *)CLSID + 560, pui.LowPart);
          if ( UnifiedFolderPath < 0
            || (UnifiedFolderPath = IEFavResolver::GetUnifiedFolderPath(
                                      (const WCHAR *)this,
                                      pszPath,
                                      (unsigned __int16 *)CLSID + 16),
                UnifiedFolderPath < 0)
            || (*((_DWORD *)CLSID + 138) = v14,
                *((_DWORD *)CLSID + 139) = pui.LowPart,
                UnifiedFolderPath = LCIEPostMessage(*((_DWORD *)this + 2), *((_DWORD *)this + 1), 0xDBDu, 0, v11),
                UnifiedFolderPath < 0) )
          {
            IsoFreeMessageBuffer(v11);
          }
        }
      }
    }
    ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)pstm);
  }
  return (unsigned int)UnifiedFolderPath;
}

```

## disassembly

```asm
0x180019984  mov     [rsp-8+arg_10], rbx
0x180019989  push    rbp
0x18001998a  push    rsi
0x18001998b  push    rdi
0x18001998c  lea     rbp, [rsp-190h]
0x180019994  sub     rsp, 290h
0x18001999b  mov     rax, cs:__security_cookie
0x1800199a2  xor     rax, rsp
0x1800199a5  mov     [rbp+1A0h+var_20], rax
0x1800199ac  mov     rbx, rdx
0x1800199af  mov     rsi, rcx
0x1800199b2  mov     edi, 80004005h
0x1800199b7  lea     rdx, [rsp+2A0h+pszPath]; pszPath
0x1800199bc  mov     rcx, rbx; pidl
0x1800199bf  call    cs:__imp_SHGetPathFromIDListW
0x1800199c5  test    eax, eax
0x1800199c7  jz      loc_180019B61
0x1800199cd  mov     eax, cs:dword_18003F000
0x1800199d3  cmp     eax, 5
0x1800199d6  jbe     short loc_180019A36
0x1800199d8  lea     rax, [rsp+2A0h+pszPath]
0x1800199dd  mov     [rsp+2A0h+pstm], rax
0x1800199e2  mov     [rsp+2A0h+var_260], 1
0x1800199e7  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800199ed  mov     qword ptr [rsp+2A0h+pui], rax
0x1800199f2  mov     ecx, 10000003h
0x1800199f7  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800199fd  mov     [rsp+2A0h+var_258], rax
0x180019a02  lea     rax, [rsp+2A0h+pstm]
0x180019a07  mov     [rsp+2A0h+var_268], rax
0x180019a0c  lea     rax, [rsp+2A0h+var_260]
0x180019a11  mov     [rsp+2A0h+var_270], rax
0x180019a16  lea     rax, [rsp+2A0h+pui]
0x180019a1b  mov     [rsp+2A0h+var_278], rax
0x180019a20  lea     rax, [rsp+2A0h+var_258]
0x180019a25  mov     [rsp+2A0h+var_280], rax
0x180019a2a  lea     rdx, byte_180035FCF
0x180019a31  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180019a36  mov     [rsp+2A0h+var_248], 0
0x180019a3e  mov     [rsp+2A0h+pstm], 0
0x180019a47  lea     r9, [rsp+2A0h+pstm]; struct IStream **
0x180019a4c  lea     r8, [rsp+2A0h+var_248]; unsigned int *
0x180019a51  mov     rdx, rbx; struct _ITEMIDLIST *
0x180019a54  mov     rcx, rsi; this
0x180019a57  call    ?PackFavoriteOrderDataToStream@IEFavResolver@@AEAAJPEFBU_ITEMIDLIST@@PEAKPEAPEAUIStream@@@Z; IEFavResolver::PackFavoriteOrderDataToStream(_ITEMIDLIST const *,ulong *,IStream * *)
0x180019a5c  mov     edi, eax
0x180019a5e  test    eax, eax
0x180019a60  js      loc_180019B57
0x180019a66  mov     qword ptr [rsp+2A0h+pui], 0
0x180019a6f  lea     rdx, [rsp+2A0h+pui]; pui
0x180019a74  mov     rbx, [rsp+2A0h+pstm]
0x180019a79  mov     rcx, rbx; pstm
0x180019a7c  call    cs:__imp_IStream_Size
0x180019a82  mov     edi, eax
0x180019a84  test    eax, eax
0x180019a86  js      loc_180019B57
0x180019a8c  mov     [rsp+2A0h+var_25C], 0
0x180019a94  mov     [rsp+2A0h+var_258], 0
0x180019a9d  mov     r8d, dword ptr [rsp+2A0h+pui]
0x180019aa2  add     r8d, 234h
0x180019aa9  lea     r9, [rsp+2A0h+var_258]
0x180019aae  lea     rdx, [rsp+2A0h+var_25C]
0x180019ab3  mov     ecx, [rsi+8]
0x180019ab6  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x180019abc  mov     edi, eax
0x180019abe  test    eax, eax
0x180019ac0  js      loc_180019B57
0x180019ac6  mov     rcx, rbx; pstm
0x180019ac9  call    cs:__imp_IStream_Reset
0x180019acf  mov     rdx, [rsp+2A0h+var_258]
0x180019ad4  add     rdx, 230h; pv
0x180019adb  mov     r8d, dword ptr [rsp+2A0h+pui]; cb
0x180019ae0  mov     rcx, rbx; pstm
0x180019ae3  call    cs:__imp_IStream_Read
0x180019ae9  mov     edi, eax
0x180019aeb  test    eax, eax
0x180019aed  js      short loc_180019B4C
0x180019aef  mov     r8, [rsp+2A0h+var_258]
0x180019af4  add     r8, 20h ; ' '; unsigned __int16 *
0x180019af8  lea     rdx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x180019afd  mov     rcx, rsi; this
0x180019b00  call    ?GetUnifiedFolderPath@IEFavResolver@@AEAAJPEBGPEAGH@Z; IEFavResolver::GetUnifiedFolderPath(ushort const *,ushort *,int)
0x180019b05  mov     edi, eax
0x180019b07  test    eax, eax
0x180019b09  js      short loc_180019B4C
0x180019b0b  mov     ecx, [rsp+2A0h+var_248]
0x180019b0f  mov     rax, [rsp+2A0h+var_258]
0x180019b14  mov     [rax+228h], ecx
0x180019b1a  mov     ecx, dword ptr [rsp+2A0h+pui]
0x180019b1e  mov     rax, [rsp+2A0h+var_258]
0x180019b23  mov     [rax+22Ch], ecx
0x180019b29  mov     eax, [rsp+2A0h+var_25C]
0x180019b2d  mov     dword ptr [rsp+2A0h+var_280], eax
0x180019b31  xor     r9d, r9d
0x180019b34  mov     r8d, 0DBDh
0x180019b3a  mov     edx, [rsi+4]
0x180019b3d  mov     ecx, [rsi+8]
0x180019b40  call    cs:__imp_?LCIEPostMessage@@YAJKKKKK@Z; LCIEPostMessage(ulong,ulong,ulong,ulong,ulong)
0x180019b46  mov     edi, eax
0x180019b48  test    eax, eax
0x180019b4a  jns     short loc_180019B57
0x180019b4c  mov     ecx, [rsp+2A0h+var_25C]
0x180019b50  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x180019b56  nop
0x180019b57  lea     rcx, [rsp+2A0h+pstm]
0x180019b5c  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180019b61  mov     eax, edi
0x180019b63  mov     rcx, [rbp+1A0h+var_20]
0x180019b6a  xor     rcx, rsp; StackCookie
0x180019b6d  call    __security_check_cookie
0x180019b72  mov     rbx, [rsp+2A0h+arg_10]
0x180019b7a  add     rsp, 290h
0x180019b81  pop     rdi
0x180019b82  pop     rsi
0x180019b83  pop     rbp
0x180019b84  retn
```
