# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000f4b0`
- end: `0x18000f61f`
- name: `?Stop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `367`
- prototype: `void __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180010444`

## callees

- `0x180001bdc`
- `0x180002bc0`
- `0x18000354c`
- `0x180007010`
- `0x18000a648`
- `0x18000e400`
- `0x18000e47c`
- `0x18000f4b0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f50f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f50f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f566`

## pseudocode

```c
void __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  int v6; // edi
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // rdi
  __int64 v9; // rax
  const struct wil::FailureInfo *v10; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v15; // [rsp+70h] [rbp-90h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]

  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v4 = a1[34];
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v10);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    v7 = ServiceHostLogging::Provider();
    v8 = v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      v9 = *((_QWORD *)v7 + 3);
      if ( (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = a2;
        v13 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v20 = 4;
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = &v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v8, byte_1800150A1, a1[34] + 8LL, 0, 5, v14);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000f4b0  push    rbp
0x18000f4b2  push    rbx
0x18000f4b3  push    rsi
0x18000f4b4  push    rdi
0x18000f4b5  lea     rbp, [rsp-8]
0x18000f4ba  sub     rsp, 108h
0x18000f4c1  mov     rax, cs:__security_cookie
0x18000f4c8  xor     rax, rsp
0x18000f4cb  mov     [rbp+20h+var_30], rax
0x18000f4cf  mov     esi, edx
0x18000f4d1  mov     rbx, rcx
0x18000f4d4  lea     rdx, [rsp+120h+SRWLock]
0x18000f4d9  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000f4de  mov     rax, [rbx+110h]
0x18000f4e5  mov     edi, [rax+0F8h]
0x18000f4eb  cmp     edi, 1
0x18000f4ee  jl      loc_18000F602
0x18000f4f4  cmp     dword ptr [rax+48h], 0
0x18000f4f8  jl      short loc_18000F4FD
0x18000f4fa  mov     [rax+48h], esi
0x18000f4fd  dec     edi
0x18000f4ff  mov     [rax+0F8h], edi
0x18000f505  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x18000f50a  test    rcx, rcx
0x18000f50d  jz      short loc_18000F515
0x18000f50f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f515  test    edi, edi
0x18000f517  jnz     short loc_18000F52D
0x18000f519  mov     rax, [rbx]
0x18000f51c  mov     rcx, rbx
0x18000f51f  mov     rax, [rax+8]
0x18000f523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f528  jmp     loc_18000F5E1
0x18000f52d  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000f532  mov     rdi, rax
0x18000f535  mov     ecx, [rax]
0x18000f537  cmp     ecx, 5
0x18000f53a  jbe     loc_18000F5E1
0x18000f540  mov     rax, [rax+18h]
0x18000f544  mov     rcx, [rdi+10h]
0x18000f548  mov     rdx, 400000000000h
0x18000f552  test    rdx, rcx
0x18000f555  jz      loc_18000F5E1
0x18000f55b  mov     rcx, rax
0x18000f55e  and     rcx, rdx
0x18000f561  cmp     rcx, rax
0x18000f564  jnz     short loc_18000F5E1
0x18000f566  call    cs:__imp_GetCurrentThreadId
0x18000f56c  mov     [rsp+120h+var_F0], eax
0x18000f570  mov     dword ptr [rsp+120h+SRWLock], esi
0x18000f574  mov     [rsp+120h+var_E0], 1000000h
0x18000f57d  lea     rax, [rsp+120h+var_F0]
0x18000f582  mov     [rbp+20h+var_90], rax
0x18000f586  mov     [rbp+20h+var_88], 4
0x18000f58e  lea     rax, [rsp+120h+SRWLock]
0x18000f593  mov     [rbp+20h+var_A0], rax
0x18000f597  mov     [rbp+20h+var_98], 4
0x18000f59f  lea     rax, [rsp+120h+var_E0]
0x18000f5a4  mov     [rsp+120h+var_B0], rax
0x18000f5a9  mov     [rsp+120h+var_A8], 8
0x18000f5b2  mov     r8, [rbx+110h]
0x18000f5b9  add     r8, 8
0x18000f5bd  lea     rax, [rsp+120h+var_D0]
0x18000f5c2  mov     [rsp+120h+var_F8], rax
0x18000f5c7  mov     [rsp+120h+var_100], 5
0x18000f5cf  xor     r9d, r9d
0x18000f5d2  lea     rdx, byte_1800150A1
0x18000f5d9  mov     rcx, rdi
0x18000f5dc  call    _tlgWriteTransfer_EventWriteTransfer
0x18000f5e1  mov     rcx, rbx
0x18000f5e4  call    ?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000f5e9  nop
0x18000f5ea  mov     rcx, [rbp+20h+var_30]
0x18000f5ee  xor     rcx, rsp; StackCookie
0x18000f5f1  call    __security_check_cookie
0x18000f5f6  add     rsp, 108h
0x18000f5fd  pop     rdi
0x18000f5fe  pop     rsi
0x18000f5ff  pop     rbx
0x18000f600  pop     rbp
0x18000f601  retn
0x18000f602  xor     edx, edx; Val
0x18000f604  mov     r8d, 98h; Size
0x18000f60a  lea     rcx, [rsp+120h+var_D0]; void *
0x18000f60f  call    memset_0
0x18000f614  lea     rcx, [rsp+120h+var_D0]; this
0x18000f619  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
