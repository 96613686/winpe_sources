# PolicyEngineController::RunPolicyEvaluation(EvaluationTrigger)

- ea: `0x18001c0e0`
- end: `0x18001c231`
- name: `?RunPolicyEvaluation@PolicyEngineController@@UEAAJW4EvaluationTrigger@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004600`
- `0x180004668`
- `0x180008a38`
- `0x18000c0f0`
- `0x18000c288`
- `0x18000fe20`
- `0x18001b0b0`
- `0x18001bb30`
- `0x18001c0e0`
- `0x180026010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c1c0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001c1c0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001c12e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001c12e`

## string_xrefs

- `0x18001c201`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\policyenginecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PolicyEngineController::RunPolicyEvaluation(__int64 a1, int a2)
{
  volatile int *v3; // rdx
  __int64 v4; // rax
  unsigned int v5; // edi
  __int64 *v6; // rax
  __int64 v7; // rsi
  int v8; // edi
  _QWORD v10[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+68h] [rbp+10h] BYREF

  v13 = a2;
  v3 = (volatile int *)(unsigned int)tls_index;
  if ( dword_180036C40 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180036C40);
    if ( dword_180036C40 == -1 )
    {
      dword_180036C44 = SHTaskPoolGetUniqueContext();
      Init_thread_footer(&dword_180036C40);
    }
  }
  v12 = a1;
  if ( a1 )
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(a1 + 44), v3);
  v4 = lambda_58090dfcce1eb05be233a7a4f9886a38_::_lambda_58090dfcce1eb05be233a7a4f9886a38_(v10, &v12, a1, &v13);
  v5 = dword_180036C44;
  v6 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_58090dfcce1eb05be233a7a4f9886a38_____lambda_58090dfcce1eb05be233a7a4f9886a38___(
                    &v12,
                    v4);
  v7 = *v6;
  *v6 = 0;
  if ( v12 )
  {
    v12 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v8 = SHTaskPoolQueueTask(3, 2, v5);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v10[0] )
  {
    v10[0] = 0;
    ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPolicyEngineController,Microsoft::WRL::FtmBase>::Release)();
  }
  if ( v8 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\policyenginecontroller.cpp",
      (const char *)(unsigned int)v8,
      v7);
  if ( a1 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPolicyEngineController,Microsoft::WRL::FtmBase>::Release(a1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001c0e0  mov     [rsp+arg_10], rbx
0x18001c0e5  mov     [rsp+arg_18], rsi
0x18001c0ea  mov     [rsp+arg_8], edx
0x18001c0ee  push    rdi
0x18001c0ef  sub     rsp, 50h
0x18001c0f3  mov     rbx, rcx
0x18001c0f6  mov     edx, cs:_tls_index
0x18001c0fc  mov     rax, gs:58h
0x18001c105  mov     ecx, 4
0x18001c10a  mov     rax, [rax+rdx*8]
0x18001c10e  mov     eax, [rcx+rax]
0x18001c111  cmp     cs:dword_180036C40, eax
0x18001c117  jle     short loc_18001C146
0x18001c119  lea     rcx, dword_180036C40
0x18001c120  call    _Init_thread_header
0x18001c125  cmp     cs:dword_180036C40, 0FFFFFFFFh
0x18001c12c  jnz     short loc_18001C146
0x18001c12e  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18001c134  mov     cs:dword_180036C44, eax
0x18001c13a  lea     rcx, dword_180036C40
0x18001c141  call    _Init_thread_footer
0x18001c146  mov     [rsp+58h+arg_0], rbx
0x18001c14b  test    rbx, rbx
0x18001c14e  jz      short loc_18001C159
0x18001c150  lea     rcx, [rbx+2Ch]; this
0x18001c154  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18001c159  lea     r9, [rsp+58h+arg_8]
0x18001c15e  mov     r8, rbx
0x18001c161  lea     rdx, [rsp+58h+arg_0]
0x18001c166  lea     rcx, [rsp+58h+var_28]
0x18001c16b  call    _lambda_58090dfcce1eb05be233a7a4f9886a38____lambda_58090dfcce1eb05be233a7a4f9886a38_
0x18001c170  mov     edi, cs:dword_180036C44
0x18001c176  mov     rdx, rax
0x18001c179  lea     rcx, [rsp+58h+arg_0]
0x18001c17e  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_58090dfcce1eb05be233a7a4f9886a38_____lambda_58090dfcce1eb05be233a7a4f9886a38___
0x18001c183  mov     rsi, [rax]
0x18001c186  mov     qword ptr [rax], 0
0x18001c18d  mov     rcx, [rsp+58h+arg_0]
0x18001c192  test    rcx, rcx
0x18001c195  jz      short loc_18001C1A5
0x18001c197  mov     [rsp+58h+arg_0], 0
0x18001c1a0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18001c1a5  mov     [rsp+58h+var_30], 0
0x18001c1ae  mov     qword ptr [rsp+58h+var_38], rsi; int
0x18001c1b3  xor     r9d, r9d
0x18001c1b6  mov     r8d, edi
0x18001c1b9  lea     edx, [r9+2]
0x18001c1bd  lea     ecx, [rdx+1]
0x18001c1c0  call    cs:__imp_SHTaskPoolQueueTask
0x18001c1c6  mov     edi, eax
0x18001c1c8  test    rsi, rsi
0x18001c1cb  jz      short loc_18001C1DD
0x18001c1cd  mov     rdx, [rsi]
0x18001c1d0  mov     rcx, rsi
0x18001c1d3  mov     rax, [rdx+10h]
0x18001c1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1dc  nop
0x18001c1dd  mov     rcx, [rsp+58h+var_28]
0x18001c1e2  test    rcx, rcx
0x18001c1e5  jz      short loc_18001C1F5
0x18001c1e7  mov     [rsp+58h+var_28], 0
0x18001c1f0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPolicyEngineController@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPolicyEngineController,Microsoft::WRL::FtmBase>::Release(void)
0x18001c1f5  test    edi, edi
0x18001c1f7  jns     short loc_18001C212
0x18001c1f9  mov     rcx, [rsp+58h]; this
0x18001c1fe  mov     r9d, edi; char *
0x18001c201  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001c208  mov     edx, 38h ; '8'; void *
0x18001c20d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c212  test    rbx, rbx
0x18001c215  jz      short loc_18001C21F
0x18001c217  mov     rcx, rbx
0x18001c21a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPolicyEngineController@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPolicyEngineController,Microsoft::WRL::FtmBase>::Release(void)
0x18001c21f  mov     eax, edi
0x18001c221  mov     rbx, [rsp+58h+arg_10]
0x18001c226  mov     rsi, [rsp+58h+arg_18]
0x18001c22b  add     rsp, 50h
0x18001c22f  pop     rdi
0x18001c230  retn
```
