# EdppProcessEnumRoutine

- ea: `0x14002cd1c`
- end: `0x14002d073`
- name: `EdppProcessEnumRoutine`
- size: `855`
- prototype: `__int64 __fastcall(struct _KPROCESS *, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x14002c9c4`

## callees

- `0x140003c8c`
- `0x140003e2c`
- `0x140003ec0`
- `0x140006a20`
- `0x140006f40`
- `0x14001f900`
- `0x140027560`
- `0x14002c1c0`
- `0x14002c2b8`
- `0x14002c450`
- `0x14002cd1c`
- `0x14002d18c`
- `0x1400328b0`
- `0x140032a50`
- `0x140033dc0`
- `0x140035250`
- `0x1400354d0`
- `0x140035530`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002ce11`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002ce11`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002ce89`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002ce89`
- `ntoskrnl!ZwSetInformationThread` at `0x14002ceb7`
- `ntoskrnl!ZwSetInformationThread` at `0x14002ceb7`

## pseudocode

```c
__int64 __fastcall EdppProcessEnumRoutine(struct _KPROCESS *a1, void *a2, __int64 a3, __int64 a4)
{
  void *v4; // rdi
  char v8; // r15
  char *v9; // r12
  int Tokens; // eax
  char *v11; // r14
  int IsTokenSandBoxed; // ebx
  void *v13; // r13
  _OWORD *v14; // rax
  __int64 v15; // r12
  __int64 v16; // rax
  __int64 v17; // r8
  __int128 v18; // xmm0
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  char v23; // [rsp+28h] [rbp-B1h]
  unsigned __int8 v24; // [rsp+40h] [rbp-99h] BYREF
  bool v25; // [rsp+41h] [rbp-98h] BYREF
  bool v26; // [rsp+42h] [rbp-97h] BYREF
  char *v27; // [rsp+48h] [rbp-91h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-89h] BYREF
  int v29; // [rsp+54h] [rbp-85h] BYREF
  __int64 v30; // [rsp+58h] [rbp-81h] BYREF
  __int64 ThreadInformation; // [rsp+60h] [rbp-79h] BYREF
  void *v32; // [rsp+68h] [rbp-71h] BYREF
  __int64 v33; // [rsp+70h] [rbp-69h]
  const UNICODE_STRING *v34; // [rsp+78h] [rbp-61h] BYREF
  _QWORD v35[12]; // [rsp+80h] [rbp-59h] BYREF
  __int128 v36; // [rsp+E0h] [rbp+7h] BYREF

  v4 = 0;
  ThreadInformation = a3;
  v33 = a4;
  v29 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v32 = 0;
  memset(v35, 0, sizeof(v35));
  v28 = 0;
  v30 = 0;
  v34 = 0;
  v36 = 0;
  if ( (unsigned __int64)a2 <= 4 )
    return 0;
  v8 = 0;
  v9 = 0;
  Tokens = AiGetTokens(a2, (void **)&v27, &v32);
  v11 = v27;
  IsTokenSandBoxed = Tokens;
  v13 = v32;
  if ( Tokens >= 0 )
  {
    v14 = (_OWORD *)AiAlloc(0x10u);
    v35[2] = v14;
    if ( v14 )
    {
      *v14 = 0;
      IsTokenSandBoxed = AiCapturePackageMoniker(a1, &v24, &v26, v35[2]);
      if ( IsTokenSandBoxed >= 0 )
      {
        ExAcquirePushLockSharedEx(&EdppRuntimeConfig, 0);
        v15 = v24;
        v27 = byte_140019508;
        if ( EdpPluginConfigActive((__int64)byte_140019508) )
        {
          IsTokenSandBoxed = AiIsTokenSandBoxed(v11, &v25);
          if ( IsTokenSandBoxed >= 0 && !v25 )
          {
            v16 = AiAlloc(0x18u);
            v4 = (void *)v16;
            if ( v16 )
            {
              *(_QWORD *)(v16 + 12) = 0;
              *(_DWORD *)(v16 + 20) = 0;
              *(_QWORD *)v16 = a1;
              *(_DWORD *)(v16 + 8) = -1073741823;
              v35[1] = a1;
              v35[6] = v11;
              v35[5] = v13;
              v35[7] = v16;
              IsTokenSandBoxed = EdppImpersonateProcess((__int64)v35);
              if ( IsTokenSandBoxed >= 0 )
              {
                v8 = 1;
                IsTokenSandBoxed = EdppCaptureProcess(a1, (__int64)v35);
                if ( IsTokenSandBoxed >= 0 )
                {
                  v18 = (_BYTE)v15 ? AiCategoryAppx : AiCategoryExe;
                  v36 = v18;
                  if ( (_BYTE)v15 )
                  {
                    LOBYTE(v17) = v26;
                    v23 = 0;
                    v19 = AiSetAttributesAppx(v35[4], v35[2], v17, v11, v13);
                  }
                  else
                  {
                    v19 = AiSetAttributesExe(ThreadInformation, v35[4], (_DWORD)v11, (_DWORD)v13, 0);
                  }
                  IsTokenSandBoxed = v19;
                  if ( v19 >= 0 )
                  {
                    v35[9] = &v36;
                    v20 = v15;
                    v9 = v27;
                    v20 *= 2;
                    LODWORD(v35[10]) = *(_DWORD *)(v33 + 8 * v20);
                    v35[11] = *(_QWORD *)(v33 + 8 * v20 + 8);
                    v35[0] = v27;
                    IsTokenSandBoxed = EdpPluginEvaluate(v35, &v29, &v30, &v34, &v28);
                    if ( IsTokenSandBoxed >= 0 )
                    {
                      v22 = v30;
                      if ( dword_14001950C == 1 )
                        v22 = v30 | 0x80;
                      IsTokenSandBoxed = EdpPluginAction((__int64)v35, v21, v22, (__int64)v34, v28, v23, 1);
                    }
                    v35[0] = 0;
                    goto LABEL_10;
                  }
                }
              }
            }
            else
            {
              IsTokenSandBoxed = -1073741801;
            }
          }
        }
        else
        {
          IsTokenSandBoxed = EdppClearToken((__int64)v11, (__int64)a1);
        }
        v9 = v27;
      }
    }
    else
    {
      IsTokenSandBoxed = -1073741801;
    }
  }
LABEL_10:
  AiCleanTokens(v11, v13);
  EdppCleanupArgs(v35);
  AiFree(v4);
  if ( v9 )
    ExReleasePushLockSharedEx(&EdppRuntimeConfig, 0);
  if ( v8 )
  {
    ThreadInformation = 0;
    ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return (unsigned int)IsTokenSandBoxed;
}

```

