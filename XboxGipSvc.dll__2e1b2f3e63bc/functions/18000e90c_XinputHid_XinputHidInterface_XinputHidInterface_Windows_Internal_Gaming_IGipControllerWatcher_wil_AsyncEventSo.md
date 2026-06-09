# XinputHid::XinputHidInterface::XinputHidInterface(Windows::Internal::Gaming::IGipControllerWatcher *,wil::AsyncEventSourceT<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>,Windows::Internal::GitEventSourceSupportsAgile,Microsoft::WRL::InvokeModeOptions<2>,1,wil::err_returncode_policy> *)

- ea: `0x18000e90c`
- end: `0x18000ecf1`
- name: `??0XinputHidInterface@XinputHid@@QEAA@PEAUIGipControllerWatcher@Gaming@Internal@Windows@@PEAV?$AsyncEventSourceT@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@VGitEventSourceSupportsAgile@Internal@3@U?$InvokeModeOptions@$01@WRL@Microsoft@@$00Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `997`
- prototype: `char *__fastcall(char *lpParameter, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000df30`

## callees

- `0x1800016c0`
- `0x180001b6c`
- `0x180002158`
- `0x180002188`
- `0x1800021fc`
- `0x180009260`
- `0x18000e90c`
- `0x180010768`
- `0x180010d1c`
- `0x180010ed4`
- `0x180010efc`
- `0x180012010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000ebe3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000ebe3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e95d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e972`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e95d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e972`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ea33`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ea33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec25`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e988`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000e988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea76`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eac8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000eac8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18000eba2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18000eba2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18000eb40`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18000eb40`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000eaa2`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000eaa2`

## pseudocode

```c
char *__fastcall XinputHid::XinputHidInterface::XinputHidInterface(char *lpParameter, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned int v7; // r8d
  char *Thread; // rax
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // rax
  WCHAR *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  WCHAR *v17; // rdi
  CONFIGRET Device_Interface_ListW; // eax
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // r8d
  const wchar_t *v21; // r14
  int v22; // r15d
  int dwCreationFlags; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  ULONG pulLen; // [rsp+30h] [rbp-D0h] BYREF
  char *v27; // [rsp+38h] [rbp-C8h]
  char *v28; // [rsp+40h] [rbp-C0h]
  WCHAR *v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h]
  GUID v32; // [rsp+60h] [rbp-A0h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v28 = lpParameter;
  *((_QWORD *)lpParameter + 1) = a2;
  *((_QWORD *)lpParameter + 2) = a3;
  *((_QWORD *)lpParameter + 5) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)lpParameter + 6) = CreateEventW(0, 1, 0, 0);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(lpParameter + 56), 0, 0);
  v27 = lpParameter + 96;
  *((_DWORD *)lpParameter + 24) = 0;
  *((_QWORD *)lpParameter + 13) = 0;
  *((_QWORD *)lpParameter + 14) = 0;
  v4 = operator new(0x40u);
  *v4 = v4;
  v4[1] = v4;
  *((_QWORD *)lpParameter + 13) = v4;
  *((_QWORD *)lpParameter + 15) = 0;
  *((_QWORD *)lpParameter + 16) = 0;
  *((_QWORD *)lpParameter + 17) = 0;
  *((_QWORD *)lpParameter + 18) = 7;
  *((_QWORD *)lpParameter + 19) = 8;
  *((_DWORD *)lpParameter + 24) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::_Assign_grow(
    lpParameter + 120,
    16,
    *((_QWORD *)lpParameter + 13));
  if ( (unsigned __int64)(*((_QWORD *)lpParameter + 5) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x53, v5, (const char *)0x8000FFFFLL, dwCreationFlags);
  if ( (unsigned __int64)(*((_QWORD *)lpParameter + 6) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x54, v5, (const char *)0x8000FFFFLL, dwCreationFlags);
  if ( XinputHid::finalCallbackEvent && !ResetEvent(XinputHid::finalCallbackEvent) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\xbox\\devices\\gipmanagementsvc\\lib\\xinputhidinterface.cpp",
      v6);
  memset_0(&v30, 0, 0x1A0u);
  v30 = 416;
  v31 = 0;
  v32 = InterfaceClassGuid;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpParameter + 56));
  v27 = lpParameter + 56;
  XinputHid::callbackState = 1;
  if ( (unsigned int)CM_Register_Notification(
                       &v30,
                       lpParameter,
                       &XinputHid::DeviceNotificationCallback,
                       lpParameter + 24) )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x78, v7, (const char *)0x8000FFFFLL, dwCreationFlags);
  Thread = (char *)CreateThread(0, 0, XinputHid::XinputHidInterface::WorkerThreadThunk, lpParameter, 0, 0);
  *((_QWORD *)lpParameter + 4) = Thread;
  if ( (unsigned __int64)(Thread - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x7C, v9, (const char *)0x8000FFFFLL, dwCreationFlagsa);
  v10 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))lpParameter + 1))(
          *((_QWORD *)lpParameter + 1),
          &GUID_fd249c25_76f6_448c_bcee_290d15598124,
          lpParameter);
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x80, v11, (const char *)(unsigned int)v10, dwCreationFlagsa);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)lpParameter + 16LL))(*(_QWORD *)lpParameter);
  while ( 1 )
  {
    pulLen = 0;
    if ( CM_Get_Device_Interface_List_SizeW(&pulLen, (LPGUID)&InterfaceClassGuid, 0, 0) )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x96, v12, (const char *)0x8000FFFFLL, dwCreationFlagsa);
    v13 = 2LL * pulLen;
    if ( !is_mul_ok(pulLen, 2u) )
      v13 = -1;
    v14 = (WCHAR *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v14;
    v29 = v14;
    if ( !v14 )
      wil::details::in1diag3::_FailFast_NullAlloc(retaddr, (void *)0x9A, v15, v16);
    Device_Interface_ListW = CM_Get_Device_Interface_ListW((LPGUID)&InterfaceClassGuid, 0, v14, pulLen, 0);
    if ( Device_Interface_ListW != 26 )
      break;
    operator delete(v17, v19);
  }
  if ( Device_Interface_ListW )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0xA8, v20, (const char *)0x8000FFFFLL, dwCreationFlagsa);
  if ( *v17 )
  {
    v21 = v17;
    do
    {
      if ( v21 )
        v22 = wcsnlen(v21, pulLen);
      else
        v22 = 0;
      XinputHid::XinputHidInterface::XusbDeviceInterfaceCallback(lpParameter, 0, 0, (unsigned int)(2 * v22 + 2), v21);
      v21 += (unsigned int)(v22 + 1);
    }
    while ( *v21 );
  }
  operator delete(v17, v19);
  if ( lpParameter != (char *)-56LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 56));
  return lpParameter;
}

```

## disassembly

```asm
0x18000e90c  mov     [rsp-8+arg_8], rbx
0x18000e911  mov     [rsp-8+arg_10], rsi
0x18000e916  push    rbp
0x18000e917  push    rdi
0x18000e918  push    r12
0x18000e91a  push    r14
0x18000e91c  push    r15
0x18000e91e  lea     rbp, [rsp-100h]
0x18000e926  sub     rsp, 200h
0x18000e92d  mov     rax, cs:__security_cookie
0x18000e934  xor     rax, rsp
0x18000e937  mov     [rbp+120h+var_30], rax
0x18000e93e  mov     rsi, rcx
0x18000e941  mov     [rsp+220h+var_1E0], rcx
0x18000e946  mov     [rcx+8], rdx
0x18000e94a  mov     [rcx+10h], r8
0x18000e94e  xor     r9d, r9d; lpName
0x18000e951  xor     r8d, r8d; bInitialState
0x18000e954  lea     r14d, [r9+1]
0x18000e958  mov     edx, r14d; bManualReset
0x18000e95b  xor     ecx, ecx; lpEventAttributes
0x18000e95d  call    cs:__imp_CreateEventW
0x18000e963  mov     [rsi+28h], rax
0x18000e967  xor     r9d, r9d; lpName
0x18000e96a  xor     r8d, r8d; bInitialState
0x18000e96d  mov     edx, r14d; bManualReset
0x18000e970  xor     ecx, ecx; lpEventAttributes
0x18000e972  call    cs:__imp_CreateEventW
0x18000e978  mov     [rsi+30h], rax
0x18000e97c  lea     rbx, [rsi+38h]
0x18000e980  xor     r8d, r8d; Flags
0x18000e983  xor     edx, edx; dwSpinCount
0x18000e985  mov     rcx, rbx; lpCriticalSection
0x18000e988  call    cs:__imp_InitializeCriticalSectionEx
0x18000e98e  nop
0x18000e98f  lea     rdi, [rsi+60h]
0x18000e993  mov     [rsp+220h+var_1E8], rdi
0x18000e998  xor     r12d, r12d
0x18000e99b  mov     [rdi], r12d
0x18000e99e  mov     [rdi+8], r12
0x18000e9a2  mov     [rdi+10h], r12
0x18000e9a6  lea     ecx, [r14+3Fh]; Size
0x18000e9aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e9af  mov     [rax], rax
0x18000e9b2  mov     [rax+8], rax
0x18000e9b6  mov     [rdi+8], rax
0x18000e9ba  lea     rcx, [rdi+18h]
0x18000e9be  mov     [rcx], r12
0x18000e9c1  mov     [rcx+8], r12
0x18000e9c5  mov     [rcx+10h], r12
0x18000e9c9  mov     qword ptr [rdi+30h], 7
0x18000e9d1  mov     qword ptr [rdi+38h], 8
0x18000e9d9  mov     dword ptr [rdi], 3F800000h
0x18000e9df  mov     r8, [rdi+8]
0x18000e9e3  lea     edx, [r14+0Fh]
0x18000e9e7  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>)
0x18000e9ec  nop
0x18000e9ed  mov     rax, [rsi+28h]
0x18000e9f1  sub     rax, r14
0x18000e9f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e9f8  setnbe  al
0x18000e9fb  mov     rcx, [rbp+128h]; this
0x18000ea02  test    al, al
0x18000ea04  jnz     loc_18000EC79
0x18000ea0a  mov     rax, [rsi+30h]
0x18000ea0e  sub     rax, r14
0x18000ea11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ea15  setnbe  al
0x18000ea18  mov     rcx, [rbp+128h]; this
0x18000ea1f  test    al, al
0x18000ea21  jnz     loc_18000EC8A
0x18000ea27  mov     rcx, cs:?finalCallbackEvent@XinputHid@@3PEAXEA; hEvent
0x18000ea2e  test    rcx, rcx
0x18000ea31  jz      short loc_18000EA48
0x18000ea33  call    cs:__imp_ResetEvent
0x18000ea39  mov     rcx, [rbp+128h]; this
0x18000ea40  test    eax, eax
0x18000ea42  jz      loc_18000EC9B
0x18000ea48  mov     edi, 1A0h
0x18000ea4d  mov     r8d, edi; Size
0x18000ea50  xor     edx, edx; Val
0x18000ea52  lea     rcx, [rsp+220h+var_1D0]; void *
0x18000ea57  call    memset_0
0x18000ea5c  mov     [rsp+220h+var_1D0], rdi
0x18000ea61  mov     [rsp+220h+var_1C8], r12d
0x18000ea66  movups  xmm0, xmmword ptr cs:InterfaceClassGuid.Data1
0x18000ea6d  movdqu  [rsp+220h+var_1C0], xmm0
0x18000ea73  mov     rcx, rbx; lpCriticalSection
0x18000ea76  call    cs:__imp_EnterCriticalSection
0x18000ea7c  mov     [rsp+220h+var_1E8], rbx
0x18000ea81  mov     cs:?callbackState@XinputHid@@3_JC, r14; __int64 volatile XinputHid::callbackState
0x18000ea88  mov     rdi, [rbp+128h]
0x18000ea8f  lea     r9, [rsi+18h]
0x18000ea93  lea     r8, ?DeviceNotificationCallback@XinputHid@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; XinputHid::DeviceNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18000ea9a  mov     rdx, rsi
0x18000ea9d  lea     rcx, [rsp+220h+var_1D0]
0x18000eaa2  call    cs:__imp_CM_Register_Notification
0x18000eaa8  test    eax, eax
0x18000eaaa  jnz     loc_18000ECAD
0x18000eab0  mov     [rsp+220h+lpThreadId], r12; lpThreadId
0x18000eab5  mov     [rsp+220h+dwCreationFlags], r12d; int
0x18000eaba  mov     r9, rsi; lpParameter
0x18000eabd  lea     r8, ?WorkerThreadThunk@XinputHidInterface@XinputHid@@CAKPEAX@Z; lpStartAddress
0x18000eac4  xor     edx, edx; dwStackSize
0x18000eac6  xor     ecx, ecx; lpThreadAttributes
0x18000eac8  call    cs:__imp_CreateThread
0x18000eace  mov     [rsi+20h], rax
0x18000ead2  dec     rax
0x18000ead5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ead9  setnbe  al
0x18000eadc  mov     rcx, [rbp+128h]; this
0x18000eae3  test    al, al
0x18000eae5  jnz     loc_18000ECC1
0x18000eaeb  mov     rcx, [rsi+8]
0x18000eaef  mov     rax, [rcx]
0x18000eaf2  mov     r8, rsi
0x18000eaf5  lea     rdx, _GUID_fd249c25_76f6_448c_bcee_290d15598124
0x18000eafc  mov     rax, [rax]
0x18000eaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb04  mov     rcx, [rbp+128h]; this
0x18000eb0b  test    eax, eax
0x18000eb0d  js      loc_18000ECD2
0x18000eb13  mov     rcx, [rsi]
0x18000eb16  mov     rax, [rcx]
0x18000eb19  mov     rax, [rax+10h]
0x18000eb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb22  mov     [rsp+220h+pulLen], r12d
0x18000eb27  mov     rdi, [rbp+128h]
0x18000eb2e  xor     r9d, r9d; ulFlags
0x18000eb31  xor     r8d, r8d; pDeviceID
0x18000eb34  lea     rdx, InterfaceClassGuid; InterfaceClassGuid
0x18000eb3b  lea     rcx, [rsp+220h+pulLen]; pulLen
0x18000eb40  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x18000eb46  test    eax, eax
0x18000eb48  jnz     loc_18000EC65
0x18000eb4e  mov     ecx, [rsp+220h+pulLen]
0x18000eb52  mov     eax, 2
0x18000eb57  mul     rcx
0x18000eb5a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000eb61  cmovb   rax, rcx
0x18000eb65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb6c  mov     rcx, rax; unsigned __int64
0x18000eb6f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000eb74  mov     rdi, rax
0x18000eb77  mov     [rsp+220h+var_1D8], rax
0x18000eb7c  mov     rcx, [rbp+128h]; this
0x18000eb83  test    rax, rax
0x18000eb86  jz      loc_18000EC5A
0x18000eb8c  mov     [rsp+220h+dwCreationFlags], r12d; int
0x18000eb91  mov     r9d, [rsp+220h+pulLen]; BufferLen
0x18000eb96  mov     r8, rax; Buffer
0x18000eb99  xor     edx, edx; pDeviceID
0x18000eb9b  lea     rcx, InterfaceClassGuid; InterfaceClassGuid
0x18000eba2  call    cs:__imp_CM_Get_Device_Interface_ListW
0x18000eba8  cmp     eax, 1Ah
0x18000ebab  jnz     short loc_18000EBBA
0x18000ebad  mov     rcx, rdi; void *
0x18000ebb0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ebb5  jmp     loc_18000EB22
0x18000ebba  mov     rcx, [rbp+128h]; this
0x18000ebc1  test    eax, eax
0x18000ebc3  jnz     loc_18000ECE0
0x18000ebc9  cmp     [rdi], r12w
0x18000ebcd  jz      short loc_18000EC14
0x18000ebcf  mov     r14, rdi
0x18000ebd2  test    r14, r14
0x18000ebd5  jnz     short loc_18000EBDC
0x18000ebd7  mov     r15, r12
0x18000ebda  jmp     short loc_18000EBEC
0x18000ebdc  mov     edx, [rsp+220h+pulLen]; MaxCount
0x18000ebe0  mov     rcx, r14; Source
0x18000ebe3  call    cs:__imp_wcsnlen
0x18000ebe9  mov     r15, rax
0x18000ebec  lea     r9d, ds:2[r15*2]
0x18000ebf4  mov     qword ptr [rsp+220h+dwCreationFlags], r14
0x18000ebf9  xor     r8d, r8d
0x18000ebfc  xor     edx, edx
0x18000ebfe  mov     rcx, rsi
0x18000ec01  call    ?XusbDeviceInterfaceCallback@XinputHidInterface@XinputHid@@QEAAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@KPEAG@Z; XinputHid::XinputHidInterface::XusbDeviceInterfaceCallback(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong,ushort *)
0x18000ec06  lea     eax, [r15+1]
0x18000ec0a  lea     r14, [r14+rax*2]
0x18000ec0e  cmp     [r14], r12w
0x18000ec12  jnz     short loc_18000EBD2
0x18000ec14  mov     rcx, rdi; void *
0x18000ec17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ec1c  nop
0x18000ec1d  test    rbx, rbx
0x18000ec20  jz      short loc_18000EC2C
0x18000ec22  mov     rcx, rbx; lpCriticalSection
0x18000ec25  call    cs:__imp_LeaveCriticalSection
0x18000ec2b  nop
0x18000ec2c  mov     rax, rsi
0x18000ec2f  mov     rcx, [rbp+120h+var_30]
0x18000ec36  xor     rcx, rsp; StackCookie
0x18000ec39  call    __security_check_cookie
0x18000ec3e  lea     r11, [rsp+220h+var_20]
0x18000ec46  mov     rbx, [r11+38h]
0x18000ec4a  mov     rsi, [r11+40h]
0x18000ec4e  mov     rsp, r11
0x18000ec51  pop     r15
0x18000ec53  pop     r14
0x18000ec55  pop     r12
0x18000ec57  pop     rdi
0x18000ec58  pop     rbp
0x18000ec59  retn
0x18000ec5a  mov     edx, 9Ah; void *
0x18000ec5f  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18000ec65  mov     edx, 96h; void *
0x18000ec6a  mov     r9d, 8000FFFFh; char *
0x18000ec70  mov     rcx, rdi; this
0x18000ec73  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ec79  mov     edx, 53h ; 'S'; void *
0x18000ec7e  mov     r9d, 8000FFFFh; char *
0x18000ec84  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ec8a  mov     edx, 54h ; 'T'; void *
0x18000ec8f  mov     r9d, 8000FFFFh; char *
0x18000ec95  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ec9b  lea     r8, aOnecoreuapXbox_0; "onecoreuap\\xbox\\devices\\gipmanagemen"...
0x18000eca2  mov     edx, 5Fh ; '_'; void *
0x18000eca7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ecad  mov     edx, 78h ; 'x'; void *
0x18000ecb2  mov     r9d, 8000FFFFh; char *
0x18000ecb8  mov     rcx, rdi; this
0x18000ecbb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ecc1  mov     edx, 7Ch ; '|'; void *
0x18000ecc6  mov     r9d, 8000FFFFh; char *
0x18000eccc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ecd2  mov     r9d, eax; char *
0x18000ecd5  mov     edx, 80h; void *
0x18000ecda  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000ece0  mov     edx, 0A8h; void *
0x18000ece5  mov     r9d, 8000FFFFh; char *
0x18000eceb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
