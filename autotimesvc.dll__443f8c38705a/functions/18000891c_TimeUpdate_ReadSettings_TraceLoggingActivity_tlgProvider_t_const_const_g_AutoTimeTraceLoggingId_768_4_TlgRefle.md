# TimeUpdate::ReadSettings(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)

- ea: `0x18000891c`
- end: `0x180008cb9`
- name: `?ReadSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@AEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `925`
- prototype: `__int64 *__fastcall(TimeUpdate *, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x1800084c4`

## callees

- `0x180001010`
- `0x1800010f4`
- `0x180001150`
- `0x1800012f0`
- `0x180002a70`
- `0x180004e68`
- `0x180005620`
- `0x180005840`
- `0x180005a74`
- `0x1800061ac`
- `0x18000891c`
- `0x18000ad28`
- `0x18000f598`
- `0x18000f6a4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a57`

## pseudocode

```c
__int64 *__fastcall TimeUpdate::ReadSettings(TimeUpdate *a1, __int64 *a2, _DWORD *a3)
{
  __int64 *v3; // r14
  int *v5; // r9
  _BYTE *v6; // r13
  bool v7; // r15
  char v8; // r12
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  __int64 *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  volatile signed __int32 *v13; // rsi
  unsigned int v14; // r8d
  const char *v15; // r9
  volatile signed __int32 *v16; // rsi
  TimeUpdate *v17; // rbx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 Settings; // rax
  volatile signed __int32 *v24; // rbx
  _QWORD v25[5]; // [rsp+0h] [rbp-E8h] BYREF
  char v26; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v27[7]; // [rsp+41h] [rbp-A7h] BYREF
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE *v29; // [rsp+50h] [rbp-98h] BYREF
  TimeUpdate *v30; // [rsp+58h] [rbp-90h]
  TimeUpdate *v31; // [rsp+60h] [rbp-88h]
  __int64 *v32; // [rsp+68h] [rbp-80h]
  Settings *v33; // [rsp+70h] [rbp-78h] BYREF
  volatile signed __int32 *v34; // [rsp+78h] [rbp-70h]
  _BYTE v35[8]; // [rsp+80h] [rbp-68h] BYREF
  volatile signed __int32 *v36; // [rsp+88h] [rbp-60h]
  int v37; // [rsp+90h] [rbp-58h] BYREF
  char v38; // [rsp+94h] [rbp-54h]
  _BYTE v39[16]; // [rsp+98h] [rbp-50h] BYREF
  int v40; // [rsp+A8h] [rbp-40h] BYREF
  int v41; // [rsp+ACh] [rbp-3Ch]
  int v42; // [rsp+B0h] [rbp-38h]
  int v43; // [rsp+B4h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v3 = a2;
  v30 = a1;
  v31 = a1;
  v32 = a2;
  LODWORD(v28) = 1;
  v37 = 0;
  v40 = a3[2];
  v41 = a3[3];
  v42 = a3[4];
  v43 = a3[5];
  v38 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v37);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    if ( v38 && (v40 || v41 || v42 || v43) )
      v5 = &v40;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)byte_180016521,
      (__int64)v39,
      (__int64)v5);
  }
  try
  {
    v6 = (char *)a1 + 240;
    v29 = (char *)a1 + 240;
    v7 = *((_BYTE *)a1 + 240) == 0;
    v27[0] = v7;
    v8 = 0;
    v26 = 0;
    *v3 = 0;
    v3[1] = 0;
    Settings::Read(&v33);
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 16);
    EnterCriticalSection(v9);
    v28 = v9;
    if ( !(unsigned __int8)Settings::operator==(v33, *((_QWORD *)v30 + 28)) )
    {
      if ( *((_BYTE *)v33 + 6) != *(_BYTE *)(*((_QWORD *)v30 + 28) + 6LL) )
        v7 = 1;
      v27[0] = v7;
      std::shared_ptr<Settings>::operator=((char *)v30 + 224, &v33);
      v8 = 1;
      v26 = 1;
    }
    v10 = (__int64 *)std::shared_ptr<Settings>::shared_ptr<Settings>(v35);
    v11 = *v10;
    *v10 = *v3;
    *v3 = v11;
    v12 = v10[1];
    v10[1] = v3[1];
    v3[1] = v12;
    v13 = v36;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v28);
    v16 = v34;
    if ( v34 )
    {
      if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    v17 = v30;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, v25, v14, v15);
    Settings = TimeUpdate::GetSettings((__int64)v31, (__int64)v35);
    std::shared_ptr<Settings>::operator=(v32, Settings);
    v24 = v36;
    if ( v36 && _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
    v7 = v27[0];
    v8 = v26;
    v17 = v31;
    v3 = v32;
    v6 = v29;
  }
  if ( (v8 || !*v6)
    && (unsigned int)dword_18001C010 > 4
    && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000302LL) )
  {
    v20 = *v3;
    v21 = (_QWORD *)(*v3 + 24);
    if ( *(_QWORD *)(*v3 + 48) > 7u )
      v21 = (_QWORD *)*v21;
    v29 = v21;
    v26 = *(_BYTE *)(v20 + 6);
    v27[0] = *(_BYTE *)(v20 + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v20,
      (__int64)qword_1800166E8,
      v18,
      v19,
      (__int64)v27,
      (__int64)&v26,
      &v29);
  }
  if ( v7 )
  {
    TimeUpdate::DoApplySettings(v17, &v37, v3);
    *v6 = 1;
  }
  v37 = 2;
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    v26 = v8;
    v25[4] = &v26;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
      (__int64)&dword_18001C010,
      (__int64)byte_180016411,
      (__int64)v39);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v37);
  return v3;
}

