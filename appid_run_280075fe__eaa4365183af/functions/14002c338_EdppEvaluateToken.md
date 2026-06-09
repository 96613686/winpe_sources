# EdppEvaluateToken

- ea: `0x14002c338`
- end: `0x14002c447`
- name: `EdppEvaluateToken`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002bff0`

## callees

- `0x14000540c`
- `0x140005544`
- `0x1400058c8`
- `0x14002c338`
- `0x14002c838`
- `0x14002c944`

## import_xrefs

- `ntoskrnl!ZwQueryInformationToken` at `0x14002c3a3`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002c3a3`
- `ntoskrnl!ZwClose` at `0x14002c428`
- `ntoskrnl!ZwClose` at `0x14002c428`

## pseudocode

```c
__int64 __fastcall EdppEvaluateToken(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  NTSTATUS IsCurrentContextAllowed; // ebx
  int v5; // edx
  int v6; // r9d
  ULONG ReturnLength; // [rsp+30h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  __int128 v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 v12; // [rsp+80h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+88h] [rbp+28h] BYREF

  v12 = a3;
  v3 = 0;
  LOBYTE(v12) = 0;
  v10 = 0;
  TokenInformation = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  v11 = 0;
  IsCurrentContextAllowed = EdppParseEvaluateData(a1, a2, 140, &v11, &TokenHandle);
  if ( IsCurrentContextAllowed >= 0 )
  {
    IsCurrentContextAllowed = ZwQueryInformationToken(
                                TokenHandle,
                                TokenImpersonationLevel,
                                &TokenInformation,
                                4u,
                                &ReturnLength);
    if ( IsCurrentContextAllowed >= 0 )
    {
      if ( TokenInformation != 2 )
      {
LABEL_4:
        IsCurrentContextAllowed = -1073741790;
        goto LABEL_9;
      }
      IsCurrentContextAllowed = EdppIsCurrentContextAllowed(&v11, &v12);
      if ( IsCurrentContextAllowed >= 0 )
      {
        if ( !(_BYTE)v12 )
          goto LABEL_4;
        IsCurrentContextAllowed = SrpCreateEnterpriseContext(0, 1, &v11, &v10);
        v3 = v10;
        if ( IsCurrentContextAllowed >= 0 )
          IsCurrentContextAllowed = SrpSetEnterpriseContextToken((_DWORD)TokenHandle, v5, 0, v6, v10, 0);
      }
    }
  }
LABEL_9:
  SrpDeleteEnterpriseContext(v3);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  return (unsigned int)IsCurrentContextAllowed;
}

```

## disassembly

```asm
0x14002c338  mov     r11, rsp
0x14002c33b  mov     [r11+8], rbx
0x14002c33f  mov     [r11+10h], rdi
0x14002c343  mov     [r11+18h], r8
0x14002c347  push    rbp
0x14002c348  mov     rbp, rsp
0x14002c34b  sub     rsp, 60h
0x14002c34f  xor     edi, edi
0x14002c351  mov     byte ptr [rbp+arg_10], 0
0x14002c355  xorps   xmm0, xmm0
0x14002c358  mov     [rbp+var_20], rdi
0x14002c35c  lea     rax, [rbp+TokenHandle]
0x14002c360  mov     [rbp+TokenInformation], edi
0x14002c363  lea     r9, [rbp+var_18]
0x14002c367  mov     [rbp+TokenHandle], rdi
0x14002c36b  mov     r8d, 8Ch
0x14002c371  mov     [rbp+var_30], edi
0x14002c374  movups  [rbp+var_18], xmm0
0x14002c378  mov     [r11-48h], rax
0x14002c37c  call    EdppParseEvaluateData
0x14002c381  mov     ebx, eax
0x14002c383  test    eax, eax
0x14002c385  js      loc_14002C417
0x14002c38b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14002c38f  lea     rax, [rbp+var_30]
0x14002c393  lea     r9d, [rdi+4]; TokenInformationLength
0x14002c397  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x14002c39c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14002c3a0  lea     edx, [rdi+9]; TokenInformationClass
0x14002c3a3  call    cs:__imp_ZwQueryInformationToken
0x14002c3aa  nop     dword ptr [rax+rax+00h]
0x14002c3af  mov     ebx, eax
0x14002c3b1  test    eax, eax
0x14002c3b3  js      short loc_14002C417
0x14002c3b5  cmp     [rbp+TokenInformation], 2
0x14002c3b9  jz      short loc_14002C3C2
0x14002c3bb  mov     ebx, 0C0000022h
0x14002c3c0  jmp     short loc_14002C417
0x14002c3c2  lea     rdx, [rbp+arg_10]
0x14002c3c6  lea     rcx, [rbp+var_18]
0x14002c3ca  call    EdppIsCurrentContextAllowed
0x14002c3cf  mov     ebx, eax
0x14002c3d1  test    eax, eax
0x14002c3d3  js      short loc_14002C417
0x14002c3d5  cmp     byte ptr [rbp+arg_10], dil
0x14002c3d9  jz      short loc_14002C3BB
0x14002c3db  lea     r9, [rbp+var_20]
0x14002c3df  mov     edx, 1
0x14002c3e4  lea     r8, [rbp+var_18]
0x14002c3e8  xor     ecx, ecx
0x14002c3ea  call    SrpCreateEnterpriseContext
0x14002c3ef  mov     ebx, eax
0x14002c3f1  test    eax, eax
0x14002c3f3  js      short loc_14002C413
0x14002c3f5  mov     rcx, [rbp+TokenHandle]
0x14002c3f9  xor     r8d, r8d
0x14002c3fc  mov     [rsp+60h+var_38], rdi
0x14002c401  mov     rdi, [rbp+var_20]
0x14002c405  mov     [rsp+60h+ReturnLength], rdi
0x14002c40a  call    SrpSetEnterpriseContextToken
0x14002c40f  mov     ebx, eax
0x14002c411  jmp     short loc_14002C417
0x14002c413  mov     rdi, [rbp+var_20]
0x14002c417  mov     rcx, rdi
0x14002c41a  call    SrpDeleteEnterpriseContext
0x14002c41f  mov     rcx, [rbp+TokenHandle]; Handle
0x14002c423  test    rcx, rcx
0x14002c426  jz      short loc_14002C434
0x14002c428  call    cs:__imp_ZwClose
0x14002c42f  nop     dword ptr [rax+rax+00h]
0x14002c434  mov     rdi, [rsp+60h+arg_8]
0x14002c439  mov     eax, ebx
0x14002c43b  mov     rbx, [rsp+60h+arg_0]
0x14002c440  add     rsp, 60h
0x14002c444  pop     rbp
0x14002c445  retn
```
