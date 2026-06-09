# CStartMenuInternetRunResultSetManager::GetResult(uint,uint,RS_GET_TYPE,IQueryContinue *,_GUID const &,void * *)

- ea: `0x18002c070`
- end: `0x18002c269`
- name: `?GetResult@CStartMenuInternetRunResultSetManager@@UEAAJIIW4RS_GET_TYPE@@PEAUIQueryContinue@@AEBU_GUID@@PEAPEAX@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b200`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18000ecc4`
- `0x18000eec0`
- `0x180021e64`
- `0x18002c070`
- `0x18002eb70`
- `0x18002eff0`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `SHCORE!__imp_SHWindowsPolicy` at `0x18002c10a`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18002c10a`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002c1d9`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002c1d9`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18002c127`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18002c127`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18002c179`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18002c179`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStartMenuInternetRunResultSetManager::GetResult(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7)
{
  int v9; // ecx
  int ContinueOnSite; // ebx
  int v11; // r8d
  int v12; // r9d
  int v13; // eax
  __int64 v14; // r8
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  IUri *ppURI[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pwzURI[2088]; // [rsp+60h] [rbp-A0h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      a1,
      (unsigned int)Shell32_StartMenuQueryFactory_Internet_Run_Start,
      a3,
      a4,
      (__int64)ppURI);
  *a7 = 0;
  ContinueOnSite = QueryContinueOnSite(*(struct IUnknown **)(a1 + 24));
  if ( ContinueOnSite >= 0 )
  {
    ContinueOnSite = -2147467259;
    if ( !a2 && *(_QWORD *)(a1 + 96) && !(unsigned int)SHWindowsPolicy(POLID_NoRun) )
    {
      v13 = StrCmpNICW(*(LPCWSTR *)(a1 + 96), L"www.", 4)
          ? StringCchCopyW(pwzURI, 0x824u, *(const unsigned __int16 **)(a1 + 96))
          : StringCchPrintfW(pwzURI, 0x824u, L"http://%s", *(_QWORD *)(a1 + 96));
      ContinueOnSite = v13;
      if ( v13 >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(ppURI);
        ContinueOnSite = CreateUri(pwzURI, 0, 0, ppURI);
        if ( ContinueOnSite >= 0 )
        {
          v16 = 0;
          ContinueOnSite = ((__int64 (__fastcall *)(IUri *, int *))ppURI[0]->lpVtbl->GetScheme)(ppURI[0], &v16);
          if ( ContinueOnSite >= 0 )
          {
            if ( (unsigned int)(v16 - 1) > 0xFFFFFFFD )
            {
              ContinueOnSite = -2147024809;
            }
            else
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
              ContinueOnSite = SHCreateItemFromParsingName(pwzURI, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
              if ( ContinueOnSite >= 0 )
                ContinueOnSite = PropertyStoreFromItem((__int64)ppv, 0x1F4u, v14, pwzURI, 0, a6, a7);
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
            }
          }
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)ppURI);
      }
    }
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v9,
      (unsigned int)Shell32_StartMenuQueryFactory_Internet_Run_Stop,
      v11,
      v12,
      (__int64)ppURI);
  return (unsigned int)ContinueOnSite;
}

