# CUHHandlerManager::StartJITCOMServer(IContextCallback * *,tagComCallData *)

- ea: `0x180019024`
- end: `0x1800193b2`
- name: `?StartJITCOMServer@CUHHandlerManager@@QEAAJPEAPEAUIContextCallback@@PEAUtagComCallData@@@Z`
- size: `910`
- prototype: `int(CUHHandlerManager *__hidden this, struct IContextCallback **, struct tagComCallData *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017b84`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b9c`
- `0x18000dee8`
- `0x18000dff4`
- `0x1800110fc`
- `0x1800125b4`
- `0x180019024`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800190fc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180019140`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800190fc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180019140`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019383`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019383`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019121`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019162`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019121`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019162`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019280`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019280`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019240`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019240`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019321`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019321`

## string_xrefs

- `0x18001922a`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019256`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019293`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800192e4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18001932f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180019185`: `Registering JIT COM server with CLSID %ws and APPID %ws`
- `0x1800191bd`: `Software\Classes\CLSID`
- `0x1800192f2`: `Successfully registered JIT COM server`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUHHandlerManager::StartJITCOMServer(CUHHandlerManager *this, LPVOID *a2, struct tagComCallData *a3)
{
  unsigned int v5; // edx
  HRESULT Guid; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  wil::details::in1diag3 *v10; // rcx
  HANDLE EventW; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  HRESULT Instance; // eax
  unsigned __int64 v15; // r9
  struct tagComCallData *v16; // r8
  int v17; // eax
  DWORD v18; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  int v21; // [rsp+40h] [rbp-79h] BYREF
  struct tagComCallData *v22; // [rsp+48h] [rbp-71h]
  int v23[4]; // [rsp+50h] [rbp-69h] BYREF
  _OWORD v24[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v25; // [rsp+80h] [rbp-39h]
  __int64 v26; // [rsp+88h] [rbp-31h]
  __int128 v27; // [rsp+90h] [rbp-29h]
  __int128 v28; // [rsp+A0h] [rbp-19h]
  __int128 v29; // [rsp+B0h] [rbp-9h]
  __int128 v30; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v22 = a3;
  v21 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v23[0] = 0;
  *((_OWORD *)this + 24) = 0;
  memset((char *)this + 400, 0, 0x4Eu);
  *((_OWORD *)this + 30) = 0;
  memset((char *)this + 496, 0, 0x4Eu);
  Guid = CCoInit::Initialize((CCoInit *)&v21, v5, 1);
  if ( Guid < 0 )
  {
    v7 = 1109;
LABEL_19:
    v10 = retaddr;
LABEL_33:
    v15 = (unsigned int)Guid;
    goto LABEL_34;
  }
  Guid = CoCreateGuid((GUID *)this + 24);
  if ( Guid < 0 )
  {
    v7 = 1112;
    goto LABEL_19;
  }
  if ( !StringFromGUID2((const GUID *const)this + 24, (LPOLESTR)this + 200, 39) )
  {
    Guid = -2147024774;
    v7 = 1114;
    goto LABEL_19;
  }
  Guid = CoCreateGuid((GUID *)this + 30);
  if ( Guid < 0 )
  {
    v7 = 1123;
    goto LABEL_19;
  }
  if ( !StringFromGUID2((const GUID *const)this + 30, (LPOLESTR)this + 248, 39) )
  {
    Guid = -2147024774;
    v7 = 1125;
    goto LABEL_19;
  }
  WUTrace(
    0,
    0,
    0x1000000,
    4,
    0,
    L"Registering JIT COM server with CLSID %ws and APPID %ws",
    (char *)this + 400,
    (char *)this + 496);
  LODWORD(ppv) = (_DWORD)this + 496;
  Guid = RegSetStringValueOnVolatileKey(v8, L"Software\\Classes\\CLSID", (char *)this + 400, L"AppID");
  if ( Guid < 0 )
  {
    v7 = 1139;
    goto LABEL_19;
  }
  Guid = CSusSecurityChecker::IsLocalSystem((CSusSecurityChecker *)v24, v23, 0);
  if ( Guid < 0 )
  {
    v7 = 1140;
    goto LABEL_19;
  }
  if ( v23[0] )
  {
    ppv = (LPVOID *)L"nt authority\\system";
    Guid = RegSetStringValueOnVolatileKey(v9, L"Software\\Classes\\AppID", (char *)this + 496, L"RunAs");
    if ( Guid < 0 )
    {
      v7 = 1149;
      goto LABEL_19;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 46) = EventW;
  if ( !EventW )
  {
    v10 = retaddr;
    v13 = 1154;
    goto LABEL_31;
  }
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, a2);
  Guid = Instance;
  if ( Instance < 0 )
  {
    v10 = retaddr;
    v15 = (unsigned int)Instance;
    v7 = 1156;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      v10,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)v15,
      (int)ppv);
    goto LABEL_36;
  }
  v16 = v22;
  v22->pUserDefined = this;
  LODWORD(ppv) = 5;
  v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), struct tagComCallData *, GUID *))(*(_QWORD *)*a2 + 24LL))(
          *a2,
          ConnectCallback,
          v16,
          &GUID_000001da_0000_0000_c000_000000000046);
  Guid = v17;
  if ( v17 < 0 )
  {
    v10 = retaddr;
    v15 = (unsigned int)v17;
    v7 = 1162;
    goto LABEL_34;
  }
  WUTrace(0, 0, 0x1000000, 4, 0, L"Successfully registered JIT COM server");
  v18 = WaitForSingleObject(*((HANDLE *)this + 46), 0x1388u);
  if ( v18 )
  {
    v10 = retaddr;
    if ( v18 == 258 )
    {
      Guid = -2145124319;
      v7 = 1171;
      goto LABEL_33;
    }
    if ( v18 != -1 )
    {
      Guid = -2145112065;
      v7 = 1180;
      goto LABEL_33;
    }
    v13 = 1177;
LABEL_31:
    Guid = wil::details::in1diag3::Return_GetLastError(
             v10,
             (void *)v13,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
             v12);
    goto LABEL_36;
  }
  Guid = 0;
