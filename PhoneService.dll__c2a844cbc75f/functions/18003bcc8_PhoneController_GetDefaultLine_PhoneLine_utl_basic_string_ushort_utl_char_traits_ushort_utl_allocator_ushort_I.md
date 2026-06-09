# PhoneController::_GetDefaultLine(PhoneLine * *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,ISecurityToken *)

- ea: `0x18003bcc8`
- end: `0x18003bfda`
- name: `?_GetDefaultLine@PhoneController@@IEAAJPEAPEAVPhoneLine@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAUISecurityToken@@@Z`
- size: `786`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180028760`
- `0x18002c0b0`
- `0x18002c2a0`
- `0x18003c7d8`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x18000e1a4`
- `0x1800272c8`
- `0x18002c574`
- `0x18002c580`
- `0x18003bcc8`
- `0x180051ca4`
- `0x18006df58`
- `0x180070bb0`
- `0x18007f9ec`
- `0x18008d936`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bcf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bd1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bcf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bd1c`
- `PhoneUtil!StringToPhoneLineId` at `0x18003bdbe`
- `PhoneUtil!StringToPhoneLineId` at `0x18003bdbe`

## string_xrefs

- `0x18003bcff`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003bf0c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003bf82`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_GetDefaultLine(
        __int64 a1,
        PhoneLine **a2,
        const unsigned __int16 **a3,
        struct ISecurityToken *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // r9
  void *v14; // rcx
  bool v15; // zf
  int v16; // eax
  BackTraceCollection *v17; // rcx
  __int64 v18; // rcx
  int AllPhoneLines; // eax
  BackTraceCollection *v20; // rcx
  PhoneLine **v21; // rdi
  PhoneLine *v22; // rbx
  PhoneLine *v23; // rsi
  const unsigned __int16 *v24; // rdx
  int v25; // eax
  BackTraceCollection *v26; // rcx
  unsigned int v27; // edi
  __int128 Buf1; // [rsp+30h] [rbp-39h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-29h] BYREF
  __int16 v31; // [rsp+50h] [rbp-19h] BYREF
  __int64 v32; // [rsp+52h] [rbp-17h]
  int v33; // [rsp+5Ah] [rbp-Fh]
  __int16 v34; // [rsp+5Eh] [rbp-Bh]
  __m128i si128; // [rsp+60h] [rbp-9h] BYREF
  __int64 v36; // [rsp+70h] [rbp+7h]
  GUID Buf2; // [rsp+78h] [rbp+Fh] BYREF

  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 681);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *a2 = 0;
  v9 = *(_QWORD *)(a1 + 488);
  v34 = 0;
  v32 = 0;
  Block[0] = &v31;
  Block[1] = &v31;
  v31 = 0;
  v33 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  v10 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Get(
          v9 + 1696,
          Block);
  v12 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    v13 = 690;
LABEL_6:
    Log_HREvent_7(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v13);
LABEL_7:
    v14 = Block[0];
    v15 = Block[0] == &v31;
