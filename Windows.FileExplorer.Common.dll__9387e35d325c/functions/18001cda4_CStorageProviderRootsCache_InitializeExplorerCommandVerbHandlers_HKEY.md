# CStorageProviderRootsCache::InitializeExplorerCommandVerbHandlers(HKEY__ *)

- ea: `0x18001cda4`
- end: `0x18001d021`
- name: `?InitializeExplorerCommandVerbHandlers@CStorageProviderRootsCache@@AEAAJPEAUHKEY__@@@Z`
- size: `637`
- prototype: `int(CStorageProviderRootsCache *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016fe8`

## callees

- `0x18000606c`
- `0x1800077c8`
- `0x180007900`
- `0x180007c24`
- `0x180007d34`
- `0x18001cda4`
- `0x18001d028`
- `0x180037780`
- `0x180037c20`
- `0x180037ca0`

## import_xrefs

- `SHCORE!__imp_GUIDFromStringW` at `0x18001ceac`
- `SHCORE!__imp_GUIDFromStringW` at `0x18001ceac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cfd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ce6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cf81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cfd0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce45`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ce45`

## string_xrefs

- `0x18001cf67`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18001cf9a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18001cfb5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18001cfe4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageProviderRootsCache::InitializeExplorerCommandVerbHandlers(
        CStorageProviderRootsCache *this,
        HKEY a2)
{
  unsigned int i; // esi
  int v5; // eax
  unsigned int v6; // ebx
  WCHAR *v7; // rbx
  LSTATUS ValueW; // eax
  bool v9; // sf
  const unsigned __int16 *v11; // rdi
  StateRepoHelpers::ExplorerCommandVerb *v12; // rax
  int v13; // eax
  unsigned int v14; // edi
  void *v15; // rdi
  void *v16; // rbx
  int pdwType; // [rsp+20h] [rbp-89h]
  LPCWSTR lpValue[2]; // [rsp+40h] [rbp-69h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-59h] BYREF
  StateRepoHelpers::ExplorerCommandVerb *v20; // [rsp+60h] [rbp-49h]
  __int128 v21; // [rsp+70h] [rbp-39h] BYREF
  _WORD pvData[40]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  for ( i = 0; ; ++i )
  {
    if ( i >= 0x32 )
      return 0;
    lpValue[0] = 0;
    v5 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           lpValue,
           L"%s_%d",
           L"MenuVerbHandler",
           i);
    v6 = v5;
    if ( v5 < 0 )
      break;
    pcbData[0] = 78;
    v7 = (WCHAR *)lpValue[0];
    ValueW = RegGetValueW(a2, 0, lpValue[0], 2u, 0, pvData, pcbData);
    v9 = ValueW < 0;
    if ( ValueW )
    {
      pvData[0] = 0;
      v9 = ValueW < 0;
      if ( ValueW > 0 )
        v9 = 1;
    }
    if ( v9 )
    {
      if ( v7 )
        CoTaskMemFree(v7);
      return 0;
    }
    v21 = 0;
    if ( !(unsigned int)GUIDFromStringW(pvData, &v21) )
    {
      v14 = -2147023266;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB43,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)0x8007065ELL,
        pdwType);
LABEL_23:
      if ( v7 )
        CoTaskMemFree(v7);
      return v14;
    }
    v11 = &String1;
    if ( *((_QWORD *)this + 15) )
      v11 = (const unsigned __int16 *)*((_QWORD *)this + 15);
    v12 = (StateRepoHelpers::ExplorerCommandVerb *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v20 = v12;
    if ( v12 )
    {
      *(_OWORD *)pcbData = v21;
      v12 = (StateRepoHelpers::ExplorerCommandVerb *)StateRepoHelpers::ExplorerCommandVerb::ExplorerCommandVerb(
                                                       v12,
                                                       v11,
                                                       v7,
                                                       (struct _GUID *)pcbData);
    }
    *(_QWORD *)pcbData = v12;
    if ( !v12 )
    {
      v14 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB47,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)0x8007000ELL,
        pdwType);
      goto LABEL_23;
    }
    v13 = CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_Add<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>> &&>(
            (char *)this + 592,
            pcbData);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB48,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v13,
        pdwType);
      v16 = *(void **)pcbData;
      if ( *(_QWORD *)pcbData )
      {
        StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(*(StateRepoHelpers::ExplorerCommandVerb **)pcbData);
        operator delete(v16, (const struct std::nothrow_t *)0x20);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(lpValue);
      return v14;
    }
    v15 = *(void **)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(*(StateRepoHelpers::ExplorerCommandVerb **)pcbData);
      operator delete(v15, (const struct std::nothrow_t *)0x20);
    }
    if ( v7 )
      CoTaskMemFree(v7);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB3F,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v5,
    pdwType);
  if ( lpValue[0] )
    CoTaskMemFree((LPVOID)lpValue[0]);
  return v6;
}

```

