# SsdmTelemetryProvider::PersonalizationDuration::StartActivity(void)

- ea: `0x18000b328`
- end: `0x18000b4ce`
- name: `?StartActivity@PersonalizationDuration@SsdmTelemetryProvider@@QEAAXXZ`
- size: `422`
- prototype: `void __fastcall(SsdmTelemetryProvider::PersonalizationDuration *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ace8`

## callees

- `0x18000163c`
- `0x180005a9c`
- `0x1800063b4`
- `0x18000a8cc`
- `0x18000b328`
- `0x18000e990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3b4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b396`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b396`

## pseudocode

```c
void __fastcall SsdmTelemetryProvider::PersonalizationDuration::StartActivity(
        SsdmTelemetryProvider::PersonalizationDuration *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v12[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]

  wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  v3 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v3 > 5u
    && (*(_QWORD *)(v3 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v3 + 24) & 0x200000000000LL) == *(_QWORD *)(v3 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  }
  else
  {
    *(_OWORD *)(v2 + 8) = 0;
  }
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v5 = *((_QWORD *)SsdmTelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v5 > 5u )
  {
    v4 = *(_QWORD *)(v5 + 24);
    if ( (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0 && (v4 & 0x200000000000LL) == v4 )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v11 = 0;
      v6 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v6 + 4)
        || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
        && !*(_DWORD *)(v6 + 28)
        && !*(_DWORD *)(v6 + 32)
        && !*(_DWORD *)(v6 + 36) )
      {
        v7 = 0;
      }
      p_SRWLock = &SRWLock;
      v16 = 4;
      v13 = &v11;
      v14 = 8;
      tlgWriteTransfer_EventWriteTransfer(v5, word_18001748A, v6 + 8, v7, 4, v12);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v8 = (char *)this + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v4,
                          1);
      *(_QWORD *)v8 = Local;
      if ( Local )
      {
        *((_QWORD *)v8 + 2) = *Local;
        *Local = v8;
        *((_DWORD *)v8 + 6) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v8 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000b328  push    rbp
0x18000b32a  push    rbx
0x18000b32b  push    rdi
0x18000b32c  push    r14
0x18000b32e  lea     rbp, [rsp-3Fh]
0x18000b333  sub     rsp, 98h
0x18000b33a  mov     rax, cs:__security_cookie
0x18000b341  xor     rax, rsp
0x18000b344  mov     [rbp+57h+var_30], rax
0x18000b348  mov     rbx, rcx
0x18000b34b  lea     rdx, [rbp+57h+SRWLock]
0x18000b34f  call    ?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000b354  mov     rdi, [rbx+110h]
0x18000b35b  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000b360  mov     rdx, [rax+8]
0x18000b364  mov     eax, [rdx]
0x18000b366  mov     r14, 200000000000h
0x18000b370  cmp     eax, 5
0x18000b373  jbe     short loc_18000B39E
0x18000b375  mov     rcx, [rdx+18h]
0x18000b379  mov     rax, [rdx+10h]
0x18000b37d  test    r14, rax
0x18000b380  jz      short loc_18000B39E
0x18000b382  mov     rax, rcx
0x18000b385  and     rax, r14
0x18000b388  cmp     rax, rcx
0x18000b38b  jnz     short loc_18000B39E
0x18000b38d  lea     rdx, [rdi+8]; ActivityId
0x18000b391  mov     ecx, 3; ControlCode
0x18000b396  call    cs:__imp_EventActivityIdControl
0x18000b39c  jmp     short loc_18000B3A5
0x18000b39e  xorps   xmm0, xmm0
0x18000b3a1  movups  xmmword ptr [rdi+8], xmm0
0x18000b3a5  mov     dword ptr [rdi], 1
0x18000b3ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000b3af  test    rcx, rcx
0x18000b3b2  jz      short loc_18000B3BA
0x18000b3b4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b3ba  call    ?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ; SsdmTelemetryProvider::Instance(void)
0x18000b3bf  mov     rdi, [rax+8]
0x18000b3c3  mov     eax, [rdi]
0x18000b3c5  cmp     eax, 5
0x18000b3c8  jbe     loc_18000B470
0x18000b3ce  mov     rcx, [rdi+18h]
0x18000b3d2  mov     rax, [rdi+10h]
0x18000b3d6  test    r14, rax
0x18000b3d9  jz      loc_18000B470
0x18000b3df  mov     rax, rcx
0x18000b3e2  and     rax, r14
0x18000b3e5  cmp     rax, rcx
0x18000b3e8  jnz     loc_18000B470
0x18000b3ee  call    cs:__imp_GetCurrentThreadId
0x18000b3f4  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000b3f7  mov     [rbp+57h+var_78], 0
0x18000b3ff  mov     r8, [rbx+110h]
0x18000b406  cmp     byte ptr [r8+4], 0
0x18000b40b  jz      short loc_18000B42C
0x18000b40d  lea     r9, [r8+18h]
0x18000b411  cmp     dword ptr [r9], 0
0x18000b415  jnz     short loc_18000B42F
0x18000b417  cmp     dword ptr [r9+4], 0
0x18000b41c  jnz     short loc_18000B42F
0x18000b41e  cmp     dword ptr [r9+8], 0
0x18000b423  jnz     short loc_18000B42F
0x18000b425  cmp     dword ptr [r9+0Ch], 0
0x18000b42a  jnz     short loc_18000B42F
0x18000b42c  xor     r9d, r9d
0x18000b42f  lea     rax, [rbp+57h+SRWLock]
0x18000b433  mov     [rbp+57h+var_40], rax
0x18000b437  mov     ecx, 4
0x18000b43c  mov     [rbp+57h+var_38], rcx
0x18000b440  lea     rax, [rbp+57h+var_78]
0x18000b444  mov     [rbp+57h+var_50], rax
0x18000b448  mov     [rbp+57h+var_48], 8
0x18000b450  add     r8, 8
0x18000b454  lea     rax, [rbp+57h+var_70]
0x18000b458  mov     [rsp+0B0h+var_88], rax
0x18000b45d  mov     [rsp+0B0h+var_90], ecx
0x18000b461  lea     rdx, word_18001748A
0x18000b468  mov     rcx, rdi
0x18000b46b  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b470  cmp     dword ptr [rbx+138h], 0
0x18000b477  jnz     short loc_18000B4B5
0x18000b479  add     rbx, 120h
0x18000b480  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b488  jz      short loc_18000B4AE
0x18000b48a  mov     dl, 1
0x18000b48c  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000b491  mov     [rbx], rax
0x18000b494  test    rax, rax
0x18000b497  jz      short loc_18000B4B5
0x18000b499  mov     rcx, [rax]
0x18000b49c  mov     [rbx+10h], rcx
0x18000b4a0  mov     [rax], rbx
0x18000b4a3  call    cs:__imp_GetCurrentThreadId
0x18000b4a9  mov     [rbx+18h], eax
0x18000b4ac  jmp     short loc_18000B4B5
0x18000b4ae  mov     qword ptr [rbx], 0
0x18000b4b5  mov     rcx, [rbp+57h+var_30]
0x18000b4b9  xor     rcx, rsp; StackCookie
0x18000b4bc  call    __security_check_cookie
0x18000b4c1  add     rsp, 98h
0x18000b4c8  pop     r14
0x18000b4ca  pop     rdi
0x18000b4cb  pop     rbx
0x18000b4cc  pop     rbp
0x18000b4cd  retn
```
