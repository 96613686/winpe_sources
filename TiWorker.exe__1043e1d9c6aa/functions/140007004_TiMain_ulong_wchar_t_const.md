# TiMain(ulong,wchar_t * * const)

- ea: `0x140007004`
- end: `0x140007221`
- name: `?TiMain@@YAXKQEAPEA_W@Z`
- size: `541`
- prototype: `void __fastcall(__int64, wchar_t **const)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000766c`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x140006d68`
- `0x140006e70`
- `0x140007004`
- `0x140007228`
- `0x14000e328`
- `0x14000f5b0`
- `0x140010800`
- `0x140016bf8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400070d9`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1400070d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400070e3`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400070b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400070b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007061`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007061`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000712d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000712d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400071f7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400071f7`

## string_xrefs

- `0x14000706d`: `Failed to initialize COM.`
- `0x1400070c3`: `Failed to initialize COM security.`
- `0x140007137`: `Failed to access COM GlobalOptions object`
- `0x14000715d`: `Failed to set COM GlobalOptions, exception handling still in place.`
- `0x140007190`: `Failed to set COM unmarshaling policy to strong`
- `0x1400071a2`: `Failed to initialize Trusted Installer.`

## pseudocode

```c
void __fastcall TiMain(__int64 a1, wchar_t **const a2)
{
  int ModulePath; // eax
  wchar_t *v3; // rsi
  HRESULT v4; // eax
  int v5; // ebp
  int v6; // eax
  const char *v7; // r9
  signed int LastError; // eax
  bool v9; // sf
  int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  wchar_t *v12; // [rsp+50h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-20h] BYREF

  ppv = 0;
  v12 = 0;
  ModulePath = PathGetModulePath((__int64)&v12);
  v3 = v12;
  if ( ModulePath >= 0 )
    WdsLoad(v12, 0);
  LogAdapter::g_Logger = (struct LogAdapter::Logger *)&vWdsLogger;
  v4 = CoInitializeEx(0, 0);
  if ( v4 < 0 )
  {
    v5 = 0;
    CBSWdsLog(0x4000000, (unsigned int)v4, 1, "Failed to initialize COM.");
    goto LABEL_23;
  }
  v5 = 1;
  v6 = CoInitializeSecurity(0, -1, 0, 0, 5u, 2u, 0, 8u, 0);
  if ( v6 >= 0 )
  {
    if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
    {
      LastError = GetLastError();
      v9 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError < 0;
      }
      if ( v9 )
        CBSWdsLog(
          0x4000000,
          (unsigned int)LastError,
          1,
          "Unable to enable termination on heap corruption, continuing anyway.");
    }
    v6 = CoCreateInstance(&CLSID_GlobalOptions, 0, 3u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
    if ( v6 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
      if ( v10 < 0 )
        CBSWdsLog(
          0x4000000,
          (unsigned int)v10,
          1,
          "Failed to set COM GlobalOptions, exception handling still in place.");
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
      if ( v6 >= 0 )
      {
        v6 = TiInitialize();
        if ( v6 >= 0 )
        {
          v6 = TiWorkerMainLoop();
          if ( v6 >= 0 )
            goto LABEL_23;
          v7 = "Failed TiMain loop";
        }
        else
        {
          v7 = "Failed to initialize Trusted Installer.";
        }
      }
      else
      {
        v7 = "Failed to set COM unmarshaling policy to strong";
      }
    }
    else
    {
      v7 = "Failed to access COM GlobalOptions object";
    }
  }
  else
  {
    v7 = "Failed to initialize COM security.";
  }
  CBSWdsLog(0x4000000, (unsigned int)v6, 1, v7);
LABEL_23:
  TiFinalize();
  if ( v3 )
    operator delete(v3 - 4, v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v5 )
    CoUninitialize();
  WdsUnload();
}

