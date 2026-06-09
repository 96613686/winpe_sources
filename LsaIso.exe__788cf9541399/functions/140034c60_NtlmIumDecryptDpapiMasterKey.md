# NtlmIumDecryptDpapiMasterKey

- ea: `0x140034c60`
- end: `0x140034ef3`
- name: `NtlmIumDecryptDpapiMasterKey`
- size: `659`
- prototype: `__int64 __fastcall(__int64, struct _MSV1_0_SECRETS_WRAPPER *, unsigned int, unsigned int, __int64, int, __int64, unsigned int, __int64, int, PSID Sid, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140006720`
- `0x140033de0`
- `0x140033e20`
- `0x140033e90`
- `0x140033f00`
- `0x140033f60`
- `0x140034c60`
- `0x140036038`
- `0x140036080`
- `0x140036330`
- `0x140038d10`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034cd1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034cd1`
- `NtlmShared!MsvpDecryptDpapiMasterKey` at `0x140034e55`
- `NtlmShared!MsvpDecryptDpapiMasterKey` at `0x140034e55`
- `ntdll!RtlLengthSid` at `0x140034d48`
- `ntdll!RtlLengthSid` at `0x140034d48`

## pseudocode

```c
__int64 __fastcall NtlmIumDecryptDpapiMasterKey(
        __int64 a1,
        struct _MSV1_0_SECRETS_WRAPPER *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        int a10,
        PSID Sid,
        _DWORD *a12,
        _QWORD *a13)
{
  struct _MSV1_0_SECRETS_WRAPPER *v13; // rdi
  const char *v15; // r8
  int v16; // ebx
  unsigned int v17; // r12d
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int128 *v20; // rax
  __int64 v21; // rax
  __int64 v22; // [rsp+28h] [rbp-71h]
  unsigned int v23; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-45h]
  unsigned int v25; // [rsp+58h] [rbp-41h]
  void *v26; // [rsp+60h] [rbp-39h] BYREF
  __int64 v27; // [rsp+68h] [rbp-31h]
  __int64 v28; // [rsp+70h] [rbp-29h]
  __int128 v29; // [rsp+78h] [rbp-21h] BYREF
  __int64 v30; // [rsp+88h] [rbp-11h]

  v13 = a2;
  v25 = a3;
  v28 = a5;
  v27 = a7;
  v24 = a4;
  if ( qword_140052C50 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  v26 = 0;
  v23 = 0;
  if ( !a2 || !a4 || !a5 || !a6 || !a7 || !a9 || !a8 || !Sid || !a12 || !a13 || RtlLengthSid(Sid) != a10 )
    return 3221225485LL;
  if ( *((_BYTE *)v13 + 8) )
  {
    v16 = IumpUnprotectCredential(v13);
    if ( v16 >= 0 )
    {
      v16 = (*(&IumpLsaIsoFunctions + 1))(
              "NtlmRootSecret",
              a9,
              a8,
              MIDL_user_allocate,
              SafeAllocaFreeToHeap,
              &v26,
              &v23,
              0,
              0);
      if ( v16 >= 0 )
      {
        v17 = v24;
        v18 = 0;
        do
        {
          v30 = 0;
          v29 = 0;
          v19 = 24;
          v20 = &v29;
          do
          {
            *(_BYTE *)v20 = 0;
            v20 = (__int128 *)((char *)v20 + 1);
            --v19;
          }
          while ( v19 );
          v16 = ((__int64 (__fastcall *)(_QWORD, struct _MSV1_0_SECRETS_WRAPPER *, _QWORD, void *, PSID, __int128 *))funcs_140034E22[v18])(
                  v25,
                  v13,
                  v23,
                  v26,
                  Sid,
                  &v29);
          if ( v16 >= 0 )
          {
            LODWORD(v22) = a6;
            v16 = MsvpDecryptDpapiMasterKey((char *)&v29 + 4, (unsigned int)v29, v28, v17, v27, v22, a13, a12);
            if ( v16 >= 0 )
              goto LABEL_25;
          }
          v18 = (unsigned int)(v18 + 1);
        }
        while ( (unsigned int)v18 < 5 );
      }
    }
  }
  else
  {
    v16 = -1073741811;
  }
  *a12 = 0;
  *a13 = 0;
LABEL_25:
  if ( v26 )
    SafeAllocaFreeToHeap(v26);
  v21 = 352;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (struct _MSV1_0_SECRETS_WRAPPER *)((char *)v13 + 1);
    --v21;
  }
  while ( v21 );
  if ( v16 < 0 )
    NtlmTraceErrorWithStatusViaWpp("NtlmIumDecryptDpapiMasterKey", 0x498u, "NtlmFailure", v16);
  else
    NtlmTraceInfoViaWpp("NtlmIumDecryptDpapiMasterKey", 0x498u, v15);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140034c60  mov     [rsp-8+arg_0], rbx
