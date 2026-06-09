# BfsUpdateGlobalFilePolicy

- ea: `0x14000d848`
- end: `0x14000dad6`
- name: `BfsUpdateGlobalFilePolicy`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14000bf64`

## callees

- `0x140001008`
- `0x140001bc0`
- `0x14000c8cc`
- `0x14000d848`
- `0x140012b68`
- `0x140012bc8`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x14000d99a`
- `ntoskrnl!RtlCopySid` at `0x14000da03`
- `ntoskrnl!RtlCopySid` at `0x14000d99a`
- `ntoskrnl!RtlCopySid` at `0x14000da03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da67`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da67`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000da8f`
- `ntoskrnl!ExAllocatePool2` at `0x14000d8e8`
- `ntoskrnl!ExAllocatePool2` at `0x14000d955`
- `ntoskrnl!ExAllocatePool2` at `0x14000d9d8`
- `ntoskrnl!ExAllocatePool2` at `0x14000d8e8`
- `ntoskrnl!ExAllocatePool2` at `0x14000d955`
- `ntoskrnl!ExAllocatePool2` at `0x14000d9d8`

## pseudocode

```c
__int64 __fastcall BfsUpdateGlobalFilePolicy(__int64 a1, __int64 a2, unsigned __int8 *a3, unsigned __int8 *a4)
{
  __int64 v4; // r12
  int v6; // edx
  __int64 v10; // r13
  _QWORD *GlobalFilePolicy; // rdi
  int v12; // r8d
  int v13; // r9d
  NTSTATUS inserted; // ebx
  void *Pool2; // rax
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  NTSTATUS v19; // eax
  void *v20; // rax
  void *v21; // rcx
  void *v22; // rcx
  int v24; // [rsp+20h] [rbp-58h]
  __int64 v25; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v27; // [rsp+58h] [rbp-20h]
  __int64 v28; // [rsp+60h] [rbp-18h]

  v4 = *(_QWORD *)(a2 + 88);
  v6 = a3[1];
  v25 = 0;
  BfsUpdateHash(a3, (unsigned int)(4 * v6 + 8), &v25);
  BfsUpdateHash(a4, 4 * (unsigned int)a4[1] + 8, &v25);
  v10 = BfsFinalHash(&v25);
  GlobalFilePolicy = (_QWORD *)BfsGetGlobalFilePolicy(a2, a3, a4);
  if ( !GlobalFilePolicy )
  {
    GlobalFilePolicy = (_QWORD *)ExAllocatePool2(256, 48, 1198745154);
    if ( !GlobalFilePolicy )
    {
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v25) = -1073741801;
        v27 = &v25;
        v28 = 4;
        tlgWriteTransfer_EtwWriteTransfer(-1073741801, (int)&byte_140016D91, v12, v13, v24, &v26);
      }
      return (unsigned int)inserted;
    }
    Pool2 = (void *)ExAllocatePool2(256, 4LL * a3[1] + 8, 1400071746);
    GlobalFilePolicy[3] = Pool2;
    if ( !Pool2 )
      goto LABEL_6;
    v19 = RtlCopySid(4 * a3[1] + 8, Pool2, a3);
    inserted = v19;
    if ( v19 < 0 )
    {
      v18 = dword_140019000;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v25) = v19;
        goto LABEL_16;
      }
LABEL_17:
      v21 = (void *)GlobalFilePolicy[3];
      if ( v21 )
        ExFreePoolWithTag(v21, 0);
      v22 = (void *)GlobalFilePolicy[4];
      if ( v22 )
        ExFreePoolWithTag(v22, 0);
      ExFreePoolWithTag(GlobalFilePolicy, 0);
      return (unsigned int)inserted;
    }
    v20 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
    GlobalFilePolicy[4] = v20;
    if ( !v20 )
    {
LABEL_6:
      v18 = -1073741801;
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v25) = -1073741801;
LABEL_16:
        v28 = 4;
        v27 = &v25;
        tlgWriteTransfer_EtwWriteTransfer(v18, (int)&byte_140016D91, v16, v17, v24, &v26);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    inserted = RtlCopySid(4 * a4[1] + 8, v20, a4);
    if ( inserted < 0 || (inserted = BfsInsertEntryHashTable(v4, v10, GlobalFilePolicy), inserted < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v25) = inserted;
        goto LABEL_16;
      }
      goto LABEL_17;
    }
  }
  if ( *(_QWORD *)(a1 + 64) != -1 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 64));
    GlobalFilePolicy[5] = *(_QWORD *)(a1 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d848  push    rbp
0x14000d84a  push    rbx
0x14000d84b  push    rsi
0x14000d84c  push    rdi
0x14000d84d  push    r12
0x14000d84f  push    r13
0x14000d851  push    r14
0x14000d853  push    r15
0x14000d855  mov     rbp, rsp
0x14000d858  sub     rsp, 78h
0x14000d85c  mov     rax, cs:__security_cookie
0x14000d863  xor     rax, rsp
0x14000d866  mov     [rbp+var_10], rax
0x14000d86a  mov     r12, [rdx+58h]
0x14000d86e  mov     rbx, rdx
0x14000d871  movzx   edx, byte ptr [r8+1]
0x14000d876  mov     r15, r8
0x14000d879  mov     rsi, rcx
0x14000d87c  mov     [rbp+var_48], 0
0x14000d884  lea     r8, [rbp+var_48]
0x14000d888  mov     rcx, r15
0x14000d88b  mov     r14, r9
0x14000d88e  lea     edx, ds:8[rdx*4]
0x14000d895  call    BfsUpdateHash
0x14000d89a  movzx   edx, byte ptr [r14+1]
0x14000d89f  lea     r8, [rbp+var_48]
0x14000d8a3  mov     rcx, r14
0x14000d8a6  lea     edx, ds:8[rdx*4]
0x14000d8ad  call    BfsUpdateHash
0x14000d8b2  lea     rcx, [rbp+var_48]
0x14000d8b6  call    BfsFinalHash
0x14000d8bb  mov     r8, r14
0x14000d8be  mov     rdx, r15
0x14000d8c1  mov     rcx, rbx
0x14000d8c4  mov     r13, rax
0x14000d8c7  call    BfsGetGlobalFilePolicy
0x14000d8cc  mov     rdi, rax
0x14000d8cf  test    rax, rax
0x14000d8d2  jnz     loc_14000DA9D
0x14000d8d8  mov     ebx, 100h
0x14000d8dd  lea     edx, [rax+30h]
0x14000d8e0  mov     ecx, ebx
0x14000d8e2  mov     r8d, 47736642h
0x14000d8e8  call    cs:__imp_ExAllocatePool2
0x14000d8ef  nop     dword ptr [rax+rax+00h]
0x14000d8f4  mov     rdi, rax
0x14000d8f7  test    rax, rax
0x14000d8fa  jnz     short loc_14000D93F
0x14000d8fc  mov     eax, cs:dword_140019000
0x14000d902  mov     ecx, 0C0000017h; int
0x14000d907  mov     ebx, ecx
0x14000d909  cmp     eax, 3
0x14000d90c  jbe     loc_14000DAB6
0x14000d912  lea     rax, [rbp+var_48]
0x14000d916  mov     dword ptr [rbp+var_48], ecx
0x14000d919  mov     [rbp+var_20], rax
0x14000d91d  lea     rdx, byte_140016D91; int
0x14000d924  lea     rax, [rbp+var_40]
0x14000d928  mov     [rbp+var_18], 4
0x14000d930  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x14000d935  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d93a  jmp     loc_14000DAB6
0x14000d93f  movzx   edx, byte ptr [r15+1]
0x14000d944  mov     r8d, 53736642h
0x14000d94a  mov     rcx, rbx
0x14000d94d  lea     rdx, ds:8[rdx*4]
0x14000d955  call    cs:__imp_ExAllocatePool2
0x14000d95c  nop     dword ptr [rax+rax+00h]
0x14000d961  mov     [rdi+18h], rax
0x14000d965  test    rax, rax
0x14000d968  jnz     short loc_14000D988
0x14000d96a  mov     eax, cs:dword_140019000
0x14000d970  mov     ecx, 0C0000017h
0x14000d975  mov     ebx, ecx
0x14000d977  cmp     eax, 3
0x14000d97a  jbe     loc_14000DA5C
0x14000d980  mov     dword ptr [rbp+var_48], ecx
0x14000d983  jmp     loc_14000DA37
0x14000d988  movzx   ecx, byte ptr [r15+1]
0x14000d98d  mov     r8, r15; SourceSid
0x14000d990  mov     rdx, rax; DestinationSid
0x14000d993  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000d99a  call    cs:__imp_RtlCopySid
0x14000d9a1  nop     dword ptr [rax+rax+00h]
0x14000d9a6  mov     ebx, eax
0x14000d9a8  test    eax, eax
0x14000d9aa  jns     short loc_14000D9C0
0x14000d9ac  mov     ecx, cs:dword_140019000
0x14000d9b2  cmp     ecx, 3
0x14000d9b5  jbe     loc_14000DA5C
0x14000d9bb  mov     dword ptr [rbp+var_48], eax
0x14000d9be  jmp     short loc_14000DA37
0x14000d9c0  movzx   edx, byte ptr [r14+1]
0x14000d9c5  mov     ecx, 100h
0x14000d9ca  mov     r8d, 53736642h
0x14000d9d0  lea     rdx, ds:8[rdx*4]
0x14000d9d8  call    cs:__imp_ExAllocatePool2
0x14000d9df  nop     dword ptr [rax+rax+00h]
0x14000d9e4  mov     [rdi+20h], rax
0x14000d9e8  test    rax, rax
0x14000d9eb  jz      loc_14000D96A
0x14000d9f1  movzx   ecx, byte ptr [r14+1]
0x14000d9f6  mov     r8, r14; SourceSid
0x14000d9f9  mov     rdx, rax; DestinationSid
0x14000d9fc  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000da03  call    cs:__imp_RtlCopySid
0x14000da0a  nop     dword ptr [rax+rax+00h]
0x14000da0f  mov     ebx, eax
0x14000da11  test    eax, eax
0x14000da13  js      short loc_14000DA29
0x14000da15  mov     r8, rdi
0x14000da18  mov     rdx, r13
0x14000da1b  mov     rcx, r12
0x14000da1e  call    BfsInsertEntryHashTable
0x14000da23  mov     ebx, eax
0x14000da25  test    eax, eax
0x14000da27  jns     short loc_14000DA9D
0x14000da29  mov     eax, cs:dword_140019000
0x14000da2f  cmp     eax, 3
0x14000da32  jbe     short loc_14000DA5C
0x14000da34  mov     dword ptr [rbp+var_48], ebx
0x14000da37  lea     rax, [rbp+var_48]
0x14000da3b  mov     [rbp+var_18], 4
0x14000da43  mov     [rbp+var_20], rax
0x14000da47  lea     rdx, byte_140016D91; int
0x14000da4e  lea     rax, [rbp+var_40]
0x14000da52  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x14000da57  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000da5c  mov     rcx, [rdi+18h]; P
0x14000da60  test    rcx, rcx
0x14000da63  jz      short loc_14000DA73
0x14000da65  xor     edx, edx; Tag
0x14000da67  call    cs:__imp_ExFreePoolWithTag
0x14000da6e  nop     dword ptr [rax+rax+00h]
0x14000da73  mov     rcx, [rdi+20h]; P
0x14000da77  test    rcx, rcx
0x14000da7a  jz      short loc_14000DA8A
0x14000da7c  xor     edx, edx; Tag
0x14000da7e  call    cs:__imp_ExFreePoolWithTag
0x14000da85  nop     dword ptr [rax+rax+00h]
0x14000da8a  xor     edx, edx; Tag
0x14000da8c  mov     rcx, rdi; P
0x14000da8f  call    cs:__imp_ExFreePoolWithTag
0x14000da96  nop     dword ptr [rax+rax+00h]
0x14000da9b  jmp     short loc_14000DAB6
0x14000da9d  mov     rax, [rsi+40h]
0x14000daa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000daa5  jz      short loc_14000DAB4
0x14000daa7  lock inc qword ptr [rsi+40h]
0x14000daac  mov     rax, [rsi+40h]
0x14000dab0  mov     [rdi+28h], rax
0x14000dab4  xor     ebx, ebx
0x14000dab6  mov     eax, ebx
0x14000dab8  mov     rcx, [rbp+var_10]
0x14000dabc  xor     rcx, rsp; StackCookie
0x14000dabf  call    __security_check_cookie
0x14000dac4  add     rsp, 78h
0x14000dac8  pop     r15
0x14000daca  pop     r14
0x14000dacc  pop     r13
0x14000dace  pop     r12
0x14000dad0  pop     rdi
0x14000dad1  pop     rsi
0x14000dad2  pop     rbx
0x14000dad3  pop     rbp
0x14000dad4  retn
```
