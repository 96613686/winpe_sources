# wil::ActivityBase<AAMTraceProvider,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180013940`
- end: `0x180013b94`
- name: `?Stop@?$ActivityBase@VAAMTraceProvider@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `596`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011ad0`

## callees

- `0x180013940`
- `0x180024840`
- `0x180035e10`
- `0x1800475b0`
- `0x18005ae90`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001399c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800139b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800139ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001399c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800139b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800139ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013984`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a40`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013b1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013b1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<AAMTraceProvider,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  int v7; // esi
  __int64 v8; // rbx
  const GUID *v9; // r8
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+80h] [rbp-80h]
  __int128 v17; // [rsp+90h] [rbp-70h]
  __int128 v18; // [rsp+A0h] [rbp-60h]
  __int128 v19; // [rsp+B0h] [rbp-50h]
  __int128 v20; // [rsp+C0h] [rbp-40h]
  __int128 v21; // [rsp+D0h] [rbp-30h]
  __int128 v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+F0h] [rbp-10h]

  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
  }
  else
  {
    v11 = 0;
    v4 = 0;
  }
  v5 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    UserData = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v5 + 72) >= 0 )
    *(_DWORD *)(v5 + 72) = 0;
  v7 = v6 - 1;
  *(_DWORD *)(v5 + 248) = v7;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v7 )
  {
    v8 = *((_QWORD *)AAMTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u && (*(_QWORD *)(v8 + 16) & 1) != 0 && (*(_QWORD *)(v8 + 24) & 1LL) == *(_QWORD *)(v8 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(v11) = 0;
      v12 = 0x1000000;
      v9 = (const GUID *)(*(_QWORD *)(a1 + 272) + 8LL);
      *(_QWORD *)&v18 = &CurrentThreadId;
      *((_QWORD *)&v18 + 1) = 4;
      *(_QWORD *)&v17 = &v11;
      *((_QWORD *)&v17 + 1) = 4;
      *(_QWORD *)&v16 = &v12;
      *((_QWORD *)&v16 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 1;
      UserData.Ptr = *(_QWORD *)(v8 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v15 = &word_1800B7BE6;
      *((_QWORD *)&v15 + 1) = 0x10000004DLL;
      EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, v9, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180013940  mov     [rsp-8+arg_8], rbx
0x180013945  mov     [rsp-8+arg_10], rsi
0x18001394a  push    rbp
0x18001394b  push    rdi
0x18001394c  push    r14
0x18001394e  lea     rbp, [rsp-10h]
0x180013953  sub     rsp, 110h
0x18001395a  mov     rax, cs:__security_cookie
0x180013961  xor     rax, rsp
0x180013964  mov     [rbp+20h+var_20], rax
0x180013968  mov     rdi, rcx
0x18001396b  xor     r14d, r14d
0x18001396e  mov     rbx, [rcx+118h]
0x180013975  test    rbx, rbx
0x180013978  jz      short loc_1800139A4
0x18001397a  add     rbx, 108h
0x180013981  mov     rcx, rbx; SRWLock
0x180013984  call    cs:__imp_AcquireSRWLockExclusive
0x18001398a  lea     rax, [rsp+120h+SRWLock]
0x18001398f  mov     [rax], r14
0x180013992  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x180013997  test    rcx, rcx
0x18001399a  jz      short loc_1800139BF
0x18001399c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800139a2  jmp     short loc_1800139BF
0x1800139a4  lea     rax, [rsp+120h+var_E0]
0x1800139a9  mov     [rax], r14
0x1800139ac  mov     rcx, [rsp+120h+var_E0]; SRWLock
0x1800139b1  test    rcx, rcx
0x1800139b4  jz      short loc_1800139BC
0x1800139b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800139bc  mov     rbx, r14
0x1800139bf  mov     rax, [rdi+110h]
0x1800139c6  mov     esi, [rax+0F8h]
0x1800139cc  cmp     esi, 1
0x1800139cf  jl      loc_180013B5A
0x1800139d5  cmp     dword ptr [rax+48h], 0
0x1800139d9  jl      short loc_1800139DF
0x1800139db  mov     [rax+48h], r14d
0x1800139df  dec     esi
0x1800139e1  mov     [rax+0F8h], esi
0x1800139e7  test    rbx, rbx
0x1800139ea  jz      short loc_1800139F5
0x1800139ec  mov     rcx, rbx; SRWLock
0x1800139ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800139f5  test    esi, esi
0x1800139f7  jnz     short loc_180013A0D
0x1800139f9  mov     rax, [rdi]
0x1800139fc  mov     rcx, rdi
0x1800139ff  mov     rax, [rax+8]
0x180013a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a08  jmp     loc_180013B23
0x180013a0d  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x180013a12  mov     rbx, [rax+8]
0x180013a16  mov     eax, [rbx]
0x180013a18  cmp     eax, 5
0x180013a1b  jbe     loc_180013B23
0x180013a21  mov     rcx, [rbx+18h]
0x180013a25  mov     rax, [rbx+10h]
0x180013a29  test    al, 1
0x180013a2b  jz      loc_180013B23
0x180013a31  mov     rax, rcx
0x180013a34  and     eax, 1
0x180013a37  cmp     rax, rcx
0x180013a3a  jnz     loc_180013B23
0x180013a40  call    cs:__imp_GetCurrentThreadId
0x180013a46  mov     [rsp+120h+var_E8], eax
0x180013a4a  mov     dword ptr [rsp+120h+var_E0], r14d
0x180013a4f  mov     [rsp+120h+var_D8], 1000000h
0x180013a58  mov     r8, [rdi+110h]
0x180013a5f  add     r8, 8; ActivityId
0x180013a63  lea     rax, [rsp+120h+var_E8]
0x180013a68  mov     qword ptr [rbp+20h+var_80], rax
0x180013a6c  mov     qword ptr [rbp+20h+var_80+8], 4
0x180013a74  lea     rax, [rsp+120h+var_E0]
0x180013a79  mov     qword ptr [rbp+20h+var_90], rax
0x180013a7d  mov     qword ptr [rbp+20h+var_90+8], 4
0x180013a85  lea     rax, [rsp+120h+var_D8]
0x180013a8a  mov     qword ptr [rbp+20h+var_A0], rax
0x180013a8e  mov     qword ptr [rbp+20h+var_A0+8], 8
0x180013a96  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x180013a9e  movzx   eax, cs:word_1800B7BDC
0x180013aa5  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180013aa9  mov     [rsp+120h+EventDescriptor.Keyword], 1
0x180013ab2  mov     rax, [rbx+8]
0x180013ab6  mov     [rsp+120h+var_C0.Ptr], rax
0x180013abb  movzx   eax, word ptr [rax]
0x180013abe  mov     [rsp+120h+var_C0.Size], eax
0x180013ac2  mov     dword ptr [rsp+120h+var_C0.0Ch], 2
0x180013aca  lea     rax, word_1800B7BE6
0x180013ad1  mov     qword ptr [rsp+120h+var_B0], rax
0x180013ad6  mov     dword ptr [rsp+120h+var_B0+8], 4Dh ; 'M'
0x180013ade  mov     dword ptr [rsp+120h+var_B0+0Ch], 1
0x180013ae6  lea     rax, _TraceLoggingMetadataEnd
0x180013aed  lea     rcx, _TraceLoggingMetadata
0x180013af4  sub     eax, ecx
0x180013af6  mov     dword ptr [rsp+120h+SRWLock], eax
0x180013afa  mov     eax, dword ptr [rsp+120h+SRWLock]
0x180013afe  lea     rax, [rsp+120h+var_C0]
0x180013b03  mov     [rsp+120h+UserData], rax; UserData
0x180013b08  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x180013b10  xor     r9d, r9d; RelatedActivityId
0x180013b13  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x180013b18  mov     rcx, [rbx+20h]; RegHandle
0x180013b1c  call    cs:__imp_EventWriteTransfer
0x180013b22  nop
0x180013b23  lea     rcx, [rdi+120h]; this
0x180013b2a  cmp     dword ptr [rcx+18h], 0
0x180013b2e  jz      short loc_180013B36
0x180013b30  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180013b35  nop
0x180013b36  mov     rcx, [rbp+20h+var_20]
0x180013b3a  xor     rcx, rsp; StackCookie
0x180013b3d  call    __security_check_cookie
0x180013b42  lea     r11, [rsp+120h+var_10]
0x180013b4a  mov     rbx, [r11+28h]
0x180013b4e  mov     rsi, [r11+30h]
0x180013b52  mov     rsp, r11
0x180013b55  pop     r14
0x180013b57  pop     rdi
0x180013b58  pop     rbp
0x180013b59  retn
0x180013b5a  xorps   xmm0, xmm0
0x180013b5d  xor     eax, eax
0x180013b5f  movups  xmmword ptr [rsp+120h+var_C0.Ptr], xmm0
0x180013b64  movups  [rsp+120h+var_B0], xmm0
0x180013b69  movups  [rbp+20h+var_A0], xmm0
0x180013b6d  movups  [rbp+20h+var_90], xmm0
0x180013b71  movups  [rbp+20h+var_80], xmm0
0x180013b75  movups  [rbp+20h+var_70], xmm0
0x180013b79  movups  [rbp+20h+var_60], xmm0
0x180013b7d  movups  [rbp+20h+var_50], xmm0
0x180013b81  movups  [rbp+20h+var_40], xmm0
0x180013b85  mov     [rbp+20h+var_30], rax
0x180013b89  lea     rcx, [rsp+120h+var_C0]; this
0x180013b8e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
