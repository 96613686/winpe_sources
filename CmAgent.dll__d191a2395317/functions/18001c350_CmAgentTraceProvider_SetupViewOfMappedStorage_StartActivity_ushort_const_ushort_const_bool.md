# CmAgentTraceProvider::SetupViewOfMappedStorage::StartActivity(ushort const *,ushort const *,bool)

- ea: `0x18001c350`
- end: `0x18001c506`
- name: `?StartActivity@SetupViewOfMappedStorage@CmAgentTraceProvider@@QEAAXPEBG0_N@Z`
- size: `438`
- prototype: `void __fastcall(CmAgentTraceProvider::SetupViewOfMappedStorage *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001ae40`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001c350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c3d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c3d3`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::SetupViewOfMappedStorage::StartActivity(
        CmAgentTraceProvider::SetupViewOfMappedStorage *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 v8; // r15
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r9
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ecx
  char v16; // [rsp+30h] [rbp-59h] BYREF
  DWORD v17; // [rsp+34h] [rbp-55h] BYREF
  __int64 v18; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v20; // [rsp+60h] [rbp-29h]
  __int64 v21; // [rsp+68h] [rbp-21h]
  DWORD *v22; // [rsp+70h] [rbp-19h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  const unsigned __int16 *v24; // [rsp+80h] [rbp-9h]
  int v25; // [rsp+88h] [rbp-1h]
  int v26; // [rsp+8Ch] [rbp+3h]
  const unsigned __int16 *v27; // [rsp+90h] [rbp+7h]
  int v28; // [rsp+98h] [rbp+Fh]
  int v29; // [rsp+9Ch] [rbp+13h]
  char *v30; // [rsp+A0h] [rbp+17h]
  __int64 v31; // [rsp+A8h] [rbp+1Fh]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v8 > 5u
    && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
  {
    v16 = a4;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    v17 = CurrentThreadId;
    v18 = 0x1000000;
    if ( !*(_BYTE *)(v10 + 4)
      || (v11 = (const GUID *)(v10 + 24), !*(_DWORD *)(v10 + 24))
      && !*(_DWORD *)(v10 + 28)
      && !*(_DWORD *)(v10 + 32)
      && !*(_DWORD *)(v10 + 36) )
    {
      v11 = 0;
    }
    v31 = 1;
    v30 = &v16;
    v12 = 2;
    v13 = -1;
    if ( a3 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      a3 = &qword_18003F6C0;
      v15 = 2;
    }
    v27 = a3;
    v28 = v15;
    v29 = 0;
    if ( a2 )
    {
      do
        ++v13;
      while ( a2[v13] );
      v12 = 2 * v13 + 2;
    }
    else
    {
      a2 = &qword_18003F6C0;
    }
    v25 = v12;
    v22 = &v17;
    v24 = a2;
    v20 = &v18;
    v26 = 0;
    v23 = 4;
    v21 = 8;
    tlgWriteTransfer_EventWriteTransfer(v8, (unsigned __int8 *)word_1800432EA, (const GUID *)(v10 + 8), v11, 7u, &v19);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::SetupViewOfMappedStorage *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001c350  mov     [rsp-8+arg_8], rbx
0x18001c355  mov     [rsp-8+arg_10], rsi
0x18001c35a  push    rbp
0x18001c35b  push    rdi
0x18001c35c  push    r12
0x18001c35e  push    r14
0x18001c360  push    r15
0x18001c362  lea     rbp, [rsp-37h]
0x18001c367  sub     rsp, 0C0h
0x18001c36e  mov     rax, cs:__security_cookie
0x18001c375  xor     rax, rsp
0x18001c378  mov     [rbp+57h+var_30], rax
0x18001c37c  mov     dil, r9b
0x18001c37f  mov     rbx, r8
0x18001c382  mov     rsi, rdx
0x18001c385  mov     r14, rcx
0x18001c388  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001c38d  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001c392  xor     r12d, r12d
0x18001c395  mov     r15, [rax+8]
0x18001c399  mov     eax, [r15]
0x18001c39c  cmp     eax, 5
0x18001c39f  jbe     loc_18001C4CB
0x18001c3a5  mov     rcx, [r15+18h]
0x18001c3a9  mov     rdx, 400000000000h
0x18001c3b3  mov     rax, [r15+10h]
0x18001c3b7  test    rdx, rax
0x18001c3ba  jz      loc_18001C4CB
0x18001c3c0  mov     rax, rcx
0x18001c3c3  and     rax, rdx
0x18001c3c6  cmp     rax, rcx
0x18001c3c9  jnz     loc_18001C4CB
0x18001c3cf  mov     [rbp+57h+var_B0], dil
0x18001c3d3  call    cs:__imp_GetCurrentThreadId
0x18001c3da  nop     dword ptr [rax+rax+00h]
0x18001c3df  mov     r8, [r14+110h]
0x18001c3e6  mov     [rbp+57h+var_AC], eax
0x18001c3e9  mov     [rbp+57h+var_A8], 1000000h
0x18001c3f1  cmp     [r8+4], r12b
0x18001c3f5  jz      short loc_18001C412
0x18001c3f7  lea     r9, [r8+18h]
0x18001c3fb  cmp     [r9], r12d
0x18001c3fe  jnz     short loc_18001C415
0x18001c400  cmp     [r9+4], r12d
0x18001c404  jnz     short loc_18001C415
0x18001c406  cmp     [r9+8], r12d
0x18001c40a  jnz     short loc_18001C415
0x18001c40c  cmp     [r9+0Ch], r12d
0x18001c410  jnz     short loc_18001C415
0x18001c412  mov     r9, r12
0x18001c415  lea     rax, [rbp+57h+var_B0]
0x18001c419  mov     [rbp+57h+var_38], 1
0x18001c421  mov     [rbp+57h+var_40], rax
0x18001c425  mov     edx, 2
0x18001c42a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c42e  test    rbx, rbx
0x18001c431  jz      short loc_18001C449
0x18001c433  mov     rcx, rax
0x18001c436  inc     rcx
0x18001c439  cmp     [rbx+rcx*2], r12w
0x18001c43e  jnz     short loc_18001C436
0x18001c440  lea     ecx, ds:2[rcx*2]
0x18001c447  jmp     short loc_18001C452
0x18001c449  lea     rbx, qword_18003F6C0
0x18001c450  mov     ecx, edx
0x18001c452  mov     [rbp+57h+var_50], rbx
0x18001c456  mov     [rbp+57h+var_48], ecx
0x18001c459  mov     [rbp+57h+var_44], r12d
0x18001c45d  test    rsi, rsi
0x18001c460  jz      short loc_18001C475
0x18001c462  inc     rax
0x18001c465  cmp     [rsi+rax*2], r12w
0x18001c46a  jnz     short loc_18001C462
0x18001c46c  lea     edx, ds:2[rax*2]
0x18001c473  jmp     short loc_18001C47C
0x18001c475  lea     rsi, qword_18003F6C0
0x18001c47c  lea     rax, [rbp+57h+var_AC]
0x18001c480  mov     [rbp+57h+var_58], edx
0x18001c483  mov     [rbp+57h+var_70], rax
0x18001c487  lea     rdx, word_1800432EA
0x18001c48e  lea     rax, [rbp+57h+var_A8]
0x18001c492  mov     [rbp+57h+var_60], rsi
0x18001c496  mov     [rbp+57h+var_80], rax
0x18001c49a  add     r8, 8
0x18001c49e  lea     rax, [rbp+57h+var_A0]
0x18001c4a2  mov     [rbp+57h+var_54], r12d
0x18001c4a6  mov     [rsp+0E0h+var_B8], rax
0x18001c4ab  mov     rcx, r15
0x18001c4ae  mov     [rsp+0E0h+var_C0], 7
0x18001c4b6  mov     [rbp+57h+var_68], 4
0x18001c4be  mov     [rbp+57h+var_78], 8
0x18001c4c6  call    _tlgWriteTransfer_EventWriteTransfer
0x18001c4cb  lea     rcx, [r14+120h]; this
0x18001c4d2  cmp     [rcx+18h], r12d
0x18001c4d6  jnz     short loc_18001C4DD
0x18001c4d8  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001c4dd  mov     rcx, [rbp+57h+var_30]
0x18001c4e1  xor     rcx, rsp; StackCookie
0x18001c4e4  call    __security_check_cookie
0x18001c4e9  lea     r11, [rsp+0E0h+var_20]
0x18001c4f1  mov     rbx, [r11+38h]
0x18001c4f5  mov     rsi, [r11+40h]
0x18001c4f9  mov     rsp, r11
0x18001c4fc  pop     r15
0x18001c4fe  pop     r14
0x18001c500  pop     r12
0x18001c502  pop     rdi
0x18001c503  pop     rbp
0x18001c504  retn
```
