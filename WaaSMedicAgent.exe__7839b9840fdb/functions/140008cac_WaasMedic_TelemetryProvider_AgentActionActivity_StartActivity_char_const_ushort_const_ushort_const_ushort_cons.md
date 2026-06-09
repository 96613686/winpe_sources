# WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(char const *,ushort const *,ushort const *,ushort const *)

- ea: `0x140008cac`
- end: `0x140008f23`
- name: `?StartActivity@AgentActionActivity@TelemetryProvider@WaasMedic@@QEAAXPEBDPEBG11@Z`
- size: `631`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AgentActionActivity *__hidden this, const char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x140007f3c`
- `0x1400093c0`

## callees

- `0x14000198c`
- `0x140002a30`
- `0x1400056a0`
- `0x14000830c`
- `0x14000885c`
- `0x140008cac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008d49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008ef5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140008d27`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x140008d27`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AgentActionActivity::StartActivity(
        WaasMedic::TelemetryProvider::AgentActionActivity *this,
        const char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  RTL_SRWLOCK *v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  const struct _tlgProvider_t *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r10
  __int64 v18; // r9
  const unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  int v21; // edx
  __int64 v22; // r8
  int v23; // r8d
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // ecx
  _QWORD *v28; // rbx
  _QWORD *Local; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-91h] BYREF
  __int64 v31; // [rsp+38h] [rbp-89h] BYREF
  _BYTE v32[32]; // [rsp+40h] [rbp-81h] BYREF
  __int64 *v33; // [rsp+60h] [rbp-61h]
  __int64 v34; // [rsp+68h] [rbp-59h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-51h]
  __int64 v36; // [rsp+78h] [rbp-49h]
  const char *v37; // [rsp+80h] [rbp-41h]
  int v38; // [rsp+88h] [rbp-39h]
  int v39; // [rsp+8Ch] [rbp-35h]
  const unsigned __int16 *v40; // [rsp+90h] [rbp-31h]
  int v41; // [rsp+98h] [rbp-29h]
  int v42; // [rsp+9Ch] [rbp-25h]
  const unsigned __int16 *v43; // [rsp+A0h] [rbp-21h]
  int v44; // [rsp+A8h] [rbp-19h]
  int v45; // [rsp+ACh] [rbp-15h]
  const unsigned __int16 *v46; // [rsp+B0h] [rbp-11h]
  int v47; // [rsp+B8h] [rbp-9h]
  int v48; // [rsp+BCh] [rbp-5h]

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v9 = *((_QWORD *)this + 34);
  v10 = WaasMedic::TelemetryProvider::Provider();
  if ( *(_DWORD *)v10 > 5u
    && (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
  {
    EventActivityIdControl(3u, (LPGUID)(v9 + 8));
  }
  else
  {
    *(_OWORD *)(v9 + 8) = 0;
  }
  v11 = SRWLock;
  *(_DWORD *)v9 = 1;
  if ( v11 )
    ReleaseSRWLockExclusive(v11);
  v12 = WaasMedic::TelemetryProvider::Provider();
  v13 = v12;
  v14 = *(unsigned int *)v12;
  if ( (unsigned int)v14 > 5 )
  {
    v15 = *((_QWORD *)v12 + 3);
    v14 = *((_QWORD *)v12 + 2);
    if ( (v14 & 0x400000000000LL) != 0 )
    {
      v14 = v15 & 0x400000000000LL;
      if ( (v15 & 0x400000000000LL) == v15 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v17 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v31 = 0x1000000;
        if ( !*(_BYTE *)(v17 + 4)
          || (v18 = v17 + 24, !*(_DWORD *)(v17 + 24))
          && !*(_DWORD *)(v17 + 28)
          && !*(_DWORD *)(v17 + 32)
          && !*(_DWORD *)(v17 + 36) )
        {
          v18 = 0;
        }
        v19 = a5;
        v20 = -1;
        v21 = 2;
        if ( a5 )
        {
          v22 = -1;
          do
            ++v22;
          while ( a5[v22] );
          v23 = 2 * v22 + 2;
        }
        else
        {
          v19 = &dword_1400158BC;
          v23 = 2;
        }
        v46 = v19;
        v47 = v23;
        v48 = 0;
        if ( a4 )
        {
          v24 = -1;
          do
            ++v24;
          while ( a4[v24] );
          v25 = 2 * v24 + 2;
        }
        else
        {
          a4 = &dword_1400158BC;
          v25 = 2;
        }
        v43 = a4;
        v44 = v25;
        v45 = 0;
        if ( a3 )
        {
          v26 = -1;
          do
            ++v26;
          while ( a3[v26] );
          v21 = 2 * v26 + 2;
        }
        else
        {
          a3 = &dword_1400158BC;
        }
        v40 = a3;
        v41 = v21;
        v42 = 0;
        if ( a2 )
        {
          do
            ++v20;
          while ( a2[v20] );
          v27 = v20 + 1;
        }
        else
        {
          a2 = (const char *)&qword_1400150C8;
          v27 = 1;
        }
        v38 = v27;
        p_SRWLock = &SRWLock;
        v37 = a2;
        v34 = 8;
        v33 = &v31;
        v39 = 0;
        v36 = 4;
        tlgWriteTransfer_EventWriteTransfer(v13, byte_140019521, v17 + 8, v18, 8, v32);
      }
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v28 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v14,
                          1);
      *v28 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v28;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v28 = 0;
    }
  }
}

