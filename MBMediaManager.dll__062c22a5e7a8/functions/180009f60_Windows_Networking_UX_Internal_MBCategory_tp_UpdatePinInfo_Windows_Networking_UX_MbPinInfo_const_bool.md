# Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo(Windows::Networking::UX::MbPinInfo const &,bool)

- ea: `0x180009f60`
- end: `0x18000a455`
- name: `?tp_UpdatePinInfo@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUMbPinInfo@345@_N@Z`
- size: `1269`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this, const struct Windows::Networking::UX::MbPinInfo *, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003b860`
- `0x18003bfd4`

## callees

- `0x180008c84`
- `0x180009f60`
- `0x18000ad20`
- `0x18000ecbc`
- `0x18000efa4`
- `0x18001a494`
- `0x18001a6e8`
- `0x18001bd80`
- `0x18001bdb8`
- `0x18001bfa8`
- `0x180024378`
- `0x18002d20c`
- `0x180059010`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000a189`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000a1b8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000a189`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18000a1b8`

## string_xrefs

- `0x18000a079`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a24a`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a276`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a2a2`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a2d1`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a2fe`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a32a`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a356`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo`
- `0x18000a06d`: `force update`
- `0x18000a0e9`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000a163`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000a37b`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState`
- `0x18000a0dd`: `old _readyState=%d, new _readyState=%d`
- `0x18000a23e`: `updated attemptsRemaining. old attemptsRemaining=%d, new attemptsRemaining=%d`
- `0x18000a26a`: `updated maxLength. old maxLength=%d, new maxLength=%d`
- `0x18000a296`: `updated minLength. old minLength=%d, new minLength=%d`
- `0x18000a2c5`: `updated pinEnabled. old pinEnabled=%d, new pinEnabled=%d`
- `0x18000a2f2`: `updated pinFormat. old pinFormat=%d, new pinFormat=%d`
- `0x18000a31e`: `updated pinState. old pinState=%d, new pinState=%d`
- `0x18000a34a`: `updated pinType. old pinType=%d, new pinType=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo(
        Windows::Networking::UX::Internal::MBCategory *this,
        const struct Windows::Networking::UX::MbPinInfo *a2,
        char a3)
{
  char v6; // dl
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // ecx
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  char *v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, __int64); // rdx
  __int128 v16; // xmm1
  int v17; // esi
  int v18; // r9d
  int WwanInterfaceObject; // esi
  __int64 (__fastcall ***v20)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, __int64); // rax
  __int64 (__fastcall ***v29)(_QWORD, __int64); // rdx
  int v30; // [rsp+20h] [rbp-30h]
  _BYTE v31[28]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 (__fastcall ***v33)(_QWORD, __int64); // [rsp+70h] [rbp+20h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, __int64); // [rsp+78h] [rbp+28h] BYREF

  v6 = 0;
  v7 = *((_DWORD *)this + 122);
  if ( v7 != *((_DWORD *)a2 + 3) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10BAu,
      "updated attemptsRemaining. old attemptsRemaining=%d, new attemptsRemaining=%d",
      v7,
      *((_DWORD *)a2 + 3));
    *((_DWORD *)this + 122) = *((_DWORD *)a2 + 3);
    v6 = 1;
  }
  v8 = *((_DWORD *)this + 125);
  if ( v8 != *((_DWORD *)a2 + 6) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10C4u,
      "updated maxLength. old maxLength=%d, new maxLength=%d",
      v8,
      *((_DWORD *)a2 + 6));
    *((_DWORD *)this + 125) = *((_DWORD *)a2 + 6);
    v6 = 1;
  }
  v9 = *((_DWORD *)this + 124);
  if ( v9 != *((_DWORD *)a2 + 5) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10CEu,
      "updated minLength. old minLength=%d, new minLength=%d",
      v9,
      *((_DWORD *)a2 + 5));
    *((_DWORD *)this + 124) = *((_DWORD *)a2 + 5);
    v6 = 1;
  }
  v10 = *((unsigned __int8 *)this + 484);
  if ( (_BYTE)v10 != *((_BYTE *)a2 + 8) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10D8u,
      "updated pinEnabled. old pinEnabled=%d, new pinEnabled=%d",
      v10,
      *((unsigned __int8 *)a2 + 8));
    *((_BYTE *)this + 484) = *((_BYTE *)a2 + 8);
    v6 = 1;
  }
  v11 = *((_DWORD *)this + 123);
  if ( v11 != *((_DWORD *)a2 + 4) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10E2u,
      "updated pinFormat. old pinFormat=%d, new pinFormat=%d",
      v11,
      *((_DWORD *)a2 + 4));
    *((_DWORD *)this + 123) = *((_DWORD *)a2 + 4);
    v6 = 1;
  }
  v12 = *((_DWORD *)this + 120);
  if ( v12 != *((_DWORD *)a2 + 1) )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10ECu,
      "updated pinState. old pinState=%d, new pinState=%d",
      v12,
      *((_DWORD *)a2 + 1));
    *((_DWORD *)this + 120) = *((_DWORD *)a2 + 1);
    v6 = 1;
  }
  v13 = *((_DWORD *)this + 119);
  if ( v13 == *(_DWORD *)a2 )
  {
    if ( !v6 )
    {
      if ( !a3 )
      {
LABEL_16:
        if ( *((_QWORD *)this + 44) )
        {
          v14 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
          v15 = (__int64 (__fastcall ***)(_QWORD, __int64))v14;
          v33 = (__int64 (__fastcall ***)(_QWORD, __int64))v14;
          if ( v14 )
          {
            *(_OWORD *)v31 = *(_OWORD *)a2;
            *(_OWORD *)&v31[12] = *(_OWORD *)((char *)a2 + 12);
            v16 = *(_OWORD *)&v31[12];
            *((_DWORD *)v14 + 2) = 0;
            *(_QWORD *)v14 = &Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable';
            *((_OWORD *)v14 + 1) = *(_OWORD *)v31;
            *(_OWORD *)(v14 + 28) = v16;
          }
          else
          {
            v15 = 0;
          }
          v34 = v15;
          if ( v15 )
          {
            v25 = (__int64 *)*((_QWORD *)this + 44);
            v26 = *v25;
            v34 = 0;
            v33 = v15;
            v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v26 + 72))(v25, &v33);
            if ( v27 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1113,
                (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
                (const char *)(unsigned int)v27);
          }
          else
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x1117,
              (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
              (const char *)0x8007000ELL,
              v30);
          }
          std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(&v34);
        }
        return;
      }
      goto LABEL_20;
    }
  }
  else
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo",
      0x10F6u,
      "updated pinType. old pinType=%d, new pinType=%d",
      v13,
      *(_DWORD *)a2);
    *((_DWORD *)this + 119) = *(_DWORD *)a2;
  }
  if ( a3 )
