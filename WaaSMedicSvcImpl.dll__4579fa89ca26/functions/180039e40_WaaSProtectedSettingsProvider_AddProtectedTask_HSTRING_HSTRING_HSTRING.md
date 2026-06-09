# WaaSProtectedSettingsProvider::AddProtectedTask(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x180039e40`
- end: `0x18003a0a2`
- name: `?AddProtectedTask@WaaSProtectedSettingsProvider@@UEAAJPEAUHSTRING__@@00@Z`
- size: `610`
- prototype: `int(WaaSProtectedSettingsProvider *__hidden this, HSTRING, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18002e81c`
- `0x18002ff7c`
- `0x1800301e0`
- `0x180032c94`
- `0x180039cf0`
- `0x180039e40`
- `0x18003a0a8`
- `0x18003aa64`
- `0x18003ad74`
- `0x180068840`
- `0x180068f58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039e97`

## string_xrefs

- `0x180039fa3`: `Caller was not allowed to write to the requested task path: %s`
- `0x180039fd0`: `Could not initialize task helper for path: %s. Error was: 0x%08x`
- `0x180039f7d`: `Could not verify access to task path: %s. Error code: 0x%08x.`
- `0x180039ff8`: `Failed when attempting to create task: %s. Error was: 0x%08x`
- `0x18003a01b`: `Failed to persist the task to store. It won't be possible to restore. Error code: 0x%08x`
- `0x180039ec8`: `AddProtectedTaskActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaaSProtectedSettingsProvider::AddProtectedTask(
        WaaSProtectedSettingsProvider *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4)
{
  const unsigned __int16 *StringRawBuffer; // r14
  OLECHAR *v7; // rsi
  const unsigned __int16 *v8; // r15
  int v9; // edi
  int v10; // r13d
  int v11; // r12d
  int v12; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rdx
  int updated; // eax
  WaasMedic::TaskProtector *v16; // rcx
  int v17; // eax
  bool *v19; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  LPVOID ppv[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h]
  void **v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  char v26; // [rsp+5Ch] [rbp-A4h]
  int v27; // [rsp+80h] [rbp-80h] BYREF
  const char *v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  char v30; // [rsp+98h] [rbp-68h]
  int v31; // [rsp+A0h] [rbp-60h]
  _BYTE v32[152]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v33; // [rsp+140h] [rbp+40h]
  int v34; // [rsp+150h] [rbp+50h]
  __int64 v35; // [rsp+158h] [rbp+58h]
  int *v36; // [rsp+160h] [rbp+60h]
  __int64 v37; // [rsp+168h] [rbp+68h]
  __int64 v38; // [rsp+170h] [rbp+70h]
  void ***v39; // [rsp+178h] [rbp+78h]
  __int64 v40; // [rsp+180h] [rbp+80h]
  int v41; // [rsp+188h] [rbp+88h]
  int *v42; // [rsp+190h] [rbp+90h]
  char v43; // [rsp+198h] [rbp+98h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v7 = (OLECHAR *)WindowsGetStringRawBuffer(a3, 0);
  v8 = WindowsGetStringRawBuffer(a4, 0);
  v23 = 0;
  *(_OWORD *)ppv = 0;
  v25 = 0;
  v26 = 0;
  v30 = 0;
  v27 = 0;
  v28 = "AddProtectedTaskActivity";
  v29 = 0;
  v31 = 0;
  v33 = 0;
  memset_0(v32, 0, sizeof(v32));
  v34 = 1;
  v35 = 0;
  v36 = &v25;
  v37 = 0;
  v38 = 0;
  v39 = &v24;
  v40 = 0;
  v41 = 0;
  v42 = &v27;
  v43 = 0;
  v9 = -1;
  v10 = -1;
  v11 = -1;
  v24 = &WaasMedic::TelemetryProvider::AddProtectedTaskActivity::`vftable';
  WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StartActivity(
    (WaasMedic::TelemetryProvider::AddProtectedTaskActivity *)&v24,
    StringRawBuffer);
  LOBYTE(v20[0]) = 0;
  v12 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToNamespace(
          (WaasMedic::ProtectedSettingsNamespaceMapper *)off_1800711D0,
          (const struct WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid *const)2,
          (unsigned __int64)v7,
          v20,
          v19);
  v13 = v12;
  v21 = v12;
  if ( v12 < 0 )
  {
    v14 = L"Could not verify access to task path: %s. Error code: 0x%08x.";
LABEL_3:
    LogLevelW(2u, v14, v7, (unsigned int)v12);
    goto LABEL_13;
  }
  if ( LOBYTE(v20[0]) )
  {
    v12 = WaasMedic::TasksHelper::Initialize(ppv, v7);
    v13 = v12;
    v9 = v12;
    if ( v12 < 0 )
    {
      v14 = L"Could not initialize task helper for path: %s. Error was: 0x%08x";
      goto LABEL_3;
    }
    updated = WaasMedic::TasksHelper::CreateOrUpdateTask((WaasMedic::TasksHelper *)ppv, StringRawBuffer, v8, 0);
    v13 = updated;
    v10 = updated;
    if ( updated >= 0 )
    {
      v17 = WaasMedic::TaskProtector::ProtectTask(v16, StringRawBuffer, v7, v8);
      v13 = v17;
      v11 = v17;
      if ( v17 < 0 )
        LogLevelW(
          2u,
          L"Failed to persist the task to store. It won't be possible to restore. Error code: 0x%08x",
          (unsigned int)v17);
    }
    else
    {
      LogLevelW(
        2u,
        L"Failed when attempting to create task: %s. Error was: 0x%08x",
        StringRawBuffer,
        (unsigned int)updated);
    }
  }
  else
  {
    LogLevelW(4u, L"Caller was not allowed to write to the requested task path: %s", v7);
    v13 = -2147024891;
  }
