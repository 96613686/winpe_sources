# QueryAttributes

- ea: `0x14010fb10`
- end: `0x14010fd3f`
- name: `QueryAttributes`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14010fd48`
- `0x14010fdd8`

## callees

- `0x14010f730`
- `0x14010fb10`
- `0x1401f3fc0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14010fb73`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fba9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fbd7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc02`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc30`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fb73`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fba9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fbd7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc02`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010fc30`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14010fc86`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14010fc86`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14010fc9d`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14010fc9d`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14010fcaf`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14010fcaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fc48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fcde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fd01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fc48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fcde`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fd01`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // esi
  int SecurityAttributesToken; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  _DWORD v13[4]; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-19h] BYREF

  memset(DestinationString, 0, sizeof(DestinationString));
  v6 = 0;
  v13[0] = 0;
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = 100;
    RtlInitUnicodeString(DestinationString, L"EDP://PolicyFlags");
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v7 = 16;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EnterpriseIds");
  }
  if ( (a2 & 4) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"PEDP://IntentEnterpriseId");
  }
  if ( (a2 & 8) != 0 )
  {
    v7 += 84;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EvaluationFlags");
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v6 = (void *)EnterpriseContextLibMemAlloc(v7);
    if ( !v6 )
      return (unsigned int)-1073741801;
    if ( *a1 )
    {
      SecurityAttributesToken = SeQuerySecurityAttributesToken(*a1, DestinationString, v8, v6, v7, v13);
    }
    else
    {
      v10 = a1[3];
      if ( v10 )
        SecurityAttributesToken = ZwQuerySecurityAttributesToken(v10, DestinationString, v8, v6, v7, v13);
      else
        SecurityAttributesToken = SeQuerySecurityAttributesTokenAccessInformation(
                                    a1[2],
                                    DestinationString,
                                    v8,
                                    v6,
                                    v7,
                                    v13);
    }
    v11 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
    {
      if ( SecurityAttributesToken == -1073741275 )
      {
        ExFreePoolWithTag(v6, 0);
        v11 = 0;
        *a3 = 0;
        return v11;
      }
      if ( SecurityAttributesToken >= 0 )
      {
        *a3 = v6;
        return v11;
      }
LABEL_27:
      ExFreePoolWithTag(v6, 0);
      return v11;
    }
    if ( v7 >= v13[0] )
      goto LABEL_27;
    v7 = v13[0];
  }
}

```

## disassembly

