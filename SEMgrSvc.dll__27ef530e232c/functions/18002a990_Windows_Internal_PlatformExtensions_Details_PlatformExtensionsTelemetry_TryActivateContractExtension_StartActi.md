# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x18002a990`
- end: `0x18002ab7c`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `492`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002c538`

## callees

- `0x1800010f4`
- `0x1800049a0`
- `0x18001da08`
- `0x18001eb04`
- `0x180028704`
- `0x18002a990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aa2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aa2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002aa6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa78`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002aa0d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002aa0d`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // rax
  PCWSTR StringRawBuffer; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  const GUID *v18; // r9
  __int64 v19; // rax
  int v20; // eax
  int v21; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v23; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-39h]
  __int64 v26; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v28; // [rsp+88h] [rbp-21h]
  PCWSTR v29; // [rsp+90h] [rbp-19h]
  int v30; // [rsp+98h] [rbp-11h]
  int v31; // [rsp+9Ch] [rbp-Dh]
  int *v32; // [rsp+A0h] [rbp-9h]
  __int64 v33; // [rsp+A8h] [rbp-1h]
  __int64 v34; // [rsp+B0h] [rbp+7h]
  __int64 v35; // [rsp+B8h] [rbp+Fh]

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u
    && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  }
  else
  {
    *(_OWORD *)(v8 + 8) = 0;
  }
  v10 = SRWLock;
  *(_DWORD *)v8 = 1;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v13 = (__int64)v11;
  if ( *(_DWORD *)v11 > 5u )
  {
    v14 = *((_QWORD *)v11 + 3);
    v12 = *(_QWORD *)(v13 + 16);
    if ( (v12 & 0x400000000000LL) != 0 )
    {
      v12 = v14 & 0x400000000000LL;
      if ( (v14 & 0x400000000000LL) == v14 )
      {
        v21 = a3;
        StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
        CurrentThreadId = GetCurrentThreadId();
        v17 = *(_QWORD *)(a1 + 272);
        LODWORD(SRWLock) = CurrentThreadId;
        v23 = 0;
        if ( !*(_BYTE *)(v17 + 4)
          || (v18 = (const GUID *)(v17 + 24), !*(_DWORD *)(v17 + 24))
          && !*(_DWORD *)(v17 + 28)
          && !*(_DWORD *)(v17 + 32)
          && !*(_DWORD *)(v17 + 36) )
        {
          v18 = 0;
        }
        v34 = a4;
        v32 = &v21;
        v35 = 16;
        v33 = 4;
        if ( StringRawBuffer )
        {
          v19 = -1;
          do
            ++v19;
          while ( StringRawBuffer[v19] );
          v20 = 2 * v19 + 2;
        }
        else
        {
          StringRawBuffer = &qword_1800A6D00;
          v20 = 2;
        }
        v30 = v20;
        v29 = StringRawBuffer;
        p_SRWLock = &SRWLock;
        v31 = 0;
        v25 = &v23;
        v28 = 4;
        v26 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v13,
          (unsigned __int8 *)byte_18011B637,
          (const GUID *)(v17 + 8),
          v18,
          7u,
          &v24);
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v12);
}

