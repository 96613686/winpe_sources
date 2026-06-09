# FeNotifyFilterEx

- ea: `0x140038e00`
- end: `0x140039474`
- name: `FeNotifyFilterEx`
- size: `1652`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001b7b0`
- `0x140038dc8`
- `0x140047dc0`

## callees

- `0x1400119a4`
- `0x140011a64`
- `0x140011b70`
- `0x14002d120`
- `0x140038e00`
- `0x14004efd4`
- `0x1400509ac`
- `0x1400668fc`
- `0x140078080`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039000`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400390e8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400392cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039382`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039000`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400390e8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400392cb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140039382`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038fc5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140039290`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038fc5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140039290`
- `NDIS!NdisReleaseRWLock` at `0x14003911f`
- `NDIS!NdisReleaseRWLock` at `0x1400393b5`
- `NDIS!NdisReleaseRWLock` at `0x14003911f`
- `NDIS!NdisReleaseRWLock` at `0x1400393b5`
- `NDIS!NdisAcquireRWLockWrite` at `0x140038fe3`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400392ae`
- `NDIS!NdisAcquireRWLockWrite` at `0x140038fe3`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400392ae`

## pseudocode

```c
__int64 __fastcall FeNotifyFilterEx(unsigned __int16 a1, __int64 a2, __int64 a3, unsigned int a4, char a5)
{
  __int64 v5; // rbx
  void *v6; // rsi
  int v8; // edi
  __int64 v10; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  char v12; // r8
  bool v13; // bp
  char v14; // r15
  char v15; // r14
  bool v16; // r12
  bool v17; // r13
  unsigned int v18; // edi
  PNPAGED_LOOKASIDE_LIST v19; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v21; // rdx
  char v22; // bp
  char v23; // di
  PNPAGED_LOOKASIDE_LIST v24; // rbx
  _DWORD *v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  bool v29; // zf
  int v30; // eax
  int v31; // eax
  void (__fastcall *v32)(_QWORD, __int64); // rax
  PNPAGED_LOOKASIDE_LIST v33; // rdi
  KIRQL v34; // bl
  __int64 v35; // rdx
  bool v36; // bp
  PNPAGED_LOOKASIDE_LIST v37; // rdi
  _DWORD *v38; // rdx
  __int64 v39; // rcx
  char v41; // [rsp+30h] [rbp-58h]
  char v42; // [rsp+31h] [rbp-57h]
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-54h] BYREF
  __int64 v44; // [rsp+38h] [rbp-50h] BYREF
  void *v45; // [rsp+40h] [rbp-48h] BYREF

  v5 = 0;
  v6 = 0;
  v8 = a1;
  v44 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v10 = *(unsigned int *)(a3 + 44);
  v45 = 0;
  FeGetRefCalloutEx(v10, 0, &v44);
  if ( a4 == 2 && (*(_DWORD *)(v44 + 56) & 4) == 0 )
    goto LABEL_114;
  if ( (a5 & 1) != 0 )
  {
    v12 = 0;
    v14 = 0;
    v15 = 0;
    v41 = 0;
    v13 = 0;
  }
  else
  {
    FeGetRefCalloutEx(*(unsigned int *)(a3 + 44), 1, &v45);
    if ( (Feature_Netsec_OffloadCounterFix__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_Netsec_OffloadCounterFix__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_Netsec_OffloadCounterFix__private_IsEnabledDeviceUsageNoInline();
    v6 = v45;
    if ( IsEnabledDeviceUsageNoInline && v45 == gFeCallout )
      goto LABEL_112;
    switch ( v8 )
    {
      case 0:
      case 1:
      case 2:
      case 3:
      case 4:
      case 5:
      case 6:
      case 7:
      case 12:
      case 13:
      case 14:
      case 15:
      case 16:
      case 17:
      case 18:
      case 19:
      case 70:
      case 71:
      case 78:
      case 79:
      case 80:
      case 81:
        v12 = 1;
        break;
      default:
        v12 = 0;
        break;
    }
    v41 = v12;
    v13 = v8 == 20 || v8 == 22 || (unsigned int)(v8 - 66) < 2;
    switch ( v8 )
    {
      case 4:
      case 5:
      case 6:
      case 7:
      case 16:
      case 17:
      case 18:
      case 19:
      case 24:
      case 25:
      case 26:
      case 27:
      case 48:
      case 49:
      case 50:
      case 51:
      case 52:
      case 53:
      case 54:
      case 55:
      case 57:
      case 59:
      case 79:
      case 81:
        v14 = 1;
        break;
      default:
        v14 = 0;
        break;
    }
    switch ( v8 )
    {
      case 0:
      case 1:
      case 2:
      case 3:
      case 12:
      case 13:
      case 14:
      case 15:
      case 24:
      case 25:
      case 26:
      case 27:
      case 44:
      case 45:
      case 46:
      case 47:
      case 52:
      case 53:
      case 54:
      case 55:
      case 56:
      case 58:
      case 78:
      case 80:
        v15 = 1;
        break;
      default:
        v15 = 0;
        break;
    }
  }
  v16 = 0;
  v17 = 0;
  v42 = 0;
  v18 = a4;
  if ( !a4 && (v12 || v13 || v14 || v15) )
  {
    v19 = gWfpGlobal;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v19[1].L.ListHead.Alignment, &LockState, 0);
    if ( CurrentIrql != 2 && gWfpPerProContext )
    {
      v21 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      *(_QWORD *)(v21 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v21 = 4;
    }
    if ( v13 && *(_BYTE *)(v44 + 118) )
      LOBYTE(gWfpGlobal[9].L.Size) = 1;
    v22 = v41;
    if ( v41 )
    {
      if ( ++*((_DWORD *)v6 + 31) == 1 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x40) == 0 )
        v17 = 1;
    }
    if ( v14 )
    {
      if ( ++*((_DWORD *)v6 + 32) == 1 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x100) == 0 )
      {
        v23 = 1;
        v42 = 1;
      }
      else
      {
        v23 = 0;
        v42 = 0;
      }
    }
    else
    {
      v23 = 0;
    }
    if ( v15 )
    {
      if ( ++*((_DWORD *)v6 + 33) == 1 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x200) == 0 )
        v16 = 1;
    }
    v24 = gWfpGlobal;
    if ( gWfpPerProContext )
    {
      v25 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v25 == 4 )
        *v25 = 0;
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v24[1].L.ListHead.Alignment, &LockState);
    if ( v17 )
    {
      v27 = KfdNotifyRscIncompatCalloutAdd(v26);
      v5 = v27;
      if ( v27 )
      {
        v28 = WPP_GLOBAL_Control;
        v29 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_68:
        if ( !v29 && BYTE1(v28->Timer) >= 2u && (HIDWORD(v28->Timer) & 0x1000) != 0 )
          WPP_SF_sd(
            v28->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"FeNotifyFilterEx",
            v5);
        goto LABEL_112;
      }
    }
    if ( v23 )
    {
      v30 = KfdNotifyUsoIncompatCallout(0);
      v5 = v30;
      if ( v30 )
      {
        v28 = WPP_GLOBAL_Control;
        v29 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_68;
      }
    }
    if ( v16 )
    {
      v31 = KfdNotifyUroIncompatCallout(0);
      v5 = v31;
      if ( v31 )
      {
        v28 = WPP_GLOBAL_Control;
        v29 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_68;
      }
    }
    v18 = 0;
  }
  else
  {
    v22 = v41;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64))(v44 + 32))(v18, a2, a3) )
  {
    v28 = WPP_GLOBAL_Control;
    v29 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    v5 = -1071513545;
    goto LABEL_68;
  }
  v32 = *(void (__fastcall **)(_QWORD, __int64))&gWfpGlobal[10].L.Future[6];
  if ( v32 )
  {
    if ( !v18 )
    {
      v32(*(unsigned int *)(a3 + 44), 1);
      v5 = 0;
      goto LABEL_112;
    }
    if ( v18 == 1 )
    {
      v32(*(unsigned int *)(a3 + 44), 0);
LABEL_78:
      if ( v22 || v14 || (v5 = 0, v15) )
      {
        v33 = gWfpGlobal;
        v34 = KeGetCurrentIrql();
        NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v33[1].L.ListHead.Alignment, &LockState, 0);
        if ( v34 != 2 && gWfpPerProContext )
        {
          v35 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          *(_QWORD *)(v35 + 8) = MEMORY[0xFFFFF78000000008];
          *(_DWORD *)v35 = 4;
        }
        v5 = 0;
        if ( v14 )
        {
          v29 = (*((_DWORD *)v6 + 32))-- == 1;
          v36 = v29 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x100) == 0;
        }
        else
        {
          v36 = v42;
        }
        if ( v15 )
        {
          v29 = (*((_DWORD *)v6 + 33))-- == 1;
          v16 = v29 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x200) == 0;
        }
        if ( v41 )
        {
          v29 = (*((_DWORD *)v6 + 31))-- == 1;
          v17 = v29 && *((_DWORD *)v6 + 1) && (*((_DWORD *)v6 + 14) & 0x40) == 0;
        }
        v37 = gWfpGlobal;
        if ( gWfpPerProContext )
        {
          v38 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          if ( *v38 == 4 )
            *v38 = 0;
        }
        NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v37[1].L.ListHead.Alignment, &LockState);
        if ( v36 )
        {
          LOBYTE(v39) = 1;
          KfdNotifyUsoIncompatCallout(v39);
        }
        if ( v16 )
        {
          LOBYTE(v39) = 1;
          KfdNotifyUroIncompatCallout(v39);
        }
        if ( v17 )
          KfdNotifyRscIncompatCalloutDelete();
      }
      goto LABEL_112;
    }
  }
  v5 = 0;
  if ( v18 == 1 )
    goto LABEL_78;