LABEL_13:
  WaasMedic::TelemetryProvider::AddProtectedTaskActivity::Stop(
    (WaasMedic::TelemetryProvider::AddProtectedTaskActivity *)&v24,
    v13,
    v21,
    v9,
    v10,
    v11);
  v24 = &WaasMedic::TelemetryProvider::AddProtectedTaskActivity::`vftable';
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v24);
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  return v13;
}

```

## disassembly

```asm
0x180039e40  mov     [rsp-8+arg_0], rbx
0x180039e45  push    rbp
0x180039e46  push    rsi
0x180039e47  push    rdi
0x180039e48  push    r12
0x180039e4a  push    r13
0x180039e4c  push    r14
0x180039e4e  push    r15
0x180039e50  lea     rbp, [rsp-0B0h]
0x180039e58  sub     rsp, 1B0h
0x180039e5f  mov     rax, cs:__security_cookie
0x180039e66  xor     rax, rsp
0x180039e69  mov     [rbp+0E0h+var_40], rax
0x180039e70  mov     rdi, r9
0x180039e73  mov     rbx, r8
0x180039e76  mov     rcx, rdx; string
0x180039e79  xor     edx, edx; length
0x180039e7b  call    cs:__imp_WindowsGetStringRawBuffer
0x180039e81  mov     r14, rax
0x180039e84  xor     edx, edx; length
0x180039e86  mov     rcx, rbx; string
0x180039e89  call    cs:__imp_WindowsGetStringRawBuffer
0x180039e8f  mov     rsi, rax
0x180039e92  xor     edx, edx; length
0x180039e94  mov     rcx, rdi; string
0x180039e97  call    cs:__imp_WindowsGetStringRawBuffer
0x180039e9d  mov     r15, rax
0x180039ea0  xorps   xmm0, xmm0
0x180039ea3  xor     eax, eax
0x180039ea5  mov     [rsp+1E0h+var_198], rax
0x180039eaa  xorps   xmm1, xmm1
0x180039ead  movdqu  xmmword ptr [rsp+1E0h+ppv], xmm1
0x180039eb3  xor     ebx, ebx
0x180039eb5  mov     word ptr [rsp+1E0h+var_198], bx
0x180039eba  mov     [rsp+1E0h+var_188], ebx
0x180039ebe  mov     [rsp+1E0h+var_184], bl
0x180039ec2  mov     [rbp+0E0h+var_148], bl
0x180039ec5  mov     [rbp+0E0h+var_160], ebx
0x180039ec8  lea     rax, aAddprotectedta; "AddProtectedTaskActivity"
0x180039ecf  mov     [rbp+0E0h+var_158], rax
0x180039ed3  mov     [rbp+0E0h+var_150], rbx
0x180039ed7  mov     [rbp+0E0h+var_140], ebx
0x180039eda  movdqa  [rbp+0E0h+var_A0], xmm0
0x180039edf  xor     edx, edx; Val
0x180039ee1  mov     r8d, 98h; Size
0x180039ee7  lea     rcx, [rbp+0E0h+var_138]; void *
0x180039eeb  call    memset_0
0x180039ef0  mov     [rbp+0E0h+var_90], 1
0x180039ef7  xor     eax, eax
0x180039ef9  mov     [rbp+0E0h+var_88], rax
0x180039efd  lea     rax, [rsp+1E0h+var_188]
0x180039f02  mov     [rbp+0E0h+var_80], rax
0x180039f06  mov     [rbp+0E0h+var_78], rbx
0x180039f0a  mov     [rbp+0E0h+var_70], rbx
0x180039f0e  lea     rax, [rsp+1E0h+var_190]
0x180039f13  mov     [rbp+0E0h+var_68], rax
0x180039f17  mov     [rbp+0E0h+var_60], rbx
0x180039f1e  mov     [rbp+0E0h+var_58], ebx
0x180039f24  lea     rax, [rbp+0E0h+var_160]
0x180039f28  mov     [rbp+0E0h+var_50], rax
0x180039f2f  mov     [rbp+0E0h+var_48], bl
0x180039f35  or      edi, 0FFFFFFFFh
0x180039f38  mov     r13d, edi
0x180039f3b  mov     r12d, edi
0x180039f3e  lea     rax, ??_7AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::AddProtectedTaskActivity::`vftable'
0x180039f45  mov     [rsp+1E0h+var_190], rax
0x180039f4a  mov     rdx, r14; unsigned __int16 *
0x180039f4d  lea     rcx, [rsp+1E0h+var_190]; this
0x180039f52  call    ?StartActivity@AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXPEBG@Z; WaasMedic::TelemetryProvider::AddProtectedTaskActivity::StartActivity(ushort const *)
0x180039f57  nop
0x180039f58  mov     byte ptr [rsp+1E0h+var_1B0], bl
0x180039f5c  lea     r9, [rsp+1E0h+var_1B0]; unsigned __int16 *
0x180039f61  mov     r8, rsi; unsigned __int64
0x180039f64  lea     edx, [rbx+2]; struct WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid *
0x180039f67  lea     rcx, off_1800711D0; this
0x180039f6e  call    ?IsCallerAllowedToWriteToNamespace@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJQEBUtagLocationNameToSid@12@_KPEBGAEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToNamespace(WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid const * const,unsigned __int64,ushort const *,bool &)
0x180039f73  mov     ebx, eax
0x180039f75  mov     [rsp+1E0h+var_1AC], eax
0x180039f79  test    eax, eax
0x180039f7b  jns     short loc_180039F99
0x180039f7d  lea     rdx, aCouldNotVerify_1; "Could not verify access to task path: %"...
0x180039f84  mov     r8, rsi
0x180039f87  mov     r9d, eax
0x180039f8a  mov     ecx, 2; unsigned __int8
0x180039f8f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039f94  jmp     loc_18003A02C
0x180039f99  cmp     byte ptr [rsp+1E0h+var_1B0], 0
0x180039f9e  jnz     short loc_180039FBB
0x180039fa0  mov     r8, rsi
0x180039fa3  lea     rdx, aCallerWasNotAl_0; "Caller was not allowed to write to the "...
0x180039faa  mov     ecx, 4; unsigned __int8
0x180039faf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039fb4  mov     ebx, 80070005h
0x180039fb9  jmp     short loc_18003A02C
0x180039fbb  mov     rdx, rsi; psz
0x180039fbe  lea     rcx, [rsp+1E0h+ppv]; ppv
0x180039fc3  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x180039fc8  mov     ebx, eax
0x180039fca  mov     edi, eax
0x180039fcc  test    eax, eax
0x180039fce  jns     short loc_180039FD9
0x180039fd0  lea     rdx, aCouldNotInitia; "Could not initialize task helper for pa"...
0x180039fd7  jmp     short loc_180039F84
0x180039fd9  xor     r9d, r9d; unsigned __int16 *
0x180039fdc  mov     r8, r15; unsigned __int16 *
0x180039fdf  mov     rdx, r14; unsigned __int16 *
0x180039fe2  lea     rcx, [rsp+1E0h+ppv]; this
0x180039fe7  call    ?CreateOrUpdateTask@TasksHelper@WaasMedic@@QEAAJPEBG00@Z; WaasMedic::TasksHelper::CreateOrUpdateTask(ushort const *,ushort const *,ushort const *)
0x180039fec  mov     ebx, eax
0x180039fee  mov     r13d, eax
0x180039ff1  test    eax, eax
0x180039ff3  jns     short loc_18003A001
0x180039ff5  mov     r8, r14
0x180039ff8  lea     rdx, aFailedWhenAtte; "Failed when attempting to create task: "...
0x180039fff  jmp     short loc_180039F87
0x18003a001  mov     r9, r15; unsigned __int16 *
0x18003a004  mov     r8, rsi; unsigned __int16 *
0x18003a007  mov     rdx, r14; unsigned __int16 *
0x18003a00a  call    ?ProtectTask@TaskProtector@WaasMedic@@QEAAJPEBG00@Z; WaasMedic::TaskProtector::ProtectTask(ushort const *,ushort const *,ushort const *)
0x18003a00f  mov     ebx, eax
0x18003a011  mov     r12d, eax
0x18003a014  test    eax, eax
0x18003a016  jns     short loc_18003A02C
0x18003a018  mov     r8d, eax
0x18003a01b  lea     rdx, aFailedToPersis_0; "Failed to persist the task to store. It"...
0x18003a022  mov     ecx, 2; unsigned __int8
0x18003a027  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a02c  mov     [rsp+1E0h+var_1B8], r12d; int
0x18003a031  mov     dword ptr [rsp+1E0h+var_1C0], r13d; int
0x18003a036  mov     r9d, edi; int
0x18003a039  mov     r8d, [rsp+1E0h+var_1AC]; int
0x18003a03e  mov     edx, ebx; int
0x18003a040  lea     rcx, [rsp+1E0h+var_190]; this
0x18003a045  call    ?Stop@AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXJJJJJ@Z; WaasMedic::TelemetryProvider::AddProtectedTaskActivity::Stop(long,long,long,long,long)
0x18003a04a  nop
0x18003a04b  lea     rax, ??_7AddProtectedTaskActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::AddProtectedTaskActivity::`vftable'
0x18003a052  mov     [rsp+1E0h+var_190], rax
0x18003a057  lea     rcx, [rsp+1E0h+var_190]
0x18003a05c  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003a061  lea     rcx, [rsp+1E0h+var_190]
0x18003a066  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003a06b  nop
0x18003a06c  lea     rcx, [rsp+1E0h+ppv]; this
0x18003a071  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x18003a076  mov     eax, ebx
0x18003a078  mov     rcx, [rbp+0E0h+var_40]
0x18003a07f  xor     rcx, rsp; StackCookie
0x18003a082  call    __security_check_cookie
0x18003a087  mov     rbx, [rsp+1E0h+arg_0]
0x18003a08f  add     rsp, 1B0h
0x18003a096  pop     r15
0x18003a098  pop     r14
0x18003a09a  pop     r13
0x18003a09c  pop     r12
0x18003a09e  pop     rdi
0x18003a09f  pop     rsi
0x18003a0a0  pop     rbp
0x18003a0a1  retn
```