```

## disassembly

```asm
0x140008cac  push    rbp
0x140008cae  push    rbx
0x140008caf  push    rsi
0x140008cb0  push    rdi
0x140008cb1  push    r12
0x140008cb3  push    r13
0x140008cb5  push    r14
0x140008cb7  push    r15
0x140008cb9  lea     rbp, [rsp-17h]
0x140008cbe  sub     rsp, 0D8h
0x140008cc5  mov     rax, cs:__security_cookie
0x140008ccc  xor     rax, rsp
0x140008ccf  mov     [rbp+4Fh+var_50], rax
0x140008cd3  mov     r15, rdx
0x140008cd6  mov     rdi, r9
0x140008cd9  lea     rdx, [rsp+110h+SRWLock]
0x140008cde  mov     r14, r8
0x140008ce1  mov     rsi, rcx
0x140008ce4  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140008ce9  mov     rbx, [rsi+110h]
0x140008cf0  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x140008cf5  mov     r13, 400000000000h
0x140008cff  mov     edx, [rax]
0x140008d01  cmp     edx, 5
0x140008d04  jbe     short loc_140008D2F
0x140008d06  mov     rcx, [rax+18h]
0x140008d0a  mov     rax, [rax+10h]
0x140008d0e  test    r13, rax
0x140008d11  jz      short loc_140008D2F
0x140008d13  mov     rax, rcx
0x140008d16  and     rax, r13
0x140008d19  cmp     rax, rcx
0x140008d1c  jnz     short loc_140008D2F
0x140008d1e  lea     rdx, [rbx+8]; ActivityId
0x140008d22  mov     ecx, 3; ControlCode
0x140008d27  call    cs:__imp_EventActivityIdControl
0x140008d2d  jmp     short loc_140008D36
0x140008d2f  xorps   xmm0, xmm0
0x140008d32  movups  xmmword ptr [rbx+8], xmm0
0x140008d36  mov     rcx, [rsp+110h+SRWLock]; SRWLock
0x140008d3b  xor     r12d, r12d
0x140008d3e  mov     dword ptr [rbx], 1
0x140008d44  test    rcx, rcx
0x140008d47  jz      short loc_140008D4F
0x140008d49  call    cs:__imp_ReleaseSRWLockExclusive
0x140008d4f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x140008d54  mov     rbx, rax
0x140008d57  mov     ecx, [rax]
0x140008d59  cmp     ecx, 5
0x140008d5c  jbe     loc_140008EC3
0x140008d62  mov     rdx, [rax+18h]
0x140008d66  mov     rcx, [rax+10h]
0x140008d6a  test    r13, rcx
0x140008d6d  jz      loc_140008EC3
0x140008d73  mov     rcx, rdx
0x140008d76  and     rcx, r13
0x140008d79  cmp     rcx, rdx
0x140008d7c  jnz     loc_140008EC3
0x140008d82  call    cs:__imp_GetCurrentThreadId
0x140008d88  mov     r10, [rsi+110h]
0x140008d8f  mov     dword ptr [rsp+110h+SRWLock], eax
0x140008d93  mov     [rsp+110h+var_D8], 1000000h
0x140008d9c  cmp     [r10+4], r12b
0x140008da0  jz      short loc_140008DBD
0x140008da2  lea     r9, [r10+18h]
0x140008da6  cmp     [r9], r12d
0x140008da9  jnz     short loc_140008DC0
0x140008dab  cmp     [r9+4], r12d
0x140008daf  jnz     short loc_140008DC0
0x140008db1  cmp     [r9+8], r12d
0x140008db5  jnz     short loc_140008DC0
0x140008db7  cmp     [r9+0Ch], r12d
0x140008dbb  jnz     short loc_140008DC0
0x140008dbd  mov     r9, r12
0x140008dc0  mov     rax, [rbp+4Fh+arg_20]
0x140008dc4  lea     r11, dword_1400158BC
0x140008dcb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008dcf  mov     edx, 2
0x140008dd4  test    rax, rax
0x140008dd7  jz      short loc_140008DF0
0x140008dd9  mov     r8, rcx
0x140008ddc  inc     r8
0x140008ddf  cmp     [rax+r8*2], r12w
0x140008de4  jnz     short loc_140008DDC
0x140008de6  lea     r8d, ds:2[r8*2]
0x140008dee  jmp     short loc_140008DF6
0x140008df0  mov     rax, r11
0x140008df3  mov     r8d, edx
0x140008df6  mov     [rbp+4Fh+var_60], rax
0x140008dfa  mov     [rbp+4Fh+var_58], r8d
0x140008dfe  mov     [rbp+4Fh+var_54], r12d
0x140008e02  test    rdi, rdi
0x140008e05  jz      short loc_140008E1D
0x140008e07  mov     rax, rcx
0x140008e0a  inc     rax
0x140008e0d  cmp     [rdi+rax*2], r12w
0x140008e12  jnz     short loc_140008E0A
0x140008e14  lea     eax, ds:2[rax*2]
0x140008e1b  jmp     short loc_140008E22
0x140008e1d  mov     rdi, r11
0x140008e20  mov     eax, edx
0x140008e22  mov     [rbp+4Fh+var_70], rdi
0x140008e26  mov     [rbp+4Fh+var_68], eax
0x140008e29  mov     [rbp+4Fh+var_64], r12d
0x140008e2d  test    r14, r14
0x140008e30  jz      short loc_140008E48
0x140008e32  mov     rax, rcx
0x140008e35  inc     rax
0x140008e38  cmp     [r14+rax*2], r12w
0x140008e3d  jnz     short loc_140008E35
0x140008e3f  lea     edx, ds:2[rax*2]
0x140008e46  jmp     short loc_140008E4B
0x140008e48  mov     r14, r11
0x140008e4b  mov     [rbp+4Fh+var_80], r14
0x140008e4f  mov     [rbp+4Fh+var_78], edx
0x140008e52  mov     [rbp+4Fh+var_74], r12d
0x140008e56  test    r15, r15
0x140008e59  jz      short loc_140008E68
0x140008e5b  inc     rcx
0x140008e5e  cmp     [r15+rcx], r12b
0x140008e62  jnz     short loc_140008E5B
0x140008e64  inc     ecx
0x140008e66  jmp     short loc_140008E74
0x140008e68  lea     r15, qword_1400150C8
0x140008e6f  mov     ecx, 1
0x140008e74  mov     [rbp+4Fh+var_88], ecx
0x140008e77  lea     rax, [rsp+110h+SRWLock]
0x140008e7c  mov     [rbp+4Fh+var_A0], rax
0x140008e80  lea     r8, [r10+8]
0x140008e84  mov     ecx, 8
0x140008e89  mov     [rbp+4Fh+var_90], r15
0x140008e8d  lea     rax, [rsp+110h+var_D8]
0x140008e92  mov     [rbp+4Fh+var_A8], rcx
0x140008e96  mov     [rbp+4Fh+var_B0], rax
0x140008e9a  lea     rdx, byte_140019521
0x140008ea1  lea     rax, [rsp+110h+var_D0]
0x140008ea6  mov     [rbp+4Fh+var_84], r12d
0x140008eaa  mov     [rsp+110h+var_E8], rax
0x140008eaf  mov     [rsp+110h+var_F0], ecx
0x140008eb3  mov     rcx, rbx
0x140008eb6  mov     [rbp+4Fh+var_98], 4
0x140008ebe  call    _tlgWriteTransfer_EventWriteTransfer
0x140008ec3  cmp     [rsi+138h], r12d
0x140008eca  jnz     short loc_140008F03
0x140008ecc  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r12; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140008ed3  lea     rbx, [rsi+120h]
0x140008eda  jz      short loc_140008F00
0x140008edc  mov     dl, 1
0x140008ede  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x140008ee3  mov     [rbx], rax
0x140008ee6  test    rax, rax
0x140008ee9  jz      short loc_140008F03
0x140008eeb  mov     rcx, [rax]
0x140008eee  mov     [rbx+10h], rcx
0x140008ef2  mov     [rax], rbx
0x140008ef5  call    cs:__imp_GetCurrentThreadId
0x140008efb  mov     [rbx+18h], eax
0x140008efe  jmp     short loc_140008F03
0x140008f00  mov     [rbx], r12
0x140008f03  mov     rcx, [rbp+4Fh+var_50]
0x140008f07  xor     rcx, rsp; StackCookie
0x140008f0a  call    __security_check_cookie
0x140008f0f  add     rsp, 0D8h
0x140008f16  pop     r15
0x140008f18  pop     r14
0x140008f1a  pop     r13
0x140008f1c  pop     r12
0x140008f1e  pop     rdi
0x140008f1f  pop     rsi
0x140008f20  pop     rbx
0x140008f21  pop     rbp
0x140008f22  retn
```
