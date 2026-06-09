# HostNameVerifierProvider::VerifyAllInstalled::StartActivity(void)

- ea: `0x14000dfdc`
- end: `0x14000e0e5`
- name: `?StartActivity@VerifyAllInstalled@HostNameVerifierProvider@@QEAAXXZ`
- size: `265`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyAllInstalled *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14000ed9c`

## callees

- `0x140001b4c`
- `0x140001b78`
- `0x140002210`
- `0x14000b0f0`
- `0x14000da38`
- `0x14000dfdc`
- `0x140010c80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e030`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyAllInstalled::StartActivity(
        HostNameVerifierProvider::VerifyAllInstalled *this)
{
  __int64 v2; // rcx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD CurrentThreadId; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = HostNameVerifierProvider::Provider(v2);
  v5 = v3;
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    p_CurrentThreadId = &CurrentThreadId;
    v14 = 4;
    v11 = &v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, &unk_140015F98, v6 + 8, v7, 4, v10);
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000dfdc  mov     [rsp+arg_8], rbx
0x14000dfe1  push    rdi
0x14000dfe2  sub     rsp, 90h
0x14000dfe9  mov     rax, cs:__security_cookie
0x14000dff0  xor     rax, rsp
0x14000dff3  mov     [rsp+98h+var_18], rax
0x14000dffb  mov     rbx, rcx
0x14000dffe  call    ?zInternalStart@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000e003  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e008  mov     rdi, rax
0x14000e00b  mov     ecx, [rax]
0x14000e00d  cmp     ecx, 5
0x14000e010  jbe     loc_14000E0BB
0x14000e016  mov     rdx, 400000000000h
0x14000e020  mov     rcx, rax
0x14000e023  call    _tlgKeywordOn
0x14000e028  test    al, al
0x14000e02a  jz      loc_14000E0BB
0x14000e030  call    cs:__imp_GetCurrentThreadId
0x14000e036  mov     [rsp+98h+var_68], eax
0x14000e03a  mov     [rsp+98h+var_60], 1000000h
0x14000e043  mov     r8, [rbx+110h]
0x14000e04a  cmp     byte ptr [r8+4], 0
0x14000e04f  jz      short loc_14000E070
0x14000e051  lea     r9, [r8+18h]
0x14000e055  cmp     dword ptr [r9], 0
0x14000e059  jnz     short loc_14000E073
0x14000e05b  cmp     dword ptr [r9+4], 0
0x14000e060  jnz     short loc_14000E073
0x14000e062  cmp     dword ptr [r9+8], 0
0x14000e067  jnz     short loc_14000E073
0x14000e069  cmp     dword ptr [r9+0Ch], 0
0x14000e06e  jnz     short loc_14000E073
0x14000e070  xor     r9d, r9d
0x14000e073  lea     rax, [rsp+98h+var_68]
0x14000e078  mov     [rsp+98h+var_28], rax
0x14000e07d  mov     ecx, 4
0x14000e082  mov     [rsp+98h+var_20], rcx
0x14000e087  lea     rax, [rsp+98h+var_60]
0x14000e08c  mov     [rsp+98h+var_38], rax
0x14000e091  mov     [rsp+98h+var_30], 8
0x14000e09a  add     r8, 8
0x14000e09e  lea     rax, [rsp+98h+var_58]
0x14000e0a3  mov     [rsp+98h+var_70], rax
0x14000e0a8  mov     [rsp+98h+var_78], ecx
0x14000e0ac  lea     rdx, unk_140015F98
0x14000e0b3  mov     rcx, rdi
0x14000e0b6  call    _tlgWriteTransfer_EventWriteTransfer
0x14000e0bb  mov     rcx, rbx
0x14000e0be  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14000e0c3  nop
0x14000e0c4  mov     rcx, [rsp+98h+var_18]
0x14000e0cc  xor     rcx, rsp; StackCookie
0x14000e0cf  call    __security_check_cookie
0x14000e0d4  mov     rbx, [rsp+98h+arg_8]
0x14000e0dc  add     rsp, 90h
0x14000e0e3  pop     rdi
0x14000e0e4  retn
```
