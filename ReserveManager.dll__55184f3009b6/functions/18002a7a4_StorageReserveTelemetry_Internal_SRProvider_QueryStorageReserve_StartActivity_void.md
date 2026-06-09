# StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(void)

- ea: `0x18002a7a4`
- end: `0x18002a91b`
- name: `?StartActivity@QueryStorageReserve@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `375`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002980c`

## callees

- `0x1800013b4`
- `0x180003870`
- `0x180007990`
- `0x180028738`
- `0x18002939c`
- `0x18002a7a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a819`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a819`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a7fb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002a7fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a8e8`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // r9d
  char *v8; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-19h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+58h] [rbp+7h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp+27h]
  __int64 v14; // [rsp+80h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+88h] [rbp+37h]
  __int64 v16; // [rsp+90h] [rbp+3Fh]

  v11[1] = -2;
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StorageReserveTelemetry::Internal::StorageReserveProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  v4 = (int)v3;
  v5 = *(unsigned int *)v3;
  if ( (unsigned int)v5 > 5 )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v11[0] = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_SRWLock = &SRWLock;
    v16 = 4;
    v13 = v11;
    v14 = 8;
    tlgWriteTransfer_EventWriteTransfer(v4, (int)&word_1800447C6, v6 + 8, v7, 4u, &v12);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v5,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x18002a7a4  mov     rax, rsp
0x18002a7a7  push    rbp
0x18002a7a8  lea     rbp, [rax-5Fh]
0x18002a7ac  sub     rsp, 0A0h
0x18002a7b3  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x18002a7bb  mov     [rax+10h], rbx
0x18002a7bf  mov     [rax+18h], rdi
0x18002a7c3  mov     rax, cs:__security_cookie
0x18002a7ca  xor     rax, rsp
0x18002a7cd  mov     [rbp+57h+var_10], rax
0x18002a7d1  mov     rbx, rcx
0x18002a7d4  lea     rdx, [rbp+57h+SRWLock]
0x18002a7d8  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002a7dd  mov     rdi, [rbx+110h]
0x18002a7e4  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a7e9  mov     r8d, [rax]
0x18002a7ec  cmp     r8d, 5
0x18002a7f0  jbe     short loc_18002A803
0x18002a7f2  lea     rdx, [rdi+8]; ActivityId
0x18002a7f6  mov     ecx, 3; ControlCode
0x18002a7fb  call    cs:__imp_EventActivityIdControl
0x18002a801  jmp     short loc_18002A80A
0x18002a803  xorps   xmm0, xmm0
0x18002a806  movups  xmmword ptr [rdi+8], xmm0
0x18002a80a  mov     dword ptr [rdi], 1
0x18002a810  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18002a814  test    rcx, rcx
0x18002a817  jz      short loc_18002A820
0x18002a819  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a81f  nop
0x18002a820  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a825  mov     rdi, rax
0x18002a828  mov     ecx, [rax]
0x18002a82a  cmp     ecx, 5
0x18002a82d  jbe     loc_18002A8B5
0x18002a833  call    cs:__imp_GetCurrentThreadId
0x18002a839  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002a83c  mov     [rbp+57h+var_68], 0
0x18002a844  mov     r8, [rbx+110h]
0x18002a84b  cmp     byte ptr [r8+4], 0
0x18002a850  jz      short loc_18002A871
0x18002a852  lea     r9, [r8+18h]
0x18002a856  cmp     dword ptr [r9], 0
0x18002a85a  jnz     short loc_18002A874
0x18002a85c  cmp     dword ptr [r9+4], 0
0x18002a861  jnz     short loc_18002A874
0x18002a863  cmp     dword ptr [r9+8], 0
0x18002a868  jnz     short loc_18002A874
0x18002a86a  cmp     dword ptr [r9+0Ch], 0
0x18002a86f  jnz     short loc_18002A874
0x18002a871  xor     r9d, r9d; int
0x18002a874  lea     rax, [rbp+57h+SRWLock]
0x18002a878  mov     [rbp+57h+var_20], rax
0x18002a87c  mov     ecx, 4
0x18002a881  mov     [rbp+57h+var_18], rcx
0x18002a885  lea     rax, [rbp+57h+var_68]
0x18002a889  mov     [rbp+57h+var_30], rax
0x18002a88d  mov     [rbp+57h+var_28], 8
0x18002a895  add     r8, 8; int
0x18002a899  lea     rax, [rbp+57h+var_50]
0x18002a89d  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x18002a8a2  mov     [rsp+0A0h+var_80], ecx; ULONG
0x18002a8a6  lea     rdx, word_1800447C6; int
0x18002a8ad  mov     rcx, rdi; int
0x18002a8b0  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a8b5  cmp     dword ptr [rbx+138h], 0
0x18002a8bc  jnz     short loc_18002A8FA
0x18002a8be  add     rbx, 120h
0x18002a8c5  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a8cd  jz      short loc_18002A8F3
0x18002a8cf  mov     dl, 1
0x18002a8d1  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002a8d6  mov     [rbx], rax
0x18002a8d9  test    rax, rax
0x18002a8dc  jz      short loc_18002A8FA
0x18002a8de  mov     rcx, [rax]
0x18002a8e1  mov     [rbx+10h], rcx
0x18002a8e5  mov     [rax], rbx
0x18002a8e8  call    cs:__imp_GetCurrentThreadId
0x18002a8ee  mov     [rbx+18h], eax
0x18002a8f1  jmp     short loc_18002A8FA
0x18002a8f3  mov     qword ptr [rbx], 0
0x18002a8fa  mov     rcx, [rbp+57h+var_10]
0x18002a8fe  xor     rcx, rsp; StackCookie
0x18002a901  call    __security_check_cookie
0x18002a906  lea     r11, [rsp+0A0h+var_s0]
0x18002a90e  mov     rbx, [r11+18h]
0x18002a912  mov     rdi, [r11+20h]
0x18002a916  mov     rsp, r11
0x18002a919  pop     rbp
0x18002a91a  retn
```
