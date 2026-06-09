# RadioEventWatcher::OnRadioArrival(_GUID const *,ushort const *,bool)

- ea: `0x180017270`
- end: `0x18001746b`
- name: `?OnRadioArrival@RadioEventWatcher@@AEAAXPEBU_GUID@@PEBG_N@Z`
- size: `507`
- prototype: `void __fastcall(RadioEventWatcher *__hidden this, const struct _GUID *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002980`

## callees

- `0x180003880`
- `0x180004e20`
- `0x180006668`
- `0x180010964`
- `0x180017270`
- `0x18001cb44`
- `0x1800225a0`
- `0x180023148`
- `0x180063040`
- `0x1800634d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017428`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017428`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800172b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800172b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001733c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001733c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017320`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017320`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800173a0`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800173a0`

## pseudocode

```c
void __fastcall RadioEventWatcher::OnRadioArrival(
        RadioEventWatcher *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        bool a4)
{
  bool v8; // di
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  __int64 v10; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  bool v13; // sf
  bool v14; // sf
  __int64 v15; // rax
  const unsigned __int16 *v16; // [rsp+40h] [rbp-208h] BYREF
  __int64 v17; // [rsp+50h] [rbp-1F8h] BYREF
  int v18; // [rsp+58h] [rbp-1F0h]
  _BYTE v19[4]; // [rsp+5Ch] [rbp-1ECh] BYREF
  __int64 v20; // [rsp+60h] [rbp-1E8h]
  _BYTE v21[32]; // [rsp+1F0h] [rbp-58h] BYREF

  v16 = a3;
  v8 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_BTHPORT_DEVICE_INTERFACE.Data4;
  if ( v10 )
  {
    v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1 )
      v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data4;
    if ( !v15 )
      v8 = *((_QWORD *)this + 16) != -1;
  }
  else if ( (int)Windows::Internal::String::Initialize<unsigned short const *>((char *)this + 152, &v16) >= 0 )
  {
    FileW = CreateFileW(a3, 0xC0000000, 3u, 0, 3u, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(
      (char *)this + 120,
      FileW);
    if ( *((_QWORD *)this + 16) == -1 )
    {
      LastError = GetLastError();
      v13 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = LastError < 0;
      }
      if ( v13 )
        goto LABEL_13;
    }
    v17 = 416;
    v18 = 1;
    memset_0(v19, 0, 0x194u);
    v20 = *((_QWORD *)this + 16);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 136);
    LastError = CM_Register_Notification(&v17, this, &RadioEventWatcher::s_CMNotificationCallback, (char *)this + 144);
    v14 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError < 0;
    }
    if ( v14 )
    {
LABEL_13:
      cdp::detail::StringFormat(
        v21,
        "Failed to register for radio arrival notification for instance %s, result 0x%08lx",
        (const char *)a3,
        LastError);
      shared::LogMessage(1, v21);
      std::string::~string(v21);
    }
    else
    {
      v8 = a4;
    }
  }
  if ( v9 )
    LeaveCriticalSection(v9);
  if ( v8 )
    RadioEventWatcher::ProcessStateChange(this, 1);
}

