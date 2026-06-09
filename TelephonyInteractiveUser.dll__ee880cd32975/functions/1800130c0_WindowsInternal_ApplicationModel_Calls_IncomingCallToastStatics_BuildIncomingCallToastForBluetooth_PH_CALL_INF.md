# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToastForBluetooth(PH_CALL_INFO const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800130c0`
- end: `0x1800136be`
- name: `?_BuildIncomingCallToastForBluetooth@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJAEBUPH_CALL_INFO@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x1800027c0`
- `0x180004a0c`
- `0x180004d80`
- `0x180005a90`
- `0x180011e68`
- `0x1800127d8`
- `0x1800130c0`
- `0x180014d98`
- `0x180019010`

## import_xrefs

- `PhoneOm!GetBluetoothHandsFreeLineInfo` at `0x1800132d5`
- `PhoneOm!GetBluetoothHandsFreeLineInfo` at `0x1800132d5`
- `PhoneUtil!GetDisplayNameFromCallInformation` at `0x18001347f`
- `PhoneUtil!GetDisplayNameFromCallInformation` at `0x18001347f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013207`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013416`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180013408`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180013408`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_BuildIncomingCallToastForBluetooth(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int128 v4; // xmm0
  bool v8; // al
  __int64 v9; // r8
  bool v10; // zf
  __int64 (__fastcall *v11)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64, __int64, void **); // rax
  signed int BluetoothHandsFreeLineInfo; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  signed int LastError; // eax
  __int64 v24; // r8
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // r8
  WCHAR Buffer[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v31[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+82h] [rbp-7Eh]
  int v34; // [rsp+8Ah] [rbp-76h]
  __int16 v35; // [rsp+8Eh] [rbp-72h]
  void *Block[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A2h] [rbp-5Eh]
  int v39; // [rsp+AAh] [rbp-56h]
  __int16 v40; // [rsp+AEh] [rbp-52h]
  void *v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v42; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+C2h] [rbp-3Eh]
  int v44; // [rsp+CAh] [rbp-36h]
  __int16 v45; // [rsp+CEh] [rbp-32h]
  void *v46[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v47; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v48; // [rsp+E2h] [rbp-1Eh]
  int v49; // [rsp+EAh] [rbp-16h]
  __int16 v50; // [rsp+EEh] [rbp-12h]
  void *v51[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v52; // [rsp+100h] [rbp+0h] BYREF
  __int64 v53; // [rsp+102h] [rbp+2h]
  int v54; // [rsp+10Ah] [rbp+Ah]
  __int16 v55; // [rsp+10Eh] [rbp+Eh]
  void *v56[2]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v57; // [rsp+120h] [rbp+20h] BYREF
  __int64 v58; // [rsp+122h] [rbp+22h]
  int v59; // [rsp+12Ah] [rbp+2Ah]
  __int16 v60; // [rsp+12Eh] [rbp+2Eh]
  _BYTE v61[16]; // [rsp+130h] [rbp+30h] BYREF
  int v62; // [rsp+140h] [rbp+40h]
  _BYTE v63[160]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR v64[264]; // [rsp+3F0h] [rbp+2F0h] BYREF

  v3 = a2 + 3060;
  v4 = *(_OWORD *)(a2 + 3060);
  v33 = 0;
  v31[0] = &v32;
  v34 = 0;
  v31[1] = &v32;
  v35 = 0;
  Block[0] = &v37;
  v32 = 0;
  Block[1] = &v37;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v37 = 0;
  *(_OWORD *)Buffer = v4;
  v8 = WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(
         a1,
         (struct _GUID *)Buffer);
  v9 = a2 + 3044;
  v10 = !v8;
  v11 = *(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64, __int64, void **))(*(_QWORD *)a1 + 176LL);
  if ( v10 )
  {
    BluetoothHandsFreeLineInfo = v11(a1, 6, v9, v31);
    if ( BluetoothHandsFreeLineInfo < 0 )
    {
      v14 = 255;
      goto LABEL_4;
    }
    *(_QWORD *)Buffer = 0;
    if ( !LoadStringW(g_resourceDll, 0x2719u, Buffer, 0) )
    {
      Log_AssertionEvent_0();
      __int2c();
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             Block,
                             *(_QWORD *)Buffer) )
    {
      Log_HREvent_1(2147942414LL, 0, v16, 256);
LABEL_54:
      if ( Block[0] != &v37 )
        operator delete(Block[0]);
      if ( v31[0] != &v32 )
        operator delete(v31[0]);
      return 2147942414LL;
    }
  }
  else
  {
    BluetoothHandsFreeLineInfo = v11(a1, 4, v9, v31);
    if ( BluetoothHandsFreeLineInfo < 0 )
    {
      v14 = 251;
LABEL_4:
      Log_HREvent_1((unsigned int)BluetoothHandsFreeLineInfo, 1, v13, v14);
LABEL_5:
      if ( Block[0] != &v37 )
        operator delete(Block[0]);
      if ( v31[0] != &v32 )
        operator delete(v31[0]);
      return (unsigned int)BluetoothHandsFreeLineInfo;
    }
  }
  v43 = 0;
  v41[0] = &v42;
  v44 = 0;
  v41[1] = &v42;
  v17 = *(_QWORD *)a1;
  v45 = 0;
  v42 = 0;
  BluetoothHandsFreeLineInfo = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64, void **))(v17 + 96))(
                                 a1,
                                 a2,
                                 v41);
  if ( BluetoothHandsFreeLineInfo < 0 )
  {
    v19 = 261;
LABEL_18:
    Log_HREvent_1((unsigned int)BluetoothHandsFreeLineInfo, 1, v18, v19);
LABEL_19:
    if ( v41[0] != &v42 )
      operator delete(v41[0]);
    goto LABEL_5;
  }
  memset_0(v61, 0, 0x220u);
  BluetoothHandsFreeLineInfo = GetBluetoothHandsFreeLineInfo(v3, v61);
  if ( BluetoothHandsFreeLineInfo < 0 )
  {
    v19 = 264;
    goto LABEL_18;
  }
  v46[0] = &v47;
  v46[1] = &v47;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  if ( ((v61[0] & 2) == 0 || !v62)
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v46,
                           L"ms-winsoundevent:notification.looping.call") )
  {
    Log_HREvent_1(2147942414LL, 0, v20, 269);
LABEL_50:
    if ( v46[0] != &v47 )
      operator delete(v46[0]);
    if ( v41[0] != &v42 )
      operator delete(v41[0]);
    goto LABEL_54;
  }
  v53 = 0;
  v51[0] = &v52;
  v54 = 0;
  v51[1] = &v52;
  v55 = 0;
  v52 = 0;
  v21 = WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_SetHfpImagePath(a1, v51);
  BluetoothHandsFreeLineInfo = v21;
  if ( v21 < 0 )
  {
    Log_HREvent_1((unsigned int)v21, 1, v22, 273);
LABEL_29:
    if ( v51[0] != &v52 )
      operator delete(v51[0]);
    if ( v46[0] != &v47 )
      operator delete(v46[0]);
    goto LABEL_19;
  }
  v58 = 0;
  v56[0] = &v57;
  v59 = 0;
  v56[1] = &v57;
  v60 = 0;
  v57 = 0;
  if ( !*(_WORD *)(a2 + 1392) )
  {
    if ( GetSystemWindowsDirectoryW(v64, 0x104u) )
    {
      v27 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
              v56,
              L"%s\\SystemResources\\Windows.Systemtoast.Calling\\Images\\Placeholder_buddy.png",
              v64);
      BluetoothHandsFreeLineInfo = v27;
      if ( v27 >= 0 )
        goto LABEL_38;
      Log_HREvent_1((unsigned int)v27, 1, v28, 239);
    }
    else
    {
      LastError = GetLastError();
      BluetoothHandsFreeLineInfo = LastError;
      if ( LastError > 0 )
        BluetoothHandsFreeLineInfo = (unsigned __int16)LastError | 0x80070000;
      Log_HREvent_1((unsigned int)BluetoothHandsFreeLineInfo, 0, v24, 237);
      if ( BluetoothHandsFreeLineInfo >= 0 )
        goto LABEL_38;
    }
    v26 = 278;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v56,
                           a2 + 1392) )
  {
    Log_HREvent_1(2147942414LL, 0, v29, 282);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    if ( v51[0] != &v52 )
      operator delete(v51[0]);
    goto LABEL_50;
  }
LABEL_38:
  memset_0(v63, 0, sizeof(v63));
  BluetoothHandsFreeLineInfo = GetDisplayNameFromCallInformation(
                                 a2,
                                 a2 + 160,
                                 (*(_DWORD *)(a2 + 3036) & 3u) << 10,
                                 v63,
                                 80);
  if ( BluetoothHandsFreeLineInfo < 0 )
  {
    v26 = 288;
    goto LABEL_43;
  }
  BluetoothHandsFreeLineInfo = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *, __int64, void *, void *, _BYTE *, void *, void *, void *, void *, __int64))(*(_QWORD *)a1 + 88LL))(
                                 a1,
                                 a2 + 5784,
                                 v31[0],
                                 v51[0],
                                 v63,
                                 Block[0],
                                 v56[0],
                                 v46[0],
                                 v41[0],
                                 a3);
  if ( BluetoothHandsFreeLineInfo < 0 )
  {
    v26 = 299;
LABEL_43:
    Log_HREvent_1((unsigned int)BluetoothHandsFreeLineInfo, 1, v25, v26);
    if ( v56[0] != &v57 )
      operator delete(v56[0]);
    goto LABEL_29;
  }
  if ( v56[0] != &v57 )
    operator delete(v56[0]);
  if ( v51[0] != &v52 )
    operator delete(v51[0]);
  if ( v46[0] != &v47 )
    operator delete(v46[0]);
  if ( v41[0] != &v42 )
    operator delete(v41[0]);
  if ( Block[0] != &v37 )
    operator delete(Block[0]);
  if ( v31[0] != &v32 )
    operator delete(v31[0]);
  return 0;
}

```