## disassembly

```asm
0x18001cda4  mov     [rsp-8+arg_10], rbx
0x18001cda9  mov     [rsp-8+arg_18], rsi
0x18001cdae  push    rbp
0x18001cdaf  push    rdi
0x18001cdb0  push    r13
0x18001cdb2  push    r14
0x18001cdb4  push    r15
0x18001cdb6  lea     rbp, [rsp-37h]
0x18001cdbb  sub     rsp, 0E0h
0x18001cdc2  mov     rax, cs:__security_cookie
0x18001cdc9  xor     rax, rsp
0x18001cdcc  mov     [rbp+57h+var_30], rax
0x18001cdd0  mov     r15, rdx
0x18001cdd3  mov     r14, rcx
0x18001cdd6  xor     esi, esi
0x18001cdd8  lea     r13d, [rsi+20h]
0x18001cddc  cmp     esi, 32h ; '2'
0x18001cddf  jnb     loc_18001CE73
0x18001cde5  mov     [rbp+57h+lpValue], 0
0x18001cded  mov     r9d, esi
0x18001cdf0  lea     r8, aMenuverbhandle; "MenuVerbHandler"
0x18001cdf7  lea     rdx, aSD; "%s_%d"
0x18001cdfe  lea     rcx, [rbp+57h+lpValue]
0x18001ce02  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001ce07  mov     ebx, eax
0x18001ce09  test    eax, eax
0x18001ce0b  js      loc_18001CFAE
0x18001ce11  mov     [rbp+57h+var_B0], 4Eh ; 'N'
0x18001ce18  lea     rax, [rbp+57h+var_B0]
0x18001ce1c  mov     [rsp+100h+pcbData], rax; pcbData
0x18001ce21  lea     rax, [rbp+57h+var_80]
0x18001ce25  mov     [rsp+100h+pvData], rax; pvData
0x18001ce2a  mov     [rsp+100h+pdwType], 0; int
0x18001ce33  mov     r9d, 2; dwFlags
0x18001ce39  mov     rbx, [rbp+57h+lpValue]
0x18001ce3d  mov     r8, rbx; lpValue
0x18001ce40  xor     edx, edx; lpSubKey
0x18001ce42  mov     rcx, r15; hkey
0x18001ce45  call    cs:__imp_RegGetValueW
0x18001ce4b  test    eax, eax
0x18001ce4d  jz      short loc_18001CE63
0x18001ce4f  xor     ecx, ecx
0x18001ce51  mov     [rbp+57h+var_80], cx
0x18001ce55  test    eax, eax
0x18001ce57  jle     short loc_18001CE63
0x18001ce59  movzx   eax, ax
0x18001ce5c  or      eax, 80070000h
0x18001ce61  test    eax, eax
0x18001ce63  jns     short loc_18001CE9D
0x18001ce65  test    rbx, rbx
0x18001ce68  jz      short loc_18001CE73
0x18001ce6a  mov     rcx, rbx; pv
0x18001ce6d  call    cs:__imp_CoTaskMemFree
0x18001ce73  xor     eax, eax
0x18001ce75  mov     rcx, [rbp+57h+var_30]
0x18001ce79  xor     rcx, rsp; StackCookie
0x18001ce7c  call    __security_check_cookie
0x18001ce81  lea     r11, [rsp+100h+var_20]
0x18001ce89  mov     rbx, [r11+40h]
0x18001ce8d  mov     rsi, [r11+48h]
0x18001ce91  mov     rsp, r11
0x18001ce94  pop     r15
0x18001ce96  pop     r14
0x18001ce98  pop     r13
0x18001ce9a  pop     rdi
0x18001ce9b  pop     rbp
0x18001ce9c  retn
0x18001ce9d  xorps   xmm0, xmm0
0x18001cea0  movups  [rbp+57h+var_90], xmm0
0x18001cea4  lea     rdx, [rbp+57h+var_90]
0x18001cea8  lea     rcx, [rbp+57h+var_80]
0x18001ceac  call    cs:__imp_GUIDFromStringW
0x18001ceb2  test    eax, eax
0x18001ceb4  jz      loc_18001CF5B
0x18001ceba  lea     rdi, String1
0x18001cec1  cmp     qword ptr [r14+78h], 0
0x18001cec6  cmovnz  rdi, [r14+78h]
0x18001cecb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ced2  mov     rcx, r13; unsigned __int64
0x18001ced5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ceda  mov     [rbp+57h+var_A0], rax
0x18001cede  test    rax, rax
0x18001cee1  jz      short loc_18001CEFF
0x18001cee3  movaps  xmm0, [rbp+57h+var_90]
0x18001cee7  movdqa  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001ceec  lea     r9, [rbp+57h+var_B0]; struct _GUID
0x18001cef0  mov     r8, rbx; unsigned __int16 *
0x18001cef3  mov     rdx, rdi; unsigned __int16 *
0x18001cef6  mov     rcx, rax; this
0x18001cef9  call    ??0ExplorerCommandVerb@StateRepoHelpers@@QEAA@PEBG0U_GUID@@@Z; StateRepoHelpers::ExplorerCommandVerb::ExplorerCommandVerb(ushort const *,ushort const *,_GUID)
0x18001cefe  nop
0x18001ceff  mov     qword ptr [rbp+57h+var_B0], rax
0x18001cf03  test    rax, rax
0x18001cf06  jz      loc_18001CF8E
0x18001cf0c  lea     rcx, [r14+250h]
0x18001cf13  lea     rdx, [rbp+57h+var_B0]
0x18001cf17  call    ??$_Add@$$QEAV?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@?$CTSimpleArray@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardCompareHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardMergeHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@@@QEAAJ$$QEAV?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@PEA_K@Z; CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_Add<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>> &&>(wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>> &&,unsigned __int64 *)
0x18001cf1c  mov     edi, eax
0x18001cf1e  test    eax, eax
0x18001cf20  js      loc_18001CFDD
0x18001cf26  mov     rdi, qword ptr [rbp+57h+var_B0]
0x18001cf2a  test    rdi, rdi
0x18001cf2d  jz      short loc_18001CF42
0x18001cf2f  mov     rcx, rdi; this
0x18001cf32  call    ??1ExplorerCommandVerb@StateRepoHelpers@@QEAA@XZ; StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(void)
0x18001cf37  mov     rdx, r13; struct std::nothrow_t *
0x18001cf3a  mov     rcx, rdi; void *
0x18001cf3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001cf42  inc     esi
0x18001cf44  test    rbx, rbx
0x18001cf47  jz      loc_18001CDDC
0x18001cf4d  mov     rcx, rbx; pv
0x18001cf50  call    cs:__imp_CoTaskMemFree
0x18001cf56  jmp     loc_18001CDDC
0x18001cf5b  mov     rcx, [rbp+5Fh]; this
0x18001cf5f  mov     edi, 8007065Eh
0x18001cf64  mov     r9d, edi; char *
0x18001cf67  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001cf6e  mov     edx, 0B43h; void *
0x18001cf73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf78  nop
0x18001cf79  test    rbx, rbx
0x18001cf7c  jz      short loc_18001CF87
0x18001cf7e  mov     rcx, rbx; pv
0x18001cf81  call    cs:__imp_CoTaskMemFree
0x18001cf87  mov     eax, edi
0x18001cf89  jmp     loc_18001CE75
0x18001cf8e  mov     rcx, [rbp+5Fh]; this
0x18001cf92  mov     edi, 8007000Eh
0x18001cf97  mov     r9d, edi; char *
0x18001cf9a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001cfa1  mov     edx, 0B47h; void *
0x18001cfa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfab  nop
0x18001cfac  jmp     short loc_18001CF79
0x18001cfae  mov     rcx, [rbp+5Fh]; this
0x18001cfb2  mov     r9d, ebx; char *
0x18001cfb5  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001cfbc  mov     edx, 0B3Fh; void *
0x18001cfc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfc6  nop
0x18001cfc7  mov     rcx, [rbp+57h+lpValue]; pv
0x18001cfcb  test    rcx, rcx
0x18001cfce  jz      short loc_18001CFD6
0x18001cfd0  call    cs:__imp_CoTaskMemFree
0x18001cfd6  mov     eax, ebx
0x18001cfd8  jmp     loc_18001CE75
0x18001cfdd  mov     rcx, [rbp+5Fh]; this
0x18001cfe1  mov     r9d, edi; char *
0x18001cfe4  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001cfeb  mov     edx, 0B48h; void *
0x18001cff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cff5  nop
0x18001cff6  mov     rbx, qword ptr [rbp+57h+var_B0]
0x18001cffa  test    rbx, rbx
0x18001cffd  jz      short loc_18001D013
0x18001cfff  mov     rcx, rbx; this
0x18001d002  call    ??1ExplorerCommandVerb@StateRepoHelpers@@QEAA@XZ; StateRepoHelpers::ExplorerCommandVerb::~ExplorerCommandVerb(void)
0x18001d007  mov     rdx, r13; struct std::nothrow_t *
0x18001d00a  mov     rcx, rbx; void *
0x18001d00d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d012  nop
0x18001d013  lea     rcx, [rbp+57h+lpValue]; void *
0x18001d017  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001d01c  jmp     loc_18001CF87
```
