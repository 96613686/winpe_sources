# DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StartActivity(void)

- ea: `0x18000ac94`
- end: `0x18000ae35`
- name: `?StartActivity@RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800085b0`

## callees

- `0x1800018dc`
- `0x1800042fc`
- `0x180008814`
- `0x180009170`
- `0x18000ac94`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae0a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000acfe`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000acfe`

## pseudocode

```c
void __fastcall DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::StartActivity(
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  RTL_SRWLOCK *v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  char *v12; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v16[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v17; // [rsp+60h] [rbp+7h]
  __int64 v18; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v20; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = DeviceCenterContextHandlersLogging::Provider();
  if ( *(_DWORD *)v3 > 5u
    && (*((_QWORD *)v3 + 2) & 0x200000000000LL) != 0
    && (*((_QWORD *)v3 + 3) & 0x200000000000LL) == *((_QWORD *)v3 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  v4 = SRWLock;
  *(_DWORD *)v2 = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  v5 = DeviceCenterContextHandlersLogging::Provider();
  v6 = v5;
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 )
  {
    v8 = *((_QWORD *)v5 + 3);
    v7 = *((_QWORD *)v6 + 2);
    if ( (v7 & 0x200000000000LL) != 0 )
    {
      v7 = v8 & 0x200000000000LL;
      if ( (v8 & 0x200000000000LL) == v8 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v10 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v15 = 0;
        if ( !*(_BYTE *)(v10 + 4)
          || (v11 = v10 + 24, !*(_DWORD *)(v10 + 24))
          && !*(_DWORD *)(v10 + 28)
          && !*(_DWORD *)(v10 + 32)
          && !*(_DWORD *)(v10 + 36) )
        {
          v11 = 0;
        }
        v18 = 8;
        v20 = 4;
        p_SRWLock = &SRWLock;
        v17 = &v15;
        tlgWriteTransfer_EventWriteTransfer(v6, byte_180010DB1, v10 + 8, v11, 4, v16);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v7,
                          1);
      *(_QWORD *)v12 = Local;
      if ( Local )
      {
        *((_QWORD *)v12 + 2) = *Local;
        *Local = v12;
        *((_DWORD *)v12 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v12 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000ac94  push    rbp
0x18000ac96  push    rbx
0x18000ac97  push    rdi
0x18000ac98  push    r14
0x18000ac9a  lea     rbp, [rsp-3Fh]
0x18000ac9f  sub     rsp, 98h
0x18000aca6  mov     rax, cs:__security_cookie
0x18000acad  xor     rax, rsp
0x18000acb0  mov     [rbp+57h+var_30], rax
0x18000acb4  lea     rdx, [rbp+57h+SRWLock]
0x18000acb8  mov     rbx, rcx
0x18000acbb  call    ?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000acc0  mov     rdi, [rbx+110h]
0x18000acc7  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000accc  mov     r14, 200000000000h
0x18000acd6  mov     edx, [rax]
0x18000acd8  cmp     edx, 5
0x18000acdb  jbe     short loc_18000AD06
0x18000acdd  mov     rcx, [rax+18h]
0x18000ace1  mov     rax, [rax+10h]
0x18000ace5  test    r14, rax
0x18000ace8  jz      short loc_18000AD06
0x18000acea  mov     rax, rcx
0x18000aced  and     rax, r14
0x18000acf0  cmp     rax, rcx
0x18000acf3  jnz     short loc_18000AD06
0x18000acf5  lea     rdx, [rdi+8]; ActivityId
0x18000acf9  mov     ecx, 3; ControlCode
0x18000acfe  call    cs:__imp_EventActivityIdControl
0x18000ad04  jmp     short loc_18000AD0D
0x18000ad06  xorps   xmm0, xmm0
0x18000ad09  movups  xmmword ptr [rdi+8], xmm0
0x18000ad0d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000ad11  mov     dword ptr [rdi], 1
0x18000ad17  test    rcx, rcx
0x18000ad1a  jz      short loc_18000AD22
0x18000ad1c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad22  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000ad27  mov     rdi, rax
0x18000ad2a  mov     ecx, [rax]
0x18000ad2c  cmp     ecx, 5
0x18000ad2f  jbe     loc_18000ADD7
0x18000ad35  mov     rax, [rax+18h]
0x18000ad39  mov     rcx, [rdi+10h]
0x18000ad3d  test    r14, rcx
0x18000ad40  jz      loc_18000ADD7
0x18000ad46  mov     rcx, rax
0x18000ad49  and     rcx, r14
0x18000ad4c  cmp     rcx, rax
0x18000ad4f  jnz     loc_18000ADD7
0x18000ad55  call    cs:__imp_GetCurrentThreadId
0x18000ad5b  mov     r8, [rbx+110h]
0x18000ad62  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000ad65  mov     [rbp+57h+var_78], 0
0x18000ad6d  cmp     byte ptr [r8+4], 0
0x18000ad72  jz      short loc_18000AD93
0x18000ad74  lea     r9, [r8+18h]
0x18000ad78  cmp     dword ptr [r9], 0
0x18000ad7c  jnz     short loc_18000AD96
0x18000ad7e  cmp     dword ptr [r9+4], 0
0x18000ad83  jnz     short loc_18000AD96
0x18000ad85  cmp     dword ptr [r9+8], 0
0x18000ad8a  jnz     short loc_18000AD96
0x18000ad8c  cmp     dword ptr [r9+0Ch], 0
0x18000ad91  jnz     short loc_18000AD96
0x18000ad93  xor     r9d, r9d
0x18000ad96  mov     ecx, 4
0x18000ad9b  mov     [rbp+57h+var_48], 8
0x18000ada3  lea     rax, [rbp+57h+SRWLock]
0x18000ada7  mov     [rbp+57h+var_38], rcx
0x18000adab  mov     [rbp+57h+var_40], rax
0x18000adaf  lea     rdx, byte_180010DB1
0x18000adb6  lea     rax, [rbp+57h+var_78]
0x18000adba  add     r8, 8
0x18000adbe  mov     [rbp+57h+var_50], rax
0x18000adc2  lea     rax, [rbp+57h+var_70]
0x18000adc6  mov     [rsp+0B0h+var_88], rax
0x18000adcb  mov     [rsp+0B0h+var_90], ecx
0x18000adcf  mov     rcx, rdi
0x18000add2  call    _tlgWriteTransfer_EventWriteTransfer
0x18000add7  cmp     dword ptr [rbx+138h], 0
0x18000adde  jnz     short loc_18000AE1C
0x18000ade0  add     rbx, 120h
0x18000ade7  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000adef  jz      short loc_18000AE15
0x18000adf1  mov     dl, 1
0x18000adf3  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000adf8  mov     [rbx], rax
0x18000adfb  test    rax, rax
0x18000adfe  jz      short loc_18000AE1C
0x18000ae00  mov     rcx, [rax]
0x18000ae03  mov     [rbx+10h], rcx
0x18000ae07  mov     [rax], rbx
0x18000ae0a  call    cs:__imp_GetCurrentThreadId
0x18000ae10  mov     [rbx+18h], eax
0x18000ae13  jmp     short loc_18000AE1C
0x18000ae15  mov     qword ptr [rbx], 0
0x18000ae1c  mov     rcx, [rbp+57h+var_30]
0x18000ae20  xor     rcx, rsp; StackCookie
0x18000ae23  call    __security_check_cookie
0x18000ae28  add     rsp, 98h
0x18000ae2f  pop     r14
0x18000ae31  pop     rdi
0x18000ae32  pop     rbx
0x18000ae33  pop     rbp
0x18000ae34  retn
```
