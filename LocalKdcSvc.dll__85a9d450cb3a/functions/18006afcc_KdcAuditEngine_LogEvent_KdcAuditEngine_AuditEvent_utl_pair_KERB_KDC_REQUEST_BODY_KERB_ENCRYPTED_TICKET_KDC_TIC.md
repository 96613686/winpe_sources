# KdcAuditEngine::LogEvent(KdcAuditEngine::AuditEvent,utl::pair<KERB_KDC_REQUEST_BODY *,KERB_ENCRYPTED_TICKET *>,_KDC_TICKET_INFO const &,utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &,utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &,utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &,utl::optional<long>)

- ea: `0x18006afcc`
- end: `0x18006b4da`
- name: `?LogEvent@KdcAuditEngine@@QEBAXW4AuditEvent@1@U?$pair@PEAUKERB_KDC_REQUEST_BODY@@PEAUKERB_ENCRYPTED_TICKET@@@utl@@AEBU_KDC_TICKET_INFO@@AEBV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@4@33V?$optional@J@4@@Z`
- size: `1294`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021eb4`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000a878`
- `0x18000a8d8`
- `0x18000e9e8`
- `0x18001371c`
- `0x1800138c4`
- `0x180013c1c`
- `0x18001cdc4`
- `0x18006a7fc`
- `0x18006aa64`
- `0x18006aae4`
- `0x18006ab0c`
- `0x18006afcc`
- `0x18006b8d8`
- `0x18006bc20`
- `0x180072338`
- `0x180080068`
- `0x180080170`
- `0x18008030c`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b0d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18006b0d3`

## pseudocode

```c
int __fastcall KdcAuditEngine::LogEvent(
        __int64 a1,
        int a2,
        __int64 *a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD **a7,
        __int64 a8)
{
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 *Value; // rax
  const wchar_t *v14; // rdi
  const wchar_t *v15; // rsi
  __int64 v16; // rax
  int v17; // ebx
  int v18; // ebx
  const wchar_t *v19; // rax
  const wchar_t *v20; // rax
  _BYTE v22[8]; // [rsp+90h] [rbp-80h] BYREF
  const wchar_t *v23; // [rsp+98h] [rbp-78h]
  char v24; // [rsp+A0h] [rbp-70h]
  __int64 v25; // [rsp+A8h] [rbp-68h] BYREF
  _DWORD v26[2]; // [rsp+B0h] [rbp-60h] BYREF
  _BYTE v27[8]; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-50h]
  char v29; // [rsp+C8h] [rbp-48h]
  __int64 v30; // [rsp+D8h] [rbp-38h]
  char v31; // [rsp+E0h] [rbp-30h]
  _OWORD v32[2]; // [rsp+E8h] [rbp-28h] BYREF
  __int64 v33; // [rsp+108h] [rbp-8h]
  __int64 *v34; // [rsp+110h] [rbp+0h] BYREF
  _BYTE v35[8]; // [rsp+118h] [rbp+8h] BYREF
  const wchar_t *v36; // [rsp+120h] [rbp+10h]
  char v37; // [rsp+128h] [rbp+18h]
  _BYTE v38[48]; // [rsp+130h] [rbp+20h] BYREF
  __int64 v39; // [rsp+160h] [rbp+50h]
  _BYTE v40[48]; // [rsp+168h] [rbp+58h] BYREF
  __int64 v41; // [rsp+198h] [rbp+88h]
  _BYTE v42[48]; // [rsp+1A0h] [rbp+90h] BYREF
  __int64 v43; // [rsp+1D0h] [rbp+C0h]
  void *v44[5]; // [rsp+1D8h] [rbp+C8h] BYREF
  _OWORD v45[7]; // [rsp+200h] [rbp+F0h] BYREF
  _BYTE v46[128]; // [rsp+270h] [rbp+160h] BYREF
  _BYTE Sid[80]; // [rsp+2F0h] [rbp+1E0h] BYREF
  _OWORD v48[6]; // [rsp+340h] [rbp+230h] BYREF
  __int16 v49; // [rsp+3AEh] [rbp+29Eh]

  if ( !*(_BYTE *)(a1 + 24) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = *a3;
  v12 = a3[1];
  v25 = v12;
  if ( !v11 || !v12 || !*a5 || !*a6 || !*a7 )
  {
    LODWORD(v12) = MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !v11 )
      return v12;
    v12 = v25;
  }
  if ( v12 && *a5 && *a6 && *a7 )
  {
    v34 = &v25;
    lambda_e64b62a3704c3b288d98d26c75f0ec9e_::operator()(&v34, v27);
    if ( v29 )
    {
      if ( v31 )
      {
        memset_0(Sid, 0, 0x48u);
        KdcMakeAccountSid(Sid, *(_DWORD *)(a4 + 48));
        Value = (__int64 *)TlsGetValue(KdcThreadContext::s_tlsIndex);
        if ( Value )
        {
          if ( *((_BYTE *)Value + 8) )
          {
            KdcThreadContext::GetNetworkInfo(Value, (__int64)v46);
            LODWORD(v45[0]) = 45;
            memset_0((char *)v45 + 4, 0, 0x6Cu);
            utl::expected<KdcThreadContext::KdcNetworkInfo,long>::value_or<KdcThreadContext::KdcNetworkInfo>(
              (__int64)v46,
              v48,
              v45);
            KdcEventPrincipal::KdcEventPrincipal((__int64)v42, a5);
            KdcEventPrincipal::KdcEventPrincipal((__int64)v40, a6);
            KdcEventPrincipal::KdcEventPrincipal((__int64)v38, a7);
            (*(void (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)**a7 + 232LL))(**a7, v26);
            if ( v26[1] >= 0 )
            {
              KerberosCryptoPolicy::BitmaskToString(v22, v26[0]);
              KerberosCryptoPolicy::EtypeListToString(v35, *(_QWORD *)(v11 + 112));
              v14 = L"-";
              v15 = L"-";
              if ( v37 )
                v15 = v36;
              if ( BYTE4(a8) )
              {
                v16 = KerberosCryptoPolicy::ETypeToString(v44, (unsigned int)a8);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                  v32,
                  v16);
                LOBYTE(v33) = 1;
                utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v44);
              }
              else
              {
                memset(v32, 0, sizeof(v32));
                v33 = 0;
              }
              if ( a2 )
              {
                v17 = a2 - 1;
                if ( v17 )
                {
                  v18 = v17 - 1;
                  if ( v18 )
                  {
                    if ( v18 == 1 && (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 0x20) != 0 )
                    {
                      if ( v24 )
                        v14 = v23;
                      McTemplateU0zzzzzkzzzzzzhz_EtwEventWriteTransfer(
                        *(_QWORD *)(v39 + 24),
                        (unsigned int)KdcAuditBlockTargetInsecureKeys,
                        v28,
                        v30,
                        *(_QWORD *)(v43 + 8),
                        *(_QWORD *)(v43 + 24),
                        *(_QWORD *)(a4 + 8),
                        (__int64)Sid,
                        *(_QWORD *)(v41 + 8),
                        *(_QWORD *)(v41 + 24),
                        *(_QWORD *)(v39 + 8),
                        (__int64)v14,
                        *(_QWORD *)(v39 + 24),
                        (__int64)v48,
                        v49,
                        (__int64)v15);
                    }
                  }
                  else if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 0x10) != 0 )
                  {
                    v19 = L"-";
                    if ( (_BYTE)v33 )
                      v19 = *(const wchar_t **)&v32[0];
                    if ( v24 )
                      v14 = v23;
                    McTemplateU0zzzzzkzzzzzzhzz_EtwEventWriteTransfer(
                      *(_QWORD *)(v39 + 24),
                      (unsigned int)KdcAuditWarnTargetInsecureKeys,
                      v28,
                      v30,
                      *(_QWORD *)(v43 + 8),
                      *(_QWORD *)(v43 + 24),
                      *(_QWORD *)(a4 + 8),
                      (__int64)Sid,
                      *(_QWORD *)(v41 + 8),
                      *(_QWORD *)(v41 + 24),
                      *(_QWORD *)(v39 + 8),
                      (__int64)v14,
                      *(_QWORD *)(v39 + 24),
                      (__int64)v48,
                      v49,
                      (__int64)v15,
                      (__int64)v19);
                  }
                }
                else if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 0x20) != 0 )
                {
                  if ( v24 )
                    v14 = v23;
                  McTemplateU0zzzzzkzzzzzzhz_EtwEventWriteTransfer(
                    *(_QWORD *)(v39 + 24),
                    (unsigned int)KdcAuditBlockedETypeAdvertizementByClient,
                    v28,
                    v30,
                    *(_QWORD *)(v43 + 8),
                    *(_QWORD *)(v43 + 24),
                    *(_QWORD *)(a4 + 8),
                    (__int64)Sid,
                    *(_QWORD *)(v41 + 8),
                    *(_QWORD *)(v41 + 24),
                    *(_QWORD *)(v39 + 8),
                    (__int64)v14,
                    *(_QWORD *)(v39 + 24),
                    (__int64)v48,
                    v49,
                    (__int64)v15);
                }
              }
              else if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 0x10) != 0 )
              {
                v20 = L"-";
                if ( (_BYTE)v33 )
                  v20 = *(const wchar_t **)&v32[0];
                if ( v24 )
                  v14 = v23;
                McTemplateU0zzzzzkzzzzzzhzz_EtwEventWriteTransfer(
                  *(_QWORD *)(v39 + 24),
                  (unsigned int)KdcAuditWarnETypeAdvertizementByClient,
                  v28,
                  v30,
                  *(_QWORD *)(v43 + 8),
                  *(_QWORD *)(v43 + 24),
                  *(_QWORD *)(a4 + 8),
                  (__int64)Sid,
                  *(_QWORD *)(v41 + 8),
                  *(_QWORD *)(v41 + 24),
                  *(_QWORD *)(v39 + 8),
                  (__int64)v14,
                  *(_QWORD *)(v39 + 24),
                  (__int64)v48,
                  v49,
                  (__int64)v15,
                  (__int64)v20);
              }
              utl::_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>::~_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(v32);
              utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(v35);
              utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(v22);
            }
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v38);
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v40);
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v42);
          }
        }
      }
    }
    LODWORD(v12) = utl::pair<utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>>::~pair<utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>>(v27);
  }
  return v12;
}

