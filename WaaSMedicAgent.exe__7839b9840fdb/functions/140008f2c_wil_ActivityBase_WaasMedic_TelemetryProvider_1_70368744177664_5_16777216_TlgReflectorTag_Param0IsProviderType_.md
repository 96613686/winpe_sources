# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x140008f2c`
- end: `0x1400090a4`
- name: `?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `376`
- prototype: `void __fastcall(_QWORD *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140007f3c`
- `0x1400093c0`
- `0x14000a8f0`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x14000369c`
- `0x140007220`
- `0x14000827c`
- `0x14000830c`
- `0x14000885c`
- `0x140008f2c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008feb`

## pseudocode

```c
void __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  _QWORD v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v15; // [rsp+70h] [rbp-90h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+98h] [rbp-68h]

  v13[1] = -2;
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
    v7 = WaasMedic::TelemetryProvider::Provider();
    v8 = v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      v9 = *((_QWORD *)v7 + 3);
      if ( (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = a2;
        v13[0] = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v20 = 4;
        p_SRWLock = &SRWLock;
        v18 = 4;
        v15 = v13;
        v16 = 8;
        tlgWriteTransfer_EventWriteTransfer(v8, &unk_140019598, a1[34] + 8LL, 0, 5, v14);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x140008f2c  push    rbp
0x140008f2e  push    rbx
0x140008f2f  push    rsi
0x140008f30  push    rdi
0x140008f31  lea     rbp, [rsp-8]
0x140008f36  sub     rsp, 108h
0x140008f3d  mov     [rsp+120h+var_D8], 0FFFFFFFFFFFFFFFEh
0x140008f46  mov     rax, cs:__security_cookie
0x140008f4d  xor     rax, rsp
0x140008f50  mov     [rbp+20h+var_30], rax
0x140008f54  mov     esi, edx
0x140008f56  mov     rbx, rcx
0x140008f59  lea     rdx, [rsp+120h+SRWLock]
0x140008f5e  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008f63  mov     rax, [rbx+110h]
0x140008f6a  mov     edi, [rax+0F8h]
0x140008f70  cmp     edi, 1
0x140008f73  jl      loc_140009087
0x140008f79  cmp     dword ptr [rax+48h], 0
0x140008f7d  jl      short loc_140008F82
0x140008f7f  mov     [rax+48h], esi
0x140008f82  dec     edi
0x140008f84  mov     [rax+0F8h], edi
0x140008f8a  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x140008f8f  test    rcx, rcx
0x140008f92  jz      short loc_140008F9A
0x140008f94  call    cs:__imp_ReleaseSRWLockExclusive
0x140008f9a  test    edi, edi
0x140008f9c  jnz     short loc_140008FB2
0x140008f9e  mov     rax, [rbx]
0x140008fa1  mov     rcx, rbx
0x140008fa4  mov     rax, [rax+8]
0x140008fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fad  jmp     loc_140009066
0x140008fb2  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x140008fb7  mov     rdi, rax
0x140008fba  mov     ecx, [rax]
0x140008fbc  cmp     ecx, 5
0x140008fbf  jbe     loc_140009066
0x140008fc5  mov     rax, [rax+18h]
0x140008fc9  mov     rcx, [rdi+10h]
0x140008fcd  mov     rdx, 400000000000h
0x140008fd7  test    rdx, rcx
0x140008fda  jz      loc_140009066
0x140008fe0  mov     rcx, rax
0x140008fe3  and     rcx, rdx
0x140008fe6  cmp     rcx, rax
0x140008fe9  jnz     short loc_140009066
0x140008feb  call    cs:__imp_GetCurrentThreadId
0x140008ff1  mov     [rsp+120h+var_F0], eax
0x140008ff5  mov     dword ptr [rsp+120h+SRWLock], esi
0x140008ff9  mov     [rsp+120h+var_E0], 1000000h
0x140009002  lea     rax, [rsp+120h+var_F0]
0x140009007  mov     [rbp+20h+var_90], rax
0x14000900b  mov     [rbp+20h+var_88], 4
0x140009013  lea     rax, [rsp+120h+SRWLock]
0x140009018  mov     [rbp+20h+var_A0], rax
0x14000901c  mov     [rbp+20h+var_98], 4
0x140009024  lea     rax, [rsp+120h+var_E0]
0x140009029  mov     [rsp+120h+var_B0], rax
0x14000902e  mov     [rsp+120h+var_A8], 8
0x140009037  mov     r8, [rbx+110h]
0x14000903e  add     r8, 8
0x140009042  lea     rax, [rsp+120h+var_D0]
0x140009047  mov     [rsp+120h+var_F8], rax
0x14000904c  mov     [rsp+120h+var_100], 5
0x140009054  xor     r9d, r9d
0x140009057  lea     rdx, unk_140019598
0x14000905e  mov     rcx, rdi
0x140009061  call    _tlgWriteTransfer_EventWriteTransfer
0x140009066  mov     rcx, rbx
0x140009069  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000906e  nop
0x14000906f  mov     rcx, [rbp+20h+var_30]
0x140009073  xor     rcx, rsp; StackCookie
0x140009076  call    __security_check_cookie
0x14000907b  add     rsp, 108h
0x140009082  pop     rdi
0x140009083  pop     rsi
0x140009084  pop     rbx
0x140009085  pop     rbp
0x140009086  retn
0x140009087  xor     edx, edx; Val
0x140009089  mov     r8d, 98h; Size
0x14000908f  lea     rcx, [rsp+120h+var_D0]; void *
0x140009094  call    memset_0
0x140009099  lea     rcx, [rsp+120h+var_D0]; this
0x14000909e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