## disassembly

```asm
0x1800130c0  push    rbp
0x1800130c2  push    rbx
0x1800130c3  push    rsi
0x1800130c4  push    rdi
0x1800130c5  push    r12
0x1800130c7  push    r14
0x1800130c9  push    r15
0x1800130cb  lea     rbp, [rsp-510h]
0x1800130d3  sub     rsp, 610h
0x1800130da  mov     rax, cs:__security_cookie
0x1800130e1  xor     rax, rsp
0x1800130e4  mov     [rbp+540h+var_40], rax
0x1800130eb  xor     r12d, r12d
0x1800130ee  lea     rbx, [rdx+0BF4h]
0x1800130f5  movups  xmm0, xmmword ptr [rbx]
0x1800130f8  lea     rax, [rbp+540h+var_5C0]
0x1800130fc  mov     [rbp+540h+var_5BE], r12
0x180013100  mov     [rsp+640h+var_5D0], rax
0x180013105  mov     r14, rdx
0x180013108  lea     rax, [rbp+540h+var_5C0]
0x18001310c  mov     [rbp+540h+var_5B6], r12d
0x180013110  mov     [rsp+640h+var_5C8], rax
0x180013115  lea     rdx, [rsp+640h+Buffer]; struct _GUID
0x18001311a  lea     rax, [rbp+540h+var_5A0]
0x18001311e  mov     [rbp+540h+var_5B2], r12w
0x180013123  mov     [rbp+540h+Block], rax
0x180013127  mov     r15, r8
0x18001312a  lea     rax, [rbp+540h+var_5A0]
0x18001312e  mov     [rbp+540h+var_5C0], r12w
0x180013133  mov     [rbp+540h+var_5A8], rax
0x180013137  mov     rsi, rcx
0x18001313a  mov     [rbp+540h+var_59E], r12
0x18001313e  mov     [rbp+540h+var_596], r12d
0x180013142  mov     [rbp+540h+var_592], r12w
0x180013147  mov     [rbp+540h+var_5A0], r12w
0x18001314c  movdqu  xmmword ptr [rsp+640h+Buffer], xmm0
0x180013152  call    ?_AudioEndpointsAvailable@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@IEAA_NU_GUID@@@Z; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_AudioEndpointsAvailable(_GUID)
0x180013157  mov     rcx, [rsi]
0x18001315a  lea     r8, [r14+0BE4h]
0x180013161  test    al, al
0x180013163  lea     r9, [rsp+640h+var_5D0]
0x180013168  mov     r10, [rcx+0B0h]
0x18001316f  mov     rcx, rsi
0x180013172  mov     rax, r10
0x180013175  jz      short loc_1800131D6
0x180013177  lea     edx, [r12+4]
0x18001317c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013181  mov     edi, eax
0x180013183  test    eax, eax
0x180013185  jns     loc_180013248
0x18001318b  mov     r9d, 0FBh
0x180013191  mov     edx, 1
0x180013196  mov     ecx, edi
0x180013198  call    Log_HREvent_1
0x18001319d  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800131a4  mov     rcx, [rbp+540h+Block]; Block
0x1800131a8  lea     rax, [rbp+540h+var_5A0]
0x1800131ac  cmp     rcx, rax
0x1800131af  jz      short loc_1800131B9
0x1800131b1  mov     rdx, rbx
0x1800131b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800131b9  mov     rcx, [rsp+640h+var_5D0]; Block
0x1800131be  lea     rax, [rbp+540h+var_5C0]
0x1800131c2  cmp     rcx, rax
0x1800131c5  jz      short loc_1800131CF
0x1800131c7  mov     rdx, rbx
0x1800131ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800131cf  mov     eax, edi
0x1800131d1  jmp     loc_18001369D
0x1800131d6  mov     edx, 6
0x1800131db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e0  mov     edi, eax
0x1800131e2  test    eax, eax
0x1800131e4  jns     short loc_1800131EE
0x1800131e6  mov     r9d, 0FFh
0x1800131ec  jmp     short loc_180013191
0x1800131ee  mov     rcx, cs:?g_resourceDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800131f5  lea     r8, [rsp+640h+Buffer]; lpBuffer
0x1800131fa  xor     r9d, r9d; cchBufferMax
0x1800131fd  mov     qword ptr [rsp+640h+Buffer], r12
0x180013202  mov     edx, 2719h; uID
0x180013207  call    cs:__imp_LoadStringW
0x18001320d  test    eax, eax
0x18001320f  jnz     short loc_180013218
0x180013211  call    Log_AssertionEvent_0
0x180013216  int     2Ch; Windows NT - assertion failure
0x180013218  mov     rdx, qword ptr [rsp+640h+Buffer]
0x18001321d  lea     rcx, [rbp+540h+Block]
0x180013221  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013226  test    al, al
0x180013228  jnz     short loc_180013248
0x18001322a  xor     edx, edx
0x18001322c  mov     ecx, 8007000Eh
0x180013231  mov     r9d, 100h
0x180013237  call    Log_HREvent_1
0x18001323c  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013243  jmp     loc_18001357B
0x180013248  lea     rax, [rbp+540h+var_580]
0x18001324c  mov     [rbp+540h+var_57E], r12
0x180013250  mov     [rbp+540h+var_590], rax
0x180013254  lea     r8, [rbp+540h+var_590]
0x180013258  lea     rax, [rbp+540h+var_580]
0x18001325c  mov     [rbp+540h+var_576], r12d
0x180013260  mov     [rbp+540h+var_588], rax
0x180013264  mov     rdx, r14
0x180013267  mov     rax, [rsi]
0x18001326a  mov     rcx, rsi
0x18001326d  mov     [rbp+540h+var_572], r12w
0x180013272  mov     [rbp+540h+var_580], r12w
0x180013277  mov     rax, [rax+60h]
0x18001327b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013280  mov     edi, eax
0x180013282  test    eax, eax
0x180013284  jns     short loc_1800132BD
0x180013286  mov     r9d, 105h
0x18001328c  mov     edx, 1
0x180013291  mov     ecx, edi
0x180013293  call    Log_HREvent_1
0x180013298  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001329f  mov     rcx, [rbp+540h+var_590]; Block
0x1800132a3  lea     rax, [rbp+540h+var_580]
0x1800132a7  cmp     rcx, rax
0x1800132aa  jz      loc_1800131A4
0x1800132b0  mov     rdx, rbx
0x1800132b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800132b8  jmp     loc_1800131A4
0x1800132bd  xor     edx, edx; Val
0x1800132bf  lea     rcx, [rbp+540h+var_510]; void *
0x1800132c3  mov     r8d, 220h; Size
0x1800132c9  call    memset_0
0x1800132ce  lea     rdx, [rbp+540h+var_510]
0x1800132d2  mov     rcx, rbx
0x1800132d5  call    cs:__imp_GetBluetoothHandsFreeLineInfo
0x1800132db  mov     edi, eax
0x1800132dd  test    eax, eax
0x1800132df  jns     short loc_1800132E9
0x1800132e1  mov     r9d, 108h
0x1800132e7  jmp     short loc_18001328C
0x1800132e9  test    [rbp+540h+var_510], 2
0x1800132ed  lea     rax, [rbp+540h+var_560]
0x1800132f1  mov     [rbp+540h+var_570], rax
0x1800132f5  lea     rax, [rbp+540h+var_560]
0x1800132f9  mov     [rbp+540h+var_568], rax
0x1800132fd  mov     [rbp+540h+var_55E], r12
0x180013301  mov     [rbp+540h+var_556], r12d
0x180013305  mov     [rbp+540h+var_552], r12w
0x18001330a  mov     [rbp+540h+var_560], r12w
0x18001330f  jz      short loc_180013317
0x180013311  cmp     [rbp+540h+var_500], r12d
0x180013315  jnz     short loc_180013349
0x180013317  lea     rdx, aMsWinsoundeven; "ms-winsoundevent:notification.looping.c"...
0x18001331e  lea     rcx, [rbp+540h+var_570]
0x180013322  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013327  test    al, al
0x180013329  jnz     short loc_180013349
0x18001332b  xor     edx, edx
0x18001332d  mov     ecx, 8007000Eh
0x180013332  mov     r9d, 10Dh
0x180013338  call    Log_HREvent_1
0x18001333d  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013344  jmp     loc_180013551
0x180013349  lea     rax, [rbp+540h+var_540]
0x18001334d  mov     [rbp+540h+var_53E], r12
0x180013351  mov     [rbp+540h+var_550], rax
0x180013355  lea     rdx, [rbp+540h+var_550]
0x180013359  lea     rax, [rbp+540h+var_540]
0x18001335d  mov     [rbp+540h+var_536], r12d
0x180013361  mov     rcx, rsi
0x180013364  mov     [rbp+540h+var_548], rax
0x180013368  mov     [rbp+540h+var_532], r12w
0x18001336d  mov     [rbp+540h+var_540], r12w
0x180013372  call    ?_SetHfpImagePath@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@IEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_SetHfpImagePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180013377  mov     edi, eax
0x180013379  test    eax, eax
0x18001337b  jns     short loc_1800133C9
0x18001337d  mov     edx, 1
0x180013382  mov     r9d, 111h
0x180013388  mov     ecx, eax
0x18001338a  call    Log_HREvent_1
0x18001338f  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180013396  mov     rcx, [rbp+540h+var_550]; Block
0x18001339a  lea     rax, [rbp+540h+var_540]
0x18001339e  cmp     rcx, rax
0x1800133a1  jz      short loc_1800133AB
0x1800133a3  mov     rdx, rbx
0x1800133a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800133ab  mov     rcx, [rbp+540h+var_570]; Block
0x1800133af  lea     rax, [rbp+540h+var_560]
0x1800133b3  cmp     rcx, rax
0x1800133b6  jz      loc_18001329F
0x1800133bc  mov     rdx, rbx
0x1800133bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800133c4  jmp     loc_18001329F
0x1800133c9  lea     rax, [rbp+540h+var_520]
0x1800133cd  mov     [rbp+540h+var_51E], r12
0x1800133d1  mov     [rbp+540h+var_530], rax
0x1800133d5  lea     rdx, [r14+570h]
0x1800133dc  lea     rax, [rbp+540h+var_520]
0x1800133e0  mov     [rbp+540h+var_516], r12d
0x1800133e4  mov     [rbp+540h+var_528], rax
0x1800133e8  mov     [rbp+540h+var_512], r12w
0x1800133ed  mov     [rbp+540h+var_520], r12w
0x1800133f2  cmp     [rdx], r12w
0x1800133f6  jnz     loc_1800134FD
0x1800133fc  mov     edx, 104h; uSize
0x180013401  lea     rcx, [rbp+540h+var_250]; lpBuffer
0x180013408  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001340e  test    eax, eax
0x180013410  jnz     loc_180013497
0x180013416  call    cs:__imp_GetLastError
0x18001341c  mov     edi, eax
0x18001341e  test    eax, eax
0x180013420  jle     short loc_18001342B
0x180013422  movzx   edi, ax
0x180013425  or      edi, 80070000h
0x18001342b  xor     edx, edx
0x18001342d  mov     r9d, 0EDh
0x180013433  mov     ecx, edi
0x180013435  call    Log_HREvent_1
0x18001343a  test    edi, edi
0x18001343c  js      loc_1800134C6
0x180013442  xor     edx, edx; Val
0x180013444  lea     rcx, [rbp+540h+var_2F0]; void *
0x18001344b  mov     r8d, 0A0h; Size
0x180013451  call    memset_0
0x180013456  mov     r8d, [r14+0BDCh]
0x18001345d  lea     rdx, [r14+0A0h]
0x180013464  and     r8d, 3
0x180013468  mov     [rsp+640h+var_620], 50h ; 'P'
0x180013471  shl     r8d, 0Ah
0x180013475  lea     r9, [rbp+540h+var_2F0]
0x18001347c  mov     rcx, r14
0x18001347f  call    cs:__imp_GetDisplayNameFromCallInformation
0x180013485  mov     edi, eax
0x180013487  test    eax, eax
0x180013489  jns     loc_1800135B0
0x18001348f  mov     r9d, 120h
0x180013495  jmp     short loc_1800134CC
0x180013497  lea     r8, [rbp+540h+var_250]
0x18001349e  lea     rdx, aSSystemresourc_1; "%s\\SystemResources\\Windows.Systemtoas"...
0x1800134a5  lea     rcx, [rbp+540h+var_530]
0x1800134a9  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800134ae  mov     edi, eax
0x1800134b0  test    eax, eax
0x1800134b2  jns     short loc_180013442
0x1800134b4  mov     edx, 1
0x1800134b9  mov     r9d, 0EFh
0x1800134bf  mov     ecx, eax
0x1800134c1  call    Log_HREvent_1
0x1800134c6  mov     r9d, 116h
0x1800134cc  mov     edx, 1
0x1800134d1  mov     ecx, edi
0x1800134d3  call    Log_HREvent_1
0x1800134d8  mov     rcx, [rbp+540h+var_530]; Block
0x1800134dc  lea     rax, [rbp+540h+var_520]
0x1800134e0  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800134e7  cmp     rcx, rax
0x1800134ea  jz      loc_180013396
0x1800134f0  mov     rdx, rbx
0x1800134f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800134f8  jmp     loc_180013396
0x1800134fd  lea     rcx, [rbp+540h+var_530]
0x180013501  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013506  test    al, al
0x180013508  jnz     loc_180013442
0x18001350e  xor     edx, edx
0x180013510  mov     ecx, 8007000Eh
0x180013515  mov     r9d, 11Ah
0x18001351b  call    Log_HREvent_1
0x180013520  mov     rcx, [rbp+540h+var_530]; Block
0x180013524  lea     rax, [rbp+540h+var_520]
0x180013528  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001352f  cmp     rcx, rax
0x180013532  jz      short loc_18001353C
0x180013534  mov     rdx, rbx
0x180013537  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001353c  mov     rcx, [rbp+540h+var_550]; Block
0x180013540  lea     rax, [rbp+540h+var_540]
0x180013544  cmp     rcx, rax
0x180013547  jz      short loc_180013551
0x180013549  mov     rdx, rbx
0x18001354c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013551  mov     rcx, [rbp+540h+var_570]; Block
0x180013555  lea     rax, [rbp+540h+var_560]
0x180013559  cmp     rcx, rax
0x18001355c  jz      short loc_180013566
0x18001355e  mov     rdx, rbx
0x180013561  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013566  mov     rcx, [rbp+540h+var_590]; Block
0x18001356a  lea     rax, [rbp+540h+var_580]
0x18001356e  cmp     rcx, rax
0x180013571  jz      short loc_18001357B
0x180013573  mov     rdx, rbx
0x180013576  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001357b  mov     rcx, [rbp+540h+Block]; Block
0x18001357f  lea     rax, [rbp+540h+var_5A0]
0x180013583  cmp     rcx, rax
0x180013586  jz      short loc_180013590
0x180013588  mov     rdx, rbx
0x18001358b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
  ... truncated ...
```
