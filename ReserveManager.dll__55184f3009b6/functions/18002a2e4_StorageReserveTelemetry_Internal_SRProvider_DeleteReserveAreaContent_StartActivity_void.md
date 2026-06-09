# StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StartActivity(void)

- ea: `0x18002a2e4`
- end: `0x18002a439`
- name: `?StartActivity@DeleteReserveAreaContent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800262e0`

## callees

- `0x1800013b4`
- `0x180003870`
- `0x180007990`
- `0x18002939c`
- `0x18002a2e4`
- `0x18002cfdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a406`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *this)
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

  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
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
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&byte_18004425B, v7 + 8, v8, 4u, &v13);
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
0x18002a2e4  mov     [rsp+arg_8], rbx
0x18002a2e9  push    rdi
0x18002a2ea  sub     rsp, 90h
0x18002a2f1  mov     rax, cs:__security_cookie
0x18002a2f8  xor     rax, rsp
0x18002a2fb  mov     [rsp+98h+var_18], rax
0x18002a303  mov     rbx, rcx
0x18002a306  call    ?zInternalStart@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002a30b  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a310  mov     rdi, rax
0x18002a313  mov     edx, [rax]
0x18002a315  cmp     edx, 5
0x18002a318  jbe     loc_18002A3D3
0x18002a31e  mov     rax, [rax+18h]
0x18002a322  mov     r8, 400000000000h
0x18002a32c  mov     rdx, [rdi+10h]
0x18002a330  test    r8, rdx
0x18002a333  jz      loc_18002A3D3
0x18002a339  mov     rcx, rax
0x18002a33c  and     rcx, r8
0x18002a33f  cmp     rcx, rax
0x18002a342  jnz     loc_18002A3D3
0x18002a348  call    cs:__imp_GetCurrentThreadId
0x18002a34e  mov     r8, [rbx+110h]
0x18002a355  mov     [rsp+98h+var_68], eax
0x18002a359  mov     [rsp+98h+var_60], 1000000h
0x18002a362  cmp     byte ptr [r8+4], 0
0x18002a367  jz      short loc_18002A388
0x18002a369  lea     r9, [r8+18h]
0x18002a36d  cmp     dword ptr [r9], 0
0x18002a371  jnz     short loc_18002A38B
0x18002a373  cmp     dword ptr [r9+4], 0
0x18002a378  jnz     short loc_18002A38B
0x18002a37a  cmp     dword ptr [r9+8], 0
0x18002a37f  jnz     short loc_18002A38B
0x18002a381  cmp     dword ptr [r9+0Ch], 0
0x18002a386  jnz     short loc_18002A38B
0x18002a388  xor     r9d, r9d; int
0x18002a38b  mov     ecx, 4
0x18002a390  mov     [rsp+98h+var_30], 8
0x18002a399  lea     rax, [rsp+98h+var_68]
0x18002a39e  mov     [rsp+98h+var_20], rcx
0x18002a3a3  mov     [rsp+98h+var_28], rax
0x18002a3a8  lea     rdx, byte_18004425B; int
0x18002a3af  lea     rax, [rsp+98h+var_60]
0x18002a3b4  add     r8, 8; int
0x18002a3b8  mov     [rsp+98h+var_38], rax
0x18002a3bd  lea     rax, [rsp+98h+var_58]
0x18002a3c2  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18002a3c7  mov     [rsp+98h+var_78], ecx; ULONG
0x18002a3cb  mov     rcx, rdi; int
0x18002a3ce  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a3d3  cmp     dword ptr [rbx+138h], 0
0x18002a3da  jnz     short loc_18002A418
0x18002a3dc  add     rbx, 120h
0x18002a3e3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002a3eb  jz      short loc_18002A411
0x18002a3ed  mov     dl, 1
0x18002a3ef  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002a3f4  mov     [rbx], rax
0x18002a3f7  test    rax, rax
0x18002a3fa  jz      short loc_18002A418
0x18002a3fc  mov     rcx, [rax]
0x18002a3ff  mov     [rbx+10h], rcx
0x18002a403  mov     [rax], rbx
0x18002a406  call    cs:__imp_GetCurrentThreadId
0x18002a40c  mov     [rbx+18h], eax
0x18002a40f  jmp     short loc_18002A418
0x18002a411  mov     qword ptr [rbx], 0
0x18002a418  mov     rcx, [rsp+98h+var_18]
0x18002a420  xor     rcx, rsp; StackCookie
0x18002a423  call    __security_check_cookie
0x18002a428  mov     rbx, [rsp+98h+arg_8]
0x18002a430  add     rsp, 90h
0x18002a437  pop     rdi
0x18002a438  retn
```
