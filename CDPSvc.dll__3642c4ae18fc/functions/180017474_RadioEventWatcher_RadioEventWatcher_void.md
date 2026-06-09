# RadioEventWatcher::RadioEventWatcher(void)

- ea: `0x180017474`
- end: `0x180017793`
- name: `??0RadioEventWatcher@@QEAA@XZ`
- size: `799`
- prototype: `RadioEventWatcher *__fastcall(RadioEventWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003de10`

## callees

- `0x18000977c`
- `0x180010964`
- `0x180017474`
- `0x18001779c`
- `0x1800225a0`
- `0x180023148`
- `0x18002da20`
- `0x1800634d4`
- `0x1800636b0`
- `0x1800636cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800174b4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800174be`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800174b4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800174be`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800174e0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800174e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800176e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800176e0`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017599`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017680`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017750`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017599`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017680`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017750`

## pseudocode

```c
RadioEventWatcher *__fastcall RadioEventWatcher::RadioEventWatcher(RadioEventWatcher *this)
{
  __int64 *v2; // rax
  __int64 *v3; // rdx
  __int64 v4; // r8
  RadioEventWatcher *v5; // rcx
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rdi
  unsigned int v12; // eax
  void *v13; // rdx
  unsigned int v14; // r8d
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  _BYTE v20[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+1F0h] [rbp+F0h] BYREF
  int v23; // [rsp+1F8h] [rbp+F8h]
  _BYTE v24[4]; // [rsp+1FCh] [rbp+FCh] BYREF
  GUID v25; // [rsp+200h] [rbp+100h]
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  *((_QWORD *)this + 1) = 0;
  InitializeSRWLock((PSRWLOCK)this + 2);
  InitializeSRWLock((PSRWLOCK)this + 3);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &RadioEventWatcher::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 48), 0, 0);
  *((_QWORD *)this + 11) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::`vftable';
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
  *((_QWORD *)this + 16) = -1;
  *((_QWORD *)this + 17) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::`vftable';
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  std::atomic<bool>::atomic<bool>((char *)this + 160);
  v22 = 416;
  v23 = 0;
  memset_0(v24, 0, 0x194u);
  v25 = GUID_BTHPORT_DEVICE_INTERFACE;
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 88);
  if ( (unsigned int)CM_Register_Notification(
                       &v22,
                       this,
                       &RadioEventWatcher::s_CMNotificationCallback,
                       (char *)this + 96) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)".\\radioeventwatcher.cpp",
      (const char *)0x80004005LL,
      dwCreationDisposition);
  v18 = 416;
  v19 = 0;
  memset_0(v20, 0, 0x194u);
  v2 = &v22;
  v3 = &v18;
  v4 = 3;
  do
  {
    *(_OWORD *)v2 = *(_OWORD *)v3;
    *((_OWORD *)v2 + 1) = *((_OWORD *)v3 + 1);
    *((_OWORD *)v2 + 2) = *((_OWORD *)v3 + 2);
    *((_OWORD *)v2 + 3) = *((_OWORD *)v3 + 3);
    *((_OWORD *)v2 + 4) = *((_OWORD *)v3 + 4);
    *((_OWORD *)v2 + 5) = *((_OWORD *)v3 + 5);
    *((_OWORD *)v2 + 6) = *((_OWORD *)v3 + 6);
    *((_OWORD *)v2 + 7) = *((_OWORD *)v3 + 7);
    v2 += 16;
    v3 += 16;
    --v4;
  }
  while ( v4 );
  *(_OWORD *)v2 = *(_OWORD *)v3;
  *((_OWORD *)v2 + 1) = *((_OWORD *)v3 + 1);
  v25 = GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE;
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 104);
  if ( (unsigned int)CM_Register_Notification(
                       &v22,
                       this,
                       &RadioEventWatcher::s_CMNotificationCallback,
                       (char *)this + 112) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)".\\radioeventwatcher.cpp",
      (const char *)0x80004005LL,
      dwCreationDisposition);
  if ( RadioEventWatcher::FindRadioInstance(v5, (RadioEventWatcher *)((char *)this + 152)) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 19), 0);
    FileW = CreateFileW(StringRawBuffer, 0xC0000000, 3u, 0, 3u, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(
      (char *)this + 120,
      FileW);
    v11 = *((_QWORD *)this + 16);
    if ( v11 == -1 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, v8, v9, v10);
    v18 = 416;
    v19 = 1;
    memset_0(v20, 0, 0x194u);
    v21 = v11;
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 136);
    v12 = CM_Register_Notification(&v18, this, &RadioEventWatcher::s_CMNotificationCallback, (char *)this + 144);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v13, v14, (const char *)v12, dwCreationDispositiona);
    *((_BYTE *)this + 160) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x180017474  push    rbp
0x180017476  push    rbx
0x180017477  push    rsi
0x180017478  push    rdi
0x180017479  push    r12
0x18001747b  push    r13
0x18001747d  push    r14
0x18001747f  push    r15
0x180017481  lea     rbp, [rsp-2A8h]
0x180017489  sub     rsp, 3A8h
0x180017490  mov     rax, cs:__security_cookie
0x180017497  xor     rax, rsp
0x18001749a  mov     [rbp+2E0h+var_50], rax
0x1800174a1  mov     rsi, rcx
0x1800174a4  mov     [rsp+3E0h+var_3A0], rcx
0x1800174a9  xor     r14d, r14d
0x1800174ac  mov     [rcx+8], r14
0x1800174b0  add     rcx, 10h; SRWLock
0x1800174b4  call    cs:__imp_InitializeSRWLock
0x1800174ba  lea     rcx, [rsi+18h]; SRWLock
0x1800174be  call    cs:__imp_InitializeSRWLock
0x1800174c4  nop
0x1800174c5  mov     [rsi+20h], r14
0x1800174c9  mov     [rsi+28h], r14
0x1800174cd  lea     rax, ??_7RadioEventWatcher@@6B@; const RadioEventWatcher::`vftable'
0x1800174d4  mov     [rsi], rax
0x1800174d7  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800174db  xor     r8d, r8d; Flags
0x1800174de  xor     edx, edx; dwSpinCount
0x1800174e0  call    cs:__imp_InitializeCriticalSectionEx
0x1800174e6  nop
0x1800174e7  lea     rdx, ??_7?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::`vftable'
0x1800174ee  mov     [rsi+58h], rdx
0x1800174f2  mov     [rsi+60h], r14
0x1800174f6  mov     [rsi+68h], rdx
0x1800174fa  mov     [rsi+70h], r14
0x1800174fe  lea     rcx, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180017505  mov     [rsi+78h], rcx
0x180017509  mov     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x180017514  lea     r13, [rsi+88h]
0x18001751b  mov     [r13+0], rdx
0x18001751f  mov     [r13+8], r14
0x180017523  lea     r15, [rsi+98h]
0x18001752a  mov     [r15], r14
0x18001752d  lea     r14, [rsi+0A0h]
0x180017534  mov     rcx, r14
0x180017537  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x18001753c  mov     [rbp+2E0h+var_1F0], 1A0h
0x180017547  mov     [rbp+2E0h+var_1E8], 0
0x180017551  xor     edx, edx; Val
0x180017553  mov     r8d, 194h; Size
0x180017559  lea     rcx, [rbp+2E0h+var_1E4]; void *
0x180017560  call    memset_0
0x180017565  movups  xmm0, xmmword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data1
0x18001756c  movdqu  [rbp+2E0h+var_1E0], xmm0
0x180017574  lea     rcx, [rsi+58h]
0x180017578  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x18001757d  mov     rdi, [rbp+2E8h]
0x180017584  lea     r9, [rsi+60h]
0x180017588  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18001758f  mov     rdx, rsi
0x180017592  lea     rcx, [rbp+2E0h+var_1F0]
0x180017599  call    cs:__imp_CM_Register_Notification
0x18001759f  test    eax, eax
0x1800175a1  jz      short loc_1800175BE
0x1800175a3  mov     r9d, 80004005h; char *
0x1800175a9  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x1800175b0  mov     edx, 29h ; ')'; void *
0x1800175b5  mov     rcx, rdi; this
0x1800175b8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800175be  mov     [rsp+3E0h+var_390], 1A0h
0x1800175c7  xor     edi, edi
0x1800175c9  mov     [rsp+3E0h+var_388], edi
0x1800175cd  xor     edx, edx; Val
0x1800175cf  mov     r8d, 194h; Size
0x1800175d5  lea     rcx, [rsp+3E0h+var_384]; void *
0x1800175da  call    memset_0
0x1800175df  lea     rax, [rbp+2E0h+var_1F0]
0x1800175e6  lea     rdx, [rsp+3E0h+var_390]
0x1800175eb  mov     ecx, 80h
0x1800175f0  lea     r8d, [rdi+3]
0x1800175f4  movups  xmm0, xmmword ptr [rdx]
0x1800175f7  movups  xmmword ptr [rax], xmm0
0x1800175fa  movups  xmm1, xmmword ptr [rdx+10h]
0x1800175fe  movups  xmmword ptr [rax+10h], xmm1
0x180017602  movups  xmm0, xmmword ptr [rdx+20h]
0x180017606  movups  xmmword ptr [rax+20h], xmm0
0x18001760a  movups  xmm1, xmmword ptr [rdx+30h]
0x18001760e  movups  xmmword ptr [rax+30h], xmm1
0x180017612  movups  xmm0, xmmword ptr [rdx+40h]
0x180017616  movups  xmmword ptr [rax+40h], xmm0
0x18001761a  movups  xmm1, xmmword ptr [rdx+50h]
0x18001761e  movups  xmmword ptr [rax+50h], xmm1
0x180017622  movups  xmm0, xmmword ptr [rdx+60h]
0x180017626  movups  xmmword ptr [rax+60h], xmm0
0x18001762a  movups  xmm1, xmmword ptr [rdx+70h]
0x18001762e  movups  xmmword ptr [rax+70h], xmm1
0x180017632  add     rax, rcx
0x180017635  add     rdx, rcx
0x180017638  sub     r8, 1
0x18001763c  jnz     short loc_1800175F4
0x18001763e  movups  xmm0, xmmword ptr [rdx]
0x180017641  movups  xmmword ptr [rax], xmm0
0x180017644  movups  xmm1, xmmword ptr [rdx+10h]
0x180017648  movups  xmmword ptr [rax+10h], xmm1
0x18001764c  movups  xmm0, xmmword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1
0x180017653  movdqu  [rbp+2E0h+var_1E0], xmm0
0x18001765b  lea     rcx, [rsi+68h]
0x18001765f  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180017664  mov     rbx, [rbp+2E8h]
0x18001766b  lea     r9, [rsi+70h]
0x18001766f  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017676  mov     rdx, rsi
0x180017679  lea     rcx, [rbp+2E0h+var_1F0]
0x180017680  call    cs:__imp_CM_Register_Notification
0x180017686  test    eax, eax
0x180017688  jz      short loc_1800176A5
0x18001768a  mov     r9d, 80004005h; char *
0x180017690  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180017697  mov     edx, 2Fh ; '/'; void *
0x18001769c  mov     rcx, rbx; this
0x18001769f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800176a5  mov     rdx, r15; struct Windows::Internal::String *
0x1800176a8  call    ?FindRadioInstance@RadioEventWatcher@@AEAAJPEAVString@Internal@Windows@@@Z; RadioEventWatcher::FindRadioInstance(Windows::Internal::String *)
0x1800176ad  test    eax, eax
0x1800176af  js      loc_18001776D
0x1800176b5  xor     edx, edx; length
0x1800176b7  mov     rcx, [r15]; string
0x1800176ba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800176c0  mov     [rsp+3E0h+hTemplateFile], rdi; hTemplateFile
0x1800176c5  mov     [rsp+3E0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800176c9  mov     [rsp+3E0h+dwCreationDisposition], 3; unsigned int
0x1800176d1  xor     r9d, r9d; lpSecurityAttributes
0x1800176d4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800176d9  lea     r8d, [r9+3]; dwShareMode
0x1800176dd  mov     rcx, rax; lpFileName
0x1800176e0  call    cs:__imp_CreateFileW
0x1800176e6  mov     rdx, rax
0x1800176e9  lea     rcx, [rsi+78h]
0x1800176ed  call    ?Attach@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(void *)
0x1800176f2  mov     rdi, [rsi+80h]
0x1800176f9  mov     rcx, [rbp+2E8h]; this
0x180017700  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180017704  jnz     short loc_18001770C
0x180017706  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001770c  mov     [rsp+3E0h+var_390], 1A0h
0x180017715  mov     ebx, 1
0x18001771a  mov     [rsp+3E0h+var_388], ebx
0x18001771e  xor     edx, edx; Val
0x180017720  mov     r8d, 194h; Size
0x180017726  lea     rcx, [rsp+3E0h+var_384]; void *
0x18001772b  call    memset_0
0x180017730  mov     [rsp+3E0h+var_380], rdi
0x180017735  mov     rcx, r13
0x180017738  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x18001773d  lea     r9, [r13+8]
0x180017741  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017748  mov     rdx, rsi
0x18001774b  lea     rcx, [rsp+3E0h+var_390]
0x180017750  call    cs:__imp_CM_Register_Notification
0x180017756  mov     rcx, [rbp+2E8h]; this
0x18001775d  test    eax, eax
0x18001775f  jz      short loc_18001776A
0x180017761  mov     r9d, eax; char *
0x180017764  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001776a  xchg    bl, [r14]
0x18001776d  mov     rax, rsi
0x180017770  mov     rcx, [rbp+2E0h+var_50]
0x180017777  xor     rcx, rsp; StackCookie
0x18001777a  call    __security_check_cookie
0x18001777f  add     rsp, 3A8h
0x180017786  pop     r15
0x180017788  pop     r14
0x18001778a  pop     r13
0x18001778c  pop     r12
0x18001778e  pop     rdi
0x18001778f  pop     rsi
0x180017790  pop     rbx
0x180017791  pop     rbp
0x180017792  retn
```
