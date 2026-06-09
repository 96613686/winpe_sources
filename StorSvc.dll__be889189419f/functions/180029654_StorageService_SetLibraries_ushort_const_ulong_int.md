# StorageService::SetLibraries(ushort const *,ulong,int)

- ea: `0x180029654`
- end: `0x1800298c6`
- name: `?SetLibraries@StorageService@@IEAAJPEBGKH@Z`
- size: `626`
- prototype: `__int64 __fastcall(StorageService *this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a3f8`

## callees

- `0x180001548`
- `0x18000d030`
- `0x180012ce0`
- `0x18001f824`
- `0x180029654`
- `0x18002d550`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18002971c`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18002971c`
- `RPCRT4!RpcRevertToSelf` at `0x180029847`
- `RPCRT4!RpcRevertToSelf` at `0x180029847`
- `RPCRT4!RpcImpersonateClient` at `0x18002969e`
- `RPCRT4!RpcImpersonateClient` at `0x18002969e`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180029739`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180029739`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StorageService::SetLibraries(StorageService *this, const unsigned __int16 *a2, int a3, int a4)
{
  RPC_STATUS v7; // ebx
  int v8; // r9d
  int v9; // esi
  __int64 v10; // rdi
  int v11; // r12d
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v20; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  ppv = 0;
  v17 = 0;
  v7 = RpcImpersonateClient(0);
  if ( v7 >= 0 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = 32LL * v9;
      if ( (a3 & *(_DWORD *)((_BYTE *)&rgLFI + v10)) == 0 )
        goto LABEL_18;
      v11 = StringCchPrintfW(
              pszPath,
              0x104u,
              L"%s\\%s",
              a2,
              *(struct _LIBRARY_FOLDER_INFO near **)((char *)&rgLFI + v10 + 24));
      v7 = SHLoadLibraryFromKnownFolder((char *)&rgLFI + v10 + 4, v12, v13, &v17);
      if ( v7 >= 0 )
        break;
LABEL_20:
      if ( (unsigned int)++v9 >= 5 )
      {
        RpcRevertToSelf();
        goto LABEL_22;
      }
    }
    if ( a4 )
    {
      if ( !IsApiSetImplemented("api-ms-win-shell-namespace-l1-1-0") )
      {
        v7 = -2147024846;
        goto LABEL_18;
      }
      v7 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( v7 < 0 || (v7 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v17 + 40LL))(v17, ppv), v7 < 0) )
      {
LABEL_18:
        v15 = v17;
        if ( v17 )
        {
          v17 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        goto LABEL_20;
      }
    }
    else
    {
      v18 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v17 + 56LL))(
             v17,
             3,
             &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
             &v18);
      if ( v7 < 0
        || (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v18 + 64LL))(v18, 0, &ppv), v7 < 0) )
      {
        ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&v18);
        goto LABEL_18;
      }
      ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&v18);
    }
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v17 + 80LL))(v17, 2, ppv);
    if ( v7 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 136LL))(v17);
      v7 = v11;
      if ( v14 < 0 )
        v7 = v14;
    }
    goto LABEL_18;
  }
