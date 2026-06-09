# WaasMedic::TelemetryProvider::DetectWaaSCurrency::StartActivity(TraceLoggingCorrelationVector *)

- ea: `0x180065de0`
- end: `0x180065f7f`
- name: `?StartActivity@DetectWaaSCurrency@TelemetryProvider@WaasMedic@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z`
- size: `415`
- prototype: `void(WaasMedic::TelemetryProvider::DetectWaaSCurrency *__hidden this, struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180065920`

## callees

- `0x180001718`
- `0x1800050a0`
- `0x18000acc0`
- `0x18000d04c`
- `0x18001df78`
- `0x180065488`
- `0x180065de0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065e6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065e6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065f4d`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::DetectWaaSCurrency::StartActivity(
        WaasMedic::TelemetryProvider::DetectWaaSCurrency *this,
        struct TraceLoggingCorrelationVector *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // rax
  int v10; // eax
  _QWORD *v11; // rbx
  _QWORD *Local; // rax
  DWORD v13; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v14[10]; // [rsp+38h] [rbp-21h] BYREF
  int v15; // [rsp+88h] [rbp+2Fh]
  int v16; // [rsp+8Ch] [rbp+33h]

  v2 = (const unsigned __int16 *)((char *)this + 336);
  if ( a2 )
    TraceLoggingCorrelationVector::Increment(a2, (char *)this + 336);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v6 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v6 > 5u )
  {
    v5 = *(_QWORD *)(v6 + 24);
    v4 = 0x400000000000LL;
    if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v5 & 0x400000000000LL) == v5 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v13 = CurrentThreadId;
      v14[0] = 0x1000000;
      if ( v2 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *((_BYTE *)v2 + v9) );
        v10 = v9 + 1;
      }
      else
      {
        v2 = &qword_180072C40;
        v10 = 1;
      }
      v15 = v10;
      v14[9] = v2;
      v14[7] = &v13;
      v16 = 0;
      v14[5] = v14;
      v14[8] = 4;
      v14[6] = 8;
      tlgWriteTransfer_EventWriteTransfer(v6, byte_180094E29, v8 + 8);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v11 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v4) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          v4);
      *v11 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v11;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v11 = 0;
    }
  }
}

```

## disassembly

```asm
0x180065de0  mov     [rsp-8+arg_10], rbx
0x180065de5  mov     [rsp-8+arg_18], rsi
0x180065dea  push    rbp
0x180065deb  push    rdi
0x180065dec  push    r14
0x180065dee  lea     rbp, [rsp-47h]
0x180065df3  sub     rsp, 0A0h
0x180065dfa  mov     rax, cs:__security_cookie
0x180065e01  xor     rax, rsp
0x180065e04  mov     [rbp+57h+var_20], rax
0x180065e08  xor     r14d, r14d
0x180065e0b  lea     rbx, [rcx+150h]
0x180065e12  mov     rax, rdx
0x180065e15  mov     rdi, rcx
0x180065e18  test    rdx, rdx
0x180065e1b  jz      short loc_180065E28
0x180065e1d  mov     rdx, rbx; char *
0x180065e20  mov     rcx, rax; this
0x180065e23  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180065e28  mov     rcx, rdi
0x180065e2b  call    ?zInternalStart@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180065e30  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180065e35  mov     rsi, [rax+8]
0x180065e39  mov     eax, [rsi]
0x180065e3b  cmp     eax, 5
0x180065e3e  jbe     loc_180065F1B
0x180065e44  mov     rcx, [rsi+18h]
0x180065e48  mov     rdx, 400000000000h
0x180065e52  mov     rax, [rsi+10h]
0x180065e56  test    rdx, rax
0x180065e59  jz      loc_180065F1B
0x180065e5f  mov     rax, rcx
0x180065e62  and     rax, rdx
0x180065e65  cmp     rax, rcx
0x180065e68  jnz     loc_180065F1B
0x180065e6e  call    cs:__imp_GetCurrentThreadId
0x180065e74  mov     r8, [rdi+110h]
0x180065e7b  mov     [rbp+57h+var_80], eax
0x180065e7e  mov     [rbp+57h+var_78], 1000000h
0x180065e86  cmp     [r8+4], r14b
0x180065e8a  jz      short loc_180065EA7
0x180065e8c  lea     r9, [r8+18h]
0x180065e90  cmp     [r9], r14d
0x180065e93  jnz     short loc_180065EAA
0x180065e95  cmp     [r9+4], r14d
0x180065e99  jnz     short loc_180065EAA
0x180065e9b  cmp     [r9+8], r14d
0x180065e9f  jnz     short loc_180065EAA
0x180065ea1  cmp     [r9+0Ch], r14d
0x180065ea5  jnz     short loc_180065EAA
0x180065ea7  mov     r9, r14
0x180065eaa  test    rbx, rbx
0x180065ead  jz      short loc_180065EC0
0x180065eaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065eb3  inc     rax
0x180065eb6  cmp     [rbx+rax], r14b
0x180065eba  jnz     short loc_180065EB3
0x180065ebc  inc     eax
0x180065ebe  jmp     short loc_180065ECC
0x180065ec0  lea     rbx, qword_180072C40
0x180065ec7  mov     eax, 1
0x180065ecc  mov     [rbp+57h+var_28], eax
0x180065ecf  lea     rdx, byte_180094E29
0x180065ed6  lea     rax, [rbp+57h+var_80]
0x180065eda  mov     [rbp+57h+var_30], rbx
0x180065ede  mov     [rbp+57h+var_40], rax
0x180065ee2  add     r8, 8
0x180065ee6  lea     rax, [rbp+57h+var_78]
0x180065eea  mov     [rbp+57h+var_24], r14d
0x180065eee  mov     [rbp+57h+var_50], rax
0x180065ef2  mov     rcx, rsi
0x180065ef5  lea     rax, [rbp+57h+var_70]
0x180065ef9  mov     [rbp+57h+var_38], 4
0x180065f01  mov     [rsp+0B0h+var_88], rax
0x180065f06  mov     [rsp+0B0h+var_90], 5
0x180065f0e  mov     [rbp+57h+var_48], 8
0x180065f16  call    _tlgWriteTransfer_EventWriteTransfer
0x180065f1b  cmp     [rdi+138h], r14d
0x180065f22  jnz     short loc_180065F5B
0x180065f24  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r14; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180065f2b  lea     rbx, [rdi+120h]
0x180065f32  jz      short loc_180065F58
0x180065f34  mov     dl, 1
0x180065f36  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180065f3b  mov     [rbx], rax
0x180065f3e  test    rax, rax
0x180065f41  jz      short loc_180065F5B
0x180065f43  mov     rcx, [rax]
0x180065f46  mov     [rbx+10h], rcx
0x180065f4a  mov     [rax], rbx
0x180065f4d  call    cs:__imp_GetCurrentThreadId
0x180065f53  mov     [rbx+18h], eax
0x180065f56  jmp     short loc_180065F5B
0x180065f58  mov     [rbx], r14
0x180065f5b  mov     rcx, [rbp+57h+var_20]
0x180065f5f  xor     rcx, rsp; StackCookie
0x180065f62  call    __security_check_cookie
0x180065f67  lea     r11, [rsp+0B0h+var_10]
0x180065f6f  mov     rbx, [r11+30h]
0x180065f73  mov     rsi, [r11+38h]
0x180065f77  mov     rsp, r11
0x180065f7a  pop     r14
0x180065f7c  pop     rdi
0x180065f7d  pop     rbp
0x180065f7e  retn
```
