# PhoneController::_UninitializeLine(PhoneLine *)

- ea: `0x180049f94`
- end: `0x18004a251`
- name: `?_UninitializeLine@PhoneController@@IEAAXPEAVPhoneLine@@@Z`
- size: `701`
- prototype: `void __fastcall(PhoneController *__hidden this, struct PhoneLine *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800404a0`
- `0x180043c58`
- `0x180044484`

## callees

- `0x1800056a0`
- `0x18000e1a4`
- `0x18002c574`
- `0x18002c580`
- `0x180041858`
- `0x180049f94`
- `0x18004b778`
- `0x18004ef10`
- `0x18005354c`
- `0x180071b9c`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a02d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a02d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a099`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049fe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049fc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049fe9`

## string_xrefs

- `0x18004a067`: `onecoreuap\private\net\inc\phone\RevokableComPtr.h`
- `0x180049fdd`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a113`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a19e`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004a1f4`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
void __fastcall PhoneController::_UninitializeLine(PhoneController *this, struct PhoneLine *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int (__fastcall ***v6)(_QWORD, GUID *, struct _GUID *); // rcx
  int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int AllCalls; // eax
  CallInfo **i; // rbx
  CallInfo *v13; // rcx
  __int64 v14; // rdi
  CallInfo *v15; // rax
  int v16; // eax
  struct _GUID v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+368h] [rbp+268h]

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8346);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v5 = *((_QWORD *)a2 + 166);
  if ( v5 )
  {
    *((_QWORD *)a2 + 166) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *(_QWORD *)&v17.Data1 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a2 + 1);
  v6 = (int (__fastcall ***)(_QWORD, GUID *, struct _GUID *))*((_QWORD *)a2 + 10);
  v7 = *((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 8) = 1;
  if ( v6 )
  {
    if ( (**v6)(v6, &GUID_d3f351e4_d0f1_4736_b983_716d7064f39a, &v17) < 0 )
    {
      Log_AssertionEvent_11(v8, "onecoreuap\\private\\net\\inc\\phone\\RevokableComPtr.h", 192);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v9 = *((_QWORD *)a2 + 10);
    if ( v9 )
    {
      *((_QWORD *)a2 + 10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a2 + 1);
  if ( !v7 )
  {
    if ( !*(_QWORD *)&v17.Data1 )
      goto LABEL_16;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v17.Data1 + 136LL))(*(_QWORD *)&v17.Data1);
  }
  if ( *(_QWORD *)&v17.Data1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v17.Data1 + 16LL))(*(_QWORD *)&v17.Data1);
LABEL_16:
  v10 = *((_QWORD *)this + 12);
  *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v21 = -1;
  v18 = *(_OWORD *)Block;
  v19 = -1;
  AllCalls = PhoneCallStorage::GetAllCalls(v10, &v18, 0);
  if ( AllCalls < 0 )
    Log_HREvent_7((unsigned int)AllCalls, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8355);
  for ( i = (CallInfo **)v18; i != *((CallInfo ***)&v18 + 1); ++i )
  {
    v13 = *i;
    *(_QWORD *)&v17.Data1 = 0;
    CallInfo::GetPhoneLine(v13, (struct PhoneLine **)&v17);
    v14 = *(_QWORD *)&v17.Data1;
    if ( *(struct PhoneLine **)&v17.Data1 == a2 )
    {
      memset_0(&v22, 0, 0xF40u);
      v15 = *i;
      v23 = 32;
      v24 = 5;
      v22 = *((_DWORD *)v15 + 767);
      if ( !(unsigned __int8)utl::vector<CallUpdate,utl::allocator<CallUpdate>>::push_back(Block, &v22) )
        Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8368);
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v17 = *(struct _GUID *)((char *)a2 + 88);
  v16 = PhoneController::_OnCallsChanged(this, &v17, (__int64)Block);
  if ( v16 < 0 )
    Log_HREvent_7((unsigned int)v16, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8372);
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v18);
  if ( Block[0] != (void *)-1LL )
  {
    Block[1] = Block[0];
    operator delete(Block[0]);
  }
}

```

## disassembly