LABEL_36:
  CSusSecurityChecker::~CSusSecurityChecker((CSusSecurityChecker *)v24);
  if ( v21 )
    CoUninitialize();
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x180019024  mov     [rsp-8+arg_18], rbx
0x180019029  push    rbp
0x18001902a  push    rsi
0x18001902b  push    rdi
0x18001902c  push    r12
0x18001902e  push    r13
0x180019030  push    r14
0x180019032  push    r15
0x180019034  lea     rbp, [rsp-27h]
0x180019039  sub     rsp, 0E0h
0x180019040  mov     rax, cs:__security_cookie
0x180019047  xor     rax, rsp
0x18001904a  mov     [rbp+57h+var_40], rax
0x18001904e  mov     [rbp+57h+var_C8], r8
0x180019052  mov     r13, rdx
0x180019055  mov     rsi, rcx
0x180019058  xor     ebx, ebx
0x18001905a  mov     [rbp+57h+var_D0], ebx
0x18001905d  xor     edx, edx; Val
0x18001905f  lea     r8d, [rbx+70h]; Size
0x180019063  lea     rcx, [rbp+57h+var_B0]; void *
0x180019067  call    memset
0x18001906c  mov     [rbp+57h+var_88], rbx
0x180019070  xorps   xmm0, xmm0
0x180019073  movdqa  [rbp+57h+var_80], xmm0
0x180019078  xorps   xmm1, xmm1
0x18001907b  movdqa  [rbp+57h+var_70], xmm1
0x180019080  movdqa  [rbp+57h+var_60], xmm0
0x180019085  movdqa  [rbp+57h+var_50], xmm1
0x18001908a  xor     eax, eax
0x18001908c  movups  [rbp+57h+var_B0], xmm0
0x180019090  movups  [rbp+57h+var_A0], xmm0
0x180019094  mov     [rbp+57h+var_90], rax
0x180019098  mov     [rbp+57h+var_C0], ebx
0x18001909b  lea     r15, [rsi+180h]
0x1800190a2  movups  xmmword ptr [r15], xmm0
0x1800190a6  lea     r14, [rsi+190h]
0x1800190ad  lea     ebx, [rax+4Eh]
0x1800190b0  mov     r8d, ebx; Size
0x1800190b3  xor     edx, edx; Val
0x1800190b5  mov     rcx, r14; void *
0x1800190b8  call    memset
0x1800190bd  lea     r12, [rsi+1E0h]
0x1800190c4  xorps   xmm0, xmm0
0x1800190c7  movups  xmmword ptr [r12], xmm0
0x1800190cc  lea     rdi, [rsi+1F0h]
0x1800190d3  mov     r8d, ebx; Size
0x1800190d6  xor     edx, edx; Val
0x1800190d8  mov     rcx, rdi; void *
0x1800190db  call    memset
0x1800190e0  mov     r8b, 1; bool
0x1800190e3  lea     rcx, [rbp+57h+var_D0]; this
0x1800190e7  call    ?Initialize@CCoInit@@QEAAJK_N@Z; CCoInit::Initialize(ulong,bool)
0x1800190ec  mov     ebx, eax
0x1800190ee  test    eax, eax
0x1800190f0  jns     short loc_1800190F9
0x1800190f2  mov     edx, 455h
0x1800190f7  jmp     short loc_18001910D
0x1800190f9  mov     rcx, r15; pguid
0x1800190fc  call    cs:__imp_CoCreateGuid
0x180019102  mov     ebx, eax
0x180019104  test    eax, eax
0x180019106  jns     short loc_180019115
0x180019108  mov     edx, 458h
0x18001910d  xor     r15d, r15d
0x180019110  jmp     loc_180019226
0x180019115  mov     r8d, 27h ; '''; cchMax
0x18001911b  mov     rdx, r14; lpsz
0x18001911e  mov     rcx, r15; rguid
0x180019121  call    cs:__imp_StringFromGUID2
0x180019127  xor     r15d, r15d
0x18001912a  test    eax, eax
0x18001912c  jnz     short loc_18001913D
0x18001912e  mov     ebx, 8007007Ah
0x180019133  mov     edx, 45Ah
0x180019138  jmp     loc_180019226
0x18001913d  mov     rcx, r12; pguid
0x180019140  call    cs:__imp_CoCreateGuid
0x180019146  mov     ebx, eax
0x180019148  test    eax, eax
0x18001914a  jns     short loc_180019156
0x18001914c  mov     edx, 463h
0x180019151  jmp     loc_180019226
0x180019156  mov     r8d, 27h ; '''; cchMax
0x18001915c  mov     rdx, rdi; lpsz
0x18001915f  mov     rcx, r12; rguid
0x180019162  call    cs:__imp_StringFromGUID2
0x180019168  test    eax, eax
0x18001916a  jnz     short loc_18001917B
0x18001916c  mov     ebx, 8007007Ah
0x180019171  mov     edx, 465h
0x180019176  jmp     loc_180019226
0x18001917b  mov     [rsp+110h+var_D8], rdi
0x180019180  mov     [rsp+110h+var_E0], r14
0x180019185  lea     rax, aRegisteringJit; "Registering JIT COM server with CLSID %"...
0x18001918c  mov     [rsp+110h+var_E8], rax
0x180019191  mov     [rsp+110h+ppv], r15
0x180019196  mov     r12d, 4
0x18001919c  mov     r9d, r12d
0x18001919f  xor     edx, edx
0x1800191a1  xor     ecx, ecx
0x1800191a3  mov     r8d, 1000000h
0x1800191a9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800191ae  mov     [rsp+110h+ppv], rdi
0x1800191b3  lea     r9, aAppid; "AppID"
0x1800191ba  mov     r8, r14
0x1800191bd  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x1800191c4  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1800191c9  mov     ebx, eax
0x1800191cb  test    eax, eax
0x1800191cd  jns     short loc_1800191D6
0x1800191cf  mov     edx, 473h
0x1800191d4  jmp     short loc_180019226
0x1800191d6  xor     r8d, r8d; void *
0x1800191d9  lea     rdx, [rbp+57h+var_C0]; int *
0x1800191dd  lea     rcx, [rbp+57h+var_B0]; this
0x1800191e1  call    ?IsLocalSystem@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsLocalSystem(int *,void *)
0x1800191e6  mov     ebx, eax
0x1800191e8  test    eax, eax
0x1800191ea  jns     short loc_1800191F3
0x1800191ec  mov     edx, 474h
0x1800191f1  jmp     short loc_180019226
0x1800191f3  cmp     [rbp+57h+var_C0], r15d
0x1800191f7  jz      short loc_180019236
0x1800191f9  lea     rax, aNtAuthoritySys; "nt authority\\system"
0x180019200  mov     [rsp+110h+ppv], rax
0x180019205  lea     r9, aRunas; "RunAs"
0x18001920c  mov     r8, rdi
0x18001920f  lea     rdx, SubKey; "Software\\Classes\\AppID"
0x180019216  call    ?RegSetStringValueOnVolatileKey@@YAJPEAUHKEY__@@PEB_W111W4RegistryHiveType@@@Z; RegSetStringValueOnVolatileKey(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x18001921b  mov     ebx, eax
0x18001921d  test    eax, eax
0x18001921f  jns     short loc_180019236
0x180019221  mov     edx, 47Dh
0x180019226  mov     rcx, [rbp+5Fh]
0x18001922a  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019231  jmp     loc_180019366
0x180019236  xor     r9d, r9d; lpName
0x180019239  xor     r8d, r8d; bInitialState
0x18001923c  xor     edx, edx; bManualReset
0x18001923e  xor     ecx, ecx; lpEventAttributes
0x180019240  call    cs:__imp_CreateEventW
0x180019246  mov     [rsi+170h], rax
0x18001924d  test    rax, rax
0x180019250  jnz     short loc_180019267
0x180019252  mov     rcx, [rbp+5Fh]
0x180019256  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001925d  mov     edx, 482h
0x180019262  jmp     loc_180019353
0x180019267  mov     [rsp+110h+ppv], r13; ppv
0x18001926c  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180019273  xor     edx, edx; pUnkOuter
0x180019275  lea     r8d, [rdx+1]; dwClsContext
0x180019279  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180019280  call    cs:__imp_CoCreateInstance
0x180019286  mov     ebx, eax
0x180019288  test    eax, eax
0x18001928a  jns     short loc_1800192A4
0x18001928c  mov     rcx, [rbp+5Fh]
0x180019290  mov     r9d, eax
0x180019293  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001929a  mov     edx, 484h
0x18001929f  jmp     loc_180019369
0x1800192a4  mov     r8, [rbp+57h+var_C8]
0x1800192a8  mov     [r8+8], rsi
0x1800192ac  mov     rcx, [r13+0]
0x1800192b0  mov     rax, [rcx]
0x1800192b3  mov     [rsp+110h+var_E8], r15
0x1800192b8  mov     dword ptr [rsp+110h+ppv], 5
0x1800192c0  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x1800192c7  lea     rdx, ?ConnectCallback@@YAJPEAUtagComCallData@@@Z; ConnectCallback(tagComCallData *)
0x1800192ce  mov     rax, [rax+18h]
0x1800192d2  call    _guard_dispatch_icall
0x1800192d7  mov     ebx, eax
0x1800192d9  test    eax, eax
0x1800192db  jns     short loc_1800192F2
0x1800192dd  mov     rcx, [rbp+5Fh]
0x1800192e1  mov     r9d, eax
0x1800192e4  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800192eb  mov     edx, 48Ah
0x1800192f0  jmp     short loc_180019369
0x1800192f2  lea     rax, aSuccessfullyRe; "Successfully registered JIT COM server"
0x1800192f9  mov     [rsp+110h+var_E8], rax
0x1800192fe  mov     [rsp+110h+ppv], r15; int
0x180019303  mov     r9d, r12d
0x180019306  xor     edx, edx
0x180019308  xor     ecx, ecx
0x18001930a  mov     r8d, 1000000h
0x180019310  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180019315  mov     edx, 1388h; dwMilliseconds
0x18001931a  mov     rcx, [rsi+170h]; hHandle
0x180019321  call    cs:__imp_WaitForSingleObject
0x180019327  test    eax, eax
0x180019329  jz      short loc_180019370
0x18001932b  mov     rcx, [rbp+5Fh]; this
0x18001932f  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019336  cmp     eax, 102h
0x18001933b  jz      short loc_18001935C
0x18001933d  cmp     eax, 0FFFFFFFFh
0x180019340  jz      short loc_18001934E
0x180019342  mov     ebx, 80242FFFh
0x180019347  mov     edx, 49Ch
0x18001934c  jmp     short loc_180019366
0x18001934e  mov     edx, 499h; void *
0x180019353  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019358  mov     ebx, eax
0x18001935a  jmp     short loc_180019373
0x18001935c  mov     ebx, 80240021h
0x180019361  mov     edx, 493h; void *
0x180019366  mov     r9d, ebx; char *
0x180019369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001936e  jmp     short loc_180019373
0x180019370  mov     ebx, r15d
0x180019373  lea     rcx, [rbp+57h+var_B0]; this
0x180019377  call    ??1CSusSecurityChecker@@QEAA@XZ; CSusSecurityChecker::~CSusSecurityChecker(void)
0x18001937c  nop
0x18001937d  cmp     [rbp+57h+var_D0], r15d
0x180019381  jz      short loc_180019389
0x180019383  call    cs:__imp_CoUninitialize
0x180019389  mov     eax, ebx
0x18001938b  mov     rcx, [rbp+57h+var_40]
0x18001938f  xor     rcx, rsp; StackCookie
0x180019392  call    __security_check_cookie
0x180019397  mov     rbx, [rsp+110h+arg_18]
0x18001939f  add     rsp, 0E0h
0x1800193a6  pop     r15
0x1800193a8  pop     r14
0x1800193aa  pop     r13
0x1800193ac  pop     r12
0x1800193ae  pop     rdi
0x1800193af  pop     rsi
0x1800193b0  pop     rbp
0x1800193b1  retn
```
