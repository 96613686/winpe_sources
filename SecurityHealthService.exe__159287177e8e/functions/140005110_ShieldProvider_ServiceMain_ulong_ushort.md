# ShieldProvider::ServiceMain(ulong,ushort * *)

- ea: `0x140005110`
- end: `0x140005366`
- name: `?ServiceMain@ShieldProvider@@YAXKPEAPEAG@Z`
- size: `598`
- prototype: `void __fastcall(ShieldProvider *this, bool *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000162c`
- `0x1400031e0`
- `0x14000352c`
- `0x14000373c`
- `0x140004174`
- `0x140004588`
- `0x140004e84`
- `0x140005110`
- `0x140007384`
- `0x140007538`
- `0x14000fab4`
- `0x140013010`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x1400051ab`
- `KERNEL32!DebugBreak` at `0x1400051ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005177`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005177`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x14000522c`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x14000522c`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x140005344`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x140005344`
- `ntdll!NtQuerySystemInformation` at `0x140005195`
- `ntdll!NtQuerySystemInformation` at `0x140005195`
- `ole32!CoInitializeEx` at `0x14000524a`
- `ole32!CoInitializeEx` at `0x14000524a`

## string_xrefs

- `0x14000513a`: `SOFTWARE\Microsoft\Windows Security Health\Miscellaneous`

## pseudocode

