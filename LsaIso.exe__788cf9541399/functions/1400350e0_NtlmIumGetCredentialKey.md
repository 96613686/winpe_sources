# NtlmIumGetCredentialKey

- ea: `0x1400350e0`
- end: `0x1400352ad`
- name: `NtlmIumGetCredentialKey`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140006720`
- `0x1400350e0`
- `0x140036038`
- `0x140036080`
- `0x140036330`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14003510a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14003510a`
- `NtlmShared!MsvpDeriveSecureCredKey` at `0x140035224`
- `NtlmShared!MsvpDeriveSecureCredKey` at `0x140035224`
- `ntdll!RtlLengthSid` at `0x14003518e`
- `ntdll!RtlLengthSid` at `0x14003518e`

## pseudocode

```c
__int64 __fastcall NtlmIumGetCredentialKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        struct _MSV1_0_SECRETS_WRAPPER *a4,
        int a5,
        PSID Sid,
        int a7,
        _BYTE *a8)
{
  struct _MSV1_0_SECRETS_WRAPPER *v8; // rdi
  int v12; // ebx
  _BYTE *v13; // rsi
  int v14; // ebx
  const char *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  void *v18; // [rsp+50h] [rbp-28h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF

  v8 = a4;
  if ( qword_140052C50 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  v18 = 0;
  v19 = 0;
  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  if ( !a4 )
    return 3221225485LL;
  v12 = a5;
  if ( !a5 )
    return 3221225485LL;
  if ( !Sid )
    return 3221225485LL;
  if ( !a7 )
    return 3221225485LL;
  v13 = a8;
  if ( !a8 || RtlLengthSid(Sid) != v12 )
    return 3221225485LL;
  v14 = (*(&IumpLsaIsoFunctions + 1))(
          "NtlmRootSecret",
          a3,
          a2,
          MIDL_user_allocate,
          SafeAllocaFreeToHeap,
          &v18,
          &v19,
          0,
          0);
  if ( v14 < 0 )
    goto LABEL_18;
  if ( *((_BYTE *)v8 + 8) )
  {
    v14 = IumpUnprotectCredential(v8);
    if ( v14 < 0 )
      goto LABEL_18;
  }
  if ( a7 != 2 )
  {
    v14 = -1073741811;
LABEL_18:
    v16 = 20;
    do
    {
      *v13++ = 0;
      --v16;
    }
    while ( v16 );
    goto LABEL_20;
  }
  v14 = MsvpDeriveSecureCredKey(Sid, (char *)v8 + 38, v13);
  if ( v14 < 0 )
    goto LABEL_18;
LABEL_20:
  if ( v18 )
    SafeAllocaFreeToHeap(v18);
  v17 = 352;
  do
  {
    *(_BYTE *)v8 = 0;
    v8 = (struct _MSV1_0_SECRETS_WRAPPER *)((char *)v8 + 1);
    --v17;
  }
  while ( v17 );
  if ( v14 < 0 )
    NtlmTraceErrorWithStatusViaWpp("NtlmIumGetCredentialKey", 0x53Fu, "NtlmFailure", v14);
  else
    NtlmTraceInfoViaWpp("NtlmIumGetCredentialKey", 0x53Fu, v15);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400350e0  mov     [rsp+arg_8], rbx
0x1400350e5  mov     [rsp+arg_10], rsi
0x1400350ea  push    rdi
0x1400350eb  push    r12
0x1400350ed  push    r15
0x1400350ef  sub     rsp, 60h
0x1400350f3  cmp     cs:qword_140052C50, rcx
0x1400350fa  mov     rdi, r9
0x1400350fd  mov     r15, r8
0x140035100  mov     r12d, edx
0x140035103  jz      short loc_14003511A
0x140035105  mov     ecx, 5; dwMilliseconds
0x14003510a  call    cs:__imp_Sleep
0x140035110  mov     eax, 0C0000022h
0x140035115  jmp     loc_140035297
0x14003511a  mov     [rsp+78h+var_28], 0
0x140035123  mov     [rsp+78h+arg_0], 0
0x14003512e  test    r12d, r12d
0x140035131  jz      loc_140035292
0x140035137  test    r15, r15
0x14003513a  jz      loc_140035292
0x140035140  test    rdi, rdi
0x140035143  jz      loc_140035292
0x140035149  mov     ebx, [rsp+78h+arg_20]
0x140035150  test    ebx, ebx
0x140035152  jz      loc_140035292
0x140035158  cmp     [rsp+78h+Sid], 0
0x140035161  jz      loc_140035292
0x140035167  cmp     [rsp+78h+arg_30], 0
0x14003516f  jz      loc_140035292
0x140035175  mov     rsi, [rsp+78h+arg_38]
0x14003517d  test    rsi, rsi
0x140035180  jz      loc_140035292
0x140035186  mov     rcx, [rsp+78h+Sid]; Sid
0x14003518e  call    cs:__imp_RtlLengthSid
0x140035194  cmp     eax, ebx
0x140035196  jnz     loc_140035292
0x14003519c  mov     [rsp+78h+var_38], 0
0x1400351a5  lea     rax, [rsp+78h+arg_0]
0x1400351ad  mov     [rsp+78h+var_40], 0
0x1400351b6  lea     r9, MIDL_user_allocate
0x1400351bd  mov     [rsp+78h+var_48], rax
0x1400351c2  lea     rcx, aNtlmrootsecret; "NtlmRootSecret"
0x1400351c9  lea     rax, [rsp+78h+var_28]
0x1400351ce  mov     r8d, r12d
0x1400351d1  mov     [rsp+78h+var_50], rax
0x1400351d6  mov     rdx, r15
0x1400351d9  lea     rax, SafeAllocaFreeToHeap
0x1400351e0  mov     [rsp+78h+var_58], rax
0x1400351e5  mov     rax, qword ptr cs:?IumpLsaIsoFunctions@@3U_LsaIsoSupportFunctions@@A+8; _LsaIsoSupportFunctions IumpLsaIsoFunctions
0x1400351ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400351f1  mov     ebx, eax
0x1400351f3  test    eax, eax
0x1400351f5  js      short loc_140035237
0x1400351f7  cmp     byte ptr [rdi+8], 0
0x1400351fb  jz      short loc_14003520B
0x1400351fd  mov     rcx, rdi; struct _MSV1_0_SECRETS_WRAPPER *
0x140035200  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x140035205  mov     ebx, eax
0x140035207  test    eax, eax
0x140035209  js      short loc_140035237
0x14003520b  cmp     [rsp+78h+arg_30], 2
0x140035213  jnz     short loc_140035232
0x140035215  mov     rcx, [rsp+78h+Sid]
0x14003521d  lea     rdx, [rdi+26h]
0x140035221  mov     r8, rsi
0x140035224  call    cs:__imp_MsvpDeriveSecureCredKey
0x14003522a  mov     ebx, eax
0x14003522c  test    eax, eax
0x14003522e  js      short loc_140035237
0x140035230  jmp     short loc_140035248
0x140035232  mov     ebx, 0C000000Dh
0x140035237  mov     eax, 14h
0x14003523c  mov     byte ptr [rsi], 0
0x14003523f  inc     rsi
0x140035242  sub     rax, 1
0x140035246  jnz     short loc_14003523C
0x140035248  mov     rcx, [rsp+78h+var_28]; void *
0x14003524d  test    rcx, rcx
0x140035250  jz      short loc_140035257
0x140035252  call    SafeAllocaFreeToHeap
0x140035257  mov     eax, 160h
0x14003525c  mov     byte ptr [rdi], 0
0x14003525f  inc     rdi
0x140035262  sub     rax, 1
0x140035266  jnz     short loc_14003525C
0x140035268  lea     rcx, aNtlmiumgetcred; "NtlmIumGetCredentialKey"
0x14003526f  mov     edx, 53Fh; unsigned int
0x140035274  test    ebx, ebx
0x140035276  js      short loc_14003527F
0x140035278  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x14003527d  jmp     short loc_14003528E
0x14003527f  mov     r9d, ebx; int
0x140035282  lea     r8, aNtlmfailure; "NtlmFailure"
0x140035289  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x14003528e  mov     eax, ebx
0x140035290  jmp     short loc_140035297
0x140035292  mov     eax, 0C000000Dh
0x140035297  lea     r11, [rsp+78h+var_18]
0x14003529c  mov     rbx, [r11+28h]
0x1400352a0  mov     rsi, [r11+30h]
0x1400352a4  mov     rsp, r11
0x1400352a7  pop     r15
0x1400352a9  pop     r12
0x1400352ab  pop     rdi
0x1400352ac  retn
```
