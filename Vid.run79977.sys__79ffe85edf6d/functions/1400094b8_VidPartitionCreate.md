# VidPartitionCreate

- ea: `0x1400094b8`
- end: `0x140009847`
- name: `VidPartitionCreate`
- size: `911`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, void *Buf2@<rdx>, char)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140009194`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140007898`
- `0x1400094b8`
- `0x14000a010`
- `0x14000a040`
- `0x140011d70`
- `0x1400122fc`
- `0x1400123ac`
- `0x140021c60`
- `0x140021db0`
- `0x140030960`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x1400849f8`
- `0x14009bbd8`
- `0x14009bc68`
- `0x1400f82a0`
- `0x1400f9f60`
- `0x1400fa3ac`
- `0x1400fb404`
- `0x1400fd510`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000976c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000976c`
- `ntoskrnl!ExAllocatePool2` at `0x1400095fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400095fc`

## string_xrefs

- `0x14000957a`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x14000961c`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400097b0`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140009581`: `VidPartitionCreate`
- `0x140009623`: `VidPartitionCreate`
- `0x1400097a0`: `VidPartitionCreate`

## pseudocode

```c
__int64 __fastcall VidPartitionCreate(PCUNICODE_STRING SourceString, void *Buf2, __int64 a3, __int64 a4, char a5)
{
  PVOID v6; // rsi
  int v9; // edx
  int v10; // r8d
  __int64 v11; // r12
  __int64 v12; // rsi
  int v13; // r8d
  int v14; // r14d
  void *Pool2; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // r8d
  _QWORD *v21; // [rsp+30h] [rbp-81h] BYREF
  int v22; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v25[16]; // [rsp+70h] [rbp-41h] BYREF
  int *v26; // [rsp+80h] [rbp-31h]
  __int64 v27; // [rsp+88h] [rbp-29h]
  PVOID *v28; // [rsp+90h] [rbp-21h]
  __int64 v29; // [rsp+98h] [rbp-19h]
  void *v30; // [rsp+A0h] [rbp-11h]
  __int64 v31; // [rsp+A8h] [rbp-9h]

  v6 = VidDeviceExtension;
  v21 = VidDeviceExtension;
  v11 = *(char *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(
                    WdfDriverGlobals,
                    a4)
                + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v9, v10, a3, (__int64)SourceString->Buffer, v11);
  }
  if ( !(_BYTE)v11 )
  {
    v12 = VidPartitionTableLookupAndReference(v6, Buf2, 1);
    if ( !v12 )
    {
      v14 = -1070137335;
      VidTraceErrorInternal0("VidPartitionCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 675);
      goto LABEL_28;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qSq(WPP_GLOBAL_Control->AttachedDevice, 14, v13, a3, (__int64)SourceString->Buffer, v12);
    }
    v14 = 0;
LABEL_25:
    *(_QWORD *)(a3 + 24) = v12 | v11;
    return (unsigned int)v14;
  }
  if ( a5 || (v14 = VidSidPartitionCheck(Buf2), v14 >= 0) )
  {
    Pool2 = (void *)ExAllocatePool2(64, 12816, 1917084758);
    v12 = (__int64)Pool2;
    if ( !Pool2 )
    {
      v14 = -1073741670;
      VidTraceErrorInternal0("VidPartitionCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 714);
      goto LABEL_28;
    }
    v14 = VidPartitionInitialize(Pool2, SourceString);
    if ( v14 >= 0 )
    {
      if ( !a5 || (v14 = VidExoPartitionInitialize(v12), v14 >= 0) )
      {
        v14 = VidPartitionTableInsert(v21, v12);
        if ( v14 >= 0 )
        {
          VidBamReferencePowerPolicy();
          *(_QWORD *)(v12 + 808) = 1;
          *(_QWORD *)(v12 + 816) = 1;
          *(_QWORD *)(v12 + 800) = 1;
          VidOpCtrlUnblock(v12 + 704);
          VidReferencePartition(v12);
          VidOpCtrlStart((char *)VidDeviceExtension + 8, v16, v17, v18);
          _InterlockedAdd64((volatile signed __int64 *)(v21[45] + 8LL), 1u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qSq(WPP_GLOBAL_Control->AttachedDevice, 15, v19, a3, (__int64)SourceString->Buffer, v12);
          }
          goto LABEL_25;
        }
      }
      VidThreadPoolDrain(v12 + 3488);
      VidThreadPoolTeardown(v12 + 3488);
      VidLockAcquireExclusive(v12 + 8);
      VidLockAcquireExclusive(v12 + 3744);
      VidPartitionUninitialize(v12);
      VidLockRelease(v12 + 3744);
      VidLockRelease(v12 + 8);
    }
    ExFreePoolWithTag((PVOID)v12, 0x72446456u);
  }
LABEL_28:
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v24, "VidPartitionCreate");
    tlgCreate1Sz_char(v25, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
    v22 = 831;
    v26 = &v22;
    v27 = 4;
    v28 = (PVOID *)&v21;
    LODWORD(v21) = v14;
    v29 = 4;
    v30 = Buf2;
    v31 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400464D2, 0, 0, 7, v23);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400094b8  push    rbp
0x1400094ba  push    rbx
0x1400094bb  push    rsi
0x1400094bc  push    rdi
0x1400094bd  push    r12
0x1400094bf  push    r13
0x1400094c1  push    r14
0x1400094c3  push    r15
0x1400094c5  lea     rbp, [rsp-17h]
0x1400094ca  sub     rsp, 0C8h
0x1400094d1  mov     rax, cs:__security_cookie
0x1400094d8  xor     rax, rsp
0x1400094db  mov     [rbp+4Fh+var_50], rax
0x1400094df  mov     rax, cs:WdfFunctions_01015
0x1400094e6  mov     r13, rdx
0x1400094e9  mov     rsi, cs:VidDeviceExtension
0x1400094f0  mov     r15, rcx
0x1400094f3  mov     rcx, cs:WdfDriverGlobals
0x1400094fa  mov     rdx, r9
0x1400094fd  mov     rdi, r8
0x140009500  mov     [rsp+100h+var_D0], rsi
0x140009505  mov     rax, [rax+8E8h]
0x14000950c  call    _guard_dispatch_icall
0x140009511  movsx   r12, byte ptr [rax+40h]
0x140009516  mov     rcx, cs:WPP_GLOBAL_Control
0x14000951d  lea     r14, WPP_GLOBAL_Control
0x140009524  cmp     rcx, r14
0x140009527  jz      short loc_140009550
0x140009529  mov     eax, [rcx+2Ch]
0x14000952c  test    al, 2
0x14000952e  jz      short loc_140009550
0x140009530  cmp     byte ptr [rcx+29h], 4
0x140009534  jb      short loc_140009550
0x140009536  mov     rax, [r15+8]
0x14000953a  mov     r9, rdi
0x14000953d  mov     rcx, [rcx+18h]
0x140009541  mov     dword ptr [rsp+100h+var_D8], r12d
0x140009546  mov     [rsp+100h+var_E0], rax
0x14000954b  call    WPP_SF_qSd
0x140009550  test    r12b, r12b
0x140009553  jnz     short loc_1400095D2
0x140009555  mov     r8d, 1
0x14000955b  mov     rdx, r13
0x14000955e  mov     rcx, rsi
0x140009561  call    VidPartitionTableLookupAndReference
0x140009566  mov     rsi, rax
0x140009569  test    rax, rax
0x14000956c  jnz     short loc_140009592
0x14000956e  mov     r14d, 0C0370009h
0x140009574  mov     r8d, 2A3h
0x14000957a  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009581  lea     rcx, aVidpartitioncr; "VidPartitionCreate"
0x140009588  call    VidTraceErrorInternal0
0x14000958d  jmp     loc_140009778
0x140009592  mov     rcx, cs:WPP_GLOBAL_Control
0x140009599  cmp     rcx, r14
0x14000959c  jz      short loc_1400095CA
0x14000959e  mov     eax, [rcx+2Ch]
0x1400095a1  test    al, 2
0x1400095a3  jz      short loc_1400095CA
0x1400095a5  cmp     byte ptr [rcx+29h], 4
0x1400095a9  jb      short loc_1400095CA
0x1400095ab  mov     rax, [r15+8]
0x1400095af  mov     edx, 0Eh
0x1400095b4  mov     rcx, [rcx+18h]
0x1400095b8  mov     r9, rdi
0x1400095bb  mov     [rsp+100h+var_D8], rsi
0x1400095c0  mov     [rsp+100h+var_E0], rax
0x1400095c5  call    WPP_SF_qSq
0x1400095ca  xor     r14d, r14d
0x1400095cd  jmp     loc_14000970D
0x1400095d2  mov     bl, [rbp+4Fh+arg_20]
0x1400095d5  test    bl, bl
0x1400095d7  jnz     short loc_1400095EC
0x1400095d9  mov     rcx, r13; Buf2
0x1400095dc  call    VidSidPartitionCheck
0x1400095e1  mov     r14d, eax
0x1400095e4  test    eax, eax
0x1400095e6  js      loc_140009778
0x1400095ec  mov     edx, 3210h
0x1400095f1  mov     ecx, 40h ; '@'
0x1400095f6  mov     r8d, 72446456h
0x1400095fc  call    cs:__imp_ExAllocatePool2
0x140009603  nop     dword ptr [rax+rax+00h]
0x140009608  mov     rsi, rax
0x14000960b  test    rax, rax
0x14000960e  jnz     short loc_140009634
0x140009610  mov     r14d, 0C000009Ah
0x140009616  mov     r8d, 2CAh
0x14000961c  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009623  lea     rcx, aVidpartitioncr; "VidPartitionCreate"
0x14000962a  call    VidTraceErrorInternal0
0x14000962f  jmp     loc_140009778
0x140009634  mov     r8, r13
0x140009637  mov     rdx, r15; SourceString
0x14000963a  mov     rcx, rsi; DeferredContext
0x14000963d  call    VidPartitionInitialize
0x140009642  mov     r14d, eax
0x140009645  test    eax, eax
0x140009647  js      loc_140009764
0x14000964d  test    bl, bl
0x14000964f  jz      short loc_140009664
0x140009651  mov     rcx, rsi
0x140009654  call    VidExoPartitionInitialize
0x140009659  mov     r14d, eax
0x14000965c  test    eax, eax
0x14000965e  js      loc_14000971C
0x140009664  mov     rcx, [rsp+100h+var_D0]
0x140009669  mov     rdx, rsi
0x14000966c  call    VidPartitionTableInsert
0x140009671  mov     r14d, eax
0x140009674  test    eax, eax
0x140009676  js      loc_14000971C
0x14000967c  call    VidBamReferencePowerPolicy
0x140009681  mov     ebx, 1
0x140009686  lea     rcx, [rsi+2C0h]
0x14000968d  mov     [rsi+328h], rbx
0x140009694  mov     [rsi+330h], rbx
0x14000969b  mov     [rsi+320h], rbx
0x1400096a2  call    VidOpCtrlUnblock
0x1400096a7  mov     rcx, rsi
0x1400096aa  call    VidReferencePartition
0x1400096af  mov     rcx, cs:VidDeviceExtension
0x1400096b6  add     rcx, 8
0x1400096ba  call    VidOpCtrlStart
0x1400096bf  mov     rax, [rsp+100h+var_D0]
0x1400096c4  mov     rcx, [rax+168h]
0x1400096cb  lock add [rcx+8], rbx
0x1400096d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096d7  lea     rax, WPP_GLOBAL_Control
0x1400096de  cmp     rcx, rax
0x1400096e1  jz      short loc_14000970D
0x1400096e3  mov     eax, [rcx+2Ch]
0x1400096e6  test    al, 2
0x1400096e8  jz      short loc_14000970D
0x1400096ea  cmp     byte ptr [rcx+29h], 4
0x1400096ee  jb      short loc_14000970D
0x1400096f0  mov     rax, [r15+8]
0x1400096f4  lea     edx, [rbx+0Eh]
0x1400096f7  mov     rcx, [rcx+18h]
0x1400096fb  mov     r9, rdi
0x1400096fe  mov     [rsp+100h+var_D8], rsi
0x140009703  mov     [rsp+100h+var_E0], rax
0x140009708  call    WPP_SF_qSq
0x14000970d  mov     rax, r12
0x140009710  or      rax, rsi
0x140009713  mov     [rdi+18h], rax
0x140009717  jmp     loc_140009823
0x14000971c  lea     rbx, [rsi+0DA0h]
0x140009723  mov     rcx, rbx
0x140009726  call    VidThreadPoolDrain
0x14000972b  mov     rcx, rbx
0x14000972e  call    VidThreadPoolTeardown
0x140009733  lea     rcx, [rsi+8]
0x140009737  call    VidLockAcquireExclusive
0x14000973c  lea     rbx, [rsi+0EA0h]
0x140009743  mov     rcx, rbx
0x140009746  call    VidLockAcquireExclusive
0x14000974b  mov     rcx, rsi
0x14000974e  call    VidPartitionUninitialize
0x140009753  mov     rcx, rbx
0x140009756  call    VidLockRelease
0x14000975b  lea     rcx, [rsi+8]
0x14000975f  call    VidLockRelease
0x140009764  mov     edx, 72446456h; Tag
0x140009769  mov     rcx, rsi; P
0x14000976c  call    cs:__imp_ExFreePoolWithTag
0x140009773  nop     dword ptr [rax+rax+00h]
0x140009778  mov     eax, cs:dword_140065110
0x14000977e  cmp     eax, 2
0x140009781  jbe     loc_140009823
0x140009787  mov     edx, 100h
0x14000978c  lea     rcx, dword_140065110
0x140009793  call    _tlgKeywordOn
0x140009798  test    al, al
0x14000979a  jz      loc_140009823
0x1400097a0  lea     rdx, aVidpartitioncr; "VidPartitionCreate"
0x1400097a7  lea     rcx, [rbp+4Fh+var_A0]
0x1400097ab  call    _tlgCreate1Sz_char
0x1400097b0  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400097b7  lea     rcx, [rbp+4Fh+var_90]
0x1400097bb  call    _tlgCreate1Sz_char
0x1400097c0  lea     rax, [rbp+4Fh+var_C8]
0x1400097c4  mov     [rbp+4Fh+var_C8], 33Fh
0x1400097cb  mov     [rbp+4Fh+var_80], rax
0x1400097cf  lea     rdx, unk_1400464D2
0x1400097d6  lea     rax, [rsp+100h+var_D0]
0x1400097db  mov     [rbp+4Fh+var_78], 4
0x1400097e3  mov     [rbp+4Fh+var_70], rax
0x1400097e7  lea     rcx, dword_140065110
0x1400097ee  lea     rax, [rbp+4Fh+var_C0]
0x1400097f2  mov     dword ptr [rsp+100h+var_D0], r14d
0x1400097f7  mov     [rsp+100h+var_D8], rax
0x1400097fc  xor     r9d, r9d
0x1400097ff  xor     r8d, r8d
0x140009802  mov     dword ptr [rsp+100h+var_E0], 7
0x14000980a  mov     [rbp+4Fh+var_68], 4
0x140009812  mov     [rbp+4Fh+var_60], r13
0x140009816  mov     [rbp+4Fh+var_58], 10h
0x14000981e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009823  mov     eax, r14d
0x140009826  mov     rcx, [rbp+4Fh+var_50]
0x14000982a  xor     rcx, rsp; StackCookie
0x14000982d  call    __security_check_cookie
0x140009832  add     rsp, 0C8h
0x140009839  pop     r15
0x14000983b  pop     r14
0x14000983d  pop     r13
0x14000983f  pop     r12
0x140009841  pop     rdi
0x140009842  pop     rsi
0x140009843  pop     rbx
0x140009844  pop     rbp
0x140009845  retn
```
