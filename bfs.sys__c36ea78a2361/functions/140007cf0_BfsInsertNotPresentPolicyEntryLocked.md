# BfsInsertNotPresentPolicyEntryLocked

- ea: `0x140007cf0`
- end: `0x140007fe3`
- name: `BfsInsertNotPresentPolicyEntryLocked`
- size: `755`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400092a4`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x140007cf0`
- `0x140008e38`
- `0x140012ca0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140007f36`
- `ntoskrnl!KeInitializeEvent` at `0x140007f36`
- `ntoskrnl!RtlCopySid` at `0x140007e32`
- `ntoskrnl!RtlCopySid` at `0x140007e69`
- `ntoskrnl!RtlCopySid` at `0x140007e32`
- `ntoskrnl!RtlCopySid` at `0x140007e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007fb9`
- `ntoskrnl!ExAllocatePool2` at `0x140007d5e`
- `ntoskrnl!ExAllocatePool2` at `0x140007dca`
- `ntoskrnl!ExAllocatePool2` at `0x140007ea0`
- `ntoskrnl!ExAllocatePool2` at `0x140007ed7`
- `ntoskrnl!ExAllocatePool2` at `0x140007d5e`
- `ntoskrnl!ExAllocatePool2` at `0x140007dca`
- `ntoskrnl!ExAllocatePool2` at `0x140007ea0`
- `ntoskrnl!ExAllocatePool2` at `0x140007ed7`

## pseudocode

