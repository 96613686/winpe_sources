# BfsCalculateRegistryPrefix

- ea: `0x14000e9d8`
- end: `0x14000ed7c`
- name: `BfsCalculateRegistryPrefix`
- size: `932`
- prototype: `__int64 __fastcall(PUCHAR *, PUCHAR *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ed84`

## callees

- `0x140001008`
- `0x14000e9d8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ec6d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000ec6d`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ebc6`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ebc6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ea3b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ea3b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ec83`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed2b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed3e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed4d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ec83`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed2b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed3e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ed4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ec0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ec5a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000ec5a`
- `ntoskrnl!ExAllocatePool2` at `0x14000eb0e`
- `ntoskrnl!ExAllocatePool2` at `0x14000ec39`
- `ntoskrnl!ExAllocatePool2` at `0x14000eb0e`
- `ntoskrnl!ExAllocatePool2` at `0x14000ec39`
- `cng!BCryptCreateHash` at `0x14000ea61`
- `cng!BCryptCreateHash` at `0x14000ea61`
- `cng!BCryptGetProperty` at `0x14000ead6`
- `cng!BCryptGetProperty` at `0x14000ead6`
- `cng!BCryptHashData` at `0x14000eb4c`
- `cng!BCryptHashData` at `0x14000eb71`
- `cng!BCryptHashData` at `0x14000eb4c`
- `cng!BCryptHashData` at `0x14000eb71`
- `cng!BCryptFinishHash` at `0x14000eb95`
- `cng!BCryptFinishHash` at `0x14000eb95`
- `cng!BCryptDestroyHash` at `0x14000ed14`
- `cng!BCryptDestroyHash` at `0x14000ed14`

## string_xrefs

- `0x14000ea1b`: `\Registry\WC\Silo`

## pseudocode