## disassembly

```asm
0x14002cd1c  mov     [rsp-8+arg_10], rbx
0x14002cd21  push    rbp
0x14002cd22  push    rsi
0x14002cd23  push    rdi
0x14002cd24  push    r12
0x14002cd26  push    r13
0x14002cd28  push    r14
0x14002cd2a  push    r15
0x14002cd2c  lea     rbp, [rsp-27h]
0x14002cd31  sub     rsp, 100h
0x14002cd38  mov     rax, cs:__security_cookie
0x14002cd3f  xor     rax, rsp
0x14002cd42  mov     [rbp+57h+var_40], rax
0x14002cd46  xor     edi, edi
0x14002cd48  mov     [rbp+57h+ThreadInformation], r8
0x14002cd4c  mov     rbx, rdx
0x14002cd4f  mov     [rbp+57h+var_C0], r9
0x14002cd53  mov     rsi, rcx
0x14002cd56  mov     [rsp+130h+var_DC], edi
0x14002cd5a  xor     edx, edx; Val
0x14002cd5c  mov     [rsp+130h+var_F0], dil
0x14002cd61  lea     r8d, [rdi+60h]; Size
0x14002cd65  mov     [rsp+130h+var_EE], dil
0x14002cd6a  lea     rcx, [rbp+57h+var_B0]; void *
0x14002cd6e  mov     [rsp+130h+var_EF], dil
0x14002cd73  mov     [rsp+130h+var_E8], rdi
0x14002cd78  mov     [rbp+57h+var_C8], rdi
0x14002cd7c  call    memset
0x14002cd81  mov     [rsp+130h+var_E0], edi
0x14002cd85  xorps   xmm0, xmm0
0x14002cd88  mov     [rsp+130h+var_D8], rdi
0x14002cd8d  mov     [rbp+57h+var_B8], rdi
0x14002cd91  movups  [rbp+57h+var_50], xmm0
0x14002cd95  cmp     rbx, 4
0x14002cd99  ja      short loc_14002CDA2
0x14002cd9b  xor     eax, eax
0x14002cd9d  jmp     loc_14002CEC5
0x14002cda2  lea     r8, [rbp+57h+var_C8]
0x14002cda6  mov     rcx, rbx
0x14002cda9  lea     rdx, [rsp+130h+var_E8]
0x14002cdae  mov     r15b, dil
0x14002cdb1  mov     r12, rdi
0x14002cdb4  call    AiGetTokens
0x14002cdb9  mov     r14, [rsp+130h+var_E8]
0x14002cdbe  mov     ebx, eax
0x14002cdc0  mov     r13, [rbp+57h+var_C8]
0x14002cdc4  test    eax, eax
0x14002cdc6  js      loc_14002CE5F
0x14002cdcc  mov     ecx, 10h
0x14002cdd1  call    AiAlloc
0x14002cdd6  mov     [rbp+57h+var_A0], rax
0x14002cdda  test    rax, rax
0x14002cddd  jnz     short loc_14002CDE6
0x14002cddf  mov     ebx, 0C0000017h
0x14002cde4  jmp     short loc_14002CE5F
0x14002cde6  xorps   xmm0, xmm0
0x14002cde9  lea     r8, [rsp+130h+var_EE]
0x14002cdee  movups  xmmword ptr [rax], xmm0
0x14002cdf1  mov     r9, [rbp+57h+var_A0]
0x14002cdf5  lea     rdx, [rsp+130h+var_F0]
0x14002cdfa  mov     rcx, rsi
0x14002cdfd  call    AiCapturePackageMoniker
0x14002ce02  mov     ebx, eax
0x14002ce04  test    eax, eax
0x14002ce06  js      short loc_14002CE5F
0x14002ce08  xor     edx, edx
0x14002ce0a  lea     rcx, EdppRuntimeConfig
0x14002ce11  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002ce18  nop     dword ptr [rax+rax+00h]
0x14002ce1d  mov     rcx, [rbp+57h+var_C0]
0x14002ce21  lea     rax, byte_140019508
0x14002ce28  movzx   r12d, [rsp+130h+var_F0]
0x14002ce2e  mov     dl, r12b
0x14002ce31  mov     [rsp+130h+var_E8], rax
0x14002ce36  mov     r9d, [rcx+10h]
0x14002ce3a  mov     r8d, [rcx]
0x14002ce3d  mov     rcx, rax
0x14002ce40  call    EdpPluginConfigActive
0x14002ce45  mov     rcx, r14
0x14002ce48  test    al, al
0x14002ce4a  jnz     loc_14002CEED
0x14002ce50  mov     rdx, rsi
0x14002ce53  call    EdppClearToken
0x14002ce58  mov     ebx, eax
0x14002ce5a  mov     r12, [rsp+130h+var_E8]
0x14002ce5f  mov     rdx, r13
0x14002ce62  mov     rcx, r14
0x14002ce65  call    AiCleanTokens
0x14002ce6a  lea     rcx, [rbp+57h+var_B0]; void *
0x14002ce6e  call    EdppCleanupArgs
0x14002ce73  mov     rcx, rdi
0x14002ce76  call    AiFree
0x14002ce7b  test    r12, r12
0x14002ce7e  jz      short loc_14002CE95
0x14002ce80  xor     edx, edx
0x14002ce82  lea     rcx, EdppRuntimeConfig
0x14002ce89  call    cs:__imp_ExReleasePushLockSharedEx
0x14002ce90  nop     dword ptr [rax+rax+00h]
0x14002ce95  test    r15b, r15b
0x14002ce98  jz      short loc_14002CEC3
0x14002ce9a  mov     r9d, 8; ThreadInformationLength
0x14002cea0  mov     [rbp+57h+ThreadInformation], 0
0x14002cea8  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x14002ceac  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002ceb3  lea     edx, [r9-3]; ThreadInformationClass
0x14002ceb7  call    cs:__imp_ZwSetInformationThread
0x14002cebe  nop     dword ptr [rax+rax+00h]
0x14002cec3  mov     eax, ebx
0x14002cec5  mov     rcx, [rbp+57h+var_40]
0x14002cec9  xor     rcx, rsp; StackCookie
0x14002cecc  call    __security_check_cookie
0x14002ced1  mov     rbx, [rsp+130h+arg_10]
0x14002ced9  add     rsp, 100h
0x14002cee0  pop     r15
0x14002cee2  pop     r14
0x14002cee4  pop     r13
0x14002cee6  pop     r12
0x14002cee8  pop     rdi
0x14002cee9  pop     rsi
0x14002ceea  pop     rbp
0x14002ceeb  retn
0x14002ceed  lea     rdx, [rsp+130h+var_EF]
0x14002cef2  call    AiIsTokenSandBoxed
0x14002cef7  mov     ebx, eax
0x14002cef9  test    eax, eax
0x14002cefb  js      loc_14002CE5A
0x14002cf01  cmp     [rsp+130h+var_EF], dil
0x14002cf06  jnz     loc_14002CE5A
0x14002cf0c  mov     ecx, 18h
0x14002cf11  call    AiAlloc
0x14002cf16  mov     rdi, rax
0x14002cf19  test    rax, rax
0x14002cf1c  jnz     short loc_14002CF28
0x14002cf1e  mov     ebx, 0C0000017h
0x14002cf23  jmp     loc_14002CE5A
0x14002cf28  mov     qword ptr [rax+0Ch], 0
0x14002cf30  lea     rcx, [rbp+57h+var_B0]
0x14002cf34  mov     dword ptr [rax+14h], 0
0x14002cf3b  mov     [rax], rsi
0x14002cf3e  mov     dword ptr [rax+8], 0C0000001h
0x14002cf45  mov     [rbp+57h+var_A8], rsi
0x14002cf49  mov     [rbp+57h+var_80], r14
0x14002cf4d  mov     [rbp+57h+var_88], r13
0x14002cf51  mov     [rbp+57h+var_78], rax
0x14002cf55  call    EdppImpersonateProcess
0x14002cf5a  mov     ebx, eax
0x14002cf5c  test    eax, eax
0x14002cf5e  js      loc_14002CE5A
0x14002cf64  lea     rdx, [rbp+57h+var_B0]
0x14002cf68  mov     rcx, rsi
0x14002cf6b  mov     r15d, 1
0x14002cf71  call    EdppCaptureProcess
0x14002cf76  mov     ebx, eax
0x14002cf78  test    eax, eax
0x14002cf7a  js      loc_14002CE5A
0x14002cf80  test    r12b, r12b
0x14002cf83  jz      short loc_14002CF8E
0x14002cf85  movups  xmm0, cs:AiCategoryAppx
0x14002cf8c  jmp     short loc_14002CF95
0x14002cf8e  movups  xmm0, cs:AiCategoryExe
0x14002cf95  movdqa  [rbp+57h+var_50], xmm0
0x14002cf9a  test    r12b, r12b
0x14002cf9d  jz      short loc_14002CFC4
0x14002cf9f  mov     r8b, [rsp+130h+var_EE]
0x14002cfa4  mov     r9, r14
0x14002cfa7  mov     rdx, [rbp+57h+var_A0]
0x14002cfab  mov     rcx, [rbp+57h+var_90]
0x14002cfaf  mov     [rsp+130h+var_108], 0
0x14002cfb8  mov     [rsp+130h+var_110], r13
0x14002cfbd  call    AiSetAttributesAppx
0x14002cfc2  jmp     short loc_14002CFDC
0x14002cfc4  mov     rdx, [rbp+57h+var_90]
0x14002cfc8  mov     r9, r13
0x14002cfcb  mov     rcx, [rbp+57h+ThreadInformation]
0x14002cfcf  mov     r8, r14
0x14002cfd2  mov     byte ptr [rsp+130h+var_110], 0
0x14002cfd7  call    AiSetAttributesExe
0x14002cfdc  mov     ebx, eax
0x14002cfde  test    eax, eax
0x14002cfe0  js      loc_14002CE5A
0x14002cfe6  mov     rdx, [rbp+57h+var_C0]
0x14002cfea  lea     rax, [rbp+57h+var_50]
0x14002cfee  mov     [rbp+57h+var_68], rax
0x14002cff2  lea     r9, [rbp+57h+var_B8]
0x14002cff6  mov     rcx, r12
0x14002cff9  lea     r8, [rsp+130h+var_D8]
0x14002cffe  mov     r12, [rsp+130h+var_E8]
0x14002d003  add     rcx, rcx
0x14002d006  mov     eax, [rdx+rcx*8]
0x14002d009  mov     [rbp+57h+var_60], eax
0x14002d00c  mov     rax, [rdx+rcx*8+8]
0x14002d011  lea     rdx, [rsp+130h+var_DC]
0x14002d016  mov     [rbp+57h+var_58], rax
0x14002d01a  lea     rcx, [rbp+57h+var_B0]
0x14002d01e  lea     rax, [rsp+130h+var_E0]
0x14002d023  mov     [rbp+57h+var_B0], r12
0x14002d027  mov     [rsp+130h+var_110], rax
0x14002d02c  call    EdpPluginEvaluate
0x14002d031  mov     ebx, eax
0x14002d033  test    eax, eax
0x14002d035  js      short loc_14002D066
0x14002d037  cmp     cs:dword_14001950C, r15d
0x14002d03e  mov     r8, [rsp+130h+var_D8]
0x14002d043  jnz     short loc_14002D04A
0x14002d045  bts     r8, 7
0x14002d04a  mov     eax, [rsp+130h+var_E0]
0x14002d04e  lea     rcx, [rbp+57h+var_B0]
0x14002d052  mov     r9, [rbp+57h+var_B8]
0x14002d056  mov     [rsp+130h+var_100], r15d
0x14002d05b  mov     dword ptr [rsp+130h+var_110], eax
0x14002d05f  call    EdpPluginAction
0x14002d064  mov     ebx, eax
0x14002d066  mov     [rbp+57h+var_B0], 0
0x14002d06e  jmp     loc_14002CE5F
```
