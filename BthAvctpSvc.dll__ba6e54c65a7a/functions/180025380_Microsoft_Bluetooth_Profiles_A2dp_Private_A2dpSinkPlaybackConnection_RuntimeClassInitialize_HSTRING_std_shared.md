# Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::RuntimeClassInitialize(HSTRING__ *,std::shared_ptr<Microsoft::Bluetooth::Foundation::DeviceInterfaceFactory> const &)

- ea: `0x180025380`
- end: `0x1800255bc`
- name: `?RuntimeClassInitialize@A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@QEAAJPEAUHSTRING__@@AEBV?$shared_ptr@VDeviceInterfaceFactory@Foundation@Bluetooth@Microsoft@@@std@@@Z`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800252c0`

## callees

- `0x18000751c`
- `0x18000b69c`
- `0x18000de78`
- `0x1800235bc`
- `0x180025380`
- `0x180025880`
- `0x180025ad0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025447`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253e4`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::RuntimeClassInitialize(
        __int64 a1,
        HSTRING a2,
        __int64 *a3)
{
  __int64 result; // rax
  HSTRING *v6; // r14
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int StringRawBuffer; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _BYTE *, PCWSTR); // rbx
  PCWSTR v12; // rax
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  std::_Ref_count_base *v16; // rcx
  __int64 v17; // rax
  const char *v18; // r9
  int v19; // [rsp+20h] [rbp-78h]
  __int128 v20; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-48h] BYREF
  std::_Ref_count_base *v22; // [rsp+58h] [rbp-40h]
  GUID v23; // [rsp+60h] [rbp-38h] BYREF
  int v24; // [rsp+70h] [rbp-28h]
  int v25; // [rsp+74h] [rbp-24h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING v27; // [rsp+A8h] [rbp+10h] BYREF

  v27 = a2;
  if ( a2 )
  {
    v6 = (HSTRING *)(a1 + 48);
    WindowsDeleteString(*(HSTRING *)(a1 + 48));
    *v6 = 0;
    WindowsDeleteString(0);
    v7 = Microsoft::WRL::Wrappers::HString::Set(v6, &v27);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(*v6, 0);
        WPP_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_46c7da31cc553b94876790d5786b6424_Traceguids,
          StringRawBuffer,
          a1);
      }
      v10 = *a3;
      v11 = *(__int64 (__fastcall **)(__int64, _BYTE *, PCWSTR))(*(_QWORD *)v10 + 8LL);
      v20 = 0;
      v12 = WindowsGetStringRawBuffer(*v6, 0);
      try
      {
        v13 = (__int64 *)v11(v10, v21, v12);
        v14 = *v13;
        v15 = v13[1];
        *v13 = 0;
        v13[1] = 0;
        *(_QWORD *)(a1 + 56) = v14;
        v16 = *(std::_Ref_count_base **)(a1 + 64);
        *(_QWORD *)(a1 + 64) = v15;
        if ( v16 )
          std::_Ref_count_base::_Decref(v16);
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        v23 = GUID_0e62540f_bac4_4b85_b344_0d82ed5008ac;
        v24 = 5;
        v25 = 1;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, GUID *, __int64, _QWORD, __int128 *))(**(_QWORD **)(a1 + 56) + 32LL))(
                *(_QWORD *)(a1 + 56),
                v21,
                3080207,
                &v23,
                24,
                0,
                &v20);
        std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(a1 + 72, v17);
        if ( v22 )
          std::_Ref_count_base::_Decref(v22);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_46c7da31cc553b94876790d5786b6424_Traceguids, a1);
        }
        result = 0;
      }
      catch ( ... )
      {
        LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x34,
                         (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
                         v18);
        return (unsigned int)v27;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
        (const char *)(unsigned int)v7,
        v19);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
      (const char *)0x80070057LL,
      v19);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180025380  mov     [rsp+arg_0], rbx
