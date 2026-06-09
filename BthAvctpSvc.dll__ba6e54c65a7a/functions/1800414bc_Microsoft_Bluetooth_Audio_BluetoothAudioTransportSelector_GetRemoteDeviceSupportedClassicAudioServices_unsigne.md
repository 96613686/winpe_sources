# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::GetRemoteDeviceSupportedClassicAudioServices(unsigned __int64)

- ea: `0x1800414bc`
- end: `0x180041638`
- name: `?GetRemoteDeviceSupportedClassicAudioServices@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@_K@Z`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003fe50`
- `0x180042450`

## callees

- `0x180001dd0`
- `0x1800152f0`
- `0x18003de14`
- `0x18003de3c`
- `0x18003ef34`
- `0x18003f728`
- `0x1800414bc`
- `0x1800453bc`
- `0x18004ba18`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1800415e2`
- `WS2_32!__imp_WSACleanup` at `0x1800415e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::GetRemoteDeviceSupportedClassicAudioServices(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r15
  __int64 v4; // rdi
  __int128 *v6; // rbx
  __int128 *v7; // r14
  _QWORD *v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool v11; // si
  __int64 v12; // rdx
  const char *v13; // r9
  __int128 *v16; // [rsp+38h] [rbp-A0h]
  _BYTE v17[32]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-78h] BYREF
  __int128 v19; // [rsp+80h] [rbp-58h] BYREF
  __int64 v20; // [rsp+90h] [rbp-48h] BYREF
  __int128 v21; // [rsp+98h] [rbp-40h]
  char v22; // [rsp+A8h] [rbp-30h]
  _BYTE v23[7]; // [rsp+A9h] [rbp-2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  std::vector<_GUID>::vector<_GUID>(a2);
  v6 = (__int128 *)(a1 + 28);
  v7 = v6 + 4;
  v16 = v6 + 4;
  while ( v6 != v7 )
  {
    try
    {
      v19 = *v6;
      v20 = v3;
      v21 = v19;
      v22 = 0;
      Windows::Internal::Bluetooth::Helpers::winsock_init_scope::winsock_init_scope((Windows::Internal::Bluetooth::Helpers::winsock_init_scope *)v23);
      v8 = Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::begin((__int64)&v20, v18);
      v10 = Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::end(v9, v17);
      if ( *(_BYTE *)v8 == *(_BYTE *)v10 )
      {
        if ( *(_BYTE *)v8 )
          v11 = v8[1] == *(_QWORD *)(v10 + 8);
        else
          v11 = 1;
      }
      else
      {
        v11 = 0;
      }
      Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator((Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator *)v17);
      Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator((Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator *)v18);
      if ( !v11 )
      {
        v12 = *(_QWORD *)(v4 + 8);
        if ( v12 == *(_QWORD *)(v4 + 16) )
          std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v4, v12, &v19);
        else
          std::vector<_GUID>::_Emplace_back_with_unused_capacity<_GUID const &>(v4, &v19);
      }
      WSACleanup();
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x302,
        (unsigned int)"onecore\\drivers\\bluetooth\\audio\\internal\\bluetoothaudiotransportselector\\bluetoothaudiotrans"
                      "portselector.cpp",
        v13);
      if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
        std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(a2, *(_QWORD *)(a2 + 8), &v19);
      else
        std::vector<_GUID>::_Emplace_back_with_unused_capacity<_GUID const &>(a2, &v19);
      v3 = a3;
      v7 = v16;
      v4 = a2;
    }
    ++v6;
  }
  return v4;
}

```

## disassembly

