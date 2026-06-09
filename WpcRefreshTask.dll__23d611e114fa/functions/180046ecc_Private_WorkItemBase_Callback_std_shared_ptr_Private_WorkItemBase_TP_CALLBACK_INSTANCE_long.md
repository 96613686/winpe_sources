# Private::WorkItemBase::Callback(std::shared_ptr<Private::WorkItemBase> &&,_TP_CALLBACK_INSTANCE *,long)

- ea: `0x180046ecc`
- end: `0x1800471cf`
- name: `?Callback@WorkItemBase@Private@@CAX$$QEAV?$shared_ptr@VWorkItemBase@Private@@@std@@PEAU_TP_CALLBACK_INSTANCE@@J@Z`
- size: `771`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047840`
- `0x180047be0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000ecc0`
- `0x1800395ac`
- `0x1800395d8`
- `0x18003998c`
- `0x18003a6c4`
- `0x180045b28`
- `0x180046ecc`
- `0x1800478e8`
- `0x180047e20`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180046fda`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180046fda`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180046ff5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180046ff5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f86`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f71`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046f86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004700e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004700e`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180046f1a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180046f1a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180047006`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180047006`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Private::WorkItemBase::Callback(struct Private::WorkItemBase **a1, struct _TP_CALLBACK_INSTANCE *a2)
{
  struct Private::WorkItemBase **v3; // r14
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx
  struct Private::WorkItemBase *v8; // rdi
  void (__fastcall *v9)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **); // rbx
  int v10; // r8d
  struct Private::WorkItemBase *v11; // rdi
  __int64 v12; // rdx
  signed __int32 v13; // eax
  signed __int32 v14; // ett
  Private::ThreadpoolImpl *v15; // rcx
  volatile signed __int32 *v16; // rdi
  struct Private::WorkItemBase *v17; // rax
  volatile signed __int32 *v18; // rcx
  volatile signed __int32 *v19; // rdi
  struct Private::WorkItemBase *v20; // rdi
  void (__fastcall *v21)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **); // rbx
  struct Private::WorkItemBase *v22; // rdi
  __int64 v23; // r8
  __int64 v24; // r9
  Private::ThreadpoolImpl *v25[2]; // [rsp+30h] [rbp-118h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-108h] BYREF
  int v27; // [rsp+44h] [rbp-104h] BYREF
  struct Private::WorkItemBase **v28; // [rsp+48h] [rbp-100h]
  char v29[8]; // [rsp+50h] [rbp-F8h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v31; // [rsp+78h] [rbp-D0h]
  _BYTE v32[160]; // [rsp+80h] [rbp-C8h] BYREF

  v3 = a1;
  v28 = a1;
  (*(void (__fastcall **)(struct Private::WorkItemBase *, unsigned int *))(*(_QWORD *)*a1 + 32LL))(*a1, &v26);
  if ( *((_BYTE *)*v3 + 24) )
    CallbackMayRunLong(a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, v26);
  try
  {
    Threading::ThreadEntered::ThreadEntered((Threading::ThreadEntered *)v32, *((unsigned __int8 *)*v3 + 24));
    Threading::SetPerformanceId(v29, v26);
    if ( TlsGetValue(dword_1801079C8) )
      v6 = *(_QWORD *)TlsGetValue(dword_1801079C8);
    else
      v6 = 0;
    try
    {
      *((_QWORD *)*v3 + 8) = v6;
      if ( *((_BYTE *)*v3 + 72) )
      {
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        v31 = 0;
        ThreadCancelledException::ThreadCancelledException((ThreadCancelledException *)pExceptionObject);
        throw (ThreadCancelledException *)pExceptionObject;
      }
      ComInitialize::ComInitialize(&v27, *((unsigned int *)*v3 + 7));
      LOBYTE(v7) = 1;
      (*(void (__fastcall **)(struct Private::WorkItemBase *, __int64))(*(_QWORD *)*v3 + 16LL))(*v3, v7);
      v8 = *v3;
      v9 = *(void (__fastcall **)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **))(*(_QWORD *)*v3 + 24LL);
      *(_OWORD *)v25 = 0;
      __ExceptionPtrCreate(v25);
      v9(v8, v25);
      __ExceptionPtrDestroy(v25);
      if ( (v27 & 0xFFFFFFFD) != 0 )
        RoUninitialize();
      else
        CoUninitialize();
    }
    catch ( std::exception )
    {
      v20 = *v28;
      v21 = *(void (__fastcall **)(struct Private::WorkItemBase *, Private::ThreadpoolImpl **))(*(_QWORD *)*v28 + 24LL);
      *(_OWORD *)v25 = 0;
      __ExceptionPtrCreate(v25);
      __ExceptionPtrCurrentException(v25);
      v21(v20, v25);
      __ExceptionPtrDestroy(v25);
      v3 = v28;
    }
    v11 = *v3;
    *(_OWORD *)v25 = 0;
    v12 = *((_QWORD *)v11 + 5);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v12 + 8);
      while ( v13 )
      {
        v14 = v13;
        v13 = _InterlockedCompareExchange((volatile signed __int32 *)(v12 + 8), v13 + 1, v13);
        if ( v14 == v13 )
        {
          v15 = (Private::ThreadpoolImpl *)*((_QWORD *)v11 + 4);
          v25[0] = v15;
          v16 = (volatile signed __int32 *)*((_QWORD *)v11 + 5);
          v25[1] = (Private::ThreadpoolImpl *)v16;
          goto LABEL_18;
        }
      }
    }
    v15 = v25[0];
    v16 = (volatile signed __int32 *)v25[1];
