# WfpAssociateContextToFlowInternal

- ea: `0x14000ab30`
- end: `0x14000af95`
- name: `WfpAssociateContextToFlowInternal`
- size: `1125`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000a900`
- `0x14000df00`

## callees

- `0x140006d20`
- `0x140007ad0`
- `0x140009e00`
- `0x14000ab30`
- `0x14000afa0`
- `0x14000b070`
- `0x14000b0c0`
- `0x14000bb9c`
- `0x14000bc60`
- `0x14000cc70`
- `0x14004efd4`
- `0x140069660`
- `0x140078100`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ac22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ad6e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ac22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000ad6e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000abe5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000abe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ace8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ace8`
- `NDIS!NdisReleaseRWLock` at `0x14000ada6`
- `NDIS!NdisReleaseRWLock` at `0x14000ada6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ac06`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000ac06`

## pseudocode

```c
__int64 __fastcall WfpAssociateContextToFlowInternal(
        __int64 a1,
        unsigned __int16 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int16 *v8; // rbp
  int v9; // ebx
  __int64 TableFromHandle; // rsi
  __int64 v11; // rcx
  PNPAGED_LOOKASIDE_LIST v12; // rdi
  unsigned __int16 **v13; // r14
  KIRQL CurrentIrql; // bl
  __int64 v15; // rdx
  unsigned __int16 *v16; // rbx
  __int64 v17; // rcx
  unsigned int i; // eax
  __int64 v19; // r9
  unsigned int v20; // edi
  void *v21; // r14
  __int64 v22; // r8
  _DWORD *v23; // rdi
  __int64 v24; // rax
  PNPAGED_LOOKASIDE_LIST v25; // rbx
  _DWORD *v26; // rdx
  __int64 v28; // rax
  int v29; // eax
  int v30; // [rsp+30h] [rbp-58h]
  __int64 v31; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-48h] BYREF
  void *v33; // [rsp+48h] [rbp-40h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A8h] [rbp+20h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v33 = 0;
  v32 = 0;
  v30 = 0;
  v8 = 0;
  v9 = 0;
  if ( a4 )
  {
    v31 = 0;
    TableFromHandle = FeRefCalloutFlowContext(a3);
    if ( TableFromHandle )
    {
LABEL_33:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAssociateContextToFlowInternal",
          TableFromHandle);
      }
      return TableFromHandle;
    }
    v9 = 1;
    v30 = 1;
    FeGetCalloutFlowDelete(a3, &v31, 0);
    if ( !v31 )
    {
      TableFromHandle = WfpReportSysErrorAsNtStatus(v11, "WfpAssociateContextToFlowInternal", 3221225485LL, 1);
      goto LABEL_22;
    }
  }
  TableFromHandle = KfdAleGetTableFromHandle(a1, &v32);
  if ( !TableFromHandle )
  {
    v12 = gWfpGlobal;
    v13 = (unsigned __int16 **)v32;
    v8 = v32 - 56;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v12[3].L.AllocateEx, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v15 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v15 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v15 = 4;
    }
    v16 = *v13;
    v32 = *v13;
    if ( (unsigned int)IsFlowContextTableAcceptingContexts(v32) )
    {
      if ( v16 )
        goto LABEL_10;
      TableFromHandle = WfpPoolAllocNonPaged(16, 1131439703, &v32);
      if ( !TableFromHandle )
      {
        v16 = v32;
        *(_OWORD *)v32 = 0;
        *v13 = v16;
        if ( !v16 )
        {
LABEL_14:
          v20 = *v16;
          v21 = (void *)*((_QWORD *)v16 + 1);
          TableFromHandle = WfpPoolAllocNonPaged(32LL * (v20 + 1), 1131439703, &v33);
          if ( !TableFromHandle )
          {
            v22 = v20;
            v23 = v33;
            memmove(v33, v21, 32 * v22);
            ++*v16;
            if ( v21 )
              ExFreePoolWithTag(v21, 0);
            v24 = 8LL * *v16;
            *(_OWORD *)&v23[v24 - 8] = 0;
            *(_OWORD *)&v23[v24 - 4] = 0;
            v23[8 * *v16 - 5] = a3;
            LOWORD(v23[8 * *v16 - 6]) = a2;
            *(_QWORD *)&v23[8 * *v16 - 4] = a4;
            *(_QWORD *)&v23[8 * *v16 - 2] = a5;
            *((_QWORD *)v16 + 1) = v23;
          }
          goto LABEL_18;
        }
LABEL_10:
        for ( i = 0; i < *v16; ++i )
        {
          v19 = *((_QWORD *)v16 + 1) + 32LL * i;
          if ( *(_DWORD *)(v19 + 12) == a3 && *(_WORD *)(v19 + 8) == a2 )
          {
            if ( a4 && *(_QWORD *)(v19 + 16) || (v28 = a5) != 0 && *(_QWORD *)(v19 + 24) )
            {
              TableFromHandle = 0x40000000;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
              {
                WPP_SF_sd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  10,
                  (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                  (unsigned int)"WfpAssociateContextToFlowInternal",
                  0);
              }
            }
            else if ( a4 )
            {
              v29 = *(_DWORD *)v19;
              *(_QWORD *)(v19 + 16) = a4;
              if ( (v29 & 1) != 0 )
                *(_DWORD *)v19 = v29 & 0xFFFFFFFE;
              WfpCalloutDiagTraceAssociateFlow(a1, a2, a3, a4);
            }
            else
            {
              *(_QWORD *)(v19 + 24) = a5;
              WfpCalloutDiagTraceAssociateFlowStream(a1, a2, a3, v28);
            }
            goto LABEL_18;
          }
        }
        goto LABEL_14;
      }
    }
    else
    {
      TableFromHandle = WfpReportSysErrorAsNtStatus(v17, "WfpAssociateContextToFlowInternal", 3221225485LL, 1);
    }
