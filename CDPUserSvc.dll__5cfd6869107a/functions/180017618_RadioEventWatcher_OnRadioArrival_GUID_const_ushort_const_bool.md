# RadioEventWatcher::OnRadioArrival(_GUID const *,ushort const *,bool)

- ea: `0x180017618`
- end: `0x1800177fd`
- name: `?OnRadioArrival@RadioEventWatcher@@AEAAXPEBU_GUID@@PEBG_N@Z`
- size: `485`
- prototype: `void __fastcall(RadioEventWatcher *__hidden this, const struct _GUID *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x180017618`
- `0x180017870`
- `0x180017c18`
- `0x180026100`
- `0x180029d00`
- `0x18002c570`
- `0x18002d1c8`
- `0x18005a314`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001765e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001765e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800176cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800176cf`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017759`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180017759`

## pseudocode

```c
void __fastcall RadioEventWatcher::OnRadioArrival(
        RadioEventWatcher *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        bool a4)
{
  bool v8; // di
  struct _RTL_CRITICAL_SECTION *v9; // r14
  __int64 v10; // rax
  HANDLE FileW; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  signed int LastError; // eax
  signed int v15; // eax
  __int64 v16; // rax
  signed int v17; // [rsp+40h] [rbp-1E8h] BYREF
  const unsigned __int16 *v18; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-1D8h] BYREF
  int v20; // [rsp+58h] [rbp-1D0h]
  _BYTE v21[4]; // [rsp+5Ch] [rbp-1CCh] BYREF
  __int64 v22; // [rsp+60h] [rbp-1C8h]

  v18 = a3;
  v8 = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_BTHPORT_DEVICE_INTERFACE.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_BTHPORT_DEVICE_INTERFACE.Data4;
  if ( v10 )
  {
    v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1 )
      v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data4;
    if ( !v16 )
      v8 = *((_QWORD *)this + 16) != -1;
  }
  else if ( a3 && (int)Windows::Internal::String::_InitializeHelper((HSTRING *)this + 19, a3) >= 0 )
  {
    FileW = CreateFileW(a3, 0xC0000000, 3u, 0, 3u, 0, 0);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(
      (char *)this + 120,
      FileW);
    if ( *((_QWORD *)this + 16) == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = 0;
    }
    v17 = LastError;
    if ( LastError < 0 )
      goto LABEL_15;
    v19 = 416;
    v20 = 1;
    memset_0(v21, 0, 0x194u);
    v22 = *((_QWORD *)this + 16);
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 136);
    v15 = CM_Register_Notification(&v19, this, &RadioEventWatcher::s_CMNotificationCallback, (char *)this + 144);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    v17 = v15;
    if ( v15 < 0 )
LABEL_15:
      Log<unsigned short const * &,long &>(v13, v12, &v18, &v17);
    else
      v8 = a4;
  }
  if ( v9 )
    LeaveCriticalSection(v9);
  if ( v8 )
    RadioEventWatcher::ProcessStateChange(this, 1);
}

