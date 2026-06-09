# TryRunAsService(ulong *)

- ea: `0x1400321b8`
- end: `0x1400322ac`
- name: `?TryRunAsService@@YA_NPEAK@Z`
- size: `244`
- prototype: `char __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x1400323e4`

## callees

- `0x140004870`
- `0x140015bc4`
- `0x140018710`
- `0x14003086c`
- `0x140030bb0`
- `0x1400310e8`
- `0x1400321b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003221e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003221e`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003220a`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x14003220a`

## string_xrefs

- `0x1400321e1`: `ServiceCtrlDispatcherActivity`
- `0x14003223b`: `Failed to start service control dispatcher`

## pseudocode

```c
char __fastcall TryRunAsService(unsigned int *a1)
{
  char v2; // bl
  DWORD LastError; // eax
  __int64 v4; // rdx
  const char *v6; // [rsp+28h] [rbp-170h]
  _QWORD v7[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  *a1 = 0;
  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v7);
  v7[0] = &Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::`vftable';
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::StartActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity *)v7);
  if ( StartServiceCtrlDispatcherW(&DispatchTable) )
  {
    v2 = 1;
LABEL_8:
    wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v7,
      0);
    goto LABEL_9;
  }
  LastError = GetLastError();
  *a1 = LastError;
  if ( LastError == 1063 )
  {
    v2 = 0;
    goto LABEL_8;
  }
  wil::details::in1diag3::Log_Win32Msg(
    retaddr,
    (void *)0x6E,
    (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\exe\\main.cpp",
    (const char *)LastError,
    (unsigned int)"Failed to start service control dispatcher",
    v6);
  v4 = *a1;
  if ( (int)v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
  wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v7,
    v4);
  v2 = 0;
LABEL_9:
  Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::~ServiceCtrlDispatcherActivity((Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity *)v7);
  return v2;
}

```

## disassembly

```asm
0x1400321b8  push    rbx
0x1400321ba  sub     rsp, 190h
0x1400321c1  mov     rax, cs:__security_cookie
0x1400321c8  xor     rax, rsp
0x1400321cb  mov     [rsp+198h+var_18], rax
0x1400321d3  mov     rbx, rcx
0x1400321d6  mov     dword ptr [rcx], 0
0x1400321dc  lea     rcx, [rsp+198h+var_168]; struct wil::details::IFailureCallback *
0x1400321e1  lea     rdx, aServicectrldis; "ServiceCtrlDispatcherActivity"
0x1400321e8  call    ??0?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400321ed  lea     rax, ??_7ServiceCtrlDispatcherActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@6B@; const Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::`vftable'
0x1400321f4  lea     rcx, [rsp+198h+var_168]; this
0x1400321f9  mov     [rsp+198h+var_168], rax
0x1400321fe  call    ?StartActivity@ServiceCtrlDispatcherActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAAXXZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::StartActivity(void)
0x140032203  lea     rcx, ?DispatchTable@@3PAU_SERVICE_TABLE_ENTRYW@@A; lpServiceStartTable
0x14003220a  call    cs:__imp_StartServiceCtrlDispatcherW
0x140032211  nop     dword ptr [rax+rax+00h]
0x140032216  test    eax, eax
0x140032218  jz      short loc_14003221E
0x14003221a  mov     bl, 1
0x14003221c  jmp     short loc_14003227A
0x14003221e  call    cs:__imp_GetLastError
0x140032225  nop     dword ptr [rax+rax+00h]
0x14003222a  mov     [rbx], eax
0x14003222c  cmp     eax, 427h
0x140032231  jz      short loc_140032278
0x140032233  mov     rcx, [rsp+198h]; this
0x14003223b  lea     rdx, aFailedToStartS; "Failed to start service control dispatc"...
0x140032242  mov     qword ptr [rsp+198h+var_178], rdx; unsigned int
0x140032247  lea     r8, aOnecoreBaseFsR_22; "onecore\\base\\fs\\refsdedupsvc\\exe\\m"...
0x14003224e  mov     edx, 6Eh ; 'n'; void *
0x140032253  mov     r9d, eax; char *
0x140032256  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x14003225b  mov     edx, [rbx]
0x14003225d  test    edx, edx
0x14003225f  jle     short loc_14003226A
0x140032261  movzx   edx, dx
0x140032264  or      edx, 80070000h
0x14003226a  lea     rcx, [rsp+198h+var_168]
0x14003226f  call    ?Stop@?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140032274  xor     ebx, ebx
0x140032276  jmp     short loc_140032286
0x140032278  xor     bl, bl
0x14003227a  xor     edx, edx
0x14003227c  lea     rcx, [rsp+198h+var_168]
0x140032281  call    ?Stop@?$ActivityBase@VReFsDedupServiceLogging@ReFs@FileSystem@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::FileSystem::ReFs::ReFsDedupServiceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140032286  lea     rcx, [rsp+198h+var_168]; this
0x14003228b  call    ??1ServiceCtrlDispatcherActivity@ReFsDedupServiceLogging@ReFs@FileSystem@Windows@@QEAA@XZ; Windows::FileSystem::ReFs::ReFsDedupServiceLogging::ServiceCtrlDispatcherActivity::~ServiceCtrlDispatcherActivity(void)
0x140032290  mov     al, bl
0x140032292  mov     rcx, [rsp+198h+var_18]
0x14003229a  xor     rcx, rsp; StackCookie
0x14003229d  call    __security_check_cookie
0x1400322a2  add     rsp, 190h
0x1400322a9  pop     rbx
0x1400322aa  retn
```
