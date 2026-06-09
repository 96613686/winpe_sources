# EventScan::Initialize(unsigned __int64 *)

- ea: `0x18002c124`
- end: `0x18002c5a1`
- name: `?Initialize@EventScan@@QEAAJPEA_K@Z`
- size: `1149`
- prototype: `__int64 __fastcall(EventScan *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002384c`
- `0x180024374`

## callees

- `0x18000fa64`
- `0x1800159a4`
- `0x18001af70`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x180021790`
- `0x180022070`
- `0x18002bc6c`
- `0x18002c124`
- `0x18002d010`
- `0x18002d0b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002c1c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002c1c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c23f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c23f`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002c308`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18002c308`

## pseudocode

```c
__int64 __fastcall EventScan::Initialize(EventScan *this, unsigned __int64 *a2)
{
  __int64 v4; // rbx
  ULONGLONG TickCount64; // rbx
  __int64 v6; // r8
  LSTATUS ValueW; // eax
  __int64 v8; // r8
  bool v9; // sf
  unsigned __int64 v10; // rdi
  __int64 v11; // rcx
  int ObjectQuery; // ebx
  __int64 v13; // r8
  __int64 v15; // [rsp+50h] [rbp-69h] BYREF
  __int64 v16; // [rsp+58h] [rbp-61h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-59h] BYREF
  __int64 pvData; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v19[8]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v20[14]; // [rsp+78h] [rbp-41h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_18005A518 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_18005A518);
    if ( dword_18005A518 == -1 )
    {
      *(DEVPROPKEY *)byte_18005A140 = DEVPKEY_DeviceContainer_ConfigFlags;
      dword_18005A154 = 0;
      qword_18005A158 = 0;
      *(DEVPROPKEY *)byte_18005A160 = DEVPKEY_DeviceContainer_IsConnected;
      dword_18005A174 = 0;
      qword_18005A178 = 0;
      Init_thread_footer(&dword_18005A518);
    }
  }
  if ( dword_18005A51C > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_18005A51C);
    if ( dword_18005A51C == -1 )
    {
      *(DEVPROPKEY *)byte_180059588 = DEVPKEY_DeviceContainer_IsConnected;
      qword_1800595B0 = (__int64)&EventScan::s_devPropTrue;
      *(DEVPROPKEY *)byte_1800595C0 = DEVPKEY_DeviceContainer_ConfigFlags;
      *(DEVPROPKEY *)byte_180059630 = DEVPKEY_DeviceContainer_ConfigFlags;
      qword_1800595E8 = (__int64)&EventScan::s_fullyConfigured;
      qword_180059658 = (__int64)&EventScan::s_unconfigured;
      dword_18005959C = 0;
      qword_1800595A0 = 0;
      dword_1800595A8 = 17;
      dword_1800595AC = 1;
      dword_1800595B8 = 65538;
      dword_1800595D4 = 0;
      qword_1800595D8 = 0;
      dword_1800595E0 = 7;
      dword_1800595E4 = 4;
      dword_1800595F0 = 0x200000;
      xmmword_1800595F8 = 0;
      dword_180059628 = 2;
      xmmword_180059608 = 0;
      dword_180059644 = 0;
      xmmword_180059618 = 0;
      qword_180059648 = 0;
      dword_180059650 = 7;
      dword_180059654 = 4;
      dword_180059660 = 0x400000;
      xmmword_180059668 = 0;
      xmmword_180059678 = 0;
      xmmword_180059688 = 0;
      Init_thread_footer(&dword_18005A51C);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5f220cccee2e33150182d68011e709f6_Traceguids);
  TickCount64 = GetTickCount64();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v6, TickCount64 / 0x3E8);
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(g_hPersistentStateKey, 0, L"LastActiveTime", 8u, 0, &pvData, &pcbData);
  v9 = ValueW < 0;
  if ( ValueW > 0 )
    v9 = 1;
  if ( !v9 )
  {
    v15 = pvData;
    v10 = (MEMORY[0x7FFE0014] - pvData) / 0x2710uLL;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v8, v10 / 0x3E8);
    if ( v10 < TickCount64 )
      TickCount64 = v10;
  }
  *a2 = TickCount64;
  ObjectQuery = DevCreateObjectQuery(
                  2,
                  1,
                  2,
                  byte_18005A140,
                  7,
                  &unk_180059510,
                  EventScan::_DevQueryCallback,
                  this,
                  (char *)this + 8);
  if ( ObjectQuery >= 0 )
  {
    v20[1] = this;
    v20[0] = off_180046D08;
    v15 = 0;
    v20[13] = v20;
    if ( (int)wil::details::make_wnf_subscription_state<_DRIVER_RECOVERY_CONTEXT>(v11, v19, v13, &v15) < 0 )
      v16 = 0;
    else
      v16 = v15;
    if ( (__int64 *)((char *)this + 56) != &v16 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset((char *)this + 56);
      v16 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v16);
    wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(v19);
    if ( *((_QWORD *)this + 7) )
      *((_BYTE *)this + 16) = 1;
    else
      ObjectQuery = -2147024882;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_5f220cccee2e33150182d68011e709f6_Traceguids,
      (unsigned int)ObjectQuery);
  return (unsigned int)ObjectQuery;
}