```asm
0x14010fb10  mov     [rsp-8+arg_8], rbx
0x14010fb15  mov     [rsp-8+arg_18], rsi
0x14010fb1a  push    rbp
0x14010fb1b  push    rdi
0x14010fb1c  push    r12
0x14010fb1e  push    r14
0x14010fb20  push    r15
0x14010fb22  lea     rbp, [rsp-37h]
0x14010fb27  sub     rsp, 90h
0x14010fb2e  mov     rax, cs:__security_cookie
0x14010fb35  xor     rax, rsp
0x14010fb38  mov     [rbp+57h+var_30], rax
0x14010fb3c  mov     edi, edx
0x14010fb3e  mov     r12, r8
0x14010fb41  xor     edx, edx; Val
0x14010fb43  mov     r15, rcx
0x14010fb46  lea     rcx, [rbp+57h+DestinationString]; void *
0x14010fb4a  lea     r8d, [rdx+40h]; Size
0x14010fb4e  call    memset
0x14010fb53  xor     r14d, r14d
0x14010fb56  mov     [rbp+57h+var_80], r14d
0x14010fb5a  mov     [r12], r14
0x14010fb5e  test    dil, 1
0x14010fb62  jz      short loc_14010FB84
0x14010fb64  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x14010fb6b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14010fb6f  lea     ebx, [r14+64h]
0x14010fb73  call    cs:__imp_RtlInitUnicodeString
0x14010fb7a  nop     dword ptr [rax+rax+00h]
0x14010fb7f  lea     esi, [rbx-63h]
0x14010fb82  jmp     short loc_14010FB89
0x14010fb84  xor     esi, esi
0x14010fb86  lea     ebx, [rsi+10h]
0x14010fb89  test    dil, 2
0x14010fb8d  jz      short loc_14010FBB7
0x14010fb8f  mov     eax, esi
0x14010fb91  lea     rcx, [rbp+57h+DestinationString]
0x14010fb95  shl     rax, 4
0x14010fb99  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x14010fba0  add     rcx, rax; DestinationString
0x14010fba3  add     ebx, 98h
0x14010fba9  call    cs:__imp_RtlInitUnicodeString
0x14010fbb0  nop     dword ptr [rax+rax+00h]
0x14010fbb5  inc     esi
0x14010fbb7  test    dil, 4
0x14010fbbb  jz      short loc_14010FBE5
0x14010fbbd  mov     eax, esi
0x14010fbbf  lea     rcx, [rbp+57h+DestinationString]
0x14010fbc3  shl     rax, 4
0x14010fbc7  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x14010fbce  add     rcx, rax; DestinationString
0x14010fbd1  add     ebx, 98h
0x14010fbd7  call    cs:__imp_RtlInitUnicodeString
0x14010fbde  nop     dword ptr [rax+rax+00h]
0x14010fbe3  inc     esi
0x14010fbe5  test    dil, 8
0x14010fbe9  jz      short loc_14010FC10
0x14010fbeb  mov     eax, esi
0x14010fbed  lea     rcx, [rbp+57h+DestinationString]
0x14010fbf1  shl     rax, 4
0x14010fbf5  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x14010fbfc  add     rcx, rax; DestinationString
0x14010fbff  add     ebx, 54h ; 'T'
0x14010fc02  call    cs:__imp_RtlInitUnicodeString
0x14010fc09  nop     dword ptr [rax+rax+00h]
0x14010fc0e  inc     esi
0x14010fc10  test    dil, 10h
0x14010fc14  jz      short loc_14010FC3E
0x14010fc16  mov     eax, esi
0x14010fc18  lea     rcx, [rbp+57h+DestinationString]
0x14010fc1c  shl     rax, 4
0x14010fc20  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x14010fc27  add     rcx, rax; DestinationString
0x14010fc2a  add     ebx, 98h
0x14010fc30  call    cs:__imp_RtlInitUnicodeString
0x14010fc37  nop     dword ptr [rax+rax+00h]
0x14010fc3c  inc     esi
0x14010fc3e  test    r14, r14
0x14010fc41  jz      short loc_14010FC54
0x14010fc43  xor     edx, edx; Tag
0x14010fc45  mov     rcx, r14; P
0x14010fc48  call    cs:__imp_ExFreePoolWithTag
0x14010fc4f  nop     dword ptr [rax+rax+00h]
0x14010fc54  mov     ecx, ebx
0x14010fc56  call    EnterpriseContextLibMemAlloc
0x14010fc5b  mov     r14, rax
0x14010fc5e  test    rax, rax
0x14010fc61  jz      loc_14010FD0F
0x14010fc67  mov     rcx, [r15]
0x14010fc6a  lea     rax, [rbp+57h+var_80]
0x14010fc6e  mov     [rsp+0B0h+var_88], rax
0x14010fc73  mov     r9, r14
0x14010fc76  mov     [rsp+0B0h+var_90], ebx
0x14010fc7a  mov     r8d, esi
0x14010fc7d  lea     rdx, [rbp+57h+DestinationString]
0x14010fc81  test    rcx, rcx
0x14010fc84  jz      short loc_14010FC94
0x14010fc86  call    cs:__imp_SeQuerySecurityAttributesToken
0x14010fc8d  nop     dword ptr [rax+rax+00h]
0x14010fc92  jmp     short loc_14010FCBB
0x14010fc94  mov     rcx, [r15+18h]
0x14010fc98  test    rcx, rcx
0x14010fc9b  jz      short loc_14010FCAB
0x14010fc9d  call    cs:__imp_ZwQuerySecurityAttributesToken
0x14010fca4  nop     dword ptr [rax+rax+00h]
0x14010fca9  jmp     short loc_14010FCBB
0x14010fcab  mov     rcx, [r15+10h]
0x14010fcaf  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x14010fcb6  nop     dword ptr [rax+rax+00h]
0x14010fcbb  mov     edi, eax
0x14010fcbd  cmp     eax, 0C0000023h
0x14010fcc2  jnz     short loc_14010FCD1
0x14010fcc4  cmp     ebx, [rbp+57h+var_80]
0x14010fcc7  jnb     short loc_14010FCFC
0x14010fcc9  mov     ebx, [rbp+57h+var_80]
0x14010fccc  jmp     loc_14010FC3E
0x14010fcd1  cmp     edi, 0C0000225h
0x14010fcd7  jnz     short loc_14010FCF2
0x14010fcd9  xor     edx, edx; Tag
0x14010fcdb  mov     rcx, r14; P
0x14010fcde  call    cs:__imp_ExFreePoolWithTag
0x14010fce5  nop     dword ptr [rax+rax+00h]
0x14010fcea  xor     edi, edi
0x14010fcec  mov     [r12], rdi
0x14010fcf0  jmp     short loc_14010FD14
0x14010fcf2  test    edi, edi
0x14010fcf4  js      short loc_14010FCFC
0x14010fcf6  mov     [r12], r14
0x14010fcfa  jmp     short loc_14010FD14
0x14010fcfc  xor     edx, edx; Tag
0x14010fcfe  mov     rcx, r14; P
0x14010fd01  call    cs:__imp_ExFreePoolWithTag
0x14010fd08  nop     dword ptr [rax+rax+00h]
0x14010fd0d  jmp     short loc_14010FD14
0x14010fd0f  mov     edi, 0C0000017h
0x14010fd14  mov     eax, edi
0x14010fd16  mov     rcx, [rbp+57h+var_30]
0x14010fd1a  xor     rcx, rsp; StackCookie
0x14010fd1d  call    __security_check_cookie
0x14010fd22  lea     r11, [rsp+0B0h+var_20]
0x14010fd2a  mov     rbx, [r11+38h]
0x14010fd2e  mov     rsi, [r11+48h]
0x14010fd32  mov     rsp, r11
0x14010fd35  pop     r15
0x14010fd37  pop     r14
0x14010fd39  pop     r12
0x14010fd3b  pop     rdi
0x14010fd3c  pop     rbp
0x14010fd3d  retn
```