LABEL_18:
    v25 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v26 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v26 == 4 )
        *v26 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v25[3].L.AllocateEx, &LockState);
    v9 = v30;
LABEL_22:
    if ( !TableFromHandle )
      goto LABEL_23;
  }
  if ( v9 )
    FeDeRefCalloutFlowContext(a3);
LABEL_23:
  if ( v8 )
    WfpAleDereferenceEndpoint(v8);
  if ( TableFromHandle )
    goto LABEL_33;
  return TableFromHandle;
}

```

## disassembly

```asm
0x14000ab30  mov     [rsp+arg_8], dx
0x14000ab35  mov     r11, rsp
0x14000ab38  push    rbx
0x14000ab39  push    rbp
0x14000ab3a  push    rsi
0x14000ab3b  push    rdi
0x14000ab3c  push    r12
0x14000ab3e  push    r13
0x14000ab40  push    r15
0x14000ab42  sub     rsp, 50h
0x14000ab46  xor     eax, eax
0x14000ab48  lea     rdi, WPP_GLOBAL_Control
0x14000ab4f  mov     r15, rcx
0x14000ab52  mov     [r11+20h], ax
0x14000ab57  xor     ecx, ecx
0x14000ab59  mov     [r11+22h], al
0x14000ab5d  mov     [r11-40h], rcx
0x14000ab61  mov     r12, r9
0x14000ab64  mov     [r11-48h], rcx
0x14000ab68  mov     r13d, r8d
0x14000ab6b  mov     [rsp+88h+var_58], ecx
0x14000ab6f  mov     ebp, ecx
0x14000ab71  mov     ebx, ecx
0x14000ab73  test    r9, r9
0x14000ab76  jz      short loc_14000ABB4
0x14000ab78  mov     [r11-50h], rcx
0x14000ab7c  mov     ecx, r8d
0x14000ab7f  call    FeRefCalloutFlowContext
0x14000ab84  mov     rsi, rax
0x14000ab87  test    rax, rax
0x14000ab8a  jnz     loc_14000AE3B
0x14000ab90  mov     ebx, 1
0x14000ab95  lea     rdx, [rsp+88h+var_50]
0x14000ab9a  xor     r8d, r8d
0x14000ab9d  mov     [rsp+88h+var_58], ebx
0x14000aba1  mov     ecx, r13d
0x14000aba4  call    FeGetCalloutFlowDelete
0x14000aba9  cmp     [rsp+88h+var_50], rbp
0x14000abae  jz      loc_14000AF3E
0x14000abb4  lea     rdx, [rsp+88h+var_48]
0x14000abb9  mov     rcx, r15
0x14000abbc  call    KfdAleGetTableFromHandle
0x14000abc1  mov     rsi, rax
0x14000abc4  test    rax, rax
0x14000abc7  jnz     loc_14000AF29
0x14000abcd  mov     rdi, cs:gWfpGlobal
0x14000abd4  mov     [rsp+88h+arg_0], r14
0x14000abdc  mov     r14, [rsp+88h+var_48]
0x14000abe1  lea     rbp, [r14-70h]
0x14000abe5  call    cs:__imp_KeGetCurrentIrql
0x14000abec  nop     dword ptr [rax+rax+00h]
0x14000abf1  mov     rcx, [rdi+1B0h]; Lock
0x14000abf8  lea     rdx, [rsp+88h+LockState]; LockState
0x14000ac00  xor     r8d, r8d; Flags
0x14000ac03  movzx   ebx, al
0x14000ac06  call    cs:__imp_NdisAcquireRWLockWrite
0x14000ac0d  nop     dword ptr [rax+rax+00h]
0x14000ac12  cmp     bl, 2
0x14000ac15  jz      short loc_14000AC56
0x14000ac17  cmp     cs:gWfpPerProContext, rsi
0x14000ac1e  jz      short loc_14000AC56
0x14000ac20  xor     ecx, ecx; ProcNumber
0x14000ac22  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000ac29  nop     dword ptr [rax+rax+00h]
0x14000ac2e  imul    eax, cs:gWfpPerProContextSize
0x14000ac35  mov     ecx, eax
0x14000ac37  mov     rax, cs:gWfpPerProContext
0x14000ac3e  mov     rdx, [rcx+rax]
0x14000ac42  mov     rax, ds:0FFFFF78000000008h
0x14000ac4c  mov     [rdx+8], rax
0x14000ac50  mov     dword ptr [rdx], 4
0x14000ac56  mov     rbx, [r14]
0x14000ac59  mov     rcx, rbx
0x14000ac5c  mov     [rsp+88h+var_48], rbx
0x14000ac61  call    IsFlowContextTableAcceptingContexts
0x14000ac66  test    eax, eax
0x14000ac68  jz      loc_14000AF5B
0x14000ac6e  test    rbx, rbx
0x14000ac71  jz      loc_14000AE7F
0x14000ac77  movzx   r8d, word ptr [rbx]
0x14000ac7b  xor     eax, eax
0x14000ac7d  cmp     eax, r8d
0x14000ac80  jnb     short loc_14000AC9B
0x14000ac82  mov     r9d, eax
0x14000ac85  shl     r9, 5
0x14000ac89  add     r9, [rbx+8]
0x14000ac8d  cmp     [r9+0Ch], r13d
0x14000ac91  jz      loc_14000ADE4
0x14000ac97  inc     eax
0x14000ac99  jmp     short loc_14000AC7D
0x14000ac9b  movzx   edi, word ptr [rbx]
0x14000ac9e  lea     r8, [rsp+88h+var_40]
0x14000aca3  mov     r14, [rbx+8]
0x14000aca7  mov     edx, 43706657h
0x14000acac  lea     ecx, [rdi+1]
0x14000acaf  shl     rcx, 5
0x14000acb3  call    WfpPoolAllocNonPaged
0x14000acb8  mov     rsi, rax
0x14000acbb  test    rax, rax
0x14000acbe  jnz     loc_14000AD4C
0x14000acc4  mov     r8d, edi
0x14000acc7  mov     rdx, r14; Src
0x14000acca  mov     rdi, [rsp+88h+var_40]
0x14000accf  mov     rcx, rdi; void *
0x14000acd2  shl     r8, 5; Size
0x14000acd6  call    memmove
0x14000acdb  inc     word ptr [rbx]
0x14000acde  test    r14, r14
0x14000ace1  jz      short loc_14000ACF4
0x14000ace3  xor     edx, edx; Tag
0x14000ace5  mov     rcx, r14; P
0x14000ace8  call    cs:__imp_ExFreePoolWithTag
0x14000acef  nop     dword ptr [rax+rax+00h]
0x14000acf4  movzx   eax, word ptr [rbx]
0x14000acf7  xorps   xmm0, xmm0
0x14000acfa  movzx   ecx, [rsp+88h+arg_8]
0x14000ad02  shl     rax, 5
0x14000ad06  movups  xmmword ptr [rax+rdi-20h], xmm0
0x14000ad0b  movups  xmmword ptr [rax+rdi-10h], xmm0
0x14000ad10  movzx   eax, word ptr [rbx]
0x14000ad13  shl     rax, 5
0x14000ad17  mov     [rax+rdi-14h], r13d
0x14000ad1c  movzx   eax, word ptr [rbx]
0x14000ad1f  shl     rax, 5
0x14000ad23  mov     [rax+rdi-18h], cx
0x14000ad28  movzx   eax, word ptr [rbx]
0x14000ad2b  shl     rax, 5
0x14000ad2f  mov     [rax+rdi-10h], r12
0x14000ad34  movzx   ecx, word ptr [rbx]
0x14000ad37  mov     rax, [rsp+88h+arg_20]
0x14000ad3f  shl     rcx, 5
0x14000ad43  mov     [rcx+rdi-8], rax
0x14000ad48  mov     [rbx+8], rdi
0x14000ad4c  lea     rdi, WPP_GLOBAL_Control
0x14000ad53  cmp     cs:gWfpPerProContext, 0
0x14000ad5b  mov     rbx, cs:gWfpGlobal
0x14000ad62  mov     r14, [rsp+88h+arg_0]
0x14000ad6a  jz      short loc_14000AD97
0x14000ad6c  xor     ecx, ecx; ProcNumber
0x14000ad6e  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000ad75  nop     dword ptr [rax+rax+00h]
0x14000ad7a  imul    eax, cs:gWfpPerProContextSize
0x14000ad81  mov     ecx, eax
0x14000ad83  mov     rax, cs:gWfpPerProContext
0x14000ad8a  mov     rdx, [rcx+rax]
0x14000ad8e  cmp     dword ptr [rdx], 4
0x14000ad91  jz      loc_14000AEBB
0x14000ad97  mov     rcx, [rbx+1B0h]; Lock
0x14000ad9e  lea     rdx, [rsp+88h+LockState]; LockState
0x14000ada6  call    cs:__imp_NdisReleaseRWLock
0x14000adad  nop     dword ptr [rax+rax+00h]
0x14000adb2  mov     ebx, [rsp+88h+var_58]
0x14000adb6  test    rsi, rsi
0x14000adb9  jnz     loc_14000AF29
0x14000adbf  test    rbp, rbp
0x14000adc2  jz      short loc_14000ADCC
0x14000adc4  mov     rcx, rbp
0x14000adc7  call    WfpAleDereferenceEndpoint
0x14000adcc  test    rsi, rsi
0x14000adcf  jnz     short loc_14000AE3B
0x14000add1  mov     rax, rsi
0x14000add4  add     rsp, 50h
0x14000add8  pop     r15
0x14000adda  pop     r13
0x14000addc  pop     r12
0x14000adde  pop     rdi
0x14000addf  pop     rsi
0x14000ade0  pop     rbp
0x14000ade1  pop     rbx
0x14000ade2  retn
0x14000ade4  movzx   ecx, [rsp+88h+arg_8]
0x14000adec  cmp     [r9+8], cx
0x14000adf1  jnz     loc_14000AC97
0x14000adf7  test    r12, r12
0x14000adfa  jnz     loc_14000AEC6
0x14000ae00  mov     rax, [rsp+88h+arg_20]
0x14000ae08  test    rax, rax
0x14000ae0b  jz      short loc_14000AE18
0x14000ae0d  cmp     qword ptr [r9+18h], 0
0x14000ae12  jnz     loc_14000AED1
0x14000ae18  test    r12, r12
0x14000ae1b  jnz     loc_14000AF7B
0x14000ae21  mov     [r9+18h], rax
0x14000ae25  movzx   edx, cx
0x14000ae28  mov     r9, rax
0x14000ae2b  mov     rcx, r15
0x14000ae2e  mov     r8d, r13d
0x14000ae31  call    WfpCalloutDiagTraceAssociateFlowStream
0x14000ae36  jmp     loc_14000AD4C
0x14000ae3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae42  cmp     rcx, rdi
0x14000ae45  jz      short loc_14000ADD1
0x14000ae47  cmp     byte ptr [rcx+29h], 2
0x14000ae4b  jb      short loc_14000ADD1
0x14000ae4d  test    dword ptr [rcx+2Ch], 1000h
0x14000ae54  jz      loc_14000ADD1
0x14000ae5a  mov     rcx, [rcx+18h]
0x14000ae5e  lea     r9, aWfpassociateco_0; "WfpAssociateContextToFlowInternal"
0x14000ae65  mov     edx, 0Fh
0x14000ae6a  mov     [rsp+88h+var_68], esi
0x14000ae6e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000ae75  call    WPP_SF_sd
0x14000ae7a  jmp     loc_14000ADD1
0x14000ae7f  lea     r8, [rsp+88h+var_48]
0x14000ae84  mov     edx, 43706657h
0x14000ae89  mov     ecx, 10h
0x14000ae8e  call    WfpPoolAllocNonPaged
0x14000ae93  mov     rsi, rax
0x14000ae96  test    rax, rax
0x14000ae99  jnz     loc_14000AD4C
0x14000ae9f  mov     rbx, [rsp+88h+var_48]
0x14000aea4  xorps   xmm0, xmm0
0x14000aea7  movups  xmmword ptr [rbx], xmm0
0x14000aeaa  mov     [r14], rbx
0x14000aead  test    rbx, rbx
0x14000aeb0  jnz     loc_14000AC77
0x14000aeb6  jmp     loc_14000AC9B
0x14000aebb  mov     dword ptr [rdx], 0
0x14000aec1  jmp     loc_14000AD97
0x14000aec6  cmp     qword ptr [r9+10h], 0
0x14000aecb  jz      loc_14000AE00
0x14000aed1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aed8  lea     rdi, WPP_GLOBAL_Control
0x14000aedf  mov     esi, 40000000h
0x14000aee4  cmp     rcx, rdi
0x14000aee7  jz      loc_14000AD53
0x14000aeed  cmp     byte ptr [rcx+29h], 2
0x14000aef1  jb      loc_14000AD53
0x14000aef7  test    dword ptr [rcx+2Ch], 1000h
0x14000aefe  jz      loc_14000AD53
0x14000af04  mov     rcx, [rcx+18h]
0x14000af08  lea     r9, aWfpassociateco_0; "WfpAssociateContextToFlowInternal"
0x14000af0f  mov     edx, 0Ah
0x14000af14  mov     [rsp+88h+var_68], esi
0x14000af18  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000af1f  call    WPP_SF_sd
0x14000af24  jmp     loc_14000AD53
0x14000af29  test    ebx, ebx
0x14000af2b  jz      loc_14000ADBF
0x14000af31  mov     ecx, r13d
0x14000af34  call    FeDeRefCalloutFlowContext
0x14000af39  jmp     loc_14000ADBF
0x14000af3e  mov     r9d, ebx
0x14000af41  lea     rdx, aWfpassociateco_0; "WfpAssociateContextToFlowInternal"
0x14000af48  mov     r8d, 0C000000Dh
0x14000af4e  call    WfpReportSysErrorAsNtStatus
0x14000af53  mov     rsi, rax
0x14000af56  jmp     loc_14000ADB6
0x14000af5b  mov     r9d, 1
0x14000af61  lea     rdx, aWfpassociateco_0; "WfpAssociateContextToFlowInternal"
0x14000af68  mov     r8d, 0C000000Dh
0x14000af6e  call    WfpReportSysErrorAsNtStatus
0x14000af73  mov     rsi, rax
0x14000af76  jmp     loc_14000AD4C
0x14000af7b  mov     eax, [r9]
0x14000af7e  mov     [r9+10h], r12
0x14000af82  test    al, 1
0x14000af84  jz      loc_140078C66
0x14000af8a  and     eax, 0FFFFFFFEh
0x14000af8d  mov     [r9], eax
0x14000af90  jmp     loc_140078C66
0x140078c66  movzx   edx, cx
0x140078c69  mov     r9, r12
0x140078c6c  mov     rcx, r15
0x140078c6f  mov     r8d, r13d
0x140078c72  call    WfpCalloutDiagTraceAssociateFlow
0x140078c77  nop
0x140078c78  jmp     loc_14000AD4C
```
