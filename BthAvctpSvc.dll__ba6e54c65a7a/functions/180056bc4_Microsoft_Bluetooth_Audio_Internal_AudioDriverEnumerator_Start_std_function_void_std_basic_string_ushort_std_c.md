# Microsoft::Bluetooth::Audio::Internal::AudioDriverEnumerator::Start(std::function<void (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)>)

- ea: `0x180056bc4`
- end: `0x180056f69`
- name: `?Start@AudioDriverEnumerator@Internal@Audio@Bluetooth@Microsoft@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z@7@@Z`
- size: `933`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180002cc0`
- `0x180002d28`
- `0x180004080`
- `0x18000e0c0`
- `0x18000e16c`
- `0x180012554`
- `0x180019f2c`
- `0x18001a0dc`
- `0x180056bc4`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180056d7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180056d7b`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180056d56`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180056d56`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Bluetooth::Audio::Internal::AudioDriverEnumerator::Start(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  const GUID *v6; // r9
  __int64 v7; // rcx
  int ObjectQuery; // eax
  int v9; // edx
  int v10; // r8d
  int v12; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v14; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+18h]

  v15 = a3;
  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(a2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(a2) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(a3) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(a3) = 0;
  }
  v6 = &WPP_76bc50ceb4f735d545ff8d598bd01df7_Traceguids;
  if ( (_BYTE)a2 || (_BYTE)a3 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      16,
      &WPP_76bc50ceb4f735d545ff8d598bd01df7_Traceguids,
      a1);
  if ( *(_QWORD *)(a1 + 128) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\audiodriverenumerator\\audiodriverenumerator.cpp",
      (const char *)0x8000000DLL,
      v12);
  if ( !*(_QWORD *)(v3 + 56) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\audiodriverenumerator\\audiodriverenumerator.cpp",
      (const char *)0x80070057LL,
      v12);
  if ( a1 + 72 != v3 )
  {
    std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(a1 + 72);
    v7 = *(_QWORD *)(v3 + 56);
    if ( v7 )
    {
      if ( v7 == v3 )
      {
        *(_QWORD *)(a1 + 128) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, a1 + 72);
        std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v3);
      }
      else
      {
        *(_QWORD *)(a1 + 128) = v7;
        *(_QWORD *)(v3 + 56) = 0;
      }
    }
  }
  if ( dword_1800775A4 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800775A4, 4, a3, v6);
    if ( dword_1800775A4 == -1 )
    {
      *(DEVPROPKEY *)byte_180076948 = DEVPKEY_DeviceInterface_ClassGuid;
      dword_18007695C = 0;
      qword_180076960 = 0;
      dword_180076968 = 13;
      dword_18007696C = 16;
      qword_180076970 = (__int64)&GUID_BLUETOOTH_LEAUDIO_SUPPORT_INTERFACE;
      dword_180076978 = 2;
      *(DEVPROPKEY *)byte_180076980 = DEVPKEY_DeviceInterface_Enabled;
      dword_180076994 = 0;
      qword_180076998 = 0;
      dword_1800769A0 = 17;
      dword_1800769A4 = 1;
      qword_1800769A8 = (__int64)byte_1800690A9;
      Init_thread_footer(&dword_1800775A4);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&void DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(
    a1 + 144,
    0);
  ObjectQuery = DevCreateObjectQuery(1, 1, 0);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\audiodriverenumerator\\audiodriverenumerator.cpp",
      (const char *)(unsigned int)ObjectQuery,
      2);
  wil::slim_event_t<1>::wait(a1 + 136);
  AcquireSRWLockShared((PSRWLOCK)a1);
  v14 = a1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v9) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v10) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(v10) = 0;
  }
  if ( (_BYTE)v9 || (_BYTE)v10 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      17,
      &WPP_76bc50ceb4f735d545ff8d598bd01df7_Traceguids,
      a1);
  *(_OWORD *)v4 = 0;
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 0;
  *(_OWORD *)v4 = *(_OWORD *)(a1 + 8);
  *(_OWORD *)(v4 + 16) = *(_OWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 7;
  *(_WORD *)(a1 + 8) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v3);
  return v4;
}