```asm
0x180049f94  mov     [rsp-8+arg_10], rbx
0x180049f99  mov     [rsp-8+arg_18], rsi
0x180049f9e  push    rbp
0x180049f9f  push    rdi
0x180049fa0  push    r14
0x180049fa2  lea     rbp, [rsp-0EC0h]
0x180049faa  sub     rsp, 0FC0h
0x180049fb1  mov     rax, cs:__security_cookie
0x180049fb8  xor     rax, rsp
0x180049fbb  mov     [rbp+0ED0h+var_20], rax
0x180049fc2  mov     rsi, rdx
0x180049fc5  mov     r14, rcx
0x180049fc8  call    cs:__imp_GetCurrentThreadId
0x180049fce  cmp     [r14+0F0h], eax
0x180049fd5  jz      short loc_180049FFD
0x180049fd7  mov     r8d, 209Ah
0x180049fdd  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180049fe4  call    Log_AssertionEvent_3
0x180049fe9  call    cs:__imp_GetCurrentThreadId
0x180049fef  cmp     [r14+0F0h], eax
0x180049ff6  jz      short loc_180049FFD
0x180049ff8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180049ffd  mov     rcx, [rsi+530h]
0x18004a004  test    rcx, rcx
0x18004a007  jz      short loc_18004A020
0x18004a009  mov     qword ptr [rsi+530h], 0
0x18004a014  mov     rax, [rcx]
0x18004a017  mov     rax, [rax+10h]
0x18004a01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a020  lea     rcx, [rsi+28h]; lpCriticalSection
0x18004a024  mov     qword ptr [rsp+0FD0h+var_FA0.Data1], 0
0x18004a02d  call    cs:__imp_EnterCriticalSection
0x18004a033  mov     rcx, [rsi+50h]
0x18004a037  mov     edi, [rsi+20h]
0x18004a03a  mov     dword ptr [rsi+20h], 1
0x18004a041  test    rcx, rcx
0x18004a044  jz      short loc_18004A095
0x18004a046  mov     rax, [rcx]
0x18004a049  lea     r8, [rsp+0FD0h+var_FA0]
0x18004a04e  lea     rdx, _GUID_d3f351e4_d0f1_4736_b983_716d7064f39a
0x18004a055  mov     rax, [rax]
0x18004a058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a05d  test    eax, eax
0x18004a05f  jns     short loc_18004A078
0x18004a061  mov     r8d, 0C0h
0x18004a067  lea     rdx, aOnecoreuapPriv_3; "onecoreuap\\private\\net\\inc\\phone\\R"...
0x18004a06e  call    Log_AssertionEvent_11
0x18004a073  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004a078  mov     rcx, [rsi+50h]
0x18004a07c  test    rcx, rcx
0x18004a07f  jz      short loc_18004A095
0x18004a081  mov     qword ptr [rsi+50h], 0
0x18004a089  mov     rax, [rcx]
0x18004a08c  mov     rax, [rax+10h]
0x18004a090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a095  lea     rcx, [rsi+28h]; lpCriticalSection
0x18004a099  call    cs:__imp_LeaveCriticalSection
0x18004a09f  test    edi, edi
0x18004a0a1  jnz     short loc_18004A0BC
0x18004a0a3  mov     rcx, qword ptr [rsp+0FD0h+var_FA0.Data1]
0x18004a0a8  test    rcx, rcx
0x18004a0ab  jz      short loc_18004A0D2
0x18004a0ad  mov     rax, [rcx]
0x18004a0b0  mov     rax, [rax+88h]
0x18004a0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0bc  mov     rcx, qword ptr [rsp+0FD0h+var_FA0.Data1]
0x18004a0c1  test    rcx, rcx
0x18004a0c4  jz      short loc_18004A0D2
0x18004a0c6  mov     rax, [rcx]
0x18004a0c9  mov     rax, [rax+10h]
0x18004a0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0d2  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004a0da  lea     rdx, [rsp+0FD0h+var_F90]
0x18004a0df  mov     rcx, [r14+60h]
0x18004a0e3  xor     r8d, r8d
0x18004a0e6  movdqu  xmmword ptr [rsp+0FD0h+Block], xmm0
0x18004a0ec  mov     [rsp+0FD0h+var_F68], 0FFFFFFFFFFFFFFFFh
0x18004a0f5  movdqu  [rsp+0FD0h+var_F90], xmm0
0x18004a0fb  mov     [rsp+0FD0h+var_F80], 0FFFFFFFFFFFFFFFFh
0x18004a104  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x18004a109  test    eax, eax
0x18004a10b  jns     short loc_18004A123
0x18004a10d  mov     r9d, 20A3h
0x18004a113  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a11a  xor     edx, edx
0x18004a11c  mov     ecx, eax
0x18004a11e  call    Log_HREvent_7
0x18004a123  mov     rbx, qword ptr [rsp+0FD0h+var_F90]
0x18004a128  cmp     rbx, qword ptr [rsp+0FD0h+var_F90+8]
0x18004a12d  jz      loc_18004A1CE
0x18004a133  mov     rcx, [rbx]; this
0x18004a136  lea     rdx, [rsp+0FD0h+var_FA0]; struct PhoneLine **
0x18004a13b  mov     qword ptr [rsp+0FD0h+var_FA0.Data1], 0
0x18004a144  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x18004a149  mov     rdi, qword ptr [rsp+0FD0h+var_FA0.Data1]
0x18004a14e  cmp     rdi, rsi
0x18004a151  jnz     short loc_18004A1B1
0x18004a153  xor     edx, edx; Val
0x18004a155  lea     rcx, [rsp+0FD0h+var_F60]; void *
0x18004a15a  mov     r8d, 0F40h; Size
0x18004a160  call    memset_0
0x18004a165  mov     rax, [rbx]
0x18004a168  lea     rdx, [rsp+0FD0h+var_F60]
0x18004a16d  mov     [rsp+0FD0h+var_F58], 20h ; ' '
0x18004a176  mov     [rbp+0ED0h+var_C68], 5
0x18004a180  mov     ecx, [rax+0BFCh]
0x18004a186  mov     [rsp+0FD0h+var_F60], ecx
0x18004a18a  lea     rcx, [rsp+0FD0h+Block]
0x18004a18f  call    ?push_back@?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@QEAA_N$$QEAUCallUpdate@@@Z; utl::vector<CallUpdate,utl::allocator<CallUpdate>>::push_back(CallUpdate &&)
0x18004a194  test    al, al
0x18004a196  jnz     short loc_18004A1B1
0x18004a198  mov     r9d, 20B0h
0x18004a19e  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a1a5  xor     edx, edx
0x18004a1a7  mov     ecx, 8007000Eh
0x18004a1ac  call    Log_HREvent_7
0x18004a1b1  test    rdi, rdi
0x18004a1b4  jz      short loc_18004A1C5
0x18004a1b6  mov     rax, [rdi]
0x18004a1b9  mov     rcx, rdi
0x18004a1bc  mov     rax, [rax+10h]
0x18004a1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1c5  add     rbx, 8
0x18004a1c9  jmp     loc_18004A128
0x18004a1ce  movups  xmm0, xmmword ptr [rsi+58h]
0x18004a1d2  lea     r8, [rsp+0FD0h+Block]
0x18004a1d7  mov     rcx, r14; this
0x18004a1da  lea     rdx, [rsp+0FD0h+var_FA0]; struct _GUID *
0x18004a1df  movdqu  xmmword ptr [rsp+0FD0h+var_FA0.Data1], xmm0
0x18004a1e5  call    ?_OnCallsChanged@PhoneController@@IEAAJAEBU_GUID@@AEBV?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@@Z; PhoneController::_OnCallsChanged(_GUID const &,utl::vector<CallUpdate,utl::allocator<CallUpdate>> const &)
0x18004a1ea  test    eax, eax
0x18004a1ec  jns     short loc_18004A204
0x18004a1ee  mov     r9d, 20B4h
0x18004a1f4  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004a1fb  xor     edx, edx
0x18004a1fd  mov     ecx, eax
0x18004a1ff  call    Log_HREvent_7
0x18004a204  lea     rcx, [rsp+0FD0h+var_F90]
0x18004a209  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18004a20e  mov     rcx, [rsp+0FD0h+Block]; Block
0x18004a213  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004a217  jz      short loc_18004A22A
0x18004a219  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18004a220  mov     [rsp+0FD0h+Block+8], rcx
0x18004a225  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a22a  mov     rcx, [rbp+0ED0h+var_20]
0x18004a231  xor     rcx, rsp; StackCookie
0x18004a234  call    __security_check_cookie
0x18004a239  lea     r11, [rsp+0FD0h+var_10]
0x18004a241  mov     rbx, [r11+30h]
0x18004a245  mov     rsi, [r11+38h]
0x18004a249  mov     rsp, r11
0x18004a24c  pop     r14
0x18004a24e  pop     rdi
0x18004a24f  pop     rbp
0x18004a250  retn
```