```c
__int64 __fastcall BfsCalculateRegistryPrefix(
        PUCHAR *a1,
        PUCHAR *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  BCRYPT_ALG_HANDLE v4; // r15
  NTSTATUS v9; // eax
  int v10; // r8d
  int v11; // r9d
  NTSTATUS Property; // ebx
  int v13; // ecx
  UCHAR *Pool2; // r15
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // r14d
  struct _UNICODE_STRING *v19; // rsi
  USHORT Length; // cx
  USHORT v21; // ax
  __int64 v22; // rax
  int pbSecret; // [rsp+20h] [rbp-89h]
  int v25; // [rsp+40h] [rbp-69h] BYREF
  UCHAR pbOutput[4]; // [rsp+44h] [rbp-65h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-61h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+58h] [rbp-51h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+88h] [rbp-21h] BYREF
  int *v33; // [rsp+A8h] [rbp-1h]
  __int64 v34; // [rsp+B0h] [rbp+7h]

  v4 = gBfsSHA256Handle;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  DestinationString = 0;
  GuidString = 0;
  Source = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\WC\\Silo");
  v9 = BCryptCreateHash(v4, &phHash, 0, 0, 0, 0, 0);
  Property = v9;
  if ( v9 < 0 )
  {
    v13 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_31;
    v25 = v9;
    v34 = 4;
    goto LABEL_4;
  }
  Property = BCryptGetProperty(v4, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1685284418);
    if ( Pool2 )
    {
      Property = BCryptHashData(phHash, a2[1], *(unsigned __int16 *)a2, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, a1[1], *(unsigned __int16 *)a1, 0);
        if ( Property >= 0 )
        {
          Property = BCryptFinishHash(phHash, Pool2, *(ULONG *)pbOutput, 0);
          if ( Property >= 0 )
          {
            v18 = 0;
            while ( 1 )
            {
              v19 = a3;
              if ( v18 )
                v19 = a4;
              Property = RtlStringFromGUID((const GUID *const)&Pool2[16 * v18], &GuidString);
              if ( Property < 0 )
                break;
              Source.Buffer = GuidString.Buffer + 1;
              Length = GuidString.Length - 4;
              Source.Length = GuidString.Length - 4;
              Source.MaximumLength = GuidString.MaximumLength - 4;
              if ( v19->Buffer )
              {
                ExFreePoolWithTag(v19->Buffer, 0);
                Length = Source.Length;
              }
              v21 = Length + DestinationString.Length + 2;
              v19->MaximumLength = v21;
              v22 = ExAllocatePool2(256, v21, 1316185666);
              v19->Buffer = (PWSTR)v22;
              if ( !v22 )
              {
                v15 = -1073741801;
                Property = -1073741801;
                if ( (unsigned int)dword_140019000 <= 3 )
                  goto LABEL_30;
                v25 = -1073741801;
                v33 = &v25;
                goto LABEL_29;
              }
              v19->Length = 0;
              RtlCopyUnicodeString(v19, &DestinationString);
              Property = RtlAppendUnicodeStringToString(v19, &Source);
              if ( Property < 0 )
                break;
              RtlFreeUnicodeString(&GuidString);
              if ( (unsigned int)++v18 >= 2 )
              {
                Property = 0;
                goto LABEL_30;
              }
            }
          }
        }
      }
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v33 = &v25;
        v25 = Property;
LABEL_29:
        v34 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v16, v17, pbSecret, &v32);
      }
LABEL_30:
      ExFreePoolWithTag(Pool2, 0x64736642u);
    }
    else
    {
      v13 = -1073741801;
      Property = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v25 = -1073741801;
        goto LABEL_8;
      }
    }
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v25 = Property;
LABEL_8:
    v34 = 4;
LABEL_4:
    v33 = &v25;
    tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, pbSecret, &v32);
  }
LABEL_31:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( Property < 0 )
  {
    RtlFreeUnicodeString(a3);
    RtlFreeUnicodeString(a4);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000e9d8  push    rbp
0x14000e9da  push    rbx
0x14000e9db  push    rsi
0x14000e9dc  push    rdi
0x14000e9dd  push    r12
0x14000e9df  push    r13
0x14000e9e1  push    r14
0x14000e9e3  push    r15
0x14000e9e5  lea     rbp, [rsp-1Fh]
0x14000e9ea  sub     rsp, 0C8h
0x14000e9f1  mov     rax, cs:__security_cookie
0x14000e9f8  xor     rax, rsp
0x14000e9fb  mov     [rbp+57h+var_48], rax
0x14000e9ff  mov     r15, cs:gBfsSHA256Handle
0x14000ea06  xorps   xmm0, xmm0
0x14000ea09  xor     ebx, ebx
0x14000ea0b  mov     r14, rdx
0x14000ea0e  mov     rsi, rcx
0x14000ea11  mov     [rbp+57h+phHash], rbx
0x14000ea15  xorps   xmm1, xmm1
0x14000ea18  mov     dword ptr [rbp+57h+pbOutput], ebx
0x14000ea1b  lea     rdx, aRegistryWcSilo; "\\Registry\\WC\\Silo"
0x14000ea22  mov     [rbp+57h+pcbResult], ebx
0x14000ea25  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000ea29  mov     r13, r9
0x14000ea2c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000ea30  mov     r12, r8
0x14000ea33  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x14000ea37  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000ea3b  call    cs:__imp_RtlInitUnicodeString
0x14000ea42  nop     dword ptr [rax+rax+00h]
0x14000ea47  mov     [rsp+100h+dwFlags], ebx; dwFlags
0x14000ea4b  lea     rdx, [rbp+57h+phHash]; phHash
0x14000ea4f  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x14000ea53  xor     r9d, r9d; cbHashObject
0x14000ea56  xor     r8d, r8d; pbHashObject
0x14000ea59  mov     [rsp+100h+pbSecret], rbx; int
0x14000ea5e  mov     rcx, r15; hAlgorithm
0x14000ea61  call    cs:__imp_BCryptCreateHash
0x14000ea68  nop     dword ptr [rax+rax+00h]
0x14000ea6d  mov     ebx, eax
0x14000ea6f  test    eax, eax
0x14000ea71  jns     short loc_14000EAAF
0x14000ea73  mov     ecx, cs:dword_140019000; int
0x14000ea79  cmp     ecx, 3
0x14000ea7c  jbe     loc_14000ED0B
0x14000ea82  mov     [rbp+57h+var_C0], eax
0x14000ea85  mov     [rbp+57h+var_50], 4
0x14000ea8d  lea     rax, [rbp+57h+var_C0]
0x14000ea91  mov     [rbp+57h+var_58], rax
0x14000ea95  lea     rdx, byte_140016D91; int
0x14000ea9c  lea     rax, [rbp+57h+var_78]
0x14000eaa0  mov     qword ptr [rsp+100h+cbSecret], rax; PEVENT_DATA_DESCRIPTOR
0x14000eaa5  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000eaaa  jmp     loc_14000ED0B
0x14000eaaf  lea     rax, [rbp+57h+pcbResult]
0x14000eab3  mov     [rsp+100h+cbSecret], 0; dwFlags
0x14000eabb  mov     edi, 4
0x14000eac0  mov     [rsp+100h+pbSecret], rax; int
0x14000eac5  mov     r9d, edi; cbOutput
0x14000eac8  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14000eacc  lea     rdx, pszProperty; "HashDigestLength"
0x14000ead3  mov     rcx, r15; hObject
0x14000ead6  call    cs:__imp_BCryptGetProperty
0x14000eadd  nop     dword ptr [rax+rax+00h]
0x14000eae2  mov     ebx, eax
0x14000eae4  test    eax, eax
0x14000eae6  jns     short loc_14000EB00
0x14000eae8  mov     eax, cs:dword_140019000
0x14000eaee  cmp     eax, 3
0x14000eaf1  jbe     loc_14000ED0B
0x14000eaf7  mov     [rbp+57h+var_C0], ebx
0x14000eafa  mov     [rbp+57h+var_50], rdi
0x14000eafe  jmp     short loc_14000EA8D
0x14000eb00  mov     edx, dword ptr [rbp+57h+pbOutput]
0x14000eb03  mov     ecx, 100h
0x14000eb08  mov     r8d, 64736642h
0x14000eb0e  call    cs:__imp_ExAllocatePool2
0x14000eb15  nop     dword ptr [rax+rax+00h]
0x14000eb1a  mov     r15, rax
0x14000eb1d  test    rax, rax
0x14000eb20  jnz     short loc_14000EB3D
0x14000eb22  mov     eax, cs:dword_140019000
0x14000eb28  mov     ecx, 0C0000017h
0x14000eb2d  mov     ebx, ecx
0x14000eb2f  cmp     eax, 3
0x14000eb32  jbe     loc_14000ED0B
0x14000eb38  mov     [rbp+57h+var_C0], ecx
0x14000eb3b  jmp     short loc_14000EAFA
0x14000eb3d  movzx   r8d, word ptr [r14]; cbInput
0x14000eb41  xor     r9d, r9d; dwFlags
0x14000eb44  mov     rdx, [r14+8]; pbInput
0x14000eb48  mov     rcx, [rbp+57h+phHash]; hHash
0x14000eb4c  call    cs:__imp_BCryptHashData
0x14000eb53  nop     dword ptr [rax+rax+00h]
0x14000eb58  mov     ebx, eax
0x14000eb5a  test    eax, eax
0x14000eb5c  js      loc_14000ECC8
0x14000eb62  movzx   r8d, word ptr [rsi]; cbInput
0x14000eb66  xor     r9d, r9d; dwFlags
0x14000eb69  mov     rdx, [rsi+8]; pbInput
0x14000eb6d  mov     rcx, [rbp+57h+phHash]; hHash
0x14000eb71  call    cs:__imp_BCryptHashData
0x14000eb78  nop     dword ptr [rax+rax+00h]
0x14000eb7d  mov     ebx, eax
0x14000eb7f  test    eax, eax
0x14000eb81  js      loc_14000ECC8
0x14000eb87  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x14000eb8b  xor     r9d, r9d; dwFlags
0x14000eb8e  mov     rcx, [rbp+57h+phHash]; hHash
0x14000eb92  mov     rdx, r15; pbOutput
0x14000eb95  call    cs:__imp_BCryptFinishHash
0x14000eb9c  nop     dword ptr [rax+rax+00h]
0x14000eba1  mov     ebx, eax
0x14000eba3  test    eax, eax
0x14000eba5  js      loc_14000ECC8
0x14000ebab  xor     r14d, r14d
0x14000ebae  test    r14d, r14d
0x14000ebb1  mov     ecx, r14d
0x14000ebb4  mov     rsi, r12
0x14000ebb7  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14000ebbb  cmovnz  rsi, r13
0x14000ebbf  shl     rcx, 4
0x14000ebc3  add     rcx, r15; Guid
0x14000ebc6  call    cs:__imp_RtlStringFromGUID
0x14000ebcd  nop     dword ptr [rax+rax+00h]
0x14000ebd2  mov     ebx, eax
0x14000ebd4  test    eax, eax
0x14000ebd6  js      loc_14000ECC8
0x14000ebdc  mov     rax, [rbp+57h+GuidString.Buffer]
0x14000ebe0  movzx   ecx, [rbp+57h+GuidString.Length]
0x14000ebe4  add     rax, 2
0x14000ebe8  mov     [rbp+57h+Source.Buffer], rax
0x14000ebec  sub     cx, di
0x14000ebef  movzx   eax, [rbp+57h+GuidString.MaximumLength]
0x14000ebf3  sub     ax, di
0x14000ebf6  mov     [rbp+57h+Source.Length], cx
0x14000ebfa  mov     [rbp+57h+Source.MaximumLength], ax
0x14000ebfe  mov     rax, [rsi+8]
0x14000ec02  test    rax, rax
0x14000ec05  jz      short loc_14000EC1C
0x14000ec07  xor     edx, edx; Tag
0x14000ec09  mov     rcx, rax; P
0x14000ec0c  call    cs:__imp_ExFreePoolWithTag
0x14000ec13  nop     dword ptr [rax+rax+00h]
0x14000ec18  movzx   ecx, [rbp+57h+Source.Length]
0x14000ec1c  movzx   eax, [rbp+57h+DestinationString.Length]
0x14000ec20  mov     r8d, 4E736642h
0x14000ec26  add     ax, 2
0x14000ec2a  add     ax, cx
0x14000ec2d  mov     ecx, 100h
0x14000ec32  movzx   edx, ax
0x14000ec35  mov     [rsi+2], dx
0x14000ec39  call    cs:__imp_ExAllocatePool2
0x14000ec40  nop     dword ptr [rax+rax+00h]
0x14000ec45  mov     [rsi+8], rax
0x14000ec49  test    rax, rax
0x14000ec4c  jz      short loc_14000ECA0
0x14000ec4e  xor     eax, eax
0x14000ec50  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14000ec54  mov     rcx, rsi; DestinationString
0x14000ec57  mov     [rsi], ax
0x14000ec5a  call    cs:__imp_RtlCopyUnicodeString
0x14000ec61  nop     dword ptr [rax+rax+00h]
0x14000ec66  lea     rdx, [rbp+57h+Source]; Source
0x14000ec6a  mov     rcx, rsi; Destination
0x14000ec6d  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000ec74  nop     dword ptr [rax+rax+00h]
0x14000ec79  mov     ebx, eax
0x14000ec7b  test    eax, eax
0x14000ec7d  js      short loc_14000ECC8
0x14000ec7f  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000ec83  call    cs:__imp_RtlFreeUnicodeString
0x14000ec8a  nop     dword ptr [rax+rax+00h]
0x14000ec8f  inc     r14d
0x14000ec92  cmp     r14d, 2
0x14000ec96  jb      loc_14000EBAE
0x14000ec9c  xor     ebx, ebx
0x14000ec9e  jmp     short loc_14000ECF7
0x14000eca0  mov     eax, cs:dword_140019000
0x14000eca6  mov     ecx, 0C0000017h
0x14000ecab  mov     ebx, ecx
0x14000ecad  cmp     eax, 3
0x14000ecb0  jbe     short loc_14000ECF7
0x14000ecb2  lea     rax, [rbp+57h+var_C0]
0x14000ecb6  mov     [rbp+57h+var_C0], ecx
0x14000ecb9  mov     [rbp+57h+var_58], rax
0x14000ecbd  lea     rax, [rbp+57h+var_78]
0x14000ecc1  mov     qword ptr [rsp+100h+cbSecret], rax
0x14000ecc6  jmp     short loc_14000ECE7
0x14000ecc8  mov     eax, cs:dword_140019000
0x14000ecce  cmp     eax, 3
0x14000ecd1  jbe     short loc_14000ECF7
0x14000ecd3  lea     rax, [rbp+57h+var_C0]
0x14000ecd7  mov     [rbp+57h+var_58], rax
0x14000ecdb  lea     rax, [rbp+57h+var_78]
0x14000ecdf  mov     qword ptr [rsp+100h+cbSecret], rax; PEVENT_DATA_DESCRIPTOR
0x14000ece4  mov     [rbp+57h+var_C0], ebx
0x14000ece7  lea     rdx, byte_140016D91; int
0x14000ecee  mov     [rbp+57h+var_50], rdi
0x14000ecf2  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ecf7  mov     edx, 64736642h; Tag
0x14000ecfc  mov     rcx, r15; P
0x14000ecff  call    cs:__imp_ExFreePoolWithTag
0x14000ed06  nop     dword ptr [rax+rax+00h]
0x14000ed0b  mov     rcx, [rbp+57h+phHash]; hHash
0x14000ed0f  test    rcx, rcx
0x14000ed12  jz      short loc_14000ED20
0x14000ed14  call    cs:__imp_BCryptDestroyHash
0x14000ed1b  nop     dword ptr [rax+rax+00h]
0x14000ed20  cmp     [rbp+57h+GuidString.Buffer], 0
0x14000ed25  jz      short loc_14000ED37
0x14000ed27  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000ed2b  call    cs:__imp_RtlFreeUnicodeString
0x14000ed32  nop     dword ptr [rax+rax+00h]
0x14000ed37  test    ebx, ebx
0x14000ed39  jns     short loc_14000ED59
0x14000ed3b  mov     rcx, r12; UnicodeString
0x14000ed3e  call    cs:__imp_RtlFreeUnicodeString
0x14000ed45  nop     dword ptr [rax+rax+00h]
0x14000ed4a  mov     rcx, r13; UnicodeString
0x14000ed4d  call    cs:__imp_RtlFreeUnicodeString
0x14000ed54  nop     dword ptr [rax+rax+00h]
0x14000ed59  mov     eax, ebx
0x14000ed5b  mov     rcx, [rbp+57h+var_48]
0x14000ed5f  xor     rcx, rsp; StackCookie
0x14000ed62  call    __security_check_cookie
0x14000ed67  add     rsp, 0C8h
0x14000ed6e  pop     r15
0x14000ed70  pop     r14
0x14000ed72  pop     r13
0x14000ed74  pop     r12
0x14000ed76  pop     rdi
0x14000ed77  pop     rsi
0x14000ed78  pop     rbx
0x14000ed79  pop     rbp
0x14000ed7a  retn
```
