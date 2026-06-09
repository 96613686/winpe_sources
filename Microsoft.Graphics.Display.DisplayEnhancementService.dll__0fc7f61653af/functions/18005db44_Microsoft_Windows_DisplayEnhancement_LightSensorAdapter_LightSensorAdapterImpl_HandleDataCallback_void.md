# Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::HandleDataCallback(void)

- ea: `0x18005db44`
- end: `0x18005e108`
- name: `?HandleDataCallback@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@QEAA?AW4Event@?$SensorAdapterStateMachine@VLightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@@GeneratedStateMachines@2345@XZ`
- size: `1476`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e110`

## callees

- `0x180005860`
- `0x180008e3c`
- `0x180009a84`
- `0x180009aa4`
- `0x18000fa0c`
- `0x1800121d0`
- `0x18001f19c`
- `0x18005c474`
- `0x18005db44`
- `0x18005e8f0`
- `0x18005fa04`
- `0x18006016c`

## import_xrefs

- `SensorsNativeApi!SensorSetThresholds` at `0x18005dc0a`
- `SensorsNativeApi!SensorSetThresholds` at `0x18005dc0a`
- `SensorsNativeApi!SensorSetAlsWithColorThresholds` at `0x18005dbe6`
- `SensorsNativeApi!SensorSetAlsWithColorThresholds` at `0x18005dbe6`

## string_xrefs

- `0x18005e0e1`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`
- `0x18005e0f5`: `onecoreuap\drivers\mobilepc\displayenhancement\service\lightsensoradapter\lib\lightsensoradapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::HandleDataCallback(
        __int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // rax
  char v5; // si
  char v6; // bl
  __m128i si128; // xmm6
  __int64 v8; // rax
  char v9; // bl
  __int64 v10; // rax
  char v11; // bl
  __int64 *v12; // r10
  __int64 *v13; // r9
  __int64 *v14; // rax
  __int128 v15; // xmm6
  __int32 v16; // esi
  __int8 v17; // bl
  __int16 v18; // r14
  __int8 v19; // r15
  const char *v20; // r9
  __int64 v22; // [rsp+20h] [rbp-188h]
  __int64 v23; // [rsp+28h] [rbp-180h]
  int v24; // [rsp+30h] [rbp-178h]
  __int64 v25; // [rsp+38h] [rbp-170h]
  int v26; // [rsp+40h] [rbp-168h]
  char v27[8]; // [rsp+78h] [rbp-130h] BYREF
  __int64 v28[2]; // [rsp+80h] [rbp-128h] BYREF
  __m128i v29; // [rsp+90h] [rbp-118h]
  __int64 v30[2]; // [rsp+A0h] [rbp-108h] BYREF
  __m128i v31; // [rsp+B0h] [rbp-F8h]
  char Buffer[8]; // [rsp+C0h] [rbp-E8h] BYREF
  __m128i v33; // [rsp+D0h] [rbp-D8h]
  __int64 v34[2]; // [rsp+E0h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+F0h] [rbp-B8h]
  char v36[8]; // [rsp+100h] [rbp-A8h] BYREF
  __m128i v37; // [rsp+110h] [rbp-98h]
  void *v38; // [rsp+120h] [rbp-88h] BYREF
  __m128i v39; // [rsp+130h] [rbp-78h]
  char v40[8]; // [rsp+140h] [rbp-68h] BYREF
  __m128i v41; // [rsp+150h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  try
  {
    if ( *(_BYTE *)(a1 + 133) )
    {
      Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
        (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v27,
        (struct wil::srwlock *)(a1 + 96));
      *(_BYTE *)(a1 + 133) = 0;
      v23 = (a1 + 128) & -(__int64)(*(_BYTE *)(a1 + 132) != 0);
      v22 = (a1 + 120) & -(__int64)(*(_BYTE *)(a1 + 124) != 0);
      v2 = SensorSetAlsWithColorThresholds(*(_QWORD *)(a1 + 200), *(_QWORD *)(a1 + 136), a1 + 108, 0);
      if ( v2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x235,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
          (const char *)v2,
          v22);
      v3 = SensorSetThresholds(*(_QWORD *)(a1 + 200), *(_QWORD *)(a1 + 136));
      if ( v3 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x23B,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
          (const char *)v3,
          v22);
      if ( *(_BYTE *)(a1 + 116) )
      {
        v4 = std::to_string(Buffer);
        v5 = 1;
        v6 = 1;
      }
      else
      {
        v4 = std::string::string(v36, "null");
        v6 = 2;
        v5 = 1;
      }
      *(_OWORD *)v34 = 0;
      v35 = 0;
      *(_OWORD *)v34 = *(_OWORD *)v4;
      v35 = *(_OWORD *)(v4 + 16);
      *(_QWORD *)(v4 + 16) = 0;
      *(_QWORD *)(v4 + 24) = 15;
      *(_BYTE *)v4 = 0;
      if ( (v6 & 2) != 0 )
      {
        v6 &= ~2u;
        if ( v37.m128i_i64[1] > 0xFuLL )
          std::_Deallocate<16>(*(void **)v36, (struct std::nothrow_t *)(v37.m128i_i64[1] + 1));
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v37 = si128;
        v36[0] = 0;
      }
      else
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      if ( (v6 & 1) != 0 )
      {
        v6 &= ~1u;
        if ( v33.m128i_i64[1] > 0xFuLL )
          std::_Deallocate<16>(*(void **)Buffer, (struct std::nothrow_t *)(v33.m128i_i64[1] + 1));
        v33 = si128;
        Buffer[0] = 0;
      }
      if ( *(_BYTE *)(a1 + 124) )
      {
        v8 = std::to_string(v40);
        v9 = v6 | 4;
      }
      else
      {
        v8 = std::string::string(&v38, "null");
        v9 = v6 | 8;
      }
      *(_OWORD *)v30 = 0;
      v31 = 0;
      *(_OWORD *)v30 = *(_OWORD *)v8;
      v31 = *(__m128i *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 15;
      *(_BYTE *)v8 = 0;
      if ( (v9 & 8) != 0 )
      {
        v9 &= ~8u;
        if ( v39.m128i_i64[1] > 0xFuLL )
          std::_Deallocate<16>(v38, (struct std::nothrow_t *)(v39.m128i_i64[1] + 1));
        v39 = si128;
        LOBYTE(v38) = 0;
      }
      if ( (v9 & 4) != 0 )
      {
        v9 &= ~4u;
        if ( v41.m128i_i64[1] > 0xFuLL )
          std::_Deallocate<16>(*(void **)v40, (struct std::nothrow_t *)(v41.m128i_i64[1] + 1));
        v41 = si128;
        v40[0] = 0;
      }
      if ( *(_BYTE *)(a1 + 132) )
      {
        v10 = std::to_string(v36);
        v11 = v9 | 0x10;
      }
      else
      {
        v10 = std::string::string(Buffer, "null");
        v11 = v9 | 0x20;
      }
      *(_OWORD *)v28 = 0;
      v29 = 0;
      *(_OWORD *)v28 = *(_OWORD *)v10;
      v29 = *(__m128i *)(v10 + 16);
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 15;
      *(_BYTE *)v10 = 0;
      if ( (v11 & 0x20) != 0 )
      {
        v11 &= ~0x20u;
        if ( v33.m128i_i64[1] > 0xFuLL )
          std::_Deallocate<16>(*(void **)Buffer, (struct std::nothrow_t *)(v33.m128i_i64[1] + 1));
        v33 = si128;
        Buffer[0] = 0;
      }
      if ( (v11 & 0x10) != 0 && v37.m128i_i64[1] > 0xFuLL )
        std::_Deallocate<16>(*(void **)v36, (struct std::nothrow_t *)(v37.m128i_i64[1] + 1));
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = v28;
        if ( v29.m128i_i64[1] > 0xFuLL )
          v12 = (__int64 *)v28[0];
        v13 = v30;
        if ( v31.m128i_i64[1] > 0xFuLL )
          v13 = (__int64 *)v30[0];
        v14 = v34;
        if ( *((_QWORD *)&v35 + 1) > 0xFu )
          v14 = (__int64 *)v34[0];
        WPP_RECORDER_AND_TRACE_SF_sqgsss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v23,
          v24,
          v25,
          v26,
          a1,
          *(_OWORD *)&_mm_cvtps_pd((__m128)*(unsigned int *)(a1 + 108)),
          (__int64)v14,
          (__int64)v13,
          (__int64)v12);
      }
      if ( v29.m128i_i64[1] > 0xFuLL )
        std::_Deallocate<16>((void *)v28[0], (struct std::nothrow_t *)(v29.m128i_i64[1] + 1));
      v29 = si128;
      LOBYTE(v28[0]) = 0;
      if ( v31.m128i_i64[1] > 0xFuLL )
        std::_Deallocate<16>((void *)v30[0], (struct std::nothrow_t *)(v31.m128i_i64[1] + 1));
      v31 = si128;
      LOBYTE(v30[0]) = 0;
      if ( *((_QWORD *)&v35 + 1) > 0xFu )
        std::_Deallocate<16>((void *)v34[0], (struct std::nothrow_t *)(*((_QWORD *)&v35 + 1) + 1LL));
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v27);
    }
    Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(
      (Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard *)v27,
      (struct wil::srwlock *)(a1 + 168));
    v15 = *(_OWORD *)(a1 + 176);
    v16 = *(_DWORD *)(a1 + 192);
    v17 = *(_BYTE *)(a1 + 196);
    v18 = *(_WORD *)(a1 + 197);
    v19 = *(_BYTE *)(a1 + 199);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v27);
    if ( *(_BYTE *)(a1 + 232) || v17 )
    {
      *(_OWORD *)v28 = v15;
      v29.m128i_i32[0] = v16;
      v29.m128i_i8[4] = v17;
      *(__int16 *)((char *)&v29.m128i_i16[2] + 1) = v18;
      v29.m128i_i8[7] = v19;
      Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::NotifyClients(a1, v28);
      *(_BYTE *)(a1 + 232) = v17;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\lightsensoradapter\\lib\\lightsensoradapter.cpp",
      v20);
  }
  return 3;
}

```

