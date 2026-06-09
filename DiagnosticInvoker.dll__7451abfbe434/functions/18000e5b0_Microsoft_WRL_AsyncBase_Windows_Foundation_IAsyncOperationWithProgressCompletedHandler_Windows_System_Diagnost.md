# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)

- ea: `0x18000e5b0`
- end: `0x18000e6f8`
- name: `?Start@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a2c`

## callees

- `0x180001e20`
- `0x18000d4f0`
- `0x18000e5b0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e676`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e676`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e6c4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000e6c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000e639`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000e639`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(
        __int64 a1)
{
  signed __int32 v1; // edx
  signed __int32 v3; // eax
  int v4; // edi
  __int64 v5; // rsi
  __int64 v6; // r14
  HRESULT v7; // eax
  void (__fastcall *v8)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64); // rax
  signed __int32 v10[4]; // [rsp+40h] [rbp-9h] BYREF
  GUID v11; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  HSTRING string; // [rsp+78h] [rbp+2Fh] BYREF

  v1 = *(_DWORD *)(a1 + 56);
  v10[0] = -2;
  _InterlockedCompareExchange(v10, v1, -2);
  if ( v10[0] == -1 && (v3 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), 0, -1), v3 == v10[0]) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v4 >= 0
      && InitOnceExecuteOnce(
           &Microsoft::WRL::gCausalityInitOnce,
           (PINIT_ONCE_FN)Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality,
           0,
           0)
      && Microsoft::WRL::gCausality )
    {
      v5 = *(_QWORD *)Microsoft::WRL::gCausality;
      v6 = *(unsigned int *)(a1 + 64);
      string = 0;
      v7 = WindowsCreateStringReference(
             (PCWSTR)"W\x00i\x00n\x00d\x00o\x00w\x00s\x00.\x00F\x00o\x00u\x00n\x00d\x00a\x00t\x00i\x00o\x00n\x00.\x00A\x00s\x00y\x00n\x00c\x00O\x00p\x00e\x00r\x00a\x00t\x00i\x00o\x00n\x00W\x00i\x00t\x00h\x00P\x00r\x00o\x00g\x00r\x00e\x00s\x00s\x00C\x00o\x00m\x00p\x00l\x00e\x00t\x00e\x00d\x00H\x00a\x00n\x00d\x00l\x00e\x00r\x00`\x002\x00<\x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00.\x00S\x00y\x00s\x00t\x00e\x00m\x00.\x00D\x00i\x00a\x00g\x00n\x00o\x00s\x00t\x00i\x00c\x00s\x00.\x00D\x00i\x00a\x00g\x00n\x00o\x00s\x00t\x00i\x00c\x00A\x00c\x00t\x00i\x00o\x00n\x00R\x00e\x00s\x00u\x00l\x00t\x00,\x00 \x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00.\x00S\x00y\x00s\x00t\x00e\x00m\x00.\x00D\x00i\x00a\x00g\x00n\x00o\x00s\x00t\x00i\x00c\x00s\x00.\x00D\x00i\x00a\x00g\x00n\x00o\x00s\x00t\x00i\x00c\x00A\x00c\x00t\x00i\x00o\x00n\x00S\x00t\x00a\x00t\x00e\x00>",
             0xA4u,
             &hstringHeader,
             &string);
      if ( v7 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7);
        JUMPOUT(0x18000E6F7LL);
      }
      v8 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v5 + 48);
      v11 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v8(Microsoft::WRL::gCausality, 0, 2, &v11, a1, string, v6);
    }
  }
  else
  {
    v4 = -2147483635;
    RoOriginateError(2147483661LL, 0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e5b0  mov     [rsp-8+arg_8], rbx
0x18000e5b5  mov     [rsp-8+arg_10], rsi
0x18000e5ba  push    rbp
0x18000e5bb  push    rdi
0x18000e5bc  push    r14
0x18000e5be  lea     rbp, [rsp-47h]
0x18000e5c3  sub     rsp, 90h
0x18000e5ca  mov     rax, cs:__security_cookie
0x18000e5d1  xor     rax, rsp
0x18000e5d4  mov     [rbp+57h+var_20], rax
0x18000e5d8  mov     edx, [rcx+38h]
0x18000e5db  mov     rbx, rcx
0x18000e5de  mov     [rbp+57h+var_60], 0FFFFFFFEh
0x18000e5e5  mov     eax, [rbp+57h+var_60]
0x18000e5e8  lock cmpxchg [rbp+57h+var_60], edx
0x18000e5ed  or      eax, 0FFFFFFFFh
0x18000e5f0  cmp     [rbp+57h+var_60], eax
0x18000e5f3  jnz     loc_18000E6BB
0x18000e5f9  xor     ecx, ecx
0x18000e5fb  lock cmpxchg [rbx+38h], ecx
0x18000e600  cmp     eax, [rbp+57h+var_60]
0x18000e603  jnz     loc_18000E6BB
0x18000e609  mov     rax, [rbx]
0x18000e60c  mov     rcx, rbx
0x18000e60f  mov     rax, [rax+88h]
0x18000e616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61b  mov     edi, eax
0x18000e61d  test    eax, eax
0x18000e61f  js      loc_18000E6CA
0x18000e625  xor     r9d, r9d; Context
0x18000e628  lea     rdx, ?InitCausality@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000e62f  xor     r8d, r8d; Parameter
0x18000e632  lea     rcx, ?gCausalityInitOnce@WRL@Microsoft@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000e639  call    cs:__imp_InitOnceExecuteOnce
0x18000e63f  test    eax, eax
0x18000e641  jz      loc_18000E6CA
0x18000e647  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000e64e  test    rax, rax
0x18000e651  jz      short loc_18000E6CA
0x18000e653  mov     rsi, [rax]
0x18000e656  lea     r9, [rbp+57h+string]; string
0x18000e65a  mov     r14d, [rbx+40h]
0x18000e65e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000e662  mov     edx, 0A4h; length
0x18000e667  mov     [rbp+57h+string], 0
0x18000e66f  lea     rcx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; sourceString
0x18000e676  call    cs:__imp_WindowsCreateStringReference
0x18000e67c  test    eax, eax
0x18000e67e  js      short loc_18000E6F0
0x18000e680  mov     rcx, [rbp+57h+string]
0x18000e684  lea     r9, [rbp+57h+var_50]
0x18000e688  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000e68f  mov     rax, [rsi+30h]
0x18000e693  xor     edx, edx
0x18000e695  mov     [rsp+0A0h+var_70], r14
0x18000e69a  mov     [rsp+0A0h+var_78], rcx
0x18000e69f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000e6a6  lea     r8d, [rdx+2]
0x18000e6aa  mov     [rsp+0A0h+var_80], rbx
0x18000e6af  movdqu  [rbp+57h+var_50], xmm0
0x18000e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b9  jmp     short loc_18000E6CA
0x18000e6bb  mov     edi, 8000000Dh
0x18000e6c0  xor     edx, edx
0x18000e6c2  mov     ecx, edi
0x18000e6c4  call    cs:__imp_RoOriginateError
0x18000e6ca  mov     eax, edi
0x18000e6cc  mov     rcx, [rbp+57h+var_20]
0x18000e6d0  xor     rcx, rsp; StackCookie
0x18000e6d3  call    __security_check_cookie
0x18000e6d8  lea     r11, [rsp+0A0h+var_10]
0x18000e6e0  mov     rbx, [r11+28h]
0x18000e6e4  mov     rsi, [r11+30h]
0x18000e6e8  mov     rsp, r11
0x18000e6eb  pop     r14
0x18000e6ed  pop     rdi
0x18000e6ee  pop     rbp
0x18000e6ef  retn
0x18000e6f0  mov     ecx, eax; this
0x18000e6f2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
