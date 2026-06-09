# StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree::StartActivity(void)

- ea: `0x18002a924`
- end: `0x18002aa79`
- name: `?StartActivity@SetReserveAreaOnFileTree@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `341`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002a1fc`

## callees

- `0x1800013b4`
- `0x180003870`
- `0x180007990`
- `0x18002939c`
- `0x18002a924`
- `0x18002cfdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a988`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a988`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa46`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::SetReserveAreaOnFileTree *this)
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
        tlgWriteTransfer_EventWriteTransfer((int)v4, (int)&byte_1800445ED, v7 + 8, v8, 4u, &v13);
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
0x18002a924  mov     [rsp+arg_8], rbx
0x18002a929  push    rdi
0x18002a92a  sub     rsp, 90h
0x18002a931  mov     rax, cs:__security_cookie
0x18002a938  xor     rax, rsp
0x18002a93b  mov     [rsp+98h+var_18], rax
0x18002a943  mov     rbx, rcx
0x18002a946  call    ?zInternalStart@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002a94b  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002a950  mov     rdi, rax
0x18002a953  mov     edx, [rax]
0x18002a955  cmp     edx, 5
0x18002a958  jbe     loc_18002AA13
0x18002a95e  mov     rax, [rax+18h]
0x18002a962  mov     r8, 400000000000h
0x18002a96c  mov     rdx, [rdi+10h]
0x18002a970  test    r8, rdx
0x18002a973  jz      loc_18002AA13
0x18002a979  mov     rcx, rax
0x18002a97c  and     rcx, r8
0x18002a97f  cmp     rcx, rax
0x18002a982  jnz     loc_18002AA13
0x18002a988  call    cs:__imp_GetCurrentThreadId
0x18002a98e  mov     r8, [rbx+110h]
0x18002a995  mov     [rsp+98h+var_68], eax
0x18002a999  mov     [rsp+98h+var_60], 1000000h
0x18002a9a2  cmp     byte ptr [r8+4], 0
0x18002a9a7  jz      short loc_18002A9C8
0x18002a9a9  lea     r9, [r8+18h]
0x18002a9ad  cmp     dword ptr [r9], 0
0x18002a9b1  jnz     short loc_18002A9CB
0x18002a9b3  cmp     dword ptr [r9+4], 0
0x18002a9b8  jnz     short loc_18002A9CB
0x18002a9ba  cmp     dword ptr [r9+8], 0
0x18002a9bf  jnz     short loc_18002A9CB
0x18002a9c1  cmp     dword ptr [r9+0Ch], 0
0x18002a9c6  jnz     short loc_18002A9CB
0x18002a9c8  xor     r9d, r9d; int
0x18002a9cb  mov     ecx, 4
0x18002a9d0  mov     [rsp+98h+var_30], 8
0x18002a9d9  lea     rax, [rsp+98h+var_68]
0x18002a9de  mov     [rsp+98h+var_20], rcx
0x18002a9e3  mov     [rsp+98h+var_28], rax
0x18002a9e8  lea     rdx, byte_1800445ED; int
0x18002a9ef  lea     rax, [rsp+98h+var_60]
0x18002a9f4  add     r8, 8; int
0x18002a9f8  mov     [rsp+98h+var_38], rax
0x18002a9fd  lea     rax, [rsp+98h+var_58]
0x18002aa02  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18002aa07  mov     [rsp+98h+var_78], ecx; ULONG
0x18002aa0b  mov     rcx, rdi; int
0x18002aa0e  call    _tlgWriteTransfer_EventWriteTransfer
0x18002aa13  cmp     dword ptr [rbx+138h], 0
0x18002aa1a  jnz     short loc_18002AA58
0x18002aa1c  add     rbx, 120h
0x18002aa23  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18002aa2b  jz      short loc_18002AA51
0x18002aa2d  mov     dl, 1
0x18002aa2f  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18002aa34  mov     [rbx], rax
0x18002aa37  test    rax, rax
0x18002aa3a  jz      short loc_18002AA58
0x18002aa3c  mov     rcx, [rax]
0x18002aa3f  mov     [rbx+10h], rcx
0x18002aa43  mov     [rax], rbx
0x18002aa46  call    cs:__imp_GetCurrentThreadId
0x18002aa4c  mov     [rbx+18h], eax
0x18002aa4f  jmp     short loc_18002AA58
0x18002aa51  mov     qword ptr [rbx], 0
0x18002aa58  mov     rcx, [rsp+98h+var_18]
0x18002aa60  xor     rcx, rsp; StackCookie
0x18002aa63  call    __security_check_cookie
0x18002aa68  mov     rbx, [rsp+98h+arg_8]
0x18002aa70  add     rsp, 90h
0x18002aa77  pop     rdi
0x18002aa78  retn
```