```

## disassembly

```asm
0x180017618  mov     [rsp+arg_8], rbx
0x18001761d  mov     [rsp+arg_18], rbp
0x180017622  push    rsi
0x180017623  push    rdi
0x180017624  push    r13
0x180017626  push    r14
0x180017628  push    r15
0x18001762a  sub     rsp, 200h
0x180017631  mov     rax, cs:__security_cookie
0x180017638  xor     rax, rsp
0x18001763b  mov     [rsp+228h+var_38], rax
0x180017643  mov     r15b, r9b
0x180017646  mov     rbp, r8
0x180017649  mov     rbx, rdx
0x18001764c  mov     rsi, rcx
0x18001764f  mov     [rsp+228h+var_1E0], r8
0x180017654  xor     dil, dil
0x180017657  lea     r14, [rcx+30h]
0x18001765b  mov     rcx, r14; lpCriticalSection
0x18001765e  call    cs:__imp_EnterCriticalSection
0x180017664  mov     rax, [rbx]
0x180017667  sub     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data1
0x18001766e  jnz     short loc_18001767B
0x180017670  mov     rax, [rbx+8]
0x180017674  sub     rax, qword ptr cs:GUID_BTHPORT_DEVICE_INTERFACE.Data4
0x18001767b  mov     r13d, 1
0x180017681  test    rax, rax
0x180017684  jnz     loc_180017786
0x18001768a  test    rbp, rbp
0x18001768d  jz      loc_1800177B2
0x180017693  lea     rcx, [rsi+98h]; this
0x18001769a  mov     rdx, rbp; unsigned __int16 *
0x18001769d  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1800176a2  test    eax, eax
0x1800176a4  js      loc_1800177B2
0x1800176aa  mov     [rsp+228h+hTemplateFile], 0; hTemplateFile
0x1800176b3  mov     [rsp+228h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800176bb  lea     r8d, [r13+2]; dwShareMode
0x1800176bf  mov     [rsp+228h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800176c4  xor     r9d, r9d; lpSecurityAttributes
0x1800176c7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800176cc  mov     rcx, rbp; lpFileName
0x1800176cf  call    cs:__imp_CreateFileW
0x1800176d5  mov     rdx, rax
0x1800176d8  lea     rcx, [rsi+78h]
0x1800176dc  call    ?Attach@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::Attach(void *)
0x1800176e1  mov     ebp, 80070000h
0x1800176e6  cmp     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x1800176ee  jz      short loc_1800176F4
0x1800176f0  xor     eax, eax
0x1800176f2  jmp     short loc_180017703
0x1800176f4  call    cs:__imp_GetLastError
0x1800176fa  test    eax, eax
0x1800176fc  jle     short loc_180017703
0x1800176fe  movzx   eax, ax
0x180017701  or      eax, ebp
0x180017703  mov     [rsp+228h+var_1E8], eax
0x180017707  test    eax, eax
0x180017709  js      short loc_180017775
0x18001770b  mov     [rsp+228h+var_1D8], 1A0h
0x180017714  mov     [rsp+228h+var_1D0], r13d
0x180017719  xor     edx, edx; Val
0x18001771b  mov     r8d, 194h; Size
0x180017721  lea     rcx, [rsp+228h+var_1CC]; void *
0x180017726  call    memset_0
0x18001772b  mov     rax, [rsi+80h]
0x180017732  mov     [rsp+228h+var_1C8], rax
0x180017737  lea     rbx, [rsi+88h]
0x18001773e  mov     rcx, rbx
0x180017741  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180017746  lea     r9, [rbx+8]
0x18001774a  lea     r8, ?s_CMNotificationCallback@RadioEventWatcher@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; RadioEventWatcher::s_CMNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180017751  mov     rdx, rsi
0x180017754  lea     rcx, [rsp+228h+var_1D8]
0x180017759  call    cs:__imp_CM_Register_Notification
0x18001775f  test    eax, eax
0x180017761  jle     short loc_180017768
0x180017763  movzx   eax, ax
0x180017766  or      eax, ebp
0x180017768  mov     [rsp+228h+var_1E8], eax
0x18001776c  test    eax, eax
0x18001776e  js      short loc_180017775
0x180017770  mov     dil, r15b
0x180017773  jmp     short loc_1800177B2
0x180017775  lea     r9, [rsp+228h+var_1E8]
0x18001777a  lea     r8, [rsp+228h+var_1E0]
0x18001777f  call    ??$Log@AEAPEBGAEAJ@@YAXW4CDPLogLevel@@PEBDAEAPEBGAEAJ@Z; Log<ushort const * &,long &>(CDPLogLevel,char const *,ushort const * &,long &)
0x180017784  jmp     short loc_1800177B2
0x180017786  mov     rax, [rbx]
0x180017789  sub     rax, qword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data1
0x180017790  jnz     short loc_18001779D
0x180017792  mov     rax, [rbx+8]
0x180017796  sub     rax, qword ptr cs:GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE.Data4
0x18001779d  test    rax, rax
0x1800177a0  jnz     short loc_1800177B2
0x1800177a2  movzx   edi, dil
0x1800177a6  cmp     qword ptr [rsi+80h], 0FFFFFFFFFFFFFFFFh
0x1800177ae  cmovnz  edi, r13d
0x1800177b2  test    r14, r14
0x1800177b5  jz      short loc_1800177C0
0x1800177b7  mov     rcx, r14; lpCriticalSection
0x1800177ba  call    cs:__imp_LeaveCriticalSection
0x1800177c0  test    dil, dil
0x1800177c3  jz      short loc_1800177D1
0x1800177c5  mov     dl, r13b; bool
0x1800177c8  mov     rcx, rsi; this
0x1800177cb  call    ?ProcessStateChange@RadioEventWatcher@@AEAAX_N@Z; RadioEventWatcher::ProcessStateChange(bool)
0x1800177d0  nop
0x1800177d1  mov     rcx, [rsp+228h+var_38]
0x1800177d9  xor     rcx, rsp; StackCookie
0x1800177dc  call    __security_check_cookie
0x1800177e1  lea     r11, [rsp+228h+var_28]
0x1800177e9  mov     rbx, [r11+38h]
0x1800177ed  mov     rbp, [r11+48h]
0x1800177f1  mov     rsp, r11
0x1800177f4  pop     r15
0x1800177f6  pop     r14
0x1800177f8  pop     r13
0x1800177fa  pop     rdi
0x1800177fb  pop     rsi
0x1800177fc  retn
```
