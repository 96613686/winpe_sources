# CmAgentTraceProvider::NotifyCreating::StartActivity(utl::optional<_GUID> const &,utl::optional<_GUID> const &,bool,bool,utl::optional<ulong> const &,bool)

- ea: `0x18001bdc0`
- end: `0x18001bfab`
- name: `?StartActivity@NotifyCreating@CmAgentTraceProvider@@QEAAXAEBV?$optional@U_GUID@@@utl@@0_N1AEBV?$optional@K@4@1@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800178e0`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001bdc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001be8b`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::NotifyCreating::StartActivity(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        int *a6,
        char a7)
{
  GUID v7; // xmm0
  GUID v10; // xmm1
  int v11; // edi
  __int64 v12; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  const GUID *v15; // r9
  char v16; // [rsp+30h] [rbp-D0h] BYREF
  char v17; // [rsp+31h] [rbp-CFh] BYREF
  char v18; // [rsp+32h] [rbp-CEh] BYREF
  int v19; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  GUID v22; // [rsp+50h] [rbp-B0h] BYREF
  GUID v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  DWORD *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  GUID *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  GUID *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  char *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  char *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  int *v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  char *v39; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]

  v7 = GUID_NULL;
  if ( *(_BYTE *)(a2 + 16) )
    v10 = *(GUID *)a2;
  else
    v10 = GUID_NULL;
  v23 = v10;
  if ( *(_BYTE *)(a3 + 16) )
    v7 = *(GUID *)a3;
  v22 = v7;
  if ( *((_BYTE *)a6 + 4) )
    v11 = *a6;
  else
    v11 = 0;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v12 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v12 > 5u
    && (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v12 + 24) & 0x400000000000LL) == *(_QWORD *)(v12 + 24) )
  {
    v16 = a7;
    v17 = a5;
    v19 = v11;
    v18 = a4;
    CurrentThreadId = GetCurrentThreadId();
    v14 = *(_QWORD *)(a1 + 272);
    v20 = CurrentThreadId;
    v21 = 0x1000000;
    if ( !*(_BYTE *)(v14 + 4)
      || (v15 = (const GUID *)(v14 + 24), !*(_DWORD *)(v14 + 24))
      && !*(_DWORD *)(v14 + 28)
      && !*(_DWORD *)(v14 + 32)
      && !*(_DWORD *)(v14 + 36) )
    {
      v15 = 0;
    }
    v40 = 1;
    v39 = &v16;
    v38 = 4;
    v37 = &v19;
    v36 = 1;
    v35 = &v17;
    v34 = 1;
    v33 = &v18;
    v31 = &v22;
    v29 = &v23;
    v27 = &v20;
    v25 = &v21;
    v32 = 16;
    v30 = 16;
    v28 = 4;
    v26 = 8;
    tlgWriteTransfer_EventWriteTransfer(
      v12,
      (unsigned __int8 *)byte_1800446DB,
      (const GUID *)(v14 + 8),
      v15,
      0xAu,
      &v24);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18001bdc0  push    rbp
0x18001bdc2  push    rbx
0x18001bdc3  push    rsi
0x18001bdc4  push    rdi
0x18001bdc5  push    r14
0x18001bdc7  push    r15
0x18001bdc9  lea     rbp, [rsp-28h]
0x18001bdce  sub     rsp, 128h
0x18001bdd5  mov     rax, cs:__security_cookie
0x18001bddc  xor     rax, rsp
0x18001bddf  mov     [rbp+50h+var_40], rax
0x18001bde3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001bdea  xor     r15d, r15d
0x18001bded  mov     r14b, r9b
0x18001bdf0  mov     rsi, rcx
0x18001bdf3  cmp     [rdx+10h], r15b
0x18001bdf7  jz      short loc_18001BDFE
0x18001bdf9  movups  xmm1, xmmword ptr [rdx]
0x18001bdfc  jmp     short loc_18001BE01
0x18001bdfe  movups  xmm1, xmm0
0x18001be01  movdqa  [rsp+150h+var_F0], xmm1
0x18001be07  cmp     [r8+10h], r15b
0x18001be0b  jz      short loc_18001BE11
0x18001be0d  movups  xmm0, xmmword ptr [r8]
0x18001be11  mov     rax, [rbp+50h+arg_28]
0x18001be18  movdqa  [rsp+150h+var_100], xmm0
0x18001be1e  cmp     [rax+4], r15b
0x18001be22  jz      short loc_18001BE28
0x18001be24  mov     edi, [rax]
0x18001be26  jmp     short loc_18001BE2B
0x18001be28  mov     edi, r15d
0x18001be2b  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001be30  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001be35  mov     rbx, [rax+8]
0x18001be39  mov     eax, [rbx]
0x18001be3b  cmp     eax, 5
0x18001be3e  jbe     loc_18001BF7C
0x18001be44  mov     rcx, [rbx+18h]
0x18001be48  mov     rdx, 400000000000h
0x18001be52  mov     rax, [rbx+10h]
0x18001be56  test    rdx, rax
0x18001be59  jz      loc_18001BF7C
0x18001be5f  mov     rax, rcx
0x18001be62  and     rax, rdx
0x18001be65  cmp     rax, rcx
0x18001be68  jnz     loc_18001BF7C
0x18001be6e  mov     al, [rbp+50h+arg_30]
0x18001be74  mov     [rsp+150h+var_120], al
0x18001be78  mov     al, [rbp+50h+arg_20]
0x18001be7e  mov     [rsp+150h+var_11F], al
0x18001be82  mov     [rsp+150h+var_11C], edi
0x18001be86  mov     [rsp+150h+var_11E], r14b
0x18001be8b  call    cs:__imp_GetCurrentThreadId
0x18001be92  nop     dword ptr [rax+rax+00h]
0x18001be97  mov     r8, [rsi+110h]
0x18001be9e  mov     [rsp+150h+var_118], eax
0x18001bea2  mov     [rsp+150h+var_110], 1000000h
0x18001beab  cmp     [r8+4], r15b
0x18001beaf  jz      short loc_18001BECC
0x18001beb1  lea     r9, [r8+18h]
0x18001beb5  cmp     [r9], r15d
0x18001beb8  jnz     short loc_18001BECF
0x18001beba  cmp     [r9+4], r15d
0x18001bebe  jnz     short loc_18001BECF
0x18001bec0  cmp     [r9+8], r15d
0x18001bec4  jnz     short loc_18001BECF
0x18001bec6  cmp     [r9+0Ch], r15d
0x18001beca  jnz     short loc_18001BECF
0x18001becc  mov     r9, r15
0x18001becf  lea     rax, [rsp+150h+var_120]
0x18001bed4  mov     [rbp+50h+var_48], 1
0x18001bedc  mov     [rbp+50h+var_50], rax
0x18001bee0  lea     rdx, byte_1800446DB
0x18001bee7  lea     rax, [rsp+150h+var_11C]
0x18001beec  mov     [rbp+50h+var_58], 4
0x18001bef4  mov     [rbp+50h+var_60], rax
0x18001bef8  add     r8, 8
0x18001befc  lea     rax, [rsp+150h+var_11F]
0x18001bf01  mov     [rbp+50h+var_68], 1
0x18001bf09  mov     [rbp+50h+var_70], rax
0x18001bf0d  mov     rcx, rbx
0x18001bf10  lea     rax, [rsp+150h+var_11E]
0x18001bf15  mov     [rbp+50h+var_78], 1
0x18001bf1d  mov     [rbp+50h+var_80], rax
0x18001bf21  lea     rax, [rsp+150h+var_100]
0x18001bf26  mov     [rbp+50h+var_90], rax
0x18001bf2a  lea     rax, [rsp+150h+var_F0]
0x18001bf2f  mov     [rbp+50h+var_A0], rax
0x18001bf33  lea     rax, [rsp+150h+var_118]
0x18001bf38  mov     [rbp+50h+var_B0], rax
0x18001bf3c  lea     rax, [rsp+150h+var_110]
0x18001bf41  mov     [rbp+50h+var_C0], rax
0x18001bf45  lea     rax, [rsp+150h+var_E0]
0x18001bf4a  mov     [rsp+150h+var_128], rax
0x18001bf4f  mov     [rsp+150h+var_130], 0Ah
0x18001bf57  mov     [rbp+50h+var_88], 10h
0x18001bf5f  mov     [rbp+50h+var_98], 10h
0x18001bf67  mov     [rbp+50h+var_A8], 4
0x18001bf6f  mov     [rbp+50h+var_B8], 8
0x18001bf77  call    _tlgWriteTransfer_EventWriteTransfer
0x18001bf7c  lea     rcx, [rsi+120h]; this
0x18001bf83  cmp     [rcx+18h], r15d
0x18001bf87  jnz     short loc_18001BF8E
0x18001bf89  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001bf8e  mov     rcx, [rbp+50h+var_40]
0x18001bf92  xor     rcx, rsp; StackCookie
0x18001bf95  call    __security_check_cookie
0x18001bf9a  add     rsp, 128h
0x18001bfa1  pop     r15
0x18001bfa3  pop     r14
0x18001bfa5  pop     rdi
0x18001bfa6  pop     rsi
0x18001bfa7  pop     rbx
0x18001bfa8  pop     rbp
0x18001bfa9  retn
```