```

## disassembly

```asm
0x18002a990  mov     [rsp-8+arg_18], rbx
0x18002a995  push    rbp
0x18002a996  push    rsi
0x18002a997  push    rdi
0x18002a998  push    r12
0x18002a99a  push    r13
0x18002a99c  push    r14
0x18002a99e  push    r15
0x18002a9a0  lea     rbp, [rsp-27h]
0x18002a9a5  sub     rsp, 0D0h
0x18002a9ac  mov     rax, cs:__security_cookie
0x18002a9b3  xor     rax, rsp
0x18002a9b6  mov     [rbp+57h+var_40], rax
0x18002a9ba  mov     r14, rdx
0x18002a9bd  mov     r15, r9
0x18002a9c0  lea     rdx, [rbp+57h+SRWLock]
0x18002a9c4  mov     ebx, r8d
0x18002a9c7  mov     rsi, rcx
0x18002a9ca  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002a9cf  mov     rdi, [rsi+110h]
0x18002a9d6  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002a9db  mov     r13, 400000000000h
0x18002a9e5  mov     ecx, [rax]
0x18002a9e7  cmp     ecx, 5
0x18002a9ea  jbe     short loc_18002AA15
0x18002a9ec  mov     rcx, [rax+18h]
0x18002a9f0  mov     rax, [rax+10h]
0x18002a9f4  test    r13, rax
0x18002a9f7  jz      short loc_18002AA15
0x18002a9f9  mov     rax, rcx
0x18002a9fc  and     rax, r13
0x18002a9ff  cmp     rax, rcx
0x18002aa02  jnz     short loc_18002AA15
0x18002aa04  lea     rdx, [rdi+8]; ActivityId
0x18002aa08  mov     ecx, 3; ControlCode
0x18002aa0d  call    cs:__imp_EventActivityIdControl
0x18002aa13  jmp     short loc_18002AA1C
0x18002aa15  xorps   xmm0, xmm0
0x18002aa18  movups  xmmword ptr [rdi+8], xmm0
0x18002aa1c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002aa20  xor     r12d, r12d
0x18002aa23  mov     dword ptr [rdi], 1
0x18002aa29  test    rcx, rcx
0x18002aa2c  jz      short loc_18002AA34
0x18002aa2e  call    cs:__imp_ReleaseSRWLockExclusive
0x18002aa34  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002aa39  mov     rdi, rax
0x18002aa3c  mov     ecx, [rax]
0x18002aa3e  cmp     ecx, 5
0x18002aa41  jbe     loc_18002AB43
0x18002aa47  mov     rax, [rax+18h]
0x18002aa4b  mov     rdx, [rdi+10h]
0x18002aa4f  test    r13, rdx
0x18002aa52  jz      loc_18002AB43
0x18002aa58  mov     rdx, rax
0x18002aa5b  and     rdx, r13
0x18002aa5e  cmp     rdx, rax
0x18002aa61  jnz     loc_18002AB43
0x18002aa67  xor     edx, edx; length
0x18002aa69  mov     [rbp+57h+var_D0], ebx
0x18002aa6c  mov     rcx, r14; string
0x18002aa6f  call    cs:__imp_WindowsGetStringRawBuffer
0x18002aa75  mov     rbx, rax
0x18002aa78  call    cs:__imp_GetCurrentThreadId
0x18002aa7e  mov     r8, [rsi+110h]
0x18002aa85  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002aa88  mov     [rbp+57h+var_C0], r12
0x18002aa8c  cmp     [r8+4], r12b
0x18002aa90  jz      short loc_18002AAAD
0x18002aa92  lea     r9, [r8+18h]
0x18002aa96  cmp     [r9], r12d
0x18002aa99  jnz     short loc_18002AAB0
0x18002aa9b  cmp     [r9+4], r12d
0x18002aa9f  jnz     short loc_18002AAB0
0x18002aaa1  cmp     [r9+8], r12d
0x18002aaa5  jnz     short loc_18002AAB0
0x18002aaa7  cmp     [r9+0Ch], r12d
0x18002aaab  jnz     short loc_18002AAB0
0x18002aaad  mov     r9, r12
0x18002aab0  mov     [rbp+57h+var_50], r15
0x18002aab4  lea     rax, [rbp+57h+var_D0]
0x18002aab8  mov     [rbp+57h+var_60], rax
0x18002aabc  mov     [rbp+57h+var_48], 10h
0x18002aac4  mov     [rbp+57h+var_58], 4
0x18002aacc  test    rbx, rbx
0x18002aacf  jz      short loc_18002AAE8
0x18002aad1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aad5  inc     rax
0x18002aad8  cmp     [rbx+rax*2], r12w
0x18002aadd  jnz     short loc_18002AAD5
0x18002aadf  lea     eax, ds:2[rax*2]
0x18002aae6  jmp     short loc_18002AAF4
0x18002aae8  lea     rbx, qword_1800A6D00
0x18002aaef  mov     eax, 2
0x18002aaf4  mov     [rbp+57h+var_68], eax
0x18002aaf7  lea     rdx, byte_18011B637
0x18002aafe  lea     rax, [rbp+57h+SRWLock]
0x18002ab02  mov     [rbp+57h+var_70], rbx
0x18002ab06  mov     [rbp+57h+var_80], rax
0x18002ab0a  add     r8, 8
0x18002ab0e  lea     rax, [rbp+57h+var_C0]
0x18002ab12  mov     [rbp+57h+var_64], r12d
0x18002ab16  mov     [rbp+57h+var_90], rax
0x18002ab1a  mov     rcx, rdi
0x18002ab1d  lea     rax, [rbp+57h+var_B0]
0x18002ab21  mov     [rbp+57h+var_78], 4
0x18002ab29  mov     [rsp+100h+var_D8], rax
0x18002ab2e  mov     [rsp+100h+var_E0], 7
0x18002ab36  mov     [rbp+57h+var_88], 8
0x18002ab3e  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ab43  lea     rcx, [rsi+120h]; this
0x18002ab4a  cmp     [rcx+18h], r12d
0x18002ab4e  jnz     short loc_18002AB55
0x18002ab50  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002ab55  mov     rcx, [rbp+57h+var_40]
0x18002ab59  xor     rcx, rsp; StackCookie
0x18002ab5c  call    __security_check_cookie
0x18002ab61  mov     rbx, [rsp+100h+arg_18]
0x18002ab69  add     rsp, 0D0h
0x18002ab70  pop     r15
0x18002ab72  pop     r14
0x18002ab74  pop     r13
0x18002ab76  pop     r12
0x18002ab78  pop     rdi
0x18002ab79  pop     rsi
0x18002ab7a  pop     rbp
0x18002ab7b  retn
```
