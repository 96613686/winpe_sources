# NtlmIumPasswordValidateInteractive

- ea: `0x140035ad0`
- end: `0x140035c6e`
- name: `NtlmIumPasswordValidateInteractive`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140035ad0`
- `0x140036038`
- `0x140036080`
- `0x140036330`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035b2a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140035b2a`
- `NtlmShared!MsvpPasswordValidate` at `0x140035bcb`
- `NtlmShared!MsvpPasswordValidate` at `0x140035bcb`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x140035ba6`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x140035ba6`

## pseudocode

```c
__int64 __fastcall NtlmIumPasswordValidateInteractive(
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
          *a8 = MsvpPasswordValidate(v15, 1, a3, v19, a5, a6, a7);
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
        NtlmTraceInfoViaWpp("NtlmIumPasswordValidateInteractive", 0x195u, a3);
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
        NtlmTraceErrorWithStatusViaWpp("NtlmIumPasswordValidateInteractive", 0x195u, "NtlmFailure", v14);
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
0x140035ad0  mov     [rsp+arg_0], rbx
0x140035ad5  push    rbp
0x140035ad6  push    rsi
0x140035ad7  push    rdi
0x140035ad8  push    r12
0x140035ada  push    r13
0x140035adc  push    r14
0x140035ade  push    r15
0x140035ae0  sub     rsp, 70h
0x140035ae4  mov     rax, cs:__security_cookie
0x140035aeb  xor     rax, rsp
0x140035aee  mov     [rsp+0A8h+var_40], rax
0x140035af3  cmp     cs:qword_140052C50, rcx
0x140035afa  mov     rdi, r9
0x140035afd  mov     r15, [rsp+0A8h+arg_20]
0x140035b05  mov     r12, r8
0x140035b08  mov     rsi, [rsp+0A8h+arg_28]
0x140035b10  mov     r13b, dl
0x140035b13  mov     r14, [rsp+0A8h+arg_30]
0x140035b1b  mov     rbp, [rsp+0A8h+arg_38]
0x140035b23  jz      short loc_140035B3A
0x140035b25  mov     ecx, 5; dwMilliseconds
0x140035b2a  call    cs:__imp_Sleep
0x140035b30  mov     eax, 0C0000022h
0x140035b35  jmp     loc_140035C49
0x140035b3a  xorps   xmm0, xmm0
0x140035b3d  xor     eax, eax
0x140035b3f  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140035b44  mov     dword ptr [rsp+0A8h+var_58+0Fh], eax
0x140035b48  movups  [rsp+0A8h+var_68], xmm0
0x140035b4d  test    r12, r12
0x140035b50  jz      loc_140035C44
0x140035b56  test    rdi, rdi
0x140035b59  jz      loc_140035C44
0x140035b5f  test    r15, r15
0x140035b62  jz      loc_140035C44
0x140035b68  test    rsi, rsi
0x140035b6b  jz      loc_140035C44
0x140035b71  test    r14, r14
0x140035b74  jz      loc_140035C44
0x140035b7a  test    rbp, rbp
0x140035b7d  jz      loc_140035C44
0x140035b83  cmp     [r9+8], al
0x140035b87  jnz     short loc_140035B90
0x140035b89  mov     ebx, 0C000000Dh
0x140035b8e  jmp     short loc_140035BD4
0x140035b90  mov     rcx, rdi; struct _MSV1_0_SECRETS_WRAPPER *
0x140035b93  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x140035b98  mov     ebx, eax
0x140035b9a  test    eax, eax
0x140035b9c  js      short loc_140035BD4
0x140035b9e  lea     rdx, [rsp+0A8h+var_68]
0x140035ba3  mov     rcx, rdi
0x140035ba6  call    cs:__imp_MsvpCredentialToCachePasswords
0x140035bac  mov     [rsp+0A8h+var_78], r14
0x140035bb1  lea     r9, [rsp+0A8h+var_68]
0x140035bb6  mov     [rsp+0A8h+var_80], rsi
0x140035bbb  mov     r8, r12
0x140035bbe  mov     edx, 1
0x140035bc3  mov     [rsp+0A8h+var_88], r15
0x140035bc8  mov     cl, r13b
0x140035bcb  call    cs:__imp_MsvpPasswordValidate
0x140035bd1  mov     [rbp+0], al
0x140035bd4  mov     eax, 160h
0x140035bd9  mov     byte ptr [rdi], 0
0x140035bdc  inc     rdi
0x140035bdf  sub     rax, 1
0x140035be3  jnz     short loc_140035BD9
0x140035be5  test    ebx, ebx
0x140035be7  jns     short loc_140035C2F
0x140035be9  mov     [r15], eax
0x140035bec  mov     eax, 10h
0x140035bf1  mov     byte ptr [rsi], 0
0x140035bf4  inc     rsi
0x140035bf7  sub     rax, 1
0x140035bfb  jnz     short loc_140035BF1
0x140035bfd  mov     eax, 8
0x140035c02  mov     byte ptr [r14], 0
0x140035c06  inc     r14
0x140035c09  sub     rax, 1
0x140035c0d  jnz     short loc_140035C02
0x140035c0f  mov     r9d, ebx; int
0x140035c12  mov     [rbp+0], al
0x140035c15  lea     r8, aNtlmfailure; "NtlmFailure"
0x140035c1c  mov     edx, 195h; unsigned int
0x140035c21  lea     rcx, aNtlmiumpasswor_0; "NtlmIumPasswordValidateInteractive"
0x140035c28  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140035c2d  jmp     short loc_140035C40
0x140035c2f  mov     edx, 195h; unsigned int
0x140035c34  lea     rcx, aNtlmiumpasswor_0; "NtlmIumPasswordValidateInteractive"
0x140035c3b  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x140035c40  mov     eax, ebx
0x140035c42  jmp     short loc_140035C49
0x140035c44  mov     eax, 0C000000Dh
0x140035c49  mov     rcx, [rsp+0A8h+var_40]
0x140035c4e  xor     rcx, rsp; StackCookie
0x140035c51  call    __security_check_cookie
0x140035c56  mov     rbx, [rsp+0A8h+arg_0]
0x140035c5e  add     rsp, 70h
0x140035c62  pop     r15
0x140035c64  pop     r14
0x140035c66  pop     r13
0x140035c68  pop     r12
0x140035c6a  pop     rdi
0x140035c6b  pop     rsi
0x140035c6c  pop     rbp
0x140035c6d  retn
```
