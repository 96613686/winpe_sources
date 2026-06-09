# Windows::Telemetry::ServiceBase::PreventSleep::StartActivity(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180085c44`
- end: `0x180085e54`
- name: `?StartActivity@PreventSleep@ServiceBase@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180089150`

## callees

- `0x180001350`
- `0x1800857a8`
- `0x180085c44`
- `0x18008c454`
- `0x18008d0c4`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085ce7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180085ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085d20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085d20`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180085cc9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180085cc9`

## pseudocode

```c
void __fastcall Windows::Telemetry::ServiceBase::PreventSleep::StartActivity(
        __int64 a1,
        const OLECHAR **a2,
        const OLECHAR **a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rsi
  const OLECHAR *v11; // rbx
  const OLECHAR *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  const GUID *v15; // r9
  int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // ecx
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-59h] BYREF
  __int64 v21; // [rsp+40h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+48h] [rbp-49h] BYREF
  __int64 *v23; // [rsp+68h] [rbp-29h]
  __int64 v24; // [rsp+70h] [rbp-21h]
  PSRWLOCK *p_SRWLock; // [rsp+78h] [rbp-19h]
  __int64 v26; // [rsp+80h] [rbp-11h]
  const OLECHAR *v27; // [rsp+88h] [rbp-9h]
  int v28; // [rsp+90h] [rbp-1h]
  int v29; // [rsp+94h] [rbp+3h]
  const OLECHAR *v30; // [rsp+98h] [rbp+7h]
  int v31; // [rsp+A0h] [rbp+Fh]
  int v32; // [rsp+A4h] [rbp+13h]
  const char *v33; // [rsp+A8h] [rbp+17h]
  __int64 v34; // [rsp+B0h] [rbp+1Fh]

  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
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
  v10 = *((_QWORD *)Windows::Telemetry::ServiceBase::Instance() + 1);
  if ( *(_DWORD *)v10 > 5u
    && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
  {
    v11 = *a3;
    v12 = *a2;
    CurrentThreadId = GetCurrentThreadId();
    v14 = *(_QWORD *)(a1 + 272);
    LODWORD(SRWLock) = CurrentThreadId;
    v21 = 0x1000000;
    if ( !*(_BYTE *)(v14 + 4)
      || (v15 = (const GUID *)(v14 + 24), !*(_DWORD *)(v14 + 24))
      && !*(_DWORD *)(v14 + 28)
      && !*(_DWORD *)(v14 + 32)
      && !*(_DWORD *)(v14 + 36) )
    {
      v15 = 0;
    }
    v34 = 18;
    v33 = "1507.2603.28012.0";
    v16 = 2;
    v17 = -1;
    if ( v11 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v11[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v11 = &S1;
      v19 = 2;
    }
    v30 = v11;
    v31 = v19;
    v32 = 0;
    if ( v12 )
    {
      do
        ++v17;
      while ( v12[v17] );
      v16 = 2 * v17 + 2;
    }
    else
    {
      v12 = &S1;
    }
    v28 = v16;
    p_SRWLock = &SRWLock;
    v27 = v12;
    v23 = &v21;
    v29 = 0;
    v26 = 4;
    v24 = 8;
    tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)&byte_1801310E9, (const GUID *)(v14 + 8), v15, 7u, &v22);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (wil::details::ThreadFailureCallbackHolder *)(a1 + 288),
      v9);
}

```

## disassembly

