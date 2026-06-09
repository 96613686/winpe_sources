# NtlmIumPasswordValidateNetwork

- ea: `0x140035c80`
- end: `0x140035e1e`
- name: `NtlmIumPasswordValidateNetwork`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140035c80`
- `0x140036038`
- `0x140036080`
- `0x140036330`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035cda`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035cda`
- `NtlmShared!MsvpPasswordValidate` at `0x140035d7b`
- `NtlmShared!MsvpPasswordValidate` at `0x140035d7b`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x140035d56`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x140035d56`

## pseudocode

```c
__int64 __fastcall NtlmIumPasswordValidateNetwork(
        __int64 a1,
        char a2,
        const char *a3,
        _BYTE *a4,
        _DWORD *a5,
        _BYTE *a6,
        _BYTE *a7,
        _BYTE *a8)
{
  _BYTE *v8; // rdi
  _BYTE *v10; // rsi
  _BYTE *v12; // r14
  int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _BYTE v19[35]; // [rsp+40h] [rbp-68h] BYREF

  v8 = a4;
  v10 = a6;
  v12 = a7;
  if ( qword_140052C50 == a1 )
  {
    memset(v19, 0, sizeof(v19));
    if ( a3 && a4 && a5 && a6 && a7 && a8 )
    {
      if ( a4[8] )
      {
        v14 = IumpUnprotectCredential((struct _MSV1_0_SECRETS_WRAPPER *)a4);
        if ( v14 >= 0 )
        {
          MsvpCredentialToCachePasswords(v8, v19);
          LOBYTE(v15) = a2;
          *a8 = MsvpPasswordValidate(v15, 2, a3, v19, a5, a6, a7);
        }
      }
      else
      {
        v14 = -1073741811;
      }
      v16 = 352;
      do
      {
        *v8++ = 0;
        --v16;
      }
      while ( v16 );
      if ( v14 >= 0 )
      {
        NtlmTraceInfoViaWpp("NtlmIumPasswordValidateNetwork", 0x1D6u, a3);
      }
      else
      {
        *a5 = 0;
        v17 = 16;
        do
        {
          *v10++ = 0;
          --v17;
        }
        while ( v17 );
        v18 = 8;
        do
        {
          *v12++ = 0;
          --v18;
        }
        while ( v18 );
        *a8 = 0;
        NtlmTraceErrorWithStatusViaWpp("NtlmIumPasswordValidateNetwork", 0x1D6u, "NtlmFailure", v14);
      }
      return (unsigned int)v14;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140035c80  mov     [rsp+arg_0], rbx
0x140035c85  push    rbp
0x140035c86  push    rsi
0x140035c87  push    rdi
0x140035c88  push    r12
0x140035c8a  push    r13
0x140035c8c  push    r14
0x140035c8e  push    r15
0x140035c90  sub     rsp, 70h
0x140035c94  mov     rax, cs:__security_cookie
0x140035c9b  xor     rax, rsp
0x140035c9e  mov     [rsp+0A8h+var_40], rax
0x140035ca3  cmp     cs:qword_140052C50, rcx
0x140035caa  mov     rdi, r9
0x140035cad  mov     r15, [rsp+0A8h+arg_20]
0x140035cb5  mov     r12, r8
0x140035cb8  mov     rsi, [rsp+0A8h+arg_28]
0x140035cc0  mov     r13b, dl
0x140035cc3  mov     r14, [rsp+0A8h+arg_30]
0x140035ccb  mov     rbp, [rsp+0A8h+arg_38]
0x140035cd3  jz      short loc_140035CEA
0x140035cd5  mov     ecx, 5; dwMilliseconds
0x140035cda  call    cs:__imp_Sleep
0x140035ce0  mov     eax, 0C0000022h
0x140035ce5  jmp     loc_140035DF9
0x140035cea  xorps   xmm0, xmm0
0x140035ced  xor     eax, eax
0x140035cef  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140035cf4  mov     dword ptr [rsp+0A8h+var_58+0Fh], eax
0x140035cf8  movups  [rsp+0A8h+var_68], xmm0
0x140035cfd  test    r12, r12
0x140035d00  jz      loc_140035DF4
0x140035d06  test    rdi, rdi
0x140035d09  jz      loc_140035DF4
0x140035d0f  test    r15, r15
0x140035d12  jz      loc_140035DF4
0x140035d18  test    rsi, rsi
0x140035d1b  jz      loc_140035DF4
0x140035d21  test    r14, r14
0x140035d24  jz      loc_140035DF4
0x140035d2a  test    rbp, rbp
0x140035d2d  jz      loc_140035DF4
0x140035d33  cmp     [r9+8], al
0x140035d37  jnz     short loc_140035D40
0x140035d39  mov     ebx, 0C000000Dh
0x140035d3e  jmp     short loc_140035D84
0x140035d40  mov     rcx, rdi; struct _MSV1_0_SECRETS_WRAPPER *
0x140035d43  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x140035d48  mov     ebx, eax
0x140035d4a  test    eax, eax
0x140035d4c  js      short loc_140035D84
0x140035d4e  lea     rdx, [rsp+0A8h+var_68]
0x140035d53  mov     rcx, rdi
0x140035d56  call    cs:__imp_MsvpCredentialToCachePasswords
0x140035d5c  mov     [rsp+0A8h+var_78], r14
0x140035d61  lea     r9, [rsp+0A8h+var_68]
0x140035d66  mov     [rsp+0A8h+var_80], rsi
0x140035d6b  mov     r8, r12
0x140035d6e  mov     edx, 2
0x140035d73  mov     [rsp+0A8h+var_88], r15
0x140035d78  mov     cl, r13b
0x140035d7b  call    cs:__imp_MsvpPasswordValidate
0x140035d81  mov     [rbp+0], al
0x140035d84  mov     eax, 160h
0x140035d89  mov     byte ptr [rdi], 0
0x140035d8c  inc     rdi
0x140035d8f  sub     rax, 1
0x140035d93  jnz     short loc_140035D89
0x140035d95  test    ebx, ebx
0x140035d97  jns     short loc_140035DDF
0x140035d99  mov     [r15], eax
0x140035d9c  mov     eax, 10h
0x140035da1  mov     byte ptr [rsi], 0
0x140035da4  inc     rsi
0x140035da7  sub     rax, 1
0x140035dab  jnz     short loc_140035DA1
0x140035dad  mov     eax, 8
0x140035db2  mov     byte ptr [r14], 0
0x140035db6  inc     r14
0x140035db9  sub     rax, 1
0x140035dbd  jnz     short loc_140035DB2
0x140035dbf  mov     r9d, ebx; int
0x140035dc2  mov     [rbp+0], al
0x140035dc5  lea     r8, aNtlmfailure; "NtlmFailure"
0x140035dcc  mov     edx, 1D6h; unsigned int
0x140035dd1  lea     rcx, aNtlmiumpasswor; "NtlmIumPasswordValidateNetwork"
0x140035dd8  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140035ddd  jmp     short loc_140035DF0
0x140035ddf  mov     edx, 1D6h; unsigned int
0x140035de4  lea     rcx, aNtlmiumpasswor; "NtlmIumPasswordValidateNetwork"
0x140035deb  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x140035df0  mov     eax, ebx
0x140035df2  jmp     short loc_140035DF9
0x140035df4  mov     eax, 0C000000Dh
0x140035df9  mov     rcx, [rsp+0A8h+var_40]
0x140035dfe  xor     rcx, rsp; StackCookie
0x140035e01  call    __security_check_cookie
0x140035e06  mov     rbx, [rsp+0A8h+arg_0]
0x140035e0e  add     rsp, 70h
0x140035e12  pop     r15
0x140035e14  pop     r14
0x140035e16  pop     r13
0x140035e18  pop     r12
0x140035e1a  pop     rdi
0x140035e1b  pop     rsi
0x140035e1c  pop     rbp
0x140035e1d  retn
```
