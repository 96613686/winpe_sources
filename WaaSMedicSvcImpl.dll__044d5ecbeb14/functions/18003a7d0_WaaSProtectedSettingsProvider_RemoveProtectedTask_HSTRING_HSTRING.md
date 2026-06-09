# WaaSProtectedSettingsProvider::RemoveProtectedTask(HSTRING__ *,HSTRING__ *)

- ea: `0x18003a7d0`
- end: `0x18003aa5e`
- name: `?RemoveProtectedTask@WaaSProtectedSettingsProvider@@UEAAJPEAUHSTRING__@@0@Z`
- size: `654`
- prototype: `__int64 __fastcall(WaaSProtectedSettingsProvider *this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x180025d60`
- `0x18002e81c`
- `0x18002ff7c`
- `0x180032854`
- `0x180032c94`
- `0x180039cf0`
- `0x18003a0a8`
- `0x18003a7d0`
- `0x18003abec`
- `0x18003b0b4`
- `0x180068840`
- `0x180068eec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a816`

## string_xrefs

- `0x18003a91b`: `Caller was not allowed to write to the requested task path: %s`
- `0x18003a9b4`: `Could not initialize task helper for path: %s. Error was: 0x%08x`
- `0x18003a905`: `Could not verify access to task path: %s. Error code: 0x%08x.`
- `0x18003a98f`: `Failed when attempting to unprotect the task %s. Error code: 0x%08x`
- `0x18003a9d6`: `Failed when attempting to delete task: %s. Error was: 0x%08x`
- `0x18003a847`: `RemoveProtectedTaskActivity`
- `0x18003a94f`: `Failed to get the task store. Error code: 0x%08x`
- `0x18003a972`: `Failed to remove the task from store. Error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WaaSProtectedSettingsProvider::RemoveProtectedTask(
        WaaSProtectedSettingsProvider *this,
        HSTRING a2,
        HSTRING a3)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  OLECHAR *v5; // rdi
  int v6; // r15d
  int v7; // r12d
  int v8; // r14d
  int v9; // eax
  unsigned int TaskStore; // ebx
  int v11; // r13d
  void *v12; // r8
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  bool *v17; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  void **v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h] BYREF
  char v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+90h] [rbp-70h] BYREF
  const char *v26; // [rsp+98h] [rbp-68h]
  __int64 v27; // [rsp+A0h] [rbp-60h]
  char v28; // [rsp+A8h] [rbp-58h]
  int v29; // [rsp+B0h] [rbp-50h]
  _BYTE v30[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v31; // [rsp+150h] [rbp+50h]
  int v32; // [rsp+160h] [rbp+60h]
  __int64 v33; // [rsp+168h] [rbp+68h]
  int *v34; // [rsp+170h] [rbp+70h]
  __int64 v35; // [rsp+178h] [rbp+78h]
  __int64 v36; // [rsp+180h] [rbp+80h]
  void ***v37; // [rsp+188h] [rbp+88h]
  __int64 v38; // [rsp+190h] [rbp+90h]
  int v39; // [rsp+198h] [rbp+98h]
  int *v40; // [rsp+1A0h] [rbp+A0h]
  char v41; // [rsp+1A8h] [rbp+A8h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v5 = (OLECHAR *)WindowsGetStringRawBuffer(a3, 0);
  v21 = 0;
  *(_OWORD *)ppv = 0;
  v23 = 0;
  v24 = 0;
  v28 = 0;
  v25 = 0;
  v26 = "RemoveProtectedTaskActivity";
  v27 = 0;
  v29 = 0;
  v31 = 0;
  memset_0(v30, 0, sizeof(v30));
  v32 = 1;
  v33 = 0;
  v34 = &v23;
  v35 = 0;
  v36 = 0;
  v37 = &v22;
  v38 = 0;
  v39 = 0;
  v40 = &v25;
  v41 = 0;
  v6 = -1;
  v7 = -1;
  v8 = -1;
  v22 = &WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::`vftable';
  WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StartActivity(
    (WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *)&v22,
    StringRawBuffer);
  LOBYTE(v18) = 0;
  v9 = WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToNamespace(
         (WaasMedic::ProtectedSettingsNamespaceMapper *)off_1800711D0,
         (const struct WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid *const)2,
         (unsigned __int64)v5,
         &v18,
         v17);
  TaskStore = v9;
  v11 = v9;
  if ( v9 < 0 )
  {
    v12 = v5;
    v13 = L"Could not verify access to task path: %s. Error code: 0x%08x.";
LABEL_14:
    LogLevelW(2u, v13, v12, (unsigned int)v9);
    goto LABEL_15;
  }
  if ( !(_BYTE)v18 )
  {
    LogLevelW(4u, L"Caller was not allowed to write to the requested task path: %s", v5);
    TaskStore = -2147024891;
    goto LABEL_15;
  }
  v19 = 0;
  TaskStore = WaasMedic::TaskProtector::GetTaskStore(&v19);
  if ( (TaskStore & 0x80000000) != 0 )
  {
    v14 = L"Failed to get the task store. Error code: 0x%08x";
LABEL_9:
    v8 = TaskStore;
    LogLevelW(2u, v14, TaskStore);
    LogLevelW(2u, L"Failed when attempting to unprotect the task %s. Error code: 0x%08x", StringRawBuffer, TaskStore);
    goto LABEL_15;
  }
  v15 = WaasMedic::RegDelValue(-2147483646, v19, StringRawBuffer);
  TaskStore = v15;
  if ( v15 < 0 )
  {
    v14 = L"Failed to remove the task from store. Error code: 0x%08x";
    goto LABEL_9;
  }
  v8 = v15;
  v9 = WaasMedic::TasksHelper::Initialize(ppv, v5);
  TaskStore = v9;
  v6 = v9;
  if ( v9 < 0 )
  {
    v12 = v5;
    v13 = L"Could not initialize task helper for path: %s. Error was: 0x%08x";
    goto LABEL_14;
  }
  v9 = WaasMedic::TasksHelper::DeleteTask((WaasMedic::TasksHelper *)ppv, StringRawBuffer);
  TaskStore = v9;
  v7 = v9;
  if ( v9 < 0 )
  {
    v12 = (void *)StringRawBuffer;
    v13 = L"Failed when attempting to delete task: %s. Error was: 0x%08x";
    goto LABEL_14;
  }
