# GenericCallPackageHelper::RefreshP2PCerts(AadContextFunctions *,PluginState &,DiagnosticContext &,void *)

- ea: `0x180049394`
- end: `0x18004954c`
- name: `?RefreshP2PCerts@GenericCallPackageHelper@@CAJPEAVAadContextFunctions@@AEAVPluginState@@AEAVDiagnosticContext@@PEAX@Z`
- size: `440`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, void **this, struct DiagnosticContext *, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800477bc`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18000a5f4`
- `0x18001f474`
- `0x180027d34`
- `0x180032b14`
- `0x180049394`
- `0x180051aec`
- `0x180071e14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004946b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004946b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004945e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004945e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GenericCallPackageHelper::RefreshP2PCerts(
        struct AadContextFunctions *a1,
        void **this,
        struct DiagnosticContext *a3,
        HANDLE TokenHandle)
{
  int v8; // eax
  signed int LastError; // eax
  signed int v10; // ebx
  int updated; // eax
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+50h] [rbp-29h] BYREF
  int v15; // [rsp+54h] [rbp-25h] BYREF
  BOOL v16; // [rsp+58h] [rbp-21h] BYREF
  __int64 v17; // [rsp+60h] [rbp-19h]
  _BYTE v18[104]; // [rsp+68h] [rbp-11h] BYREF

  v14 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v18,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::RefreshP2PCerts",
    &v14);
  if ( !PluginState::IsCloudDomainJoined((PluginState *)this)
    || (unsigned int)SecurityGroupsHelper::CheckUserIsAdmin(TokenHandle)
    || (v15 = 0, v8 = DeviceP2PCertificateUpdate(a1, (struct _AadApPluginHandle *)*this, a3, &v15), v14 = v8, v8 >= 0) )
  {
    v17 = 0;
    v16 = ImpersonateLoggedOnUser(TokenHandle);
    if ( v16 )
      goto LABEL_10;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_10:
      updated = UpdateWorkPlaceP2PCertificates(a1, *this, a3);
      v14 = updated;
      if ( updated < 0 )
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          updated,
          "genericcallpackagehelper.cpp",
          927,
          "NTSTATUS",
          &base);
    }
    else
    {
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v10, "genericcallpackagehelper.cpp", 924, "HRESULT", &base);
      v14 = v10 & 0xAFFFFFFF | 0x40000000;
    }
    ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper((ImpersonateLoggedOnUserHelper *)&v16);
  }
  else
  {
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v8, "genericcallpackagehelper.cpp", 915, "NTSTATUS", &base);
  }
  v12 = v14;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v18);
  return v12;
}

```

## disassembly

