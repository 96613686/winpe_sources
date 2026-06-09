# Windows::Telemetry::Service::Svc::StartActivity(void)

- ea: `0x180052b8c`
- end: `0x180052ce2`
- name: `?StartActivity@Svc@Service@Telemetry@Windows@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(Windows::Telemetry::Service::Svc *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18004fd80`

## callees

- `0x1800019cc`
- `0x180007660`
- `0x180016180`
- `0x180041c1c`
- `0x1800445d4`
- `0x180052b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052bf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052bf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052caf`

## pseudocode

```c
void __fastcall Windows::Telemetry::Service::Svc::StartActivity(Windows::Telemetry::Service::Svc *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdi
  __int64 v5; // r8
  int v6; // r9d
  char *v7; // rbx
  _QWORD *Local; // rax
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v12; // [rsp+60h] [rbp-38h]
  __int64 v13; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v15; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u )
  {
    v3 = *(_QWORD *)(v4 + 24);
    v2 = 0x400000000000LL;
    if ( (*(_QWORD *)(v4 + 16) & 0x400000000000LL) != 0 && (v3 & 0x400000000000LL) == v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = 0x1000000;
      v5 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v5 + 4)
        || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
        && !*(_DWORD *)(v5 + 28)
        && !*(_DWORD *)(v5 + 32)
        && !*(_DWORD *)(v5 + 36) )
      {
        v6 = 0;
      }
      p_CurrentThreadId = &CurrentThreadId;
      v15 = 4;
      v12 = &v10;
      v13 = 8;
      tlgWriteTransfer_EventWriteTransfer(v4, (int)&byte_180081F31, v5 + 8, v6, 4u, &v11);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v2) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v3,
                          v2);
      *(_QWORD *)v7 = Local;
      if ( Local )
      {
        *((_QWORD *)v7 + 2) = *Local;
        *Local = v7;
        *((_DWORD *)v7 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v7 = 0;
    }
  }
}

```

## disassembly

```asm
0x180052b8c  mov     [rsp+arg_8], rbx
0x180052b91  push    rdi
0x180052b92  sub     rsp, 90h
0x180052b99  mov     rax, cs:__security_cookie
0x180052ba0  xor     rax, rsp
0x180052ba3  mov     [rsp+98h+var_18], rax
0x180052bab  mov     rbx, rcx
0x180052bae  call    ?zInternalStart@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180052bb3  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180052bb8  mov     rdi, [rax+8]
0x180052bbc  mov     eax, [rdi]
0x180052bbe  cmp     eax, 5
0x180052bc1  jbe     loc_180052C7C
0x180052bc7  mov     rcx, [rdi+18h]
0x180052bcb  mov     rax, [rdi+10h]
0x180052bcf  mov     rdx, 400000000000h
0x180052bd9  test    rdx, rax
0x180052bdc  jz      loc_180052C7C
0x180052be2  mov     rax, rcx
0x180052be5  and     rax, rdx
0x180052be8  cmp     rax, rcx
0x180052beb  jnz     loc_180052C7C
0x180052bf1  call    cs:__imp_GetCurrentThreadId
0x180052bf7  mov     [rsp+98h+var_68], eax
0x180052bfb  mov     [rsp+98h+var_60], 1000000h
0x180052c04  mov     r8, [rbx+110h]
0x180052c0b  cmp     byte ptr [r8+4], 0
0x180052c10  jz      short loc_180052C31
0x180052c12  lea     r9, [r8+18h]
0x180052c16  cmp     dword ptr [r9], 0
0x180052c1a  jnz     short loc_180052C34
0x180052c1c  cmp     dword ptr [r9+4], 0
0x180052c21  jnz     short loc_180052C34
0x180052c23  cmp     dword ptr [r9+8], 0
0x180052c28  jnz     short loc_180052C34
0x180052c2a  cmp     dword ptr [r9+0Ch], 0
0x180052c2f  jnz     short loc_180052C34
0x180052c31  xor     r9d, r9d; int
0x180052c34  lea     rax, [rsp+98h+var_68]
0x180052c39  mov     [rsp+98h+var_28], rax
0x180052c3e  mov     ecx, 4
0x180052c43  mov     [rsp+98h+var_20], rcx
0x180052c48  lea     rax, [rsp+98h+var_60]
0x180052c4d  mov     [rsp+98h+var_38], rax
0x180052c52  mov     [rsp+98h+var_30], 8
0x180052c5b  add     r8, 8; int
0x180052c5f  lea     rax, [rsp+98h+var_58]
0x180052c64  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180052c69  mov     [rsp+98h+var_78], ecx; ULONG
0x180052c6d  lea     rdx, byte_180081F31; int
0x180052c74  mov     rcx, rdi; int
0x180052c77  call    _tlgWriteTransfer_EventWriteTransfer
0x180052c7c  cmp     dword ptr [rbx+138h], 0
0x180052c83  jnz     short loc_180052CC1
0x180052c85  add     rbx, 120h
0x180052c8c  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180052c94  jz      short loc_180052CBA
0x180052c96  mov     dl, 1
0x180052c98  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180052c9d  mov     [rbx], rax
0x180052ca0  test    rax, rax
0x180052ca3  jz      short loc_180052CC1
0x180052ca5  mov     rcx, [rax]
0x180052ca8  mov     [rbx+10h], rcx
0x180052cac  mov     [rax], rbx
0x180052caf  call    cs:__imp_GetCurrentThreadId
0x180052cb5  mov     [rbx+18h], eax
0x180052cb8  jmp     short loc_180052CC1
0x180052cba  mov     qword ptr [rbx], 0
0x180052cc1  mov     rcx, [rsp+98h+var_18]
0x180052cc9  xor     rcx, rsp; StackCookie
0x180052ccc  call    __security_check_cookie
0x180052cd1  mov     rbx, [rsp+98h+arg_8]
0x180052cd9  add     rsp, 90h
0x180052ce0  pop     rdi
0x180052ce1  retn
```