LABEL_20:
    MBSettingUXLogging::Info("Windows::Networking::UX::Internal::MBCategory::tp_UpdatePinInfo", 0x1100u, "force update");
  Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(this, 15);
  Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(this, 16);
  v17 = *((_DWORD *)this + 151);
  if ( v17 == 6 || v17 == 7 )
  {
    v33 = 0;
    *(_QWORD *)&v31[8] = 0;
    v31[16] = 1;
    WwanInterfaceObject = Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(
                            this,
                            (struct WWAN_INTERFACE_OBJECT **)&v31[8]);
    if ( v31[16] )
    {
      v21 = v33;
      v33 = *(__int64 (__fastcall ****)(_QWORD, __int64))&v31[8];
      if ( v21 )
        WwanFreeMemory(v21);
    }
    if ( WwanInterfaceObject >= 0 && (v20 = v33) != 0 )
    {
      v17 = (*((_DWORD *)v33 + 258) != 0) + 6;
    }
    else
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
        0xE41u,
        "Failed to do GetWwanInterfaceObject");
      v17 = 6;
      v20 = v33;
    }
    v33 = 0;
    if ( v20 )
      WwanFreeMemory(v20);
  }
  v18 = *((_DWORD *)this + 151);
  if ( v18 != v17 )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
      0xE55u,
      "old _readyState=%d, new _readyState=%d",
      v18,
      v17);
    *((_DWORD *)this + 151) = v17;
    Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae(this);
    if ( *((_DWORD *)this + 151) == 3 )
    {
      MBSettingUXLogging::Info(
        "Windows::Networking::UX::Internal::MBCategory::tp_UpdateReadyState",
        0xE60u,
        "Query PinState");
      Windows::Networking::UX::Internal::MBCategory::tp_GetPinState(this);
    }
    Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface((HSTRING *)this);
  }
  if ( *((_QWORD *)this + 44) )
  {
    v28 = (__int64 (__fastcall ***)(_QWORD, __int64))operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v29 = v28;
    v33 = v28;
    if ( v28 )
    {
      *((_DWORD *)v28 + 2) = 2;
      *v28 = (__int64 (__fastcall **)(_QWORD, __int64))&Windows::Networking::UX::Internal::MBReadyStateChangeEvent::`vftable';
    }
    else
    {
      v29 = 0;
    }
    v34 = v29;
    if ( v29 )
    {
      v22 = (__int64 *)*((_QWORD *)this + 44);
      v23 = *v22;
      v34 = 0;
      v33 = v29;
      v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v23 + 72))(v22, &v33);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE6D,
          (int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v24);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xE71,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
        (const char *)0x8007000ELL,
        v30);
    }
    std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(&v34);
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180009f60  mov     [rsp-18h+arg_10], rbx
0x180009f65  push    rbp
0x180009f66  push    rsi
0x180009f67  push    rdi
0x180009f68  mov     rbp, rsp
0x180009f6b  sub     rsp, 50h
0x180009f6f  movzx   esi, r8b
0x180009f73  mov     rdi, rdx
0x180009f76  mov     rbx, rcx
0x180009f79  xor     dl, dl
0x180009f7b  mov     eax, [rdi+0Ch]
0x180009f7e  mov     r9d, [rcx+1E8h]
0x180009f85  cmp     r9d, eax
0x180009f88  jnz     loc_18000A23A
0x180009f8e  mov     eax, [rdi+18h]
0x180009f91  mov     r9d, [rbx+1F4h]
0x180009f98  cmp     r9d, eax
0x180009f9b  jnz     loc_18000A266
0x180009fa1  mov     eax, [rdi+14h]
0x180009fa4  mov     r9d, [rbx+1F0h]
0x180009fab  cmp     r9d, eax
0x180009fae  jnz     loc_18000A292
0x180009fb4  movzx   eax, byte ptr [rdi+8]
0x180009fb8  movzx   ecx, byte ptr [rbx+1E4h]
0x180009fbf  cmp     cl, al
0x180009fc1  jnz     loc_18000A2BE
0x180009fc7  mov     eax, [rdi+10h]
0x180009fca  mov     r9d, [rbx+1ECh]
0x180009fd1  cmp     r9d, eax
0x180009fd4  jnz     loc_18000A2EE
0x180009fda  mov     eax, [rdi+4]
0x180009fdd  mov     r9d, [rbx+1E0h]
0x180009fe4  cmp     r9d, eax
0x180009fe7  jnz     loc_18000A31A
0x180009fed  mov     eax, [rdi]
0x180009fef  mov     r9d, [rbx+1DCh]
0x180009ff6  cmp     r9d, eax
0x180009ff9  jnz     loc_18000A346
0x180009fff  test    dl, dl
0x18000a001  jnz     short loc_18000A068
0x18000a003  test    sil, sil
0x18000a006  jnz     short loc_18000A06D
0x18000a008  cmp     qword ptr [rbx+160h], 0
0x18000a010  jz      loc_18000A0C9
0x18000a016  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a01d  mov     ecx, 30h ; '0'; unsigned __int64
0x18000a022  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a027  mov     rdx, rax
0x18000a02a  mov     [rbp+arg_0], rax
0x18000a02e  test    rax, rax
0x18000a031  jz      loc_18000A40C
0x18000a037  movups  xmm0, xmmword ptr [rdi]
0x18000a03a  movaps  xmmword ptr [rbp+var_20], xmm0
0x18000a03e  movups  xmm1, xmmword ptr [rdi+0Ch]
0x18000a042  movups  xmmword ptr [rbp+var_20+0Ch], xmm1
0x18000a046  mov     dword ptr [rax+8], 0
0x18000a04d  lea     rax, ??_7MBPinEnterCompleteEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBPinEnterCompleteEvent::`vftable'
0x18000a054  mov     [rdx], rax
0x18000a057  movaps  xmm0, xmmword ptr [rbp+var_20]
0x18000a05b  movups  xmmword ptr [rdx+10h], xmm0
0x18000a05f  movups  xmmword ptr [rdx+1Ch], xmm1
0x18000a063  jmp     loc_18000A40E
0x18000a068  test    sil, sil
0x18000a06b  jz      short loc_18000A085
0x18000a06d  lea     r8, aForceUpdate; "force update"
0x18000a074  mov     edx, 1100h; unsigned int
0x18000a079  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a080  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a085  mov     edx, 0Fh
0x18000a08a  mov     rcx, rbx
0x18000a08d  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18000a092  mov     edx, 10h
0x18000a097  mov     rcx, rbx
0x18000a09a  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18000a09f  mov     esi, [rbx+25Ch]
0x18000a0a5  cmp     esi, 6
0x18000a0a8  jz      short loc_18000A11A
0x18000a0aa  cmp     esi, 7
0x18000a0ad  jz      short loc_18000A11A
0x18000a0af  mov     r9d, [rbx+25Ch]
0x18000a0b6  cmp     r9d, esi
0x18000a0b9  jnz     short loc_18000A0D9
0x18000a0bb  cmp     qword ptr [rbx+160h], 0
0x18000a0c3  jnz     loc_18000A394
0x18000a0c9  mov     rbx, [rsp+50h+arg_10]
0x18000a0d1  add     rsp, 50h
0x18000a0d5  pop     rdi
0x18000a0d6  pop     rsi
0x18000a0d7  pop     rbp
0x18000a0d8  retn
0x18000a0d9  mov     [rsp+50h+var_30], esi
0x18000a0dd  lea     r8, aOldReadystateD; "old _readyState=%d, new _readyState=%d"
0x18000a0e4  mov     edx, 0E55h; unsigned int
0x18000a0e9  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000a0f0  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a0f5  mov     [rbx+25Ch], esi
0x18000a0fb  mov     rcx, rbx; this
0x18000a0fe  call    ?tp_TryInitMbae@MBCategory@Internal@UX@Networking@Windows@@AEAA_NXZ; Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae(void)
0x18000a103  cmp     dword ptr [rbx+25Ch], 3
0x18000a10a  jz      loc_18000A36F
0x18000a110  mov     rcx, rbx; this
0x18000a113  call    ?tp_RefreshInterface@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_RefreshInterface(void)
0x18000a118  jmp     short loc_18000A0BB
0x18000a11a  mov     [rbp+arg_0], 0
0x18000a122  lea     rax, [rbp+arg_0]
0x18000a126  mov     [rbp+var_20], rax
0x18000a12a  mov     [rbp+var_20+8], 0
0x18000a132  mov     [rbp+var_10], 1
0x18000a136  lea     rdx, [rbp+var_20+8]; struct WWAN_INTERFACE_OBJECT **
0x18000a13a  mov     rcx, rbx; this
0x18000a13d  call    ?_GetWwanInterfaceObject@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAUWWAN_INTERFACE_OBJECT@@@Z; Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(WWAN_INTERFACE_OBJECT * *)
0x18000a142  mov     esi, eax
0x18000a144  cmp     [rbp+var_10], 0
0x18000a148  jnz     short loc_18000A1A5
0x18000a14a  test    esi, esi
0x18000a14c  js      short loc_18000A157
0x18000a14e  mov     rcx, [rbp+arg_0]
0x18000a152  test    rcx, rcx
0x18000a155  jnz     short loc_18000A194
0x18000a157  lea     r8, aFailedToDoGetw; "Failed to do GetWwanInterfaceObject"
0x18000a15e  mov     edx, 0E41h; unsigned int
0x18000a163  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000a16a  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18000a16f  mov     esi, 6
0x18000a174  mov     rcx, [rbp+arg_0]
0x18000a178  mov     [rbp+arg_0], 0
0x18000a180  test    rcx, rcx
0x18000a183  jz      loc_18000A0AF
0x18000a189  call    cs:__imp_WwanFreeMemory
0x18000a18f  jmp     loc_18000A0AF
0x18000a194  xor     esi, esi
0x18000a196  cmp     [rcx+408h], esi
0x18000a19c  setnz   sil
0x18000a1a0  add     esi, 6
0x18000a1a3  jmp     short loc_18000A178
0x18000a1a5  mov     r8, [rbp+var_20]
0x18000a1a9  mov     rcx, [r8]
0x18000a1ac  mov     rdx, [rbp+var_20+8]
0x18000a1b0  mov     [r8], rdx
0x18000a1b3  test    rcx, rcx
0x18000a1b6  jz      short loc_18000A14A
0x18000a1b8  call    cs:__imp_WwanFreeMemory
0x18000a1be  jmp     short loc_18000A14A
0x18000a1c0  mov     rcx, [rbx+160h]
0x18000a1c7  mov     rax, [rcx]
0x18000a1ca  mov     [rbp+arg_8], 0
0x18000a1d2  mov     [rbp+arg_0], rdx
0x18000a1d6  lea     rdx, [rbp+arg_0]
0x18000a1da  mov     rax, [rax+48h]
0x18000a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e3  mov     rcx, [rbp+18h]; this
0x18000a1e7  test    eax, eax
0x18000a1e9  js      loc_18000A3F3
0x18000a1ef  lea     rcx, [rbp+arg_8]
0x18000a1f3  call    ??1?$unique_ptr@UMBStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UMBStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(void)
0x18000a1f8  jmp     loc_18000A008
0x18000a1fd  mov     rcx, [rbx+160h]
0x18000a204  mov     rax, [rcx]
0x18000a207  mov     [rbp+arg_8], 0
0x18000a20f  mov     [rbp+arg_0], rdx
0x18000a213  lea     rdx, [rbp+arg_0]
0x18000a217  mov     rax, [rax+48h]
0x18000a21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a220  mov     rcx, [rbp+18h]; this
0x18000a224  test    eax, eax
0x18000a226  js      loc_18000A43B
0x18000a22c  lea     rcx, [rbp+arg_8]
0x18000a230  call    ??1?$unique_ptr@UMBStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UMBStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>::~unique_ptr<Windows::Networking::UX::Internal::MBStateMachineEvent>(void)
0x18000a235  jmp     loc_18000A0C9
0x18000a23a  mov     [rsp+50h+var_30], eax
0x18000a23e  lea     r8, aUpdatedAttempt; "updated attemptsRemaining. old attempts"...
0x18000a245  mov     edx, 10BAh; unsigned int
0x18000a24a  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a251  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a256  mov     eax, [rdi+0Ch]
0x18000a259  mov     [rbx+1E8h], eax
0x18000a25f  mov     dl, 1
0x18000a261  jmp     loc_180009F8E
0x18000a266  mov     [rsp+50h+var_30], eax
0x18000a26a  lea     r8, aUpdatedMaxleng; "updated maxLength. old maxLength=%d, ne"...
0x18000a271  mov     edx, 10C4h; unsigned int
0x18000a276  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a27d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a282  mov     eax, [rdi+18h]
0x18000a285  mov     [rbx+1F4h], eax
0x18000a28b  mov     dl, 1
0x18000a28d  jmp     loc_180009FA1
0x18000a292  mov     [rsp+50h+var_30], eax
0x18000a296  lea     r8, aUpdatedMinleng; "updated minLength. old minLength=%d, ne"...
0x18000a29d  mov     edx, 10CEh; unsigned int
0x18000a2a2  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a2a9  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a2ae  mov     eax, [rdi+14h]
0x18000a2b1  mov     [rbx+1F0h], eax
0x18000a2b7  mov     dl, 1
0x18000a2b9  jmp     loc_180009FB4
0x18000a2be  mov     r9d, ecx
0x18000a2c1  mov     [rsp+50h+var_30], eax
0x18000a2c5  lea     r8, aUpdatedPinenab; "updated pinEnabled. old pinEnabled=%d, "...
0x18000a2cc  mov     edx, 10D8h; unsigned int
0x18000a2d1  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a2d8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a2dd  movzx   eax, byte ptr [rdi+8]
0x18000a2e1  mov     [rbx+1E4h], al
0x18000a2e7  mov     dl, 1
0x18000a2e9  jmp     loc_180009FC7
0x18000a2ee  mov     [rsp+50h+var_30], eax
0x18000a2f2  lea     r8, aUpdatedPinform; "updated pinFormat. old pinFormat=%d, ne"...
0x18000a2f9  mov     edx, 10E2h; unsigned int
0x18000a2fe  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a305  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a30a  mov     eax, [rdi+10h]
0x18000a30d  mov     [rbx+1ECh], eax
0x18000a313  mov     dl, 1
0x18000a315  jmp     loc_180009FDA
0x18000a31a  mov     [rsp+50h+var_30], eax
0x18000a31e  lea     r8, aUpdatedPinstat; "updated pinState. old pinState=%d, new "...
0x18000a325  mov     edx, 10ECh; unsigned int
0x18000a32a  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a331  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a336  mov     eax, [rdi+4]
0x18000a339  mov     [rbx+1E0h], eax
0x18000a33f  mov     dl, 1
0x18000a341  jmp     loc_180009FED
0x18000a346  mov     [rsp+50h+var_30], eax
0x18000a34a  lea     r8, aUpdatedPintype; "updated pinType. old pinType=%d, new pi"...
0x18000a351  mov     edx, 10F6h; unsigned int
0x18000a356  lea     rcx, aWindowsNetwork_209; "Windows::Networking::UX::Internal::MBCa"...
0x18000a35d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a362  mov     eax, [rdi]
0x18000a364  mov     [rbx+1DCh], eax
0x18000a36a  jmp     loc_18000A068
0x18000a36f  lea     r8, aQueryPinstate; "Query PinState"
0x18000a376  mov     edx, 0E60h; unsigned int
0x18000a37b  lea     rcx, aWindowsNetwork_288; "Windows::Networking::UX::Internal::MBCa"...
0x18000a382  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18000a387  mov     rcx, rbx; this
0x18000a38a  call    ?tp_GetPinState@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ; Windows::Networking::UX::Internal::MBCategory::tp_GetPinState(void)
0x18000a38f  jmp     loc_18000A110
0x18000a394  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a39b  mov     ecx, 10h; unsigned __int64
0x18000a3a0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a3a5  mov     rdx, rax
0x18000a3a8  mov     [rbp+arg_0], rax
0x18000a3ac  test    rax, rax
0x18000a3af  jz      short loc_18000A3C4
0x18000a3b1  mov     dword ptr [rax+8], 2
0x18000a3b8  lea     rax, ??_7MBReadyStateChangeEvent@Internal@UX@Networking@Windows@@6B@; const Windows::Networking::UX::Internal::MBReadyStateChangeEvent::`vftable'
0x18000a3bf  mov     [rdx], rax
0x18000a3c2  jmp     short loc_18000A3C6
0x18000a3c4  xor     edx, edx
0x18000a3c6  mov     [rbp+arg_8], rdx
0x18000a3ca  test    rdx, rdx
0x18000a3cd  jnz     loc_18000A1C0
0x18000a3d3  mov     rcx, [rbp+18h]; this
0x18000a3d7  mov     r9d, 8007000Eh; char *
0x18000a3dd  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000a3e4  mov     edx, 0E71h; void *
0x18000a3e9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000a3ee  jmp     loc_18000A1EF
0x18000a3f3  mov     r9d, eax; char *
0x18000a3f6  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000a3fd  mov     edx, 0E6Dh; void *
0x18000a402  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a407  jmp     loc_18000A1EF
0x18000a40c  xor     edx, edx
0x18000a40e  mov     [rbp+arg_8], rdx
0x18000a412  test    rdx, rdx
0x18000a415  jnz     loc_18000A1FD
0x18000a41b  mov     rcx, [rbp+18h]; this
0x18000a41f  mov     r9d, 8007000Eh; char *
0x18000a425  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000a42c  mov     edx, 1117h; void *
0x18000a431  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000a436  jmp     loc_18000A22C
0x18000a43b  mov     r9d, eax; char *
0x18000a43e  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18000a445  mov     edx, 1113h; void *
0x18000a44a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a44f  jmp     loc_18000A22C
```