```c
__int64 __fastcall BfsInsertNotPresentPolicyEntryLocked(
        __int64 a1,
        ULONG_PTR a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rdx
  __int64 result; // rax
  __int64 v10; // rcx
  void *Pool2; // rdi
  __int64 v12; // r8
  __int64 v13; // r9
  int inserted; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  void *v17; // r14
  __int64 v18; // rcx
  bool v19; // cc
  NTSTATUS v20; // eax
  __int64 v21; // rax
  __int64 v22; // rsi
  struct _KEVENT *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // [rsp+20h] [rbp-50h]
  int v28; // [rsp+30h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+38h] [rbp-38h] BYREF
  int *v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]

  v8 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), a2, a3, a4);
  if ( !v8 )
  {
    Pool2 = (void *)ExAllocatePool2(256, 4LL * a3[1] + 8, 1400071746);
    if ( !Pool2 )
    {
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v28 = -1073741801;
        v30 = &v28;
        v31 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v10, (unsigned __int8 *)&byte_140016D91, v12, v13, v27, &v29);
      }
      return (unsigned int)inserted;
    }
    v17 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
    if ( !v17 )
    {
      v18 = (unsigned int)dword_140019000;
      v19 = (unsigned int)dword_140019000 <= 3;
LABEL_10:
      inserted = -1073741801;
      if ( v19 )
      {
LABEL_29:
        ExFreePoolWithTag(Pool2, 0);
LABEL_30:
        if ( v17 )
          ExFreePoolWithTag(v17, 0);
        return (unsigned int)inserted;
      }
      v28 = -1073741801;
LABEL_12:
      v31 = 4;
      v30 = &v28;
      tlgWriteTransfer_EtwWriteTransfer(v18, (unsigned __int8 *)&byte_140016D91, v15, v16, v27, &v29);
      goto LABEL_29;
    }
    v20 = RtlCopySid(4 * a3[1] + 8, Pool2, a3);
    inserted = v20;
    if ( v20 < 0 )
    {
      v18 = (unsigned int)dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_29;
      v28 = v20;
      goto LABEL_12;
    }
    inserted = RtlCopySid(4 * a4[1] + 8, v17, a4);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_29;
      v28 = inserted;
      goto LABEL_12;
    }
    v21 = ExAllocatePool2(256, 152, 1165190722);
    v22 = v21;
    if ( !v21 )
    {
      v19 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_10;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 144));
    v23 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306);
    *(_QWORD *)(v22 + 40) = v23;
    if ( v23 )
    {
      *(_QWORD *)(v22 + 24) = Pool2;
      *(_QWORD *)(v22 + 32) = v17;
      *(_DWORD *)(v22 + 56) = 2;
      *(_DWORD *)(v22 + 104) = 0;
      *(_OWORD *)(v22 + 112) = 0;
      *(_OWORD *)(v22 + 128) = 0;
      KeInitializeEvent(v23, NotificationEvent, 0);
      inserted = BfsInsertEntryHashTable(
                   *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8),
                   a2,
                   (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)v22);
      if ( inserted >= 0 )
        return (unsigned int)inserted;
      Pool2 = 0;
      v17 = 0;
      if ( (unsigned int)dword_140019000 <= 3 )
      {
LABEL_28:
        BfsDereferencePolicyEntryEx((char *)v22, 1);
        if ( !Pool2 )
          goto LABEL_30;
        goto LABEL_29;
      }
      v28 = inserted;
    }
    else
    {
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_28;
      v28 = -1073741801;
    }
    v31 = 4;
    v30 = &v28;
    tlgWriteTransfer_EtwWriteTransfer(v24, (unsigned __int8 *)&byte_140016D91, v25, v26, v27, &v29);
    goto LABEL_28;
  }
  result = 0x40000000;
  if ( LODWORD(v8[2].Linkage.Blink) != 0x10000000 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140007cf0  push    rbp
0x140007cf2  push    rbx
0x140007cf3  push    rsi
0x140007cf4  push    rdi
0x140007cf5  push    r12
0x140007cf7  push    r14
0x140007cf9  push    r15
0x140007cfb  mov     rbp, rsp
0x140007cfe  sub     rsp, 70h
0x140007d02  mov     rax, cs:__security_cookie
0x140007d09  xor     rax, rsp
0x140007d0c  mov     [rbp+var_8], rax
0x140007d10  mov     r15, rcx
0x140007d13  mov     rsi, r9
0x140007d16  mov     rcx, [rcx+8]; HashTable
0x140007d1a  mov     rbx, r8
0x140007d1d  mov     r12, rdx
0x140007d20  call    BfsLookupPolicyEntryHashTable
0x140007d25  mov     rdx, rax
0x140007d28  test    rax, rax
0x140007d2b  jz      short loc_140007D43
0x140007d2d  xor     ecx, ecx
0x140007d2f  mov     eax, 40000000h
0x140007d34  cmp     dword ptr [rdx+38h], 10000000h
0x140007d3b  cmovnz  eax, ecx
0x140007d3e  jmp     loc_140007FC7
0x140007d43  movzx   edx, byte ptr [rbx+1]
0x140007d47  mov     r14d, 100h
0x140007d4d  mov     r8d, 53736642h
0x140007d53  mov     ecx, r14d
0x140007d56  lea     rdx, ds:8[rdx*4]
0x140007d5e  call    cs:__imp_ExAllocatePool2
0x140007d65  nop     dword ptr [rax+rax+00h]
0x140007d6a  mov     rdi, rax
0x140007d6d  test    rax, rax
0x140007d70  jnz     short loc_140007DB5
0x140007d72  mov     eax, cs:dword_140019000
0x140007d78  mov     edx, 0C0000017h
0x140007d7d  mov     ebx, edx
0x140007d7f  cmp     eax, 3
0x140007d82  jbe     loc_140007FC5
0x140007d88  lea     rax, [rbp+var_40]
0x140007d8c  mov     [rbp+var_40], edx
0x140007d8f  mov     [rbp+var_18], rax
0x140007d93  lea     rdx, byte_140016D91; int
0x140007d9a  lea     rax, [rbp+var_38]
0x140007d9e  mov     [rbp+var_10], 4
0x140007da6  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007dab  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007db0  jmp     loc_140007FC5
0x140007db5  movzx   edx, byte ptr [rsi+1]
0x140007db9  mov     r8d, 53736642h
0x140007dbf  mov     rcx, r14
0x140007dc2  lea     rdx, ds:8[rdx*4]
0x140007dca  call    cs:__imp_ExAllocatePool2
0x140007dd1  nop     dword ptr [rax+rax+00h]
0x140007dd6  mov     r14, rax
0x140007dd9  test    rax, rax
0x140007ddc  jnz     short loc_140007E21
0x140007dde  mov     ecx, cs:dword_140019000; int
0x140007de4  cmp     ecx, 3
0x140007de7  mov     edx, 0C0000017h
0x140007dec  mov     ebx, edx
0x140007dee  jbe     loc_140007F9E
0x140007df4  mov     [rbp+var_40], edx
0x140007df7  lea     rax, [rbp+var_40]
0x140007dfb  mov     [rbp+var_10], 4
0x140007e03  mov     [rbp+var_18], rax
0x140007e07  lea     rdx, byte_140016D91; int
0x140007e0e  lea     rax, [rbp+var_38]
0x140007e12  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007e17  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007e1c  jmp     loc_140007F9E
0x140007e21  movzx   ecx, byte ptr [rbx+1]
0x140007e25  mov     r8, rbx; SourceSid
0x140007e28  mov     rdx, rdi; DestinationSid
0x140007e2b  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007e32  call    cs:__imp_RtlCopySid
0x140007e39  nop     dword ptr [rax+rax+00h]
0x140007e3e  mov     ebx, eax
0x140007e40  test    eax, eax
0x140007e42  jns     short loc_140007E58
0x140007e44  mov     ecx, cs:dword_140019000
0x140007e4a  cmp     ecx, 3
0x140007e4d  jbe     loc_140007F9E
0x140007e53  mov     [rbp+var_40], eax
0x140007e56  jmp     short loc_140007DF7
0x140007e58  movzx   ecx, byte ptr [rsi+1]
0x140007e5c  mov     r8, rsi; SourceSid
0x140007e5f  mov     rdx, r14; DestinationSid
0x140007e62  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007e69  call    cs:__imp_RtlCopySid
0x140007e70  nop     dword ptr [rax+rax+00h]
0x140007e75  mov     ebx, eax
0x140007e77  test    eax, eax
0x140007e79  jns     short loc_140007E92
0x140007e7b  mov     eax, cs:dword_140019000
0x140007e81  cmp     eax, 3
0x140007e84  jbe     loc_140007F9E
0x140007e8a  mov     [rbp+var_40], ebx
0x140007e8d  jmp     loc_140007DF7
0x140007e92  mov     edx, 98h
0x140007e97  mov     r8d, 45736642h
0x140007e9d  lea     ecx, [rdx+68h]
0x140007ea0  call    cs:__imp_ExAllocatePool2
0x140007ea7  nop     dword ptr [rax+rax+00h]
0x140007eac  mov     rsi, rax
0x140007eaf  test    rax, rax
0x140007eb2  jnz     short loc_140007EC2
0x140007eb4  mov     eax, cs:dword_140019000
0x140007eba  cmp     eax, 3
0x140007ebd  jmp     loc_140007DE7
0x140007ec2  lock inc dword ptr [rax+90h]
0x140007ec9  mov     edx, 18h
0x140007ece  mov     r8d, 76736642h
0x140007ed4  lea     ecx, [rdx+28h]
0x140007ed7  call    cs:__imp_ExAllocatePool2
0x140007ede  nop     dword ptr [rax+rax+00h]
0x140007ee3  mov     [rsi+28h], rax
0x140007ee7  test    rax, rax
0x140007eea  jnz     short loc_140007F07
0x140007eec  mov     eax, cs:dword_140019000
0x140007ef2  mov     edx, 0C0000017h
0x140007ef7  mov     ebx, edx
0x140007ef9  cmp     eax, 3
0x140007efc  jbe     loc_140007F8F
0x140007f02  mov     [rbp+var_40], edx
0x140007f05  jmp     short loc_140007F6A
0x140007f07  mov     [rsi+18h], rdi
0x140007f0b  xorps   xmm0, xmm0
0x140007f0e  mov     [rsi+20h], r14
0x140007f12  xorps   xmm1, xmm1
0x140007f15  mov     dword ptr [rsi+38h], 2
0x140007f1c  xor     r8d, r8d; State
0x140007f1f  mov     dword ptr [rsi+68h], 0
0x140007f26  xor     edx, edx; Type
0x140007f28  movups  xmmword ptr [rsi+70h], xmm0
0x140007f2c  mov     rcx, rax; Event
0x140007f2f  movups  xmmword ptr [rsi+80h], xmm1
0x140007f36  call    cs:__imp_KeInitializeEvent
0x140007f3d  nop     dword ptr [rax+rax+00h]
0x140007f42  mov     rcx, [r15+8]
0x140007f46  mov     r8, rsi
0x140007f49  mov     rdx, r12
0x140007f4c  call    BfsInsertEntryHashTable
0x140007f51  mov     ebx, eax
0x140007f53  test    eax, eax
0x140007f55  jns     short loc_140007FC5
0x140007f57  mov     eax, cs:dword_140019000
0x140007f5d  xor     edi, edi
0x140007f5f  xor     r14d, r14d
0x140007f62  cmp     eax, 3
0x140007f65  jbe     short loc_140007F8F
0x140007f67  mov     [rbp+var_40], ebx
0x140007f6a  lea     rax, [rbp+var_40]
0x140007f6e  mov     [rbp+var_10], 4
0x140007f76  mov     [rbp+var_18], rax
0x140007f7a  lea     rdx, byte_140016D91; int
0x140007f81  lea     rax, [rbp+var_38]
0x140007f85  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007f8a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007f8f  mov     dl, 1
0x140007f91  mov     rcx, rsi; P
0x140007f94  call    BfsDereferencePolicyEntryEx
0x140007f99  test    rdi, rdi
0x140007f9c  jz      short loc_140007FAF
0x140007f9e  xor     edx, edx; Tag
0x140007fa0  mov     rcx, rdi; P
0x140007fa3  call    cs:__imp_ExFreePoolWithTag
0x140007faa  nop     dword ptr [rax+rax+00h]
0x140007faf  test    r14, r14
0x140007fb2  jz      short loc_140007FC5
0x140007fb4  xor     edx, edx; Tag
0x140007fb6  mov     rcx, r14; P
0x140007fb9  call    cs:__imp_ExFreePoolWithTag
0x140007fc0  nop     dword ptr [rax+rax+00h]
0x140007fc5  mov     eax, ebx
0x140007fc7  mov     rcx, [rbp+var_8]
0x140007fcb  xor     rcx, rsp; StackCookie
0x140007fce  call    __security_check_cookie
0x140007fd3  add     rsp, 70h
0x140007fd7  pop     r15
0x140007fd9  pop     r14
0x140007fdb  pop     r12
0x140007fdd  pop     rdi
0x140007fde  pop     rsi
0x140007fdf  pop     rbx
0x140007fe0  pop     rbp
0x140007fe1  retn
```
