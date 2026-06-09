# ModelPackageManager::IsTextRecognizerAvailable(void)

- ea: `0x180075c1c`
- end: `0x180075daf`
- name: `?IsTextRecognizerAvailable@ModelPackageManager@@SA_NXZ`
- size: `403`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c780`
- `0x18001d130`
- `0x180077c10`

## callees

- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18004dea8`
- `0x180074794`
- `0x180075c1c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075d49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075d49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075c59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075d1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075c59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075d1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d75`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char ModelPackageManager::IsTextRecognizerAvailable(void)
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx
  int v1; // eax
  char v2; // si
  _DWORD *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  const char *v6; // r9
  char result; // al
  int v8; // [rsp+20h] [rbp-68h] BYREF
  __int128 v9; // [rsp+28h] [rbp-60h]
  _BYTE v10[8]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v11[48]; // [rsp+48h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 (__fastcall *v14)(__int64 *); // [rsp+90h] [rbp+8h] BYREF
  __int64 *v15; // [rsp+98h] [rbp+10h]

  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v10);
  v0 = (struct _RTL_CRITICAL_SECTION *)pv;
  v14 = (__int64 (__fastcall *)(__int64 *))pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v0 + 5);
  ++LODWORD(v0[6].DebugInfo);
  LODWORD(v0[6].SpinCount) = 24;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v14);
  try
  {
    v15 = &qword_1800AF898;
    _InterlockedIncrement64(&qword_1800AF898);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> )
    {
      LOBYTE(v14) = 0;
      v8 = 0;
      v9 = 0;
      v1 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall **)(__int64 *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
                                                                                  + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>,
             &v14);
      if ( v1 < 0 )
        winrt::throw_hresult((unsigned int)v1, &v8);
      v2 = (char)v14;
      _InterlockedDecrement64(&qword_1800AF898);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF898);
      v14 = (__int64 (__fastcall *)(__int64 *))winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK;
      v2 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::call<bool (*)(winrt::Microsoft::Windows::Vision::ITextRecognizerStatics const &)>(
             0,
             &v14);
    }
    v3 = pv;
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v3[18] |= 0x300u;
    if ( *((_QWORD *)v3 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(v3 + 2), 2);
    if ( v4 )
      LeaveCriticalSection(v4);
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v5);
      CoTaskMemFree(v5);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v11);
    result = v2;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180075c1c  mov     [rsp+arg_10], rbx
0x180075c21  mov     [rsp+arg_18], rsi
0x180075c26  push    rdi
0x180075c27  sub     rsp, 80h
0x180075c2e  lea     rcx, [rsp+88h+var_48]
0x180075c33  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180075c38  nop
0x180075c39  mov     rbx, [rsp+88h+pv]
0x180075c3e  mov     [rsp+88h+arg_0], rbx
0x180075c46  test    rbx, rbx
0x180075c49  jz      short loc_180075C52
0x180075c4b  lock inc dword ptr [rbx+120h]
0x180075c52  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180075c59  call    cs:__imp_EnterCriticalSection
0x180075c5f  inc     dword ptr [rbx+0F0h]
0x180075c65  mov     dword ptr [rbx+110h], 18h
0x180075c6f  lea     rcx, [rsp+88h+arg_0]
0x180075c77  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180075c7c  lea     rax, qword_1800AF898
0x180075c83  mov     [rsp+88h+arg_8], rax
0x180075c8b  lock inc cs:qword_1800AF898
0x180075c93  mov     rcx, cs:??$factory_cache_entry_v@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Vision::TextRecognizer,winrt::Microsoft::Windows::Vision::ITextRecognizerStatics>
0x180075c9a  test    rcx, rcx
0x180075c9d  jz      short loc_180075CE6
0x180075c9f  mov     byte ptr [rsp+88h+arg_0], 0
0x180075ca7  mov     [rsp+88h+var_68], 0
0x180075caf  xorps   xmm0, xmm0
0x180075cb2  movdqu  [rsp+88h+var_60], xmm0
0x180075cb8  mov     rax, [rcx]
0x180075cbb  lea     rdx, [rsp+88h+arg_0]
0x180075cc3  mov     rax, [rax+30h]
0x180075cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ccc  test    eax, eax
0x180075cce  js      loc_180075DA1
0x180075cd4  mov     sil, byte ptr [rsp+88h+arg_0]
0x180075cdc  lock dec cs:qword_1800AF898
0x180075ce4  jmp     short loc_180075D0D
0x180075ce6  lock dec cs:qword_1800AF898
0x180075cee  lea     rax, ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180075cf5  mov     [rsp+88h+arg_0], rax
0x180075cfd  lea     rdx, [rsp+88h+arg_0]
0x180075d05  call    ??$call@P6A_NAEBUITextRecognizerStatics@Vision@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UTextRecognizer@Vision@Windows@Microsoft@winrt@@UITextRecognizerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUITextRecognizerStatics@Vision@Windows@Microsoft@2@@Z@Z
0x180075d0a  mov     sil, al
0x180075d0d  mov     rbx, [rsp+88h+pv]
0x180075d12  lea     rdi, [rbx+0C8h]
0x180075d19  mov     rcx, rdi; lpCriticalSection
0x180075d1c  call    cs:__imp_EnterCriticalSection
0x180075d22  or      dword ptr [rbx+48h], 300h
0x180075d29  cmp     qword ptr [rbx+0F8h], 0
0x180075d31  jz      short loc_180075D41
0x180075d33  mov     edx, 2
0x180075d38  lea     rcx, [rbx+8]
0x180075d3c  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180075d41  test    rdi, rdi
0x180075d44  jz      short loc_180075D50
0x180075d46  mov     rcx, rdi; lpCriticalSection
0x180075d49  call    cs:__imp_LeaveCriticalSection
0x180075d4f  nop
0x180075d50  mov     rbx, [rsp+88h+pv]
0x180075d55  test    rbx, rbx
0x180075d58  jz      short loc_180075D7B
0x180075d5a  or      edx, 0FFFFFFFFh
0x180075d5d  lock xadd [rbx+120h], edx
0x180075d65  cmp     edx, 1
0x180075d68  jnz     short loc_180075D7B
0x180075d6a  mov     rcx, rbx
0x180075d6d  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180075d72  mov     rcx, rbx; pv
0x180075d75  call    cs:__imp_CoTaskMemFree
0x180075d7b  lea     rcx, [rsp+88h+var_40]; this
0x180075d80  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180075d85  mov     al, sil
0x180075d88  jmp     short loc_180075D8C
0x180075d8a  xor     al, al
0x180075d8c  lea     r11, [rsp+88h+var_8]
0x180075d94  mov     rbx, [r11+20h]
0x180075d98  mov     rsi, [r11+28h]
0x180075d9c  mov     rsp, r11
0x180075d9f  pop     rdi
0x180075da0  retn
0x180075da1  lea     rdx, [rsp+88h+var_68]
0x180075da6  mov     ecx, eax
0x180075da8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