LABEL_37:
    if ( !v15 )
      operator delete(v14);
    return v12;
  }
  v16 = StringToPhoneLineId(Block[0], &Buf2);
  v12 = v16;
  if ( v16 < 0 )
  {
    BackTraceCollection::Capture(v17, v16);
    v13 = 691;
    goto LABEL_6;
  }
  v18 = *(_QWORD *)(a1 + 152);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v36 = -1;
  AllPhoneLines = PhoneLineStorage::GetAllPhoneLines(v18, &si128, a4);
  v12 = AllPhoneLines;
  if ( AllPhoneLines < 0 )
  {
    BackTraceCollection::Capture(v20, AllPhoneLines);
    Log_HREvent_7(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 696);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    goto LABEL_7;
  }
  v21 = (PhoneLine **)si128.m128i_i64[0];
  v22 = 0;
  while ( v21 != (PhoneLine **)si128.m128i_i64[1] )
  {
    if ( !v22 || (Buf1 = *(_OWORD *)((char *)*v21 + 88), !memcmp_0(&Buf1, &Buf2, 0x10u)) )
    {
      if ( (PhoneLine::GetCapabilities(*v21) & 1) != 0 )
      {
        v23 = *v21;
        Buf1 = *((_OWORD *)*v21 + 7);
        if ( memcmp_0(&Buf1, VoipLineType, 0x10u) )
        {
          if ( v22 != v23 )
          {
            if ( v23 )
              (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)v23 + 8LL))(v23);
            if ( v22 )
              (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)v22 + 16LL))(v22);
            v22 = v23;
          }
        }
      }
    }
    ++v21;
  }
  if ( !v22 )
  {
    v12 = -2147023728;
    Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 725);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    v14 = Block[0];
    v15 = Block[0] == &v31;
    goto LABEL_37;
  }
  if ( a3 )
    v24 = *a3;
  else
    v24 = &qword_18009A460;
  v25 = PhoneLine::CheckOwnershipPolicy(v22, v24, a4);
  v27 = v25;
  if ( v25 >= 0 )
  {
    *a2 = v22;
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    if ( Block[0] != &v31 )
      operator delete(Block[0]);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v26, v25);
    Log_HREvent_7(v27, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 720);
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&si128);
    (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( Block[0] != &v31 )
      operator delete(Block[0]);
    return v27;
  }
}

