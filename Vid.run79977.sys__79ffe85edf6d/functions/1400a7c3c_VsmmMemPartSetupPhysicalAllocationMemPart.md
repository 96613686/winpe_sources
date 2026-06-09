# VsmmMemPartSetupPhysicalAllocationMemPart

- ea: `0x1400a7c3c`
- end: `0x1400a8222`
- name: `VsmmMemPartSetupPhysicalAllocationMemPart`
- size: `1510`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x14008e464`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021db0`
- `0x1400a7494`
- `0x1400a7c3c`
- `0x1400be51c`
- `0x1400cd8b4`
- `0x1400fe5ec`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a80c1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400a80c1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a819c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a81c6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a819c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a81c6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a8032`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a8131`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a8032`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a8131`
- `ntoskrnl!PsProcessType` at `0x1400a8113`
- `ntoskrnl!PsPartitionType` at `0x1400a8016`
- `ntoskrnl!PsPartitionType` at `0x1400a8096`
- `ntoskrnl!ZwClose` at `0x1400a8186`
- `ntoskrnl!ZwClose` at `0x1400a81b2`
- `ntoskrnl!ZwClose` at `0x1400a8186`
- `ntoskrnl!ZwClose` at `0x1400a81b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a81e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a81e8`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7d13`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7d13`
- `ntoskrnl!ObfReferenceObject` at `0x1400a7cc4`
- `ntoskrnl!ObfReferenceObject` at `0x1400a7cc4`
- `ntoskrnl!ObQueryNameString` at `0x1400a7ce7`
- `ntoskrnl!ObQueryNameString` at `0x1400a7e3b`
- `ntoskrnl!ObQueryNameString` at `0x1400a7ce7`
- `ntoskrnl!ObQueryNameString` at `0x1400a7e3b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a7ede`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a7f0d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a7ede`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400a7f0d`

## pseudocode

