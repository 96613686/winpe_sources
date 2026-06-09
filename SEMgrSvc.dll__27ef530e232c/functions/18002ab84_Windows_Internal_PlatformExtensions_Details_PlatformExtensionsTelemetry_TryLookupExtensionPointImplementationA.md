# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x18002ab84`
- end: `0x18002ad4e`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `458`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002d124`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x18001da08`
- `0x18001eb04`
- `0x180028704`
- `0x18002ab84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ac1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ac1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ac5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ac5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ac65`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002abfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002abfd`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  RTL_SRWLOCK *v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // r8
  PCWSTR StringRawBuffer; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  const GUID *v14; // r9
  __int64 v15; // rax
  int v16; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v20; // [rsp+60h] [rbp-9h]
  __int64 v21; // [rsp+68h] [rbp-1h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+7h]
  __int64 v23; // [rsp+78h] [rbp+Fh]
  PCWSTR v24; // [rsp+80h] [rbp+17h]
  int v25; // [rsp+88h] [rbp+1Fh]
  int v26; // [rsp+8Ch] [rbp+23h]

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u
    && (*((_QWORD *)v5 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v5 + 3) & 0x200000000000LL) == *((_QWORD *)v5 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  }
  else
  {
    *(_OWORD *)(v4 + 8) = 0;
  }
  v6 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v9 = (__int64)v7;
  if ( *(_DWORD *)v7 > 5u )
  {
    v10 = *((_QWORD *)v7 + 3);
    v8 = *((_QWORD *)v7 + 2);
    if ( (v8 & 0x200000000000LL) != 0 )
    {
      v8 = v10 & 0x200000000000LL;
      if ( (v10 & 0x200000000000LL) == v10 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
        CurrentThreadId = GetCurrentThreadId();
        v13 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v18 = 0;
        if ( !*(_BYTE *)(v13 + 4)
          || (v14 = (const GUID *)(v13 + 24), !*(_DWORD *)(v13 + 24))
          && !*(_DWORD *)(v13 + 28)
          && !*(_DWORD *)(v13 + 32)
          && !*(_DWORD *)(v13 + 36) )
        {
          v14 = 0;
        }
        if ( StringRawBuffer )
        {
          v15 = -1;
          do
            ++v15;
          while ( StringRawBuffer[v15] );
          v16 = 2 * v15 + 2;
        }
        else
        {
          StringRawBuffer = &qword_1800A6D00;
          v16 = 2;
        }
        v25 = v16;
        v24 = StringRawBuffer;
        p_SRWLock = &SRWLock;
        v26 = 0;
        v20 = &v18;
        v23 = 4;
        v21 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v9,
          (unsigned __int8 *)word_18011AEBA,
          (const GUID *)(v13 + 8),
          v14,
          5u,
          &v19);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288),
      v8);
}

```

## disassembly

