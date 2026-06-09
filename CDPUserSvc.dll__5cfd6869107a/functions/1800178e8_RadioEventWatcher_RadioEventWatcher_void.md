# RadioEventWatcher::RadioEventWatcher(void)

- ea: `0x1800178e8`
- end: `0x180017c11`
- name: `??0RadioEventWatcher@@QEAA@XZ`
- size: `809`
- prototype: `RadioEventWatcher *__fastcall(RadioEventWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180024df0`

## callees

- `0x1800178e8`
- `0x180017c18`
- `0x180017c70`
- `0x180026100`
- `0x180026374`
- `0x18002c570`
- `0x18002d1c8`
- `0x180041054`
- `0x1800433ec`
- `0x18005a8d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180017954`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180017954`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017928`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017932`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017928`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180017932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017b2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017b2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017b54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017b54`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017a0d`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017af4`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017bce`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017a0d`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017af4`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017bce`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
RadioEventWatcher *__fastcall RadioEventWatcher::RadioEventWatcher(RadioEventWatcher *this)
{
  __int64 *v2; // rax
  __int64 *v3; // rdx
  __int64 v4; // r8
  RadioEventWatcher *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  const WCHAR *StringRawBuffer; // rax
  HANDLE FileW; // rax
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
  if ( (int)RadioEventWatcher::FindRadioInstance(v5, (HSTRING *)this + 19, v6, v7) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 19), 0);
    FileW = CreateFileW(StringRawBuffer, 0xC0000000, 3u, 0, 3u, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(
      (char *)this + 120,
      FileW);
    v11 = *((_QWORD *)this + 16);
    if ( v11 == -1 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x36, (unsigned int)".\\radioeventwatcher.cpp", v10);
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
0x1800178e8  push    rbp
0x1800178ea  push    rbx
0x1800178eb  push    rsi
0x1800178ec  push    rdi
0x1800178ed  push    r12
0x1800178ef  push    r13
0x1800178f1  push    r14
0x1800178f3  push    r15
0x1800178f5  lea     rbp, [rsp-2A8h]
0x1800178fd  sub     rsp, 3A8h
0x180017904  mov     rax, cs:__security_cookie
0x18001790b  xor     rax, rsp
0x18001790e  mov     [rbp+2E0h+var_50], rax
0x180017915  mov     rsi, rcx
0x180017918  mov     [rsp+3E0h+var_3A0], rcx
0x18001791d  xor     r14d, r14d
0x180017920  mov     [rcx+8], r14
0x180017924  add     rcx, 10h; SRWLock
0x180017928  call    cs:__imp_InitializeSRWLock
0x18001792e  lea     rcx, [rsi+18h]; SRWLock
0x180017932  call    cs:__imp_InitializeSRWLock
0x180017938  nop
0x180017939  mov     [rsi+20h], r14
0x18001793d  mov     [rsi+28h], r14
0x180017941  lea     rax, ??_7RadioEventWatcher@@6B@; const RadioEventWatcher::`vftable'
0x180017948  mov     [rsi], rax
0x18001794b  lea     rcx, [rsi+30h]; lpCriticalSection
0x18001794f  xor     r8d, r8d; Flags
0x180017952  xor     edx, edx; dwSpinCount
0x180017954  call    cs:__imp_InitializeCriticalSectionEx
0x18001795a  nop
0x18001795b  lea     rdx, ??_7?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::`vftable'
0x180017962  mov     [rsi+58h], rdx
0x180017966  mov     [rsi+60h], r14
0x18001796a  mov     [rsi+68h], rdx
0x18001796e  mov     [rsi+70h], r14
0x180017972  lea     rcx, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180017979  mov     [rsi+78h], rcx
0x18001797d  mov     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x180017988  lea     r13, [rsi+88h]
0x18001798f  mov     [r13+0], rdx
0x180017993  mov     [r13+8], r14
0x180017997  lea     r15, [rsi+98h]
0x18001799e  mov     [r15], r14
0x1800179a1  lea     r14, [rsi+0A0h]
0x1800179a8  mov     rcx, r14
0x1800179ab  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x1800179b0  mov     [rbp+2E0h+var_1F0], 1A0h
0x1800179bb  mov     [rbp+2E0h+var_1E8], 0
0x1800179c5  xor     edx, edx; Val
0x1800179c7  mov     r8d, 194h; Size
0x1800179cd  lea     rcx, [rbp+2E0h+var_1E4]; void *
0x1800179d4  call    memset_0
0x1800179d9  movups  xmm0, xmmword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data1
0x1800179e0  movdqu  [rbp+2E0h+var_1E0], xmm0
0x1800179e8  lea     rcx, [rsi+58h]
0x1800179ec  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x1800179f1  mov     rdi, [rbp+2E8h]
0x1800179f8  lea     r9, [rsi+60h]
0x1800179fc  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017a03  mov     rdx, rsi
0x180017a06  lea     rcx, [rbp+2E0h+var_1F0]
0x180017a0d  call    cs:__imp_CM_Register_Notification
0x180017a13  test    eax, eax
0x180017a15  jz      short loc_180017A32
0x180017a17  mov     r9d, 80004005h; char *
0x180017a1d  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180017a24  mov     edx, 29h ; ')'; void *
0x180017a29  mov     rcx, rdi; this
0x180017a2c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017a32  mov     [rsp+3E0h+var_390], 1A0h
0x180017a3b  xor     edi, edi
0x180017a3d  mov     [rsp+3E0h+var_388], edi
0x180017a41  xor     edx, edx; Val
0x180017a43  mov     r8d, 194h; Size
0x180017a49  lea     rcx, [rsp+3E0h+var_384]; void *
0x180017a4e  call    memset_0
0x180017a53  lea     rax, [rbp+2E0h+var_1F0]
0x180017a5a  lea     rdx, [rsp+3E0h+var_390]
0x180017a5f  mov     ecx, 80h
0x180017a64  lea     r8d, [rdi+3]
0x180017a68  movups  xmm0, xmmword ptr [rdx]
0x180017a6b  movups  xmmword ptr [rax], xmm0
0x180017a6e  movups  xmm1, xmmword ptr [rdx+10h]
0x180017a72  movups  xmmword ptr [rax+10h], xmm1
0x180017a76  movups  xmm0, xmmword ptr [rdx+20h]
0x180017a7a  movups  xmmword ptr [rax+20h], xmm0
0x180017a7e  movups  xmm1, xmmword ptr [rdx+30h]
0x180017a82  movups  xmmword ptr [rax+30h], xmm1
0x180017a86  movups  xmm0, xmmword ptr [rdx+40h]
0x180017a8a  movups  xmmword ptr [rax+40h], xmm0
0x180017a8e  movups  xmm1, xmmword ptr [rdx+50h]
0x180017a92  movups  xmmword ptr [rax+50h], xmm1
0x180017a96  movups  xmm0, xmmword ptr [rdx+60h]
0x180017a9a  movups  xmmword ptr [rax+60h], xmm0
0x180017a9e  movups  xmm1, xmmword ptr [rdx+70h]
0x180017aa2  movups  xmmword ptr [rax+70h], xmm1
0x180017aa6  add     rax, rcx
0x180017aa9  add     rdx, rcx
0x180017aac  sub     r8, 1
0x180017ab0  jnz     short loc_180017A68
0x180017ab2  movups  xmm0, xmmword ptr [rdx]
0x180017ab5  movups  xmmword ptr [rax], xmm0
0x180017ab8  movups  xmm1, xmmword ptr [rdx+10h]
0x180017abc  movups  xmmword ptr [rax+10h], xmm1
0x180017ac0  movups  xmm0, xmmword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1
0x180017ac7  movdqu  [rbp+2E0h+var_1E0], xmm0
0x180017acf  lea     rcx, [rsi+68h]
0x180017ad3  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180017ad8  mov     rbx, [rbp+2E8h]
0x180017adf  lea     r9, [rsi+70h]
0x180017ae3  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017aea  mov     rdx, rsi
0x180017aed  lea     rcx, [rbp+2E0h+var_1F0]
0x180017af4  call    cs:__imp_CM_Register_Notification
0x180017afa  test    eax, eax
0x180017afc  jz      short loc_180017B19
0x180017afe  mov     r9d, 80004005h; char *
0x180017b04  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180017b0b  mov     edx, 2Fh ; '/'; void *
0x180017b10  mov     rcx, rbx; this
0x180017b13  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017b19  mov     rdx, r15; struct Windows::Internal::String *
0x180017b1c  call    ?FindRadioInstance@RadioEventWatcher@@AEAAJPEAVString@Internal@Windows@@@Z; RadioEventWatcher::FindRadioInstance(Windows::Internal::String *)
0x180017b21  test    eax, eax
0x180017b23  js      loc_180017BEB
0x180017b29  xor     edx, edx; length
0x180017b2b  mov     rcx, [r15]; string
0x180017b2e  call    cs:__imp_WindowsGetStringRawBuffer
0x180017b34  mov     [rsp+3E0h+hTemplateFile], rdi; hTemplateFile
0x180017b39  mov     [rsp+3E0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180017b3d  mov     [rsp+3E0h+dwCreationDisposition], 3; unsigned int
0x180017b45  xor     r9d, r9d; lpSecurityAttributes
0x180017b48  mov     edx, 0C0000000h; dwDesiredAccess
0x180017b4d  lea     r8d, [r9+3]; dwShareMode
0x180017b51  mov     rcx, rax; lpFileName
0x180017b54  call    cs:__imp_CreateFileW
0x180017b5a  mov     rdx, rax
0x180017b5d  lea     rcx, [rsi+78h]
0x180017b61  call    ?Attach@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(void *)
0x180017b66  mov     rdi, [rsi+80h]
0x180017b6d  mov     rcx, [rbp+2E8h]; this
0x180017b74  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180017b78  jnz     short loc_180017B8A
0x180017b7a  lea     r8, aRadioeventwatc; ".\\radioeventwatcher.cpp"
0x180017b81  lea     edx, [rdi+37h]; void *
0x180017b84  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017b8a  mov     [rsp+3E0h+var_390], 1A0h
0x180017b93  mov     ebx, 1
0x180017b98  mov     [rsp+3E0h+var_388], ebx
0x180017b9c  xor     edx, edx; Val
0x180017b9e  mov     r8d, 194h; Size
0x180017ba4  lea     rcx, [rsp+3E0h+var_384]; void *
0x180017ba9  call    memset_0
0x180017bae  mov     [rsp+3E0h+var_380], rdi
0x180017bb3  mov     rcx, r13
0x180017bb6  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180017bbb  lea     r9, [r13+8]
0x180017bbf  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017bc6  mov     rdx, rsi
0x180017bc9  lea     rcx, [rsp+3E0h+var_390]
0x180017bce  call    cs:__imp_CM_Register_Notification
0x180017bd4  mov     rcx, [rbp+2E8h]; this
0x180017bdb  test    eax, eax
0x180017bdd  jz      short loc_180017BE8
0x180017bdf  mov     r9d, eax; char *
0x180017be2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180017be8  xchg    bl, [r14]
0x180017beb  mov     rax, rsi
0x180017bee  mov     rcx, [rbp+2E0h+var_50]
0x180017bf5  xor     rcx, rsp; StackCookie
0x180017bf8  call    __security_check_cookie
0x180017bfd  add     rsp, 3A8h
0x180017c04  pop     r15
0x180017c06  pop     r14
0x180017c08  pop     r13
0x180017c0a  pop     r12
0x180017c0c  pop     rdi
0x180017c0d  pop     rsi
0x180017c0e  pop     rbx
0x180017c0f  pop     rbp
0x180017c10  retn
```