```asm
0x180049394  push    rbp
0x180049396  push    rbx
0x180049397  push    rsi
0x180049398  push    rdi
0x180049399  push    r12
0x18004939b  push    r14
0x18004939d  lea     rbp, [rsp-2Fh]
0x1800493a2  sub     rsp, 0A8h
0x1800493a9  mov     rbx, r9
0x1800493ac  mov     rsi, r8
0x1800493af  mov     rdi, rdx
0x1800493b2  mov     r14, rcx
0x1800493b5  mov     [rbp+57h+var_80], 0
0x1800493bc  lea     r9, [rbp+57h+var_80]
0x1800493c0  lea     r8, aGenericcallpac_10; "GenericCallPackageHelper::RefreshP2PCer"...
0x1800493c7  lea     r12, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800493ce  mov     rdx, r12
0x1800493d1  lea     rcx, [rbp+57h+var_68]
0x1800493d5  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800493da  nop
0x1800493db  mov     rcx, rdi; this
0x1800493de  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x1800493e3  test    al, al
0x1800493e5  jz      short loc_180049453
0x1800493e7  mov     rcx, rbx; TokenHandle
0x1800493ea  call    ?CheckUserIsAdmin@SecurityGroupsHelper@@SAJPEAX@Z; SecurityGroupsHelper::CheckUserIsAdmin(void *)
0x1800493ef  test    eax, eax
0x1800493f1  jnz     short loc_180049453
0x1800493f3  mov     [rbp+57h+var_7C], eax
0x1800493f6  lea     r9, [rbp+57h+var_7C]; int *
0x1800493fa  mov     r8, rsi; struct DiagnosticContext *
0x1800493fd  mov     rdx, [rdi]; struct _AadApPluginHandle *
0x180049400  mov     rcx, r14; struct AadContextFunctions *
0x180049403  call    ?DeviceP2PCertificateUpdate@@YAJPEAVAadContextFunctions@@PEAXAEAVDiagnosticContext@@PEAH@Z; DeviceP2PCertificateUpdate(AadContextFunctions *,void *,DiagnosticContext &,int *)
0x180049408  mov     [rbp+57h+var_80], eax
0x18004940b  test    eax, eax
0x18004940d  jns     short loc_180049453
0x18004940f  lea     rcx, base
0x180049416  mov     [rsp+0D0h+var_90], rcx
0x18004941b  lea     rcx, aNtstatus; "NTSTATUS"
0x180049422  mov     [rsp+0D0h+var_98], rcx
0x180049427  mov     [rsp+0D0h+var_A0], 393h
0x18004942f  mov     [rsp+0D0h+var_A8], r12
0x180049434  mov     [rsp+0D0h+var_B0], eax
0x180049438  mov     ecx, 2
0x18004943d  mov     r9d, ecx
0x180049440  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180049447  xor     edx, edx
0x180049449  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004944e  jmp     loc_18004952E
0x180049453  mov     [rbp+57h+var_70], 0
0x18004945b  mov     rcx, rbx; hToken
0x18004945e  call    cs:__imp_ImpersonateLoggedOnUser
0x180049464  mov     [rbp+57h+var_78], eax
0x180049467  test    eax, eax
0x180049469  jnz     short loc_1800494D0
0x18004946b  call    cs:__imp_GetLastError
0x180049471  mov     ebx, eax
0x180049473  test    eax, eax
0x180049475  jle     short loc_180049480
0x180049477  movzx   ebx, ax
0x18004947a  or      ebx, 80070000h
0x180049480  test    ebx, ebx
0x180049482  jns     short loc_1800494D0
0x180049484  lea     rcx, base
0x18004948b  mov     [rsp+0D0h+var_90], rcx
0x180049490  lea     rax, aHresult; "HRESULT"
0x180049497  mov     [rsp+0D0h+var_98], rax
0x18004949c  mov     [rsp+0D0h+var_A0], 39Ch
0x1800494a4  mov     [rsp+0D0h+var_A8], r12
0x1800494a9  mov     [rsp+0D0h+var_B0], ebx
0x1800494ad  mov     ecx, 2
0x1800494b2  mov     r9d, ecx
0x1800494b5  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800494bc  xor     edx, edx
0x1800494be  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800494c3  btr     ebx, 1Ch
0x1800494c7  bts     ebx, 1Eh
0x1800494cb  mov     [rbp+57h+var_80], ebx
0x1800494ce  jmp     short loc_180049525
0x1800494d0  mov     r8, rsi; struct DiagnosticContext *
0x1800494d3  mov     rdx, [rdi]; void *
0x1800494d6  mov     rcx, r14; struct AadContextFunctions *
0x1800494d9  call    ?UpdateWorkPlaceP2PCertificates@@YAJPEAVAadContextFunctions@@PEAXAEAVDiagnosticContext@@@Z; UpdateWorkPlaceP2PCertificates(AadContextFunctions *,void *,DiagnosticContext &)
0x1800494de  mov     [rbp+57h+var_80], eax
0x1800494e1  test    eax, eax
0x1800494e3  jns     short loc_180049525
0x1800494e5  lea     rcx, base
0x1800494ec  mov     [rsp+0D0h+var_90], rcx
0x1800494f1  lea     rcx, aNtstatus; "NTSTATUS"
0x1800494f8  mov     [rsp+0D0h+var_98], rcx
0x1800494fd  mov     [rsp+0D0h+var_A0], 39Fh
0x180049505  mov     [rsp+0D0h+var_A8], r12
0x18004950a  mov     [rsp+0D0h+var_B0], eax
0x18004950e  mov     ecx, 2
0x180049513  mov     r9d, ecx
0x180049516  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004951d  xor     edx, edx
0x18004951f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180049524  nop
0x180049525  lea     rcx, [rbp+57h+var_78]; this
0x180049529  call    ??1ImpersonateLoggedOnUserHelper@@QEAA@XZ; ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper(void)
0x18004952e  mov     ebx, [rbp+57h+var_80]
0x180049531  lea     rcx, [rbp+57h+var_68]
0x180049535  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004953a  mov     eax, ebx
0x18004953c  add     rsp, 0A8h
0x180049543  pop     r14
0x180049545  pop     r12
0x180049547  pop     rdi
0x180049548  pop     rsi
0x180049549  pop     rbx
0x18004954a  pop     rbp
0x18004954b  retn
```