```c
__int64 __fastcall VsmmMemPartSetupPhysicalAllocationMemPart(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  PVOID JobMemoryPartition; // rdi
  __int64 v7; // rcx
  NTSTATUS v8; // ebx
  struct _OBJECT_NAME_INFORMATION *Pool2; // rax
  _OBJECT_NAME_INFORMATION *p_ObjectNameInfo; // rsi
  PVOID *v11; // rax
  PVOID *p_Object; // rcx
  void *v13; // rdx
  unsigned int v14; // ebx
  const UNICODE_STRING *MemPartName; // rax
  const UNICODE_STRING *v16; // rax
  int v17; // r15d
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  NTSTATUS v21; // eax
  int ObjectType; // [rsp+20h] [rbp-E0h]
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  PVOID Object; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v29; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v30; // [rsp+68h] [rbp-98h] BYREF
  char v31[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[16]; // [rsp+A0h] [rbp-60h] BYREF
  PVOID *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  PVOID *v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  _DWORD *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 v42; // [rsp+F0h] [rbp-10h]
  _DWORD v43[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  _DWORD *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  wchar_t *Buffer; // [rsp+120h] [rbp+20h]
  _DWORD v49[2]; // [rsp+128h] [rbp+28h] BYREF
  _OBJECT_NAME_INFORMATION ObjectNameInfo; // [rsp+130h] [rbp+30h] BYREF

  v4 = *(_QWORD *)(a1 + 10272);
  ReturnLength = 0;
  Handle = 0;
  v30 = 0;
  v29 = 0;
  if ( !v4 || (JobMemoryPartition = *(PVOID *)(v4 + 96)) == 0 )
  {
    v7 = *(_QWORD *)(a1 + 10280);
    JobMemoryPartition = 0;
    if ( !v7 || (JobMemoryPartition = (PVOID)VsmmNtSlatGetJobMemoryPartition(v7, a2, a3, a4)) == 0 )
    {
      p_ObjectNameInfo = 0;
      v18 = VsmmMemReserveMemPartGet(0);
      v19 = v18;
      if ( v18 )
      {
        v20 = *(_DWORD *)(v18 + 32);
        v17 = 1;
        if ( (v20 & 0xFFFFFFFA) != 0 || v20 == 1 )
          goto LABEL_38;
      }
      v8 = VsmmMemPartOpenSystemMemoryPartition(&Handle);
      if ( v8 < 0 )
        goto LABEL_39;
      Object = 0;
      v21 = ObReferenceObjectByHandle(Handle, 0x1F0003u, PsPartitionType, 0, &Object, 0);
      JobMemoryPartition = Object;
      v8 = v21;
      if ( v21 < 0 )
        goto LABEL_39;
      v17 = 0;
LABEL_35:
      v8 = (*((__int64 (__fastcall **)(PVOID, PVOID *))VidDeviceExtension + 267))(JobMemoryPartition, &v30);
      if ( v8 < 0 )
        goto LABEL_39;
      v8 = ObOpenObjectByPointer(v30, 0x200u, 0, 2u, (POBJECT_TYPE)PsProcessType, 0, &v29);
      if ( v8 < 0 )
        goto LABEL_39;
      v19 = (__int64)JobMemoryPartition;
      *(_QWORD *)(a1 + 10368) = Handle;
      JobMemoryPartition = 0;
      *(_QWORD *)(a1 + 10376) = v29;
      Handle = 0;
      v29 = 0;
LABEL_38:
      *(_QWORD *)(a1 + 10360) = v19;
      v8 = 0;
      *(_DWORD *)(a1 + 10352) = v17;
      goto LABEL_39;
    }
  }
  ObfReferenceObject(JobMemoryPartition);
  ReturnLength = 144;
  v8 = ObQueryNameString(JobMemoryPartition, &ObjectNameInfo, 0x90u, &ReturnLength);
  if ( v8 == -1073741820 )
  {
    Pool2 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(256, ReturnLength, 1833788502);
    p_ObjectNameInfo = Pool2;
    if ( !Pool2 )
    {
      v8 = -1073741670;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_39;
      tlgCreate1Sz_char(v32, "VsmmMemPartSetupPhysicalAllocationMemPart");
      tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
      v25 = 2385;
      v11 = (PVOID *)&v25;
      LODWORD(Object) = -1073741670;
      p_Object = &Object;
      v13 = &unk_14004C289;
LABEL_10:
      v34 = v11;
      v38 = a1 + 656;
      v40 = v43;
      v42 = *(_QWORD *)(a1 + 128);
      v43[0] = *(unsigned __int16 *)(a1 + 120);
      v28 = *(_QWORD *)(a1 + 648);
      v44 = &v28;
      ObjectType = 10;
LABEL_11:
      v36 = p_Object;
      v35 = 4;
      v37 = 4;
      v39 = 16;
      v41 = 2;
      v43[1] = 0;
      v45 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v13, 0, 0, ObjectType, v31);
      goto LABEL_39;
    }
    v8 = ObQueryNameString(JobMemoryPartition, Pool2, ReturnLength, &ReturnLength);
  }
  else
  {
    p_ObjectNameInfo = &ObjectNameInfo;
  }
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_39;
    tlgCreate1Sz_char(v32, "VsmmMemPartSetupPhysicalAllocationMemPart");
    tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    LODWORD(Object) = 2398;
    v11 = &Object;
    v25 = v8;
    p_Object = (PVOID *)&v25;
    v13 = &unk_14004C12A;
    goto LABEL_10;
  }
  if ( !p_ObjectNameInfo->Name.Buffer )
  {
LABEL_27:
    v8 = ObOpenObjectByPointer(JobMemoryPartition, 0x200u, 0, 0x1F0003u, PsPartitionType, 0, &Handle);
    if ( v8 < 0 )
      goto LABEL_39;
    v17 = 2;
    goto LABEL_35;
  }
  v14 = 0;
  while ( 1 )
  {
    MemPartName = (const UNICODE_STRING *)VsmmMemReserveGetMemPartName(v14);
    if ( RtlEqualUnicodeString(&p_ObjectNameInfo->Name, MemPartName, 1u) )
      break;
    if ( (int)++v14 >= 2 )
    {
      if ( v14 != 2 )
        goto LABEL_27;
      v16 = (const UNICODE_STRING *)VsmmMemReserveGetMemPartName(0xFFFFFFFFLL);
      if ( !RtlEqualUnicodeString(&p_ObjectNameInfo->Name, v16, 1u) )
        goto LABEL_27;
      break;
    }
  }
  v8 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v32, "VsmmMemPartSetupPhysicalAllocationMemPart");
    tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c");
    LODWORD(Object) = 2444;
    v34 = &Object;
    p_Object = (PVOID *)&v25;
    v25 = -1073741811;
    v38 = a1 + 656;
    v13 = &unk_14004C198;
    v47 = 2;
    v40 = v43;
    v42 = *(_QWORD *)(a1 + 128);
    v43[0] = *(unsigned __int16 *)(a1 + 120);
    v28 = *(_QWORD *)(a1 + 648);
    v44 = &v28;
    v46 = v49;
    Buffer = p_ObjectNameInfo->Name.Buffer;
    v49[0] = p_ObjectNameInfo->Name.Length;
    ObjectType = 12;
    v49[1] = 0;
    goto LABEL_11;
  }
LABEL_39:
  if ( v29 )
    ZwClose(v29);
  if ( v30 )
    ObfDereferenceObject(v30);
  if ( Handle )
    ZwClose(Handle);
  if ( JobMemoryPartition )
    ObfDereferenceObject(JobMemoryPartition);
  if ( p_ObjectNameInfo && p_ObjectNameInfo != &ObjectNameInfo )
    ExFreePoolWithTag(p_ObjectNameInfo, 0x6D4D6456u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400a7c3c  mov     [rsp-8+arg_8], rbx
0x1400a7c41  mov     [rsp-8+arg_10], rsi
0x1400a7c46  push    rbp
0x1400a7c47  push    rdi
0x1400a7c48  push    r12
0x1400a7c4a  push    r13
0x1400a7c4c  push    r15
0x1400a7c4e  lea     rbp, [rsp-0D0h]
0x1400a7c56  sub     rsp, 1D0h
0x1400a7c5d  mov     rax, cs:__security_cookie
0x1400a7c64  xor     rax, rsp
0x1400a7c67  mov     [rbp+0F0h+var_30], rax
0x1400a7c6e  mov     rdi, [rcx+2820h]
0x1400a7c75  xor     r12d, r12d
0x1400a7c78  mov     [rsp+1F0h+ReturnLength], r12d
0x1400a7c7d  mov     r13, rcx
0x1400a7c80  mov     [rsp+1F0h+var_1A0], r12
0x1400a7c85  mov     [rsp+1F0h+var_188], r12
0x1400a7c8a  mov     [rsp+1F0h+var_190], r12
0x1400a7c8f  test    rdi, rdi
0x1400a7c92  jz      short loc_1400A7C9D
0x1400a7c94  mov     rdi, [rdi+60h]
0x1400a7c98  test    rdi, rdi
0x1400a7c9b  jnz     short loc_1400A7CC1
0x1400a7c9d  mov     rcx, [rcx+2828h]
0x1400a7ca4  mov     rdi, r12
0x1400a7ca7  test    rcx, rcx
0x1400a7caa  jz      loc_1400A8053
0x1400a7cb0  call    VsmmNtSlatGetJobMemoryPartition
0x1400a7cb5  mov     rdi, rax
0x1400a7cb8  test    rax, rax
0x1400a7cbb  jz      loc_1400A8053
0x1400a7cc1  mov     rcx, rdi; Object
0x1400a7cc4  call    cs:__imp_ObfReferenceObject
0x1400a7ccb  nop     dword ptr [rax+rax+00h]
0x1400a7cd0  mov     r8d, 90h; Length
0x1400a7cd6  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x1400a7cdb  lea     rdx, [rbp+0F0h+ObjectNameInfo]; ObjectNameInfo
0x1400a7cdf  mov     [rsp+1F0h+ReturnLength], r8d
0x1400a7ce4  mov     rcx, rdi; Object
0x1400a7ce7  call    cs:__imp_ObQueryNameString
0x1400a7cee  nop     dword ptr [rax+rax+00h]
0x1400a7cf3  mov     ebx, eax
0x1400a7cf5  mov     r15d, 100h
0x1400a7cfb  cmp     eax, 0C0000004h
0x1400a7d00  jnz     loc_1400A7E4B
0x1400a7d06  mov     edx, [rsp+1F0h+ReturnLength]
0x1400a7d0a  mov     r8d, 6D4D6456h
0x1400a7d10  mov     ecx, r15d
0x1400a7d13  call    cs:__imp_ExAllocatePool2
0x1400a7d1a  nop     dword ptr [rax+rax+00h]
0x1400a7d1f  mov     rsi, rax
0x1400a7d22  test    rax, rax
0x1400a7d25  jnz     loc_1400A7E2B
0x1400a7d2b  mov     ecx, cs:dword_140065110
0x1400a7d31  mov     ebx, 0C000009Ah
0x1400a7d36  cmp     ecx, 2
0x1400a7d39  jbe     loc_1400A817C
0x1400a7d3f  mov     edx, r15d
0x1400a7d42  lea     rcx, dword_140065110
0x1400a7d49  call    _tlgKeywordOn
0x1400a7d4e  test    al, al
0x1400a7d50  jz      loc_1400A817C
0x1400a7d56  lea     rdx, aVsmmmempartset_4; "VsmmMemPartSetupPhysicalAllocationMemPa"...
0x1400a7d5d  lea     rcx, [rbp+0F0h+var_160]
0x1400a7d61  call    _tlgCreate1Sz_char
0x1400a7d66  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7d6d  lea     rcx, [rbp+0F0h+var_150]
0x1400a7d71  call    _tlgCreate1Sz_char
0x1400a7d76  mov     [rsp+1F0h+var_1AC], 951h
0x1400a7d7e  lea     rax, [rsp+1F0h+var_1AC]
0x1400a7d83  mov     dword ptr [rsp+1F0h+Object], ebx
0x1400a7d87  lea     rcx, [rsp+1F0h+Object]
0x1400a7d8c  lea     rdx, unk_14004C289
0x1400a7d93  mov     [rbp+0F0h+var_140], rax
0x1400a7d97  lea     rax, [r13+290h]
0x1400a7d9e  mov     [rbp+0F0h+var_120], rax
0x1400a7da2  lea     rax, [rbp+0F0h+var_F8]
0x1400a7da6  mov     [rbp+0F0h+var_110], rax
0x1400a7daa  mov     rax, [r13+80h]
0x1400a7db1  mov     [rbp+0F0h+var_100], rax
0x1400a7db5  movzx   eax, word ptr [r13+78h]
0x1400a7dba  mov     [rbp+0F0h+var_F8], eax
0x1400a7dbd  mov     rax, [r13+288h]
0x1400a7dc4  mov     [rsp+1F0h+var_198], rax
0x1400a7dc9  lea     rax, [rsp+1F0h+var_198]
0x1400a7dce  mov     [rbp+0F0h+var_F0], rax
0x1400a7dd2  lea     rax, [rsp+1F0h+var_180]
0x1400a7dd7  mov     qword ptr [rsp+1F0h+AccessMode], rax
0x1400a7ddc  mov     dword ptr [rsp+1F0h+ObjectType], 0Ah
0x1400a7de4  mov     [rbp+0F0h+var_130], rcx
0x1400a7de8  xor     r9d, r9d
0x1400a7deb  lea     rcx, dword_140065110
0x1400a7df2  mov     [rbp+0F0h+var_138], 4
0x1400a7dfa  xor     r8d, r8d
0x1400a7dfd  mov     [rbp+0F0h+var_128], 4
0x1400a7e05  mov     [rbp+0F0h+var_118], 10h
0x1400a7e0d  mov     [rbp+0F0h+var_108], 2
0x1400a7e15  mov     [rbp+0F0h+var_F4], r12d
0x1400a7e19  mov     [rbp+0F0h+var_E8], 8
0x1400a7e21  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400a7e26  jmp     loc_1400A817C
0x1400a7e2b  mov     r8d, [rsp+1F0h+ReturnLength]; Length
0x1400a7e30  lea     r9, [rsp+1F0h+ReturnLength]; ReturnLength
0x1400a7e35  mov     rdx, rax; ObjectNameInfo
0x1400a7e38  mov     rcx, rdi; Object
0x1400a7e3b  call    cs:__imp_ObQueryNameString
0x1400a7e42  nop     dword ptr [rax+rax+00h]
0x1400a7e47  mov     ebx, eax
0x1400a7e49  jmp     short loc_1400A7E4F
0x1400a7e4b  lea     rsi, [rbp+0F0h+ObjectNameInfo]
0x1400a7e4f  test    ebx, ebx
0x1400a7e51  jns     short loc_1400A7EBB
0x1400a7e53  mov     eax, cs:dword_140065110
0x1400a7e59  cmp     eax, 2
0x1400a7e5c  jbe     loc_1400A817C
0x1400a7e62  mov     rdx, r15
0x1400a7e65  lea     rcx, dword_140065110
0x1400a7e6c  call    _tlgKeywordOn
0x1400a7e71  test    al, al
0x1400a7e73  jz      loc_1400A817C
0x1400a7e79  lea     rdx, aVsmmmempartset_4; "VsmmMemPartSetupPhysicalAllocationMemPa"...
0x1400a7e80  lea     rcx, [rbp+0F0h+var_160]
0x1400a7e84  call    _tlgCreate1Sz_char
0x1400a7e89  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7e90  lea     rcx, [rbp+0F0h+var_150]
0x1400a7e94  call    _tlgCreate1Sz_char
0x1400a7e99  mov     dword ptr [rsp+1F0h+Object], 95Eh
0x1400a7ea1  lea     rax, [rsp+1F0h+Object]
0x1400a7ea6  mov     [rsp+1F0h+var_1AC], ebx
0x1400a7eaa  lea     rcx, [rsp+1F0h+var_1AC]
0x1400a7eaf  lea     rdx, unk_14004C12A
0x1400a7eb6  jmp     loc_1400A7D93
0x1400a7ebb  cmp     [rsi+8], r12
0x1400a7ebf  jz      loc_1400A8003
0x1400a7ec5  mov     ebx, r12d
0x1400a7ec8  mov     r15d, 1
0x1400a7ece  mov     ecx, ebx
0x1400a7ed0  call    VsmmMemReserveGetMemPartName
0x1400a7ed5  mov     rdx, rax; String2
0x1400a7ed8  mov     rcx, rsi; String1
0x1400a7edb  mov     r8b, r15b; CaseInSensitive
0x1400a7ede  call    cs:__imp_RtlEqualUnicodeString
0x1400a7ee5  nop     dword ptr [rax+rax+00h]
0x1400a7eea  test    al, al
0x1400a7eec  jnz     short loc_1400A7F21
0x1400a7eee  add     ebx, r15d
0x1400a7ef1  cmp     ebx, 2
0x1400a7ef4  jl      short loc_1400A7ECE
0x1400a7ef6  jnz     loc_1400A8003
0x1400a7efc  or      ecx, 0FFFFFFFFh
0x1400a7eff  call    VsmmMemReserveGetMemPartName
0x1400a7f04  mov     rdx, rax; String2
0x1400a7f07  mov     rcx, rsi; String1
0x1400a7f0a  mov     r8b, r15b; CaseInSensitive
0x1400a7f0d  call    cs:__imp_RtlEqualUnicodeString
0x1400a7f14  nop     dword ptr [rax+rax+00h]
0x1400a7f19  test    al, al
0x1400a7f1b  jz      loc_1400A8003
0x1400a7f21  mov     eax, cs:dword_140065110
0x1400a7f27  mov     ebx, 0C000000Dh
0x1400a7f2c  cmp     eax, 2
0x1400a7f2f  jbe     loc_1400A817C
0x1400a7f35  mov     edx, 100h
0x1400a7f3a  lea     rcx, dword_140065110
0x1400a7f41  call    _tlgKeywordOn
0x1400a7f46  test    al, al
0x1400a7f48  jz      loc_1400A817C
0x1400a7f4e  lea     rdx, aVsmmmempartset_4; "VsmmMemPartSetupPhysicalAllocationMemPa"...
0x1400a7f55  lea     rcx, [rbp+0F0h+var_160]
0x1400a7f59  call    _tlgCreate1Sz_char
0x1400a7f5e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7f65  lea     rcx, [rbp+0F0h+var_150]
0x1400a7f69  call    _tlgCreate1Sz_char
0x1400a7f6e  lea     rax, [rsp+1F0h+Object]
0x1400a7f73  mov     dword ptr [rsp+1F0h+Object], 98Ch
0x1400a7f7b  mov     [rbp+0F0h+var_140], rax
0x1400a7f7f  lea     rcx, [rsp+1F0h+var_1AC]
0x1400a7f84  lea     rax, [r13+290h]
0x1400a7f8b  mov     [rsp+1F0h+var_1AC], ebx
0x1400a7f8f  mov     [rbp+0F0h+var_120], rax
0x1400a7f93  lea     rdx, unk_14004C198
0x1400a7f9a  lea     rax, [rbp+0F0h+var_F8]
0x1400a7f9e  mov     [rbp+0F0h+var_D8], 2
0x1400a7fa6  mov     [rbp+0F0h+var_110], rax
0x1400a7faa  mov     rax, [r13+80h]
0x1400a7fb1  mov     [rbp+0F0h+var_100], rax
0x1400a7fb5  movzx   eax, word ptr [r13+78h]
0x1400a7fba  mov     [rbp+0F0h+var_F8], eax
0x1400a7fbd  mov     rax, [r13+288h]
0x1400a7fc4  mov     [rsp+1F0h+var_198], rax
0x1400a7fc9  lea     rax, [rsp+1F0h+var_198]
0x1400a7fce  mov     [rbp+0F0h+var_F0], rax
0x1400a7fd2  lea     rax, [rbp+0F0h+var_C8]
0x1400a7fd6  mov     [rbp+0F0h+var_E0], rax
0x1400a7fda  mov     rax, [rsi+8]
0x1400a7fde  mov     [rbp+0F0h+var_D0], rax
0x1400a7fe2  movzx   eax, word ptr [rsi]
0x1400a7fe5  mov     [rbp+0F0h+var_C8], eax
0x1400a7fe8  lea     rax, [rsp+1F0h+var_180]
0x1400a7fed  mov     qword ptr [rsp+1F0h+AccessMode], rax
0x1400a7ff2  mov     dword ptr [rsp+1F0h+ObjectType], 0Ch
0x1400a7ffa  mov     [rbp+0F0h+var_C4], r12d
0x1400a7ffe  jmp     loc_1400A7DE4
0x1400a8003  lea     rax, [rsp+1F0h+var_1A0]
0x1400a8008  mov     r9d, 1F0003h; DesiredAccess
0x1400a800e  mov     [rsp+1F0h+Handle], rax; Handle
0x1400a8013  xor     r8d, r8d; PassedAccessState
0x1400a8016  mov     rax, cs:__imp_PsPartitionType
0x1400a801d  mov     edx, 200h; HandleAttributes
0x1400a8022  mov     [rsp+1F0h+AccessMode], r12b; AccessMode
0x1400a8027  mov     rcx, [rax]
0x1400a802a  mov     [rsp+1F0h+ObjectType], rcx; ObjectType
0x1400a802f  mov     rcx, rdi; Object
0x1400a8032  call    cs:__imp_ObOpenObjectByPointer
0x1400a8039  nop     dword ptr [rax+rax+00h]
0x1400a803e  mov     ebx, eax
0x1400a8040  test    eax, eax
0x1400a8042  js      loc_1400A817C
0x1400a8048  mov     r15d, 2
0x1400a804e  jmp     loc_1400A80DF
0x1400a8053  xor     ecx, ecx
0x1400a8055  mov     rsi, r12
0x1400a8058  call    VsmmMemReserveMemPartGet
0x1400a805d  mov     rcx, rax
0x1400a8060  test    rax, rax
0x1400a8063  jz      short loc_1400A8082
0x1400a8065  mov     eax, [rax+20h]
0x1400a8068  mov     r15d, 1
0x1400a806e  test    eax, 0FFFFFFFAh
0x1400a8073  jnz     loc_1400A816B
0x1400a8079  cmp     eax, r15d
0x1400a807c  jz      loc_1400A816B
0x1400a8082  lea     rcx, [rsp+1F0h+var_1A0]
0x1400a8087  call    VsmmMemPartOpenSystemMemoryPartition
0x1400a808c  mov     ebx, eax
0x1400a808e  test    eax, eax
0x1400a8090  js      loc_1400A817C
0x1400a8096  mov     r8, cs:__imp_PsPartitionType
0x1400a809d  lea     rax, [rsp+1F0h+Object]
0x1400a80a2  mov     rcx, [rsp+1F0h+var_1A0]; Handle
0x1400a80a7  xor     r9d, r9d; AccessMode
0x1400a80aa  mov     qword ptr [rsp+1F0h+AccessMode], r12; HandleInformation
0x1400a80af  mov     edx, 1F0003h; DesiredAccess
0x1400a80b4  mov     [rsp+1F0h+Object], r12
0x1400a80b9  mov     r8, [r8]; ObjectType
0x1400a80bc  mov     [rsp+1F0h+ObjectType], rax; Object
0x1400a80c1  call    cs:__imp_ObReferenceObjectByHandle
0x1400a80c8  nop     dword ptr [rax+rax+00h]
0x1400a80cd  mov     rdi, [rsp+1F0h+Object]
0x1400a80d2  mov     ebx, eax
0x1400a80d4  test    eax, eax
0x1400a80d6  js      loc_1400A817C
0x1400a80dc  mov     r15d, r12d
0x1400a80df  mov     rax, cs:VidDeviceExtension
0x1400a80e6  lea     rdx, [rsp+1F0h+var_188]
0x1400a80eb  mov     rcx, rdi
0x1400a80ee  mov     rax, [rax+858h]
0x1400a80f5  call    _guard_dispatch_icall
0x1400a80fa  mov     ebx, eax
0x1400a80fc  test    eax, eax
0x1400a80fe  js      short loc_1400A817C
0x1400a8100  lea     rax, [rsp+1F0h+var_190]
0x1400a8105  mov     r9d, 2; DesiredAccess
0x1400a810b  mov     [rsp+1F0h+Handle], rax; Handle
0x1400a8110  xor     r8d, r8d; PassedAccessState
0x1400a8113  mov     rax, cs:__imp_PsProcessType
0x1400a811a  mov     edx, 200h; HandleAttributes
0x1400a811f  mov     [rsp+1F0h+AccessMode], r12b; AccessMode
0x1400a8124  mov     rcx, [rax]
0x1400a8127  mov     [rsp+1F0h+ObjectType], rcx; ObjectType
0x1400a812c  mov     rcx, [rsp+1F0h+var_188]; Object
0x1400a8131  call    cs:__imp_ObOpenObjectByPointer
0x1400a8138  nop     dword ptr [rax+rax+00h]
0x1400a813d  mov     ebx, eax
0x1400a813f  test    eax, eax
0x1400a8141  js      short loc_1400A817C
0x1400a8143  mov     rax, [rsp+1F0h+var_1A0]
0x1400a8148  mov     rcx, rdi
0x1400a814b  mov     [r13+2880h], rax
0x1400a8152  mov     rdi, r12
0x1400a8155  mov     rax, [rsp+1F0h+var_190]
0x1400a815a  mov     [r13+2888h], rax
0x1400a8161  mov     [rsp+1F0h+var_1A0], r12
0x1400a8166  mov     [rsp+1F0h+var_190], r12
0x1400a816b  mov     [r13+2878h], rcx
0x1400a8172  mov     ebx, r12d
0x1400a8175  mov     [r13+2870h], r15d
0x1400a817c  mov     rcx, [rsp+1F0h+var_190]; Handle
0x1400a8181  test    rcx, rcx
0x1400a8184  jz      short loc_1400A8192
0x1400a8186  call    cs:__imp_ZwClose
0x1400a818d  nop     dword ptr [rax+rax+00h]
0x1400a8192  mov     rcx, [rsp+1F0h+var_188]; Object
0x1400a8197  test    rcx, rcx
0x1400a819a  jz      short loc_1400A81A8
0x1400a819c  call    cs:__imp_ObfDereferenceObject
0x1400a81a3  nop     dword ptr [rax+rax+00h]
0x1400a81a8  mov     rcx, [rsp+1F0h+var_1A0]; Handle
0x1400a81ad  test    rcx, rcx
  ... truncated ...
```
