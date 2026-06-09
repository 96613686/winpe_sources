# CmAgentTraceProvider::ApplyAdjustments::StartActivity(ushort const *)

- ea: `0x18001bb20`
- end: `0x18001bc84`
- name: `?StartActivity@ApplyAdjustments@CmAgentTraceProvider@@QEAAXPEBG@Z`
- size: `356`
- prototype: `void __fastcall(CmAgentTraceProvider::ApplyAdjustments *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001613c`

## callees

- `0x180001970`
- `0x180002140`
- `0x180006fcc`
- `0x1800088b0`
- `0x180009940`
- `0x18001bb20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb94`

## pseudocode

```c
void __fastcall CmAgentTraceProvider::ApplyAdjustments::StartActivity(
        CmAgentTraceProvider::ApplyAdjustments *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  int v9; // eax
  DWORD v10; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+38h] [rbp-21h] BYREF
  char v12[32]; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+7h]
  __int64 v14; // [rsp+68h] [rbp+Fh]
  DWORD *v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  const unsigned __int16 *v17; // [rsp+80h] [rbp+27h]
  int v18; // [rsp+88h] [rbp+2Fh]
  int v19; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = *((_QWORD *)CmAgentTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u
    && (*(_QWORD *)(v4 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v4 + 24) & 0x400000000000LL) == *(_QWORD *)(v4 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v10 = CurrentThreadId;
    v11 = 0x1000000;
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    if ( a2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      a2 = &qword_18003F6C0;
      v9 = 2;
    }
    v18 = v9;
    v17 = a2;
    v15 = &v10;
    v19 = 0;
    v13 = &v11;
    v16 = 4;
    v14 = 8;
    tlgWriteTransfer_EventWriteTransfer(v4, &dword_1800439D4, v6 + 8, v7, 5, v12);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CmAgentTraceProvider::ApplyAdjustments *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001bb20  mov     [rsp-8+arg_8], rbx
0x18001bb25  mov     [rsp-8+arg_10], rsi
0x18001bb2a  push    rbp
0x18001bb2b  push    rdi
0x18001bb2c  push    r14
0x18001bb2e  lea     rbp, [rsp-47h]
0x18001bb33  sub     rsp, 0A0h
0x18001bb3a  mov     rax, cs:__security_cookie
0x18001bb41  xor     rax, rsp
0x18001bb44  mov     [rbp+57h+var_20], rax
0x18001bb48  mov     rbx, rdx
0x18001bb4b  mov     rdi, rcx
0x18001bb4e  call    ?zInternalStart@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001bb53  call    ?Instance@CmAgentTraceProvider@@KAPEAV1@XZ; CmAgentTraceProvider::Instance(void)
0x18001bb58  xor     r14d, r14d
0x18001bb5b  mov     rsi, [rax+8]
0x18001bb5f  mov     eax, [rsi]
0x18001bb61  cmp     eax, 5
0x18001bb64  jbe     loc_18001BC4D
0x18001bb6a  mov     rcx, [rsi+18h]
0x18001bb6e  mov     rdx, 400000000000h
0x18001bb78  mov     rax, [rsi+10h]
0x18001bb7c  test    rdx, rax
0x18001bb7f  jz      loc_18001BC4D
0x18001bb85  mov     rax, rcx
0x18001bb88  and     rax, rdx
0x18001bb8b  cmp     rax, rcx
0x18001bb8e  jnz     loc_18001BC4D
0x18001bb94  call    cs:__imp_GetCurrentThreadId
0x18001bb9b  nop     dword ptr [rax+rax+00h]
0x18001bba0  mov     r8, [rdi+110h]
0x18001bba7  mov     [rbp+57h+var_80], eax
0x18001bbaa  mov     [rbp+57h+var_78], 1000000h
0x18001bbb2  cmp     [r8+4], r14b
0x18001bbb6  jz      short loc_18001BBD3
0x18001bbb8  lea     r9, [r8+18h]
0x18001bbbc  cmp     [r9], r14d
0x18001bbbf  jnz     short loc_18001BBD6
0x18001bbc1  cmp     [r9+4], r14d
0x18001bbc5  jnz     short loc_18001BBD6
0x18001bbc7  cmp     [r9+8], r14d
0x18001bbcb  jnz     short loc_18001BBD6
0x18001bbcd  cmp     [r9+0Ch], r14d
0x18001bbd1  jnz     short loc_18001BBD6
0x18001bbd3  mov     r9, r14
0x18001bbd6  test    rbx, rbx
0x18001bbd9  jz      short loc_18001BBF2
0x18001bbdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bbdf  inc     rax
0x18001bbe2  cmp     [rbx+rax*2], r14w
0x18001bbe7  jnz     short loc_18001BBDF
0x18001bbe9  lea     eax, ds:2[rax*2]
0x18001bbf0  jmp     short loc_18001BBFE
0x18001bbf2  lea     rbx, qword_18003F6C0
0x18001bbf9  mov     eax, 2
0x18001bbfe  mov     [rbp+57h+var_28], eax
0x18001bc01  lea     rdx, dword_1800439D4
0x18001bc08  lea     rax, [rbp+57h+var_80]
0x18001bc0c  mov     [rbp+57h+var_30], rbx
0x18001bc10  mov     [rbp+57h+var_40], rax
0x18001bc14  add     r8, 8
0x18001bc18  lea     rax, [rbp+57h+var_78]
0x18001bc1c  mov     [rbp+57h+var_24], r14d
0x18001bc20  mov     [rbp+57h+var_50], rax
0x18001bc24  mov     rcx, rsi
0x18001bc27  lea     rax, [rbp+57h+var_70]
0x18001bc2b  mov     [rbp+57h+var_38], 4
0x18001bc33  mov     [rsp+0B0h+var_88], rax
0x18001bc38  mov     [rsp+0B0h+var_90], 5
0x18001bc40  mov     [rbp+57h+var_48], 8
0x18001bc48  call    _tlgWriteTransfer_EventWriteTransfer
0x18001bc4d  lea     rcx, [rdi+120h]; this
0x18001bc54  cmp     [rcx+18h], r14d
0x18001bc58  jnz     short loc_18001BC5F
0x18001bc5a  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001bc5f  mov     rcx, [rbp+57h+var_20]
0x18001bc63  xor     rcx, rsp; StackCookie
0x18001bc66  call    __security_check_cookie
0x18001bc6b  lea     r11, [rsp+0B0h+var_10]
0x18001bc73  mov     rbx, [r11+28h]
0x18001bc77  mov     rsi, [r11+30h]
0x18001bc7b  mov     rsp, r11
0x18001bc7e  pop     r14
0x18001bc80  pop     rdi
0x18001bc81  pop     rbp
0x18001bc82  retn
```
