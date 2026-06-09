# RequestRestart(ushort const *,ulong,ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x180019dc4`
- end: `0x18001a186`
- name: `?RequestRestart@@YAJPEBGKK000@Z`
- size: `962`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, UINT uID, UINT, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000a1f8`
- `0x18000de18`
- `0x18000e48c`
- `0x180019dc4`
- `0x18001a42c`
- `0x18001bddc`
- `0x1800243e8`
- `0x18003c0b8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019fbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019fbe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019fde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019ff8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019fde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019ff8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019e70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019e70`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a126`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001a126`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180019f80`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180019f80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ec8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ec8`

## string_xrefs

- `0x180019ede`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x180019f35`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001a06a`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x18001a0e9`: `onecore\base\ngscb\tpm\task\dll\tpmtasks.cpp`
- `0x180019fb7`: `TpmTasks.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall RequestRestart(
        LPCWSTR lpValueName,
        UINT uID,
        UINT a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  signed int v10; // ebx
  LSTATUS ValueW; // eax
  HRESULT v12; // eax
  __int64 v13; // rax
  HRESULT v14; // eax
  __int64 v15; // rdx
  HMODULE ModuleHandleW; // rax
  HINSTANCE v17; // rbx
  unsigned int v18; // r11d
  int restarted; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v21; // eax
  __int64 v22; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Data; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pvData; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hkey[2]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v32; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v33[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+3F8h]

  v32 = a6;
  hkey[0] = 0;
  pvData = 1;
  v10 = wil::reg::open_unique_key_nothrow(
          lpValueName,
          L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
          hkey,
          1);
  if ( v10 >= 0 )
  {
    Data = 4;
    ValueW = RegGetValueW(hkey[0], 0, lpValueName, 0x10u, 0, &pvData, &Data);
    v10 = ValueW;
    if ( ValueW > 0 )
      v10 = (unsigned __int16)ValueW | 0x80070000;
    if ( v10 == -2147024894 )
    {
      SBServicingLogMessage((wchar_t *)L"RequestRestart for %ls", a5);
      ppv = 0;
      v12 = CoCreateInstance(
              &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
              0,
              4u,
              &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
              &ppv);
      v10 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
          (const char *)(unsigned int)v12,
          pdwType);
LABEL_27:
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
        goto LABEL_28;
      }
      pProxy = 0;
      v13 = *(_QWORD *)ppv;
      pProxy = 0;
      v14 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const WCHAR *, IUnknown **))(v13 + 24))(
              ppv,
              L"Secure Boot Key Rolling",
              &sourceString,
              &pProxy);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = 304;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
          (const char *)(unsigned int)v14,
          pdwType);
LABEL_26:
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&pProxy);
        goto LABEL_27;
      }
      v14 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = 314;
        goto LABEL_9;
      }
      memset_0(Buffer, 0, 0x208u);
      memset_0(v33, 0, 0x208u);
      ModuleHandleW = GetModuleHandleW(L"TpmTasks.dll");
      v17 = ModuleHandleW;
      if ( !ModuleHandleW || !LoadStringW(ModuleHandleW, uID, Buffer, 260) || !LoadStringW(v17, a3, v33, 260) )
      {
        SBServicingLogMessage((wchar_t *)L"Using default strings for %d", uID);
        StringCchCopyW(Buffer, 0x104u, a4);
        StringCchCopyW(v33, v18, a5);
      }
      v28 = 0;
      restarted = Microsoft::WRL::Details::MakeAndInitialize<RestartPropertiesNoDeadline,IRestartPropertiesNoDeadline,unsigned short (&)[260],unsigned short (&)[260],unsigned short const * &>(
                    &v28,
                    Buffer,
                    v33,
                    &v32);
      v10 = restarted;
      if ( restarted < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
          (const char *)(unsigned int)restarted,
          pdwType);
LABEL_25:
        ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v28);
        goto LABEL_26;
      }
      v27 = 0;
      lpVtbl = pProxy->lpVtbl;
      v27 = 0;
      v21 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
              pProxy,
              &GUID_c78535aa_5c24_4f1c_9367_90ddd54e745c,
              &v27);
      v10 = v21;
      if ( v21 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v27 + 360LL))(
                v27,
                L"SecureBootKeyRollingUniqueId",
                v28);
        v10 = v21;
        if ( v21 >= 0 )
        {
          v10 = 0;
          Data = pvData;
          RegSetKeyValueW(hkey[0], 0, lpValueName, 4u, &Data, 4u);
          goto LABEL_24;
        }
        v22 = 353;
      }
      else
      {
        v22 = 350;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\task\\dll\\tpmtasks.cpp",
        (const char *)(unsigned int)v21,
        pdwType);
LABEL_24:
      ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v27);
      goto LABEL_25;
    }
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hkey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019dc4  push    rbp
0x180019dc6  push    rbx
0x180019dc7  push    rsi
0x180019dc8  push    rdi
0x180019dc9  push    r12
0x180019dcb  push    r14
0x180019dcd  push    r15
0x180019dcf  lea     rbp, [rsp-3C0h]
0x180019dd7  sub     rsp, 4C0h
0x180019dde  mov     rax, cs:__security_cookie
0x180019de5  xor     rax, rsp
0x180019de8  mov     [rbp+3F0h+var_40], rax
0x180019def  mov     r12, r9
0x180019df2  mov     r15d, r8d
0x180019df5  mov     edi, edx
0x180019df7  mov     r14, rcx
0x180019dfa  mov     rsi, [rbp+3F0h+arg_20]
0x180019e01  mov     rax, [rbp+3F0h+arg_28]
0x180019e08  mov     [rbp+3F0h+var_470], rax
0x180019e0c  mov     [rsp+4F0h+hkey], 0
0x180019e15  mov     r9d, 1
0x180019e1b  mov     [rsp+4F0h+var_490], r9d
0x180019e20  lea     r8, [rsp+4F0h+hkey]
0x180019e25  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180019e2c  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180019e31  mov     ebx, eax
0x180019e33  test    eax, eax
0x180019e35  js      loc_18001A159
0x180019e3b  mov     [rsp+4F0h+Data], 4
0x180019e43  lea     rax, [rsp+4F0h+Data]
0x180019e48  mov     [rsp+4F0h+pcbData], rax; pcbData
0x180019e4d  lea     rax, [rsp+4F0h+var_490]
0x180019e52  mov     [rsp+4F0h+pvData], rax; pvData
0x180019e57  mov     [rsp+4F0h+pdwType], 0; pdwType
0x180019e60  mov     r9d, 10h; dwFlags
0x180019e66  mov     r8, r14; lpValue
0x180019e69  xor     edx, edx; lpSubKey
0x180019e6b  mov     rcx, [rsp+4F0h+hkey]; hkey
0x180019e70  call    cs:__imp_RegGetValueW
0x180019e76  mov     ebx, eax
0x180019e78  test    eax, eax
0x180019e7a  jle     short loc_180019E85
0x180019e7c  movzx   ebx, ax
0x180019e7f  or      ebx, 80070000h
0x180019e85  cmp     ebx, 80070002h
0x180019e8b  jnz     loc_18001A159
0x180019e91  mov     rdx, rsi
0x180019e94  lea     rcx, aRequestrestart; "RequestRestart for %ls"
0x180019e9b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180019ea0  nop
0x180019ea1  mov     [rsp+4F0h+ppv], 0
0x180019eaa  lea     rax, [rsp+4F0h+ppv]
0x180019eaf  mov     [rsp+4F0h+pdwType], rax; int
0x180019eb4  lea     r9, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a; riid
0x180019ebb  xor     edx, edx; pUnkOuter
0x180019ebd  lea     r8d, [rdx+4]; dwClsContext
0x180019ec1  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x180019ec8  call    cs:__imp_CoCreateInstance
0x180019ece  mov     ebx, eax
0x180019ed0  test    eax, eax
0x180019ed2  jns     short loc_180019EF4
0x180019ed4  mov     rcx, [rbp+3F8h]; this
0x180019edb  mov     r9d, eax; char *
0x180019ede  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x180019ee5  mov     edx, 12Dh; void *
0x180019eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eef  jmp     loc_18001A14E
0x180019ef4  mov     [rsp+4F0h+pProxy], 0
0x180019efd  mov     rcx, [rsp+4F0h+ppv]
0x180019f02  mov     rax, [rcx]
0x180019f05  mov     [rsp+4F0h+pProxy], 0
0x180019f0e  lea     r9, [rsp+4F0h+pProxy]
0x180019f13  lea     r8, sourceString
0x180019f1a  lea     rdx, aSecureBootKeyR; "Secure Boot Key Rolling"
0x180019f21  mov     rax, [rax+18h]
0x180019f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f2a  mov     ebx, eax
0x180019f2c  test    eax, eax
0x180019f2e  jns     short loc_180019F50
0x180019f30  mov     edx, 130h; void *
0x180019f35  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x180019f3c  mov     r9d, eax; char *
0x180019f3f  mov     rcx, [rbp+3F8h]; this
0x180019f46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f4b  jmp     loc_18001A143
0x180019f50  mov     [rsp+4F0h+dwCapabilities], 0; dwCapabilities
0x180019f58  mov     [rsp+4F0h+pcbData], 0; pAuthInfo
0x180019f61  mov     dword ptr [rsp+4F0h+pvData], 3; dwImpLevel
0x180019f69  mov     dword ptr [rsp+4F0h+pdwType], 0; int
0x180019f71  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180019f75  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180019f78  mov     r8d, edx; dwAuthzSvc
0x180019f7b  mov     rcx, [rsp+4F0h+pProxy]; pProxy
0x180019f80  call    cs:__imp_CoSetProxyBlanket
0x180019f86  mov     ebx, eax
0x180019f88  test    eax, eax
0x180019f8a  jns     short loc_180019F93
0x180019f8c  mov     edx, 13Ah
0x180019f91  jmp     short loc_180019F35
0x180019f93  mov     ebx, 208h
0x180019f98  mov     r8d, ebx; Size
0x180019f9b  xor     edx, edx; Val
0x180019f9d  lea     rcx, [rbp+3F0h+Buffer]; void *
0x180019fa4  call    memset_0
0x180019fa9  mov     r8d, ebx; Size
0x180019fac  xor     edx, edx; Val
0x180019fae  lea     rcx, [rbp+3F0h+var_460]; void *
0x180019fb2  call    memset_0
0x180019fb7  lea     rcx, aTpmtasksDll_0; "TpmTasks.dll"
0x180019fbe  call    cs:__imp_GetModuleHandleW
0x180019fc4  mov     rbx, rax
0x180019fc7  test    rax, rax
0x180019fca  jz      short loc_18001A002
0x180019fcc  mov     r9d, 104h; cchBufferMax
0x180019fd2  lea     r8, [rbp+3F0h+Buffer]; lpBuffer
0x180019fd9  mov     edx, edi; uID
0x180019fdb  mov     rcx, rax; hInstance
0x180019fde  call    cs:__imp_LoadStringW
0x180019fe4  test    eax, eax
0x180019fe6  jz      short loc_18001A002
0x180019fe8  mov     r9d, 104h; cchBufferMax
0x180019fee  lea     r8, [rbp+3F0h+var_460]; lpBuffer
0x180019ff2  mov     edx, r15d; uID
0x180019ff5  mov     rcx, rbx; hInstance
0x180019ff8  call    cs:__imp_LoadStringW
0x180019ffe  test    eax, eax
0x18001a000  jnz     short loc_18001A038
0x18001a002  mov     edx, edi
0x18001a004  lea     rcx, aUsingDefaultSt; "Using default strings for %d"
0x18001a00b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18001a010  mov     r8, r12; unsigned __int16 *
0x18001a013  mov     r11d, 104h
0x18001a019  mov     edx, r11d; unsigned __int64
0x18001a01c  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x18001a023  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a028  mov     r8, rsi; unsigned __int16 *
0x18001a02b  mov     edx, r11d; unsigned __int64
0x18001a02e  lea     rcx, [rbp+3F0h+var_460]; unsigned __int16 *
0x18001a032  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a037  nop
0x18001a038  mov     [rsp+4F0h+var_498], 0
0x18001a041  lea     r9, [rbp+3F0h+var_470]
0x18001a045  lea     r8, [rbp+3F0h+var_460]
0x18001a049  lea     rdx, [rbp+3F0h+Buffer]
0x18001a050  lea     rcx, [rsp+4F0h+var_498]
0x18001a055  call    ??$MakeAndInitialize@VRestartPropertiesNoDeadline@@UIRestartPropertiesNoDeadline@@AEAY0BAE@GAEAY0BAE@GAEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUIRestartPropertiesNoDeadline@@AEAY0BAE@G1AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<RestartPropertiesNoDeadline,IRestartPropertiesNoDeadline,ushort (&)[260],ushort (&)[260],ushort const * &>(IRestartPropertiesNoDeadline * *,ushort (&)[260],ushort (&)[260],ushort const * &)
0x18001a05a  mov     ebx, eax
0x18001a05c  test    eax, eax
0x18001a05e  jns     short loc_18001A080
0x18001a060  mov     rcx, [rbp+3F8h]; this
0x18001a067  mov     r9d, eax; char *
0x18001a06a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001a071  mov     edx, 15Bh; void *
0x18001a076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a07b  jmp     loc_18001A138
0x18001a080  mov     [rsp+4F0h+var_4A0], 0
0x18001a089  mov     rcx, [rsp+4F0h+pProxy]
0x18001a08e  mov     rax, [rcx]
0x18001a091  mov     [rsp+4F0h+var_4A0], 0
0x18001a09a  lea     r8, [rsp+4F0h+var_4A0]
0x18001a09f  lea     rdx, _GUID_c78535aa_5c24_4f1c_9367_90ddd54e745c
0x18001a0a6  mov     rax, [rax]
0x18001a0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ae  mov     ebx, eax
0x18001a0b0  test    eax, eax
0x18001a0b2  jns     short loc_18001A0BB
0x18001a0b4  mov     edx, 15Eh
0x18001a0b9  jmp     short loc_18001A0E6
0x18001a0bb  mov     rcx, [rsp+4F0h+var_4A0]
0x18001a0c0  mov     rax, [rcx]
0x18001a0c3  mov     r8, [rsp+4F0h+var_498]
0x18001a0c8  lea     rdx, aSecurebootkeyr; "SecureBootKeyRollingUniqueId"
0x18001a0cf  mov     rax, [rax+168h]
0x18001a0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0db  mov     ebx, eax
0x18001a0dd  test    eax, eax
0x18001a0df  jns     short loc_18001A0FE
0x18001a0e1  mov     edx, 161h; void *
0x18001a0e6  mov     r9d, eax; char *
0x18001a0e9  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\tpm\\task\\dll\\t"...
0x18001a0f0  mov     rcx, [rbp+3F8h]; this
0x18001a0f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0fc  jmp     short loc_18001A12D
0x18001a0fe  xor     ebx, ebx
0x18001a100  mov     eax, [rsp+4F0h+var_490]
0x18001a104  mov     [rsp+4F0h+Data], eax
0x18001a108  lea     ecx, [rbx+4]
0x18001a10b  mov     dword ptr [rsp+4F0h+pvData], ecx; cbData
0x18001a10f  lea     rax, [rsp+4F0h+Data]
0x18001a114  mov     [rsp+4F0h+pdwType], rax; lpData
0x18001a119  mov     r9d, ecx; dwType
0x18001a11c  mov     r8, r14; lpValueName
0x18001a11f  xor     edx, edx; lpSubKey
0x18001a121  mov     rcx, [rsp+4F0h+hkey]; hKey
0x18001a126  call    cs:__imp_RegSetKeyValueW
0x18001a12c  nop
0x18001a12d  lea     rcx, [rsp+4F0h+var_4A0]
0x18001a132  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a137  nop
0x18001a138  lea     rcx, [rsp+4F0h+var_498]
0x18001a13d  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a142  nop
0x18001a143  lea     rcx, [rsp+4F0h+pProxy]
0x18001a148  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a14d  nop
0x18001a14e  lea     rcx, [rsp+4F0h+ppv]
0x18001a153  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x18001a158  nop
0x18001a159  lea     rcx, [rsp+4F0h+hkey]
0x18001a15e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a163  mov     eax, ebx
0x18001a165  mov     rcx, [rbp+3F0h+var_40]
0x18001a16c  xor     rcx, rsp; StackCookie
0x18001a16f  call    __security_check_cookie
0x18001a174  add     rsp, 4C0h
0x18001a17b  pop     r15
0x18001a17d  pop     r14
0x18001a17f  pop     r12
0x18001a181  pop     rdi
0x18001a182  pop     rsi
0x18001a183  pop     rbx
0x18001a184  pop     rbp
0x18001a185  retn
```
