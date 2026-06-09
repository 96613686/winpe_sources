# RemoteAppIntegrationClient::TryAcquireOwner(Microsoft::WRL::ComPtr<IRemoteAppIntegrationOwner> &)

- ea: `0x180034ba8`
- end: `0x180034c5f`
- name: `?TryAcquireOwner@RemoteAppIntegrationClient@@AEAA_NAEAV?$ComPtr@UIRemoteAppIntegrationOwner@@@WRL@Microsoft@@@Z`
- size: `183`
- prototype: ``
- caller_count: `21`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031400`
- `0x1800320e0`
- `0x1800321f0`
- `0x1800322e0`
- `0x180032650`
- `0x180032e40`
- `0x180033040`
- `0x180033270`
- `0x180033350`
- `0x180033420`
- `0x180033760`
- `0x180033c80`
- `0x180033e30`
- `0x180033fd0`
- `0x180034180`
- `0x180034270`
- `0x180034470`
- `0x1800345d0`
- `0x1800347e0`
- `0x1800348e0`
- `0x180034a00`

## callees

- `0x180034ba8`
- `0x180034d6c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034be8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034be8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180034c3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180034bd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180034bd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall RemoteAppIntegrationClient::TryAcquireOwner(__int64 a1, __int64 *a2)
{
  RTL_SRWLOCK *v4; // rdi
  __int64 v6; // rbx
  __int64 v7; // rcx
  bool v8; // bl

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl'::`2'::impl) )
    return *(_QWORD *)(a1 + 40) != 0;
  v4 = (RTL_SRWLOCK *)(a1 + 24);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 24));
  if ( *(_BYTE *)(a1 + 32) )
  {
    if ( a1 != -24 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 24));
    return 0;
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 40);
    if ( *a2 == v6 )
    {
      v6 = *a2;
    }
    else
    {
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      v7 = *a2;
      *a2 = v6;
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v6 = *a2;
      }
    }
    v8 = v6 != 0;
    if ( v4 )
      ReleaseSRWLockShared(v4);
    return v8;
  }
}

```

## disassembly

```asm
0x180034ba8  mov     [rsp+arg_0], rbx
0x180034bad  mov     [rsp+arg_8], rsi
0x180034bb2  push    rdi
0x180034bb3  sub     rsp, 20h
0x180034bb7  mov     rsi, rdx
0x180034bba  mov     rbx, rcx
0x180034bbd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::GetImpl(void)'::`2'::impl
0x180034bc4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RaicToctouRaceFix_61166608>::__private_IsEnabled(void)
0x180034bc9  test    al, al
0x180034bcb  jz      short loc_180034C47
0x180034bcd  lea     rdi, [rbx+18h]
0x180034bd1  mov     rcx, rdi; SRWLock
0x180034bd4  call    cs:__imp_AcquireSRWLockShared
0x180034bda  cmp     byte ptr [rbx+20h], 0
0x180034bde  jz      short loc_180034BF2
0x180034be0  test    rdi, rdi
0x180034be3  jz      short loc_180034BEE
0x180034be5  mov     rcx, rdi; SRWLock
0x180034be8  call    cs:__imp_ReleaseSRWLockShared
0x180034bee  xor     al, al
0x180034bf0  jmp     short loc_180034C4F
0x180034bf2  mov     rbx, [rbx+28h]
0x180034bf6  cmp     [rsi], rbx
0x180034bf9  jz      short loc_180034C2C
0x180034bfb  test    rbx, rbx
0x180034bfe  jz      short loc_180034C10
0x180034c00  mov     rax, [rbx]
0x180034c03  mov     rcx, rbx
0x180034c06  mov     rax, [rax+8]
0x180034c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c0f  nop
0x180034c10  mov     rcx, [rsi]
0x180034c13  mov     [rsi], rbx
0x180034c16  test    rcx, rcx
0x180034c19  jz      short loc_180034C2A
0x180034c1b  mov     rax, [rcx]
0x180034c1e  mov     rax, [rax+10h]
0x180034c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c27  mov     rbx, [rsi]
0x180034c2a  jmp     short loc_180034C2F
0x180034c2c  mov     rbx, [rsi]
0x180034c2f  test    rbx, rbx
0x180034c32  setnz   bl
0x180034c35  test    rdi, rdi
0x180034c38  jz      short loc_180034C43
0x180034c3a  mov     rcx, rdi; SRWLock
0x180034c3d  call    cs:__imp_ReleaseSRWLockShared
0x180034c43  mov     al, bl
0x180034c45  jmp     short loc_180034C4F
0x180034c47  cmp     qword ptr [rbx+28h], 0
0x180034c4c  setnz   al
0x180034c4f  mov     rbx, [rsp+28h+arg_0]
0x180034c54  mov     rsi, [rsp+28h+arg_8]
0x180034c59  add     rsp, 20h
0x180034c5d  pop     rdi
0x180034c5e  retn
```