```

## disassembly

```asm
0x18002c070  push    rbp
0x18002c072  push    rbx
0x18002c073  push    rsi
0x18002c074  push    rdi
0x18002c075  push    r14
0x18002c077  push    r15
0x18002c079  lea     rbp, [rsp-0FC8h]
0x18002c081  mov     eax, 10C8h
0x18002c086  call    _alloca_probe
0x18002c08b  sub     rsp, rax
0x18002c08e  mov     rax, cs:__security_cookie
0x18002c095  xor     rax, rsp
0x18002c098  mov     [rbp+0FF0h+var_40], rax
0x18002c09f  mov     esi, edx
0x18002c0a1  mov     rdi, rcx
0x18002c0a4  mov     r15, [rbp+0FF0h+arg_28]
0x18002c0ab  mov     r14, [rbp+0FF0h+arg_30]
0x18002c0b2  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002c0b9  jz      short loc_18002C0D1
0x18002c0bb  lea     rax, [rsp+10F0h+ppURI]
0x18002c0c0  mov     [rsp+10F0h+var_10D0], rax
0x18002c0c5  lea     rdx, Shell32_StartMenuQueryFactory_Internet_Run_Start
0x18002c0cc  call    McGenEventWrite_EtwEventWriteTransfer
0x18002c0d1  mov     qword ptr [r14], 0
0x18002c0d8  mov     rcx, [rdi+18h]; struct IUnknown *
0x18002c0dc  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18002c0e1  mov     ebx, eax
0x18002c0e3  test    eax, eax
0x18002c0e5  js      loc_18002C229
0x18002c0eb  mov     ebx, 80004005h
0x18002c0f0  test    esi, esi
0x18002c0f2  jnz     loc_18002C229
0x18002c0f8  cmp     qword ptr [rdi+60h], 0
0x18002c0fd  jz      loc_18002C229
0x18002c103  lea     rcx, POLID_NoRun
0x18002c10a  call    cs:__imp_SHWindowsPolicy
0x18002c110  test    eax, eax
0x18002c112  jnz     loc_18002C229
0x18002c118  lea     r8d, [rsi+4]; nChar
0x18002c11c  lea     rdx, aWww; "www."
0x18002c123  mov     rcx, [rdi+60h]; pszStr1
0x18002c127  call    cs:__imp_StrCmpNICW
0x18002c12d  mov     r8, [rdi+60h]; unsigned __int16 *
0x18002c131  mov     edx, 824h; unsigned __int64
0x18002c136  lea     rcx, [rsp+10F0h+pwzURI]; unsigned __int16 *
0x18002c13b  test    eax, eax
0x18002c13d  jnz     short loc_18002C150
0x18002c13f  mov     r9, r8
0x18002c142  lea     r8, aHttpS; "http://%s"
0x18002c149  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c14e  jmp     short loc_18002C155
0x18002c150  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c155  mov     ebx, eax
0x18002c157  test    eax, eax
0x18002c159  js      loc_18002C229
0x18002c15f  lea     rcx, [rsp+10F0h+ppURI]; void *
0x18002c164  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002c169  nop
0x18002c16a  lea     r9, [rsp+10F0h+ppURI]; ppURI
0x18002c16f  xor     r8d, r8d; dwReserved
0x18002c172  xor     edx, edx; dwFlags
0x18002c174  lea     rcx, [rsp+10F0h+pwzURI]; pwzURI
0x18002c179  call    cs:__imp_CreateUri
0x18002c17f  mov     ebx, eax
0x18002c181  test    eax, eax
0x18002c183  js      loc_18002C21F
0x18002c189  mov     [rsp+10F0h+var_10B0], 0
0x18002c191  mov     rcx, [rsp+10F0h+ppURI]
0x18002c196  mov     rax, [rcx]
0x18002c199  lea     rdx, [rsp+10F0h+var_10B0]
0x18002c19e  mov     rax, [rax+0C0h]
0x18002c1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1aa  mov     ebx, eax
0x18002c1ac  test    eax, eax
0x18002c1ae  js      short loc_18002C21F
0x18002c1b0  mov     eax, [rsp+10F0h+var_10B0]
0x18002c1b4  dec     eax
0x18002c1b6  cmp     eax, 0FFFFFFFDh
0x18002c1b9  ja      short loc_18002C21A
0x18002c1bb  lea     rcx, [rsp+10F0h+ppv]; void *
0x18002c1c0  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18002c1c5  nop
0x18002c1c6  lea     r9, [rsp+10F0h+ppv]; ppv
0x18002c1cb  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18002c1d2  xor     edx, edx; pbc
0x18002c1d4  lea     rcx, [rsp+10F0h+pwzURI]; pszPath
0x18002c1d9  call    cs:__imp_SHCreateItemFromParsingName
0x18002c1df  mov     ebx, eax
0x18002c1e1  test    eax, eax
0x18002c1e3  js      short loc_18002C20E
0x18002c1e5  mov     [rsp+10F0h+var_10C0], r14
0x18002c1ea  mov     [rsp+10F0h+var_10C8], r15
0x18002c1ef  mov     [rsp+10F0h+var_10D0], 0
0x18002c1f8  lea     r9, [rsp+10F0h+pwzURI]
0x18002c1fd  mov     edx, 1F4h
0x18002c202  mov     rcx, [rsp+10F0h+ppv]
0x18002c207  call    ?PropertyStoreFromItem@@YAJPEAUIShellItem2@@W4tagSM_GROUP_ID@@HPEBG2AEBU_GUID@@PEAPEAX@Z; PropertyStoreFromItem(IShellItem2 *,tagSM_GROUP_ID,int,ushort const *,ushort const *,_GUID const &,void * *)
0x18002c20c  mov     ebx, eax
0x18002c20e  lea     rcx, [rsp+10F0h+ppv]
0x18002c213  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002c218  jmp     short loc_18002C21F
0x18002c21a  mov     ebx, 80070057h
0x18002c21f  lea     rcx, [rsp+10F0h+ppURI]
0x18002c224  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18002c229  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18002c230  jz      short loc_18002C248
0x18002c232  lea     rax, [rsp+10F0h+ppURI]
0x18002c237  mov     [rsp+10F0h+var_10D0], rax
0x18002c23c  lea     rdx, Shell32_StartMenuQueryFactory_Internet_Run_Stop
0x18002c243  call    McGenEventWrite_EtwEventWriteTransfer
0x18002c248  mov     eax, ebx
0x18002c24a  mov     rcx, [rbp+0FF0h+var_40]
0x18002c251  xor     rcx, rsp; StackCookie
0x18002c254  call    __security_check_cookie
0x18002c259  add     rsp, 10C8h
0x18002c260  pop     r15
0x18002c262  pop     r14
0x18002c264  pop     rdi
0x18002c265  pop     rsi
0x18002c266  pop     rbx
0x18002c267  pop     rbp
0x18002c268  retn
```
