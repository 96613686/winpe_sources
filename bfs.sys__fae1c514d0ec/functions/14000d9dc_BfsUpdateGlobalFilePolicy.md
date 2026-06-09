# BfsUpdateGlobalFilePolicy

- ea: `0x14000d9dc`
- end: `0x14000dc6a`
- name: `BfsUpdateGlobalFilePolicy`
- size: `654`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x14000c0f4`

## callees

- `0x140001008`
- `0x1400017b0`
- `0x14000ca5c`
- `0x14000d9dc`
- `0x140012ca0`
- `0x140012d00`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x14000db2e`
- `ntoskrnl!RtlCopySid` at `0x14000db97`
- `ntoskrnl!RtlCopySid` at `0x14000db2e`
- `ntoskrnl!RtlCopySid` at `0x14000db97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc23`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dbfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc12`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc23`
- `ntoskrnl!ExAllocatePool2` at `0x14000da7c`
- `ntoskrnl!ExAllocatePool2` at `0x14000dae9`
- `ntoskrnl!ExAllocatePool2` at `0x14000db6c`
- `ntoskrnl!ExAllocatePool2` at `0x14000da7c`
- `ntoskrnl!ExAllocatePool2` at `0x14000dae9`
- `ntoskrnl!ExAllocatePool2` at `0x14000db6c`

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
0x14000d9dc  push    rbp
0x14000d9de  push    rbx
0x14000d9df  push    rsi
0x14000d9e0  push    rdi
0x14000d9e1  push    r12
0x14000d9e3  push    r13
0x14000d9e5  push    r14
0x14000d9e7  push    r15
0x14000d9e9  mov     rbp, rsp
0x14000d9ec  sub     rsp, 78h
0x14000d9f0  mov     rax, cs:__security_cookie
0x14000d9f7  xor     rax, rsp
0x14000d9fa  mov     [rbp+var_10], rax
0x14000d9fe  mov     r12, [rdx+58h]
0x14000da02  mov     rbx, rdx
0x14000da05  movzx   edx, byte ptr [r8+1]
0x14000da0a  mov     r15, r8
0x14000da0d  mov     rsi, rcx
0x14000da10  mov     [rbp+var_48], 0
0x14000da18  lea     r8, [rbp+var_48]
0x14000da1c  mov     rcx, r15
0x14000da1f  mov     r14, r9
0x14000da22  lea     edx, ds:8[rdx*4]
0x14000da29  call    BfsUpdateHash
0x14000da2e  movzx   edx, byte ptr [r14+1]
0x14000da33  lea     r8, [rbp+var_48]
0x14000da37  mov     rcx, r14
0x14000da3a  lea     edx, ds:8[rdx*4]
0x14000da41  call    BfsUpdateHash
0x14000da46  lea     rcx, [rbp+var_48]
0x14000da4a  call    BfsFinalHash
0x14000da4f  mov     r8, r14
0x14000da52  mov     rdx, r15
0x14000da55  mov     rcx, rbx
0x14000da58  mov     r13, rax
0x14000da5b  call    BfsGetGlobalFilePolicy
0x14000da60  mov     rdi, rax
0x14000da63  test    rax, rax
0x14000da66  jnz     loc_14000DC31
0x14000da6c  mov     ebx, 100h
0x14000da71  lea     edx, [rax+30h]
0x14000da74  mov     ecx, ebx
0x14000da76  mov     r8d, 47736642h
0x14000da7c  call    cs:__imp_ExAllocatePool2
0x14000da83  nop     dword ptr [rax+rax+00h]
0x14000da88  mov     rdi, rax
0x14000da8b  test    rax, rax
0x14000da8e  jnz     short loc_14000DAD3
0x14000da90  mov     eax, cs:dword_140019000
0x14000da96  mov     ecx, 0C0000017h; int
0x14000da9b  mov     ebx, ecx
0x14000da9d  cmp     eax, 3
0x14000daa0  jbe     loc_14000DC4A
0x14000daa6  lea     rax, [rbp+var_48]
0x14000daaa  mov     dword ptr [rbp+var_48], ecx
0x14000daad  mov     [rbp+var_20], rax
0x14000dab1  lea     rdx, byte_140016D91; int
0x14000dab8  lea     rax, [rbp+var_40]
0x14000dabc  mov     [rbp+var_18], 4
0x14000dac4  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x14000dac9  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dace  jmp     loc_14000DC4A
0x14000dad3  movzx   edx, byte ptr [r15+1]
0x14000dad8  mov     r8d, 53736642h
0x14000dade  mov     rcx, rbx
0x14000dae1  lea     rdx, ds:8[rdx*4]
0x14000dae9  call    cs:__imp_ExAllocatePool2
0x14000daf0  nop     dword ptr [rax+rax+00h]
0x14000daf5  mov     [rdi+18h], rax
0x14000daf9  test    rax, rax
0x14000dafc  jnz     short loc_14000DB1C
0x14000dafe  mov     eax, cs:dword_140019000
0x14000db04  mov     ecx, 0C0000017h
0x14000db09  mov     ebx, ecx
0x14000db0b  cmp     eax, 3
0x14000db0e  jbe     loc_14000DBF0
0x14000db14  mov     dword ptr [rbp+var_48], ecx
0x14000db17  jmp     loc_14000DBCB
0x14000db1c  movzx   ecx, byte ptr [r15+1]
0x14000db21  mov     r8, r15; SourceSid
0x14000db24  mov     rdx, rax; DestinationSid
0x14000db27  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000db2e  call    cs:__imp_RtlCopySid
0x14000db35  nop     dword ptr [rax+rax+00h]
0x14000db3a  mov     ebx, eax
0x14000db3c  test    eax, eax
0x14000db3e  jns     short loc_14000DB54
0x14000db40  mov     ecx, cs:dword_140019000
0x14000db46  cmp     ecx, 3
0x14000db49  jbe     loc_14000DBF0
0x14000db4f  mov     dword ptr [rbp+var_48], eax
0x14000db52  jmp     short loc_14000DBCB
0x14000db54  movzx   edx, byte ptr [r14+1]
0x14000db59  mov     ecx, 100h
0x14000db5e  mov     r8d, 53736642h
0x14000db64  lea     rdx, ds:8[rdx*4]
0x14000db6c  call    cs:__imp_ExAllocatePool2
0x14000db73  nop     dword ptr [rax+rax+00h]
0x14000db78  mov     [rdi+20h], rax
0x14000db7c  test    rax, rax
0x14000db7f  jz      loc_14000DAFE
0x14000db85  movzx   ecx, byte ptr [r14+1]
0x14000db8a  mov     r8, r14; SourceSid
0x14000db8d  mov     rdx, rax; DestinationSid
0x14000db90  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000db97  call    cs:__imp_RtlCopySid
0x14000db9e  nop     dword ptr [rax+rax+00h]
0x14000dba3  mov     ebx, eax
0x14000dba5  test    eax, eax
0x14000dba7  js      short loc_14000DBBD
0x14000dba9  mov     r8, rdi
0x14000dbac  mov     rdx, r13
0x14000dbaf  mov     rcx, r12
0x14000dbb2  call    BfsInsertEntryHashTable
0x14000dbb7  mov     ebx, eax
0x14000dbb9  test    eax, eax
0x14000dbbb  jns     short loc_14000DC31
0x14000dbbd  mov     eax, cs:dword_140019000
0x14000dbc3  cmp     eax, 3
0x14000dbc6  jbe     short loc_14000DBF0
0x14000dbc8  mov     dword ptr [rbp+var_48], ebx
0x14000dbcb  lea     rax, [rbp+var_48]
0x14000dbcf  mov     [rbp+var_18], 4
0x14000dbd7  mov     [rbp+var_20], rax
0x14000dbdb  lea     rdx, byte_140016D91; int
0x14000dbe2  lea     rax, [rbp+var_40]
0x14000dbe6  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x14000dbeb  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000dbf0  mov     rcx, [rdi+18h]; P
0x14000dbf4  test    rcx, rcx
0x14000dbf7  jz      short loc_14000DC07
0x14000dbf9  xor     edx, edx; Tag
0x14000dbfb  call    cs:__imp_ExFreePoolWithTag
0x14000dc02  nop     dword ptr [rax+rax+00h]
0x14000dc07  mov     rcx, [rdi+20h]; P
0x14000dc0b  test    rcx, rcx
0x14000dc0e  jz      short loc_14000DC1E
0x14000dc10  xor     edx, edx; Tag
0x14000dc12  call    cs:__imp_ExFreePoolWithTag
0x14000dc19  nop     dword ptr [rax+rax+00h]
0x14000dc1e  xor     edx, edx; Tag
0x14000dc20  mov     rcx, rdi; P
0x14000dc23  call    cs:__imp_ExFreePoolWithTag
0x14000dc2a  nop     dword ptr [rax+rax+00h]
0x14000dc2f  jmp     short loc_14000DC4A
0x14000dc31  mov     rax, [rsi+40h]
0x14000dc35  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000dc39  jz      short loc_14000DC48
0x14000dc3b  lock inc qword ptr [rsi+40h]
0x14000dc40  mov     rax, [rsi+40h]
0x14000dc44  mov     [rdi+28h], rax
0x14000dc48  xor     ebx, ebx
0x14000dc4a  mov     eax, ebx
0x14000dc4c  mov     rcx, [rbp+var_10]
0x14000dc50  xor     rcx, rsp; StackCookie
0x14000dc53  call    __security_check_cookie
0x14000dc58  add     rsp, 78h
0x14000dc5c  pop     r15
0x14000dc5e  pop     r14
0x14000dc60  pop     r13
0x14000dc62  pop     r12
0x14000dc64  pop     rdi
0x14000dc65  pop     rsi
0x14000dc66  pop     rbx
0x14000dc67  pop     rbp
0x14000dc68  retn
```