LABEL_22:
  if ( (unsigned int)dword_1800BF000 > 5 )
  {
    LODWORD(v18) = v7;
    v20 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&dword_1800A5C84,
      0,
      v8,
      (__int64)&v20,
      (__int64)&v18);
  }
  ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&v17);
  ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(&ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029654  push    rbp
0x180029656  push    rbx
0x180029657  push    rsi
0x180029658  push    rdi
0x180029659  push    r12
0x18002965b  push    r13
0x18002965d  push    r14
0x18002965f  push    r15
0x180029661  lea     rbp, [rsp-178h]
0x180029669  sub     rsp, 278h
0x180029670  mov     rax, cs:__security_cookie
0x180029677  xor     rax, rsp
0x18002967a  mov     [rbp+1B0h+var_50], rax
0x180029681  mov     r15d, r9d
0x180029684  mov     r13d, r8d
0x180029687  mov     r14, rdx
0x18002968a  mov     [rsp+2B0h+ppv], 0
0x180029693  mov     [rsp+2B0h+var_280], 0
0x18002969c  xor     ecx, ecx; BindingHandle
0x18002969e  call    cs:__imp_RpcImpersonateClient
0x1800296a4  mov     ebx, eax
0x1800296a6  test    eax, eax
0x1800296a8  js      loc_18002984D
0x1800296ae  xor     esi, esi
0x1800296b0  lea     rax, ?rgLFI@@3PAU_LIBRARY_FOLDER_INFO@@A; _LIBRARY_FOLDER_INFO near * rgLFI
0x1800296b7  movsxd  rdi, esi
0x1800296ba  shl     rdi, 5
0x1800296be  test    [rdi+rax], r13d
0x1800296c2  jz      loc_180029816
0x1800296c8  mov     rax, [rdi+rax+18h]
0x1800296cd  mov     [rsp+2B0h+var_290], rax
0x1800296d2  mov     r9, r14
0x1800296d5  lea     r8, aSS; "%s\\%s"
0x1800296dc  mov     edx, 104h; unsigned __int64
0x1800296e1  lea     rcx, [rsp+2B0h+pszPath]; unsigned __int16 *
0x1800296e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800296eb  mov     r12d, eax
0x1800296ee  lea     rcx, ?rgLFI@@3PAU_LIBRARY_FOLDER_INFO@@A; _LIBRARY_FOLDER_INFO near * rgLFI
0x1800296f5  add     rcx, 4
0x1800296f9  add     rcx, rdi
0x1800296fc  lea     r9, [rsp+2B0h+var_280]
0x180029701  call    SHLoadLibraryFromKnownFolder
0x180029706  mov     ebx, eax
0x180029708  test    eax, eax
0x18002970a  js      loc_180029835
0x180029710  test    r15d, r15d
0x180029713  jz      short loc_180029774
0x180029715  lea     rcx, Contract; "api-ms-win-shell-namespace-l1-1-0"
0x18002971c  call    cs:__imp_IsApiSetImplemented
0x180029722  test    eax, eax
0x180029724  jz      short loc_18002976A
0x180029726  lea     r9, [rsp+2B0h+ppv]; ppv
0x18002972b  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180029732  xor     edx, edx; pbc
0x180029734  lea     rcx, [rsp+2B0h+pszPath]; pszPath
0x180029739  call    cs:__imp_SHCreateItemFromParsingName
0x18002973f  mov     ebx, eax
0x180029741  test    eax, eax
0x180029743  js      loc_180029816
0x180029749  mov     rcx, [rsp+2B0h+var_280]
0x18002974e  mov     rax, [rcx]
0x180029751  mov     rdx, [rsp+2B0h+ppv]
0x180029756  mov     rax, [rax+28h]
0x18002975a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002975f  mov     ebx, eax
0x180029761  test    eax, eax
0x180029763  jns     short loc_1800297D9
0x180029765  jmp     loc_180029816
0x18002976a  mov     ebx, 80070032h
0x18002976f  jmp     loc_180029816
0x180029774  mov     [rsp+2B0h+var_278], 0
0x18002977d  mov     rcx, [rsp+2B0h+var_280]
0x180029782  mov     rax, [rcx]
0x180029785  lea     r9, [rsp+2B0h+var_278]
0x18002978a  lea     r8, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180029791  mov     edx, 3
0x180029796  mov     rax, [rax+38h]
0x18002979a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002979f  mov     ebx, eax
0x1800297a1  test    eax, eax
0x1800297a3  jns     short loc_1800297B1
0x1800297a5  lea     rcx, [rsp+2B0h+var_278]
0x1800297aa  call    ??1?$CComPtr@UIKnownFolderManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(void)
0x1800297af  jmp     short loc_180029816
0x1800297b1  mov     rcx, [rsp+2B0h+var_278]
0x1800297b6  mov     rax, [rcx]
0x1800297b9  lea     r8, [rsp+2B0h+ppv]
0x1800297be  xor     edx, edx
0x1800297c0  mov     rax, [rax+40h]
0x1800297c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297c9  mov     ebx, eax
0x1800297cb  lea     rcx, [rsp+2B0h+var_278]
0x1800297d0  test    eax, eax
0x1800297d2  js      short loc_1800297AA
0x1800297d4  call    ??1?$CComPtr@UIKnownFolderManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(void)
0x1800297d9  mov     rcx, [rsp+2B0h+var_280]
0x1800297de  mov     rax, [rcx]
0x1800297e1  mov     r8, [rsp+2B0h+ppv]
0x1800297e6  mov     edx, 2
0x1800297eb  mov     rax, [rax+50h]
0x1800297ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f4  mov     ebx, eax
0x1800297f6  test    eax, eax
0x1800297f8  js      short loc_180029816
0x1800297fa  mov     rcx, [rsp+2B0h+var_280]
0x1800297ff  mov     rax, [rcx]
0x180029802  mov     rax, [rax+88h]
0x180029809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002980e  mov     ebx, r12d
0x180029811  test    eax, eax
0x180029813  cmovs   ebx, eax
0x180029816  mov     rcx, [rsp+2B0h+var_280]
0x18002981b  test    rcx, rcx
0x18002981e  jz      short loc_180029835
0x180029820  mov     [rsp+2B0h+var_280], 0
0x180029829  mov     rax, [rcx]
0x18002982c  mov     rax, [rax+10h]
0x180029830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029835  inc     esi
0x180029837  cmp     esi, 5
0x18002983a  lea     rax, ?rgLFI@@3PAU_LIBRARY_FOLDER_INFO@@A; _LIBRARY_FOLDER_INFO near * rgLFI
0x180029841  jb      loc_1800296B7
0x180029847  call    cs:__imp_RpcRevertToSelf
0x18002984d  mov     eax, cs:dword_1800BF000
0x180029853  cmp     eax, 5
0x180029856  jbe     short loc_18002988C
0x180029858  mov     dword ptr [rsp+2B0h+var_278], ebx
0x18002985c  mov     [rsp+2B0h+var_268], r14
0x180029861  lea     rax, [rsp+2B0h+var_278]
0x180029866  mov     [rsp+2B0h+var_288], rax
0x18002986b  lea     rax, [rsp+2B0h+var_268]
0x180029870  mov     [rsp+2B0h+var_290], rax
0x180029875  xor     r8d, r8d
0x180029878  lea     rdx, dword_1800A5C84
0x18002987f  lea     rcx, dword_1800BF000
0x180029886  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002988b  nop
0x18002988c  lea     rcx, [rsp+2B0h+var_280]
0x180029891  call    ??1?$CComPtr@UIKnownFolderManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(void)
0x180029896  nop
0x180029897  lea     rcx, [rsp+2B0h+ppv]
0x18002989c  call    ??1?$CComPtr@UIKnownFolderManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IKnownFolderManager>::~CComPtr<IKnownFolderManager>(void)
0x1800298a1  mov     eax, ebx
0x1800298a3  mov     rcx, [rbp+1B0h+var_50]
0x1800298aa  xor     rcx, rsp; StackCookie
0x1800298ad  call    __security_check_cookie
0x1800298b2  add     rsp, 278h
0x1800298b9  pop     r15
0x1800298bb  pop     r14
0x1800298bd  pop     r13
0x1800298bf  pop     r12
0x1800298c1  pop     rdi
0x1800298c2  pop     rsi
0x1800298c3  pop     rbx
0x1800298c4  pop     rbp
0x1800298c5  retn
```