LABEL_112:
  if ( v6 )
    _InterlockedDecrement((volatile signed __int32 *)v6 + 16);
LABEL_114:
  if ( v44 )
    _InterlockedDecrement((volatile signed __int32 *)(v44 + 64));
  if ( v5
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"FeNotifyFilterEx",
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140038e00  mov     r11, rsp
0x140038e03  mov     [r11+20h], r9d
0x140038e07  mov     [r11+18h], r8
0x140038e0b  mov     [r11+10h], rdx
0x140038e0f  push    rbx
0x140038e10  sub     rsp, 80h
0x140038e17  mov     [r11+8], rbp
0x140038e1b  xor     eax, eax
0x140038e1d  mov     [r11-10h], rsi
0x140038e21  xor     ebx, ebx
0x140038e23  mov     [r11-18h], rdi
0x140038e27  xor     esi, esi
0x140038e29  mov     [r11-30h], r14
0x140038e2d  xor     edx, edx
0x140038e2f  mov     r14, r8
0x140038e32  movzx   edi, cx
0x140038e35  lea     r8, [r11-50h]
0x140038e39  mov     [r11-50h], rbx
0x140038e3d  mov     ebp, r9d
0x140038e40  mov     word ptr [rsp+88h+LockState.OldIrql], ax
0x140038e45  mov     [rsp+88h+LockState.Flags], al
0x140038e49  mov     ecx, [r14+2Ch]
0x140038e4d  mov     [r11-48h], rsi
0x140038e51  call    FeGetRefCalloutEx
0x140038e56  lea     rdx, WPP_GLOBAL_Control
0x140038e5d  cmp     ebp, 2
0x140038e60  jnz     short loc_140038E72
0x140038e62  mov     rax, [rsp+88h+var_50]
0x140038e67  mov     eax, [rax+38h]
0x140038e6a  test    al, 4
0x140038e6c  jz      loc_140039402
0x140038e72  test    [rsp+88h+arg_20], 1
0x140038e7a  mov     [rsp+88h+var_38], r15
0x140038e7f  jnz     loc_140038F6E
0x140038e85  mov     ecx, [r14+2Ch]
0x140038e89  lea     r8, [rsp+88h+var_48]
0x140038e8e  mov     edx, 1
0x140038e93  call    FeGetRefCalloutEx
0x140038e98  mov     eax, cs:Feature_Netsec_OffloadCounterFix__private_featureState
0x140038e9e  test    al, 10h
0x140038ea0  jz      short loc_140038EA7
0x140038ea2  and     eax, 1
0x140038ea5  jmp     short loc_140038EAC
0x140038ea7  call    Feature_Netsec_OffloadCounterFix__private_IsEnabledDeviceUsageNoInline
0x140038eac  mov     rsi, [rsp+88h+var_48]
0x140038eb1  test    eax, eax
0x140038eb3  jz      short loc_140038EC2
0x140038eb5  cmp     rsi, cs:gFeCallout
0x140038ebc  jz      loc_1400393ED
0x140038ec2  lea     r9, cs:140000000h
0x140038ec9  mov     rdx, rdi
0x140038ecc  cmp     edi, 51h; switch 82 cases
0x140038ecf  ja      short def_140038EE8; jumptable 0000000140038EE8 default case, cases 8-11,20-69,72-77
0x140038ed1  movsxd  rax, edx
0x140038ed4  movzx   eax, ds:(byte_14008FEF9 - 140000000h)[r9+rax]
0x140038edd  mov     ecx, ds:(jpt_140038EE8 - 140000000h)[r9+rax*4]
0x140038ee5  add     rcx, r9
0x140038ee8  jmp     rcx; switch jump
0x140038eee  mov     r8b, 1; jumptable 0000000140038EE8 cases 0-7,12-19,70,71,78-81
0x140038ef1  jmp     short loc_140038EF6
0x140038ef3  xor     r8b, r8b; jumptable 0000000140038EE8 default case, cases 8-11,20-69,72-77
0x140038ef6  mov     ecx, edx
0x140038ef8  mov     [rsp+88h+var_58], r8b
0x140038efd  sub     ecx, 14h
0x140038f00  jz      short loc_140038F16
0x140038f02  sub     ecx, 2
0x140038f05  jz      short loc_140038F16
0x140038f07  sub     ecx, 2Ch ; ','
0x140038f0a  jz      short loc_140038F16
0x140038f0c  cmp     ecx, 1
0x140038f0f  jz      short loc_140038F16
0x140038f11  xor     bpl, bpl
0x140038f14  jmp     short loc_140038F19
0x140038f16  mov     bpl, 1
0x140038f19  lea     eax, [rdi-4]; switch 78 cases
0x140038f1c  cmp     eax, 4Dh
0x140038f1f  ja      short def_140038F37; jumptable 0000000140038F37 default case, cases 8-15,20-23,28-47,56,58,60-78,80
0x140038f21  cdqe
0x140038f23  movzx   eax, ds:(byte_14008FF53 - 140000000h)[r9+rax]
0x140038f2c  mov     ecx, ds:(jpt_140038F37 - 140000000h)[r9+rax*4]
0x140038f34  add     rcx, r9
0x140038f37  jmp     rcx; switch jump
0x140038f3d  mov     r15b, 1; jumptable 0000000140038F37 cases 4-7,16-19,24-27,48-55,57,59,79,81
0x140038f40  jmp     short loc_140038F45
0x140038f42  xor     r15b, r15b; jumptable 0000000140038F37 default case, cases 8-15,20-23,28-47,56,58,60-78,80
0x140038f45  cmp     edx, 50h; switch 81 cases
0x140038f48  ja      short def_140038F5E; jumptable 0000000140038F5E default case, cases 4-11,16-23,28-43,48-51,57,59-77,79
0x140038f4a  movzx   eax, ds:(byte_14008FFA9 - 140000000h)[r9+rdi]
0x140038f53  mov     ecx, ds:(jpt_140038F5E - 140000000h)[r9+rax*4]
0x140038f5b  add     rcx, r9
0x140038f5e  jmp     rcx; switch jump
0x140038f64  mov     r14b, 1; jumptable 0000000140038F5E cases 0-3,12-15,24-27,44-47,52-56,58,78,80
0x140038f67  jmp     short loc_140038F7F
0x140038f69  xor     r14b, r14b; jumptable 0000000140038F5E default case, cases 4-11,16-23,28-43,48-51,57,59-77,79
0x140038f6c  jmp     short loc_140038F7F
0x140038f6e  xor     r8b, r8b
0x140038f71  xor     r15b, r15b
0x140038f74  xor     r14b, r14b
0x140038f77  mov     [rsp+88h+var_58], r8b
0x140038f7c  xor     bpl, bpl
0x140038f7f  xor     dil, dil
0x140038f82  mov     [rsp+88h+var_20], r12
0x140038f87  mov     [rsp+88h+var_28], r13
0x140038f8c  xor     r12b, r12b
0x140038f8f  xor     r13b, r13b
0x140038f92  mov     [rsp+88h+var_57], dil
0x140038f97  mov     edi, [rsp+88h+arg_18]
0x140038f9e  test    edi, edi
0x140038fa0  jnz     loc_14003919E
0x140038fa6  test    r8b, r8b
0x140038fa9  jnz     short loc_140038FBE
0x140038fab  test    bpl, bpl
0x140038fae  jnz     short loc_140038FBE
0x140038fb0  test    r15b, r15b
0x140038fb3  jnz     short loc_140038FBE
0x140038fb5  test    r14b, r14b
0x140038fb8  jz      loc_14003919E
0x140038fbe  mov     rdi, cs:gWfpGlobal
0x140038fc5  call    cs:__imp_KeGetCurrentIrql
0x140038fcc  nop     dword ptr [rax+rax+00h]
0x140038fd1  mov     rcx, [rdi+80h]; Lock
0x140038fd8  lea     rdx, [rsp+88h+LockState]; LockState
0x140038fdd  xor     r8d, r8d; Flags
0x140038fe0  movzx   ebx, al
0x140038fe3  call    cs:__imp_NdisAcquireRWLockWrite
0x140038fea  nop     dword ptr [rax+rax+00h]
0x140038fef  cmp     bl, 2
0x140038ff2  jz      short loc_140039034
0x140038ff4  cmp     cs:gWfpPerProContext, 0
0x140038ffc  jz      short loc_140039034
0x140038ffe  xor     ecx, ecx; ProcNumber
0x140039000  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140039007  nop     dword ptr [rax+rax+00h]
0x14003900c  imul    eax, cs:gWfpPerProContextSize
0x140039013  mov     ecx, eax
0x140039015  mov     rax, cs:gWfpPerProContext
0x14003901c  mov     rdx, [rcx+rax]
0x140039020  mov     rax, ds:0FFFFF78000000008h
0x14003902a  mov     [rdx+8], rax
0x14003902e  mov     dword ptr [rdx], 4
0x140039034  test    bpl, bpl
0x140039037  jz      short loc_140039052
0x140039039  mov     rax, [rsp+88h+var_50]
0x14003903e  cmp     [rax+76h], r12b
0x140039042  jz      short loc_140039052
0x140039044  mov     rax, cs:gWfpGlobal
0x14003904b  mov     byte ptr [rax+4ACh], 1
0x140039052  movzx   ebp, [rsp+88h+var_58]
0x140039057  test    bpl, bpl
0x14003905a  jz      short loc_140039075
0x14003905c  inc     dword ptr [rsi+7Ch]
0x14003905f  cmp     dword ptr [rsi+7Ch], 1
0x140039063  jnz     short loc_140039075
0x140039065  cmp     dword ptr [rsi+4], 0
0x140039069  jz      short loc_140039075
0x14003906b  mov     eax, [rsi+38h]
0x14003906e  test    al, 40h
0x140039070  jnz     short loc_140039075
0x140039072  mov     r13b, 1
0x140039075  test    r15b, r15b
0x140039078  jz      short loc_1400390AC
0x14003907a  inc     dword ptr [rsi+80h]
0x140039080  cmp     dword ptr [rsi+80h], 1
0x140039087  jnz     short loc_1400390A2
0x140039089  cmp     dword ptr [rsi+4], 0
0x14003908d  jz      short loc_1400390A2
0x14003908f  test    dword ptr [rsi+38h], 100h
0x140039096  jnz     short loc_1400390A2
0x140039098  mov     dil, 1
0x14003909b  mov     [rsp+88h+var_57], dil
0x1400390a0  jmp     short loc_1400390AF
0x1400390a2  xor     dil, dil
0x1400390a5  mov     [rsp+88h+var_57], dil
0x1400390aa  jmp     short loc_1400390AF
0x1400390ac  xor     dil, dil
0x1400390af  test    r14b, r14b
0x1400390b2  jz      short loc_1400390D5
0x1400390b4  inc     dword ptr [rsi+84h]
0x1400390ba  cmp     dword ptr [rsi+84h], 1
0x1400390c1  jnz     short loc_1400390D5
0x1400390c3  cmp     dword ptr [rsi+4], 0
0x1400390c7  jz      short loc_1400390D5
0x1400390c9  test    dword ptr [rsi+38h], 200h
0x1400390d0  jnz     short loc_1400390D5
0x1400390d2  mov     r12b, 1
0x1400390d5  cmp     cs:gWfpPerProContext, 0
0x1400390dd  mov     rbx, cs:gWfpGlobal
0x1400390e4  jz      short loc_140039113
0x1400390e6  xor     ecx, ecx; ProcNumber
0x1400390e8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400390ef  nop     dword ptr [rax+rax+00h]
0x1400390f4  imul    eax, cs:gWfpPerProContextSize
0x1400390fb  mov     ecx, eax
0x1400390fd  mov     rax, cs:gWfpPerProContext
0x140039104  mov     rdx, [rcx+rax]
0x140039108  cmp     dword ptr [rdx], 4
0x14003910b  jnz     short loc_140039113
0x14003910d  mov     dword ptr [rdx], 0
0x140039113  mov     rcx, [rbx+80h]; Lock
0x14003911a  lea     rdx, [rsp+88h+LockState]; LockState
0x14003911f  call    cs:__imp_NdisReleaseRWLock
0x140039126  nop     dword ptr [rax+rax+00h]
0x14003912b  test    r13b, r13b
0x14003912e  jz      short loc_140039152
0x140039130  call    KfdNotifyRscIncompatCalloutAdd
0x140039135  movsxd  rbx, eax
0x140039138  test    eax, eax
0x14003913a  jz      short loc_140039152
0x14003913c  mov     rcx, cs:WPP_GLOBAL_Control
0x140039143  lea     rax, WPP_GLOBAL_Control
0x14003914a  cmp     rcx, rax
0x14003914d  jmp     loc_1400391EB
0x140039152  test    dil, dil
0x140039155  jz      short loc_140039178
0x140039157  xor     ecx, ecx
0x140039159  call    KfdNotifyUsoIncompatCallout
0x14003915e  movsxd  rbx, eax
0x140039161  test    eax, eax
0x140039163  jz      short loc_140039178
0x140039165  mov     rcx, cs:WPP_GLOBAL_Control
0x14003916c  lea     rax, WPP_GLOBAL_Control
0x140039173  cmp     rcx, rax
0x140039176  jmp     short loc_1400391EB
0x140039178  test    r12b, r12b
0x14003917b  jz      short loc_1400391A5
0x14003917d  xor     ecx, ecx
0x14003917f  call    KfdNotifyUroIncompatCallout
0x140039184  movsxd  rbx, eax
0x140039187  test    eax, eax
0x140039189  jz      short loc_1400391A5
0x14003918b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039192  lea     rax, WPP_GLOBAL_Control
0x140039199  cmp     rcx, rax
0x14003919c  jmp     short loc_1400391EB
0x14003919e  movzx   ebp, [rsp+88h+var_58]
0x1400391a3  jmp     short loc_1400391AC
0x1400391a5  mov     edi, [rsp+88h+arg_18]
0x1400391ac  mov     rax, [rsp+88h+var_50]
0x1400391b1  mov     ecx, edi
0x1400391b3  mov     rbx, [rsp+88h+arg_10]
0x1400391bb  mov     rdx, [rsp+88h+arg_8]
0x1400391c3  mov     r8, rbx
0x1400391c6  mov     rax, [rax+20h]
0x1400391ca  call    _guard_dispatch_icall
0x1400391cf  test    eax, eax
0x1400391d1  jz      short loc_14003922D
0x1400391d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391da  lea     rax, WPP_GLOBAL_Control
0x1400391e1  cmp     rcx, rax
0x1400391e4  mov     rbx, 0FFFFFFFFC0220037h
0x1400391eb  jz      loc_1400393E3
0x1400391f1  cmp     byte ptr [rcx+29h], 2
0x1400391f5  jb      loc_1400393E3
0x1400391fb  test    dword ptr [rcx+2Ch], 1000h
0x140039202  jz      loc_1400393E3
0x140039208  mov     rcx, [rcx+18h]
0x14003920c  lea     r9, aFenotifyfilter; "FeNotifyFilterEx"
0x140039213  mov     edx, 0Ah
0x140039218  mov     [rsp+88h+var_68], ebx
0x14003921c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140039223  call    WPP_SF_sd
0x140039228  jmp     loc_1400393E3
0x14003922d  mov     rax, cs:gWfpGlobal
0x140039234  mov     rax, [rax+570h]
0x14003923b  test    rax, rax
0x14003923e  jz      short loc_140039269
0x140039240  test    edi, edi
0x140039242  jnz     short loc_140039258
0x140039244  mov     ecx, [rbx+2Ch]
0x140039247  mov     edx, 1
0x14003924c  call    _guard_dispatch_icall
0x140039251  xor     ebx, ebx
0x140039253  jmp     loc_1400393E3
0x140039258  cmp     edi, 1
0x14003925b  jnz     short loc_140039269
0x14003925d  mov     ecx, [rbx+2Ch]
0x140039260  xor     edx, edx
0x140039262  call    _guard_dispatch_icall
0x140039267  jmp     short loc_140039274
0x140039269  xor     ebx, ebx
0x14003926b  cmp     edi, 1
0x14003926e  jnz     loc_1400393E3
0x140039274  test    bpl, bpl
0x140039277  jnz     short loc_140039289
0x140039279  test    r15b, r15b
0x14003927c  jnz     short loc_140039289
0x14003927e  xor     ebx, ebx
0x140039280  test    r14b, r14b
0x140039283  jz      loc_1400393E3
0x140039289  mov     rdi, cs:gWfpGlobal
0x140039290  call    cs:__imp_KeGetCurrentIrql
0x140039297  nop     dword ptr [rax+rax+00h]
0x14003929c  mov     rcx, [rdi+80h]; Lock
0x1400392a3  lea     rdx, [rsp+88h+LockState]; LockState
0x1400392a8  xor     r8d, r8d; Flags
0x1400392ab  movzx   ebx, al
0x1400392ae  call    cs:__imp_NdisAcquireRWLockWrite
0x1400392b5  nop     dword ptr [rax+rax+00h]
0x1400392ba  cmp     bl, 2
0x1400392bd  jz      short loc_1400392FF
  ... truncated ...
```