```

## disassembly

```asm
0x18003bcc8  push    rbp
0x18003bcca  push    rbx
0x18003bccb  push    rsi
0x18003bccc  push    rdi
0x18003bccd  push    r12
0x18003bccf  push    r14
0x18003bcd1  push    r15
0x18003bcd3  lea     rbp, [rsp-27h]
0x18003bcd8  sub     rsp, 90h
0x18003bcdf  mov     rax, cs:__security_cookie
0x18003bce6  xor     rax, rsp
0x18003bce9  mov     [rbp+57h+var_38], rax
0x18003bced  mov     r12, r9
0x18003bcf0  mov     r14, r8
0x18003bcf3  mov     r15, rdx
0x18003bcf6  mov     rdi, rcx
0x18003bcf9  call    cs:__imp_GetCurrentThreadId
0x18003bcff  lea     rsi, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003bd06  cmp     [rdi+0F0h], eax
0x18003bd0c  jz      short loc_18003BD2F
0x18003bd0e  mov     r8d, 2A9h
0x18003bd14  mov     rdx, rsi
0x18003bd17  call    Log_AssertionEvent_3
0x18003bd1c  call    cs:__imp_GetCurrentThreadId
0x18003bd22  cmp     [rdi+0F0h], eax
0x18003bd28  jz      short loc_18003BD2F
0x18003bd2a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003bd2f  xor     eax, eax
0x18003bd31  mov     qword ptr [r15], 0
0x18003bd38  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003bd3f  mov     rcx, [rdi+1E8h]
0x18003bd46  lea     rdx, [rbp+57h+Block]
0x18003bd4a  mov     [rbp+57h+var_62], ax
0x18003bd4e  add     rcx, 6A0h
0x18003bd55  lea     rax, [rbp+57h+var_70]
0x18003bd59  mov     [rbp+57h+var_6E], 0
0x18003bd61  mov     [rbp+57h+Block], rax
0x18003bd65  lea     rax, [rbp+57h+var_70]
0x18003bd69  mov     [rbp+57h+var_78], rax
0x18003bd6d  xor     eax, eax
0x18003bd6f  mov     [rbp+57h+var_70], ax
0x18003bd73  mov     [rbp+57h+var_66], 0
0x18003bd7a  movdqu  [rbp+57h+Buf2], xmm0
0x18003bd7f  call    ?Get@?$ConfigValueWithDefault@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@@QEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ConfigValueWithDefault<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>::Get(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18003bd84  mov     ebx, eax
0x18003bd86  test    eax, eax
0x18003bd88  jns     short loc_18003BDB6
0x18003bd8a  mov     edx, eax; int
0x18003bd8c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003bd91  mov     r9d, 2B2h
0x18003bd97  mov     r8, rsi
0x18003bd9a  mov     edx, 1
0x18003bd9f  mov     ecx, ebx
0x18003bda1  call    Log_HREvent_7
0x18003bda6  mov     rcx, [rbp+57h+Block]
0x18003bdaa  lea     rax, [rbp+57h+var_70]
0x18003bdae  cmp     rcx, rax
0x18003bdb1  jmp     loc_18003BFAC
0x18003bdb6  mov     rcx, [rbp+57h+Block]
0x18003bdba  lea     rdx, [rbp+57h+Buf2]
0x18003bdbe  call    cs:__imp_StringToPhoneLineId
0x18003bdc4  mov     ebx, eax
0x18003bdc6  test    eax, eax
0x18003bdc8  jns     short loc_18003BDD9
0x18003bdca  mov     edx, eax; int
0x18003bdcc  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003bdd1  mov     r9d, 2B3h
0x18003bdd7  jmp     short loc_18003BD97
0x18003bdd9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003bde1  lea     rdx, [rbp+57h+var_60]
0x18003bde5  mov     rcx, [rdi+98h]
0x18003bdec  mov     r8, r12
0x18003bdef  movdqu  [rbp+57h+var_60], xmm0
0x18003bdf4  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFFh
0x18003bdfc  call    ?GetAllPhoneLines@PhoneLineStorage@@QEAAJPEAV?$vector@V?$CComPtr@VPhoneLine@@@ATL@@V?$allocator@V?$CComPtr@VPhoneLine@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetAllPhoneLines(utl::vector<ATL::CComPtr<PhoneLine>,utl::allocator<ATL::CComPtr<PhoneLine>>> *,ISecurityToken *)
0x18003be01  mov     ebx, eax
0x18003be03  test    eax, eax
0x18003be05  jns     short loc_18003BE31
0x18003be07  mov     edx, eax; int
0x18003be09  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003be0e  mov     r9d, 2B8h
0x18003be14  mov     r8, rsi
0x18003be17  mov     edx, 1
0x18003be1c  mov     ecx, ebx
0x18003be1e  call    Log_HREvent_7
0x18003be23  lea     rcx, [rbp+57h+var_60]
0x18003be27  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003be2c  jmp     loc_18003BDA6
0x18003be31  mov     rdi, qword ptr [rbp+57h+var_60]
0x18003be35  xor     ebx, ebx
0x18003be37  cmp     rdi, qword ptr [rbp+57h+var_60+8]
0x18003be3b  jz      loc_18003BED4
0x18003be41  test    rbx, rbx
0x18003be44  jz      short loc_18003BE69
0x18003be46  mov     rax, [rdi]
0x18003be49  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18003be4d  mov     r8d, 10h; Size
0x18003be53  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003be57  movups  xmm0, xmmword ptr [rax+58h]
0x18003be5b  movdqu  [rbp+57h+Buf1], xmm0
0x18003be60  call    memcmp_0
0x18003be65  test    eax, eax
0x18003be67  jnz     short loc_18003BECB
0x18003be69  mov     rcx, [rdi]
0x18003be6c  call    ?GetCapabilities@PhoneLine@@QEAA?AW4PhoneLineCapabilities@@XZ; PhoneLine::GetCapabilities(void)
0x18003be71  test    al, 1
0x18003be73  jz      short loc_18003BECB
0x18003be75  mov     rsi, [rdi]
0x18003be78  lea     rdx, VoipLineType; Buf2
0x18003be7f  mov     r8d, 10h; Size
0x18003be85  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003be89  movups  xmm0, xmmword ptr [rsi+70h]
0x18003be8d  movdqu  [rbp+57h+Buf1], xmm0
0x18003be92  call    memcmp_0
0x18003be97  test    eax, eax
0x18003be99  jz      short loc_18003BECB
0x18003be9b  cmp     rbx, rsi
0x18003be9e  jz      short loc_18003BECB
0x18003bea0  test    rsi, rsi
0x18003bea3  jz      short loc_18003BEB4
0x18003bea5  mov     rax, [rsi]
0x18003bea8  mov     rcx, rsi
0x18003beab  mov     rax, [rax+8]
0x18003beaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003beb4  test    rbx, rbx
0x18003beb7  jz      short loc_18003BEC8
0x18003beb9  mov     rax, [rbx]
0x18003bebc  mov     rcx, rbx
0x18003bebf  mov     rax, [rax+10h]
0x18003bec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bec8  mov     rbx, rsi
0x18003becb  add     rdi, 8
0x18003becf  jmp     loc_18003BE37
0x18003bed4  test    rbx, rbx
0x18003bed7  jz      loc_18003BF7D
0x18003bedd  test    r14, r14
0x18003bee0  jz      short loc_18003BEE7
0x18003bee2  mov     rdx, [r14]
0x18003bee5  jmp     short loc_18003BEEE
0x18003bee7  lea     rdx, qword_18009A460; unsigned __int16 *
0x18003beee  mov     r8, r12; struct ISecurityToken *
0x18003bef1  mov     rcx, rbx; this
0x18003bef4  call    ?CheckOwnershipPolicy@PhoneLine@@QEAAJPEBGPEAUISecurityToken@@@Z; PhoneLine::CheckOwnershipPolicy(ushort const *,ISecurityToken *)
0x18003bef9  mov     edi, eax
0x18003befb  test    eax, eax
0x18003befd  jns     short loc_18003BF54
0x18003beff  mov     edx, eax; int
0x18003bf01  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18003bf06  mov     r9d, 2D0h
0x18003bf0c  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003bf13  mov     edx, 1
0x18003bf18  mov     ecx, edi
0x18003bf1a  call    Log_HREvent_7
0x18003bf1f  lea     rcx, [rbp+57h+var_60]
0x18003bf23  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003bf28  mov     rcx, [rbx]
0x18003bf2b  mov     rax, [rcx+10h]
0x18003bf2f  mov     rcx, rbx
0x18003bf32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf37  mov     rcx, [rbp+57h+Block]; Block
0x18003bf3b  lea     rax, [rbp+57h+var_70]
0x18003bf3f  cmp     rcx, rax
0x18003bf42  jz      short loc_18003BF50
0x18003bf44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003bf4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bf50  mov     eax, edi
0x18003bf52  jmp     short loc_18003BFBC
0x18003bf54  lea     rcx, [rbp+57h+var_60]
0x18003bf58  mov     [r15], rbx
0x18003bf5b  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003bf60  mov     rcx, [rbp+57h+Block]; Block
0x18003bf64  lea     rax, [rbp+57h+var_70]
0x18003bf68  cmp     rcx, rax
0x18003bf6b  jz      short loc_18003BF79
0x18003bf6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003bf74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bf79  xor     eax, eax
0x18003bf7b  jmp     short loc_18003BFBC
0x18003bf7d  mov     ebx, 80070490h
0x18003bf82  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003bf89  mov     ecx, ebx
0x18003bf8b  mov     r9d, 2D5h
0x18003bf91  xor     edx, edx
0x18003bf93  call    Log_HREvent_7
0x18003bf98  lea     rcx, [rbp+57h+var_60]
0x18003bf9c  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18003bfa1  mov     rcx, [rbp+57h+Block]; Block
0x18003bfa5  lea     rdx, [rbp+57h+var_70]
0x18003bfa9  cmp     rcx, rdx
0x18003bfac  jz      short loc_18003BFBA
0x18003bfae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18003bfb5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003bfba  mov     eax, ebx
0x18003bfbc  mov     rcx, [rbp+57h+var_38]
0x18003bfc0  xor     rcx, rsp; StackCookie
0x18003bfc3  call    __security_check_cookie
0x18003bfc8  add     rsp, 90h
0x18003bfcf  pop     r15
0x18003bfd1  pop     r14
0x18003bfd3  pop     r12
0x18003bfd5  pop     rdi
0x18003bfd6  pop     rsi
0x18003bfd7  pop     rbx
0x18003bfd8  pop     rbp
0x18003bfd9  retn
```