0x180025385  mov     [rsp+arg_10], rsi
0x18002538a  mov     [rsp+arg_8], rdx
0x18002538f  push    rdi
0x180025390  push    r12
0x180025392  push    r14
0x180025394  sub     rsp, 80h
0x18002539b  mov     rdi, r8
0x18002539e  mov     rsi, rcx
0x1800253a1  test    rdx, rdx
0x1800253a4  jnz     short loc_1800253CE
0x1800253a6  mov     rcx, [rsp+98h]; this
0x1800253ae  mov     ebx, 80070057h
0x1800253b3  mov     r9d, ebx; char *
0x1800253b6  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\bluetooth\\profiles\\"...
0x1800253bd  mov     edx, 1Ch; void *
0x1800253c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253c7  mov     eax, ebx
0x1800253c9  jmp     loc_1800255A2
0x1800253ce  lea     r14, [rcx+30h]
0x1800253d2  mov     rcx, [r14]; string
0x1800253d5  call    cs:__imp_WindowsDeleteString
0x1800253db  mov     qword ptr [r14], 0
0x1800253e2  xor     ecx, ecx; string
0x1800253e4  call    cs:__imp_WindowsDeleteString
0x1800253ea  lea     rdx, [rsp+98h+arg_8]; HSTRING *
0x1800253f2  mov     rcx, r14; newString
0x1800253f5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800253fa  mov     ebx, eax
0x1800253fc  test    eax, eax
0x1800253fe  jns     short loc_180025423
0x180025400  mov     rcx, [rsp+98h]; this
0x180025408  mov     r9d, eax; char *
0x18002540b  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180025412  mov     edx, 1Eh; void *
0x180025417  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002541c  mov     eax, ebx
0x18002541e  jmp     loc_1800255A2
0x180025423  lea     r12, WPP_GLOBAL_Control
0x18002542a  mov     rax, cs:WPP_GLOBAL_Control
0x180025431  cmp     rax, r12
0x180025434  jz      short loc_180025471
0x180025436  test    byte ptr [rax+1Ch], 1
0x18002543a  jz      short loc_180025471
0x18002543c  cmp     byte ptr [rax+19h], 4
0x180025440  jb      short loc_180025471
0x180025442  xor     edx, edx; length
0x180025444  mov     rcx, [r14]; string
0x180025447  call    cs:__imp_WindowsGetStringRawBuffer
0x18002544d  mov     edx, 0Ah
0x180025452  mov     [rsp+98h+var_78], rsi
0x180025457  mov     r9, rax
0x18002545a  lea     r8, WPP_46c7da31cc553b94876790d5786b6424_Traceguids
0x180025461  mov     rcx, cs:WPP_GLOBAL_Control
0x180025468  mov     rcx, [rcx+10h]
0x18002546c  call    WPP_SF_Sq
0x180025471  mov     rdi, [rdi]
0x180025474  mov     rax, [rdi]
0x180025477  mov     rbx, [rax+8]
0x18002547b  xorps   xmm0, xmm0
0x18002547e  movdqu  [rsp+98h+var_58], xmm0
0x180025484  xor     edx, edx; length
0x180025486  mov     rcx, [r14]; string
0x180025489  call    cs:__imp_WindowsGetStringRawBuffer
0x18002548f  lea     rcx, [rsp+98h+var_58]
0x180025494  mov     [rsp+98h+var_68], rcx
0x180025499  mov     dword ptr [rsp+98h+var_70], 40000000h
0x1800254a1  mov     dword ptr [rsp+98h+var_78], 3
0x1800254a9  mov     r9d, 0C0000000h
0x1800254af  mov     r8, rax
0x1800254b2  lea     rdx, [rsp+98h+var_48]
0x1800254b7  mov     rcx, rdi
0x1800254ba  mov     rax, rbx
0x1800254bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254c2  mov     rcx, [rax]
0x1800254c5  mov     rdx, [rax+8]
0x1800254c9  mov     qword ptr [rax], 0
0x1800254d0  mov     qword ptr [rax+8], 0
0x1800254d8  mov     [rsi+38h], rcx
0x1800254dc  mov     rcx, [rsi+40h]; this
0x1800254e0  mov     [rsi+40h], rdx
0x1800254e4  test    rcx, rcx
0x1800254e7  jz      short loc_1800254EE
0x1800254e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800254ee  mov     rcx, [rsp+98h+var_40]; this
0x1800254f3  test    rcx, rcx
0x1800254f6  jz      short loc_1800254FD
0x1800254f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800254fd  movups  xmm0, xmmword ptr cs:_GUID_0e62540f_bac4_4b85_b344_0d82ed5008ac.Data1
0x180025504  movdqu  [rsp+98h+var_38], xmm0
0x18002550a  mov     [rsp+98h+var_28], 5
0x180025512  mov     [rsp+98h+var_24], 1
0x18002551a  mov     rcx, [rsi+38h]
0x18002551e  mov     rax, [rcx]
0x180025521  mov     [rsp+98h+var_70], 0
0x18002552a  mov     [rsp+98h+var_78], 18h
0x180025533  lea     r9, [rsp+98h+var_38]
0x180025538  mov     r8d, 2F000Fh
0x18002553e  lea     rdx, [rsp+98h+var_48]
0x180025543  mov     rax, [rax+20h]
0x180025547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002554c  lea     rcx, [rsi+48h]
0x180025550  mov     rdx, rax
0x180025553  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x180025558  mov     rcx, [rsp+98h+var_40]; this
0x18002555d  test    rcx, rcx
0x180025560  jz      short loc_180025567
0x180025562  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025567  mov     rcx, cs:WPP_GLOBAL_Control
0x18002556e  cmp     rcx, r12
0x180025571  jz      short loc_180025597
0x180025573  test    byte ptr [rcx+1Ch], 1
0x180025577  jz      short loc_180025597
0x180025579  cmp     byte ptr [rcx+19h], 5
0x18002557d  jb      short loc_180025597
0x18002557f  mov     edx, 0Bh
0x180025584  mov     r9, rsi
0x180025587  lea     r8, WPP_46c7da31cc553b94876790d5786b6424_Traceguids
0x18002558e  mov     rcx, [rcx+10h]
0x180025592  call    WPP_SF_q
0x180025597  xor     eax, eax
0x180025599  jmp     short loc_1800255A2
0x18002559b  mov     eax, dword ptr [rsp+98h+arg_8]
0x1800255a2  lea     r11, [rsp+98h+var_18]
0x1800255aa  mov     rbx, [r11+20h]
0x1800255ae  mov     rsi, [r11+30h]
0x1800255b2  mov     rsp, r11
0x1800255b5  pop     r14
0x1800255b7  pop     r12
0x1800255b9  pop     rdi
0x1800255ba  retn
```
