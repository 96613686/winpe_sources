# BfsInsertNotPresentPolicyEntryLocked

- ea: `0x140007b60`
- end: `0x140007e53`
- name: `BfsInsertNotPresentPolicyEntryLocked`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009114`

## callees

- `0x140001008`
- `0x140006040`
- `0x140007b60`
- `0x140008ca8`
- `0x140012b68`
- `0x140013730`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140007da6`
- `ntoskrnl!KeInitializeEvent` at `0x140007da6`
- `ntoskrnl!RtlCopySid` at `0x140007ca2`
- `ntoskrnl!RtlCopySid` at `0x140007cd9`
- `ntoskrnl!RtlCopySid` at `0x140007ca2`
- `ntoskrnl!RtlCopySid` at `0x140007cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007e29`
- `ntoskrnl!ExAllocatePool2` at `0x140007bce`
- `ntoskrnl!ExAllocatePool2` at `0x140007c3a`
- `ntoskrnl!ExAllocatePool2` at `0x140007d10`
- `ntoskrnl!ExAllocatePool2` at `0x140007d47`
- `ntoskrnl!ExAllocatePool2` at `0x140007bce`
- `ntoskrnl!ExAllocatePool2` at `0x140007c3a`
- `ntoskrnl!ExAllocatePool2` at `0x140007d10`
- `ntoskrnl!ExAllocatePool2` at `0x140007d47`

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
  int v10; // ecx
  void *Pool2; // rdi
  int v12; // r8d
  int v13; // r9d
  NTSTATUS inserted; // ebx
  int v15; // r8d
  int v16; // r9d
  void *v17; // r14
  int v18; // ecx
  bool v19; // cc
  NTSTATUS v20; // eax
  __int64 v21; // rax
  __int64 v22; // rsi
  struct _KEVENT *v23; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
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
        tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v12, v13, v27, &v29);
      }
      return (unsigned int)inserted;
    }
    v17 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
    if ( !v17 )
    {
      v18 = dword_140019000;
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
      tlgWriteTransfer_EtwWriteTransfer(v18, (int)&byte_140016D91, v15, v16, v27, &v29);
      goto LABEL_29;
    }
    v20 = RtlCopySid(4 * a3[1] + 8, Pool2, a3);
    inserted = v20;
    if ( v20 < 0 )
    {
      v18 = dword_140019000;
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
      inserted = BfsInsertEntryHashTable(*(_QWORD *)(a1 + 8), a2, v22);
      if ( inserted >= 0 )
        return (unsigned int)inserted;
      Pool2 = 0;
      v17 = 0;
      if ( (unsigned int)dword_140019000 <= 3 )
      {
LABEL_28:
        BfsDereferencePolicyEntryEx((PVOID)v22);
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
    tlgWriteTransfer_EtwWriteTransfer(v24, (int)&byte_140016D91, v25, v26, v27, &v29);
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
0x140007b60  push    rbp
0x140007b62  push    rbx
0x140007b63  push    rsi
0x140007b64  push    rdi
0x140007b65  push    r12
0x140007b67  push    r14
0x140007b69  push    r15
0x140007b6b  mov     rbp, rsp
0x140007b6e  sub     rsp, 70h
0x140007b72  mov     rax, cs:__security_cookie
0x140007b79  xor     rax, rsp
0x140007b7c  mov     [rbp+var_8], rax
0x140007b80  mov     r15, rcx
0x140007b83  mov     rsi, r9
0x140007b86  mov     rcx, [rcx+8]; HashTable
0x140007b8a  mov     rbx, r8
0x140007b8d  mov     r12, rdx
0x140007b90  call    BfsLookupPolicyEntryHashTable
0x140007b95  mov     rdx, rax
0x140007b98  test    rax, rax
0x140007b9b  jz      short loc_140007BB3
0x140007b9d  xor     ecx, ecx
0x140007b9f  mov     eax, 40000000h
0x140007ba4  cmp     dword ptr [rdx+38h], 10000000h
0x140007bab  cmovnz  eax, ecx
0x140007bae  jmp     loc_140007E37
0x140007bb3  movzx   edx, byte ptr [rbx+1]
0x140007bb7  mov     r14d, 100h
0x140007bbd  mov     r8d, 53736642h
0x140007bc3  mov     ecx, r14d
0x140007bc6  lea     rdx, ds:8[rdx*4]
0x140007bce  call    cs:__imp_ExAllocatePool2
0x140007bd5  nop     dword ptr [rax+rax+00h]
0x140007bda  mov     rdi, rax
0x140007bdd  test    rax, rax
0x140007be0  jnz     short loc_140007C25
0x140007be2  mov     eax, cs:dword_140019000
0x140007be8  mov     edx, 0C0000017h
0x140007bed  mov     ebx, edx
0x140007bef  cmp     eax, 3
0x140007bf2  jbe     loc_140007E35
0x140007bf8  lea     rax, [rbp+var_40]
0x140007bfc  mov     [rbp+var_40], edx
0x140007bff  mov     [rbp+var_18], rax
0x140007c03  lea     rdx, byte_140016D91; int
0x140007c0a  lea     rax, [rbp+var_38]
0x140007c0e  mov     [rbp+var_10], 4
0x140007c16  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007c1b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007c20  jmp     loc_140007E35
0x140007c25  movzx   edx, byte ptr [rsi+1]
0x140007c29  mov     r8d, 53736642h
0x140007c2f  mov     rcx, r14
0x140007c32  lea     rdx, ds:8[rdx*4]
0x140007c3a  call    cs:__imp_ExAllocatePool2
0x140007c41  nop     dword ptr [rax+rax+00h]
0x140007c46  mov     r14, rax
0x140007c49  test    rax, rax
0x140007c4c  jnz     short loc_140007C91
0x140007c4e  mov     ecx, cs:dword_140019000; int
0x140007c54  cmp     ecx, 3
0x140007c57  mov     edx, 0C0000017h
0x140007c5c  mov     ebx, edx
0x140007c5e  jbe     loc_140007E0E
0x140007c64  mov     [rbp+var_40], edx
0x140007c67  lea     rax, [rbp+var_40]
0x140007c6b  mov     [rbp+var_10], 4
0x140007c73  mov     [rbp+var_18], rax
0x140007c77  lea     rdx, byte_140016D91; int
0x140007c7e  lea     rax, [rbp+var_38]
0x140007c82  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007c87  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007c8c  jmp     loc_140007E0E
0x140007c91  movzx   ecx, byte ptr [rbx+1]
0x140007c95  mov     r8, rbx; SourceSid
0x140007c98  mov     rdx, rdi; DestinationSid
0x140007c9b  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007ca2  call    cs:__imp_RtlCopySid
0x140007ca9  nop     dword ptr [rax+rax+00h]
0x140007cae  mov     ebx, eax
0x140007cb0  test    eax, eax
0x140007cb2  jns     short loc_140007CC8
0x140007cb4  mov     ecx, cs:dword_140019000
0x140007cba  cmp     ecx, 3
0x140007cbd  jbe     loc_140007E0E
0x140007cc3  mov     [rbp+var_40], eax
0x140007cc6  jmp     short loc_140007C67
0x140007cc8  movzx   ecx, byte ptr [rsi+1]
0x140007ccc  mov     r8, rsi; SourceSid
0x140007ccf  mov     rdx, r14; DestinationSid
0x140007cd2  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140007cd9  call    cs:__imp_RtlCopySid
0x140007ce0  nop     dword ptr [rax+rax+00h]
0x140007ce5  mov     ebx, eax
0x140007ce7  test    eax, eax
0x140007ce9  jns     short loc_140007D02
0x140007ceb  mov     eax, cs:dword_140019000
0x140007cf1  cmp     eax, 3
0x140007cf4  jbe     loc_140007E0E
0x140007cfa  mov     [rbp+var_40], ebx
0x140007cfd  jmp     loc_140007C67
0x140007d02  mov     edx, 98h
0x140007d07  mov     r8d, 45736642h
0x140007d0d  lea     ecx, [rdx+68h]
0x140007d10  call    cs:__imp_ExAllocatePool2
0x140007d17  nop     dword ptr [rax+rax+00h]
0x140007d1c  mov     rsi, rax
0x140007d1f  test    rax, rax
0x140007d22  jnz     short loc_140007D32
0x140007d24  mov     eax, cs:dword_140019000
0x140007d2a  cmp     eax, 3
0x140007d2d  jmp     loc_140007C57
0x140007d32  lock inc dword ptr [rax+90h]
0x140007d39  mov     edx, 18h
0x140007d3e  mov     r8d, 76736642h
0x140007d44  lea     ecx, [rdx+28h]
0x140007d47  call    cs:__imp_ExAllocatePool2
0x140007d4e  nop     dword ptr [rax+rax+00h]
0x140007d53  mov     [rsi+28h], rax
0x140007d57  test    rax, rax
0x140007d5a  jnz     short loc_140007D77
0x140007d5c  mov     eax, cs:dword_140019000
0x140007d62  mov     edx, 0C0000017h
0x140007d67  mov     ebx, edx
0x140007d69  cmp     eax, 3
0x140007d6c  jbe     loc_140007DFF
0x140007d72  mov     [rbp+var_40], edx
0x140007d75  jmp     short loc_140007DDA
0x140007d77  mov     [rsi+18h], rdi
0x140007d7b  xorps   xmm0, xmm0
0x140007d7e  mov     [rsi+20h], r14
0x140007d82  xorps   xmm1, xmm1
0x140007d85  mov     dword ptr [rsi+38h], 2
0x140007d8c  xor     r8d, r8d; State
0x140007d8f  mov     dword ptr [rsi+68h], 0
0x140007d96  xor     edx, edx; Type
0x140007d98  movups  xmmword ptr [rsi+70h], xmm0
0x140007d9c  mov     rcx, rax; Event
0x140007d9f  movups  xmmword ptr [rsi+80h], xmm1
0x140007da6  call    cs:__imp_KeInitializeEvent
0x140007dad  nop     dword ptr [rax+rax+00h]
0x140007db2  mov     rcx, [r15+8]
0x140007db6  mov     r8, rsi
0x140007db9  mov     rdx, r12
0x140007dbc  call    BfsInsertEntryHashTable
0x140007dc1  mov     ebx, eax
0x140007dc3  test    eax, eax
0x140007dc5  jns     short loc_140007E35
0x140007dc7  mov     eax, cs:dword_140019000
0x140007dcd  xor     edi, edi
0x140007dcf  xor     r14d, r14d
0x140007dd2  cmp     eax, 3
0x140007dd5  jbe     short loc_140007DFF
0x140007dd7  mov     [rbp+var_40], ebx
0x140007dda  lea     rax, [rbp+var_40]
0x140007dde  mov     [rbp+var_10], 4
0x140007de6  mov     [rbp+var_18], rax
0x140007dea  lea     rdx, byte_140016D91; int
0x140007df1  lea     rax, [rbp+var_38]
0x140007df5  mov     [rsp+70h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x140007dfa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007dff  mov     dl, 1
0x140007e01  mov     rcx, rsi; P
0x140007e04  call    BfsDereferencePolicyEntryEx
0x140007e09  test    rdi, rdi
0x140007e0c  jz      short loc_140007E1F
0x140007e0e  xor     edx, edx; Tag
0x140007e10  mov     rcx, rdi; P
0x140007e13  call    cs:__imp_ExFreePoolWithTag
0x140007e1a  nop     dword ptr [rax+rax+00h]
0x140007e1f  test    r14, r14
0x140007e22  jz      short loc_140007E35
0x140007e24  xor     edx, edx; Tag
0x140007e26  mov     rcx, r14; P
0x140007e29  call    cs:__imp_ExFreePoolWithTag
0x140007e30  nop     dword ptr [rax+rax+00h]
0x140007e35  mov     eax, ebx
0x140007e37  mov     rcx, [rbp+var_8]
0x140007e3b  xor     rcx, rsp; StackCookie
0x140007e3e  call    __security_check_cookie
0x140007e43  add     rsp, 70h
0x140007e47  pop     r15
0x140007e49  pop     r14
0x140007e4b  pop     r12
0x140007e4d  pop     rdi
0x140007e4e  pop     rsi
0x140007e4f  pop     rbx
0x140007e50  pop     rbp
0x140007e51  retn
```