```

## disassembly

```asm
0x18006afcc  mov     [rsp-8+arg_0], rbx
0x18006afd1  push    rbp
0x18006afd2  push    rsi
0x18006afd3  push    rdi
0x18006afd4  push    r12
0x18006afd6  push    r13
0x18006afd8  push    r14
0x18006afda  push    r15
0x18006afdc  lea     rbp, [rsp-2B0h]
0x18006afe4  sub     rsp, 3C0h
0x18006afeb  mov     rax, cs:__security_cookie
0x18006aff2  xor     rax, rsp
0x18006aff5  mov     [rbp+2E0h+var_40], rax
0x18006affc  mov     r13, r9
0x18006afff  mov     rsi, r8
0x18006b002  mov     ebx, edx
0x18006b004  mov     r14, [rbp+2E0h+arg_30]
0x18006b00b  mov     r15, [rbp+2E0h+arg_28]
0x18006b012  mov     r12, [rbp+2E0h+arg_20]
0x18006b019  cmp     byte ptr [rcx+18h], 0
0x18006b01d  jnz     short loc_18006B024
0x18006b01f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b024  mov     rdi, [rsi]
0x18006b027  mov     rax, [rsi+8]
0x18006b02b  mov     [rbp+2E0h+var_348], rax
0x18006b02f  xor     esi, esi
0x18006b031  test    rdi, rdi
0x18006b034  jz      short loc_18006B04B
0x18006b036  test    rax, rax
0x18006b039  jz      short loc_18006B04B
0x18006b03b  cmp     [r12], rsi
0x18006b03f  jz      short loc_18006B04B
0x18006b041  cmp     [r15], rsi
0x18006b044  jz      short loc_18006B04B
0x18006b046  cmp     [r14], rsi
0x18006b049  jnz     short loc_18006B05D
0x18006b04b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b050  test    rdi, rdi
0x18006b053  jz      loc_18006B4B0
0x18006b059  mov     rax, [rbp+2E0h+var_348]
0x18006b05d  test    rax, rax
0x18006b060  jz      loc_18006B4B0
0x18006b066  cmp     [r12], rsi
0x18006b06a  jz      loc_18006B4B0
0x18006b070  cmp     [r15], rsi
0x18006b073  jz      loc_18006B4B0
0x18006b079  cmp     [r14], rsi
0x18006b07c  jz      loc_18006B4B0
0x18006b082  lea     rax, [rbp+2E0h+var_348]
0x18006b086  mov     [rbp+2E0h+var_2E0], rax
0x18006b08a  lea     rdx, [rbp+2E0h+var_338]
0x18006b08e  lea     rcx, [rbp+2E0h+var_2E0]
0x18006b092  call    _lambda_e64b62a3704c3b288d98d26c75f0ec9e___operator__
0x18006b097  cmp     [rbp+2E0h+var_328], sil
0x18006b09b  jz      loc_18006B4A6
0x18006b0a1  cmp     [rbp+2E0h+var_310], sil
0x18006b0a5  jz      loc_18006B4A6
0x18006b0ab  xor     edx, edx; Val
0x18006b0ad  lea     r8d, [rdx+48h]; Size
0x18006b0b1  lea     rcx, [rbp+2E0h+Sid]; void *
0x18006b0b8  call    memset_0
0x18006b0bd  mov     edx, [r13+30h]; unsigned int
0x18006b0c1  lea     rcx, [rbp+2E0h+Sid]; Sid
0x18006b0c8  call    ?KdcMakeAccountSid@@YAXPEAXK@Z; KdcMakeAccountSid(void *,ulong)
0x18006b0cd  mov     ecx, cs:?s_tlsIndex@KdcThreadContext@@0KA; dwTlsIndex
0x18006b0d3  call    cs:__imp_TlsGetValue
0x18006b0d9  test    rax, rax
0x18006b0dc  jz      loc_18006B4A6
0x18006b0e2  cmp     [rax+8], sil
0x18006b0e6  jz      loc_18006B4A6
0x18006b0ec  lea     rdx, [rbp+2E0h+var_180]
0x18006b0f3  mov     rcx, rax
0x18006b0f6  call    ?GetNetworkInfo@KdcThreadContext@@QEBA?AV?$expected@UKdcNetworkInfo@KdcThreadContext@@J@utl@@XZ; KdcThreadContext::GetNetworkInfo(void)
0x18006b0fb  mov     [rbp+2E0h+var_1F0], 2Dh ; '-'
0x18006b105  xor     edx, edx; Val
0x18006b107  lea     r8d, [rdx+6Ch]; Size
0x18006b10b  lea     rcx, [rbp+2E0h+var_1EC]; void *
0x18006b112  call    memset_0
0x18006b117  lea     r8, [rbp+2E0h+var_1F0]
0x18006b11e  lea     rdx, [rbp+2E0h+var_B0]
0x18006b125  lea     rcx, [rbp+2E0h+var_180]
0x18006b12c  call    ??$value_or@UKdcNetworkInfo@KdcThreadContext@@@?$expected@UKdcNetworkInfo@KdcThreadContext@@J@utl@@QEGBA?AUKdcNetworkInfo@KdcThreadContext@@$$QEAU23@@Z; utl::expected<KdcThreadContext::KdcNetworkInfo,long>::value_or<KdcThreadContext::KdcNetworkInfo>(KdcThreadContext::KdcNetworkInfo &&)
0x18006b131  mov     rdx, r12
0x18006b134  lea     rcx, [rbp+2E0h+var_250]
0x18006b13b  call    ??0KdcEventPrincipal@@QEAA@AEBV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@@Z; KdcEventPrincipal::KdcEventPrincipal(utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &)
0x18006b140  mov     rdx, r15
0x18006b143  lea     rcx, [rbp+2E0h+var_288]
0x18006b147  call    ??0KdcEventPrincipal@@QEAA@AEBV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@@Z; KdcEventPrincipal::KdcEventPrincipal(utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &)
0x18006b14c  mov     rdx, r14
0x18006b14f  lea     rcx, [rbp+2E0h+var_2C0]
0x18006b153  call    ??0KdcEventPrincipal@@QEAA@AEBV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@@Z; KdcEventPrincipal::KdcEventPrincipal(utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>> const &)
0x18006b158  mov     rax, [r14]
0x18006b15b  mov     rcx, [rax]
0x18006b15e  mov     rax, [rcx]
0x18006b161  lea     rdx, [rbp+2E0h+var_340]
0x18006b165  mov     rax, [rax+0E8h]
0x18006b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b171  cmp     [rbp+2E0h+var_33C], esi
0x18006b174  jl      loc_18006B488
0x18006b17a  mov     edx, [rbp+2E0h+var_340]
0x18006b17d  lea     rcx, [rbp+2E0h+var_360]
0x18006b181  call    ?BitmaskToString@KerberosCryptoPolicy@@SA?AV?$optional@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@@utl@@I@Z; KerberosCryptoPolicy::BitmaskToString(uint)
0x18006b186  mov     rdx, [rdi+70h]
0x18006b18a  lea     rcx, [rbp+2E0h+var_2D8]
0x18006b18e  call    ?EtypeListToString@KerberosCryptoPolicy@@SA?AV?$optional@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@@utl@@PEBUKERB_KDC_REQUEST_BODY_encryption_type_s@@@Z; KerberosCryptoPolicy::EtypeListToString(KERB_KDC_REQUEST_BODY_encryption_type_s const *)
0x18006b193  lea     rdi, asc_1800A2C88; "-"
0x18006b19a  mov     rsi, rdi
0x18006b19d  xor     r14d, r14d
0x18006b1a0  cmp     [rbp+2E0h+var_2C8], r14b
0x18006b1a4  cmovnz  rsi, [rbp+2E0h+var_2D0]
0x18006b1a9  cmp     [rbp+2E0h+arg_3C], r14b
0x18006b1b0  jz      short loc_18006B1E2
0x18006b1b2  mov     edx, [rbp+2E0h+arg_38]
0x18006b1b8  lea     rcx, [rbp+2E0h+var_218]
0x18006b1bf  call    ?ETypeToString@KerberosCryptoPolicy@@SA?AV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@J@Z; KerberosCryptoPolicy::ETypeToString(long)
0x18006b1c4  mov     rdx, rax
0x18006b1c7  lea     rcx, [rbp+2E0h+var_308]
0x18006b1cb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18006b1d0  mov     byte ptr [rbp+2E0h+var_2E8], 1
0x18006b1d4  lea     rcx, [rbp+2E0h+var_218]
0x18006b1db  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006b1e0  jmp     short loc_18006B1F3
0x18006b1e2  xorps   xmm0, xmm0
0x18006b1e5  xor     eax, eax
0x18006b1e7  movups  [rbp+2E0h+var_308], xmm0
0x18006b1eb  movups  [rbp+2E0h+var_2F8], xmm0
0x18006b1ef  mov     [rbp+2E0h+var_2E8], rax
0x18006b1f3  test    ebx, ebx
0x18006b1f5  jz      loc_18006B3B0
0x18006b1fb  sub     ebx, 1
0x18006b1fe  jz      loc_18006B302
0x18006b204  sub     ebx, 1
0x18006b207  jz      short loc_18006B280
0x18006b209  cmp     ebx, 1
0x18006b20c  jnz     loc_18006B46D
0x18006b212  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, 20h
0x18006b219  jz      loc_18006B46D
0x18006b21f  mov     r8, [rbp+2E0h+var_290]
0x18006b223  mov     rcx, [r8+18h]
0x18006b227  cmp     [rbp+2E0h+var_350], r14b
0x18006b22b  cmovnz  rdi, [rbp+2E0h+var_358]
0x18006b230  mov     rdx, [rbp+2E0h+var_258]
0x18006b237  mov     [rsp+3F0h+var_378], rsi
0x18006b23c  movzx   eax, [rbp+2E0h+var_42]
0x18006b243  mov     [rsp+3F0h+var_380], ax
0x18006b248  lea     rax, [rbp+2E0h+var_B0]
0x18006b24f  mov     [rsp+3F0h+var_388], rax
0x18006b254  mov     [rsp+3F0h+var_390], rcx
0x18006b259  mov     [rsp+3F0h+var_398], rdi
0x18006b25e  mov     rax, [r8+8]
0x18006b262  mov     [rsp+3F0h+var_3A0], rax
0x18006b267  mov     rax, [rdx+18h]
0x18006b26b  mov     [rsp+3F0h+var_3A8], rax
0x18006b270  mov     rax, [rdx+8]
0x18006b274  lea     rdx, KdcAuditBlockTargetInsecureKeys
0x18006b27b  jmp     loc_18006B36B
0x18006b280  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, 10h
0x18006b287  jz      loc_18006B46D
0x18006b28d  mov     rax, rdi
0x18006b290  cmp     byte ptr [rbp+2E0h+var_2E8], r14b
0x18006b294  cmovnz  rax, qword ptr [rbp+2E0h+var_308]
0x18006b299  mov     r8, [rbp+2E0h+var_290]
0x18006b29d  mov     rcx, [r8+18h]
0x18006b2a1  cmp     [rbp+2E0h+var_350], r14b
0x18006b2a5  cmovnz  rdi, [rbp+2E0h+var_358]
0x18006b2aa  mov     rdx, [rbp+2E0h+var_258]
0x18006b2b1  mov     [rsp+3F0h+var_370], rax
0x18006b2b9  mov     [rsp+3F0h+var_378], rsi
0x18006b2be  movzx   eax, [rbp+2E0h+var_42]
0x18006b2c5  mov     [rsp+3F0h+var_380], ax
0x18006b2ca  lea     rax, [rbp+2E0h+var_B0]
0x18006b2d1  mov     [rsp+3F0h+var_388], rax
0x18006b2d6  mov     [rsp+3F0h+var_390], rcx
0x18006b2db  mov     [rsp+3F0h+var_398], rdi
0x18006b2e0  mov     rax, [r8+8]
0x18006b2e4  mov     [rsp+3F0h+var_3A0], rax
0x18006b2e9  mov     rax, [rdx+18h]
0x18006b2ed  mov     [rsp+3F0h+var_3A8], rax
0x18006b2f2  mov     rax, [rdx+8]
0x18006b2f6  lea     rdx, KdcAuditWarnTargetInsecureKeys
0x18006b2fd  jmp     loc_18006B42D
0x18006b302  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, 20h
0x18006b309  jz      loc_18006B46D
0x18006b30f  mov     r8, [rbp+2E0h+var_290]
0x18006b313  mov     rcx, [r8+18h]
0x18006b317  cmp     [rbp+2E0h+var_350], r14b
0x18006b31b  cmovnz  rdi, [rbp+2E0h+var_358]
0x18006b320  mov     rdx, [rbp+2E0h+var_258]
0x18006b327  mov     [rsp+3F0h+var_378], rsi
0x18006b32c  movzx   eax, [rbp+2E0h+var_42]
0x18006b333  mov     [rsp+3F0h+var_380], ax
0x18006b338  lea     rax, [rbp+2E0h+var_B0]
0x18006b33f  mov     [rsp+3F0h+var_388], rax
0x18006b344  mov     [rsp+3F0h+var_390], rcx
0x18006b349  mov     [rsp+3F0h+var_398], rdi
0x18006b34e  mov     rax, [r8+8]
0x18006b352  mov     [rsp+3F0h+var_3A0], rax
0x18006b357  mov     rax, [rdx+18h]
0x18006b35b  mov     [rsp+3F0h+var_3A8], rax
0x18006b360  mov     rax, [rdx+8]
0x18006b364  lea     rdx, KdcAuditBlockedETypeAdvertizementByClient
0x18006b36b  mov     [rsp+3F0h+var_3B0], rax
0x18006b370  lea     rax, [rbp+2E0h+Sid]
0x18006b377  mov     [rsp+3F0h+var_3B8], rax
0x18006b37c  mov     rax, [r13+8]
0x18006b380  mov     [rsp+3F0h+var_3C0], rax
0x18006b385  mov     r9, [rbp+2E0h+var_220]
0x18006b38c  mov     rax, [r9+18h]
0x18006b390  mov     [rsp+3F0h+var_3C8], rax
0x18006b395  mov     rax, [r9+8]
0x18006b399  mov     r8, [rbp+2E0h+var_330]
0x18006b39d  mov     r9, [rbp+2E0h+var_318]
0x18006b3a1  mov     [rsp+3F0h+var_3D0], rax
0x18006b3a6  call    McTemplateU0zzzzzkzzzzzzhz_EtwEventWriteTransfer
0x18006b3ab  jmp     loc_18006B46D
0x18006b3b0  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, 10h
0x18006b3b7  jz      loc_18006B46D
0x18006b3bd  mov     rax, rdi
0x18006b3c0  cmp     byte ptr [rbp+2E0h+var_2E8], r14b
0x18006b3c4  cmovnz  rax, qword ptr [rbp+2E0h+var_308]
0x18006b3c9  mov     r8, [rbp+2E0h+var_290]
0x18006b3cd  mov     rcx, [r8+18h]
0x18006b3d1  cmp     [rbp+2E0h+var_350], r14b
0x18006b3d5  cmovnz  rdi, [rbp+2E0h+var_358]
0x18006b3da  mov     rdx, [rbp+2E0h+var_258]
0x18006b3e1  mov     [rsp+3F0h+var_370], rax
0x18006b3e9  mov     [rsp+3F0h+var_378], rsi
0x18006b3ee  movzx   eax, [rbp+2E0h+var_42]
0x18006b3f5  mov     [rsp+3F0h+var_380], ax
0x18006b3fa  lea     rax, [rbp+2E0h+var_B0]
0x18006b401  mov     [rsp+3F0h+var_388], rax
0x18006b406  mov     [rsp+3F0h+var_390], rcx
0x18006b40b  mov     [rsp+3F0h+var_398], rdi
0x18006b410  mov     rax, [r8+8]
0x18006b414  mov     [rsp+3F0h+var_3A0], rax
0x18006b419  mov     rax, [rdx+18h]
0x18006b41d  mov     [rsp+3F0h+var_3A8], rax
0x18006b422  mov     rax, [rdx+8]
0x18006b426  lea     rdx, KdcAuditWarnETypeAdvertizementByClient
0x18006b42d  mov     [rsp+3F0h+var_3B0], rax
0x18006b432  lea     rax, [rbp+2E0h+Sid]
0x18006b439  mov     [rsp+3F0h+var_3B8], rax
0x18006b43e  mov     rax, [r13+8]
0x18006b442  mov     [rsp+3F0h+var_3C0], rax
0x18006b447  mov     r9, [rbp+2E0h+var_220]
0x18006b44e  mov     rax, [r9+18h]
0x18006b452  mov     [rsp+3F0h+var_3C8], rax
0x18006b457  mov     rax, [r9+8]
0x18006b45b  mov     [rsp+3F0h+var_3D0], rax
0x18006b460  mov     r9, [rbp+2E0h+var_318]
0x18006b464  mov     r8, [rbp+2E0h+var_330]
0x18006b468  call    McTemplateU0zzzzzkzzzzzzhzz_EtwEventWriteTransfer
0x18006b46d  lea     rcx, [rbp+2E0h+var_308]
0x18006b471  call    ??1?$_OptionalData1@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>::~_OptionalData1<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(void)
0x18006b476  lea     rcx, [rbp+2E0h+var_2D8]
0x18006b47a  call    ??1?$_OptionalData1@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(void)
0x18006b47f  lea     rcx, [rbp+2E0h+var_360]
0x18006b483  call    ??1?$_OptionalData1@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(void)
0x18006b488  lea     rcx, [rbp+2E0h+var_2C0]; this
0x18006b48c  call    ??1KdcEventPrincipal@@QEAA@XZ; KdcEventPrincipal::~KdcEventPrincipal(void)
0x18006b491  lea     rcx, [rbp+2E0h+var_288]; this
0x18006b495  call    ??1KdcEventPrincipal@@QEAA@XZ; KdcEventPrincipal::~KdcEventPrincipal(void)
0x18006b49a  lea     rcx, [rbp+2E0h+var_250]; this
0x18006b4a1  call    ??1KdcEventPrincipal@@QEAA@XZ; KdcEventPrincipal::~KdcEventPrincipal(void)
0x18006b4a6  lea     rcx, [rbp+2E0h+var_338]
0x18006b4aa  call    ??1?$pair@V?$optional@V?$unique_struct@U_UNICODE_STRING@@$$A6AXPEAU1@@Z$1?KerbFreeString@@YAX0@Z$$T$0A@@wil@@@utl@@V12@@utl@@QEAA@XZ; utl::pair<utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>>::~pair<utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::optional<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>>>(void)
0x18006b4af  nop
0x18006b4b0  mov     rcx, [rbp+2E0h+var_40]
0x18006b4b7  xor     rcx, rsp; StackCookie
0x18006b4ba  call    __security_check_cookie
0x18006b4bf  mov     rbx, [rsp+3F0h+arg_0]
0x18006b4c7  add     rsp, 3C0h
0x18006b4ce  pop     r15
0x18006b4d0  pop     r14
0x18006b4d2  pop     r13
0x18006b4d4  pop     r12
0x18006b4d6  pop     rdi
0x18006b4d7  pop     rsi
0x18006b4d8  pop     rbp
0x18006b4d9  retn
```
