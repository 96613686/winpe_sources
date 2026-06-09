# BfsRemoveKeyValues

- ea: `0x14000f5cc`
- end: `0x14000f799`
- name: `BfsRemoveKeyValues`
- size: `461`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e560`

## callees

- `0x140001008`
- `0x14000f5cc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ZwEnumerateValueKey` at `0x14000f646`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000f646`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000f691`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000f691`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f700`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f6e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f700`
- `ntoskrnl!ExAllocatePool2` at `0x14000f613`
- `ntoskrnl!ExAllocatePool2` at `0x14000f71e`
- `ntoskrnl!ExAllocatePool2` at `0x14000f613`
- `ntoskrnl!ExAllocatePool2` at `0x14000f71e`

## pseudocode

```c
__int64 __fastcall BfsRemoveKeyValues(HANDLE KeyHandle)
{
  ULONG v1; // r14d
  USHORT *Pool2; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  NTSTATUS i; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // esi
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  ULONG Length; // [rsp+20h] [rbp-39h]
  int v14; // [rsp+30h] [rbp-29h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-25h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+48h] [rbp-11h] BYREF
  int *v18; // [rsp+68h] [rbp+Fh]
  __int64 v19; // [rsp+70h] [rbp+17h]

  v1 = 216;
  ResultLength = 0;
  ValueName = 0;
  Pool2 = (USHORT *)ExAllocatePool2(256, 216, 1450403394);
  if ( !Pool2 )
  {
LABEL_14:
    i = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v18 = &v14;
      v14 = -1073741801;
      v19 = 4;
      tlgWriteTransfer_EtwWriteTransfer(3221225495LL, (unsigned __int8 *)&byte_140016D91, v4, v5, Length, &v17);
    }
    return (unsigned int)i;
  }
  for ( i = 0; i >= 0; i = ZwDeleteValueKey(KeyHandle, &ValueName) )
  {
    while ( 1 )
    {
      v7 = ZwEnumerateValueKey(KeyHandle, 0, KeyValueBasicInformation, Pool2, v1, &ResultLength);
      v8 = v7;
      if ( v7 == -2147483643 || v7 == -1073741789 )
      {
        ExFreePoolWithTag(Pool2, 0);
        v1 = ResultLength;
        Pool2 = (USHORT *)ExAllocatePool2(256, ResultLength, 1450403394);
        if ( !Pool2 )
          goto LABEL_14;
        goto LABEL_12;
      }
      if ( v7 >= 0 )
        break;
LABEL_12:
      if ( v8 == -2147483622 )
        goto LABEL_9;
    }
    ValueName.Length = Pool2[4];
    ValueName.MaximumLength = Pool2[4];
    ValueName.Buffer = Pool2 + 6;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = &v14;
    v14 = i;
    v19 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v9, (unsigned __int8 *)&byte_140016D91, v10, v11, Length, &v17);
  }
LABEL_9:
  ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x14000f5cc  push    rbp
0x14000f5ce  push    rbx
0x14000f5cf  push    rsi
0x14000f5d0  push    rdi
0x14000f5d1  push    r14
0x14000f5d3  push    r15
0x14000f5d5  lea     rbp, [rsp-2Fh]
0x14000f5da  sub     rsp, 88h
0x14000f5e1  mov     rax, cs:__security_cookie
0x14000f5e8  xor     rax, rsp
0x14000f5eb  mov     [rbp+57h+var_38], rax
0x14000f5ef  mov     r14d, 0D8h
0x14000f5f5  mov     [rbp+57h+var_7C], 0
0x14000f5fc  mov     r15, rcx
0x14000f5ff  xorps   xmm0, xmm0
0x14000f602  mov     r8d, 56736642h
0x14000f608  mov     edx, r14d
0x14000f60b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14000f60f  lea     ecx, [r14+28h]
0x14000f613  call    cs:__imp_ExAllocatePool2
0x14000f61a  nop     dword ptr [rax+rax+00h]
0x14000f61f  mov     rdi, rax
0x14000f622  test    rax, rax
0x14000f625  jz      loc_14000F740
0x14000f62b  xor     ebx, ebx
0x14000f62d  lea     rax, [rbp+57h+var_7C]
0x14000f631  mov     r9, rdi; KeyValueInformation
0x14000f634  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14000f639  xor     r8d, r8d; KeyValueInformationClass
0x14000f63c  xor     edx, edx; Index
0x14000f63e  mov     [rsp+0B0h+Length], r14d; int
0x14000f643  mov     rcx, r15; KeyHandle
0x14000f646  call    cs:__imp_ZwEnumerateValueKey
0x14000f64d  nop     dword ptr [rax+rax+00h]
0x14000f652  mov     esi, eax
0x14000f654  cmp     eax, 80000005h
0x14000f659  jz      loc_14000F6FB
0x14000f65f  cmp     eax, 0C0000023h
0x14000f664  jz      loc_14000F6FB
0x14000f66a  test    eax, eax
0x14000f66c  js      loc_14000F6F5
0x14000f672  movzx   eax, word ptr [rdi+8]
0x14000f676  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000f67a  mov     [rbp+57h+ValueName.Length], ax
0x14000f67e  mov     rcx, r15; KeyHandle
0x14000f681  movzx   eax, word ptr [rdi+8]
0x14000f685  mov     [rbp+57h+ValueName.MaximumLength], ax
0x14000f689  lea     rax, [rdi+0Ch]
0x14000f68d  mov     [rbp+57h+ValueName.Buffer], rax
0x14000f691  call    cs:__imp_ZwDeleteValueKey
0x14000f698  nop     dword ptr [rax+rax+00h]
0x14000f69d  mov     ebx, eax
0x14000f69f  test    eax, eax
0x14000f6a1  jns     short loc_14000F62D
0x14000f6a3  mov     eax, cs:dword_140019000
0x14000f6a9  cmp     eax, 3
0x14000f6ac  jbe     short loc_14000F6D6
0x14000f6ae  lea     rax, [rbp+57h+var_80]
0x14000f6b2  mov     [rbp+57h+var_48], rax
0x14000f6b6  lea     rax, [rbp+57h+var_68]
0x14000f6ba  mov     [rsp+0B0h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000f6bf  lea     rdx, byte_140016D91; int
0x14000f6c6  mov     [rbp+57h+var_80], ebx
0x14000f6c9  mov     [rbp+57h+var_40], 4
0x14000f6d1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f6d6  test    rdi, rdi
0x14000f6d9  jz      loc_14000F77A
0x14000f6df  xor     edx, edx; Tag
0x14000f6e1  mov     rcx, rdi; P
0x14000f6e4  call    cs:__imp_ExFreePoolWithTag
0x14000f6eb  nop     dword ptr [rax+rax+00h]
0x14000f6f0  jmp     loc_14000F77A
0x14000f6f5  test    ebx, ebx
0x14000f6f7  js      short loc_14000F6A3
0x14000f6f9  jmp     short loc_14000F732
0x14000f6fb  xor     edx, edx; Tag
0x14000f6fd  mov     rcx, rdi; P
0x14000f700  call    cs:__imp_ExFreePoolWithTag
0x14000f707  nop     dword ptr [rax+rax+00h]
0x14000f70c  mov     r14d, [rbp+57h+var_7C]
0x14000f710  mov     ecx, 100h
0x14000f715  mov     edx, r14d
0x14000f718  mov     r8d, 56736642h
0x14000f71e  call    cs:__imp_ExAllocatePool2
0x14000f725  nop     dword ptr [rax+rax+00h]
0x14000f72a  mov     rdi, rax
0x14000f72d  test    rax, rax
0x14000f730  jz      short loc_14000F740
0x14000f732  cmp     esi, 8000001Ah
0x14000f738  jnz     loc_14000F62D
0x14000f73e  jmp     short loc_14000F6D6
0x14000f740  mov     eax, cs:dword_140019000
0x14000f746  mov     ecx, 0C0000017h; int
0x14000f74b  mov     ebx, ecx
0x14000f74d  cmp     eax, 3
0x14000f750  jbe     short loc_14000F77A
0x14000f752  lea     rax, [rbp+57h+var_80]
0x14000f756  mov     [rbp+57h+var_48], rax
0x14000f75a  lea     rax, [rbp+57h+var_68]
0x14000f75e  mov     [rsp+0B0h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000f763  lea     rdx, byte_140016D91; int
0x14000f76a  mov     [rbp+57h+var_80], ecx
0x14000f76d  mov     [rbp+57h+var_40], 4
0x14000f775  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f77a  mov     eax, ebx
0x14000f77c  mov     rcx, [rbp+57h+var_38]
0x14000f780  xor     rcx, rsp; StackCookie
0x14000f783  call    __security_check_cookie
0x14000f788  add     rsp, 88h
0x14000f78f  pop     r15
0x14000f791  pop     r14
0x14000f793  pop     rdi
0x14000f794  pop     rsi
0x14000f795  pop     rbx
0x14000f796  pop     rbp
0x14000f797  retn
```
