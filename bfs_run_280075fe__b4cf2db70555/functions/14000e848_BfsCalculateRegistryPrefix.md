# BfsCalculateRegistryPrefix

- ea: `0x14000e848`
- end: `0x14000ebec`
- name: `BfsCalculateRegistryPrefix`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ebf4`

## callees

- `0x140001008`
- `0x14000e848`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000eadd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000eadd`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ea36`
- `ntoskrnl!RtlStringFromGUID` at `0x14000ea36`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e8ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e8ab`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eaf3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eb9b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ebae`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ebbd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eaf3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000eb9b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ebae`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ebbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eb6f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000eaca`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000eaca`
- `ntoskrnl!ExAllocatePool2` at `0x14000e97e`
- `ntoskrnl!ExAllocatePool2` at `0x14000eaa9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e97e`
- `ntoskrnl!ExAllocatePool2` at `0x14000eaa9`
- `cng!BCryptCreateHash` at `0x14000e8d1`
- `cng!BCryptCreateHash` at `0x14000e8d1`
- `cng!BCryptGetProperty` at `0x14000e946`
- `cng!BCryptGetProperty` at `0x14000e946`
- `cng!BCryptHashData` at `0x14000e9bc`
- `cng!BCryptHashData` at `0x14000e9e1`
- `cng!BCryptHashData` at `0x14000e9bc`
- `cng!BCryptHashData` at `0x14000e9e1`
- `cng!BCryptFinishHash` at `0x14000ea05`
- `cng!BCryptFinishHash` at `0x14000ea05`
- `cng!BCryptDestroyHash` at `0x14000eb84`
- `cng!BCryptDestroyHash` at `0x14000eb84`

## string_xrefs