```

## disassembly

```asm
0x180056bc4  mov     [rsp+arg_8], rbx
0x180056bc9  mov     [rsp+arg_18], rbp
0x180056bce  mov     [rsp+arg_10], r8
0x180056bd3  push    rsi
0x180056bd4  push    rdi
0x180056bd5  push    r13
0x180056bd7  push    r14
0x180056bd9  push    r15
0x180056bdb  sub     rsp, 70h
0x180056bdf  mov     rsi, r8
0x180056be2  mov     rbp, rdx
0x180056be5  mov     rdi, rcx
0x180056be8  xor     r14d, r14d
0x180056beb  lea     rax, WPP_GLOBAL_Control
0x180056bf2  lea     r15d, [r14+1]
0x180056bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bfd  cmp     rcx, rax
0x180056c00  jz      short loc_180056C11
0x180056c02  test    [rcx+1Ch], r15b
0x180056c06  jz      short loc_180056C11
0x180056c08  cmp     byte ptr [rcx+19h], 5
0x180056c0c  mov     dl, r15b
0x180056c0f  jnb     short loc_180056C14
0x180056c11  mov     dl, r14b; int
0x180056c14  lea     r13, WPP_RECORDER_INITIALIZED
0x180056c1b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180056c22  jz      short loc_180056C2E
0x180056c24  cmp     [rcx+30h], r14w
0x180056c29  mov     r8b, r15b
0x180056c2c  jnz     short loc_180056C31
0x180056c2e  mov     r8b, r14b; int
0x180056c31  lea     r9, WPP_76bc50ceb4f735d545ff8d598bd01df7_Traceguids
0x180056c38  test    dl, dl
0x180056c3a  jnz     short loc_180056C41
0x180056c3c  test    r8b, r8b
0x180056c3f  jz      short loc_180056C69
0x180056c41  mov     qword ptr [rsp+98h+var_58], rdi; char
0x180056c46  mov     [rsp+98h+MessageGuid], r9; MessageGuid
0x180056c4b  mov     [rsp+98h+var_68], 10h; __int16
0x180056c52  mov     [rsp+98h+var_70], r15d; int
0x180056c57  mov     [rsp+98h+var_78], 5; int
0x180056c5c  mov     r9, [rcx+28h]; int
0x180056c60  mov     rcx, [rcx+10h]; int
0x180056c64  call    WPP_RECORDER_AND_TRACE_SF_q
0x180056c69  cmp     [rdi+80h], r14
0x180056c70  setnz   al
0x180056c73  mov     rcx, [rsp+98h]; this
0x180056c7b  test    al, al
0x180056c7d  jnz     loc_180056E73
0x180056c83  cmp     [rsi+38h], r14
0x180056c87  setz    al
0x180056c8a  mov     rcx, [rsp+98h]; this
0x180056c92  test    al, al
0x180056c94  jnz     loc_180056E8B
0x180056c9a  mov     [rsp+98h+var_40], rdi
0x180056c9f  mov     [rsp+98h+var_38], r15b
0x180056ca4  lea     rbx, [rdi+48h]
0x180056ca8  cmp     rbx, rsi
0x180056cab  jz      short loc_180056CE8
0x180056cad  mov     rcx, rbx
0x180056cb0  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x180056cb5  mov     rcx, [rsi+38h]
0x180056cb9  test    rcx, rcx
0x180056cbc  jz      short loc_180056CE8
0x180056cbe  cmp     rcx, rsi
0x180056cc1  jnz     short loc_180056CE0
0x180056cc3  mov     rax, [rcx]
0x180056cc6  mov     rdx, rbx
0x180056cc9  mov     rax, [rax+8]
0x180056ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cd2  mov     [rbx+38h], rax
0x180056cd6  mov     rcx, rsi
0x180056cd9  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x180056cde  jmp     short loc_180056CE8
0x180056ce0  mov     [rbx+38h], rcx
0x180056ce4  mov     [rsi+38h], r14
0x180056ce8  mov     ecx, cs:_tls_index
0x180056cee  mov     rax, gs:58h
0x180056cf7  mov     edx, 4
0x180056cfc  mov     rax, [rax+rcx*8]
0x180056d00  mov     eax, [rdx+rax]
0x180056d03  cmp     cs:dword_1800775A4, eax
0x180056d09  jg      loc_180056EA3
0x180056d0f  lea     rbx, [rdi+90h]
0x180056d16  xor     edx, edx
0x180056d18  mov     rcx, rbx
0x180056d1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHDEVQUERY__@@P6AXPEAU1@@Z$1?DevCloseObjectQuery@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHDEVQUERY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HDEVQUERY__ *,void (*)(HDEVQUERY__ *),&DevCloseObjectQuery(HDEVQUERY__ *),wistd::integral_constant<unsigned __int64,0>,HDEVQUERY__ *,HDEVQUERY__ *,0,std::nullptr_t>>::reset(HDEVQUERY__ *)
0x180056d20  mov     qword ptr [rsp+98h+var_58], rbx
0x180056d25  mov     [rsp+98h+MessageGuid], rdi
0x180056d2a  lea     rax, ?DevQueryResultCallbackThunk@AudioDriverEnumerator@Internal@Audio@Bluetooth@Microsoft@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; Microsoft::Bluetooth::Audio::Internal::AudioDriverEnumerator::DevQueryResultCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180056d31  mov     qword ptr [rsp+98h+var_68], rax
0x180056d36  lea     rax, qword_180076940
0x180056d3d  mov     qword ptr [rsp+98h+var_70], rax
0x180056d42  mov     dword ptr [rsp+98h+var_78], 2; int
0x180056d4a  xor     r9d, r9d
0x180056d4d  xor     r8d, r8d
0x180056d50  mov     edx, r15d
0x180056d53  mov     ecx, r15d
0x180056d56  call    cs:__imp_DevCreateObjectQuery
0x180056d5c  mov     rcx, [rsp+98h]; this
0x180056d64  test    eax, eax
0x180056d66  js      loc_180056E5E
0x180056d6c  lea     rcx, [rdi+88h]
0x180056d73  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NXZ; wil::slim_event_t<1>::wait(void)
0x180056d78  mov     rcx, rdi; SRWLock
0x180056d7b  call    cs:__imp_AcquireSRWLockShared
0x180056d81  mov     [rsp+98h+arg_0], rdi
0x180056d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d90  lea     rax, WPP_GLOBAL_Control
0x180056d97  cmp     rcx, rax
0x180056d9a  jz      short loc_180056DAB
0x180056d9c  test    [rcx+1Ch], r15b
0x180056da0  jz      short loc_180056DAB
0x180056da2  cmp     byte ptr [rcx+19h], 5
0x180056da6  mov     dl, r15b
0x180056da9  jnb     short loc_180056DAE
0x180056dab  mov     dl, r14b; int
0x180056dae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180056db5  jz      short loc_180056DC1
0x180056db7  cmp     [rcx+30h], r14w
0x180056dbc  mov     r8b, r15b
0x180056dbf  jnz     short loc_180056DC4
0x180056dc1  mov     r8b, r14b; int
0x180056dc4  test    dl, dl
0x180056dc6  jnz     short loc_180056DCD
0x180056dc8  test    r8b, r8b
0x180056dcb  jz      short loc_180056DFC
0x180056dcd  mov     qword ptr [rsp+98h+var_58], rdi; char
0x180056dd2  lea     rax, WPP_76bc50ceb4f735d545ff8d598bd01df7_Traceguids
0x180056dd9  mov     [rsp+98h+MessageGuid], rax; MessageGuid
0x180056dde  mov     [rsp+98h+var_68], 11h; __int16
0x180056de5  mov     [rsp+98h+var_70], r15d; int
0x180056dea  mov     [rsp+98h+var_78], 5; char
0x180056def  mov     r9, [rcx+28h]; int
0x180056df3  mov     rcx, [rcx+10h]; int
0x180056df7  call    WPP_RECORDER_AND_TRACE_SF_q
0x180056dfc  xorps   xmm0, xmm0
0x180056dff  movups  xmmword ptr [rbp+0], xmm0
0x180056e03  mov     [rbp+10h], r14
0x180056e07  mov     [rbp+18h], r14
0x180056e0b  movups  xmm0, xmmword ptr [rdi+8]
0x180056e0f  movups  xmmword ptr [rbp+0], xmm0
0x180056e13  movups  xmm1, xmmword ptr [rdi+18h]
0x180056e17  movups  xmmword ptr [rbp+10h], xmm1
0x180056e1b  mov     [rdi+18h], r14
0x180056e1f  mov     qword ptr [rdi+20h], 7
0x180056e27  mov     [rdi+8], r14w
0x180056e2c  lea     rcx, [rsp+98h+arg_0]
0x180056e34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180056e39  nop
0x180056e3a  mov     rcx, rsi
0x180056e3d  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x180056e42  mov     rax, rbp
0x180056e45  lea     r11, [rsp+98h+var_28]
0x180056e4a  mov     rbx, [r11+38h]
0x180056e4e  mov     rbp, [r11+48h]
0x180056e52  mov     rsp, r11
0x180056e55  pop     r15
0x180056e57  pop     r14
0x180056e59  pop     r13
0x180056e5b  pop     rdi
0x180056e5c  pop     rsi
0x180056e5d  retn
0x180056e5e  mov     r9d, eax; char *
0x180056e61  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\audio\\int"...
0x180056e68  mov     edx, 83h; void *
0x180056e6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056e73  mov     r9d, 8000000Dh; char *
0x180056e79  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\audio\\int"...
0x180056e80  mov     edx, 5Ch ; '\'; void *
0x180056e85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056e8b  mov     r9d, 80070057h; char *
0x180056e91  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\audio\\int"...
0x180056e98  mov     edx, 5Dh ; ']'; void *
0x180056e9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180056ea3  lea     rcx, dword_1800775A4
0x180056eaa  call    _Init_thread_header
0x180056eaf  cmp     cs:dword_1800775A4, 0FFFFFFFFh
0x180056eb6  jnz     loc_180056D0F
0x180056ebc  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180056ec3  movups  xmmword ptr cs:byte_180076948, xmm0
0x180056eca  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180056ed0  mov     dword ptr cs:byte_180076948+10h, eax
0x180056ed6  mov     cs:dword_18007695C, r14d
0x180056edd  mov     cs:qword_180076960, r14
0x180056ee4  mov     cs:dword_180076968, 0Dh
0x180056eee  mov     cs:dword_18007696C, 10h
0x180056ef8  lea     rax, GUID_BLUETOOTH_LEAUDIO_SUPPORT_INTERFACE
0x180056eff  mov     cs:qword_180076970, rax
0x180056f06  mov     cs:dword_180076978, 2
0x180056f10  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180056f17  movaps  xmmword ptr cs:byte_180076980, xmm0
0x180056f1e  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180056f24  mov     dword ptr cs:byte_180076980+10h, eax
0x180056f2a  mov     cs:dword_180076994, r14d
0x180056f31  mov     cs:qword_180076998, r14
0x180056f38  mov     cs:dword_1800769A0, 11h
0x180056f42  mov     cs:dword_1800769A4, r15d
0x180056f49  lea     rax, byte_1800690A9
0x180056f50  mov     cs:qword_1800769A8, rax
0x180056f57  lea     rcx, dword_1800775A4
0x180056f5e  call    _Init_thread_footer
0x180056f63  jmp     loc_180056D0F
```