```

## disassembly

```asm
0x180017270  mov     [rsp+arg_8], rbx
0x180017275  mov     [rsp+arg_18], rbp
0x18001727a  push    rsi
0x18001727b  push    rdi
0x18001727c  push    r13
0x18001727e  push    r14
0x180017280  push    r15
0x180017282  sub     rsp, 220h
0x180017289  mov     rax, cs:__security_cookie
0x180017290  xor     rax, rsp
0x180017293  mov     [rsp+248h+var_38], rax
0x18001729b  mov     r15b, r9b
0x18001729e  mov     r14, r8
0x1800172a1  mov     rbx, rdx
0x1800172a4  mov     rsi, rcx
0x1800172a7  mov     [rsp+248h+var_208], r8
0x1800172ac  xor     dil, dil
0x1800172af  lea     rbp, [rcx+30h]
0x1800172b3  mov     rcx, rbp; lpCriticalSection
0x1800172b6  call    cs:__imp_EnterCriticalSection
0x1800172bc  mov     rax, [rbx]
0x1800172bf  sub     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data1
0x1800172c6  jnz     short loc_1800172D3
0x1800172c8  mov     rax, [rbx+8]
0x1800172cc  sub     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data4
0x1800172d3  mov     r13d, 1
0x1800172d9  test    rax, rax
0x1800172dc  jnz     loc_1800173F4
0x1800172e2  lea     rcx, [rsi+98h]
0x1800172e9  lea     rdx, [rsp+248h+var_208]
0x1800172ee  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800172f3  test    eax, eax
0x1800172f5  js      loc_180017420
0x1800172fb  mov     [rsp+248h+hTemplateFile], 0; hTemplateFile
0x180017304  mov     [rsp+248h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001730c  lea     r8d, [r13+2]; dwShareMode
0x180017310  mov     [rsp+248h+dwCreationDisposition], r8d; dwCreationDisposition
0x180017315  xor     r9d, r9d; lpSecurityAttributes
0x180017318  mov     edx, 0C0000000h; dwDesiredAccess
0x18001731d  mov     rcx, r14; lpFileName
0x180017320  call    cs:__imp_CreateFileW
0x180017326  mov     rdx, rax
0x180017329  lea     rcx, [rsi+78h]
0x18001732d  call    ?Attach@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(void *)
0x180017332  cmp     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x18001733a  jnz     short loc_180017352
0x18001733c  call    cs:__imp_GetLastError
0x180017342  test    eax, eax
0x180017344  jle     short loc_180017350
0x180017346  movzx   eax, ax
0x180017349  or      eax, 80070000h
0x18001734e  test    eax, eax
0x180017350  js      short loc_1800173BB
0x180017352  mov     [rsp+248h+var_1F8], 1A0h
0x18001735b  mov     [rsp+248h+var_1F0], r13d
0x180017360  xor     edx, edx; Val
0x180017362  mov     r8d, 194h; Size
0x180017368  lea     rcx, [rsp+248h+var_1EC]; void *
0x18001736d  call    memset_0
0x180017372  mov     rax, [rsi+80h]
0x180017379  mov     [rsp+248h+var_1E8], rax
0x18001737e  lea     rbx, [rsi+88h]
0x180017385  mov     rcx, rbx
0x180017388  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x18001738d  lea     r9, [rbx+8]
0x180017391  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017398  mov     rdx, rsi
0x18001739b  lea     rcx, [rsp+248h+var_1F8]
0x1800173a0  call    cs:__imp_CM_Register_Notification
0x1800173a6  test    eax, eax
0x1800173a8  jle     short loc_1800173B4
0x1800173aa  movzx   eax, ax
0x1800173ad  or      eax, 80070000h
0x1800173b2  test    eax, eax
0x1800173b4  js      short loc_1800173BB
0x1800173b6  mov     dil, r15b
0x1800173b9  jmp     short loc_180017420
0x1800173bb  mov     r9d, eax
0x1800173be  mov     r8, r14
0x1800173c1  lea     rdx, aFailedToRegist; "Failed to register for radio arrival no"...
0x1800173c8  lea     rcx, [rsp+248h+var_58]
0x1800173d0  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800173d5  lea     rdx, [rsp+248h+var_58]
0x1800173dd  mov     ecx, r13d
0x1800173e0  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800173e5  lea     rcx, [rsp+248h+var_58]
0x1800173ed  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800173f2  jmp     short loc_180017420
0x1800173f4  mov     rax, [rbx]
0x1800173f7  sub     rax, qword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1
0x1800173fe  jnz     short loc_18001740B
0x180017400  mov     rax, [rbx+8]
0x180017404  sub     rax, qword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data4
0x18001740b  test    rax, rax
0x18001740e  jnz     short loc_180017420
0x180017410  movzx   edi, dil
0x180017414  cmp     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x18001741c  cmovnz  edi, r13d
0x180017420  test    rbp, rbp
0x180017423  jz      short loc_18001742E
0x180017425  mov     rcx, rbp; lpCriticalSection
0x180017428  call    cs:__imp_LeaveCriticalSection
0x18001742e  test    dil, dil
0x180017431  jz      short loc_18001743F
0x180017433  mov     dl, r13b; bool
0x180017436  mov     rcx, rsi; this
0x180017439  call    ?ProcessStateChange@RadioEventWatcher@@AEAAX_N@Z; RadioEventWatcher::ProcessStateChange(bool)
0x18001743e  nop
0x18001743f  mov     rcx, [rsp+248h+var_38]
0x180017447  xor     rcx, rsp; StackCookie
0x18001744a  call    __security_check_cookie
0x18001744f  lea     r11, [rsp+248h+var_28]
0x180017457  mov     rbx, [r11+38h]
0x18001745b  mov     rbp, [r11+48h]
0x18001745f  mov     rsp, r11
0x180017462  pop     r15
0x180017464  pop     r14
0x180017466  pop     r13
0x180017468  pop     rdi
0x180017469  pop     rsi
0x18001746a  retn
```
