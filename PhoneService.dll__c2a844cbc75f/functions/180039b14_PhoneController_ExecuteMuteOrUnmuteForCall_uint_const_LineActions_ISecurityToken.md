# PhoneController::_ExecuteMuteOrUnmuteForCall(uint const &,LineActions,ISecurityToken *)

- ea: `0x180039b14`
- end: `0x180039d96`
- name: `?_ExecuteMuteOrUnmuteForCall@PhoneController@@IEAAJAEBIW4LineActions@@PEAUISecurityToken@@@Z`
- size: `642`
- prototype: `int __high(const unsigned int *, enum LineActions, struct ISecurityToken *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002c900`
- `0x180033a60`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x18002c574`
- `0x18002c580`
- `0x180039754`
- `0x180039b14`
- `0x18003b8c0`
- `0x18004ef10`
- `0x1800524c8`
- `0x18006df58`
- `0x180078b70`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039cb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039c98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039cb9`

## string_xrefs

- `0x180039b54`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039b8b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039c10`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039cad`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039cf6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180039d43`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_ExecuteMuteOrUnmuteForCall(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct ISecurityToken *a4)
{
  __int64 v8; // rcx
  CallInfo *v9; // rdi
  __int64 v11; // rcx
  CallInfo *v12; // rbx
  int ApplicationUserModelIdFromRpcClient; // eax
  BackTraceCollection *v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // r9
  int v17; // eax
  BackTraceCollection *v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  CallInfo *v21; // [rsp+30h] [rbp-39h] BYREF
  __int128 v22; // [rsp+38h] [rbp-31h] BYREF
  __int128 v23; // [rsp+48h] [rbp-21h]
  __int128 v24; // [rsp+58h] [rbp-11h]
  void *Block[2]; // [rsp+68h] [rbp-1h] BYREF
  __int16 v26; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+7Ah] [rbp+11h]
  int v28; // [rsp+82h] [rbp+19h]
  __int16 v29; // [rsp+86h] [rbp+1Dh]

  if ( a3 - 1 > 1 )
  {
    Log_AssertionEvent_3(a1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6623);
    __int2c();
  }
  v8 = *(_QWORD *)(a1 + 96);
  v21 = 0;
  PhoneCallStorage::FindCall(v8, &v21, a2, 0);
  v9 = v21;
  if ( !v21 )
  {
    Log_HREvent_7(2147943568LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6626);
    return 2147943568LL;
  }
  v21 = 0;
  CallInfo::GetPhoneLine(v9, &v21);
  v12 = v21;
  if ( a4 )
  {
    v27 = 0;
    v29 = 0;
    v28 = 0;
    Block[0] = &v26;
    Block[1] = &v26;
    v26 = 0;
    ApplicationUserModelIdFromRpcClient = PhoneController::_GetApplicationUserModelIdFromRpcClient(v11, Block);
    v15 = ApplicationUserModelIdFromRpcClient;
    if ( ApplicationUserModelIdFromRpcClient < 0 )
    {
      BackTraceCollection::Capture(v14, ApplicationUserModelIdFromRpcClient);
      v16 = 6634;
      goto LABEL_8;
    }
    v17 = PhoneLine::CheckOwnershipPolicy(v12, (const unsigned __int16 *)Block[0], a4);
    v15 = v17;
    if ( v17 < 0 )
    {
      BackTraceCollection::Capture(v18, v17);
      v16 = 6635;
LABEL_8:
      Log_HREvent_7(v15, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v16);
      if ( Block[0] != &v26 )
        operator delete(Block[0]);
      if ( !v12 )
        goto LABEL_28;
      goto LABEL_27;
    }
    if ( Block[0] != &v26 )
      operator delete(Block[0]);
  }
  if ( a3 == 1 )
  {
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v19, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6693);
      if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v22 = 0;
    v23 = 0;
    v24 = 0;
    CountCall((CallInfo *)((char *)v9 + 24), (struct PH_PHONE_CALL_COUNTS *)&v22);
    if ( !((_DWORD)v23 + HIDWORD(v23)) )
    {
      v15 = -2147020579;
      Log_HREvent_7(2147946717LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6644);
      if ( v12 )
        (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v12 + 16LL))(v12);
      goto LABEL_28;
    }
  }
  v20 = PhoneController::_ExecuteLineAction(a1, v12, a3);
  v15 = v20;
  if ( v20 < 0 )
    Log_HREvent_7((unsigned int)v20, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 6649);
  if ( !v12 )
    goto LABEL_28;
LABEL_27:
  (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_28:
  (*(void (__fastcall **)(CallInfo *))(*(_QWORD *)v9 + 16LL))(v9);
  return v15;
}

```