```asm
0x18002ab84  mov     [rsp-8+arg_10], rbx
0x18002ab89  mov     [rsp-8+arg_18], rsi
0x18002ab8e  push    rbp
0x18002ab8f  push    rdi
0x18002ab90  push    r12
0x18002ab92  push    r14
0x18002ab94  push    r15
0x18002ab96  lea     rbp, [rsp-37h]
0x18002ab9b  sub     rsp, 0A0h
0x18002aba2  mov     rax, cs:__security_cookie
0x18002aba9  xor     rax, rsp
0x18002abac  mov     [rbp+57h+var_30], rax
0x18002abb0  mov     r14, rdx
0x18002abb3  mov     rsi, rcx
0x18002abb6  lea     rdx, [rbp+57h+SRWLock]
0x18002abba  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002abbf  mov     rbx, [rsi+110h]
0x18002abc6  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002abcb  mov     r12, 200000000000h
0x18002abd5  mov     edx, [rax]
0x18002abd7  cmp     edx, 5
0x18002abda  jbe     short loc_18002AC05
0x18002abdc  mov     rcx, [rax+18h]
0x18002abe0  mov     rax, [rax+10h]
0x18002abe4  test    r12, rax
0x18002abe7  jz      short loc_18002AC05
0x18002abe9  mov     rax, rcx
0x18002abec  and     rax, r12
0x18002abef  cmp     rax, rcx
0x18002abf2  jnz     short loc_18002AC05
0x18002abf4  lea     rdx, [rbx+8]; ActivityId
0x18002abf8  mov     ecx, 3; ControlCode
0x18002abfd  call    cs:__imp_EventActivityIdControl
0x18002ac03  jmp     short loc_18002AC0C
0x18002ac05  xorps   xmm0, xmm0
0x18002ac08  movups  xmmword ptr [rbx+8], xmm0
0x18002ac0c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002ac10  xor     r15d, r15d
0x18002ac13  mov     dword ptr [rbx], 1
0x18002ac19  test    rcx, rcx
0x18002ac1c  jz      short loc_18002AC24
0x18002ac1e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ac24  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002ac29  mov     rdi, rax
0x18002ac2c  mov     ecx, [rax]
0x18002ac2e  cmp     ecx, 5
0x18002ac31  jbe     loc_18002AD14
0x18002ac37  mov     r8, [rax+18h]
0x18002ac3b  mov     rdx, [rax+10h]
0x18002ac3f  test    r12, rdx
0x18002ac42  jz      loc_18002AD14
0x18002ac48  mov     rdx, r8
0x18002ac4b  and     rdx, r12
0x18002ac4e  cmp     rdx, r8
0x18002ac51  jnz     loc_18002AD14
0x18002ac57  xor     edx, edx; length
0x18002ac59  mov     rcx, r14; string
0x18002ac5c  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ac62  mov     rbx, rax
0x18002ac65  call    cs:__imp_GetCurrentThreadId
0x18002ac6b  mov     r8, [rsi+110h]
0x18002ac72  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002ac75  mov     [rbp+57h+var_88], r15
0x18002ac79  cmp     [r8+4], r15b
0x18002ac7d  jz      short loc_18002AC9A
0x18002ac7f  lea     r9, [r8+18h]
0x18002ac83  cmp     [r9], r15d
0x18002ac86  jnz     short loc_18002AC9D
0x18002ac88  cmp     [r9+4], r15d
0x18002ac8c  jnz     short loc_18002AC9D
0x18002ac8e  cmp     [r9+8], r15d
0x18002ac92  jnz     short loc_18002AC9D
0x18002ac94  cmp     [r9+0Ch], r15d
0x18002ac98  jnz     short loc_18002AC9D
0x18002ac9a  mov     r9, r15
0x18002ac9d  test    rbx, rbx
0x18002aca0  jz      short loc_18002ACB9
0x18002aca2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aca6  inc     rax
0x18002aca9  cmp     [rbx+rax*2], r15w
0x18002acae  jnz     short loc_18002ACA6
0x18002acb0  lea     eax, ds:2[rax*2]
0x18002acb7  jmp     short loc_18002ACC5
0x18002acb9  lea     rbx, qword_1800A6D00
0x18002acc0  mov     eax, 2
0x18002acc5  mov     [rbp+57h+var_38], eax
0x18002acc8  lea     rdx, word_18011AEBA
0x18002accf  lea     rax, [rbp+57h+SRWLock]
0x18002acd3  mov     [rbp+57h+var_40], rbx
0x18002acd7  mov     [rbp+57h+var_50], rax
0x18002acdb  add     r8, 8
0x18002acdf  lea     rax, [rbp+57h+var_88]
0x18002ace3  mov     [rbp+57h+var_34], r15d
0x18002ace7  mov     [rbp+57h+var_60], rax
0x18002aceb  mov     rcx, rdi
0x18002acee  lea     rax, [rbp+57h+var_80]
0x18002acf2  mov     [rbp+57h+var_48], 4
0x18002acfa  mov     [rsp+0C0h+var_98], rax
0x18002acff  mov     [rsp+0C0h+var_A0], 5
0x18002ad07  mov     [rbp+57h+var_58], 8
0x18002ad0f  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ad14  lea     rcx, [rsi+120h]; this
0x18002ad1b  cmp     [rcx+18h], r15d
0x18002ad1f  jnz     short loc_18002AD26
0x18002ad21  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002ad26  mov     rcx, [rbp+57h+var_30]
0x18002ad2a  xor     rcx, rsp; StackCookie
0x18002ad2d  call    __security_check_cookie
0x18002ad32  lea     r11, [rsp+0C0h+var_20]
0x18002ad3a  mov     rbx, [r11+40h]
0x18002ad3e  mov     rsi, [r11+48h]
0x18002ad42  mov     rsp, r11
0x18002ad45  pop     r15
0x18002ad47  pop     r14
0x18002ad49  pop     r12
0x18002ad4b  pop     rdi
0x18002ad4c  pop     rbp
0x18002ad4d  retn
```