LABEL_15:
  WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::Stop(
    (WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *)&v22,
    TaskStore,
    v11,
    v6,
    v7,
    v8);
  v22 = &WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::`vftable';
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v22);
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  return TaskStore;
}

```

## disassembly

```asm
0x18003a7d0  mov     [rsp-8+arg_0], rbx
0x18003a7d5  push    rbp
0x18003a7d6  push    rsi
0x18003a7d7  push    rdi
0x18003a7d8  push    r12
0x18003a7da  push    r13
0x18003a7dc  push    r14
0x18003a7de  push    r15
0x18003a7e0  lea     rbp, [rsp-0C0h]
0x18003a7e8  sub     rsp, 1C0h
0x18003a7ef  mov     rax, cs:__security_cookie
0x18003a7f6  xor     rax, rsp
0x18003a7f9  mov     [rbp+0F0h+var_40], rax
0x18003a800  mov     rbx, r8
0x18003a803  mov     rcx, rdx; string
0x18003a806  xor     edx, edx; length
0x18003a808  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a80e  mov     rsi, rax
0x18003a811  xor     edx, edx; length
0x18003a813  mov     rcx, rbx; string
0x18003a816  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a81c  mov     rdi, rax
0x18003a81f  xorps   xmm0, xmm0
0x18003a822  xor     eax, eax
0x18003a824  mov     [rsp+1F0h+var_1A0], rax
0x18003a829  xorps   xmm1, xmm1
0x18003a82c  movdqu  xmmword ptr [rsp+1F0h+ppv], xmm1
0x18003a832  xor     ebx, ebx
0x18003a834  mov     word ptr [rsp+1F0h+var_1A0], bx
0x18003a839  mov     [rsp+1F0h+var_188], ebx
0x18003a83d  mov     [rsp+1F0h+var_184], bl
0x18003a841  mov     [rbp+0F0h+var_148], bl
0x18003a844  mov     [rbp+0F0h+var_160], ebx
0x18003a847  lea     rax, aRemoveprotecte; "RemoveProtectedTaskActivity"
0x18003a84e  mov     [rbp+0F0h+var_158], rax
0x18003a852  mov     [rbp+0F0h+var_150], rbx
0x18003a856  mov     [rbp+0F0h+var_140], ebx
0x18003a859  movdqa  [rbp+0F0h+var_A0], xmm0
0x18003a85e  xor     edx, edx; Val
0x18003a860  mov     r8d, 98h; Size
0x18003a866  lea     rcx, [rbp+0F0h+var_138]; void *
0x18003a86a  call    memset_0
0x18003a86f  mov     [rbp+0F0h+var_90], 1
0x18003a876  xor     eax, eax
0x18003a878  mov     [rbp+0F0h+var_88], rax
0x18003a87c  lea     rax, [rsp+1F0h+var_188]
0x18003a881  mov     [rbp+0F0h+var_80], rax
0x18003a885  mov     [rbp+0F0h+var_78], rbx
0x18003a889  mov     [rbp+0F0h+var_70], rbx
0x18003a890  lea     rax, [rsp+1F0h+var_190]
0x18003a895  mov     [rbp+0F0h+var_68], rax
0x18003a89c  mov     [rbp+0F0h+var_60], rbx
0x18003a8a3  mov     [rbp+0F0h+var_58], ebx
0x18003a8a9  lea     rax, [rbp+0F0h+var_160]
0x18003a8ad  mov     [rbp+0F0h+var_50], rax
0x18003a8b4  mov     [rbp+0F0h+var_48], bl
0x18003a8ba  or      r15d, 0FFFFFFFFh
0x18003a8be  mov     r12d, r15d
0x18003a8c1  mov     r14d, r15d
0x18003a8c4  lea     rax, ??_7RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::`vftable'
0x18003a8cb  mov     [rsp+1F0h+var_190], rax
0x18003a8d0  mov     rdx, rsi; unsigned __int16 *
0x18003a8d3  lea     rcx, [rsp+1F0h+var_190]; this
0x18003a8d8  call    ?StartActivity@RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXPEBG@Z; WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::StartActivity(ushort const *)
0x18003a8dd  nop
0x18003a8de  mov     byte ptr [rsp+1F0h+var_1C0], bl
0x18003a8e2  lea     r9, [rsp+1F0h+var_1C0]; unsigned __int16 *
0x18003a8e7  mov     r8, rdi; unsigned __int64
0x18003a8ea  lea     edx, [rbx+2]; struct WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid *
0x18003a8ed  lea     rcx, off_1800711D0; this
0x18003a8f4  call    ?IsCallerAllowedToWriteToNamespace@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJQEBUtagLocationNameToSid@12@_KPEBGAEA_N@Z; WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToNamespace(WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid const * const,unsigned __int64,ushort const *,bool &)
0x18003a8f9  mov     ebx, eax
0x18003a8fb  mov     r13d, eax
0x18003a8fe  test    eax, eax
0x18003a900  jns     short loc_18003A911
0x18003a902  mov     r8, rdi
0x18003a905  lea     rdx, aCouldNotVerify_1; "Could not verify access to task path: %"...
0x18003a90c  jmp     loc_18003A9DD
0x18003a911  cmp     byte ptr [rsp+1F0h+var_1C0], 0
0x18003a916  jnz     short loc_18003A936
0x18003a918  mov     r8, rdi
0x18003a91b  lea     rdx, aCallerWasNotAl_0; "Caller was not allowed to write to the "...
0x18003a922  mov     ecx, 4; unsigned __int8
0x18003a927  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a92c  mov     ebx, 80070005h
0x18003a931  jmp     loc_18003A9EA
0x18003a936  mov     [rsp+1F0h+var_1B8], 0
0x18003a93f  lea     rcx, [rsp+1F0h+var_1B8]; unsigned __int16 **
0x18003a944  call    ?GetTaskStore@TaskProtector@WaasMedic@@CAJPEAPEAG@Z; WaasMedic::TaskProtector::GetTaskStore(ushort * *)
0x18003a949  mov     ebx, eax
0x18003a94b  test    eax, eax
0x18003a94d  jns     short loc_18003A958
0x18003a94f  lea     rdx, aFailedToGetThe; "Failed to get the task store. Error cod"...
0x18003a956  jmp     short loc_18003A979
0x18003a958  mov     r8, rsi
0x18003a95b  mov     rdx, [rsp+1F0h+var_1B8]
0x18003a960  mov     rcx, 0FFFFFFFF80000002h
0x18003a967  call    ?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z; WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)
0x18003a96c  mov     ebx, eax
0x18003a96e  test    eax, eax
0x18003a970  jns     short loc_18003A998
0x18003a972  lea     rdx, aFailedToRemove_0; "Failed to remove the task from store. E"...
0x18003a979  mov     r8d, ebx
0x18003a97c  mov     al, 2
0x18003a97e  mov     r14d, ebx
0x18003a981  movzx   ecx, al; unsigned __int8
0x18003a984  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a989  mov     r9d, ebx
0x18003a98c  mov     r8, rsi
0x18003a98f  lea     rdx, aFailedWhenAtte_1; "Failed when attempting to unprotect the"...
0x18003a996  jmp     short loc_18003A9E0
0x18003a998  mov     r14d, ebx
0x18003a99b  mov     rdx, rdi; psz
0x18003a99e  lea     rcx, [rsp+1F0h+ppv]; ppv
0x18003a9a3  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x18003a9a8  mov     ebx, eax
0x18003a9aa  mov     r15d, eax
0x18003a9ad  test    eax, eax
0x18003a9af  jns     short loc_18003A9BD
0x18003a9b1  mov     r8, rdi
0x18003a9b4  lea     rdx, aCouldNotInitia; "Could not initialize task helper for pa"...
0x18003a9bb  jmp     short loc_18003A9DD
0x18003a9bd  mov     rdx, rsi; unsigned __int16 *
0x18003a9c0  lea     rcx, [rsp+1F0h+ppv]; this
0x18003a9c5  call    ?DeleteTask@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::DeleteTask(ushort const *)
0x18003a9ca  mov     ebx, eax
0x18003a9cc  mov     r12d, eax
0x18003a9cf  test    eax, eax
0x18003a9d1  jns     short loc_18003A9EA
0x18003a9d3  mov     r8, rsi
0x18003a9d6  lea     rdx, aFailedWhenAtte_0; "Failed when attempting to delete task: "...
0x18003a9dd  mov     r9d, eax
0x18003a9e0  mov     ecx, 2; unsigned __int8
0x18003a9e5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003a9ea  mov     [rsp+1F0h+var_1C8], r14d; int
0x18003a9ef  mov     dword ptr [rsp+1F0h+var_1D0], r12d; int
0x18003a9f4  mov     r9d, r15d; int
0x18003a9f7  mov     r8d, r13d; int
0x18003a9fa  mov     edx, ebx; int
0x18003a9fc  lea     rcx, [rsp+1F0h+var_190]; this
0x18003aa01  call    ?Stop@RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXJJJJJ@Z; WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::Stop(long,long,long,long,long)
0x18003aa06  nop
0x18003aa07  lea     rax, ??_7RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::`vftable'
0x18003aa0e  mov     [rsp+1F0h+var_190], rax
0x18003aa13  lea     rcx, [rsp+1F0h+var_190]
0x18003aa18  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003aa1d  lea     rcx, [rsp+1F0h+var_190]
0x18003aa22  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003aa27  nop
0x18003aa28  lea     rcx, [rsp+1F0h+ppv]; this
0x18003aa2d  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x18003aa32  mov     eax, ebx
0x18003aa34  mov     rcx, [rbp+0F0h+var_40]
0x18003aa3b  xor     rcx, rsp; StackCookie
0x18003aa3e  call    __security_check_cookie
0x18003aa43  mov     rbx, [rsp+1F0h+arg_0]
0x18003aa4b  add     rsp, 1C0h
0x18003aa52  pop     r15
0x18003aa54  pop     r14
0x18003aa56  pop     r13
0x18003aa58  pop     r12
0x18003aa5a  pop     rdi
0x18003aa5b  pop     rsi
0x18003aa5c  pop     rbp
0x18003aa5d  retn
```