```

## disassembly

```asm
0x18000891c  mov     r11, rsp
0x18000891f  mov     [r11+18h], rbx
0x180008923  push    rsi
0x180008924  push    r12
0x180008926  push    r13
0x180008928  push    r14
0x18000892a  push    r15
0x18000892c  sub     rsp, 0C0h
0x180008933  mov     rax, cs:__security_cookie
0x18000893a  xor     rax, rsp
0x18000893d  mov     [rsp+0E8h+var_30], rax
0x180008945  mov     r14, rdx
0x180008948  mov     rbx, rcx
0x18000894b  mov     [rsp+0E8h+var_90], rcx
0x180008950  mov     [rsp+0E8h+var_88], rcx
0x180008955  mov     [r11-80h], rdx
0x180008959  mov     esi, 1
0x18000895e  mov     dword ptr [rsp+0E8h+var_A0], esi
0x180008962  mov     dword ptr [r11-58h], 0
0x18000896a  mov     eax, [r8+8]
0x18000896e  mov     [r11-40h], eax
0x180008972  mov     eax, [r8+0Ch]
0x180008976  mov     [r11-3Ch], eax
0x18000897a  mov     eax, [r8+10h]
0x18000897e  mov     [r11-38h], eax
0x180008982  mov     eax, [r8+14h]
0x180008986  mov     [r11-34h], eax
0x18000898a  mov     [r11-54h], sil
0x18000898e  lea     rcx, [r11-58h]
0x180008992  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)
0x180008997  mov     eax, cs:dword_18001C010
0x18000899d  cmp     eax, 4
0x1800089a0  jbe     short loc_180008A11
0x1800089a2  mov     edx, 300h
0x1800089a7  lea     rcx, dword_18001C010
0x1800089ae  call    _tlgKeywordOn
0x1800089b3  test    al, al
0x1800089b5  jz      short loc_180008A11
0x1800089b7  cmp     [rsp+0E8h+var_54], 0
0x1800089bf  jz      short loc_1800089F3
0x1800089c1  cmp     [rsp+0E8h+var_40], 0
0x1800089c9  jnz     short loc_1800089E9
0x1800089cb  cmp     [rsp+0E8h+var_3C], 0
0x1800089d3  jnz     short loc_1800089E9
0x1800089d5  cmp     [rsp+0E8h+var_38], 0
0x1800089dd  jnz     short loc_1800089E9
0x1800089df  cmp     [rsp+0E8h+var_34], 0
0x1800089e7  jz      short loc_1800089F3
0x1800089e9  lea     r9, [rsp+0E8h+var_40]
0x1800089f1  jmp     short loc_1800089F6
0x1800089f3  xor     r9d, r9d
0x1800089f6  lea     r8, [rsp+0E8h+var_50]
0x1800089fe  lea     rdx, byte_180016521
0x180008a05  lea     rcx, dword_18001C010
0x180008a0c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180008a11  lea     r13, [rbx+0F0h]
0x180008a18  mov     [rsp+0E8h+var_98], r13
0x180008a1d  cmp     byte ptr [r13+0], 0
0x180008a22  setz    r15b
0x180008a26  mov     [rsp+0E8h+var_A7], r15b
0x180008a2b  xor     r12b, r12b
0x180008a2e  mov     [rsp+0E8h+var_A8], r12b
0x180008a33  mov     qword ptr [r14], 0
0x180008a3a  mov     qword ptr [r14+8], 0
0x180008a42  mov     dword ptr [rsp+0E8h+var_A0], esi
0x180008a46  lea     rcx, [rsp+0E8h+var_78]
0x180008a4b  call    ?Read@Settings@@SA?AV?$shared_ptr@VSettings@@@std@@XZ; Settings::Read(void)
0x180008a50  add     rbx, 10h
0x180008a54  mov     rcx, rbx; lpCriticalSection
0x180008a57  call    cs:__imp_EnterCriticalSection
0x180008a5d  mov     [rsp+0E8h+var_A0], rbx
0x180008a62  mov     rbx, [rsp+0E8h+var_90]
0x180008a67  mov     rdx, [rbx+0E0h]
0x180008a6e  mov     rcx, [rsp+0E8h+var_78]
0x180008a73  call    ??8Settings@@QEBA_NAEBV0@@Z; Settings::operator==(Settings const &)
0x180008a78  test    al, al
0x180008a7a  jnz     short loc_180008AB4
0x180008a7c  mov     rcx, [rbx+0E0h]
0x180008a83  movzx   r15d, r15b
0x180008a87  mov     cl, [rcx+6]
0x180008a8a  mov     rax, [rsp+0E8h+var_78]
0x180008a8f  cmp     [rax+6], cl
0x180008a92  cmovnz  r15d, esi
0x180008a96  mov     [rsp+0E8h+var_A7], r15b
0x180008a9b  lea     rdx, [rsp+0E8h+var_78]
0x180008aa0  lea     rcx, [rbx+0E0h]
0x180008aa7  call    ??4?$shared_ptr@VSettings@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Settings>::operator=(std::shared_ptr<Settings> &&)
0x180008aac  mov     r12b, sil
0x180008aaf  mov     [rsp+0E8h+var_A8], sil
0x180008ab4  lea     rdx, [rbx+0E0h]
0x180008abb  lea     rcx, [rsp+0E8h+var_68]
0x180008ac3  call    ??0?$shared_ptr@VSettings@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Settings>::shared_ptr<Settings>(std::shared_ptr<Settings> const &)
0x180008ac8  mov     rdx, [rax]
0x180008acb  mov     rcx, [r14]
0x180008ace  mov     [rax], rcx
0x180008ad1  mov     [r14], rdx
0x180008ad4  mov     rdx, [rax+8]
0x180008ad8  mov     rcx, [r14+8]
0x180008adc  mov     [rax+8], rcx
0x180008ae0  mov     [r14+8], rdx
0x180008ae4  mov     rsi, [rsp+0E8h+var_60]
0x180008aec  or      ebx, 0FFFFFFFFh
0x180008aef  test    rsi, rsi
0x180008af2  jz      short loc_180008B27
0x180008af4  mov     eax, ebx
0x180008af6  lock xadd [rsi+8], eax
0x180008afb  add     eax, ebx
0x180008afd  jnz     short loc_180008B27
0x180008aff  mov     rax, [rsi]
0x180008b02  mov     rcx, rsi
0x180008b05  mov     rax, [rax]
0x180008b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b0d  mov     eax, ebx
0x180008b0f  lock xadd [rsi+0Ch], eax
0x180008b14  add     eax, ebx
0x180008b16  jnz     short loc_180008B27
0x180008b18  mov     rax, [rsi]
0x180008b1b  mov     rcx, rsi
0x180008b1e  mov     rax, [rax+8]
0x180008b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b27  lea     rcx, [rsp+0E8h+var_A0]
0x180008b2c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180008b31  mov     rsi, [rsp+0E8h+var_70]
0x180008b36  test    rsi, rsi
0x180008b39  jz      short loc_180008B6F
0x180008b3b  mov     eax, ebx
0x180008b3d  lock xadd [rsi+8], eax
0x180008b42  add     eax, ebx
0x180008b44  jnz     short loc_180008B6F
0x180008b46  mov     rax, [rsi]
0x180008b49  mov     rcx, rsi
0x180008b4c  mov     rax, [rax]
0x180008b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b54  mov     eax, ebx
0x180008b56  lock xadd [rsi+0Ch], eax
0x180008b5b  add     eax, ebx
0x180008b5d  jnz     short loc_180008B6F
0x180008b5f  mov     rax, [rsi]
0x180008b62  mov     rcx, rsi
0x180008b65  mov     rax, [rax+8]
0x180008b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6e  nop
0x180008b6f  mov     rbx, [rsp+0E8h+var_90]
0x180008b74  jmp     short loc_180008B8F
0x180008b76  mov     r15b, [rsp+0E8h+var_A7]
0x180008b7b  mov     r12b, [rsp+0E8h+var_A8]
0x180008b80  mov     rbx, [rsp+0E8h+var_88]
0x180008b85  mov     r14, [rsp+0E8h+var_80]
0x180008b8a  mov     r13, [rsp+0E8h+var_98]
0x180008b8f  test    r12b, r12b
0x180008b92  jnz     short loc_180008B9A
0x180008b94  cmp     [r13+0], r12b
0x180008b98  jnz     short loc_180008C0D
0x180008b9a  mov     eax, cs:dword_18001C010
0x180008ba0  cmp     eax, 4
0x180008ba3  jbe     short loc_180008C0D
0x180008ba5  mov     rdx, 400000000302h
0x180008baf  lea     rcx, dword_18001C010
0x180008bb6  call    _tlgKeywordOn
0x180008bbb  test    al, al
0x180008bbd  jz      short loc_180008C0D
0x180008bbf  mov     rcx, [r14]
0x180008bc2  lea     rax, [rcx+18h]
0x180008bc6  cmp     qword ptr [rax+18h], 7
0x180008bcb  jbe     short loc_180008BD0
0x180008bcd  mov     rax, [rax]
0x180008bd0  mov     [rsp+0E8h+var_98], rax
0x180008bd5  mov     al, [rcx+6]
0x180008bd8  mov     [rsp+0E8h+var_A8], al
0x180008bdc  mov     al, [rcx+4]
0x180008bdf  mov     [rsp+0E8h+var_A7], al
0x180008be3  lea     rax, [rsp+0E8h+var_98]
0x180008be8  mov     [rsp+0E8h+var_B8], rax
0x180008bed  lea     rax, [rsp+0E8h+var_A8]
0x180008bf2  mov     [rsp+0E8h+var_C0], rax
0x180008bf7  lea     rax, [rsp+0E8h+var_A7]
0x180008bfc  mov     [rsp+0E8h+var_C8], rax
0x180008c01  lea     rdx, qword_1800166E8
0x180008c08  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x180008c0d  test    r15b, r15b
0x180008c10  jz      short loc_180008C2A
0x180008c12  mov     r8, r14
0x180008c15  lea     rdx, [rsp+0E8h+var_58]
0x180008c1d  mov     rcx, rbx; this
0x180008c20  call    ?DoApplySettings@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@AEBV?$shared_ptr@VSettings@@@std@@@Z; TimeUpdate::DoApplySettings(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &,std::shared_ptr<Settings> const &)
0x180008c25  mov     byte ptr [r13+0], 1
0x180008c2a  mov     [rsp+0E8h+var_58], 2
0x180008c35  mov     eax, cs:dword_18001C010
0x180008c3b  cmp     eax, 4
0x180008c3e  jbe     short loc_180008C80
0x180008c40  mov     edx, 300h
0x180008c45  lea     rcx, dword_18001C010
0x180008c4c  call    _tlgKeywordOn
0x180008c51  test    al, al
0x180008c53  jz      short loc_180008C80
0x180008c55  mov     [rsp+0E8h+var_A8], r12b
0x180008c5a  lea     rax, [rsp+0E8h+var_A8]
0x180008c5f  mov     [rsp+0E8h+var_C8], rax
0x180008c64  lea     r8, [rsp+0E8h+var_50]
0x180008c6c  lea     rdx, byte_180016411
0x180008c73  lea     rcx, dword_18001C010
0x180008c7a  call    ??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)
0x180008c7f  nop
0x180008c80  lea     rcx, [rsp+0E8h+var_58]
0x180008c88  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)
0x180008c8d  mov     rax, r14
0x180008c90  mov     rcx, [rsp+0E8h+var_30]
0x180008c98  xor     rcx, rsp; StackCookie
0x180008c9b  call    __security_check_cookie
0x180008ca0  mov     rbx, [rsp+0E8h+arg_10]
0x180008ca8  add     rsp, 0C0h
0x180008caf  pop     r15
0x180008cb1  pop     r14
0x180008cb3  pop     r13
0x180008cb5  pop     r12
0x180008cb7  pop     rsi
0x180008cb8  retn
```