```asm
0x180085c44  mov     rax, rsp
0x180085c47  mov     [rax+10h], rbx
0x180085c4b  mov     [rax+18h], rsi
0x180085c4f  mov     [rax+20h], rdi
0x180085c53  push    rbp
0x180085c54  push    r12
0x180085c56  push    r13
0x180085c58  push    r14
0x180085c5a  push    r15
0x180085c5c  lea     rbp, [rax-5Fh]
0x180085c60  sub     rsp, 0C0h
0x180085c67  mov     rax, cs:__security_cookie
0x180085c6e  xor     rax, rsp
0x180085c71  mov     [rbp+57h+var_30], rax
0x180085c75  mov     r15, rdx
0x180085c78  xor     r12d, r12d
0x180085c7b  lea     rdx, [rbp+57h+SRWLock]
0x180085c7f  mov     [rbp+57h+SRWLock], r12
0x180085c83  mov     rdi, r8
0x180085c86  mov     r14, rcx
0x180085c89  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180085c8e  mov     rbx, [r14+110h]
0x180085c95  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180085c9a  mov     r13, 400000000000h
0x180085ca4  mov     rcx, [rax+8]
0x180085ca8  cmp     dword ptr [rcx], 5
0x180085cab  jbe     short loc_180085CD1
0x180085cad  test    [rcx+10h], r13
0x180085cb1  jz      short loc_180085CD1
0x180085cb3  mov     rax, [rcx+18h]
0x180085cb7  and     rax, r13
0x180085cba  cmp     rax, [rcx+18h]
0x180085cbe  jnz     short loc_180085CD1
0x180085cc0  lea     rdx, [rbx+8]; ActivityId
0x180085cc4  lea     ecx, [r12+3]; ControlCode
0x180085cc9  call    cs:__imp_EventActivityIdControl
0x180085ccf  jmp     short loc_180085CD8
0x180085cd1  xorps   xmm0, xmm0
0x180085cd4  movups  xmmword ptr [rbx+8], xmm0
0x180085cd8  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180085cdc  mov     dword ptr [rbx], 1
0x180085ce2  test    rcx, rcx
0x180085ce5  jz      short loc_180085CED
0x180085ce7  call    cs:__imp_ReleaseSRWLockExclusive
0x180085ced  call    ?Instance@ServiceBase@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::ServiceBase::Instance(void)
0x180085cf2  mov     rsi, [rax+8]
0x180085cf6  cmp     dword ptr [rsi], 5
0x180085cf9  jbe     loc_180085E15
0x180085cff  test    [rsi+10h], r13
0x180085d03  jz      loc_180085E15
0x180085d09  mov     rax, [rsi+18h]
0x180085d0d  and     rax, r13
0x180085d10  cmp     rax, [rsi+18h]
0x180085d14  jnz     loc_180085E15
0x180085d1a  mov     rbx, [rdi]
0x180085d1d  mov     rdi, [r15]
0x180085d20  call    cs:__imp_GetCurrentThreadId
0x180085d26  mov     r8, [r14+110h]
0x180085d2d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180085d30  mov     [rbp+57h+var_A8], 1000000h
0x180085d38  cmp     [r8+4], r12b
0x180085d3c  jz      short loc_180085D59
0x180085d3e  lea     r9, [r8+18h]
0x180085d42  cmp     [r9], r12d
0x180085d45  jnz     short loc_180085D5C
0x180085d47  cmp     [r9+4], r12d
0x180085d4b  jnz     short loc_180085D5C
0x180085d4d  cmp     [r9+8], r12d
0x180085d51  jnz     short loc_180085D5C
0x180085d53  cmp     [r9+0Ch], r12d
0x180085d57  jnz     short loc_180085D5C
0x180085d59  mov     r9, r12; int
0x180085d5c  lea     rax, a15072603280120; "1507.2603.28012.0"
0x180085d63  mov     [rbp+57h+var_38], 12h
0x180085d6b  mov     [rbp+57h+var_40], rax
0x180085d6f  mov     edx, 2
0x180085d74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085d78  test    rbx, rbx
0x180085d7b  jz      short loc_180085D93
0x180085d7d  mov     rcx, rax
0x180085d80  inc     rcx
0x180085d83  cmp     [rbx+rcx*2], r12w
0x180085d88  jnz     short loc_180085D80
0x180085d8a  lea     ecx, ds:2[rcx*2]
0x180085d91  jmp     short loc_180085D9C
0x180085d93  lea     rbx, S1
0x180085d9a  mov     ecx, edx
0x180085d9c  mov     [rbp+57h+var_50], rbx
0x180085da0  mov     [rbp+57h+var_48], ecx
0x180085da3  mov     [rbp+57h+var_44], r12d
0x180085da7  test    rdi, rdi
0x180085daa  jz      short loc_180085DBF
0x180085dac  inc     rax
0x180085daf  cmp     [rdi+rax*2], r12w
0x180085db4  jnz     short loc_180085DAC
0x180085db6  lea     edx, ds:2[rax*2]
0x180085dbd  jmp     short loc_180085DC6
0x180085dbf  lea     rdi, S1
0x180085dc6  lea     rax, [rbp+57h+SRWLock]
0x180085dca  mov     [rbp+57h+var_58], edx
0x180085dcd  mov     [rbp+57h+var_70], rax
0x180085dd1  lea     rdx, byte_1801310E9; int
0x180085dd8  lea     rax, [rbp+57h+var_A8]
0x180085ddc  mov     [rbp+57h+var_60], rdi
0x180085de0  mov     [rbp+57h+var_80], rax
0x180085de4  add     r8, 8; int
0x180085de8  lea     rax, [rbp+57h+var_A0]
0x180085dec  mov     [rbp+57h+var_54], r12d
0x180085df0  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x180085df5  mov     rcx, rsi; int
0x180085df8  mov     [rsp+0E0h+var_C0], 7; ULONG
0x180085e00  mov     [rbp+57h+var_68], 4
0x180085e08  mov     [rbp+57h+var_78], 8
0x180085e10  call    _tlgWriteTransfer_EventWriteTransfer
0x180085e15  lea     rcx, [r14+120h]; this
0x180085e1c  cmp     [rcx+18h], r12d
0x180085e20  jnz     short loc_180085E27
0x180085e22  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180085e27  mov     rcx, [rbp+57h+var_30]
0x180085e2b  xor     rcx, rsp; StackCookie
0x180085e2e  call    __security_check_cookie
0x180085e33  lea     r11, [rsp+0E0h+var_20]
0x180085e3b  mov     rbx, [r11+38h]
0x180085e3f  mov     rsi, [r11+40h]
0x180085e43  mov     rdi, [r11+48h]
0x180085e47  mov     rsp, r11
0x180085e4a  pop     r15
0x180085e4c  pop     r14
0x180085e4e  pop     r13
0x180085e50  pop     r12
0x180085e52  pop     rbp
0x180085e53  retn
```
