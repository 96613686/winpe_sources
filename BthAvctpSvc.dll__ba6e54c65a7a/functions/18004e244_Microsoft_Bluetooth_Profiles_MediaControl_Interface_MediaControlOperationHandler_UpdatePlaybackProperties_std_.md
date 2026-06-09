# Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::UpdatePlaybackProperties(std::optional<Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsMediaState>)

- ea: `0x18004e244`
- end: `0x18004e5fc`
- name: `?UpdatePlaybackProperties@MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@AEAAJV?$optional@W4McsMediaState@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@@std@@@Z`
- size: `952`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004cd40`
- `0x18004dbd0`

## callees

- `0x180001dd0`
- `0x18000751c`
- `0x180012f50`
- `0x180019d20`
- `0x1800235bc`
- `0x18004ca70`
- `0x18004cc94`
- `0x18004d2f8`
- `0x18004d32c`
- `0x18004d390`
- `0x18004d3d8`
- `0x18004e244`
- `0x18004e674`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e5c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::UpdatePlaybackProperties(
        __int64 a1,
        __int64 a2)
{
  unsigned int v2; // ebx
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // edi
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // ecx
  __int64 v10; // r8
  int v11; // eax
  void *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // r12
  unsigned int v17; // edi
  unsigned int v18; // r15d
  __int64 v19; // rax
  int v20; // eax
  void *v21; // rcx
  int *v23; // [rsp+28h] [rbp-79h]
  int v24; // [rsp+28h] [rbp-79h]
  LPVOID pv; // [rsp+58h] [rbp-49h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-41h] BYREF
  unsigned int v27; // [rsp+64h] [rbp-3Dh] BYREF
  unsigned int v28; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v29; // [rsp+6Ch] [rbp-35h] BYREF
  unsigned int v30; // [rsp+70h] [rbp-31h] BYREF
  unsigned int v31; // [rsp+74h] [rbp-2Dh] BYREF
  unsigned int v32; // [rsp+78h] [rbp-29h] BYREF
  _DWORD v33[3]; // [rsp+7Ch] [rbp-25h] BYREF
  __int64 v34; // [rsp+88h] [rbp-19h]
  LPVOID *p_pv; // [rsp+90h] [rbp-11h] BYREF
  int v36[2]; // [rsp+98h] [rbp-9h] BYREF
  char v37; // [rsp+A0h] [rbp-1h]
  _OWORD v38[2]; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]
  char v40; // [rsp+114h] [rbp+73h]

  v40 = BYTE4(a2);
  v2 = a2;
  v31 = 255;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v38[0] = 0;
  v38[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v38[0]) = 0;
  v33[0] = 1;
  v32 = 0;
  pv = 0;
  v4 = *(__int64 **)(a1 + 72);
  v5 = *v4;
  p_pv = &pv;
  *(_QWORD *)v36 = 0;
  v37 = 1;
  v23 = v36;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _DWORD *, unsigned int *))(v5 + 24))(v4, 1, v33, &v32);
  wil::details::out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 533;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\mcp\\bthavmediacontrollerbridge\\lib\\bthavmediacontrollerbridge.cpp",
      (const char *)v7,
      (int)v36);
    v12 = pv;
    pv = 0;
    goto LABEL_15;
  }
  v9 = 0;
  if ( v32 )
  {
    while ( *((_DWORD *)pv + 4 * v9) != 1 )
    {
      if ( ++v9 >= v32 )
        goto LABEL_10;
    }
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*((_QWORD *)pv + 2 * v9 + 1) + 2 * v10) );
    std::wstring::_Assign<unsigned short>(v38);
  }
LABEL_10:
  if ( !v40 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 72) + 56LL))(
            *(_QWORD *)(a1 + 72),
            &v31);
    v6 = v11;
    if ( v11 < 0 )
    {
      v8 = 545;
LABEL_13:
      v7 = (unsigned int)v11;
      goto LABEL_14;
    }
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, unsigned int *))(**(_QWORD **)(a1 + 72) + 64LL))(
          *(_QWORD *)(a1 + 72),
          &v30,
          &v29);
  v6 = v11;
  if ( v11 < 0 )
  {
    v8 = 548;
    goto LABEL_13;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 72) + 120LL))(*(_QWORD *)(a1 + 72), &v28);
  v6 = v11;
  if ( v11 < 0 )
  {
    v8 = 549;
    goto LABEL_13;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**(_QWORD **)(a1 + 72) + 48LL))(
          *(_QWORD *)(a1 + 72),
          3,
          &v27);
  v6 = v11;
  if ( v11 < 0 )
  {
    v8 = 550;
    goto LABEL_13;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**(_QWORD **)(a1 + 72) + 48LL))(
          *(_QWORD *)(a1 + 72),
          2,
          &v26);
  v6 = v11;
  if ( v11 < 0 )
  {
    v8 = 551;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v15 = v31;
    if ( v40 )
      v15 = v2;
    LODWORD(v23) = v30;
    WPP_SF_DdddLLq(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v15, v23, v29, v28, v27, v26, a1);
  }
  v16 = *(__int64 **)(a1 + 80);
  v34 = *v16;
  v33[1] = Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsPlayingOrderFromPlayerSettings(v27, v26);
  v33[2] = Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsPlayingOrderSupportedFromPlaybackCapabilities(v28);
  *(_DWORD *)(a1 + 116) = Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsOpcodesSupportedFromMediaPlaybackCapabilities();
  v17 = v29 / 0xA;
  if ( v29 / 0xA > 0x7FFFFFFF )
    v17 = -1;
  v18 = v30 / 0xA;
  if ( v30 / 0xA > 0x7FFFFFFF )
    v18 = -1;
  if ( !v40 )
    v2 = Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsMediaStateFromPlayStatus(v31);
  v19 = Microsoft::Bluetooth::Foundation::WinRTHelpers::HStringFromWString(v38);
  v24 = v17;
  v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD))(v34 + 80))(v16, v19, v2, v18);
  v6 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\mcp\\bthavmediacontrollerbridge\\lib\\bthavmediacontrollerbridge.cpp",
      (const char *)(unsigned int)v20,
      v24);
    v12 = pv;
    pv = 0;
LABEL_15:
    if ( v12 )
      CoTaskMemFree(v12);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_f26752851b2d3f90d31187047271b4d2_Traceguids, a1);
  }
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  v6 = 0;
LABEL_46:
  std::wstring::_Tidy_deallocate(v38);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004e244  mov     rax, rsp
0x18004e247  mov     [rax+18h], rbx
0x18004e24b  mov     [rax+20h], rsi
0x18004e24f  mov     [rax+10h], rdx
0x18004e253  push    rbp
0x18004e254  push    rdi
0x18004e255  push    r12
0x18004e257  push    r13
0x18004e259  push    r15
0x18004e25b  lea     rbp, [rax-5Fh]
0x18004e25f  sub     rsp, 0D0h
0x18004e266  mov     rax, cs:__security_cookie
0x18004e26d  xor     rax, rsp
0x18004e270  mov     [rbp+57h+var_30], rax
0x18004e274  mov     rbx, rdx
0x18004e277  mov     rsi, rcx
0x18004e27a  mov     [rbp+57h+var_84], 0FFh
0x18004e281  xor     r15d, r15d
0x18004e284  mov     [rbp+57h+var_88], r15d
0x18004e288  mov     [rbp+57h+var_8C], r15d
0x18004e28c  mov     [rbp+57h+var_90], r15d
0x18004e290  mov     [rbp+57h+var_94], r15d
0x18004e294  mov     [rbp+57h+var_98], r15d
0x18004e298  xorps   xmm0, xmm0
0x18004e29b  movups  [rbp+57h+var_50], xmm0
0x18004e29f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004e2a7  movdqu  [rbp+57h+var_40], xmm1
0x18004e2ac  mov     word ptr [rbp+57h+var_50], r15w
0x18004e2b1  lea     r12d, [r15+1]
0x18004e2b5  mov     [rbp+57h+var_7C], r12d
0x18004e2b9  mov     [rbp+57h+var_80], r15d
0x18004e2bd  mov     [rbp+57h+pv], r15
0x18004e2c1  mov     rcx, [rcx+48h]
0x18004e2c5  mov     rax, [rcx]
0x18004e2c8  lea     rdx, [rbp+57h+pv]
0x18004e2cc  mov     [rbp+57h+var_68], rdx
0x18004e2d0  mov     qword ptr [rbp+57h+var_60], r15
0x18004e2d4  mov     [rbp+57h+var_58], r12b
0x18004e2d8  lea     rdx, [rbp+57h+var_60]
0x18004e2dc  mov     [rsp+0F0h+var_D0], rdx; int
0x18004e2e1  lea     r9, [rbp+57h+var_80]
0x18004e2e5  lea     r8, [rbp+57h+var_7C]
0x18004e2e9  mov     edx, r12d
0x18004e2ec  mov     rax, [rax+18h]
0x18004e2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2f5  mov     edi, eax
0x18004e2f7  lea     rcx, [rbp+57h+var_68]
0x18004e2fb  call    ??1?$out_param_t@V?$unique_ptr@UBthAvMediaItemAttribute@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<BthAvMediaItemAttribute,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004e300  test    edi, edi
0x18004e302  jns     short loc_18004E30E
0x18004e304  mov     r9d, edi
0x18004e307  mov     edx, 215h
0x18004e30c  jmp     short loc_18004E377
0x18004e30e  mov     ecx, r15d
0x18004e311  mov     r8d, [rbp+57h+var_80]
0x18004e315  test    r8d, r8d
0x18004e318  jz      short loc_18004E34F
0x18004e31a  mov     rax, [rbp+57h+pv]
0x18004e31e  mov     edx, ecx
0x18004e320  add     rdx, rdx
0x18004e323  cmp     [rax+rdx*8], r12d
0x18004e327  jz      short loc_18004E333
0x18004e329  add     ecx, r12d
0x18004e32c  cmp     ecx, r8d
0x18004e32f  jb      short loc_18004E31E
0x18004e331  jmp     short loc_18004E34F
0x18004e333  mov     rdx, [rax+rdx*8+8]
0x18004e338  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004e33c  inc     r8
0x18004e33f  cmp     [rdx+r8*2], r15w
0x18004e344  jnz     short loc_18004E33C
0x18004e346  lea     rcx, [rbp+57h+var_50]
0x18004e34a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004e34f  cmp     [rbp+57h+arg_C], r15b
0x18004e353  jnz     short loc_18004E3A4
0x18004e355  mov     rcx, [rsi+48h]
0x18004e359  mov     rax, [rcx]
0x18004e35c  lea     rdx, [rbp+57h+var_84]
0x18004e360  mov     rax, [rax+38h]
0x18004e364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e369  mov     edi, eax
0x18004e36b  test    eax, eax
0x18004e36d  jns     short loc_18004E3A4
0x18004e36f  mov     edx, 221h; void *
0x18004e374  mov     r9d, eax; char *
0x18004e377  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18004e37e  mov     rcx, [rbp+5Fh]; this
0x18004e382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e387  nop
0x18004e388  mov     rcx, [rbp+57h+pv]; pv
0x18004e38c  mov     [rbp+57h+pv], r15
0x18004e390  test    rcx, rcx
0x18004e393  jz      loc_18004E5C9
0x18004e399  call    cs:__imp_CoTaskMemFree
0x18004e39f  jmp     loc_18004E5C9
0x18004e3a4  mov     rcx, [rsi+48h]
0x18004e3a8  mov     rax, [rcx]
0x18004e3ab  lea     r8, [rbp+57h+var_8C]
0x18004e3af  lea     rdx, [rbp+57h+var_88]
0x18004e3b3  mov     rax, [rax+40h]
0x18004e3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3bc  mov     edi, eax
0x18004e3be  test    eax, eax
0x18004e3c0  jns     short loc_18004E3C9
0x18004e3c2  mov     edx, 224h
0x18004e3c7  jmp     short loc_18004E374
0x18004e3c9  mov     rcx, [rsi+48h]
0x18004e3cd  mov     rax, [rcx]
0x18004e3d0  lea     rdx, [rbp+57h+var_90]
0x18004e3d4  mov     rax, [rax+78h]
0x18004e3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3dd  mov     edi, eax
0x18004e3df  test    eax, eax
0x18004e3e1  jns     short loc_18004E3EA
0x18004e3e3  mov     edx, 225h
0x18004e3e8  jmp     short loc_18004E374
0x18004e3ea  mov     rcx, [rsi+48h]
0x18004e3ee  mov     rax, [rcx]
0x18004e3f1  lea     r8, [rbp+57h+var_94]
0x18004e3f5  mov     edx, 3
0x18004e3fa  mov     rax, [rax+30h]
0x18004e3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e403  mov     edi, eax
0x18004e405  test    eax, eax
0x18004e407  jns     short loc_18004E413
0x18004e409  mov     edx, 226h
0x18004e40e  jmp     loc_18004E374
0x18004e413  mov     rcx, [rsi+48h]
0x18004e417  mov     rax, [rcx]
0x18004e41a  lea     r8, [rbp+57h+var_98]
0x18004e41e  mov     edx, 2
0x18004e423  mov     rax, [rax+30h]
0x18004e427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e42c  mov     edi, eax
0x18004e42e  test    eax, eax
0x18004e430  jns     short loc_18004E43C
0x18004e432  mov     edx, 227h
0x18004e437  jmp     loc_18004E374
0x18004e43c  lea     rax, WPP_GLOBAL_Control
0x18004e443  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e44a  cmp     rcx, rax
0x18004e44d  jz      short loc_18004E498
0x18004e44f  test    [rcx+1Ch], r12b
0x18004e453  jz      short loc_18004E498
0x18004e455  cmp     byte ptr [rcx+19h], 4
0x18004e459  jb      short loc_18004E498
0x18004e45b  mov     r9d, [rbp+57h+var_84]
0x18004e45f  cmp     [rbp+57h+arg_C], r15b
0x18004e463  cmovnz  r9d, ebx
0x18004e467  mov     [rsp+0F0h+var_A8], rsi
0x18004e46c  mov     eax, [rbp+57h+var_98]
0x18004e46f  mov     dword ptr [rsp+0F0h+var_B0], eax
0x18004e473  mov     eax, [rbp+57h+var_94]
0x18004e476  mov     [rsp+0F0h+var_B8], eax
0x18004e47a  mov     eax, [rbp+57h+var_90]
0x18004e47d  mov     [rsp+0F0h+var_C0], eax
0x18004e481  mov     eax, [rbp+57h+var_8C]
0x18004e484  mov     [rsp+0F0h+var_C8], eax
0x18004e488  mov     eax, [rbp+57h+var_88]
0x18004e48b  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18004e48f  mov     rcx, [rcx+10h]
0x18004e493  call    WPP_SF_DdddLLq
0x18004e498  mov     r12, [rsi+50h]
0x18004e49c  mov     rax, [r12]
0x18004e4a0  mov     [rbp+57h+var_70], rax
0x18004e4a4  mov     edx, [rbp+57h+var_98]
0x18004e4a7  mov     ecx, [rbp+57h+var_94]
0x18004e4aa  call    ?McsPlayingOrderFromPlayerSettings@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YA?AW4McsPlayingOrder@12345@W4BthAvMediaShuffleMode@@W4BthAvMediaRepeatMode@@@Z; Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsPlayingOrderFromPlayerSettings(BthAvMediaShuffleMode,BthAvMediaRepeatMode)
0x18004e4af  mov     [rbp+57h+var_78], eax
0x18004e4b2  mov     ecx, [rbp+57h+var_90]
0x18004e4b5  call    ?McsPlayingOrderSupportedFromPlaybackCapabilities@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YA?AW4McsPlayingOrderSupported@12345@W4MediaPlaybackCapabilities@@@Z; Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsPlayingOrderSupportedFromPlaybackCapabilities(MediaPlaybackCapabilities)
0x18004e4ba  mov     [rbp+57h+var_74], eax
0x18004e4bd  call    ?McsOpcodesSupportedFromMediaPlaybackCapabilities@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YA?AW4McsOpcodeSupported@12345@W4MediaPlaybackCapabilities@@@Z; Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsOpcodesSupportedFromMediaPlaybackCapabilities(MediaPlaybackCapabilities)
0x18004e4c2  mov     r13d, eax
0x18004e4c5  mov     [rsi+74h], eax
0x18004e4c8  mov     r8d, 0CCCCCCCDh
0x18004e4ce  mov     eax, r8d
0x18004e4d1  mul     [rbp+57h+var_8C]
0x18004e4d4  mov     edi, edx
0x18004e4d6  shr     edi, 3
0x18004e4d9  mov     ecx, 7FFFFFFFh
0x18004e4de  cmp     edi, ecx
0x18004e4e0  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18004e4e7  cmova   edi, r9d
0x18004e4eb  mov     eax, r8d
0x18004e4ee  mul     [rbp+57h+var_88]
0x18004e4f1  mov     r15d, edx
0x18004e4f4  shr     r15d, 3
0x18004e4f8  cmp     r15d, ecx
0x18004e4fb  cmova   r15d, r9d
0x18004e4ff  cmp     [rbp+57h+arg_C], 0
0x18004e503  jnz     short loc_18004E50F
0x18004e505  mov     ecx, [rbp+57h+var_84]
0x18004e508  call    ?McsMediaStateFromPlayStatus@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@YA?AW4McsMediaState@12345@W4BthAvMediaPlayStatus@@@Z; Microsoft::Bluetooth::Profiles::MediaControl::Interface::McsMediaStateFromPlayStatus(BthAvMediaPlayStatus)
0x18004e50d  mov     ebx, eax
0x18004e50f  lea     rcx, [rbp+57h+var_50]
0x18004e513  call    ?HStringFromWString@WinRTHelpers@Foundation@Bluetooth@Microsoft@@SAPEAUHSTRING__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Bluetooth::Foundation::WinRTHelpers::HStringFromWString(std::wstring const &)
0x18004e518  mov     ecx, [rbp+57h+var_78]
0x18004e51b  mov     [rsp+0F0h+var_B8], ecx
0x18004e51f  mov     ecx, [rbp+57h+var_74]
0x18004e522  mov     [rsp+0F0h+var_C0], ecx
0x18004e526  mov     [rsp+0F0h+var_C8], r13d
0x18004e52b  mov     dword ptr [rsp+0F0h+var_D0], edi; int
0x18004e52f  mov     r9d, r15d
0x18004e532  mov     r8d, ebx
0x18004e535  mov     rdx, rax
0x18004e538  mov     rcx, r12
0x18004e53b  mov     rax, [rbp+57h+var_70]
0x18004e53f  mov     rax, [rax+50h]
0x18004e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e548  mov     edi, eax
0x18004e54a  test    eax, eax
0x18004e54c  jns     short loc_18004E578
0x18004e54e  mov     rcx, [rbp+5Fh]; this
0x18004e552  mov     r9d, eax; char *
0x18004e555  lea     r8, aOnecoreDrivers_9; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18004e55c  mov     edx, 232h; void *
0x18004e561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e566  nop
0x18004e567  mov     rcx, [rbp+57h+pv]
0x18004e56b  mov     [rbp+57h+pv], 0
0x18004e573  jmp     loc_18004E390
0x18004e578  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e57f  lea     rax, WPP_GLOBAL_Control
0x18004e586  cmp     rcx, rax
0x18004e589  jz      short loc_18004E5B0
0x18004e58b  test    byte ptr [rcx+1Ch], 1
0x18004e58f  jz      short loc_18004E5B0
0x18004e591  cmp     byte ptr [rcx+19h], 5
0x18004e595  jb      short loc_18004E5B0
0x18004e597  mov     edx, 25h ; '%'
0x18004e59c  mov     r9, rsi
0x18004e59f  lea     r8, WPP_f26752851b2d3f90d31187047271b4d2_Traceguids
0x18004e5a6  mov     rcx, [rcx+10h]
0x18004e5aa  call    WPP_SF_q
0x18004e5af  nop
0x18004e5b0  mov     rcx, [rbp+57h+pv]; pv
0x18004e5b4  mov     [rbp+57h+pv], 0
0x18004e5bc  test    rcx, rcx
0x18004e5bf  jz      short loc_18004E5C7
0x18004e5c1  call    cs:__imp_CoTaskMemFree
0x18004e5c7  xor     edi, edi
0x18004e5c9  lea     rcx, [rbp+57h+var_50]
0x18004e5cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e5d2  mov     eax, edi
0x18004e5d4  mov     rcx, [rbp+57h+var_30]
0x18004e5d8  xor     rcx, rsp; StackCookie
0x18004e5db  call    __security_check_cookie
0x18004e5e0  lea     r11, [rsp+0F0h+var_20]
0x18004e5e8  mov     rbx, [r11+40h]
0x18004e5ec  mov     rsi, [r11+48h]
0x18004e5f0  mov     rsp, r11
0x18004e5f3  pop     r15
0x18004e5f5  pop     r13
0x18004e5f7  pop     r12
0x18004e5f9  pop     rdi
0x18004e5fa  pop     rbp
0x18004e5fb  retn
```