LABEL_18:
    if ( v15 )
    {
      Private::ThreadpoolImpl::Unregister(v15, *v3);
      v17 = *v3;
      *((_QWORD *)v17 + 4) = 0;
      v18 = (volatile signed __int32 *)*((_QWORD *)v17 + 5);
      *((_QWORD *)v17 + 5) = 0;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    *v3 = 0;
    v19 = (volatile signed __int32 *)v3[1];
    v3[1] = 0;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    Threading::ThreadEntered::~ThreadEntered((Threading::ThreadEntered *)v32, v12, v10);
  }
  catch ( std::exception )
  {
    v22 = *v28;
    *(_OWORD *)v25 = 0;
    __ExceptionPtrCreate(v25);
    __ExceptionPtrCurrentException(v25);
    guard_dispatch_icall_thunk_10345483385596137414(v22, v25, v23, v24);
    __ExceptionPtrDestroy(v25);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v26);
}

```

## disassembly

```asm
0x180046ecc  mov     [rsp+arg_10], rbx
0x180046ed1  push    rdi
0x180046ed2  push    r14
0x180046ed4  push    r15
0x180046ed6  sub     rsp, 130h
0x180046edd  mov     rax, cs:__security_cookie
0x180046ee4  xor     rax, rsp
0x180046ee7  mov     [rsp+148h+var_28], rax
0x180046eef  mov     rbx, rdx
0x180046ef2  mov     r14, rcx
0x180046ef5  mov     [rsp+148h+var_100], rcx
0x180046efa  mov     rcx, [rcx]
0x180046efd  mov     rax, [rcx]
0x180046f00  lea     rdx, [rsp+148h+var_108]
0x180046f05  mov     rax, [rax+20h]
0x180046f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f0e  mov     rax, [r14]
0x180046f11  cmp     byte ptr [rax+18h], 0
0x180046f15  jz      short loc_180046F20
0x180046f17  mov     rcx, rbx; pci
0x180046f1a  call    cs:__imp_CallbackMayRunLong
0x180046f20  lea     r15, WPP_GLOBAL_Control
0x180046f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f2e  cmp     rcx, r15
0x180046f31  jz      short loc_180046F48
0x180046f33  test    byte ptr [rcx+1Ch], 10h
0x180046f37  jz      short loc_180046F48
0x180046f39  mov     r9d, [rsp+148h+var_108]
0x180046f3e  mov     rcx, [rcx+10h]
0x180046f42  call    WPP_SF_DD
0x180046f47  nop
0x180046f48  mov     rax, [r14]
0x180046f4b  movzx   edx, byte ptr [rax+18h]; int
0x180046f4f  lea     rcx, [rsp+148h+var_C8]; this
0x180046f57  call    ??0ThreadEntered@Threading@@QEAA@H@Z; Threading::ThreadEntered::ThreadEntered(int)
0x180046f5c  nop
0x180046f5d  mov     edx, [rsp+148h+var_108]
0x180046f61  lea     rcx, [rsp+148h+var_F8]
0x180046f66  call    ?SetPerformanceId@Threading@@YA?AUPerformanceId@Private@@U23@@Z; Threading::SetPerformanceId(Private::PerformanceId)
0x180046f6b  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x180046f71  call    cs:__imp_TlsGetValue
0x180046f77  test    rax, rax
0x180046f7a  jnz     short loc_180046F80
0x180046f7c  xor     ecx, ecx
0x180046f7e  jmp     short loc_180046F8F
0x180046f80  mov     ecx, cs:dword_1801079C8; dwTlsIndex
0x180046f86  call    cs:__imp_TlsGetValue
0x180046f8c  mov     rcx, [rax]
0x180046f8f  mov     rax, [r14]
0x180046f92  mov     [rax+40h], rcx
0x180046f96  mov     rdx, [r14]
0x180046f99  cmp     byte ptr [rdx+48h], 0
0x180046f9d  jnz     loc_18004719E
0x180046fa3  mov     edx, [rdx+1Ch]
0x180046fa6  lea     rcx, [rsp+148h+var_104]
0x180046fab  call    ??0ComInitialize@@QEAA@W4ComApartment@ComApartments@@_N@Z; ComInitialize::ComInitialize(ComApartments::ComApartment,bool)
0x180046fb0  nop
0x180046fb1  mov     rcx, [r14]
0x180046fb4  mov     rax, [rcx]
0x180046fb7  mov     dl, 1
0x180046fb9  mov     rax, [rax+10h]
0x180046fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fc2  mov     rdi, [r14]
0x180046fc5  mov     rax, [rdi]
0x180046fc8  mov     rbx, [rax+18h]
0x180046fcc  xorps   xmm0, xmm0
0x180046fcf  movdqu  xmmword ptr [rsp+148h+var_118], xmm0
0x180046fd5  lea     rcx, [rsp+148h+var_118]
0x180046fda  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180046fe0  lea     rdx, [rsp+148h+var_118]
0x180046fe5  mov     rcx, rdi
0x180046fe8  mov     rax, rbx
0x180046feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ff0  lea     rcx, [rsp+148h+var_118]
0x180046ff5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180046ffb  nop
0x180046ffc  test    [rsp+148h+var_104], 0FFFFFFFDh
0x180047004  jz      short loc_18004700E
0x180047006  call    cs:__imp_RoUninitialize
0x18004700c  jmp     short loc_180047015
0x18004700e  call    cs:__imp_CoUninitialize
0x180047014  nop
0x180047015  jmp     short loc_180047023
0x180047017  lea     r15, WPP_GLOBAL_Control
0x18004701e  mov     r14, [rsp+148h+var_100]
0x180047023  mov     rdi, [r14]
0x180047026  xorps   xmm0, xmm0
0x180047029  movdqu  xmmword ptr [rsp+148h+var_118], xmm0
0x18004702f  mov     rdx, [rdi+28h]
0x180047033  test    rdx, rdx
0x180047036  jz      short loc_18004704B
0x180047038  mov     eax, [rdx+8]
0x18004703b  jmp     short loc_180047047
0x18004703d  lea     ecx, [rax+1]
0x180047040  lock cmpxchg [rdx+8], ecx
0x180047045  jz      short loc_18004709A
0x180047047  test    eax, eax
0x180047049  jnz     short loc_18004703D
0x18004704b  mov     rcx, [rsp+148h+var_118]; this
0x180047050  mov     rdi, [rsp+148h+var_118+8]
0x180047055  test    rcx, rcx
0x180047058  jz      short loc_1800470AE
0x18004705a  mov     rdx, [r14]; struct Private::WorkItemBase *
0x18004705d  call    ?Unregister@ThreadpoolImpl@Private@@QEAAXAEAVWorkItemBase@2@@Z; Private::ThreadpoolImpl::Unregister(Private::WorkItemBase &)
0x180047062  mov     rax, [r14]
0x180047065  mov     qword ptr [rax+20h], 0
0x18004706d  mov     rcx, [rax+28h]
0x180047071  mov     qword ptr [rax+28h], 0
0x180047079  test    rcx, rcx
0x18004707c  jz      short loc_1800470AE
0x18004707e  or      ebx, 0FFFFFFFFh
0x180047081  mov     eax, ebx
0x180047083  lock xadd [rcx+0Ch], eax
0x180047088  add     eax, ebx
0x18004708a  jnz     short loc_1800470B1
0x18004708c  mov     rax, [rcx]
0x18004708f  mov     rax, [rax+8]
0x180047093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047098  jmp     short loc_1800470B1
0x18004709a  mov     rcx, [rdi+20h]
0x18004709e  mov     [rsp+148h+var_118], rcx
0x1800470a3  mov     rdi, [rdi+28h]
0x1800470a7  mov     [rsp+148h+var_118+8], rdi
0x1800470ac  jmp     short loc_180047055
0x1800470ae  or      ebx, 0FFFFFFFFh
0x1800470b1  test    rdi, rdi
0x1800470b4  jz      short loc_1800470E9
0x1800470b6  mov     eax, ebx
0x1800470b8  lock xadd [rdi+8], eax
0x1800470bd  add     eax, ebx
0x1800470bf  jnz     short loc_1800470E9
0x1800470c1  mov     rax, [rdi]
0x1800470c4  mov     rcx, rdi
0x1800470c7  mov     rax, [rax]
0x1800470ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470cf  mov     eax, ebx
0x1800470d1  lock xadd [rdi+0Ch], eax
0x1800470d6  add     eax, ebx
0x1800470d8  jnz     short loc_1800470E9
0x1800470da  mov     rax, [rdi]
0x1800470dd  mov     rcx, rdi
0x1800470e0  mov     rax, [rax+8]
0x1800470e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470e9  mov     qword ptr [r14], 0
0x1800470f0  mov     rdi, [r14+8]
0x1800470f4  mov     qword ptr [r14+8], 0
0x1800470fc  test    rdi, rdi
0x1800470ff  jz      short loc_180047135
0x180047101  mov     eax, ebx
0x180047103  lock xadd [rdi+8], eax
0x180047108  add     eax, ebx
0x18004710a  jnz     short loc_180047135
0x18004710c  mov     rax, [rdi]
0x18004710f  mov     rcx, rdi
0x180047112  mov     rax, [rax]
0x180047115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004711a  mov     eax, ebx
0x18004711c  lock xadd [rdi+0Ch], eax
0x180047121  add     eax, ebx
0x180047123  jnz     short loc_180047135
0x180047125  mov     rax, [rdi]
0x180047128  mov     rcx, rdi
0x18004712b  mov     rax, [rax+8]
0x18004712f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047134  nop
0x180047135  lea     rcx, [rsp+148h+var_C8]; this
0x18004713d  call    ??1ThreadEntered@Threading@@QEAA@XZ; Threading::ThreadEntered::~ThreadEntered(void)
0x180047142  nop
0x180047143  jmp     short loc_18004714C
0x180047145  lea     r15, WPP_GLOBAL_Control
0x18004714c  mov     rcx, cs:WPP_GLOBAL_Control
0x180047153  cmp     rcx, r15
0x180047156  jz      short loc_180047179
0x180047158  test    byte ptr [rcx+1Ch], 10h
0x18004715c  jz      short loc_180047179
0x18004715e  mov     edx, 0Fh
0x180047163  mov     r9d, [rsp+148h+var_108]
0x180047168  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x18004716f  mov     rcx, [rcx+10h]
0x180047173  call    WPP_SF_d
0x180047178  nop
0x180047179  mov     rcx, [rsp+148h+var_28]
0x180047181  xor     rcx, rsp; StackCookie
0x180047184  call    __security_check_cookie
0x180047189  mov     rbx, [rsp+148h+arg_10]
0x180047191  add     rsp, 130h
0x180047198  pop     r15
0x18004719a  pop     r14
0x18004719c  pop     rdi
0x18004719d  retn
0x18004719e  xorps   xmm0, xmm0
0x1800471a1  xor     eax, eax
0x1800471a3  movups  [rsp+148h+pExceptionObject], xmm0
0x1800471a8  movups  [rsp+148h+var_E0], xmm0
0x1800471ad  mov     [rsp+148h+var_D0], rax
0x1800471b2  lea     rcx, [rsp+148h+pExceptionObject]; this
0x1800471b7  call    ??0ThreadCancelledException@@QEAA@XZ; ThreadCancelledException::ThreadCancelledException(void)
0x1800471bc  lea     rdx, _TI4?AVThreadCancelledException@@; pThrowInfo
0x1800471c3  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800471c8  call    _CxxThrowException_0
```
