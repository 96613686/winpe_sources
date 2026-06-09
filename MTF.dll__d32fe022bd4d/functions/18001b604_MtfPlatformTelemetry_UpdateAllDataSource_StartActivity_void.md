# MtfPlatformTelemetry::UpdateAllDataSource::StartActivity(void)

- ea: `0x18001b604`
- end: `0x18001b775`
- name: `?StartActivity@UpdateAllDataSource@MtfPlatformTelemetry@@QEAAXXZ`
- size: `369`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateAllDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001c840`

## callees

- `0x18000163c`
- `0x180004d20`
- `0x1800053cc`
- `0x180018d00`
- `0x18001b604`
- `0x18002bca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b673`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b673`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b655`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b655`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b742`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b742`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateAllDataSource::StartActivity(
        MtfPlatformTelemetry::UpdateAllDataSource *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  _DWORD *v5; // rdi
  __int64 v6; // r8
  char *v7; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  _QWORD v10[9]; // [rsp+38h] [rbp-1h] BYREF

  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( **((_DWORD **)MtfPlatformTelemetry::Instance() + 1) <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v5 = (_DWORD *)*((_QWORD *)MtfPlatformTelemetry::Instance() + 1);
  if ( *v5 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v10[0] = 0;
    v6 = *((_QWORD *)this + 34);
    v10[7] = &SRWLock;
    v10[8] = 4;
    v10[5] = v10;
    v10[6] = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, &byte_180036187, v6 + 8);
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v7 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      LOBYTE(v3) = 1;
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          v3);
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
0x18001b604  mov     [rsp-8+arg_8], rbx
0x18001b609  mov     [rsp-8+arg_10], rdi
0x18001b60e  push    rbp
0x18001b60f  lea     rbp, [rsp-57h]
0x18001b614  sub     rsp, 90h
0x18001b61b  mov     rax, cs:__security_cookie
0x18001b622  xor     rax, rsp
0x18001b625  mov     [rbp+57h+var_10], rax
0x18001b629  mov     rbx, rcx
0x18001b62c  lea     rdx, [rbp+57h+SRWLock]
0x18001b630  call    ?LockExclusive@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b635  mov     rdi, [rbx+110h]
0x18001b63c  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b641  mov     rdx, [rax+8]
0x18001b645  mov     eax, [rdx]
0x18001b647  cmp     eax, 5
0x18001b64a  jbe     short loc_18001B65D
0x18001b64c  lea     rdx, [rdi+8]; ActivityId
0x18001b650  mov     ecx, 3; ControlCode
0x18001b655  call    cs:__imp_EventActivityIdControl
0x18001b65b  jmp     short loc_18001B664
0x18001b65d  xorps   xmm0, xmm0
0x18001b660  movups  xmmword ptr [rdi+8], xmm0
0x18001b664  mov     dword ptr [rdi], 1
0x18001b66a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001b66e  test    rcx, rcx
0x18001b671  jz      short loc_18001B679
0x18001b673  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b679  call    ?Instance@MtfPlatformTelemetry@@KAPEAV1@XZ; MtfPlatformTelemetry::Instance(void)
0x18001b67e  mov     rdi, [rax+8]
0x18001b682  mov     eax, [rdi]
0x18001b684  cmp     eax, 5
0x18001b687  jbe     loc_18001B70F
0x18001b68d  call    cs:__imp_GetCurrentThreadId
0x18001b693  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001b696  mov     [rbp+57h+var_58], 0
0x18001b69e  mov     r8, [rbx+110h]
0x18001b6a5  cmp     byte ptr [r8+4], 0
0x18001b6aa  jz      short loc_18001B6CB
0x18001b6ac  lea     r9, [r8+18h]
0x18001b6b0  cmp     dword ptr [r9], 0
0x18001b6b4  jnz     short loc_18001B6CE
0x18001b6b6  cmp     dword ptr [r9+4], 0
0x18001b6bb  jnz     short loc_18001B6CE
0x18001b6bd  cmp     dword ptr [r9+8], 0
0x18001b6c2  jnz     short loc_18001B6CE
0x18001b6c4  cmp     dword ptr [r9+0Ch], 0
0x18001b6c9  jnz     short loc_18001B6CE
0x18001b6cb  xor     r9d, r9d
0x18001b6ce  lea     rax, [rbp+57h+SRWLock]
0x18001b6d2  mov     [rbp+57h+var_20], rax
0x18001b6d6  mov     ecx, 4
0x18001b6db  mov     [rbp+57h+var_18], rcx
0x18001b6df  lea     rax, [rbp+57h+var_58]
0x18001b6e3  mov     [rbp+57h+var_30], rax
0x18001b6e7  mov     [rbp+57h+var_28], 8
0x18001b6ef  add     r8, 8
0x18001b6f3  lea     rax, [rbp+57h+var_50]
0x18001b6f7  mov     [rsp+90h+var_68], rax
0x18001b6fc  mov     [rsp+90h+var_70], ecx
0x18001b700  lea     rdx, byte_180036187
0x18001b707  mov     rcx, rdi
0x18001b70a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b70f  cmp     dword ptr [rbx+138h], 0
0x18001b716  jnz     short loc_18001B754
0x18001b718  add     rbx, 120h
0x18001b71f  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001b727  jz      short loc_18001B74D
0x18001b729  mov     dl, 1
0x18001b72b  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001b730  mov     [rbx], rax
0x18001b733  test    rax, rax
0x18001b736  jz      short loc_18001B754
0x18001b738  mov     rcx, [rax]
0x18001b73b  mov     [rbx+10h], rcx
0x18001b73f  mov     [rax], rbx
0x18001b742  call    cs:__imp_GetCurrentThreadId
0x18001b748  mov     [rbx+18h], eax
0x18001b74b  jmp     short loc_18001B754
0x18001b74d  mov     qword ptr [rbx], 0
0x18001b754  mov     rcx, [rbp+57h+var_10]
0x18001b758  xor     rcx, rsp; StackCookie
0x18001b75b  call    __security_check_cookie
0x18001b760  lea     r11, [rsp+90h+var_s0]
0x18001b768  mov     rbx, [r11+18h]
0x18001b76c  mov     rdi, [r11+20h]
0x18001b770  mov     rsp, r11
0x18001b773  pop     rbp
0x18001b774  retn
```
