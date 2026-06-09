# BfPreDirectoryControl

- ea: `0x140024e40`
- end: `0x14002575f`
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
- `0x14002494c`
- `0x140024a58`
- `0x140024e40`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400252a8`
- `ntoskrnl!ProbeForRead` at `0x1400252a8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025220`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140025220`
- `ntoskrnl!KeSetEvent` at `0x14002571e`
- `ntoskrnl!KeSetEvent` at `0x14002571e`
- `FLTMGR!FltLockUserBuffer` at `0x1400251bd`
- `FLTMGR!FltLockUserBuffer` at `0x1400251bd`
- `FLTMGR!FltReleaseContext` at `0x140025732`
- `FLTMGR!FltReleaseContext` at `0x140025732`

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
    v36 = -78;
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
          (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
          163,
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
          v36 = -23;
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
          v36 = -14;
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
          v36 = 65;
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
      v36 = 93;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_95;
      v23 = 40;
      LODWORD(v37) = v21;
      v36 = -39;
    }
LABEL_94:
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      12,
      v23,
      (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
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
0x140024e40  mov     r11, rsp
0x140024e43  mov     [r11+10h], rbx
0x140024e47  mov     [r11+18h], rsi
0x140024e4b  mov     [r11+8], rcx
0x140024e4f  push    rdi
0x140024e50  push    r12
0x140024e52  push    r13
0x140024e54  push    r14
0x140024e56  push    r15
0x140024e58  sub     rsp, 0D0h
0x140024e5f  mov     r12, rdx
0x140024e62  mov     r14, rcx
0x140024e65  xor     ebx, ebx
0x140024e67  mov     [rsp+0F8h+var_98], ebx
0x140024e6b  mov     [r11-70h], ebx
0x140024e6f  mov     [r11-78h], rbx
0x140024e73  mov     [r11-58h], rbx
0x140024e77  mov     esi, ebx
0x140024e79  mov     [rsp+0F8h+Context], rbx
0x140024e7e  lea     rax, [r11-70h]
0x140024e82  mov     [r11-48h], rax
0x140024e86  lea     rax, [rsp+0F8h+var_88]
0x140024e8b  mov     [rsp+0F8h+var_40], rax
0x140024e93  lea     rax, [rsp+0F8h+var_88]
0x140024e98  mov     [r11-80h], rax
0x140024e9c  lea     rax, [rsp+0F8h+var_88]
0x140024ea1  mov     [rsp+0F8h+var_88], rax
0x140024ea6  mov     [rsp+0F8h+var_A6+1], bl
0x140024eaa  mov     [rsp+0F8h+var_A6+2], bl
0x140024eae  lea     rax, [rcx+10h]
0x140024eb2  mov     [rsp+0F8h+var_50], rax
0x140024eba  mov     rdx, [rax]
0x140024ebd  mov     edi, [rdx+18h]
0x140024ec0  mov     eax, [rcx]
0x140024ec2  and     eax, 8
0x140024ec5  mov     [rsp+0F8h+var_9C], eax
0x140024ec9  setz    byte ptr [r11+20h]
0x140024ece  mov     eax, 10000h
0x140024ed3  cmp     edi, eax
0x140024ed5  cmova   edi, eax
0x140024ed8  mov     dword ptr [rsp+0F8h+var_A6+6], edi
0x140024edc  lea     r15d, [rbx+1]
0x140024ee0  cmp     [rdx+8], rbx
0x140024ee4  jnz     short loc_140024EED
0x140024ee6  mov     edi, ebx
0x140024ee8  jmp     loc_1400256B6
0x140024eed  cmp     [rdx+5], r15b
0x140024ef1  jnz     loc_14002564D
0x140024ef7  mov     r13d, [rdx+28h]
0x140024efb  mov     [rsp+0F8h+var_5C], r13d
0x140024f03  cmp     r13d, 3Ch ; '<'
0x140024f07  jg      short loc_140024F37
0x140024f09  jz      loc_140024FAF
0x140024f0f  mov     ecx, r13d
0x140024f12  sub     ecx, r15d
0x140024f15  jz      loc_140024FAF
0x140024f1b  sub     ecx, r15d
0x140024f1e  jz      loc_140024FAF
0x140024f24  sub     ecx, r15d
0x140024f27  jz      loc_140024FAF
0x140024f2d  sub     ecx, 9
0x140024f30  jz      short loc_140024FAF
0x140024f32  sub     ecx, 19h
0x140024f35  jmp     short loc_140024F4C
0x140024f37  mov     ecx, r13d
0x140024f3a  sub     ecx, 3Fh ; '?'
0x140024f3d  jz      short loc_140024FAF
0x140024f3f  sub     ecx, 0Fh
0x140024f42  jz      short loc_140024FAF
0x140024f44  sub     ecx, r15d
0x140024f47  jz      short loc_140024FAF
0x140024f49  sub     ecx, r15d
0x140024f4c  jz      short loc_140024FAF
0x140024f4e  cmp     ecx, r15d
0x140024f51  jz      short loc_140024FAF
0x140024f53  mov     edi, ebx
0x140024f55  lea     rcx, WPP_RECORDER_INITIALIZED
0x140024f5c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140024f63  jz      loc_1400256B6
0x140024f69  mov     r9d, 30h ; '0'
0x140024f6f  mov     dword ptr [rsp+0F8h+var_C0], r13d
0x140024f74  mov     dword ptr [rsp+0F8h+var_C8], 0CA3h
0x140024f7c  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140024f83  mov     qword ptr [rsp+0F8h+Priority], rax
0x140024f88  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x140024f8f  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x140024f94  lea     r8d, [r9-24h]
0x140024f98  mov     dl, 2
0x140024f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fa1  mov     rcx, [rcx+40h]
0x140024fa5  call    WPP_RECORDER_SF_sDD
0x140024faa  jmp     loc_1400256B6
0x140024faf  mov     al, [rdx+6]
0x140024fb2  mov     [rsp+0F8h+var_A8], al
0x140024fb6  mov     rax, [rdx+38h]
0x140024fba  mov     [rsp+0F8h+Address], rax
0x140024fc2  mov     rcx, [rdx+40h]
0x140024fc6  mov     [rsp+0F8h+MemoryDescriptorList], rcx
0x140024fce  lea     r8, [rsp+0F8h+Context]
0x140024fd3  lea     rdx, [rsp+0F8h+var_A6+2]
0x140024fd8  mov     rcx, r12
0x140024fdb  call    BfGetSetDirectoryEnumerationHandleContext
0x140024fe0  mov     rsi, [rsp+0F8h+Context]
0x140024fe5  test    eax, eax
0x140024fe7  js      loc_14002564D
0x140024fed  lea     rax, [r14+10h]
0x140024ff1  mov     [rsp+0F8h+var_30], rax
0x140024ff9  mov     rax, [rax]
0x140024ffc  test    [rax+6], r15b
0x140025000  jz      short loc_14002505E
0x140025002  mov     [rsi+54h], ebx
0x140025005  mov     rcx, [rsi+58h]
0x140025009  test    rcx, rcx
0x14002500c  jz      short loc_140025049
0x14002500e  mov     rdx, [rcx]
0x140025011  test    rdx, rdx
0x140025014  jz      short loc_14002501B
0x140025016  mov     rax, rcx
0x140025019  jmp     short loc_140025027
0x14002501b  lea     rax, [rcx+8]
0x14002501f  mov     rdx, [rax]
0x140025022  test    rdx, rdx
0x140025025  jz      short loc_14002502F
0x140025027  mov     rcx, rdx
0x14002502a  mov     [rax], rbx
0x14002502d  jmp     short loc_14002500E
0x14002502f  mov     rdi, [rcx+10h]
0x140025033  xor     edx, edx
0x140025035  call    BfReturnedWalkContextAvlDeleteFunction
0x14002503a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14002503e  jz      short loc_140025045
0x140025040  mov     rcx, rdi
0x140025043  jmp     short loc_14002500E
0x140025045  mov     edi, dword ptr [rsp+0F8h+var_A6+6]
0x140025049  mov     [rsi+58h], rbx
0x14002504d  cmp     [rsi+70h], bl
0x140025050  jz      short loc_14002505E
0x140025052  lea     rcx, [rsi+60h]
0x140025056  call    BfFreeEnumerationContextList
0x14002505b  mov     [rsi+70h], bl
0x14002505e  lea     r8, [rsi+58h]
0x140025062  lea     rax, [rsp+0F8h+var_A6]
0x140025067  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax; __int64
0x14002506c  lea     r9, [rsp+0F8h+var_88]
0x140025071  mov     rdx, r12
0x140025074  mov     rcx, r14; CallbackData
0x140025077  call    BfGetMappingList
0x14002507c  mov     edx, 80000000h
0x140025081  lea     ecx, [rax+rdx]
0x140025084  test    edx, ecx
0x140025086  jnz     short loc_140025093
0x140025088  cmp     eax, 0C000003Ah
0x14002508d  jnz     loc_14002564D
0x140025093  mov     dl, r15b
0x140025096  lea     rcx, [rsi+60h]
0x14002509a  mov     rax, [rcx]
0x14002509d  jmp     short loc_1400250A7
0x14002509f  cmp     [rax+30h], ebx
0x1400250a2  ja      short loc_1400250AE
0x1400250a4  mov     rax, [rax]
0x1400250a7  cmp     rax, rcx
0x1400250aa  jnz     short loc_14002509F
0x1400250ac  jmp     short loc_1400250B0
0x1400250ae  mov     dl, bl
0x1400250b0  lea     rax, [rsp+0F8h+var_88]
0x1400250b5  cmp     [rsp+0F8h+var_88], rax
0x1400250ba  jnz     short loc_1400250CC
0x1400250bc  test    dl, dl
0x1400250be  jz      short loc_1400250CC
0x1400250c0  mov     eax, [rsi+50h]
0x1400250c3  test    r15b, al
0x1400250c6  jz      loc_14002564D
0x1400250cc  mov     qword ptr [rsp+0F8h+Priority], rbx; __int64
0x1400250d1  lea     rax, [rsp+0F8h+var_58]
0x1400250d9  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax; __int64
0x1400250de  lea     r9, [rsp+0F8h+var_78]
0x1400250e6  mov     r8, rsi; Context
0x1400250e9  mov     rdx, [r12+20h]; FileObject
0x1400250ee  mov     rcx, [r12+18h]; Instance
0x1400250f3  call    BfMapShadowFileObjectToReal
0x1400250f8  test    al, al
0x1400250fa  jnz     short loc_140025116
0x1400250fc  mov     rax, [r12+18h]
0x140025101  mov     [rsp+0F8h+var_78], rax
0x140025109  mov     rax, [r12+20h]
0x14002510e  mov     [rsp+0F8h+var_58], rax
0x140025116  lea     rax, [rsp+0F8h+var_88]
0x14002511b  cmp     [rsp+0F8h+var_88], rax
0x140025120  jz      short loc_140025144
0x140025122  mov     qword ptr [rsp+0F8h+Priority], rsi
0x140025127  mov     [rsp+0F8h+BugCheckOnFailure], edi
0x14002512b  xor     r9d, r9d
0x14002512e  xor     r8d, r8d
0x140025131  xor     edx, edx
0x140025133  xor     ecx, ecx
0x140025135  call    BfCreateEnumerationContext
0x14002513a  mov     edi, eax
0x14002513c  test    eax, eax
0x14002513e  js      loc_1400256B6
0x140025144  mov     [rsp+0F8h+var_C8], rsi
0x140025149  mov     eax, dword ptr [rsp+0F8h+var_A6+6]
0x14002514d  mov     [rsp+0F8h+Priority], eax
0x140025151  mov     rax, [rsp+0F8h+var_58]
0x140025159  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x14002515e  mov     r9, [rsp+0F8h+var_78]
0x140025166  mov     r8, [r12+20h]
0x14002516b  mov     rdx, [r12+18h]
0x140025170  mov     rcx, r14
0x140025173  call    BfSetupEnumerationContexts
0x140025178  mov     edi, eax
0x14002517a  test    eax, eax
0x14002517c  jns     short loc_1400251A9
0x14002517e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025185  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002518c  jz      loc_1400256B6
0x140025192  mov     r9d, 28h ; '('
0x140025198  mov     dword ptr [rsp+0F8h+var_C0], eax
0x14002519c  mov     dword ptr [rsp+0F8h+var_C8], 0BD9h
0x1400251a4  jmp     loc_140025686
0x1400251a9  mov     r12, [rsp+0F8h+MemoryDescriptorList]
0x1400251b1  test    r12, r12
0x1400251b4  jz      loc_140025284
0x1400251ba  mov     rcx, r14; CallbackData
0x1400251bd  call    cs:__imp_FltLockUserBuffer
0x1400251c4  nop     dword ptr [rax+rax+00h]
0x1400251c9  mov     edi, eax
0x1400251cb  test    eax, eax
0x1400251cd  jns     short loc_1400251FA
0x1400251cf  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400251d6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400251dd  jz      loc_1400256B6
0x1400251e3  mov     r9d, 29h ; ')'
0x1400251e9  mov     dword ptr [rsp+0F8h+var_C0], eax
0x1400251ed  mov     dword ptr [rsp+0F8h+var_C8], 0BE9h
0x1400251f5  jmp     loc_140025686
0x1400251fa  test    byte ptr [r12+0Ah], 5
0x140025200  jz      short loc_140025209
0x140025202  mov     r9, [r12+18h]
0x140025207  jmp     short loc_14002522F
0x140025209  mov     [rsp+0F8h+Priority], 40000010h; Priority
0x140025211  mov     [rsp+0F8h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140025215  xor     r9d, r9d; RequestedAddress
0x140025218  mov     r8d, r15d; CacheType
0x14002521b  xor     edx, edx; AccessMode
0x14002521d  mov     rcx, r12; MemoryDescriptorList
0x140025220  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140025227  nop     dword ptr [rax+rax+00h]
0x14002522c  mov     r9, rax
0x14002522f  mov     [rsp+0F8h+Address], r9
0x140025237  test    r9, r9
0x14002523a  jnz     short loc_14002526C
0x14002523c  mov     edi, 0C0000017h
0x140025241  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025248  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002524f  jz      loc_1400256B6
0x140025255  mov     r9d, 2Ah ; '*'
0x14002525b  mov     dword ptr [rsp+0F8h+var_C0], edi
0x14002525f  mov     dword ptr [rsp+0F8h+var_C8], 0BF2h
0x140025267  jmp     loc_140025686
0x14002526c  mov     [rsp+0F8h+var_78], r9
0x140025274  mov     [rsp+0F8h+arg_18], bl
0x14002527b  mov     [rsp+0F8h+var_A7], bl
0x14002527f  jmp     loc_140025341
0x140025284  mov     r9, [rsp+0F8h+Address]
0x14002528c  mov     [rsp+0F8h+var_78], r9
0x140025294  cmp     [rsp+0F8h+var_9C], ebx
0x140025298  jnz     loc_14002532C
0x14002529e  mov     edx, dword ptr [rsp+0F8h+var_A6+6]; Length
0x1400252a2  mov     r8d, r15d; Alignment
0x1400252a5  mov     rcx, r9; Address
0x1400252a8  call    cs:__imp_ProbeForRead
0x1400252af  nop     dword ptr [rax+rax+00h]
0x1400252b4  mov     r8b, [rsp+0F8h+arg_18]
0x1400252bc  mov     [rsp+0F8h+var_A7], r8b
0x1400252c1  jmp     short loc_140025341
0x1400252c3  mov     edi, 0C00000E8h
0x1400252c8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400252cf  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400252d6  jz      short loc_14002531C
0x1400252d8  mov     r9d, 2Bh ; '+'
0x1400252de  mov     [rsp+0F8h+var_B8], edi
0x1400252e2  mov     dword ptr [rsp+0F8h+var_C0], eax
0x1400252e6  mov     dword ptr [rsp+0F8h+var_C8], 0C11h
0x1400252ee  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400252f5  mov     qword ptr [rsp+0F8h+Priority], rax
0x1400252fa  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x140025301  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x140025306  lea     r8d, [r9-1Fh]
0x14002530a  mov     dl, 2
0x14002530c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025313  mov     rcx, [rcx+40h]
0x140025317  call    WPP_RECORDER_SF_sDdd
0x14002531c  xor     ebx, ebx
0x14002531e  lea     r15d, [rbx+1]
0x140025322  mov     rsi, [rsp+0F8h+Context]
0x140025327  jmp     loc_1400256B6
0x14002532c  mov     r8b, [rsp+0F8h+arg_18]
0x140025334  mov     [rsp+0F8h+arg_18], r8b
0x14002533c  mov     [rsp+0F8h+var_A7], r8b
0x140025341  mov     r14d, ebx
  ... truncated ...
```
