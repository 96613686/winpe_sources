# StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StartActivity(void)

- ea: `0x18002a648`
- end: `0x18002a79d`
- name: `?StartActivity@MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800287e4`

## callees

- `0x1800013b4`
- `0x180003870`
- `0x180007990`
- `0x18002939c`
- `0x18002a648`
- `0x18002cfdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a76a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a6ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a76a`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rdi
  __int64 v5; // rax
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  int v8; // r9d
  char *v9; // rbx
  _QWORD *Local; // rax
  DWORD v11; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v14; // [rsp+60h] [rbp-38h]
  __int64 v15; // [rsp+68h] [rbp-30h]
  DWORD *v16; // [rsp+70h] [rbp-28h]
  __int64 v17; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v2 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  v4 = v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v5 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v4 + 2) & 0x400000000000LL) != 0 )
    {
      v3 = v5 & 0x400000000000LL;
      if ( (v5 & 0x400000000000LL) == v5 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v7 = *((_QWORD *)this + 34);
        v11 = CurrentThreadId;
        v12 = 0x1000000;
        if ( !*(_BYTE *)(v7 + 4)
          || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
          && !*(_DWORD *)(v7 + 28)
          && !*(_DWORD *)(v7 + 32)
          && !*(_DWORD *)(v7 + 36) )
        {
          v8 = 0;
        }
        v15 = 8;
        v17 = 4;
        v16 = &v11;
        v14 = &v12;
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&word_180043ACE, v7 + 8, v8, 4u, &v13);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v9 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          1);
      *(_QWORD *)v9 = Local;
      if ( Local )
      {
        *((_QWORD *)v9 + 2) = *Local;
        *Local = v9;
        *((_DWORD *)v9 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v9 = 0;
    }
  }
}

```

## disassembly

```asm
0x18002a648  mov     [rsp+arg_8], rbx
0x18002a64d  push    rdi
0x18002a64e  sub     rsp, 90h
0x18002a655  mov     rax, cs:__security_cookie
0x18002a65c  xor     rax, rsp
0x18002a65f  mov     [rsp+98h+var_18], rax
0x18002a667  mov     rbx, rcx
0x18002a66a  call    ?zInternalStart@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002a66f  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a674  mov     rdi, rax
0x18002a677  mov     edx, [rax]
0x18002a679  cmp     edx, 5
0x18002a67c  jbe     loc_18002A737
0x18002a682  mov     rax, [rax+18h]
0x18002a686  mov     r8, 400000000000h
0x18002a690  mov     rdx, [rdi+10h]
0x18002a694  test    r8, rdx
0x18002a697  jz      loc_18002A737
0x18002a69d  mov     rcx, rax
0x18002a6a0  and     rcx, r8
0x18002a6a3  cmp     rcx, rax
0x18002a6a6  jnz     loc_18002A737
0x18002a6ac  call    cs:__imp_GetCurrentThreadId
0x18002a6b2  mov     r8, [rbx+110h]
0x18002a6b9  mov     [rsp+98h+var_68], eax
0x18002a6bd  mov     [rsp+98h+var_60], 1000000h
0x18002a6c6  cmp     byte ptr [r8+4], 0
0x18002a6cb  jz      short loc_18002A6EC
0x18002a6cd  lea     r9, [r8+18h]
0x18002a6d1  cmp     dword ptr [r9], 0
0x18002a6d5  jnz     short loc_18002A6EF
0x18002a6d7  cmp     dword ptr [r9+4], 0
0x18002a6dc  jnz     short loc_18002A6EF
0x18002a6de  cmp     dword ptr [r9+8], 0
0x18002a6e3  jnz     short loc_18002A6EF
0x18002a6e5  cmp     dword ptr [r9+0Ch], 0
0x18002a6ea  jnz     short loc_18002A6EF
0x18002a6ec  xor     r9d, r9d; int
0x18002a6ef  mov     ecx, 4
0x18002a6f4  mov     [rsp+98h+var_30], 8
0x18002a6fd  lea     rax, [rsp+98h+var_68]
0x18002a702  mov     [rsp+98h+var_20], rcx
0x18002a707  mov     [rsp+98h+var_28], rax
0x18002a70c  lea     rdx, word_180043ACE; int
0x18002a713  lea     rax, [rsp+98h+var_60]
0x18002a718  add     r8, 8; int
0x18002a71c  mov     [rsp+98h+var_38], rax
0x18002a721  lea     rax, [rsp+98h+var_58]
0x18002a726  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18002a72b  mov     [rsp+98h+var_78], ecx; ULONG
0x18002a72f  mov     rcx, rdi; int
0x18002a732  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a737  cmp     dword ptr [rbx+138h], 0
0x18002a73e  jnz     short loc_18002A77C
0x18002a740  add     rbx, 120h
0x18002a747  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a74f  jz      short loc_18002A775
0x18002a751  mov     dl, 1
0x18002a753  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002a758  mov     [rbx], rax
0x18002a75b  test    rax, rax
0x18002a75e  jz      short loc_18002A77C
0x18002a760  mov     rcx, [rax]
0x18002a763  mov     [rbx+10h], rcx
0x18002a767  mov     [rax], rbx
0x18002a76a  call    cs:__imp_GetCurrentThreadId
0x18002a770  mov     [rbx+18h], eax
0x18002a773  jmp     short loc_18002A77C
0x18002a775  mov     qword ptr [rbx], 0
0x18002a77c  mov     rcx, [rsp+98h+var_18]
0x18002a784  xor     rcx, rsp; StackCookie
0x18002a787  call    __security_check_cookie
0x18002a78c  mov     rbx, [rsp+98h+arg_8]
0x18002a794  add     rsp, 90h
0x18002a79b  pop     rdi
0x18002a79c  retn
```
