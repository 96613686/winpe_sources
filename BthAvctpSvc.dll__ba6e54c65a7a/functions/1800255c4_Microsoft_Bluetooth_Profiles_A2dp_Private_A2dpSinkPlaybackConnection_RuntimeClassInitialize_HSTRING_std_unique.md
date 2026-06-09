# Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::RuntimeClassInitialize(HSTRING__ *,std::unique_ptr<Microsoft::Bluetooth::Foundation::DeviceIoTarget,std::default_delete<Microsoft::Bluetooth::Foundation::DeviceIoTarget>>)

- ea: `0x1800255c4`
- end: `0x180025879`
- name: `?RuntimeClassInitialize@A2dpSinkPlaybackConnection@Private@A2dp@Profiles@Bluetooth@Microsoft@@QEAAJPEAUHSTRING__@@V?$unique_ptr@VDeviceIoTarget@Foundation@Bluetooth@Microsoft@@U?$default_delete@VDeviceIoTarget@Foundation@Bluetooth@Microsoft@@@std@@@std@@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800252c0`

## callees

- `0x18000751c`
- `0x18000b3d4`
- `0x18000b7e4`
- `0x18000de78`
- `0x180019ce0`
- `0x18001a564`
- `0x18001a6c0`
- `0x18001dc90`
- `0x18001f0f8`
- `0x1800235bc`
- `0x1800255c4`
- `0x180025880`
- `0x180025ad0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002569e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002569e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025627`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025632`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Bluetooth::Profiles::A2dp::Private::A2dpSinkPlaybackConnection::RuntimeClassInitialize(
        __int64 a1,
        HSTRING a2,
        _QWORD *a3)
{
  __int64 result; // rax
  HSTRING *v6; // r14
  int v7; // eax
  unsigned int v8; // esi
  unsigned int StringRawBuffer; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  Microsoft::Bluetooth::Foundation::DeviceIoTarget *v12; // rsi
  PCWSTR v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-158h]
  GUID v18; // [rsp+30h] [rbp-148h] BYREF
  int v19; // [rsp+40h] [rbp-138h]
  int v20; // [rsp+44h] [rbp-134h]
  PCWSTR v21; // [rsp+50h] [rbp-128h]
  __int64 v22; // [rsp+58h] [rbp-120h]
  _BYTE v23[8]; // [rsp+60h] [rbp-118h] BYREF
  std::_Ref_count_base *v24; // [rsp+68h] [rbp-110h]
  _BYTE v25[40]; // [rsp+70h] [rbp-108h] BYREF
  _BYTE v26[8]; // [rsp+98h] [rbp-E0h] BYREF
  _QWORD v27[14]; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v28[13]; // [rsp+110h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]
  HSTRING v30; // [rsp+188h] [rbp+10h] BYREF
  _QWORD *v31; // [rsp+190h] [rbp+18h]

  v31 = a3;
  v30 = a2;
  if ( a2 )
  {
    v6 = (HSTRING *)(a1 + 48);
    WindowsDeleteString(*(HSTRING *)(a1 + 48));
    *v6 = 0;
    WindowsDeleteString(0);
    v7 = Microsoft::WRL::Wrappers::HString::Set(v6, &v30);
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
          12,
          (unsigned int)&WPP_46c7da31cc553b94876790d5786b6424_Traceguids,
          StringRawBuffer,
          a1);
      }
      v10 = *a3;
      *a3 = 0;
      v11 = *(_QWORD *)(a1 + 88);
      *(_QWORD *)(a1 + 88) = v10;
      if ( v11 )
        std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()();
      v12 = *(Microsoft::Bluetooth::Foundation::DeviceIoTarget **)(a1 + 88);
      v28[7] = 0;
      v27[6] = 0;
      v18 = (GUID)0x3C0000000uLL;
      LOBYTE(v20) = 0;
      v13 = WindowsGetStringRawBuffer(*v6, 0);
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      try
      {
        v21 = v13;
        v22 = v14;
        Microsoft::Bluetooth::Foundation::DeviceIoTarget::Open(v12, (__int64)v28);
        v18 = GUID_0e62540f_bac4_4b85_b344_0d82ed5008ac;
        v19 = 5;
        v20 = 1;
        Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>::RequestBuffer<KSIDENTIFIER>(
          (__int64)v25,
          (__int64)&v18);
        v30 = 0;
        Microsoft::Bluetooth::Foundation::DeviceIoTarget::DeviceIoControl<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t,1,1>(
          *(Microsoft::Bluetooth::Foundation::DeviceIoTarget **)(a1 + 88),
          (__int64)v23,
          v15,
          (__int64)v25,
          (__int64)&v30);
        v27[0] = off_1800612A0;
        v27[1] = a1;
        v27[13] = v27;
        Microsoft::Bluetooth::Foundation::Future<Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t>>::Then(
          v23,
          v26);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_46c7da31cc553b94876790d5786b6424_Traceguids, a1);
        }
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        std::vector<unsigned char>::_Tidy(v25);
        std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(a3);
        result = 0;
      }
      catch ( ... )
      {
        LODWORD(v30) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x50,
                         (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
                         v16);
        std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(v31);
        return (unsigned int)v30;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
        (const char *)(unsigned int)v7,
        v17);
      std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(a3);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\a2dp\\interface\\lib\\a2dpsinkplaybackconnection.cpp",
      (const char *)0x80070057LL,
      v17);
    std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(a3);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800255c4  mov     [rsp+arg_0], rbx
0x1800255c9  mov     [rsp+arg_10], r8
0x1800255ce  mov     [rsp+arg_8], rdx
0x1800255d3  push    rsi
0x1800255d4  push    rdi
0x1800255d5  push    r12
0x1800255d7  push    r14
0x1800255d9  push    r15
0x1800255db  sub     rsp, 150h
0x1800255e2  mov     rbx, r8
0x1800255e5  mov     rdi, rcx
0x1800255e8  xor     r15d, r15d
0x1800255eb  test    rdx, rdx
0x1800255ee  jnz     short loc_180025620
0x1800255f0  mov     rcx, [rsp+178h]; this
0x1800255f8  mov     edi, 80070057h
0x1800255fd  mov     r9d, edi; char *
0x180025600  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180025607  lea     edx, [r15+3Ah]; void *
0x18002560b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025610  nop
0x180025611  mov     rcx, rbx
0x180025614  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x180025619  mov     eax, edi
0x18002561b  jmp     loc_180025861
0x180025620  lea     r14, [rcx+30h]
0x180025624  mov     rcx, [r14]; string
0x180025627  call    cs:__imp_WindowsDeleteString
0x18002562d  mov     [r14], r15
0x180025630  xor     ecx, ecx; string
0x180025632  call    cs:__imp_WindowsDeleteString
0x180025638  lea     rdx, [rsp+178h+arg_8]; HSTRING *
0x180025640  mov     rcx, r14; newString
0x180025643  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180025648  mov     esi, eax
0x18002564a  test    eax, eax
0x18002564c  jns     short loc_18002567A
0x18002564e  mov     rcx, [rsp+178h]; this
0x180025656  mov     r9d, eax; char *
0x180025659  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180025660  mov     edx, 3Ch ; '<'; void *
0x180025665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002566a  nop
0x18002566b  mov     rcx, rbx
0x18002566e  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x180025673  mov     eax, esi
0x180025675  jmp     loc_180025861
0x18002567a  lea     r12, WPP_GLOBAL_Control
0x180025681  mov     rax, cs:WPP_GLOBAL_Control
0x180025688  cmp     rax, r12
0x18002568b  jz      short loc_1800256C8
0x18002568d  test    byte ptr [rax+1Ch], 1
0x180025691  jz      short loc_1800256C8
0x180025693  cmp     byte ptr [rax+19h], 4
0x180025697  jb      short loc_1800256C8
0x180025699  xor     edx, edx; length
0x18002569b  mov     rcx, [r14]; string
0x18002569e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800256a4  mov     edx, 0Ch
0x1800256a9  mov     qword ptr [rsp+178h+var_158], rdi
0x1800256ae  mov     r9, rax
0x1800256b1  lea     r8, WPP_46c7da31cc553b94876790d5786b6424_Traceguids
0x1800256b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256bf  mov     rcx, [rcx+10h]
0x1800256c3  call    WPP_SF_Sq
0x1800256c8  mov     rax, [rbx]
0x1800256cb  mov     [rbx], r15
0x1800256ce  mov     rdx, [rdi+58h]
0x1800256d2  mov     [rdi+58h], rax
0x1800256d6  test    rdx, rdx
0x1800256d9  jz      short loc_1800256E0
0x1800256db  call    ??R?$default_delete@VThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVThreadProcessorControl@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::ThreadProcessorControl>::operator()(Microsoft::Bluetooth::Foundation::ThreadProcessorControl *)
0x1800256e0  mov     rsi, [rdi+58h]
0x1800256e4  mov     [rsp+178h+var_30], r15
0x1800256ec  mov     [rsp+178h+var_A8], r15
0x1800256f4  mov     dword ptr [rsp+178h+var_148], 0C0000000h
0x1800256fc  mov     dword ptr [rsp+178h+var_148+4], 3
0x180025704  mov     byte ptr [rsp+178h+var_148+8], r15b
0x180025709  xor     eax, eax
0x18002570b  mov     word ptr [rsp+178h+var_148+9], ax
0x180025710  mov     byte ptr [rsp+178h+var_148+0Bh], al
0x180025714  mov     dword ptr [rsp+178h+var_148+0Ch], r15d
0x180025719  mov     byte ptr [rsp+178h+var_134], r15b
0x18002571e  xor     edx, edx; length
0x180025720  mov     rcx, [r14]; string
0x180025723  call    cs:__imp_WindowsGetStringRawBuffer
0x180025729  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002572d  inc     rdx
0x180025730  cmp     [rax+rdx*2], r15w
0x180025735  jnz     short loc_18002572D
0x180025737  mov     [rsp+178h+var_128], rax
0x18002573c  mov     [rsp+178h+var_120], rdx
0x180025741  lea     rax, [rsp+178h+var_68]
0x180025749  mov     qword ptr [rsp+178h+var_158], rax; __int64
0x18002574e  lea     r9, [rsp+178h+var_E0]
0x180025756  lea     r8, [rsp+178h+var_148]
0x18002575b  lea     rdx, [rsp+178h+var_128]
0x180025760  mov     rcx, rsi; this
0x180025763  call    ?Open@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@QEAAXV?$basic_zstring_view@G@wil@@AEBUOptions@1234@V?$function@$$A6AXAEBUDevicePnpCustomNotification@Foundation@Bluetooth@Microsoft@@@Z@std@@V?$function@$$A6AXW4State@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@PEAX@Z@9@@Z; Microsoft::Bluetooth::Foundation::DeviceIoTarget::Open(wil::basic_zstring_view<ushort>,Microsoft::Bluetooth::Foundation::DeviceIoTarget::Options const &,std::function<void (Microsoft::Bluetooth::Foundation::DevicePnpCustomNotification const &)>,std::function<void (Microsoft::Bluetooth::Foundation::DeviceIoTarget::State,void *)>)
0x180025768  movups  xmm0, xmmword ptr cs:_GUID_0e62540f_bac4_4b85_b344_0d82ed5008ac.Data1
0x18002576f  movdqu  [rsp+178h+var_148], xmm0
0x180025775  mov     [rsp+178h+var_138], 5
0x18002577d  mov     [rsp+178h+var_134], 1
0x180025785  lea     rdx, [rsp+178h+var_148]
0x18002578a  lea     rcx, [rsp+178h+var_108]
0x18002578f  call    ??$?0UKSIDENTIFIER@@X@?$RequestBuffer@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@QEAA@AEBUKSIDENTIFIER@@@Z; Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>::RequestBuffer<KSIDENTIFIER>(KSIDENTIFIER const &)
0x180025794  nop
0x180025795  mov     [rsp+178h+arg_8], r15
0x18002579d  lea     rax, [rsp+178h+arg_8]
0x1800257a5  mov     qword ptr [rsp+178h+var_158], rax; __int64
0x1800257aa  lea     r9, [rsp+178h+var_108]
0x1800257af  lea     rdx, [rsp+178h+var_118]
0x1800257b4  mov     rcx, [rdi+58h]; this
0x1800257b8  call    ??$DeviceIoControl@V?$RequestBuffer@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T$00$00@DeviceIoTarget@Foundation@Bluetooth@Microsoft@@QEAA?A_PI$$QEAV?$RequestBuffer@UKSIDENTIFIER@@@123@$$QEA$$T@Z
0x1800257bd  lea     rax, off_1800612A0
0x1800257c4  mov     [rsp+178h+var_D8], rax
0x1800257cc  mov     [rsp+178h+var_D0], rdi
0x1800257d4  lea     rax, [rsp+178h+var_D8]
0x1800257dc  mov     [rsp+178h+var_70], rax
0x1800257e4  lea     rdx, [rsp+178h+var_E0]
0x1800257ec  lea     rcx, [rsp+178h+var_118]
0x1800257f1  call    ?Then@?$Future@U?$IoTargetIoctlResult@V?$RequestBuffer@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@QEAAXV?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBuffer@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@@Z; Microsoft::Bluetooth::Foundation::Future<Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t>>::Then(wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBuffer<KSIDENTIFIER>,std::nullptr_t>)>)
0x1800257f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257fd  cmp     rcx, r12
0x180025800  jz      short loc_180025826
0x180025802  test    byte ptr [rcx+1Ch], 1
0x180025806  jz      short loc_180025826
0x180025808  cmp     byte ptr [rcx+19h], 5
0x18002580c  jb      short loc_180025826
0x18002580e  mov     edx, 0Eh
0x180025813  mov     r9, rdi
0x180025816  lea     r8, WPP_46c7da31cc553b94876790d5786b6424_Traceguids
0x18002581d  mov     rcx, [rcx+10h]
0x180025821  call    WPP_SF_q
0x180025826  mov     rcx, [rsp+178h+var_110]; this
0x18002582b  test    rcx, rcx
0x18002582e  jz      short loc_180025836
0x180025830  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025835  nop
0x180025836  lea     rcx, [rsp+178h+var_108]
0x18002583b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180025840  nop
0x180025841  mov     rcx, rbx
0x180025844  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x180025849  xor     eax, eax
0x18002584b  jmp     short loc_180025861
0x18002584d  mov     rcx, [rsp+178h+arg_10]
0x180025855  call    ??1?$unique_ptr@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@VRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>::~unique_ptr<Microsoft::Bluetooth::Foundation::Details::RequestDispatcher>(void)
0x18002585a  mov     eax, dword ptr [rsp+178h+arg_8]
0x180025861  mov     rbx, [rsp+178h+arg_0]
0x180025869  add     rsp, 150h
0x180025870  pop     r15
0x180025872  pop     r14
0x180025874  pop     r12
0x180025876  pop     rdi
0x180025877  pop     rsi
0x180025878  retn
```