```

## disassembly

```asm
0x18002c124  mov     [rsp-8+arg_10], rbx
0x18002c129  mov     [rsp-8+arg_18], rsi
0x18002c12e  push    rbp
0x18002c12f  push    rdi
0x18002c130  push    r13
0x18002c132  push    r14
0x18002c134  push    r15
0x18002c136  lea     rbp, [rsp-37h]
0x18002c13b  sub     rsp, 0F0h
0x18002c142  mov     rax, cs:__security_cookie
0x18002c149  xor     rax, rsp
0x18002c14c  mov     [rbp+57h+var_28], rax
0x18002c150  mov     rax, gs:58h
0x18002c159  xor     r15d, r15d
0x18002c15c  mov     r8d, cs:_tls_index
0x18002c163  mov     r14, rdx
0x18002c166  mov     edi, 4
0x18002c16b  mov     rsi, rcx
0x18002c16e  mov     rbx, [rax+r8*8]
0x18002c172  mov     eax, [rbx+rdi]
0x18002c175  cmp     cs:dword_18005A518, eax
0x18002c17b  jg      loc_18002C527
0x18002c181  mov     eax, [rbx+rdi]
0x18002c184  mov     r13d, 7
0x18002c18a  cmp     cs:dword_18005A51C, eax
0x18002c190  jg      loc_18002C3E0
0x18002c196  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c19d  lea     r13, WPP_GLOBAL_Control
0x18002c1a4  cmp     rcx, r13
0x18002c1a7  jz      short loc_18002C1C4
0x18002c1a9  test    byte ptr [rcx+1Ch], 1
0x18002c1ad  jz      short loc_18002C1C4
0x18002c1af  mov     rcx, [rcx+10h]
0x18002c1b3  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c1ba  mov     edx, 0Ah
0x18002c1bf  call    WPP_SF_
0x18002c1c4  call    cs:__imp_GetTickCount64
0x18002c1ca  mov     rbx, rax
0x18002c1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1d4  mov     rax, 624DD2F1A9FBE77h
0x18002c1de  cmp     rcx, r13
0x18002c1e1  jz      short loc_18002C20A
0x18002c1e3  test    byte ptr [rcx+1Ch], 1
0x18002c1e7  jz      short loc_18002C20A
0x18002c1e9  mov     rcx, [rcx+10h]
0x18002c1ed  mov     r9, rbx
0x18002c1f0  mul     rbx
0x18002c1f3  sub     r9, rdx
0x18002c1f6  shr     r9, 1
0x18002c1f9  add     r9, rdx
0x18002c1fc  mov     edx, 0Bh
0x18002c201  shr     r9, 9
0x18002c205  call    WPP_SF_I
0x18002c20a  mov     rcx, cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA; hkey
0x18002c211  lea     rax, [rbp+57h+var_B0]
0x18002c215  mov     [rsp+110h+pcbData], rax; pcbData
0x18002c21a  lea     r8, aLastactivetime; "LastActiveTime"
0x18002c221  lea     rax, [rbp+57h+var_A8]
0x18002c225  mov     [rbp+57h+var_A8], r15
0x18002c229  mov     r9d, 8; dwFlags
0x18002c22f  mov     [rsp+110h+pvData], rax; pvData
0x18002c234  xor     edx, edx; lpSubKey
0x18002c236  mov     [rsp+110h+pdwType], r15; pdwType
0x18002c23b  mov     [rbp+57h+var_B0], r9d
0x18002c23f  call    cs:__imp_RegGetValueW
0x18002c245  test    eax, eax
0x18002c247  jle     short loc_18002C253
0x18002c249  movzx   eax, ax
0x18002c24c  or      eax, 80070000h
0x18002c251  test    eax, eax
0x18002c253  js      short loc_18002C2C5
0x18002c255  mov     eax, dword ptr [rbp+57h+var_A8+4]
0x18002c258  mov     ecx, 7FFE0014h
0x18002c25d  mov     dword ptr [rbp+57h+var_C0+4], eax
0x18002c260  mov     eax, dword ptr [rbp+57h+var_A8]
0x18002c263  mov     dword ptr [rbp+57h+var_C0], eax
0x18002c266  mov     rax, 346DC5D63886594Bh
0x18002c270  mov     rcx, [rcx]
0x18002c273  sub     rcx, [rbp+57h+var_C0]
0x18002c277  mul     rcx
0x18002c27a  mov     rdi, rdx
0x18002c27d  shr     rdi, 0Bh
0x18002c281  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c288  cmp     rcx, r13
0x18002c28b  jz      short loc_18002C2BE
0x18002c28d  test    byte ptr [rcx+1Ch], 1
0x18002c291  jz      short loc_18002C2BE
0x18002c293  mov     rcx, [rcx+10h]
0x18002c297  mov     rax, 624DD2F1A9FBE77h
0x18002c2a1  mul     rdi
0x18002c2a4  mov     r9, rdi
0x18002c2a7  sub     r9, rdx
0x18002c2aa  shr     r9, 1
0x18002c2ad  add     r9, rdx
0x18002c2b0  mov     edx, 0Ch
0x18002c2b5  shr     r9, 9
0x18002c2b9  call    WPP_SF_I
0x18002c2be  cmp     rdi, rbx
0x18002c2c1  cmovb   rbx, rdi
0x18002c2c5  mov     ecx, 2
0x18002c2ca  mov     [r14], rbx
0x18002c2cd  lea     rax, [rsi+8]
0x18002c2d1  mov     r8d, ecx
0x18002c2d4  mov     [rsp+110h+var_D0], rax
0x18002c2d9  lea     r9, byte_18005A140
0x18002c2e0  mov     [rsp+110h+var_D8], rsi
0x18002c2e5  lea     rax, ?_DevQueryCallback@EventScan@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; EventScan::_DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18002c2ec  mov     [rsp+110h+pcbData], rax
0x18002c2f1  lea     edx, [rcx-1]
0x18002c2f4  lea     rax, unk_180059510
0x18002c2fb  mov     [rsp+110h+pvData], rax
0x18002c300  mov     dword ptr [rsp+110h+pdwType], 7
0x18002c308  call    cs:__imp_DevCreateObjectQuery
0x18002c30e  mov     ebx, eax
0x18002c310  test    eax, eax
0x18002c312  js      short loc_18002C38C
0x18002c314  lea     rax, off_180046D08
0x18002c31b  mov     [rbp+57h+var_90], rsi
0x18002c31f  mov     [rbp+57h+var_98], rax
0x18002c323  lea     r9, [rbp+57h+var_C0]
0x18002c327  lea     rax, [rbp+57h+var_98]
0x18002c32b  mov     [rbp+57h+var_C0], r15
0x18002c32f  lea     rdx, [rbp+57h+var_A0]
0x18002c333  mov     [rbp+57h+var_30], rax
0x18002c337  call    ??$make_wnf_subscription_state@U_DRIVER_RECOVERY_CONTEXT@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_DRIVER_RECOVERY_CONTEXT@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_DRIVER_RECOVERY_CONTEXT@@@01@@Z; wil::details::make_wnf_subscription_state<_DRIVER_RECOVERY_CONTEXT>(_WNF_STATE_NAME const &,wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)> &&,ulong,wil::details::wnf_subscription_state<_DRIVER_RECOVERY_CONTEXT> * *)
0x18002c33c  test    eax, eax
0x18002c33e  js      short loc_18002C34A
0x18002c340  mov     rdx, [rbp+57h+var_C0]
0x18002c344  mov     [rbp+57h+var_B8], rdx
0x18002c348  jmp     short loc_18002C351
0x18002c34a  mov     [rbp+57h+var_B8], r15
0x18002c34e  mov     rdx, r15
0x18002c351  lea     rdi, [rsi+38h]
0x18002c355  lea     rax, [rbp+57h+var_B8]
0x18002c359  cmp     rdi, rax
0x18002c35c  jz      short loc_18002C36A
0x18002c35e  mov     rcx, rdi
0x18002c361  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18002c366  mov     [rbp+57h+var_B8], r15
0x18002c36a  lea     rcx, [rbp+57h+var_B8]
0x18002c36e  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18002c373  lea     rcx, [rbp+57h+var_A0]
0x18002c377  call    ??1?$function@$$A6AXAEBU_DRIVER_RECOVERY_CONTEXT@@@Z@wistd@@QEAA@XZ; wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(void)
0x18002c37c  cmp     [rdi], r15
0x18002c37f  jz      short loc_18002C387
0x18002c381  mov     byte ptr [rsi+10h], 1
0x18002c385  jmp     short loc_18002C38C
0x18002c387  mov     ebx, 8007000Eh
0x18002c38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c393  cmp     rcx, r13
0x18002c396  jz      short loc_18002C3B6
0x18002c398  test    byte ptr [rcx+1Ch], 1
0x18002c39c  jz      short loc_18002C3B6
0x18002c39e  mov     rcx, [rcx+10h]
0x18002c3a2  lea     r8, WPP_5f220cccee2e33150182d68011e709f6_Traceguids
0x18002c3a9  mov     edx, 0Fh
0x18002c3ae  mov     r9d, ebx
0x18002c3b1  call    WPP_SF_d
0x18002c3b6  mov     eax, ebx
0x18002c3b8  mov     rcx, [rbp+57h+var_28]
0x18002c3bc  xor     rcx, rsp; StackCookie
0x18002c3bf  call    __security_check_cookie
0x18002c3c4  lea     r11, [rsp+110h+var_20]
0x18002c3cc  mov     rbx, [r11+40h]
0x18002c3d0  mov     rsi, [r11+48h]
0x18002c3d4  mov     rsp, r11
0x18002c3d7  pop     r15
0x18002c3d9  pop     r14
0x18002c3db  pop     r13
0x18002c3dd  pop     rdi
0x18002c3de  pop     rbp
0x18002c3df  retn
0x18002c3e0  lea     rcx, dword_18005A51C
0x18002c3e7  call    _Init_thread_header
0x18002c3ec  cmp     cs:dword_18005A51C, 0FFFFFFFFh
0x18002c3f3  jnz     loc_18002C196
0x18002c3f9  mov     eax, cs:DEVPKEY_DeviceContainer_IsConnected.pid
0x18002c3ff  lea     rcx, ?s_fullyConfigured@EventScan@@0KB; ulong const EventScan::s_fullyConfigured
0x18002c406  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18002c40d  mov     dword ptr cs:byte_180059588+10h, eax
0x18002c413  lea     rax, ?s_devPropTrue@EventScan@@0DB; char const EventScan::s_devPropTrue
0x18002c41a  movups  xmm1, xmmword ptr cs:DEVPKEY_DeviceContainer_ConfigFlags.fmtid.Data1
0x18002c421  mov     cs:qword_1800595B0, rax
0x18002c428  mov     edx, 4
0x18002c42d  mov     eax, cs:DEVPKEY_DeviceContainer_ConfigFlags.pid
0x18002c433  mov     dword ptr cs:byte_1800595C0+10h, eax
0x18002c439  mov     dword ptr cs:byte_180059630+10h, eax
0x18002c43f  lea     rax, ?s_unconfigured@EventScan@@0KB; ulong const EventScan::s_unconfigured
0x18002c446  movups  xmmword ptr cs:byte_180059588, xmm0
0x18002c44d  mov     cs:qword_1800595E8, rcx
0x18002c454  lea     rcx, dword_18005A51C
0x18002c45b  xorps   xmm0, xmm0
0x18002c45e  mov     cs:qword_180059658, rax
0x18002c465  mov     cs:dword_18005959C, r15d
0x18002c46c  mov     cs:qword_1800595A0, r15
0x18002c473  mov     cs:dword_1800595A8, 11h
0x18002c47d  mov     cs:dword_1800595AC, 1
0x18002c487  mov     cs:dword_1800595B8, 10002h
0x18002c491  movaps  xmmword ptr cs:byte_1800595C0, xmm1
0x18002c498  mov     cs:dword_1800595D4, r15d
0x18002c49f  mov     cs:qword_1800595D8, r15
0x18002c4a6  mov     cs:dword_1800595E0, r13d
0x18002c4ad  mov     cs:dword_1800595E4, edx
0x18002c4b3  mov     cs:dword_1800595F0, 200000h
0x18002c4bd  movups  cs:xmmword_1800595F8, xmm0
0x18002c4c4  mov     cs:dword_180059628, 2
0x18002c4ce  movups  cs:xmmword_180059608, xmm0
0x18002c4d5  mov     cs:dword_180059644, r15d
0x18002c4dc  movups  cs:xmmword_180059618, xmm0
0x18002c4e3  mov     cs:qword_180059648, r15
0x18002c4ea  movaps  xmmword ptr cs:byte_180059630, xmm1
0x18002c4f1  mov     cs:dword_180059650, r13d
0x18002c4f8  mov     cs:dword_180059654, edx
0x18002c4fe  mov     cs:dword_180059660, 400000h
0x18002c508  movups  cs:xmmword_180059668, xmm0
0x18002c50f  movups  cs:xmmword_180059678, xmm0
0x18002c516  movups  cs:xmmword_180059688, xmm0
0x18002c51d  call    _Init_thread_footer
0x18002c522  jmp     loc_18002C196
0x18002c527  lea     rcx, dword_18005A518
0x18002c52e  call    _Init_thread_header
0x18002c533  cmp     cs:dword_18005A518, 0FFFFFFFFh
0x18002c53a  jnz     loc_18002C181
0x18002c540  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_ConfigFlags.fmtid.Data1
0x18002c547  mov     eax, cs:DEVPKEY_DeviceContainer_ConfigFlags.pid
0x18002c54d  lea     rcx, dword_18005A518
0x18002c554  mov     dword ptr cs:byte_18005A140+10h, eax
0x18002c55a  mov     eax, cs:DEVPKEY_DeviceContainer_IsConnected.pid
0x18002c560  movaps  xmmword ptr cs:byte_18005A140, xmm0
0x18002c567  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_IsConnected.fmtid.Data1
0x18002c56e  mov     cs:dword_18005A154, r15d
0x18002c575  mov     cs:qword_18005A158, r15
0x18002c57c  movaps  xmmword ptr cs:byte_18005A160, xmm0
0x18002c583  mov     dword ptr cs:byte_18005A160+10h, eax
0x18002c589  mov     cs:dword_18005A174, r15d
0x18002c590  mov     cs:qword_18005A178, r15
0x18002c597  call    _Init_thread_footer
0x18002c59c  jmp     loc_18002C181
```
