# BfPreDirectoryControl

- ea: `0x140024e50`
- end: `0x14002576f`
- name: `BfPreDirectoryControl`
- size: `2335`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callees

- `0x140001348`
- `0x140002740`
- `0x140003140`
- `0x1400060f0`
- `0x14000f77c`
- `0x140014324`
- `0x1400149a8`
- `0x140017f00`
- `0x14001ad80`
- `0x1400207f0`
- `0x140020a98`
- `0x140020c54`
- `0x140020d60`
- `0x140020f10`
- `0x140024958`
- `0x140024a64`
- `0x140024e50`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400252b8`
- `ntoskrnl!ProbeForRead` at `0x1400252b8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025230`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025230`
- `ntoskrnl!KeSetEvent` at `0x14002572e`
- `ntoskrnl!KeSetEvent` at `0x14002572e`
- `FLTMGR!FltLockUserBuffer` at `0x1400251cd`
- `FLTMGR!FltLockUserBuffer` at `0x1400251cd`
- `FLTMGR!FltReleaseContext` at `0x140025742`
- `FLTMGR!FltReleaseContext` at `0x140025742`

## pseudocode

```c
__int64 __fastcall BfPreDirectoryControl(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  char *v4; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  unsigned int Length; // edi
  unsigned int v7; // r15d
  NTSTATUS EnumerationContext; // edi
  int LowPart; // r13d
  bool v10; // zf
  int v11; // ecx
  int SetDirectoryEnumerationHandleContext; // eax
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // rdi
  int MappingList; // eax
  char v19; // dl
  char *i; // rax
  int v21; // eax
  int v22; // edx
  int v23; // r9d
  PMDL v24; // r12
  NTSTATUS v25; // eax
  PVOID MappedSystemVa; // r9
  FLT_CALLBACK_DATA_FLAGS v27; // r14d
  UCHAR v28; // di
  NTSTATUS v29; // r12d
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  PVOID v33; // rcx
  PVOID *v34; // rax
  char v36; // [rsp+30h] [rbp-C8h]
  __int64 v37; // [rsp+38h] [rbp-C0h]
  UCHAR OperationFlags; // [rsp+50h] [rbp-A8h]
  _WORD v39[5]; // [rsp+52h] [rbp-A6h] BYREF
  FLT_CALLBACK_DATA_FLAGS v40; // [rsp+5Ch] [rbp-9Ch]
  unsigned int v41; // [rsp+60h] [rbp-98h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-90h] BYREF
  _QWORD *v43; // [rsp+70h] [rbp-88h] BYREF
  PVOID Entry; // [rsp+78h] [rbp-80h]
  volatile void *v45; // [rsp+80h] [rbp-78h]
  int v46; // [rsp+88h] [rbp-70h] BYREF
  volatile void *Address; // [rsp+90h] [rbp-68h]
  NTSTATUS v48; // [rsp+98h] [rbp-60h]
  int v49; // [rsp+9Ch] [rbp-5Ch]
  __int64 v50; // [rsp+A0h] [rbp-58h] BYREF
  const PFLT_IO_PARAMETER_BLOCK *p_Iopb; // [rsp+A8h] [rbp-50h]
  int *v52; // [rsp+B0h] [rbp-48h] BYREF
  _QWORD **v53; // [rsp+B8h] [rbp-40h]
  PMDL MemoryDescriptorList; // [rsp+C0h] [rbp-38h]
  const PFLT_IO_PARAMETER_BLOCK *v55; // [rsp+C8h] [rbp-30h]
  char v57; // [rsp+118h] [rbp+20h]

  v41 = 0;
  v46 = 0;
  v45 = 0;
  v50 = 0;
  v4 = 0;
  Context = 0;
  v52 = &v46;
  v53 = &v43;
  Entry = &v43;
  v43 = &v43;
  *(_WORD *)((char *)v39 + 1) = 0;
  p_Iopb = &CallbackData->Iopb;
  Iopb = CallbackData->Iopb;
  Length = Iopb->Parameters.Read.Length;
  v10 = (CallbackData->Flags & 8) == 0;
  v40 = CallbackData->Flags & 8;
  v57 = v10;
  if ( Length > 0x10000 )
    Length = 0x10000;
  *(_DWORD *)&v39[3] = Length;
  v7 = 1;
  if ( !Iopb->TargetFileObject )
  {
    EnumerationContext = 0;
    goto LABEL_95;
  }
  if ( Iopb->MinorFunction != 1 )
  {
LABEL_91:
    v32 = BfCheckAndSwitchTarget(CallbackData);
    EnumerationContext = v32;
    if ( v32 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_95;
    v23 = 49;
    LODWORD(v37) = v32;
    v36 = -76;
    goto LABEL_94;
  }
  LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
  v49 = LowPart;
  if ( LowPart > 60 )
  {
    if ( LowPart != 63 && LowPart != 78 && LowPart != 79 )
    {
      v11 = LowPart - 80;
      v10 = LowPart == 80;
      goto LABEL_17;
    }
  }
  else if ( LowPart != 60 && LowPart != 1 && LowPart != 2 && LowPart != 3 && LowPart != 12 )
  {
    v11 = LowPart - 37;
    v10 = LowPart == 37;
LABEL_17:
    if ( !v10 && v11 != 1 )
    {
      EnumerationContext = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(Iopb) = 2;
        WPP_RECORDER_SF_sDD(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Iopb,
          12,
          48,
          (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
          165,
          LowPart);
      }
      goto LABEL_95;
    }
  }
  OperationFlags = Iopb->OperationFlags;
  Address = Iopb->Parameters.Create.EaBuffer;
  MemoryDescriptorList = Iopb->Parameters.QueryEa.MdlAddress;
  SetDirectoryEnumerationHandleContext = BfGetSetDirectoryEnumerationHandleContext(a2, &v39[1], &Context);
  v4 = (char *)Context;
  if ( SetDirectoryEnumerationHandleContext < 0 )
    goto LABEL_91;
  v55 = &CallbackData->Iopb;
  if ( (CallbackData->Iopb->OperationFlags & 1) != 0 )
  {
    *((_DWORD *)Context + 21) = 0;
    v13 = (_QWORD *)*((_QWORD *)v4 + 11);
    if ( v13 )
    {
      while ( 1 )
      {
        v14 = (_QWORD *)*v13;
        if ( *v13 )
          break;
        v15 = v13 + 1;
        v14 = (_QWORD *)v13[1];
        if ( v14 )
        {
LABEL_27:
          v13 = v14;
          *v15 = 0;
        }
        else
        {
          v16 = v13[2];
          BfReturnedWalkContextAvlDeleteFunction(v13, 0);
          v17 = v16 & 0xFFFFFFFFFFFFFFFCuLL;
          if ( !v17 )
          {
            Length = *(_DWORD *)&v39[3];
            goto LABEL_31;
          }
          v13 = (_QWORD *)v17;
        }
      }
      v15 = v13;
      goto LABEL_27;
    }
LABEL_31:
    *((_QWORD *)v4 + 11) = 0;
    if ( v4[112] )
    {
      BfFreeEnumerationContextList(v4 + 96);
      v4[112] = 0;
    }
  }
  MappingList = BfGetMappingList(CallbackData, (__int64)v39);
  if ( (int)(MappingList + 0x80000000) >= 0 && MappingList != -1073741766 )
    goto LABEL_91;
  v19 = 1;
  for ( i = (char *)*((_QWORD *)v4 + 12); i != v4 + 96; i = *(char **)i )
  {
    if ( *((_DWORD *)i + 12) )
    {
      v19 = 0;
      break;
    }
  }
  if ( v43 == &v43 && v19 && (*((_DWORD *)v4 + 20) & 1) == 0 )
    goto LABEL_91;
  if ( !(unsigned __int8)BfMapShadowFileObjectToReal(
                           *(PFLT_INSTANCE *)(a2 + 24),
                           *(PFILE_OBJECT *)(a2 + 32),
                           v4,
                           (__int64)&v50,
                           0) )
  {
    v45 = *(volatile void **)(a2 + 24);
    v50 = *(_QWORD *)(a2 + 32);
  }
  if ( v43 == &v43
    || (EnumerationContext = BfCreateEnumerationContext(0, 0, 0, 0, Length, (__int64)v4), EnumerationContext >= 0) )
  {
    v21 = BfSetupEnumerationContexts(
            CallbackData,
            *(_QWORD *)(a2 + 24),
            *(_QWORD *)(a2 + 32),
            v45,
            v50,
            *(_DWORD *)&v39[3],
            v4);
    EnumerationContext = v21;
    if ( v21 >= 0 )
    {
      v24 = MemoryDescriptorList;
      if ( MemoryDescriptorList )
      {
        v25 = FltLockUserBuffer(CallbackData);
        EnumerationContext = v25;
        if ( v25 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_95;
          v23 = 41;
          LODWORD(v37) = v25;
          v36 = -21;
          goto LABEL_94;
        }
        if ( (v24->MdlFlags & 5) != 0 )
          MappedSystemVa = v24->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000010u);
        Address = MappedSystemVa;
        if ( !MappedSystemVa )
        {
          EnumerationContext = -1073741801;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_95;
          v23 = 42;
          LODWORD(v37) = -1073741801;
          v36 = -12;
          goto LABEL_94;
        }
        v45 = MappedSystemVa;
        v57 = 0;
      }
      else
      {
        LODWORD(MappedSystemVa) = (_DWORD)Address;
        v45 = Address;
        if ( !v40 )
          ProbeForRead(Address, *(unsigned int *)&v39[3], 1u);
      }
      v27 = 0;
      v40 = 0;
      v28 = OperationFlags;
      LOBYTE(v39[0]) = OperationFlags;
      v29 = -1073741809;
      while ( 1 )
      {
        if ( v27 + v46 >= *(_DWORD *)&v39[3] )
        {
LABEL_80:
          if ( v52 )
          {
            if ( ((unsigned __int8)v57 & (unsigned __int8)-(v27 != 0)) != 0 )
              RtlWriteULongToUser(v52, 0);
            else
              *v52 = 0;
          }
          *((_DWORD *)v4 + 21) += v27;
          if ( HIBYTE(v39[0]) )
          {
            v29 = -2147483643;
          }
          else if ( v27 )
          {
            v29 = 0;
          }
          else if ( *((_DWORD *)v4 + 21) )
          {
            v29 = -2147483642;
          }
          CallbackData->IoStatus.Status = v29;
          CallbackData->IoStatus.Information = v27;
          goto LABEL_97;
        }
        if ( v43 != v53 )
        {
          v30 = *((_QWORD *)v4 + 12);
          if ( !*(_DWORD *)(v30 + 48) )
            BfConvertWalkContextToDirectoryEnumeration(
              &v43,
              (unsigned int)LowPart,
              (*p_Iopb)->Parameters.QueryEa.EaList,
              v4,
              v30,
              (char *)v39 + 1);
        }
        LOBYTE(MappedSystemVa) = v28;
        v31 = BfExecuteEnumerationContexts(
                LowPart,
                (*p_Iopb)->Parameters.QueryEa.EaList,
                (*p_Iopb)->Parameters.Create.EaLength,
                (_DWORD)MappedSystemVa,
                (__int64)v4);
        EnumerationContext = v31;
        if ( v31 < 0 && (unsigned int)(v31 + 2147483643) > 1 && v31 != -1073741809 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_95;
          v23 = 44;
          LODWORD(v37) = v31;
          v36 = 67;
          goto LABEL_94;
        }
        EnumerationContext = BfMergeEnumerationContexts(
                               (unsigned int)LowPart,
                               (__int64)v4,
                               v57,
                               OperationFlags & 2,
                               *(_DWORD *)&v39[3] - v27,
                               (__int64)Address + v27,
                               &v41,
                               &v52);
        v48 = EnumerationContext;
        if ( EnumerationContext < 0 )
          break;
        if ( !v41 )
          goto LABEL_80;
        v27 += v41;
        v40 = v27;
        if ( (OperationFlags & 2) != 0 )
          goto LABEL_80;
        OperationFlags &= ~1u;
        LOBYTE(v39[0]) = OperationFlags;
        v28 = OperationFlags;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_95;
      v23 = 46;
      LODWORD(v37) = EnumerationContext;
      v36 = 95;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_95;
      v23 = 40;
      LODWORD(v37) = v21;
      v36 = -37;
    }
LABEL_94:
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      12,
      v23,
      (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
      v36,
      v37);
  }
LABEL_95:
  if ( EnumerationContext < 0 )
  {
    CallbackData->IoStatus.Status = EnumerationContext;
    CallbackData->IoStatus.Information = 0;
LABEL_97:
    v7 = 4;
  }
  while ( v43 != v53 )
  {
    v33 = Entry;
    if ( *(_QWORD ***)Entry != v53 || (v34 = (PVOID *)*((_QWORD *)Entry + 1), *v34 != Entry) )
      __fastfail(3u);
    Entry = (PVOID)*((_QWORD *)Entry + 1);
    *v34 = &v43;
    BfDereferenceMappingListEntry(v33);
  }
  if ( LOBYTE(v39[1]) )
    KeSetEvent((PRKEVENT)(v4 + 128), 0, 0);
  if ( v4 )
    FltReleaseContext(v4);
  return v7;
}

```