```asm
0x1800414bc  mov     [rsp+arg_0], rbx
0x1800414c1  mov     [rsp+arg_18], rsi
0x1800414c6  mov     [rsp+arg_10], r8
0x1800414cb  push    rdi
0x1800414cc  push    r14
0x1800414ce  push    r15
0x1800414d0  sub     rsp, 0C0h
0x1800414d7  mov     rax, cs:__security_cookie
0x1800414de  xor     rax, rsp
0x1800414e1  mov     [rsp+0D8h+var_28], rax
0x1800414e9  mov     r15, r8
0x1800414ec  mov     rdi, rdx
0x1800414ef  mov     rbx, rcx
0x1800414f2  mov     [rsp+0D8h+var_B0], rdx
0x1800414f7  mov     [rsp+0D8h+var_B8], 0
0x1800414ff  mov     rcx, rdx
0x180041502  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180041507  mov     [rsp+0D8h+var_B8], 1
0x18004150f  add     rbx, 1Ch
0x180041513  lea     r14, [rbx+40h]
0x180041517  mov     [rsp+0D8h+var_A0], r14
0x18004151c  mov     [rsp+0D8h+var_A8], rbx
0x180041521  cmp     rbx, r14
0x180041524  jz      loc_18004160B
0x18004152a  movups  xmm0, xmmword ptr [rbx]
0x18004152d  movdqu  [rsp+0D8h+var_58], xmm0
0x180041536  mov     [rsp+0D8h+var_48], r15
0x18004153e  movdqu  [rsp+0D8h+var_40], xmm0
0x180041547  mov     [rsp+0D8h+var_30], 0
0x18004154f  lea     rcx, [rsp+0D8h+var_2F]; this
0x180041557  call    ??0winsock_init_scope@Helpers@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::Helpers::winsock_init_scope::winsock_init_scope(void)
0x18004155c  nop
0x18004155d  lea     rdx, [rsp+0D8h+var_78]
0x180041562  lea     rcx, [rsp+0D8h+var_48]
0x18004156a  call    ?begin@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA?AViterator@12345@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::begin(void)
0x18004156f  mov     rsi, rax
0x180041572  lea     rdx, [rsp+0D8h+var_98]
0x180041577  call    ?end@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA?AViterator@12345@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::end(void)
0x18004157c  mov     rcx, rax
0x18004157f  mov     al, [rsi]
0x180041581  cmp     al, [rcx]
0x180041583  jz      short loc_18004158A
0x180041585  xor     sil, sil
0x180041588  jmp     short loc_18004159F
0x18004158a  test    al, al
0x18004158c  jz      short loc_18004159C
0x18004158e  mov     rax, [rcx+8]
0x180041592  cmp     [rsi+8], rax
0x180041596  setz    sil
0x18004159a  jmp     short loc_18004159F
0x18004159c  mov     sil, 1
0x18004159f  lea     rcx, [rsp+0D8h+var_98]; this
0x1800415a4  call    ??1iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator(void)
0x1800415a9  lea     rcx, [rsp+0D8h+var_78]; this
0x1800415ae  call    ??1iterator@sdp_service_lookup@Helpers@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::Helpers::sdp_service_lookup::iterator::~iterator(void)
0x1800415b3  test    sil, sil
0x1800415b6  jnz     short loc_1800415E2
0x1800415b8  mov     rdx, [rdi+8]
0x1800415bc  mov     rcx, rdi
0x1800415bf  cmp     rdx, [rdi+10h]
0x1800415c3  jz      short loc_1800415D4
0x1800415c5  lea     rdx, [rsp+0D8h+var_58]
0x1800415cd  call    ??$_Emplace_back_with_unused_capacity@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAAEAU_GUID@@AEBU2@@Z; std::vector<_GUID>::_Emplace_back_with_unused_capacity<_GUID const &>(_GUID const &)
0x1800415d2  jmp     short loc_1800415E2
0x1800415d4  lea     r8, [rsp+0D8h+var_58]
0x1800415dc  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x1800415e1  nop
0x1800415e2  call    cs:__imp_WSACleanup
0x1800415e8  nop
0x1800415e9  jmp     short loc_180041602
0x1800415eb  mov     r15, [rsp+0D8h+arg_10]
0x1800415f3  mov     rbx, [rsp+0D8h+var_A8]
0x1800415f8  mov     r14, [rsp+0D8h+var_A0]
0x1800415fd  mov     rdi, [rsp+0D8h+var_B0]
0x180041602  add     rbx, 10h
0x180041606  jmp     loc_18004151C
0x18004160b  mov     rax, rdi
0x18004160e  mov     rcx, [rsp+0D8h+var_28]
0x180041616  xor     rcx, rsp; StackCookie
0x180041619  call    __security_check_cookie
0x18004161e  lea     r11, [rsp+0D8h+var_18]
0x180041626  mov     rbx, [r11+20h]
0x18004162a  mov     rsi, [r11+38h]
0x18004162e  mov     rsp, r11
0x180041631  pop     r15
0x180041633  pop     r14
0x180041635  pop     rdi
0x180041636  retn
```