## disassembly

```asm
0x18005db44  mov     rax, rsp
0x18005db47  mov     [rax+10h], rbx
0x18005db4b  mov     [rax+18h], rsi
0x18005db4f  push    rdi
0x18005db50  push    r12
0x18005db52  push    r13
0x18005db54  push    r14
0x18005db56  push    r15
0x18005db58  sub     rsp, 180h
0x18005db5f  movaps  xmmword ptr [rax-38h], xmm6
0x18005db63  mov     rax, cs:__security_cookie
0x18005db6a  xor     rax, rsp
0x18005db6d  mov     [rsp+1A8h+var_48], rax
0x18005db75  mov     rdi, rcx
0x18005db78  xor     r13d, r13d
0x18005db7b  mov     [rsp+1A8h+var_138], r13d
0x18005db80  cmp     [rcx+85h], r13b
0x18005db87  jz      loc_18005E01E
0x18005db8d  lea     rdx, [rcx+60h]; struct wil::srwlock *
0x18005db91  lea     rcx, [rsp+1A8h+var_130]; this
0x18005db96  call    ??0ExclusiveSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(wil::srwlock &)
0x18005db9b  nop
0x18005db9c  mov     [rdi+85h], r13b
0x18005dba3  lea     r15, [rdi+80h]
0x18005dbaa  lea     r14, [rdi+78h]
0x18005dbae  mov     al, [rdi+84h]
0x18005dbb4  neg     al
0x18005dbb6  sbb     rdx, rdx
0x18005dbb9  and     rdx, r15
0x18005dbbc  mov     al, [rdi+7Ch]
0x18005dbbf  neg     al
0x18005dbc1  sbb     rcx, rcx
0x18005dbc4  and     rcx, r14
0x18005dbc7  mov     qword ptr [rsp+1A8h+var_180], rdx; int
0x18005dbcc  mov     qword ptr [rsp+1A8h+var_188], rcx; unsigned int
0x18005dbd1  xor     r9d, r9d
0x18005dbd4  lea     r8, [rdi+6Ch]
0x18005dbd8  mov     rdx, [rdi+88h]
0x18005dbdf  mov     rcx, [rdi+0C8h]
0x18005dbe6  call    cs:__imp_SensorSetAlsWithColorThresholds
0x18005dbec  mov     rcx, [rsp+1A8h]; this
0x18005dbf4  test    eax, eax
0x18005dbf6  jnz     loc_18005E0DE
0x18005dbfc  mov     rdx, [rdi+88h]
0x18005dc03  mov     rcx, [rdi+0C8h]
0x18005dc0a  call    cs:__imp_SensorSetThresholds
0x18005dc10  mov     rcx, [rsp+1A8h]; this
0x18005dc18  test    eax, eax
0x18005dc1a  jnz     loc_18005E0F2
0x18005dc20  cmp     [rdi+74h], r13b
0x18005dc24  jz      short loc_18005DC42
0x18005dc26  movss   xmm1, dword ptr [rdi+70h]
0x18005dc2b  lea     rcx, [rsp+1A8h+Buffer]; Buffer
0x18005dc33  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@M@Z; std::to_string(float)
0x18005dc38  nop
0x18005dc39  mov     esi, 1
0x18005dc3e  mov     ebx, esi
0x18005dc40  jmp     short loc_18005DC5E
0x18005dc42  lea     rdx, aNull_1; "null"
0x18005dc49  lea     rcx, [rsp+1A8h+var_A8]
0x18005dc51  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005dc56  mov     ebx, 2
0x18005dc5b  lea     esi, [rbx-1]
0x18005dc5e  mov     [rsp+1A8h+var_138], ebx
0x18005dc62  xorps   xmm0, xmm0
0x18005dc65  movups  xmmword ptr [rsp+1A8h+var_C8], xmm0
0x18005dc6d  xorps   xmm1, xmm1
0x18005dc70  movdqu  [rsp+1A8h+var_B8], xmm1
0x18005dc79  movups  xmm0, xmmword ptr [rax]
0x18005dc7c  movups  xmmword ptr [rsp+1A8h+var_C8], xmm0
0x18005dc84  movups  xmm1, xmmword ptr [rax+10h]
0x18005dc88  movups  [rsp+1A8h+var_B8], xmm1
0x18005dc90  mov     [rax+10h], r13
0x18005dc94  mov     qword ptr [rax+18h], 0Fh
0x18005dc9c  mov     [rax], r13b
0x18005dc9f  test    bl, 2
0x18005dca2  jz      short loc_18005DCE4
0x18005dca4  and     ebx, 0FFFFFFFDh
0x18005dca7  mov     [rsp+1A8h+var_138], ebx
0x18005dcab  mov     rdx, [rsp+1A8h+var_90]
0x18005dcb3  cmp     rdx, 0Fh
0x18005dcb7  jbe     short loc_18005DCC9
0x18005dcb9  inc     rdx
0x18005dcbc  mov     rcx, qword ptr [rsp+1A8h+var_A8]
0x18005dcc4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dcc9  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18005dcd1  movdqu  xmmword ptr [rsp+110h], xmm6
0x18005dcda  mov     [rsp+1A8h+var_A8], r13b
0x18005dce2  jmp     short loc_18005DCEC
0x18005dce4  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18005dcec  test    sil, bl
0x18005dcef  jz      short loc_18005DD27
0x18005dcf1  and     ebx, 0FFFFFFFEh
0x18005dcf4  mov     [rsp+1A8h+var_138], ebx
0x18005dcf8  mov     rdx, [rsp+1A8h+var_D0]
0x18005dd00  cmp     rdx, 0Fh
0x18005dd04  jbe     short loc_18005DD16
0x18005dd06  inc     rdx
0x18005dd09  mov     rcx, qword ptr [rsp+1A8h+Buffer]
0x18005dd11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dd16  movdqu  xmmword ptr [rsp+0D0h], xmm6
0x18005dd1f  mov     [rsp+1A8h+Buffer], r13b
0x18005dd27  cmp     [rdi+7Ch], r13b
0x18005dd2b  jz      short loc_18005DD45
0x18005dd2d  movss   xmm1, dword ptr [r14]
0x18005dd32  lea     rcx, [rsp+1A8h+var_68]; Buffer
0x18005dd3a  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@M@Z; std::to_string(float)
0x18005dd3f  nop
0x18005dd40  or      ebx, 4
0x18005dd43  jmp     short loc_18005DD5C
0x18005dd45  lea     rdx, aNull_1; "null"
0x18005dd4c  lea     rcx, [rsp+1A8h+var_88]
0x18005dd54  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005dd59  or      ebx, 8
0x18005dd5c  mov     [rsp+1A8h+var_138], ebx
0x18005dd60  xorps   xmm0, xmm0
0x18005dd63  movups  xmmword ptr [rsp+1A8h+var_108], xmm0
0x18005dd6b  xorps   xmm1, xmm1
0x18005dd6e  movdqu  [rsp+1A8h+var_F8], xmm1
0x18005dd77  movups  xmm0, xmmword ptr [rax]
0x18005dd7a  movups  xmmword ptr [rsp+1A8h+var_108], xmm0
0x18005dd82  movups  xmm1, xmmword ptr [rax+10h]
0x18005dd86  movups  [rsp+1A8h+var_F8], xmm1
0x18005dd8e  mov     [rax+10h], r13
0x18005dd92  mov     r14d, 0Fh
0x18005dd98  mov     [rax+18h], r14
0x18005dd9c  mov     [rax], r13b
0x18005dd9f  test    bl, 8
0x18005dda2  jz      short loc_18005DDD9
0x18005dda4  and     ebx, 0FFFFFFF7h
0x18005dda7  mov     [rsp+1A8h+var_138], ebx
0x18005ddab  mov     rdx, [rsp+1A8h+var_70]
0x18005ddb3  cmp     rdx, r14
0x18005ddb6  jbe     short loc_18005DDC8
0x18005ddb8  inc     rdx
0x18005ddbb  mov     rcx, [rsp+1A8h+var_88]
0x18005ddc3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005ddc8  movdqu  xmmword ptr [rsp+130h], xmm6
0x18005ddd1  mov     byte ptr [rsp+1A8h+var_88], r13b
0x18005ddd9  test    bl, 4
0x18005dddc  jz      short loc_18005DE13
0x18005ddde  and     ebx, 0FFFFFFFBh
0x18005dde1  mov     [rsp+1A8h+var_138], ebx
0x18005dde5  mov     rdx, [rsp+1A8h+var_50]
0x18005dded  cmp     rdx, r14
0x18005ddf0  jbe     short loc_18005DE02
0x18005ddf2  inc     rdx
0x18005ddf5  mov     rcx, qword ptr [rsp+1A8h+var_68]
0x18005ddfd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005de02  movdqu  xmmword ptr [rsp+150h], xmm6
0x18005de0b  mov     [rsp+1A8h+var_68], r13b
0x18005de13  cmp     [rdi+84h], r13b
0x18005de1a  jz      short loc_18005DE34
0x18005de1c  movss   xmm1, dword ptr [r15]
0x18005de21  lea     rcx, [rsp+1A8h+var_A8]; Buffer
0x18005de29  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@M@Z; std::to_string(float)
0x18005de2e  nop
0x18005de2f  or      ebx, 10h
0x18005de32  jmp     short loc_18005DE4B
0x18005de34  lea     rdx, aNull_1; "null"
0x18005de3b  lea     rcx, [rsp+1A8h+Buffer]
0x18005de43  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18005de48  or      ebx, 20h
0x18005de4b  xorps   xmm0, xmm0
0x18005de4e  movups  xmmword ptr [rsp+1A8h+var_128], xmm0
0x18005de56  xorps   xmm1, xmm1
0x18005de59  movdqu  [rsp+1A8h+var_118], xmm1
0x18005de62  movups  xmm0, xmmword ptr [rax]
0x18005de65  movups  xmmword ptr [rsp+1A8h+var_128], xmm0
0x18005de6d  movups  xmm1, xmmword ptr [rax+10h]
0x18005de71  movups  [rsp+1A8h+var_118], xmm1
0x18005de79  mov     [rax+10h], r13
0x18005de7d  mov     [rax+18h], r14
0x18005de81  mov     [rax], r13b
0x18005de84  test    bl, 20h
0x18005de87  jz      short loc_18005DEBA
0x18005de89  and     ebx, 0FFFFFFDFh
0x18005de8c  mov     rdx, [rsp+1A8h+var_D0]
0x18005de94  cmp     rdx, r14
0x18005de97  jbe     short loc_18005DEA9
0x18005de99  inc     rdx
0x18005de9c  mov     rcx, qword ptr [rsp+1A8h+Buffer]
0x18005dea4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dea9  movdqu  xmmword ptr [rsp+0D0h], xmm6
0x18005deb2  mov     [rsp+1A8h+Buffer], r13b
0x18005deba  test    bl, 10h
0x18005debd  jz      short loc_18005DEDC
0x18005debf  mov     rdx, [rsp+1A8h+var_90]
0x18005dec7  cmp     rdx, r14
0x18005deca  jbe     short loc_18005DEDC
0x18005decc  inc     rdx
0x18005decf  mov     rcx, qword ptr [rsp+1A8h+var_A8]
0x18005ded7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dedc  lea     rax, WPP_GLOBAL_Control
0x18005dee3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005deea  cmp     rcx, rax
0x18005deed  jz      short loc_18005DEFE
0x18005deef  test    dword ptr [rcx+1Ch], 400h
0x18005def6  jz      short loc_18005DEFE
0x18005def8  cmp     byte ptr [rcx+19h], 4
0x18005defc  jnb     short loc_18005DF01
0x18005defe  mov     sil, r13b
0x18005df01  lea     rax, WPP_RECORDER_INITIALIZED
0x18005df08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005df0f  setnz   r8b
0x18005df13  test    sil, sil
0x18005df16  jnz     short loc_18005DF1D
0x18005df18  test    r8b, r8b
0x18005df1b  jz      short loc_18005DF9A
0x18005df1d  lea     r10, [rsp+1A8h+var_128]
0x18005df25  cmp     qword ptr [rsp+1A8h+var_118+8], r14
0x18005df2d  cmova   r10, [rsp+1A8h+var_128]
0x18005df36  lea     r9, [rsp+1A8h+var_108]
0x18005df3e  cmp     qword ptr [rsp+1A8h+var_F8+8], r14
0x18005df46  cmova   r9, [rsp+1A8h+var_108]
0x18005df4f  lea     rax, [rsp+1A8h+var_C8]
0x18005df57  cmp     qword ptr [rsp+1A8h+var_B8+8], r14
0x18005df5f  cmova   rax, [rsp+1A8h+var_C8]
0x18005df68  movss   xmm0, dword ptr [rdi+6Ch]
0x18005df6d  cvtps2pd xmm0, xmm0
0x18005df70  mov     [rsp+1A8h+var_140], r10; __int64
0x18005df75  mov     [rsp+1A8h+var_148], r9; __int64
0x18005df7a  mov     [rsp+1A8h+var_150], rax; __int64
0x18005df7f  movsd   qword ptr [rsp+1A8h+var_158], xmm0; char
0x18005df85  mov     qword ptr [rsp+1A8h+var_160], rdi; char
0x18005df8a  mov     r9, [rcx+28h]
0x18005df8e  mov     dl, sil
0x18005df91  mov     rcx, [rcx+10h]; LoggerHandle
0x18005df95  call    WPP_RECORDER_AND_TRACE_SF_sqgsss
0x18005df9a  mov     rdx, qword ptr [rsp+1A8h+var_118+8]
0x18005dfa2  cmp     rdx, r14
0x18005dfa5  jbe     short loc_18005DFB7
0x18005dfa7  inc     rdx
0x18005dfaa  mov     rcx, [rsp+1A8h+var_128]
0x18005dfb2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dfb7  movdqu  [rsp+1A8h+var_118], xmm6
0x18005dfc0  mov     byte ptr [rsp+1A8h+var_128], r13b
0x18005dfc8  mov     rdx, qword ptr [rsp+1A8h+var_F8+8]
0x18005dfd0  cmp     rdx, r14
0x18005dfd3  jbe     short loc_18005DFE5
0x18005dfd5  inc     rdx
0x18005dfd8  mov     rcx, [rsp+1A8h+var_108]
0x18005dfe0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005dfe5  movdqu  [rsp+1A8h+var_F8], xmm6
0x18005dfee  mov     byte ptr [rsp+1A8h+var_108], r13b
0x18005dff6  mov     rdx, qword ptr [rsp+1A8h+var_B8+8]
0x18005dffe  cmp     rdx, r14
0x18005e001  jbe     short loc_18005E014
0x18005e003  inc     rdx
0x18005e006  mov     rcx, [rsp+1A8h+var_C8]
0x18005e00e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005e013  nop
0x18005e014  lea     rcx, [rsp+1A8h+var_130]
0x18005e019  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005e01e  lea     rdx, [rdi+0A8h]; struct wil::srwlock *
0x18005e025  lea     rcx, [rsp+1A8h+var_130]; this
0x18005e02a  call    ??0SharedSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(wil::srwlock &)
0x18005e02f  movups  xmm6, xmmword ptr [rdi+0B0h]
0x18005e036  mov     esi, [rdi+0C0h]
0x18005e03c  mov     bl, [rdi+0C4h]
0x18005e042  movzx   r14d, word ptr [rdi+0C5h]
0x18005e04a  mov     r15b, [rdi+0C7h]
0x18005e051  lea     rcx, [rsp+1A8h+var_130]
0x18005e056  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005e05b  mov     al, [rdi+0E8h]
0x18005e061  nop
0x18005e062  test    al, al
0x18005e064  jnz     short loc_18005E06A
0x18005e066  test    bl, bl
0x18005e068  jz      short loc_18005E0A7
0x18005e06a  movaps  xmmword ptr [rsp+1A8h+var_128], xmm6
0x18005e072  mov     dword ptr [rsp+1A8h+var_118], esi
0x18005e079  mov     byte ptr [rsp+1A8h+var_118+4], bl
0x18005e080  mov     word ptr [rsp+1A8h+var_118+5], r14w
0x18005e089  mov     byte ptr [rsp+1A8h+var_118+7], r15b
0x18005e091  lea     rdx, [rsp+1A8h+var_128]
0x18005e099  mov     rcx, rdi
0x18005e09c  call    ?NotifyClients@LightSensorAdapterImpl@LightSensorAdapter@DisplayEnhancement@Windows@Microsoft@@AEAAXULightSensorData@Foundation@345@@Z; Microsoft::Windows::DisplayEnhancement::LightSensorAdapter::LightSensorAdapterImpl::NotifyClients(Microsoft::Windows::DisplayEnhancement::Foundation::LightSensorData)
0x18005e0a1  xchg    bl, [rdi+0E8h]
0x18005e0a7  mov     eax, 3
0x18005e0ac  mov     rcx, [rsp+1A8h+var_48]
0x18005e0b4  xor     rcx, rsp; StackCookie
0x18005e0b7  call    __security_check_cookie
0x18005e0bc  lea     r11, [rsp+1A8h+var_28]
0x18005e0c4  mov     rbx, [r11+38h]
0x18005e0c8  mov     rsi, [r11+40h]
0x18005e0cc  movaps  xmm6, xmmword ptr [r11-10h]
0x18005e0d1  mov     rsp, r11
0x18005e0d4  pop     r15
0x18005e0d6  pop     r14
0x18005e0d8  pop     r13
0x18005e0da  pop     r12
0x18005e0dc  pop     rdi
0x18005e0dd  retn
0x18005e0de  mov     r9d, eax; char *
0x18005e0e1  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18005e0e8  mov     edx, 235h; void *
0x18005e0ed  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005e0f2  mov     r9d, eax; char *
0x18005e0f5  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\displaye"...
  ... truncated ...
```