## disassembly

```asm
0x180039b14  push    rbp
0x180039b16  push    rbx
0x180039b17  push    rsi
0x180039b18  push    rdi
0x180039b19  push    r12
0x180039b1b  push    r14
0x180039b1d  push    r15
0x180039b1f  lea     rbp, [rsp-27h]
0x180039b24  sub     rsp, 90h
0x180039b2b  mov     rax, cs:__security_cookie
0x180039b32  xor     rax, rsp
0x180039b35  mov     [rbp+57h+var_38], rax
0x180039b39  lea     eax, [r8-1]
0x180039b3d  mov     r12, r9
0x180039b40  mov     r15d, r8d
0x180039b43  mov     rbx, rdx
0x180039b46  mov     r14, rcx
0x180039b49  cmp     eax, 1
0x180039b4c  jbe     short loc_180039B62
0x180039b4e  mov     r8d, 19DFh
0x180039b54  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039b5b  call    Log_AssertionEvent_3
0x180039b60  int     2Ch; Windows NT - assertion failure
0x180039b62  mov     rcx, [r14+60h]
0x180039b66  lea     rdx, [rbp+57h+var_90]
0x180039b6a  xor     r9d, r9d
0x180039b6d  mov     [rbp+57h+var_90], 0
0x180039b75  mov     r8, rbx
0x180039b78  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x180039b7d  mov     rdi, [rbp+57h+var_90]
0x180039b81  test    rdi, rdi
0x180039b84  jnz     short loc_180039BA8
0x180039b86  mov     ebx, 80070490h
0x180039b8b  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039b92  mov     ecx, ebx
0x180039b94  mov     r9d, 19E2h
0x180039b9a  xor     edx, edx
0x180039b9c  call    Log_HREvent_7
0x180039ba1  mov     eax, ebx
0x180039ba3  jmp     loc_180039D78
0x180039ba8  lea     rdx, [rbp+57h+var_90]; struct PhoneLine **
0x180039bac  mov     [rbp+57h+var_90], 0
0x180039bb4  mov     rcx, rdi; this
0x180039bb7  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180039bbc  mov     rbx, [rbp+57h+var_90]
0x180039bc0  test    r12, r12
0x180039bc3  jz      loc_180039C8E
0x180039bc9  xor     eax, eax
0x180039bcb  mov     [rbp+57h+var_46], 0
0x180039bd3  mov     [rbp+57h+var_3A], ax
0x180039bd7  lea     rdx, [rbp+57h+Block]
0x180039bdb  lea     rax, [rbp+57h+var_48]
0x180039bdf  mov     [rbp+57h+var_3E], 0
0x180039be6  mov     [rbp+57h+Block], rax
0x180039bea  lea     rax, [rbp+57h+var_48]
0x180039bee  mov     [rbp+57h+var_50], rax
0x180039bf2  xor     eax, eax
0x180039bf4  mov     [rbp+57h+var_48], ax
0x180039bf8  call    ?_GetApplicationUserModelIdFromRpcClient@PhoneController@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; PhoneController::_GetApplicationUserModelIdFromRpcClient(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180039bfd  mov     esi, eax
0x180039bff  test    eax, eax
0x180039c01  jns     short loc_180039C51
0x180039c03  mov     edx, eax; int
0x180039c05  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180039c0a  mov     r9d, 19EAh
0x180039c10  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039c17  mov     edx, 1
0x180039c1c  mov     ecx, esi
0x180039c1e  call    Log_HREvent_7
0x180039c23  mov     rcx, [rbp+57h+Block]; Block
0x180039c27  lea     rax, [rbp+57h+var_48]
0x180039c2b  cmp     rcx, rax
0x180039c2e  jz      short loc_180039C3C
0x180039c30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180039c37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039c3c  test    rbx, rbx
0x180039c3f  jz      loc_180039D67
0x180039c45  mov     rax, [rbx]
0x180039c48  mov     rax, [rax+10h]
0x180039c4c  jmp     loc_180039D5F
0x180039c51  mov     rdx, [rbp+57h+Block]; unsigned __int16 *
0x180039c55  mov     r8, r12; struct ISecurityToken *
0x180039c58  mov     rcx, rbx; this
0x180039c5b  call    ?CheckOwnershipPolicy@PhoneLine@@QEAAJPEBGPEAUISecurityToken@@@Z; PhoneLine::CheckOwnershipPolicy(ushort const *,ISecurityToken *)
0x180039c60  mov     esi, eax
0x180039c62  test    eax, eax
0x180039c64  jns     short loc_180039C75
0x180039c66  mov     edx, eax; int
0x180039c68  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180039c6d  mov     r9d, 19EBh
0x180039c73  jmp     short loc_180039C10
0x180039c75  mov     rcx, [rbp+57h+Block]; Block
0x180039c79  lea     rax, [rbp+57h+var_48]
0x180039c7d  cmp     rcx, rax
0x180039c80  jz      short loc_180039C8E
0x180039c82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180039c89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039c8e  cmp     r15d, 1
0x180039c92  jnz     loc_180039D29
0x180039c98  call    cs:__imp_GetCurrentThreadId
0x180039c9e  cmp     [r14+0F0h], eax
0x180039ca5  jz      short loc_180039CCD
0x180039ca7  mov     r8d, 1A25h
0x180039cad  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039cb4  call    Log_AssertionEvent_3
0x180039cb9  call    cs:__imp_GetCurrentThreadId
0x180039cbf  cmp     [r14+0F0h], eax
0x180039cc6  jz      short loc_180039CCD
0x180039cc8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039ccd  xorps   xmm0, xmm0
0x180039cd0  lea     rcx, [rdi+18h]; struct PH_CALL_INFO *
0x180039cd4  lea     rdx, [rbp+57h+var_88]; struct PH_PHONE_CALL_COUNTS *
0x180039cd8  movups  [rbp+57h+var_88], xmm0
0x180039cdc  movups  [rbp+57h+var_78], xmm0
0x180039ce0  movups  [rbp+57h+var_68], xmm0
0x180039ce4  call    ?CountCall@@YAXAEBUPH_CALL_INFO@@PEAUPH_PHONE_CALL_COUNTS@@@Z; CountCall(PH_CALL_INFO const &,PH_PHONE_CALL_COUNTS *)
0x180039ce9  mov     ecx, dword ptr [rbp+57h+var_78+0Ch]
0x180039cec  add     ecx, dword ptr [rbp+57h+var_78]
0x180039cef  jnz     short loc_180039D29
0x180039cf1  mov     esi, 800710DDh
0x180039cf6  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039cfd  mov     ecx, esi
0x180039cff  mov     r9d, 19F4h
0x180039d05  xor     edx, edx
0x180039d07  call    Log_HREvent_7
0x180039d0c  test    rbx, rbx
0x180039d0f  jz      short loc_180039D20
0x180039d11  mov     rcx, [rbx]
0x180039d14  mov     rax, [rcx+10h]
0x180039d18  mov     rcx, rbx
0x180039d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d20  mov     rcx, [rdi]
0x180039d23  mov     rax, [rcx+10h]
0x180039d27  jmp     short loc_180039D6E
0x180039d29  mov     r8d, r15d
0x180039d2c  mov     rdx, rbx
0x180039d2f  mov     rcx, r14
0x180039d32  call    ?_ExecuteLineAction@PhoneController@@IEAAJPEAVPhoneLine@@W4LineActions@@H@Z; PhoneController::_ExecuteLineAction(PhoneLine *,LineActions,int)
0x180039d37  mov     esi, eax
0x180039d39  test    eax, eax
0x180039d3b  jns     short loc_180039D53
0x180039d3d  mov     r9d, 19F9h
0x180039d43  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180039d4a  xor     edx, edx
0x180039d4c  mov     ecx, eax
0x180039d4e  call    Log_HREvent_7
0x180039d53  test    rbx, rbx
0x180039d56  jz      short loc_180039D67
0x180039d58  mov     rcx, [rbx]
0x180039d5b  mov     rax, [rcx+10h]
0x180039d5f  mov     rcx, rbx
0x180039d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d67  mov     rax, [rdi]
0x180039d6a  mov     rax, [rax+10h]
0x180039d6e  mov     rcx, rdi
0x180039d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d76  mov     eax, esi
0x180039d78  mov     rcx, [rbp+57h+var_38]
0x180039d7c  xor     rcx, rsp; StackCookie
0x180039d7f  call    __security_check_cookie
0x180039d84  add     rsp, 90h
0x180039d8b  pop     r15
0x180039d8d  pop     r14
0x180039d8f  pop     r12
0x180039d91  pop     rdi
0x180039d92  pop     rsi
0x180039d93  pop     rbx
0x180039d94  pop     rbp
0x180039d95  retn
```