- `0x14000e88b`: `\Registry\WC\Silo`

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
0x14000e848  push    rbp
0x14000e84a  push    rbx
0x14000e84b  push    rsi
0x14000e84c  push    rdi
0x14000e84d  push    r12
0x14000e84f  push    r13
0x14000e851  push    r14
0x14000e853  push    r15
0x14000e855  lea     rbp, [rsp-1Fh]
0x14000e85a  sub     rsp, 0C8h
0x14000e861  mov     rax, cs:__security_cookie
0x14000e868  xor     rax, rsp
0x14000e86b  mov     [rbp+57h+var_48], rax
0x14000e86f  mov     r15, cs:gBfsSHA256Handle
0x14000e876  xorps   xmm0, xmm0
0x14000e879  xor     ebx, ebx
0x14000e87b  mov     r14, rdx
0x14000e87e  mov     rsi, rcx
0x14000e881  mov     [rbp+57h+phHash], rbx
0x14000e885  xorps   xmm1, xmm1
0x14000e888  mov     dword ptr [rbp+57h+pbOutput], ebx
0x14000e88b  lea     rdx, aRegistryWcSilo; "\\Registry\\WC\\Silo"
0x14000e892  mov     [rbp+57h+pcbResult], ebx
0x14000e895  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000e899  mov     r13, r9
0x14000e89c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000e8a0  mov     r12, r8
0x14000e8a3  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x14000e8a7  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x14000e8ab  call    cs:__imp_RtlInitUnicodeString
0x14000e8b2  nop     dword ptr [rax+rax+00h]
0x14000e8b7  mov     [rsp+100h+dwFlags], ebx; dwFlags
0x14000e8bb  lea     rdx, [rbp+57h+phHash]; phHash
0x14000e8bf  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x14000e8c3  xor     r9d, r9d; cbHashObject
0x14000e8c6  xor     r8d, r8d; pbHashObject
0x14000e8c9  mov     [rsp+100h+pbSecret], rbx; int
0x14000e8ce  mov     rcx, r15; hAlgorithm
0x14000e8d1  call    cs:__imp_BCryptCreateHash
0x14000e8d8  nop     dword ptr [rax+rax+00h]
0x14000e8dd  mov     ebx, eax
0x14000e8df  test    eax, eax
0x14000e8e1  jns     short loc_14000E91F
0x14000e8e3  mov     ecx, cs:dword_140019000; int
0x14000e8e9  cmp     ecx, 3
0x14000e8ec  jbe     loc_14000EB7B
0x14000e8f2  mov     [rbp+57h+var_C0], eax
0x14000e8f5  mov     [rbp+57h+var_50], 4
0x14000e8fd  lea     rax, [rbp+57h+var_C0]
0x14000e901  mov     [rbp+57h+var_58], rax
0x14000e905  lea     rdx, byte_140016D91; int
0x14000e90c  lea     rax, [rbp+57h+var_78]
0x14000e910  mov     qword ptr [rsp+100h+cbSecret], rax; PEVENT_DATA_DESCRIPTOR
0x14000e915  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e91a  jmp     loc_14000EB7B
0x14000e91f  lea     rax, [rbp+57h+pcbResult]
0x14000e923  mov     [rsp+100h+cbSecret], 0; dwFlags
0x14000e92b  mov     edi, 4
0x14000e930  mov     [rsp+100h+pbSecret], rax; int
0x14000e935  mov     r9d, edi; cbOutput
0x14000e938  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14000e93c  lea     rdx, pszProperty; "HashDigestLength"
0x14000e943  mov     rcx, r15; hObject
0x14000e946  call    cs:__imp_BCryptGetProperty
0x14000e94d  nop     dword ptr [rax+rax+00h]
0x14000e952  mov     ebx, eax
0x14000e954  test    eax, eax
0x14000e956  jns     short loc_14000E970
0x14000e958  mov     eax, cs:dword_140019000
0x14000e95e  cmp     eax, 3
0x14000e961  jbe     loc_14000EB7B
0x14000e967  mov     [rbp+57h+var_C0], ebx
0x14000e96a  mov     [rbp+57h+var_50], rdi
0x14000e96e  jmp     short loc_14000E8FD
0x14000e970  mov     edx, dword ptr [rbp+57h+pbOutput]
0x14000e973  mov     ecx, 100h
0x14000e978  mov     r8d, 64736642h
0x14000e97e  call    cs:__imp_ExAllocatePool2
0x14000e985  nop     dword ptr [rax+rax+00h]
0x14000e98a  mov     r15, rax
0x14000e98d  test    rax, rax
0x14000e990  jnz     short loc_14000E9AD
0x14000e992  mov     eax, cs:dword_140019000
0x14000e998  mov     ecx, 0C0000017h
0x14000e99d  mov     ebx, ecx
0x14000e99f  cmp     eax, 3
0x14000e9a2  jbe     loc_14000EB7B
0x14000e9a8  mov     [rbp+57h+var_C0], ecx
0x14000e9ab  jmp     short loc_14000E96A
0x14000e9ad  movzx   r8d, word ptr [r14]; cbInput
0x14000e9b1  xor     r9d, r9d; dwFlags
0x14000e9b4  mov     rdx, [r14+8]; pbInput
0x14000e9b8  mov     rcx, [rbp+57h+phHash]; hHash
0x14000e9bc  call    cs:__imp_BCryptHashData
0x14000e9c3  nop     dword ptr [rax+rax+00h]
0x14000e9c8  mov     ebx, eax
0x14000e9ca  test    eax, eax
0x14000e9cc  js      loc_14000EB38
0x14000e9d2  movzx   r8d, word ptr [rsi]; cbInput
0x14000e9d6  xor     r9d, r9d; dwFlags
0x14000e9d9  mov     rdx, [rsi+8]; pbInput
0x14000e9dd  mov     rcx, [rbp+57h+phHash]; hHash
0x14000e9e1  call    cs:__imp_BCryptHashData
0x14000e9e8  nop     dword ptr [rax+rax+00h]
0x14000e9ed  mov     ebx, eax
0x14000e9ef  test    eax, eax
0x14000e9f1  js      loc_14000EB38
0x14000e9f7  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x14000e9fb  xor     r9d, r9d; dwFlags
0x14000e9fe  mov     rcx, [rbp+57h+phHash]; hHash
0x14000ea02  mov     rdx, r15; pbOutput
0x14000ea05  call    cs:__imp_BCryptFinishHash
0x14000ea0c  nop     dword ptr [rax+rax+00h]
0x14000ea11  mov     ebx, eax
0x14000ea13  test    eax, eax
0x14000ea15  js      loc_14000EB38
0x14000ea1b  xor     r14d, r14d
0x14000ea1e  test    r14d, r14d
0x14000ea21  mov     ecx, r14d
0x14000ea24  mov     rsi, r12
0x14000ea27  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14000ea2b  cmovnz  rsi, r13
0x14000ea2f  shl     rcx, 4
0x14000ea33  add     rcx, r15; Guid
0x14000ea36  call    cs:__imp_RtlStringFromGUID
0x14000ea3d  nop     dword ptr [rax+rax+00h]
0x14000ea42  mov     ebx, eax
0x14000ea44  test    eax, eax
0x14000ea46  js      loc_14000EB38
0x14000ea4c  mov     rax, [rbp+57h+GuidString.Buffer]
0x14000ea50  movzx   ecx, [rbp+57h+GuidString.Length]
0x14000ea54  add     rax, 2
0x14000ea58  mov     [rbp+57h+Source.Buffer], rax
0x14000ea5c  sub     cx, di
0x14000ea5f  movzx   eax, [rbp+57h+GuidString.MaximumLength]
0x14000ea63  sub     ax, di
0x14000ea66  mov     [rbp+57h+Source.Length], cx
0x14000ea6a  mov     [rbp+57h+Source.MaximumLength], ax
0x14000ea6e  mov     rax, [rsi+8]
0x14000ea72  test    rax, rax
0x14000ea75  jz      short loc_14000EA8C
0x14000ea77  xor     edx, edx; Tag
0x14000ea79  mov     rcx, rax; P
0x14000ea7c  call    cs:__imp_ExFreePoolWithTag
0x14000ea83  nop     dword ptr [rax+rax+00h]
0x14000ea88  movzx   ecx, [rbp+57h+Source.Length]
0x14000ea8c  movzx   eax, [rbp+57h+DestinationString.Length]
0x14000ea90  mov     r8d, 4E736642h
0x14000ea96  add     ax, 2
0x14000ea9a  add     ax, cx
0x14000ea9d  mov     ecx, 100h
0x14000eaa2  movzx   edx, ax
0x14000eaa5  mov     [rsi+2], dx
0x14000eaa9  call    cs:__imp_ExAllocatePool2
0x14000eab0  nop     dword ptr [rax+rax+00h]
0x14000eab5  mov     [rsi+8], rax
0x14000eab9  test    rax, rax
0x14000eabc  jz      short loc_14000EB10
0x14000eabe  xor     eax, eax
0x14000eac0  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14000eac4  mov     rcx, rsi; DestinationString
0x14000eac7  mov     [rsi], ax
0x14000eaca  call    cs:__imp_RtlCopyUnicodeString
0x14000ead1  nop     dword ptr [rax+rax+00h]
0x14000ead6  lea     rdx, [rbp+57h+Source]; Source
0x14000eada  mov     rcx, rsi; Destination
0x14000eadd  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000eae4  nop     dword ptr [rax+rax+00h]
0x14000eae9  mov     ebx, eax
0x14000eaeb  test    eax, eax
0x14000eaed  js      short loc_14000EB38
0x14000eaef  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000eaf3  call    cs:__imp_RtlFreeUnicodeString
0x14000eafa  nop     dword ptr [rax+rax+00h]
0x14000eaff  inc     r14d
0x14000eb02  cmp     r14d, 2
0x14000eb06  jb      loc_14000EA1E
0x14000eb0c  xor     ebx, ebx
0x14000eb0e  jmp     short loc_14000EB67
0x14000eb10  mov     eax, cs:dword_140019000
0x14000eb16  mov     ecx, 0C0000017h
0x14000eb1b  mov     ebx, ecx
0x14000eb1d  cmp     eax, 3
0x14000eb20  jbe     short loc_14000EB67
0x14000eb22  lea     rax, [rbp+57h+var_C0]
0x14000eb26  mov     [rbp+57h+var_C0], ecx
0x14000eb29  mov     [rbp+57h+var_58], rax
0x14000eb2d  lea     rax, [rbp+57h+var_78]
0x14000eb31  mov     qword ptr [rsp+100h+cbSecret], rax
0x14000eb36  jmp     short loc_14000EB57
0x14000eb38  mov     eax, cs:dword_140019000
0x14000eb3e  cmp     eax, 3
0x14000eb41  jbe     short loc_14000EB67
0x14000eb43  lea     rax, [rbp+57h+var_C0]
0x14000eb47  mov     [rbp+57h+var_58], rax
0x14000eb4b  lea     rax, [rbp+57h+var_78]
0x14000eb4f  mov     qword ptr [rsp+100h+cbSecret], rax; PEVENT_DATA_DESCRIPTOR
0x14000eb54  mov     [rbp+57h+var_C0], ebx
0x14000eb57  lea     rdx, byte_140016D91; int
0x14000eb5e  mov     [rbp+57h+var_50], rdi
0x14000eb62  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000eb67  mov     edx, 64736642h; Tag
0x14000eb6c  mov     rcx, r15; P
0x14000eb6f  call    cs:__imp_ExFreePoolWithTag
0x14000eb76  nop     dword ptr [rax+rax+00h]
0x14000eb7b  mov     rcx, [rbp+57h+phHash]; hHash
0x14000eb7f  test    rcx, rcx
0x14000eb82  jz      short loc_14000EB90
0x14000eb84  call    cs:__imp_BCryptDestroyHash
0x14000eb8b  nop     dword ptr [rax+rax+00h]
0x14000eb90  cmp     [rbp+57h+GuidString.Buffer], 0
0x14000eb95  jz      short loc_14000EBA7
0x14000eb97  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000eb9b  call    cs:__imp_RtlFreeUnicodeString
0x14000eba2  nop     dword ptr [rax+rax+00h]
0x14000eba7  test    ebx, ebx
0x14000eba9  jns     short loc_14000EBC9
0x14000ebab  mov     rcx, r12; UnicodeString
0x14000ebae  call    cs:__imp_RtlFreeUnicodeString
0x14000ebb5  nop     dword ptr [rax+rax+00h]
0x14000ebba  mov     rcx, r13; UnicodeString
0x14000ebbd  call    cs:__imp_RtlFreeUnicodeString
0x14000ebc4  nop     dword ptr [rax+rax+00h]
0x14000ebc9  mov     eax, ebx
0x14000ebcb  mov     rcx, [rbp+57h+var_48]
0x14000ebcf  xor     rcx, rsp; StackCookie
0x14000ebd2  call    __security_check_cookie
0x14000ebd7  add     rsp, 0C8h
0x14000ebde  pop     r15
0x14000ebe0  pop     r14
0x14000ebe2  pop     r13
0x14000ebe4  pop     r12
0x14000ebe6  pop     rdi
0x14000ebe7  pop     rsi
0x14000ebe8  pop     rbx
0x14000ebe9  pop     rbp
0x14000ebea  retn
```
