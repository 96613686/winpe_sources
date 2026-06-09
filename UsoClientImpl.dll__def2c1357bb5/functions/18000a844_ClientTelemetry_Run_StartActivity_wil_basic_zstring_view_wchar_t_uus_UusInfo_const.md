# ClientTelemetry::Run::StartActivity(wil::basic_zstring_view<wchar_t>,uus::UusInfo const &)

- ea: `0x18000a844`
- end: `0x18000aa85`
- name: `?StartActivity@Run@ClientTelemetry@@QEAAXV?$basic_zstring_view@_W@wil@@AEBUUusInfo@uus@@@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018920`

## callees

- `0x180001f60`
- `0x18000a2ac`
- `0x18000a844`
- `0x18001a1bc`
- `0x180035e54`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a8eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a930`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a930`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a8cd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000a8cd`

## pseudocode

```c
void __fastcall ClientTelemetry::Run::StartActivity(__int64 a1, const wchar_t **a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __int64 v6; // rbx
  __int64 v7; // rcx
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r14
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rdi
  const wchar_t *v13; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  const GUID *v16; // r9
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-69h] BYREF
  __int64 v24; // [rsp+38h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+40h] [rbp-59h] BYREF
  __int64 *v26; // [rsp+60h] [rbp-39h]
  __int64 v27; // [rsp+68h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp-29h]
  __int64 v29; // [rsp+78h] [rbp-21h]
  const wchar_t *v30; // [rsp+80h] [rbp-19h]
  int v31; // [rsp+88h] [rbp-11h]
  int v32; // [rsp+8Ch] [rbp-Dh]
  const char *v33; // [rsp+90h] [rbp-9h]
  __int64 v34; // [rsp+98h] [rbp-1h]
  const wchar_t *v35; // [rsp+A0h] [rbp+7h]
  int v36; // [rsp+A8h] [rbp+Fh]
  int v37; // [rsp+ACh] [rbp+13h]
  const wchar_t *v38; // [rsp+B0h] [rbp+17h]
  int v39; // [rsp+B8h] [rbp+1Fh]
  int v40; // [rsp+BCh] [rbp+23h]

  v3 = *a3;
  SRWLock = 0;
  *(_OWORD *)(a1 + 328) = v3;
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *((_QWORD *)ClientTelemetry::Instance() + 1);
  if ( *(_DWORD *)v7 > 5u
    && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
  {
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  }
  else
  {
    *(_OWORD *)(v6 + 8) = 0;
  }
  v8 = SRWLock;
  *(_DWORD *)v6 = 1;
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  v10 = *((_QWORD *)ClientTelemetry::Instance() + 1);
  if ( *(_DWORD *)v10 > 5u
    && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
  {
    v11 = *(const wchar_t **)(a1 + 336);
    v12 = *(const wchar_t **)(a1 + 328);
    v13 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v15 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v24 = 0x1000000;
    if ( !*(_BYTE *)(v15 + 4)
      || (v16 = (const GUID *)(v15 + 24), !*(_DWORD *)(v15 + 24))
      && !*(_DWORD *)(v15 + 28)
      && !*(_DWORD *)(v15 + 32)
      && !*(_DWORD *)(v15 + 36) )
    {
      v16 = 0;
    }
    v17 = -1;
    v18 = 2;
    if ( v11 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v11[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v11 = &S2;
      v20 = 2;
    }
    v38 = v11;
    v39 = v20;
    v40 = 0;
    if ( v12 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v12[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v12 = &S2;
      v22 = 2;
    }
    v36 = v22;
    v33 = "1507.2603.28012.0";
    v35 = v12;
    v37 = 0;
    v34 = 18;
    if ( v13 )
    {
      do
        ++v17;
      while ( v13[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v13 = &S2;
    }
    v31 = v18;
    v27 = 8;
    p_SRWLock = &SRWLock;
    v30 = v13;
    v26 = &v24;
    v32 = 0;
    v29 = 4;
    tlgWriteTransfer_EventWriteTransfer(
      v10,
      (unsigned __int8 *)&dword_180090B84,
      (const GUID *)(v15 + 8),
      v16,
      8u,
      &v25);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v9);
}

```

## disassembly

```asm
0x18000a844  mov     [rsp-8+arg_8], rbx
0x18000a849  mov     [rsp-8+arg_10], rsi
0x18000a84e  push    rbp
0x18000a84f  push    rdi
0x18000a850  push    r12
0x18000a852  push    r14
0x18000a854  push    r15
0x18000a856  lea     rbp, [rsp-37h]
0x18000a85b  sub     rsp, 0D0h
0x18000a862  mov     rax, cs:__security_cookie
0x18000a869  xor     rax, rsp
0x18000a86c  mov     [rbp+57h+var_30], rax
0x18000a870  movups  xmm0, xmmword ptr [r8]
0x18000a874  mov     rsi, rdx
0x18000a877  xor     r12d, r12d
0x18000a87a  lea     rdx, [rbp+57h+SRWLock]
0x18000a87e  mov     [rbp+57h+SRWLock], r12
0x18000a882  movdqu  xmmword ptr [rcx+148h], xmm0
0x18000a88a  mov     r15, rcx
0x18000a88d  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000a892  mov     rbx, [r15+110h]
0x18000a899  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000a89e  mov     rdi, 400000000000h
0x18000a8a8  mov     rcx, [rax+8]
0x18000a8ac  cmp     dword ptr [rcx], 5
0x18000a8af  jbe     short loc_18000A8D5
0x18000a8b1  test    [rcx+10h], rdi
0x18000a8b5  jz      short loc_18000A8D5
0x18000a8b7  mov     rax, [rcx+18h]
0x18000a8bb  and     rax, rdi
0x18000a8be  cmp     rax, [rcx+18h]
0x18000a8c2  jnz     short loc_18000A8D5
0x18000a8c4  lea     rdx, [rbx+8]; ActivityId
0x18000a8c8  lea     ecx, [r12+3]; ControlCode
0x18000a8cd  call    cs:__imp_EventActivityIdControl
0x18000a8d3  jmp     short loc_18000A8DC
0x18000a8d5  xorps   xmm0, xmm0
0x18000a8d8  movups  xmmword ptr [rbx+8], xmm0
0x18000a8dc  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18000a8e0  mov     dword ptr [rbx], 1
0x18000a8e6  test    rcx, rcx
0x18000a8e9  jz      short loc_18000A8F1
0x18000a8eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a8f1  call    ?Instance@ClientTelemetry@@KAPEAV1@XZ; ClientTelemetry::Instance(void)
0x18000a8f6  mov     r14, [rax+8]
0x18000a8fa  cmp     dword ptr [r14], 5
0x18000a8fe  jbe     loc_18000AA4B
0x18000a904  test    [r14+10h], rdi
0x18000a908  jz      loc_18000AA4B
0x18000a90e  mov     rax, [r14+18h]
0x18000a912  and     rax, rdi
0x18000a915  cmp     rax, [r14+18h]
0x18000a919  jnz     loc_18000AA4B
0x18000a91f  mov     rbx, [r15+150h]
0x18000a926  mov     rdi, [r15+148h]
0x18000a92d  mov     rsi, [rsi]
0x18000a930  call    cs:__imp_GetCurrentThreadId
0x18000a936  mov     r8, [r15+110h]
0x18000a93d  mov     dword ptr [rbp+57h+SRWLock], eax
0x18000a940  mov     [rbp+57h+var_B8], 1000000h
0x18000a948  cmp     [r8+4], r12b
0x18000a94c  jz      short loc_18000A969
0x18000a94e  lea     r9, [r8+18h]
0x18000a952  cmp     [r9], r12d
0x18000a955  jnz     short loc_18000A96C
0x18000a957  cmp     [r9+4], r12d
0x18000a95b  jnz     short loc_18000A96C
0x18000a95d  cmp     [r9+8], r12d
0x18000a961  jnz     short loc_18000A96C
0x18000a963  cmp     [r9+0Ch], r12d
0x18000a967  jnz     short loc_18000A96C
0x18000a969  mov     r9, r12; int
0x18000a96c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a970  lea     r10, S2
0x18000a977  mov     edx, 2
0x18000a97c  test    rbx, rbx
0x18000a97f  jz      short loc_18000A997
0x18000a981  mov     rcx, rax
0x18000a984  inc     rcx
0x18000a987  cmp     [rbx+rcx*2], r12w
0x18000a98c  jnz     short loc_18000A984
0x18000a98e  lea     ecx, ds:2[rcx*2]
0x18000a995  jmp     short loc_18000A99C
0x18000a997  mov     rbx, r10
0x18000a99a  mov     ecx, edx
0x18000a99c  mov     [rbp+57h+var_40], rbx
0x18000a9a0  mov     [rbp+57h+var_38], ecx
0x18000a9a3  mov     [rbp+57h+var_34], r12d
0x18000a9a7  test    rdi, rdi
0x18000a9aa  jz      short loc_18000A9C2
0x18000a9ac  mov     rcx, rax
0x18000a9af  inc     rcx
0x18000a9b2  cmp     [rdi+rcx*2], r12w
0x18000a9b7  jnz     short loc_18000A9AF
0x18000a9b9  lea     ecx, ds:2[rcx*2]
0x18000a9c0  jmp     short loc_18000A9C7
0x18000a9c2  mov     rdi, r10
0x18000a9c5  mov     ecx, edx
0x18000a9c7  mov     [rbp+57h+var_48], ecx
0x18000a9ca  lea     rcx, a15072603280120; "1507.2603.28012.0"
0x18000a9d1  mov     [rbp+57h+var_60], rcx
0x18000a9d5  mov     [rbp+57h+var_50], rdi
0x18000a9d9  mov     [rbp+57h+var_44], r12d
0x18000a9dd  mov     [rbp+57h+var_58], 12h
0x18000a9e5  test    rsi, rsi
0x18000a9e8  jz      short loc_18000A9FD
0x18000a9ea  inc     rax
0x18000a9ed  cmp     [rsi+rax*2], r12w
0x18000a9f2  jnz     short loc_18000A9EA
0x18000a9f4  lea     edx, ds:2[rax*2]
0x18000a9fb  jmp     short loc_18000AA00
0x18000a9fd  mov     rsi, r10
0x18000aa00  mov     ecx, 8
0x18000aa05  mov     [rbp+57h+var_68], edx
0x18000aa08  lea     rax, [rbp+57h+SRWLock]
0x18000aa0c  mov     [rbp+57h+var_88], rcx
0x18000aa10  mov     [rbp+57h+var_80], rax
0x18000aa14  lea     rdx, dword_180090B84; int
0x18000aa1b  lea     rax, [rbp+57h+var_B8]
0x18000aa1f  mov     [rbp+57h+var_70], rsi
0x18000aa23  mov     [rbp+57h+var_90], rax
0x18000aa27  add     r8, rcx; int
0x18000aa2a  lea     rax, [rbp+57h+var_B0]
0x18000aa2e  mov     [rbp+57h+var_64], r12d
0x18000aa32  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x18000aa37  mov     [rsp+0F0h+var_D0], ecx; ULONG
0x18000aa3b  mov     rcx, r14; int
0x18000aa3e  mov     [rbp+57h+var_78], 4
0x18000aa46  call    _tlgWriteTransfer_EventWriteTransfer
0x18000aa4b  lea     rcx, [r15+120h]; this
0x18000aa52  cmp     [rcx+18h], r12d
0x18000aa56  jnz     short loc_18000AA5D
0x18000aa58  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000aa5d  mov     rcx, [rbp+57h+var_30]
0x18000aa61  xor     rcx, rsp; StackCookie
0x18000aa64  call    __security_check_cookie
0x18000aa69  lea     r11, [rsp+0F0h+var_20]
0x18000aa71  mov     rbx, [r11+38h]
0x18000aa75  mov     rsi, [r11+40h]
0x18000aa79  mov     rsp, r11
0x18000aa7c  pop     r15
0x18000aa7e  pop     r14
0x18000aa80  pop     r12
0x18000aa82  pop     rdi
0x18000aa83  pop     rbp
0x18000aa84  retn
```
