# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ae3c`
- end: `0x18000afaa`
- name: `?Stop@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `366`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180007a10`

## callees

- `0x1800018dc`
- `0x1800054f0`
- `0x180008214`
- `0x180008814`
- `0x180009170`
- `0x18000ae3c`
- `0x18000c966`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ae9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aef2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aef2`

## pseudocode

```c
void __fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  RTL_SRWLOCK *v6; // rcx
  int v7; // edi
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  const struct wil::FailureInfo *v13; // rdx
  DWORD v14; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v18; // [rsp+70h] [rbp-90h]
  __int64 v19; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  DWORD *v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h]

  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v17, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v17, v13);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = SRWLock;
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( v7 )
  {
    v8 = DeviceCenterContextHandlersLogging::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v12 = a1[34];
        v14 = CurrentThreadId;
        LODWORD(SRWLock) = a2;
        v22 = &v14;
        v16 = 0x1000000;
        p_SRWLock = &SRWLock;
        v23 = 4;
        v18 = &v16;
        v21 = 4;
        v19 = 8;
        tlgWriteTransfer_EventWriteTransfer(v9, (unsigned __int8 *)&word_180010E36, (const GUID *)(v12 + 8), 0, 5u, v17);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000ae3c  push    rbp
0x18000ae3e  push    rbx
0x18000ae3f  push    rsi
0x18000ae40  push    rdi
0x18000ae41  lea     rbp, [rsp-8]
0x18000ae46  sub     rsp, 108h
0x18000ae4d  mov     rax, cs:__security_cookie
0x18000ae54  xor     rax, rsp
0x18000ae57  mov     [rbp+20h+var_30], rax
0x18000ae5b  mov     esi, edx
0x18000ae5d  mov     rbx, rcx
0x18000ae60  lea     rdx, [rsp+120h+SRWLock]
0x18000ae65  call    ?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ae6a  mov     rax, [rbx+110h]
0x18000ae71  mov     edi, [rax+0F8h]
0x18000ae77  cmp     edi, 1
0x18000ae7a  jl      loc_18000AF8D
0x18000ae80  cmp     dword ptr [rax+48h], 0
0x18000ae84  jl      short loc_18000AE89
0x18000ae86  mov     [rax+48h], esi
0x18000ae89  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18000ae8e  dec     edi
0x18000ae90  mov     [rax+0F8h], edi
0x18000ae96  test    rcx, rcx
0x18000ae99  jz      short loc_18000AEA1
0x18000ae9b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aea1  test    edi, edi
0x18000aea3  jnz     short loc_18000AEB9
0x18000aea5  mov     rax, [rbx]
0x18000aea8  mov     rcx, rbx
0x18000aeab  mov     rax, [rax+8]
0x18000aeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb4  jmp     loc_18000AF6D
0x18000aeb9  call    ?Provider@DeviceCenterContextHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; DeviceCenterContextHandlersLogging::Provider(void)
0x18000aebe  mov     rdi, rax
0x18000aec1  mov     ecx, [rax]
0x18000aec3  cmp     ecx, 5
0x18000aec6  jbe     loc_18000AF6D
0x18000aecc  mov     rax, [rax+18h]
0x18000aed0  mov     rdx, 200000000000h
0x18000aeda  mov     rcx, [rdi+10h]
0x18000aede  test    rdx, rcx
0x18000aee1  jz      loc_18000AF6D
0x18000aee7  mov     rcx, rax
0x18000aeea  and     rcx, rdx
0x18000aeed  cmp     rcx, rax
0x18000aef0  jnz     short loc_18000AF6D
0x18000aef2  call    cs:__imp_GetCurrentThreadId
0x18000aef8  mov     r8, [rbx+110h]
0x18000aeff  lea     rdx, word_180010E36
0x18000af06  mov     [rsp+120h+var_F0], eax
0x18000af0a  add     r8, 8
0x18000af0e  lea     rax, [rsp+120h+var_F0]
0x18000af13  mov     dword ptr [rsp+120h+SRWLock], esi
0x18000af17  mov     [rbp+20h+var_90], rax
0x18000af1b  xor     r9d, r9d
0x18000af1e  lea     rax, [rsp+120h+SRWLock]
0x18000af23  mov     [rsp+120h+var_E0], 1000000h
0x18000af2c  mov     [rbp+20h+var_A0], rax
0x18000af30  mov     rcx, rdi
0x18000af33  lea     rax, [rsp+120h+var_E0]
0x18000af38  mov     [rbp+20h+var_88], 4
0x18000af40  mov     [rsp+120h+var_B0], rax
0x18000af45  lea     rax, [rsp+120h+var_D0]
0x18000af4a  mov     [rsp+120h+var_F8], rax
0x18000af4f  mov     [rsp+120h+var_100], 5
0x18000af57  mov     [rbp+20h+var_98], 4
0x18000af5f  mov     [rsp+120h+var_A8], 8
0x18000af68  call    _tlgWriteTransfer_EventWriteTransfer
0x18000af6d  mov     rcx, rbx
0x18000af70  call    ?IgnoreCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000af75  mov     rcx, [rbp+20h+var_30]
0x18000af79  xor     rcx, rsp; StackCookie
0x18000af7c  call    __security_check_cookie
0x18000af81  add     rsp, 108h
0x18000af88  pop     rdi
0x18000af89  pop     rsi
0x18000af8a  pop     rbx
0x18000af8b  pop     rbp
0x18000af8c  retn
0x18000af8d  xor     edx, edx; Val
0x18000af8f  lea     rcx, [rsp+120h+var_D0]; void *
0x18000af94  mov     r8d, 98h; Size
0x18000af9a  call    memset_0
0x18000af9f  lea     rcx, [rsp+120h+var_D0]; this
0x18000afa4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