0x140034c65  push    rbp
0x140034c66  push    rsi
0x140034c67  push    rdi
0x140034c68  push    r12
0x140034c6a  push    r13
0x140034c6c  push    r14
0x140034c6e  push    r15
0x140034c70  lea     rbp, [rsp-7]
0x140034c75  sub     rsp, 0A0h
0x140034c7c  mov     rax, cs:__security_cookie
0x140034c83  xor     rax, rsp
0x140034c86  mov     [rbp+37h+var_40], rax
0x140034c8a  cmp     cs:qword_140052C50, rcx
0x140034c91  mov     rdi, rdx
0x140034c94  mov     rdx, [rbp+37h+arg_20]
0x140034c98  mov     eax, r9d
0x140034c9b  mov     r12, [rbp+37h+arg_40]
0x140034ca2  mov     r13, [rbp+37h+Sid]
0x140034ca9  mov     r14, [rbp+37h+arg_58]
0x140034cb0  mov     r15, [rbp+37h+arg_60]
0x140034cb7  mov     [rbp+37h+var_78], r8d
0x140034cbb  mov     r8, [rbp+37h+arg_30]
0x140034cbf  mov     [rbp+37h+var_60], rdx
0x140034cc3  mov     [rbp+37h+var_68], r8
0x140034cc7  mov     [rbp+37h+var_7C], eax
0x140034cca  jz      short loc_140034CE1
0x140034ccc  mov     ecx, 5; dwMilliseconds
0x140034cd1  call    cs:__imp_Sleep
0x140034cd7  mov     eax, 0C0000022h
0x140034cdc  jmp     loc_140034ECC
0x140034ce1  xor     ebx, ebx
0x140034ce3  mov     [rbp+37h+var_70], rbx
0x140034ce7  mov     [rbp+37h+var_80], ebx
0x140034cea  test    rdi, rdi
0x140034ced  jz      loc_140034EC7
0x140034cf3  test    eax, eax
0x140034cf5  jz      loc_140034EC7
0x140034cfb  test    rdx, rdx
0x140034cfe  jz      loc_140034EC7
0x140034d04  cmp     [rbp+37h+arg_28], ebx
0x140034d07  jz      loc_140034EC7
0x140034d0d  test    r8, r8
0x140034d10  jz      loc_140034EC7
0x140034d16  test    r12, r12
0x140034d19  jz      loc_140034EC7
0x140034d1f  mov     esi, [rbp+37h+arg_38]
0x140034d22  test    esi, esi
0x140034d24  jz      loc_140034EC7
0x140034d2a  test    r13, r13
0x140034d2d  jz      loc_140034EC7
0x140034d33  test    r14, r14
0x140034d36  jz      loc_140034EC7
0x140034d3c  test    r15, r15
0x140034d3f  jz      loc_140034EC7
0x140034d45  mov     rcx, r13; Sid
0x140034d48  call    cs:__imp_RtlLengthSid
0x140034d4e  cmp     eax, [rbp+37h+arg_48]
0x140034d54  jnz     loc_140034EC7
0x140034d5a  cmp     [rdi+8], bl
0x140034d5d  jnz     short loc_140034D69
0x140034d5f  mov     ebx, 0C000000Dh
0x140034d64  jmp     loc_140034E70
0x140034d69  mov     rcx, rdi; struct _MSV1_0_SECRETS_WRAPPER *
0x140034d6c  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x140034d71  mov     ebx, eax
0x140034d73  test    eax, eax
0x140034d75  js      loc_140034E70
0x140034d7b  mov     [rsp+0D0h+var_90], 0
0x140034d84  lea     rax, [rbp+37h+var_80]
0x140034d88  mov     [rsp+0D0h+var_98], 0
0x140034d91  lea     r9, MIDL_user_allocate
0x140034d98  mov     [rsp+0D0h+var_A0], rax
0x140034d9d  lea     rcx, aNtlmrootsecret; "NtlmRootSecret"
0x140034da4  lea     rax, [rbp+37h+var_70]
0x140034da8  mov     r8d, esi
0x140034dab  mov     [rsp+0D0h+var_A8], rax
0x140034db0  mov     rdx, r12
0x140034db3  lea     rax, SafeAllocaFreeToHeap
0x140034dba  mov     [rsp+0D0h+var_B0], rax
0x140034dbf  mov     rax, qword ptr cs:?IumpLsaIsoFunctions@@3U_LsaIsoSupportFunctions@@A+8; _LsaIsoSupportFunctions IumpLsaIsoFunctions
0x140034dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034dcb  mov     ebx, eax
0x140034dcd  test    eax, eax
0x140034dcf  js      loc_140034E70
0x140034dd5  mov     r12d, [rbp+37h+var_7C]
0x140034dd9  xor     esi, esi
0x140034ddb  xor     eax, eax
0x140034ddd  xorps   xmm0, xmm0
0x140034de0  mov     [rbp+37h+var_48], rax
0x140034de4  movups  [rbp+37h+var_58], xmm0
0x140034de8  lea     ecx, [rax+18h]
0x140034deb  lea     rax, [rbp+37h+var_58]
0x140034def  mov     byte ptr [rax], 0
0x140034df2  inc     rax
0x140034df5  sub     rcx, 1
0x140034df9  jnz     short loc_140034DEF
0x140034dfb  mov     r9, [rbp+37h+var_70]
0x140034dff  lea     rcx, [rbp+37h+var_58]
0x140034e03  mov     r8d, [rbp+37h+var_80]
0x140034e07  lea     r10, funcs_140034E22
0x140034e0e  mov     rax, ds:(funcs_140034E22 - 14003CAE0h)[r10+rsi*8]
0x140034e12  mov     rdx, rdi
0x140034e15  mov     [rsp+0D0h+var_A8], rcx
0x140034e1a  mov     ecx, [rbp+37h+var_78]
0x140034e1d  mov     [rsp+0D0h+var_B0], r13
0x140034e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034e27  mov     ebx, eax
0x140034e29  test    eax, eax
0x140034e2b  js      short loc_140034E61
0x140034e2d  mov     eax, [rbp+37h+arg_28]
0x140034e30  lea     rcx, [rbp+37h+var_58+4]
0x140034e34  mov     r8, [rbp+37h+var_60]
0x140034e38  mov     r9d, r12d
0x140034e3b  mov     edx, dword ptr [rbp+37h+var_58]
0x140034e3e  mov     [rsp+0D0h+var_98], r14
0x140034e43  mov     [rsp+0D0h+var_A0], r15
0x140034e48  mov     dword ptr [rsp+0D0h+var_A8], eax
0x140034e4c  mov     rax, [rbp+37h+var_68]
0x140034e50  mov     [rsp+0D0h+var_B0], rax
0x140034e55  call    cs:__imp_MsvpDecryptDpapiMasterKey
0x140034e5b  mov     ebx, eax
0x140034e5d  test    eax, eax
0x140034e5f  jns     short loc_140034E7E
0x140034e61  inc     esi
0x140034e63  cmp     esi, 5
0x140034e66  jb      loc_140034DDB
0x140034e6c  test    ebx, ebx
0x140034e6e  jns     short loc_140034E7E
0x140034e70  mov     dword ptr [r14], 0
0x140034e77  mov     qword ptr [r15], 0
0x140034e7e  mov     rcx, [rbp+37h+var_70]; void *
0x140034e82  test    rcx, rcx
0x140034e85  jz      short loc_140034E8C
0x140034e87  call    SafeAllocaFreeToHeap
0x140034e8c  mov     eax, 160h
0x140034e91  mov     byte ptr [rdi], 0
0x140034e94  inc     rdi
0x140034e97  sub     rax, 1
0x140034e9b  jnz     short loc_140034E91
0x140034e9d  lea     rcx, aNtlmiumdecrypt; "NtlmIumDecryptDpapiMasterKey"
0x140034ea4  mov     edx, 498h; unsigned int
0x140034ea9  test    ebx, ebx
0x140034eab  js      short loc_140034EB4
0x140034ead  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x140034eb2  jmp     short loc_140034EC3
0x140034eb4  mov     r9d, ebx; int
0x140034eb7  lea     r8, aNtlmfailure; "NtlmFailure"
0x140034ebe  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140034ec3  mov     eax, ebx
0x140034ec5  jmp     short loc_140034ECC
0x140034ec7  mov     eax, 0C000000Dh
0x140034ecc  mov     rcx, [rbp+37h+var_40]
0x140034ed0  xor     rcx, rsp; StackCookie
0x140034ed3  call    __security_check_cookie
0x140034ed8  mov     rbx, [rsp+0D0h+arg_0]
0x140034ee0  add     rsp, 0A0h
0x140034ee7  pop     r15
0x140034ee9  pop     r14
0x140034eeb  pop     r13
0x140034eed  pop     r12
0x140034eef  pop     rdi
0x140034ef0  pop     rsi
0x140034ef1  pop     rbp
0x140034ef2  retn
```