```c
void __fastcall ShieldProvider::ServiceMain(ShieldProvider *this, bool *a2, unsigned __int16 **a3)
{
  unsigned __int16 **v3; // r9
  bool v4; // di
  int v5; // eax
  HKEY v6; // rdx
  unsigned int *v7; // r9
  HKEY v8; // rbx
  ULONG64 *v9; // rbx
  const GUID **v10; // rdi
  const GUID *v11; // r8
  unsigned int v12; // r8d
  ShieldProvider *v13; // rcx
  HKEY v14; // rax
  _QWORD *v15; // rbx
  TRACEHANDLE v16; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+38h] BYREF

  ShieldProvider::GetIsDevMode(this, a2);
  if ( ShieldProvider::g_fDevMode )
  {
    hKey = 0;
    v4 = 0;
    v5 = ShieldProvider::ShieldUtilRegOpenKey(
           (ShieldProvider *)&hKey,
           (HKEY *)L"SOFTWARE\\Microsoft\\Windows Security Health\\Miscellaneous",
           (const unsigned __int16 *)0x20019,
           v3);
    v8 = hKey;
    if ( v5 >= 0 )
    {
      LODWORD(hKey) = 0;
      if ( (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)v8, v6, (const unsigned __int16 *)&hKey, v7) >= 0 )
        v4 = (_DWORD)hKey != 0;
    }
    if ( v8 )
      RegCloseKey(v8);
    if ( v4 )
    {
      LOWORD(hKey) = 0;
      if ( !NtQuerySystemInformation(SystemKernelDebuggerInformation, &hKey, 2u, 0) && (_BYTE)hKey && !BYTE1(hKey) )
        DebugBreak();
    }
  }
  qword_14001B980 = 0;
  v9 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShieldProviderWdspHost;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v10 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_14001B988 = 1;
  do
  {
    v11 = *v10;
    TraceGuidReg.Guid = v11;
    ++v10;
    TraceGuidReg.RegHandle = 0;
    v9[4] = (ULONG64)v11;
    RegisterTraceGuidsW(WppControlCallback, v9, v11, 1u, &TraceGuidReg, 0, 0, v9 + 1);
    v9 = (ULONG64 *)*v9;
  }
  while ( v9 );
  ShieldProvider::InitializeTracing(0, 0x1FFu, v12);
  if ( CoInitializeEx(0, 0) >= 0
    && (int)ShieldProvider::InitializeSecurity() >= 0
    && (int)ShieldProvider::LoadSystemPathFromFileHandle() >= 0 )
  {
    v14 = (HKEY)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    hKey = v14;
    if ( v14 )
    {
      ShieldProvider::g_pMain = (struct ShieldProvider::ShieldProviderMain *)v14;
      *(_QWORD *)v14 = &ShieldProvider::ShieldProviderMain::`vftable';
      *((_DWORD *)v14 + 5) = 252844334;
      *(_OWORD *)(v14 + 14) = 0;
      *(_OWORD *)(v14 + 17) = 0;
      *((_QWORD *)v14 + 11) = 0;
      *((_QWORD *)v14 + 12) = 0;
      if ( (int)ShieldProvider::ShieldProviderMain::Initialize((ShieldProvider::ShieldProviderMain *)&ShieldProvider::ShieldProviderMain::`vftable') >= 0 )
      {
        LOBYTE(hKey) = 0;
        if ( (int)ShieldProvider::LoadServiceCore(1u, (__int64)ShieldProvider::g_pMain, 0, &hKey) < 0 && !(_BYTE)hKey )
          ShieldProvider::LoadServiceCore(0, (__int64)ShieldProvider::g_pMain, 1, &hKey);
        (*(void (__fastcall **)(struct ShieldProvider::ShieldProviderMain *, __int64, _QWORD))(*(_QWORD *)ShieldProvider::g_pMain
                                                                                             + 24LL))(
          ShieldProvider::g_pMain,
          1,
          0);
      }
    }
    else
    {
      ShieldProvider::g_pMain = 0;
    }
  }
  ShieldProvider::UninitializeTracing(v13);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v15 )
    {
      v16 = v15[1];
      if ( v16 )
      {
        UnregisterTraceGuids(v16);
        v15[1] = 0;
      }
      v15 = (_QWORD *)*v15;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
}

```

## disassembly

```asm
0x140005110  push    rbp
0x140005112  push    rbx
0x140005113  push    rsi
0x140005114  push    rdi
0x140005115  mov     rbp, rsp
0x140005118  sub     rsp, 58h
0x14000511c  call    ?GetIsDevMode@ShieldProvider@@YAJPEA_N@Z; ShieldProvider::GetIsDevMode(bool *)
0x140005121  xor     esi, esi
0x140005123  cmp     cs:?g_fDevMode@ShieldProvider@@3_NA, sil; bool ShieldProvider::g_fDevMode
0x14000512a  jz      loc_1400051B1
0x140005130  mov     r8d, 20019h; unsigned __int16 *
0x140005136  mov     [rbp+hKey], rsi
0x14000513a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Security H"...
0x140005141  mov     dil, sil
0x140005144  lea     rcx, [rbp+hKey]; this
0x140005148  call    ?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)
0x14000514d  mov     rbx, [rbp+hKey]
0x140005151  test    eax, eax
0x140005153  js      short loc_14000516F
0x140005155  lea     r8, [rbp+hKey]; unsigned __int16 *
0x140005159  mov     dword ptr [rbp+hKey], esi
0x14000515c  mov     rcx, rbx; this
0x14000515f  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x140005164  test    eax, eax
0x140005166  js      short loc_14000516F
0x140005168  cmp     dword ptr [rbp+hKey], esi
0x14000516b  setnz   dil
0x14000516f  test    rbx, rbx
0x140005172  jz      short loc_14000517D
0x140005174  mov     rcx, rbx; hKey
0x140005177  call    cs:__imp_RegCloseKey
0x14000517d  test    dil, dil
0x140005180  jz      short loc_1400051B1
0x140005182  xor     r9d, r9d; ReturnLength
0x140005185  mov     word ptr [rbp+hKey], si
0x140005189  lea     rdx, [rbp+hKey]; SystemInformation
0x14000518d  lea     r8d, [r9+2]; SystemInformationLength
0x140005191  lea     ecx, [r9+23h]; SystemInformationClass
0x140005195  call    cs:__imp_NtQuerySystemInformation
0x14000519b  test    eax, eax
0x14000519d  jnz     short loc_1400051B1
0x14000519f  cmp     byte ptr [rbp+hKey], sil
0x1400051a3  jz      short loc_1400051B1
0x1400051a5  cmp     byte ptr [rbp+hKey+1], sil
0x1400051a9  jnz     short loc_1400051B1
0x1400051ab  call    cs:__imp_DebugBreak
0x1400051b1  lea     rax, WPP_ThisDir_CTLGUID_ShieldProviderWdspHost
0x1400051b8  mov     cs:qword_14001B980, rsi
0x1400051bf  lea     rbx, WPP_MAIN_CB
0x1400051c6  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1400051cd  mov     cs:WPP_GLOBAL_Control, rbx
0x1400051d4  lea     rdi, WPP_REGISTRATION_GUIDS
0x1400051db  mov     cs:WPP_MAIN_CB, rsi
0x1400051e2  mov     cs:qword_14001B988, 1
0x1400051ed  mov     r8, [rdi]; ControlGuid
0x1400051f0  lea     rax, [rbx+8]
0x1400051f4  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x1400051f9  lea     rcx, WppControlCallback; RequestAddress
0x140005200  mov     [rsp+58h+MofResourceName], rsi; MofResourceName
0x140005205  lea     rax, [rbp+var_18]
0x140005209  mov     [rbp+var_18.Guid], r8
0x14000520d  lea     rdi, [rdi+8]
0x140005211  mov     [rbp+var_18.RegHandle], rsi
0x140005215  mov     r9d, 1; GuidCount
0x14000521b  mov     [rsp+58h+MofImagePath], rsi; MofImagePath
0x140005220  mov     rdx, rbx; RequestContext
0x140005223  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x140005228  mov     [rbx+20h], r8
0x14000522c  call    cs:__imp_RegisterTraceGuidsW
0x140005232  mov     rbx, [rbx]
0x140005235  test    rbx, rbx
0x140005238  jnz     short loc_1400051ED
0x14000523a  mov     edx, 1FFh; unsigned int
0x14000523f  xor     ecx, ecx; this
0x140005241  call    ?InitializeTracing@ShieldProvider@@YAJKK@Z; ShieldProvider::InitializeTracing(ulong,ulong)
0x140005246  xor     edx, edx; dwCoInit
0x140005248  xor     ecx, ecx; pvReserved
0x14000524a  call    cs:__imp_CoInitializeEx
0x140005250  test    eax, eax
0x140005252  js      loc_140005321
0x140005258  call    ShieldProvider__InitializeSecurity
0x14000525d  test    eax, eax
0x14000525f  js      loc_140005321
0x140005265  call    ShieldProvider__LoadSystemPathFromFileHandle
0x14000526a  test    eax, eax
0x14000526c  js      loc_140005321
0x140005272  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005279  lea     ecx, [rbx+68h]; unsigned __int64
0x14000527c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005281  mov     [rbp+hKey], rax
0x140005285  test    rax, rax
0x140005288  jz      loc_14000531A
0x14000528e  xorps   xmm0, xmm0
0x140005291  mov     cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA, rax; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x140005298  lea     rcx, ??_7ShieldProviderMain@ShieldProvider@@6B@; this
0x14000529f  mov     [rax], rcx
0x1400052a2  mov     dword ptr [rax+14h], 0F12192Eh
0x1400052a9  movups  xmmword ptr [rax+38h], xmm0
0x1400052ad  movups  xmmword ptr [rax+44h], xmm0
0x1400052b1  mov     [rax+58h], rsi
0x1400052b5  mov     [rax+60h], rsi
0x1400052b9  call    ?Initialize@ShieldProviderMain@ShieldProvider@@QEAAJXZ; ShieldProvider::ShieldProviderMain::Initialize(void)
0x1400052be  test    eax, eax
0x1400052c0  js      short loc_140005321
0x1400052c2  mov     rdx, cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x1400052c9  lea     r9, [rbp+hKey]
0x1400052cd  xor     r8d, r8d
0x1400052d0  mov     byte ptr [rbp+hKey], sil
0x1400052d4  lea     ecx, [rbx+1]
0x1400052d7  call    ShieldProvider__LoadServiceCore
0x1400052dc  test    eax, eax
0x1400052de  jns     short loc_1400052FB
0x1400052e0  cmp     byte ptr [rbp+hKey], sil
0x1400052e4  jnz     short loc_1400052FB
0x1400052e6  mov     rdx, cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x1400052ed  lea     r9, [rbp+hKey]
0x1400052f1  mov     r8b, 1
0x1400052f4  xor     ecx, ecx
0x1400052f6  call    ShieldProvider__LoadServiceCore
0x1400052fb  mov     rcx, cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x140005302  xor     r9d, r9d
0x140005305  xor     r8d, r8d
0x140005308  mov     rax, [rcx]
0x14000530b  lea     edx, [r9+1]
0x14000530f  mov     rax, [rax+18h]
0x140005313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005318  jmp     short loc_140005321
0x14000531a  mov     cs:?g_pMain@ShieldProvider@@3PEAVShieldProviderMain@1@EA, rsi; ShieldProvider::ShieldProviderMain * ShieldProvider::g_pMain
0x140005321  call    ?UninitializeTracing@ShieldProvider@@YAXXZ; ShieldProvider::UninitializeTracing(void)
0x140005326  mov     rbx, cs:WPP_GLOBAL_Control
0x14000532d  lea     rdi, WPP_GLOBAL_Control
0x140005334  cmp     rbx, rdi
0x140005337  jz      short loc_14000535D
0x140005339  jmp     short loc_140005351
0x14000533b  mov     rcx, [rbx+8]; RegistrationHandle
0x14000533f  test    rcx, rcx
0x140005342  jz      short loc_14000534E
0x140005344  call    cs:__imp_UnregisterTraceGuids
0x14000534a  mov     [rbx+8], rsi
0x14000534e  mov     rbx, [rbx]
0x140005351  test    rbx, rbx
0x140005354  jnz     short loc_14000533B
0x140005356  mov     cs:WPP_GLOBAL_Control, rdi
0x14000535d  add     rsp, 58h
0x140005361  pop     rdi
0x140005362  pop     rsi
0x140005363  pop     rbx
0x140005364  pop     rbp
0x140005365  retn
```
