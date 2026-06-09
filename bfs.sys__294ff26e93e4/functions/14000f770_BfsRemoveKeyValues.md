# BfsRemoveKeyValues

- ea: `0x14000f770`
- end: `0x14000f93d`
- name: `BfsRemoveKeyValues`
- size: `461`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e6f0`

## callees

- `0x140001008`
- `0x14000f770`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwEnumerateValueKey` at `0x14000f7ea`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000f7ea`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000f835`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000f835`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f888`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f888`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f8a4`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7b7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f8c2`
- `ntoskrnl!ExAllocatePool2` at `0x14000f7b7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f8c2`

## pseudocode

```c
__int64 __fastcall BfsRemoveKeyValues(HANDLE KeyHandle)
{
  ULONG v1; // r14d
  USHORT *Pool2; // rdi
  int v4; // r8d
  int v5; // r9d
  NTSTATUS i; // ebx
  NTSTATUS v7; // eax
  NTSTATUS v8; // esi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
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
      tlgWriteTransfer_EtwWriteTransfer(-1073741801, (int)&byte_140016D91, v4, v5, Length, &v17);
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
    tlgWriteTransfer_EtwWriteTransfer(v9, (int)&byte_140016D91, v10, v11, Length, &v17);
  }
LABEL_9:
  ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x14000f770  push    rbp
0x14000f772  push    rbx
0x14000f773  push    rsi
0x14000f774  push    rdi
0x14000f775  push    r14
0x14000f777  push    r15
0x14000f779  lea     rbp, [rsp-2Fh]
0x14000f77e  sub     rsp, 88h
0x14000f785  mov     rax, cs:__security_cookie
0x14000f78c  xor     rax, rsp
0x14000f78f  mov     [rbp+57h+var_38], rax
0x14000f793  mov     r14d, 0D8h
0x14000f799  mov     [rbp+57h+var_7C], 0
0x14000f7a0  mov     r15, rcx
0x14000f7a3  xorps   xmm0, xmm0
0x14000f7a6  mov     r8d, 56736642h
0x14000f7ac  mov     edx, r14d
0x14000f7af  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14000f7b3  lea     ecx, [r14+28h]
0x14000f7b7  call    cs:__imp_ExAllocatePool2
0x14000f7be  nop     dword ptr [rax+rax+00h]
0x14000f7c3  mov     rdi, rax
0x14000f7c6  test    rax, rax
0x14000f7c9  jz      loc_14000F8E4
0x14000f7cf  xor     ebx, ebx
0x14000f7d1  lea     rax, [rbp+57h+var_7C]
0x14000f7d5  mov     r9, rdi; KeyValueInformation
0x14000f7d8  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x14000f7dd  xor     r8d, r8d; KeyValueInformationClass
0x14000f7e0  xor     edx, edx; Index
0x14000f7e2  mov     [rsp+0B0h+Length], r14d; int
0x14000f7e7  mov     rcx, r15; KeyHandle
0x14000f7ea  call    cs:__imp_ZwEnumerateValueKey
0x14000f7f1  nop     dword ptr [rax+rax+00h]
0x14000f7f6  mov     esi, eax
0x14000f7f8  cmp     eax, 80000005h
0x14000f7fd  jz      loc_14000F89F
0x14000f803  cmp     eax, 0C0000023h
0x14000f808  jz      loc_14000F89F
0x14000f80e  test    eax, eax
0x14000f810  js      loc_14000F899
0x14000f816  movzx   eax, word ptr [rdi+8]
0x14000f81a  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000f81e  mov     [rbp+57h+ValueName.Length], ax
0x14000f822  mov     rcx, r15; KeyHandle
0x14000f825  movzx   eax, word ptr [rdi+8]
0x14000f829  mov     [rbp+57h+ValueName.MaximumLength], ax
0x14000f82d  lea     rax, [rdi+0Ch]
0x14000f831  mov     [rbp+57h+ValueName.Buffer], rax
0x14000f835  call    cs:__imp_ZwDeleteValueKey
0x14000f83c  nop     dword ptr [rax+rax+00h]
0x14000f841  mov     ebx, eax
0x14000f843  test    eax, eax
0x14000f845  jns     short loc_14000F7D1
0x14000f847  mov     eax, cs:dword_140019000
0x14000f84d  cmp     eax, 3
0x14000f850  jbe     short loc_14000F87A
0x14000f852  lea     rax, [rbp+57h+var_80]
0x14000f856  mov     [rbp+57h+var_48], rax
0x14000f85a  lea     rax, [rbp+57h+var_68]
0x14000f85e  mov     [rsp+0B0h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000f863  lea     rdx, byte_140016D91; int
0x14000f86a  mov     [rbp+57h+var_80], ebx
0x14000f86d  mov     [rbp+57h+var_40], 4
0x14000f875  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f87a  test    rdi, rdi
0x14000f87d  jz      loc_14000F91E
0x14000f883  xor     edx, edx; Tag
0x14000f885  mov     rcx, rdi; P
0x14000f888  call    cs:__imp_ExFreePoolWithTag
0x14000f88f  nop     dword ptr [rax+rax+00h]
0x14000f894  jmp     loc_14000F91E
0x14000f899  test    ebx, ebx
0x14000f89b  js      short loc_14000F847
0x14000f89d  jmp     short loc_14000F8D6
0x14000f89f  xor     edx, edx; Tag
0x14000f8a1  mov     rcx, rdi; P
0x14000f8a4  call    cs:__imp_ExFreePoolWithTag
0x14000f8ab  nop     dword ptr [rax+rax+00h]
0x14000f8b0  mov     r14d, [rbp+57h+var_7C]
0x14000f8b4  mov     ecx, 100h
0x14000f8b9  mov     edx, r14d
0x14000f8bc  mov     r8d, 56736642h
0x14000f8c2  call    cs:__imp_ExAllocatePool2
0x14000f8c9  nop     dword ptr [rax+rax+00h]
0x14000f8ce  mov     rdi, rax
0x14000f8d1  test    rax, rax
0x14000f8d4  jz      short loc_14000F8E4
0x14000f8d6  cmp     esi, 8000001Ah
0x14000f8dc  jnz     loc_14000F7D1
0x14000f8e2  jmp     short loc_14000F87A
0x14000f8e4  mov     eax, cs:dword_140019000
0x14000f8ea  mov     ecx, 0C0000017h; int
0x14000f8ef  mov     ebx, ecx
0x14000f8f1  cmp     eax, 3
0x14000f8f4  jbe     short loc_14000F91E
0x14000f8f6  lea     rax, [rbp+57h+var_80]
0x14000f8fa  mov     [rbp+57h+var_48], rax
0x14000f8fe  lea     rax, [rbp+57h+var_68]
0x14000f902  mov     [rsp+0B0h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000f907  lea     rdx, byte_140016D91; int
0x14000f90e  mov     [rbp+57h+var_80], ecx
0x14000f911  mov     [rbp+57h+var_40], 4
0x14000f919  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f91e  mov     eax, ebx
0x14000f920  mov     rcx, [rbp+57h+var_38]
0x14000f924  xor     rcx, rsp; StackCookie
0x14000f927  call    __security_check_cookie
0x14000f92c  add     rsp, 88h
0x14000f933  pop     r15
0x14000f935  pop     r14
0x14000f937  pop     rdi
0x14000f938  pop     rsi
0x14000f939  pop     rbx
0x14000f93a  pop     rbp
0x14000f93b  retn
```