## disassembly

```asm
0x140024e50  mov     r11, rsp
0x140024e53  mov     [r11+10h], rbx
0x140024e57  mov     [r11+18h], rsi
0x140024e5b  mov     [r11+8], rcx
0x140024e5f  push    rdi
0x140024e60  push    r12
0x140024e62  push    r13
0x140024e64  push    r14
0x140024e66  push    r15
0x140024e68  sub     rsp, 0D0h
0x140024e6f  mov     r12, rdx
0x140024e72  mov     r14, rcx
0x140024e75  xor     ebx, ebx
0x140024e77  mov     [rsp+0F8h+var_98], ebx
0x140024e7b  mov     [r11-70h], ebx
0x140024e7f  mov     [r11-78h], rbx
0x140024e83  mov     [r11-58h], rbx
0x140024e87  mov     esi, ebx
0x140024e89  mov     [rsp+0F8h+Context], rbx
0x140024e8e  lea     rax, [r11-70h]
0x140024e92  mov     [r11-48h], rax
0x140024e96  lea     rax, [rsp+0F8h+var_88]
0x140024e9b  mov     [rsp+0F8h+var_40], rax
0x140024ea3  lea     rax, [rsp+0F8h+var_88]
0x140024ea8  mov     [r11-80h], rax
0x140024eac  lea     rax, [rsp+0F8h+var_88]
0x140024eb1  mov     [rsp+0F8h+var_88], rax
0x140024eb6  mov     [rsp+0F8h+var_A6+1], bl
0x140024eba  mov     [rsp+0F8h+var_A6+2], bl
0x140024ebe  lea     rax, [rcx+10h]
0x140024ec2  mov     [rsp+0F8h+var_50], rax
0x140024eca  mov     rdx, [rax]
0x140024ecd  mov     edi, [rdx+18h]
0x140024ed0  mov     eax, [rcx]
0x140024ed2  and     eax, 8
0x140024ed5  mov     [rsp+0F8h+var_9C], eax
0x140024ed9  setz    byte ptr [r11+20h]
0x140024ede  mov     eax, 10000h
0x140024ee3  cmp     edi, eax
0x140024ee5  cmova   edi, eax
0x140024ee8  mov     dword ptr [rsp+0F8h+var_A6+6], edi
0x140024eec  lea     r15d, [rbx+1]
0x140024ef0  cmp     [rdx+8], rbx
0x140024ef4  jnz     short loc_140024EFD
0x140024ef6  mov     edi, ebx
0x140024ef8  jmp     loc_1400256C6
0x140024efd  cmp     [rdx+5], r15b
0x140024f01  jnz     loc_14002565D
0x140024f07  mov     r13d, [rdx+28h]
0x140024f0b  mov     [rsp+0F8h+var_5C], r13d
0x140024f13  cmp     r13d, 3Ch ; '<'
0x140024f17  jg      short loc_140024F47
0x140024f19  jz      loc_140024FBF
0x140024f1f  mov     ecx, r13d
0x140024f22  sub     ecx, r15d
0x140024f25  jz      loc_140024FBF
0x140024f2b  sub     ecx, r15d
0x140024f2e  jz      loc_140024FBF
0x140024f34  sub     ecx, r15d
0x140024f37  jz      loc_140024FBF
0x140024f3d  sub     ecx, 9
0x140024f40  jz      short loc_140024FBF
0x140024f42  sub     ecx, 19h
0x140024f45  jmp     short loc_140024F5C
0x140024f47  mov     ecx, r13d
0x140024f4a  sub     ecx, 3Fh ; '?'
0x140024f4d  jz      short loc_140024FBF
0x140024f4f  sub     ecx, 0Fh
0x140024f52  jz      short loc_140024FBF
0x140024f54  sub     ecx, r15d
0x140024f57  jz      short loc_140024FBF
0x140024f59  sub     ecx, r15d
0x140024f5c  jz      short loc_140024FBF
0x140024f5e  cmp     ecx, r15d
0x140024f61  jz      short loc_140024FBF
0x140024f63  mov     edi, ebx
0x140024f65  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024f6c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024f73  jz      loc_1400256C6
0x140024f79  mov     r9d, 30h ; '0'
0x140024f7f  mov     dword ptr [rsp+0F8h+var_C0], r13d
0x140024f84  mov     dword ptr [rsp+0F8h+var_C8], 0CA5h
0x140024f8c  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140024f93  mov     qword ptr [rsp+0F8h+Priority], rax
0x140024f98  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x140024f9f  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x140024fa4  lea     r8d, [r9-24h]
0x140024fa8  mov     dl, 2
0x140024faa  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fb1  mov     rcx, [rcx+40h]
0x140024fb5  call    WPP_RECORDER_SF_sDD
0x140024fba  jmp     loc_1400256C6
0x140024fbf  mov     al, [rdx+6]
0x140024fc2  mov     [rsp+0F8h+var_A8], al
0x140024fc6  mov     rax, [rdx+38h]
0x140024fca  mov     [rsp+0F8h+Address], rax
0x140024fd2  mov     rcx, [rdx+40h]
0x140024fd6  mov     [rsp+0F8h+MemoryDescriptorList], rcx
0x140024fde  lea     r8, [rsp+0F8h+Context]
0x140024fe3  lea     rdx, [rsp+0F8h+var_A6+2]
0x140024fe8  mov     rcx, r12
0x140024feb  call    BfGetSetDirectoryEnumerationHandleContext
0x140024ff0  mov     rsi, [rsp+0F8h+Context]
0x140024ff5  test    eax, eax
0x140024ff7  js      loc_14002565D
0x140024ffd  lea     rax, [r14+10h]
0x140025001  mov     [rsp+0F8h+var_30], rax
0x140025009  mov     rax, [rax]
0x14002500c  test    [rax+6], r15b
0x140025010  jz      short loc_14002506E
0x140025012  mov     [rsi+54h], ebx
0x140025015  mov     rcx, [rsi+58h]
0x140025019  test    rcx, rcx
0x14002501c  jz      short loc_140025059
0x14002501e  mov     rdx, [rcx]
0x140025021  test    rdx, rdx
0x140025024  jz      short loc_14002502B
0x140025026  mov     rax, rcx
0x140025029  jmp     short loc_140025037
0x14002502b  lea     rax, [rcx+8]
0x14002502f  mov     rdx, [rax]
0x140025032  test    rdx, rdx
0x140025035  jz      short loc_14002503F
0x140025037  mov     rcx, rdx
0x14002503a  mov     [rax], rbx
0x14002503d  jmp     short loc_14002501E
0x14002503f  mov     rdi, [rcx+10h]
0x140025043  xor     edx, edx
0x140025045  call    BfReturnedWalkContextAvlDeleteFunction
0x14002504a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14002504e  jz      short loc_140025055
0x140025050  mov     rcx, rdi
0x140025053  jmp     short loc_14002501E
0x140025055  mov     edi, dword ptr [rsp+0F8h+var_A6+6]
0x140025059  mov     [rsi+58h], rbx
0x14002505d  cmp     [rsi+70h], bl
0x140025060  jz      short loc_14002506E
0x140025062  lea     rcx, [rsi+60h]
0x140025066  call    BfFreeEnumerationContextList
0x14002506b  mov     [rsi+70h], bl
0x14002506e  lea     r8, [rsi+58h]
0x140025072  lea     rax, [rsp+0F8h+var_A6]
0x140025077  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax; __int64
0x14002507c  lea     r9, [rsp+0F8h+var_88]
0x140025081  mov     rdx, r12
0x140025084  mov     rcx, r14; CallbackData
0x140025087  call    BfGetMappingList
0x14002508c  mov     edx, 80000000h
0x140025091  lea     ecx, [rax+rdx]
0x140025094  test    edx, ecx
0x140025096  jnz     short loc_1400250A3
0x140025098  cmp     eax, 0C000003Ah
0x14002509d  jnz     loc_14002565D
0x1400250a3  mov     dl, r15b
0x1400250a6  lea     rcx, [rsi+60h]
0x1400250aa  mov     rax, [rcx]
0x1400250ad  jmp     short loc_1400250B7
0x1400250af  cmp     [rax+30h], ebx
0x1400250b2  ja      short loc_1400250BE
0x1400250b4  mov     rax, [rax]
0x1400250b7  cmp     rax, rcx
0x1400250ba  jnz     short loc_1400250AF
0x1400250bc  jmp     short loc_1400250C0
0x1400250be  mov     dl, bl
0x1400250c0  lea     rax, [rsp+0F8h+var_88]
0x1400250c5  cmp     [rsp+0F8h+var_88], rax
0x1400250ca  jnz     short loc_1400250DC
0x1400250cc  test    dl, dl
0x1400250ce  jz      short loc_1400250DC
0x1400250d0  mov     eax, [rsi+50h]
0x1400250d3  test    r15b, al
0x1400250d6  jz      loc_14002565D
0x1400250dc  mov     qword ptr [rsp+0F8h+Priority], rbx; __int64
0x1400250e1  lea     rax, [rsp+0F8h+var_58]
0x1400250e9  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax; __int64
0x1400250ee  lea     r9, [rsp+0F8h+var_78]
0x1400250f6  mov     r8, rsi; Context
0x1400250f9  mov     rdx, [r12+20h]; FileObject
0x1400250fe  mov     rcx, [r12+18h]; Instance
0x140025103  call    BfMapShadowFileObjectToReal
0x140025108  test    al, al
0x14002510a  jnz     short loc_140025126
0x14002510c  mov     rax, [r12+18h]
0x140025111  mov     [rsp+0F8h+var_78], rax
0x140025119  mov     rax, [r12+20h]
0x14002511e  mov     [rsp+0F8h+var_58], rax
0x140025126  lea     rax, [rsp+0F8h+var_88]
0x14002512b  cmp     [rsp+0F8h+var_88], rax
0x140025130  jz      short loc_140025154
0x140025132  mov     qword ptr [rsp+0F8h+Priority], rsi
0x140025137  mov     [rsp+0F8h+BugCheckOnFailure], edi
0x14002513b  xor     r9d, r9d
0x14002513e  xor     r8d, r8d
0x140025141  xor     edx, edx
0x140025143  xor     ecx, ecx
0x140025145  call    BfCreateEnumerationContext
0x14002514a  mov     edi, eax
0x14002514c  test    eax, eax
0x14002514e  js      loc_1400256C6
0x140025154  mov     [rsp+0F8h+var_C8], rsi
0x140025159  mov     eax, dword ptr [rsp+0F8h+var_A6+6]
0x14002515d  mov     [rsp+0F8h+Priority], eax
0x140025161  mov     rax, [rsp+0F8h+var_58]
0x140025169  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x14002516e  mov     r9, [rsp+0F8h+var_78]
0x140025176  mov     r8, [r12+20h]
0x14002517b  mov     rdx, [r12+18h]
0x140025180  mov     rcx, r14
0x140025183  call    BfSetupEnumerationContexts
0x140025188  mov     edi, eax
0x14002518a  test    eax, eax
0x14002518c  jns     short loc_1400251B9
0x14002518e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025195  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002519c  jz      loc_1400256C6
0x1400251a2  mov     r9d, 28h ; '('
0x1400251a8  mov     dword ptr [rsp+0F8h+var_C0], eax
0x1400251ac  mov     dword ptr [rsp+0F8h+var_C8], 0BDBh
0x1400251b4  jmp     loc_140025696
0x1400251b9  mov     r12, [rsp+0F8h+MemoryDescriptorList]
0x1400251c1  test    r12, r12
0x1400251c4  jz      loc_140025294
0x1400251ca  mov     rcx, r14; CallbackData
0x1400251cd  call    cs:__imp_FltLockUserBuffer
0x1400251d4  nop     dword ptr [rax+rax+00h]
0x1400251d9  mov     edi, eax
0x1400251db  test    eax, eax
0x1400251dd  jns     short loc_14002520A
0x1400251df  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400251e6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400251ed  jz      loc_1400256C6
0x1400251f3  mov     r9d, 29h ; ')'
0x1400251f9  mov     dword ptr [rsp+0F8h+var_C0], eax
0x1400251fd  mov     dword ptr [rsp+0F8h+var_C8], 0BEBh
0x140025205  jmp     loc_140025696
0x14002520a  test    byte ptr [r12+0Ah], 5
0x140025210  jz      short loc_140025219
0x140025212  mov     r9, [r12+18h]
0x140025217  jmp     short loc_14002523F
0x140025219  mov     [rsp+0F8h+Priority], 40000010h; Priority
0x140025221  mov     [rsp+0F8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140025225  xor     r9d, r9d; RequestedAddress
0x140025228  mov     r8d, r15d; CacheType
0x14002522b  xor     edx, edx; AccessMode
0x14002522d  mov     rcx, r12; MemoryDescriptorList
0x140025230  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140025237  nop     dword ptr [rax+rax+00h]
0x14002523c  mov     r9, rax
0x14002523f  mov     [rsp+0F8h+Address], r9
0x140025247  test    r9, r9
0x14002524a  jnz     short loc_14002527C
0x14002524c  mov     edi, 0C0000017h
0x140025251  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025258  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002525f  jz      loc_1400256C6
0x140025265  mov     r9d, 2Ah ; '*'
0x14002526b  mov     dword ptr [rsp+0F8h+var_C0], edi
0x14002526f  mov     dword ptr [rsp+0F8h+var_C8], 0BF4h
0x140025277  jmp     loc_140025696
0x14002527c  mov     [rsp+0F8h+var_78], r9
0x140025284  mov     [rsp+0F8h+arg_18], bl
0x14002528b  mov     [rsp+0F8h+var_A7], bl
0x14002528f  jmp     loc_140025351
0x140025294  mov     r9, [rsp+0F8h+Address]
0x14002529c  mov     [rsp+0F8h+var_78], r9
0x1400252a4  cmp     [rsp+0F8h+var_9C], ebx
0x1400252a8  jnz     loc_14002533C
0x1400252ae  mov     edx, dword ptr [rsp+0F8h+var_A6+6]; Length
0x1400252b2  mov     r8d, r15d; Alignment
0x1400252b5  mov     rcx, r9; Address
0x1400252b8  call    cs:__imp_ProbeForRead
0x1400252bf  nop     dword ptr [rax+rax+00h]
0x1400252c4  mov     r8b, [rsp+0F8h+arg_18]
0x1400252cc  mov     [rsp+0F8h+var_A7], r8b
0x1400252d1  jmp     short loc_140025351
0x1400252d3  mov     edi, 0C00000E8h
0x1400252d8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400252df  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400252e6  jz      short loc_14002532C
0x1400252e8  mov     r9d, 2Bh ; '+'
0x1400252ee  mov     [rsp+0F8h+var_B8], edi
0x1400252f2  mov     dword ptr [rsp+0F8h+var_C0], eax
0x1400252f6  mov     dword ptr [rsp+0F8h+var_C8], 0C13h
0x1400252fe  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025305  mov     qword ptr [rsp+0F8h+Priority], rax
0x14002530a  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x140025311  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x140025316  lea     r8d, [r9-1Fh]
0x14002531a  mov     dl, 2
0x14002531c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025323  mov     rcx, [rcx+40h]
0x140025327  call    WPP_RECORDER_SF_sDdd
0x14002532c  xor     ebx, ebx
0x14002532e  lea     r15d, [rbx+1]
0x140025332  mov     rsi, [rsp+0F8h+Context]
0x140025337  jmp     loc_1400256C6
0x14002533c  mov     r8b, [rsp+0F8h+arg_18]
0x140025344  mov     [rsp+0F8h+arg_18], r8b
0x14002534c  mov     [rsp+0F8h+var_A7], r8b
0x140025351  mov     r14d, ebx
  ... truncated ...
```