```

## disassembly

```asm
0x140007004  mov     r11, rsp
0x140007007  mov     [r11+8], rbx
0x14000700b  mov     [r11+10h], rbp
0x14000700f  push    rsi
0x140007010  sub     rsp, 70h
0x140007014  mov     rax, cs:__security_cookie
0x14000701b  xor     rax, rsp
0x14000701e  mov     [rsp+78h+var_18], rax
0x140007023  lea     rcx, [r11-28h]
0x140007027  mov     qword ptr [r11-20h], 0
0x14000702f  mov     qword ptr [r11-28h], 0
0x140007037  call    PathGetModulePath
0x14000703c  mov     rsi, [rsp+78h+var_28]
0x140007041  test    eax, eax
0x140007043  js      short loc_14000704F
0x140007045  xor     edx, edx; HINSTANCE
0x140007047  mov     rcx, rsi; wchar_t *
0x14000704a  call    ?WdsLoad@@YAJPEB_WPEAUHINSTANCE__@@@Z; WdsLoad(wchar_t const *,HINSTANCE__ *)
0x14000704f  lea     rax, ?vWdsLogger@@3VWdsLogger@LogAdapter@@A; LogAdapter::WdsLogger vWdsLogger
0x140007056  xor     edx, edx; dwCoInit
0x140007058  xor     ecx, ecx; pvReserved
0x14000705a  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rax; LogAdapter::Logger * LogAdapter::g_Logger
0x140007061  call    cs:__imp_CoInitializeEx
0x140007067  test    eax, eax
0x140007069  jns     short loc_14000707D
0x14000706b  xor     ebp, ebp
0x14000706d  lea     r9, aFailedToInitia; "Failed to initialize COM."
0x140007074  lea     r8d, [rbp+1]
0x140007078  jmp     loc_1400071BE
0x14000707d  mov     [rsp+78h+pReserved3], 0; pReserved3
0x140007086  mov     ebx, 1
0x14000708b  mov     [rsp+78h+dwCapabilities], 8; dwCapabilities
0x140007093  xor     r9d, r9d; pReserved1
0x140007096  mov     [rsp+78h+pAuthList], 0; pAuthList
0x14000709f  xor     r8d, r8d; asAuthSvc
0x1400070a2  mov     [rsp+78h+dwImpLevel], 2; dwImpLevel
0x1400070aa  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400070ad  xor     ecx, ecx; pSecDesc
0x1400070af  mov     [rsp+78h+dwAuthnLevel], 5; dwAuthnLevel
0x1400070b7  mov     ebp, ebx
0x1400070b9  call    cs:__imp_CoInitializeSecurity
0x1400070bf  test    eax, eax
0x1400070c1  jns     short loc_1400070CF
0x1400070c3  lea     r9, aFailedToInitia_3; "Failed to initialize COM security."
0x1400070ca  jmp     loc_1400071BB
0x1400070cf  xor     r9d, r9d; HeapInformationLength
0x1400070d2  xor     r8d, r8d; HeapInformation
0x1400070d5  mov     edx, ebx; HeapInformationClass
0x1400070d7  xor     ecx, ecx; HeapHandle
0x1400070d9  call    cs:__imp_HeapSetInformation
0x1400070df  test    eax, eax
0x1400070e1  jnz     short loc_14000710F
0x1400070e3  call    cs:__imp_GetLastError
0x1400070e9  test    eax, eax
0x1400070eb  jle     short loc_1400070F7
0x1400070ed  movzx   eax, ax
0x1400070f0  or      eax, 80070000h
0x1400070f5  test    eax, eax
0x1400070f7  jns     short loc_14000710F
0x1400070f9  lea     r9, aUnableToEnable; "Unable to enable termination on heap co"...
0x140007100  mov     r8d, ebx
0x140007103  mov     edx, eax
0x140007105  mov     ecx, 4000000h
0x14000710a  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000710f  xor     edx, edx; pUnkOuter
0x140007111  lea     rax, [rsp+78h+ppv]
0x140007116  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000711d  mov     qword ptr [rsp+78h+dwAuthnLevel], rax; ppv
0x140007122  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007129  lea     r8d, [rdx+3]; dwClsContext
0x14000712d  call    cs:__imp_CoCreateInstance
0x140007133  test    eax, eax
0x140007135  jns     short loc_140007140
0x140007137  lea     r9, aFailedToAccess; "Failed to access COM GlobalOptions obje"...
0x14000713e  jmp     short loc_1400071BB
0x140007140  mov     rcx, [rsp+78h+ppv]
0x140007145  mov     r8d, 2
0x14000714b  mov     edx, ebx
0x14000714d  mov     rax, [rcx]
0x140007150  mov     rax, [rax+18h]
0x140007154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007159  test    eax, eax
0x14000715b  jns     short loc_140007173
0x14000715d  lea     r9, aFailedToSetCom; "Failed to set COM GlobalOptions, except"...
0x140007164  mov     r8d, ebx
0x140007167  mov     edx, eax
0x140007169  mov     ecx, 4000000h
0x14000716e  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007173  mov     rcx, [rsp+78h+ppv]
0x140007178  mov     r8, rbx
0x14000717b  mov     edx, 5
0x140007180  mov     rax, [rcx]
0x140007183  mov     rax, [rax+18h]
0x140007187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000718c  test    eax, eax
0x14000718e  jns     short loc_140007199
0x140007190  lea     r9, aFailedToSetCom_0; "Failed to set COM unmarshaling policy t"...
0x140007197  jmp     short loc_1400071BB
0x140007199  call    TiInitialize
0x14000719e  test    eax, eax
0x1400071a0  jns     short loc_1400071AB
0x1400071a2  lea     r9, aFailedToInitia_9; "Failed to initialize Trusted Installer."
0x1400071a9  jmp     short loc_1400071BB
0x1400071ab  call    TiWorkerMainLoop
0x1400071b0  test    eax, eax
0x1400071b2  jns     short loc_1400071CA
0x1400071b4  lea     r9, aFailedTimainLo; "Failed TiMain loop"
0x1400071bb  mov     r8d, ebx
0x1400071be  mov     edx, eax
0x1400071c0  mov     ecx, 4000000h
0x1400071c5  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400071ca  call    TiFinalize
0x1400071cf  test    rsi, rsi
0x1400071d2  jz      short loc_1400071DD
0x1400071d4  lea     rcx, [rsi-8]; void *
0x1400071d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400071dd  mov     rcx, [rsp+78h+ppv]
0x1400071e2  test    rcx, rcx
0x1400071e5  jz      short loc_1400071F3
0x1400071e7  mov     rax, [rcx]
0x1400071ea  mov     rax, [rax+10h]
0x1400071ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071f3  test    ebp, ebp
0x1400071f5  jz      short loc_1400071FD
0x1400071f7  call    cs:__imp_CoUninitialize
0x1400071fd  call    ?WdsUnload@@YAXXZ; WdsUnload(void)
0x140007202  mov     rcx, [rsp+78h+var_18]
0x140007207  xor     rcx, rsp; StackCookie
0x14000720a  call    __security_check_cookie
0x14000720f  lea     r11, [rsp+78h+var_8]
0x140007214  mov     rbx, [r11+10h]
0x140007218  mov     rbp, [r11+18h]
0x14000721c  mov     rsp, r11
0x14000721f  pop     rsi
0x140007220  retn
```
