# WofPreReadCallback

- ea: `0x140007b20`
- end: `0x1400081e6`
- name: `WofPreReadCallback`
- size: `1734`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140007b20`
- `0x14000ba78`
- `0x14000dc88`
- `0x14000e3dc`
- `0x14000e9d8`
- `0x140011640`
- `0x140034fa0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140007bb4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140007bb4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007ddb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007ddb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400081d5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400081d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007bcb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007bcb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007f6a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007f6a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007b55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007b55`
- `FLTMGR!FltLockUserBuffer` at `0x140007d84`
- `FLTMGR!FltLockUserBuffer` at `0x140007d84`
- `FLTMGR!FltGetStreamContext` at `0x140007b6d`
- `FLTMGR!FltGetStreamContext` at `0x140007b6d`
- `FLTMGR!FltReleaseContext` at `0x140007d29`
- `FLTMGR!FltReleaseContext` at `0x140007d29`

## string_xrefs

- `0x140008084`: `cached`
- `0x14000808d`: `noncached`

## pseudocode

```c
__int64 __fastcall WofPreReadCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // r14d
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  NTSTATUS IsDataInFilesystem; // eax
  struct _EX_RUNDOWN_REF *v11; // r12
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  LARGE_INTEGER ByteOffset; // rbx
  bool v14; // r14
  __int64 (__fastcall *v15)(PFLT_CALLBACK_DATA, PEX_RUNDOWN_REF, char *, LARGE_INTEGER, ULONG, __int64 *); // rax
  int v16; // ebx
  int v17; // edx
  int v18; // edx
  int v19; // r15d
  PFLT_IO_PARAMETER_BLOCK v20; // rcx
  PVOID MappedSystemVa; // r15
  struct _MDL *MdlAddress; // r10
  PFLT_IO_PARAMETER_BLOCK v23; // r9
  LARGE_INTEGER v24; // r8
  __int64 (__fastcall *v25)(PFLT_CALLBACK_DATA, _QWORD, struct _EX_RUNDOWN_REF *, __int64, char *, ULONG, LARGE_INTEGER, DWORD, PVOID, PVOID, _QWORD *); // rax
  PVOID EaBuffer; // rcx
  __int64 v27; // r9
  unsigned __int64 PoolWithTag; // rax
  PFLT_IO_PARAMETER_BLOCK v29; // r8
  PFILE_OBJECT TargetFileObject; // r9
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rax
  const char *v32; // rcx
  char v33; // al
  signed __int32 v34[10]; // [rsp+0h] [rbp-80h] BYREF
  ULONG Priority[2]; // [rsp+28h] [rbp-58h]
  _QWORD *v36; // [rsp+50h] [rbp-30h]
  PEX_RUNDOWN_REF RunRef; // [rsp+60h] [rbp-20h] BYREF
  LARGE_INTEGER v38; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v39[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v40; // [rsp+C8h] [rbp+48h] BYREF
  PFLT_CONTEXT Context; // [rsp+D8h] [rbp+58h] BYREF

  v3 = 0;
  Context = 0;
  v38.QuadPart = 0;
  v39[0] = 0;
  LOBYTE(v40) = 0;
  RunRef = 0;
  KeEnterCriticalRegion();
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    IsDataInFilesystem = WofIsDataInFilesystemEx(Context, (_QWORD *)a2, (bool *)&v40, &RunRef);
    v11 = RunRef;
    if ( IsDataInFilesystem < 0 )
    {
      CallbackData->IoStatus.Status = IsDataInFilesystem;
LABEL_19:
      v3 = 4;
      if ( v11 )
        ExReleaseRundownProtection(v11);
      goto LABEL_21;
    }
    if ( (_BYTE)v40 )
    {
      if ( RunRef )
        *a3 = (unsigned __int64)RunRef | 1;
      else
        v3 = 1;
      goto LABEL_21;
    }
    Iopb = CallbackData->Iopb;
    ByteOffset = Iopb->Parameters.Read.ByteOffset;
    v14 = (Iopb->IrpFlags & 2) != 0;
    if ( (Iopb->IrpFlags & 2) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(Iopb) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)Iopb,
          3,
          10,
          (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
          *(_QWORD *)(a2 + 32));
      }
      if ( !CallbackData->Iopb->Parameters.Read.Length )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(Iopb) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Iopb,
            3,
            11,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
        CallbackData->IoStatus.Information = 0;
        CallbackData->IoStatus.Status = 0;
        goto LABEL_66;
      }
      if ( ((int (__fastcall *)(char *, LARGE_INTEGER *, _QWORD))qword_14001A280[53 * *((unsigned int *)Context + 3)])(
             (char *)Context + 64,
             &v38,
             0) < 0
        || ByteOffset.QuadPart >= v38.QuadPart )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v17) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            3,
            12,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
        CallbackData->IoStatus.Status = -1073741807;
        goto LABEL_18;
      }
      v19 = FltLockUserBuffer(CallbackData);
      if ( v19 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            3,
            13,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
        CallbackData->IoStatus.Status = v19;
        goto LABEL_18;
      }
      v20 = CallbackData->Iopb;
      MappedSystemVa = 0;
      if ( (v20->MinorFunction & 2) == 0 )
      {
        MdlAddress = v20->Parameters.Read.MdlAddress;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
            MappedSystemVa = MdlAddress->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
          {
            CallbackData->IoStatus.Status = -1073741801;
LABEL_18:
            CallbackData->IoStatus.Information = 0;
            goto LABEL_19;
          }
        }
        else
        {
          MappedSystemVa = v20->Parameters.CreatePipe.Parameters;
        }
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = (int)WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v29 = CallbackData->Iopb;
          TargetFileObject = v29->TargetFileObject;
          SectionObjectPointer = TargetFileObject->SectionObjectPointer;
          if ( !SectionObjectPointer || (v32 = "cached", !SectionObjectPointer->SharedCacheMap) )
            v32 = "noncached";
          WPP_RECORDER_SF_dDsZq(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)WPP_GLOBAL_Control,
            (_DWORD)v29,
            14,
            v34[8],
            v29->Parameters.Read.Length,
            ByteOffset.QuadPart,
            (__int64)v32,
            (__int64)&TargetFileObject->FileName,
            (char)MappedSystemVa);
        }
      }
      if ( !MappedSystemVa )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v18) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v18,
            3,
            15,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids);
        }
        CallbackData->IoStatus.Status = -1073741592;
        goto LABEL_18;
      }
      v23 = CallbackData->Iopb;
      v24.QuadPart = v23->Parameters.Read.Length;
      if ( v24.QuadPart > v38.QuadPart || ByteOffset.QuadPart > v38.QuadPart - v24.QuadPart )
        v24.LowPart = v38.LowPart - ByteOffset.LowPart;
      v25 = *(__int64 (__fastcall **)(PFLT_CALLBACK_DATA, _QWORD, struct _EX_RUNDOWN_REF *, __int64, char *, ULONG, LARGE_INTEGER, DWORD, PVOID, PVOID, _QWORD *))&algn_14001A230[424 * *((unsigned int *)Context + 3)];
      v36 = v39;
      EaBuffer = v23->Parameters.Create.EaBuffer;
      v27 = *(_QWORD *)(a2 + 24);
      LOBYTE(Priority[0]) = v14;
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))v25)(
              CallbackData,
              0,
              v11,
              v27,
              (char *)Context + 64,
              Priority[0],
              (LARGE_INTEGER)ByteOffset.QuadPart,
              v24.LowPart,
              MappedSystemVa,
              EaBuffer,
              v39);
      if ( v16 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(Iopb) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)Iopb,
            3,
            16,
            (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
            v16);
        }
        CallbackData->IoStatus.Status = v16;
        goto LABEL_18;
      }
      goto LABEL_16;
    }
    v15 = *(__int64 (__fastcall **)(PFLT_CALLBACK_DATA, PEX_RUNDOWN_REF, char *, LARGE_INTEGER, ULONG, __int64 *))&algn_14001A230[424 * *((unsigned int *)Context + 3) + 16];
    if ( v15 )
    {
      v40 = 0;
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))v15)(
              CallbackData,
              RunRef,
              (char *)Context + 64,
              (LARGE_INTEGER)ByteOffset.QuadPart,
              Iopb->Parameters.Read.Length,
              &v40);
      if ( v16 < 0 )
      {
LABEL_16:
        if ( v16 != 259 )
        {
          CallbackData->IoStatus.Status = v16;
          if ( v16 >= 0 )
          {
LABEL_66:
            v33 = v39[0];
            CallbackData->IoStatus.Information = v39[0];
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              LOBYTE(Iopb) = 5;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)Iopb,
                3,
                17,
                (__int64)WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids,
                v33);
            }
            goto LABEL_19;
          }
          goto LABEL_18;
        }
        v3 = 2;
LABEL_21:
        FltReleaseContext(Context);
        goto LABEL_5;
      }
      PoolWithTag = (unsigned __int64)ExAllocatePoolWithTag(PagedPool, 0x18u, 0x47666F57u);
      if ( !PoolWithTag )
      {
        (*(void (__fastcall **)(__int64))&algn_14001A230[424 * *((unsigned int *)Context + 3) + 8])(v40);
        CallbackData->IoStatus.Status = -1073741670;
        goto LABEL_18;
      }
      *(_QWORD *)PoolWithTag = v11;
      *(_DWORD *)(PoolWithTag + 8) = *((_DWORD *)Context + 3);
      *(_QWORD *)(PoolWithTag + 16) = v40;
      *a3 = PoolWithTag | 2;
    }
    else
    {
      *a3 = RunRef;
    }
    v3 = 5;
    goto LABEL_21;
  }
  v7 = 10 * ((*(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) >> 12) % (unsigned __int64)(unsigned int)dword_140018660);
  do
  {
    v8 = qword_1400186A0[v7];
    _InterlockedOr(v34, 0);
  }
  while ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)v8) );
  *a3 = v8 | 1;
LABEL_5:
  KeLeaveCriticalRegion();
  return v3;
}

```

## disassembly

```asm
0x140007b20  push    rbp
0x140007b22  push    rbx
0x140007b23  push    rsi
0x140007b24  push    rdi
0x140007b25  push    r13
0x140007b27  push    r14
0x140007b29  push    r15
0x140007b2b  mov     rbp, rsp
0x140007b2e  sub     rsp, 80h
0x140007b35  xor     r14d, r14d
0x140007b38  mov     r15, r8
0x140007b3b  mov     [rbp+Context], r14
0x140007b3f  mov     rdi, rdx
0x140007b42  mov     [rbp+var_18], r14
0x140007b46  mov     r13, rcx
0x140007b49  mov     [rbp+var_10], r14
0x140007b4d  mov     byte ptr [rbp+arg_8], r14b
0x140007b51  mov     [rbp+RunRef], r14
0x140007b55  call    cs:__imp_KeEnterCriticalRegion
0x140007b5c  nop     dword ptr [rax+rax+00h]
0x140007b61  mov     rdx, [rdi+20h]; FileObject
0x140007b65  lea     r8, [rbp+Context]; Context
0x140007b69  mov     rcx, [rdi+18h]; Instance
0x140007b6d  call    cs:__imp_FltGetStreamContext
0x140007b74  nop     dword ptr [rax+rax+00h]
0x140007b79  test    eax, eax
0x140007b7b  jns     short loc_140007BED
0x140007b7d  mov     rax, [rdi+20h]
0x140007b81  lea     rsi, cs:140000000h
0x140007b88  mov     ecx, cs:dword_140018660
0x140007b8e  xor     edx, edx
0x140007b90  mov     rax, [rax+18h]
0x140007b94  shr     rax, 0Ch
0x140007b98  div     rcx
0x140007b9b  mov     eax, edx
0x140007b9d  lea     rdi, [rax+rax*4]
0x140007ba1  add     rdi, rdi
0x140007ba4  mov     rbx, rva qword_1400186A0[rsi+rdi*8]
0x140007bac  lock or [rsp+80h+var_80], r14d
0x140007bb1  mov     rcx, rbx; RunRef
0x140007bb4  call    cs:__imp_ExAcquireRundownProtection
0x140007bbb  nop     dword ptr [rax+rax+00h]
0x140007bc0  test    al, al
0x140007bc2  jz      short loc_140007BA4
0x140007bc4  or      rbx, 1
0x140007bc8  mov     [r15], rbx
0x140007bcb  call    cs:__imp_KeLeaveCriticalRegion
0x140007bd2  nop     dword ptr [rax+rax+00h]
0x140007bd7  mov     eax, r14d
0x140007bda  add     rsp, 80h
0x140007be1  pop     r15
0x140007be3  pop     r14
0x140007be5  pop     r13
0x140007be7  pop     rdi
0x140007be8  pop     rsi
0x140007be9  pop     rbx
0x140007bea  pop     rbp
0x140007beb  retn
0x140007bed  mov     rcx, [rbp+Context]
0x140007bf1  lea     r9, [rbp+RunRef]
0x140007bf5  lea     r8, [rbp+arg_8]
0x140007bf9  mov     [rsp+80h+arg_0], r12
0x140007c01  mov     rdx, rdi
0x140007c04  call    WofIsDataInFilesystemEx
0x140007c09  mov     r12, [rbp+RunRef]
0x140007c0d  test    eax, eax
0x140007c0f  js      loc_140007F25
0x140007c15  cmp     byte ptr [rbp+arg_8], r14b
0x140007c19  jnz     loc_140007F2E
0x140007c1f  mov     rax, [rbp+Context]
0x140007c23  mov     ecx, [rax+8]
0x140007c26  and     ecx, 0F000000h
0x140007c2c  cmp     ecx, 2000000h
0x140007c32  jnz     loc_140007F4E
0x140007c38  mov     rdx, [r13+10h]
0x140007c3c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140007c43  lea     rsi, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140007c4a  mov     eax, [rdx]
0x140007c4c  bt      eax, 1
0x140007c50  mov     rbx, [rdx+28h]
0x140007c54  setb    r14b
0x140007c58  bt      eax, 1
0x140007c5c  jnb     short loc_140007C9B
0x140007c5e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140007c65  jnz     loc_140007EE4
0x140007c6b  mov     rax, [r13+10h]
0x140007c6f  cmp     dword ptr [rax+18h], 0
0x140007c73  jnz     loc_140007D42
0x140007c79  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140007c80  jnz     loc_140007FDA
0x140007c86  mov     qword ptr [r13+20h], 0
0x140007c8e  mov     dword ptr [r13+18h], 0
0x140007c96  jmp     loc_14000812D
0x140007c9b  mov     r8, [rbp+Context]
0x140007c9f  lea     rsi, cs:140000000h
0x140007ca6  mov     eax, [r8+0Ch]
0x140007caa  imul    rcx, rax, 1A8h
0x140007cb1  mov     rax, [rcx+rsi+1A240h]
0x140007cb9  test    rax, rax
0x140007cbc  jz      loc_140007FC8
0x140007cc2  lea     rcx, [rbp+arg_8]
0x140007cc6  mov     [rbp+arg_8], 0
0x140007cce  mov     qword ptr [rsp+80h+Priority], rcx
0x140007cd3  add     r8, 40h ; '@'
0x140007cd7  mov     ecx, [rdx+18h]
0x140007cda  mov     r9, rbx
0x140007cdd  mov     [rsp+80h+BugCheckOnFailure], ecx
0x140007ce1  mov     rdx, r12
0x140007ce4  mov     rcx, r13
0x140007ce7  call    _guard_dispatch_icall
0x140007cec  mov     ebx, eax
0x140007cee  test    eax, eax
0x140007cf0  jns     loc_140007F5A
0x140007cf6  cmp     ebx, 103h
0x140007cfc  jz      loc_140008179
0x140007d02  mov     [r13+18h], ebx
0x140007d06  test    ebx, ebx
0x140007d08  jns     loc_14000811F
0x140007d0e  mov     qword ptr [r13+20h], 0
0x140007d16  mov     r14d, 4
0x140007d1c  test    r12, r12
0x140007d1f  jnz     loc_1400081D2
0x140007d25  mov     rcx, [rbp+Context]; Context
0x140007d29  call    cs:__imp_FltReleaseContext
0x140007d30  nop     dword ptr [rax+rax+00h]
0x140007d35  mov     r12, [rsp+80h+arg_0]
0x140007d3d  jmp     loc_140007BCB
0x140007d42  mov     rcx, [rbp+Context]
0x140007d46  lea     rsi, cs:140000000h
0x140007d4d  xor     r8d, r8d
0x140007d50  lea     rdx, [rbp+var_18]
0x140007d54  mov     eax, [rcx+0Ch]
0x140007d57  add     rcx, 40h ; '@'
0x140007d5b  imul    rax, 1A8h
0x140007d62  mov     rax, [rax+rsi+1A280h]
0x140007d6a  call    _guard_dispatch_icall
0x140007d6f  test    eax, eax
0x140007d71  js      loc_140008184
0x140007d77  cmp     rbx, [rbp+var_18]
0x140007d7b  jge     loc_140008184
0x140007d81  mov     rcx, r13; CallbackData
0x140007d84  call    cs:__imp_FltLockUserBuffer
0x140007d8b  nop     dword ptr [rax+rax+00h]
0x140007d90  mov     r15d, eax
0x140007d93  test    eax, eax
0x140007d95  js      loc_140008010
0x140007d9b  mov     rcx, [r13+10h]
0x140007d9f  xor     r15d, r15d
0x140007da2  test    byte ptr [rcx+5], 2
0x140007da6  jnz     short loc_140007DFC
0x140007da8  mov     r10, [rcx+38h]
0x140007dac  test    r10, r10
0x140007daf  jz      loc_140008053
0x140007db5  test    byte ptr [r10+0Ah], 5
0x140007dba  jnz     loc_140007F1C
0x140007dc0  mov     [rsp+80h+Priority], 40000010h; Priority
0x140007dc8  xor     r9d, r9d; RequestedAddress
0x140007dcb  xor     edx, edx; AccessMode
0x140007dcd  mov     [rsp+80h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140007dd2  mov     r8d, 1; CacheType
0x140007dd8  mov     rcx, r10; MemoryDescriptorList
0x140007ddb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140007de2  nop     dword ptr [rax+rax+00h]
0x140007de7  mov     r15, rax
0x140007dea  test    r15, r15
0x140007ded  jnz     short loc_140007DFC
0x140007def  mov     dword ptr [r13+18h], 0C0000017h
0x140007df7  jmp     loc_140007D0E
0x140007dfc  lea     rax, WPP_RECORDER_INITIALIZED
0x140007e03  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007e0a  jnz     loc_14000805C
0x140007e10  test    r15, r15
0x140007e13  jz      loc_1400080CE
0x140007e19  mov     r9, [r13+10h]
0x140007e1d  mov     rcx, [rbp+var_18]
0x140007e21  mov     r8d, [r9+18h]
0x140007e25  cmp     r8, rcx
0x140007e28  jg      loc_140008115
0x140007e2e  mov     rax, rcx
0x140007e31  sub     rax, r8
0x140007e34  cmp     rbx, rax
0x140007e37  jg      loc_140008115
0x140007e3d  mov     rdx, [rbp+Context]
0x140007e41  mov     eax, [rdx+0Ch]
0x140007e44  add     rdx, 40h ; '@'
0x140007e48  imul    rcx, rax, 1A8h
0x140007e4f  mov     rax, [rcx+rsi+1A230h]
0x140007e57  lea     rcx, [rbp+var_10]
0x140007e5b  mov     [rsp+80h+var_30], rcx
0x140007e60  mov     rcx, [r9+38h]
0x140007e64  mov     r9, [rdi+18h]
0x140007e68  mov     [rsp+80h+var_38], rcx
0x140007e6d  mov     rcx, r13
0x140007e70  mov     [rsp+80h+var_40], r15
0x140007e75  mov     dword ptr [rsp+80h+var_48], r8d
0x140007e7a  mov     r8, r12
0x140007e7d  mov     [rsp+80h+var_50], rbx
0x140007e82  mov     byte ptr [rsp+80h+Priority], r14b
0x140007e87  mov     qword ptr [rsp+80h+BugCheckOnFailure], rdx
0x140007e8c  xor     edx, edx
0x140007e8e  call    _guard_dispatch_icall
0x140007e93  mov     ebx, eax
0x140007e95  test    eax, eax
0x140007e97  jns     loc_140007CF6
0x140007e9d  lea     rax, WPP_RECORDER_INITIALIZED
0x140007ea4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007eab  jz      short loc_140007EDB
0x140007ead  mov     rcx, cs:WPP_GLOBAL_Control
0x140007eb4  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x140007ebb  mov     r9d, 10h
0x140007ec1  mov     [rsp+80h+Priority], ebx
0x140007ec5  mov     r8d, 3
0x140007ecb  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140007ed0  mov     dl, 2
0x140007ed2  mov     rcx, [rcx+40h]
0x140007ed6  call    WPP_RECORDER_SF_d
0x140007edb  mov     [r13+18h], ebx
0x140007edf  jmp     loc_140007D0E
0x140007ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007eeb  mov     r9d, 0Ah
0x140007ef1  mov     rax, [rdi+20h]
0x140007ef5  mov     r8d, 3
0x140007efb  mov     qword ptr [rsp+80h+Priority], rax
0x140007f00  mov     dl, 4
0x140007f02  mov     qword ptr [rsp+80h+BugCheckOnFailure], rsi
0x140007f07  mov     rcx, [rcx+40h]
0x140007f0b  call    WPP_RECORDER_SF_q
0x140007f10  lea     rcx, WPP_RECORDER_INITIALIZED
0x140007f17  jmp     loc_140007C6B
0x140007f1c  mov     r15, [r10+18h]
0x140007f20  jmp     loc_140007DEA
0x140007f25  mov     [r13+18h], eax
0x140007f29  jmp     loc_140007D16
0x140007f2e  mov     rax, [rbp+RunRef]
0x140007f32  test    rax, rax
0x140007f35  jz      short loc_140007F43
0x140007f37  or      rax, 1
0x140007f3b  mov     [r15], rax
0x140007f3e  jmp     loc_140007D25
0x140007f43  mov     r14d, 1
0x140007f49  jmp     loc_140007D25
0x140007f4e  mov     rax, [rbp+Context]
0x140007f52  mov     ecx, [rax+8]
0x140007f55  jmp     loc_140007C38
0x140007f5a  mov     edx, 18h; NumberOfBytes
0x140007f5f  mov     ecx, 1; PoolType
0x140007f64  mov     r8d, 47666F57h; Tag
0x140007f6a  call    cs:__imp_ExAllocatePoolWithTag
0x140007f71  nop     dword ptr [rax+rax+00h]
0x140007f76  mov     rdx, rax
0x140007f79  test    rax, rax
0x140007f7c  jnz     short loc_140007FAA
0x140007f7e  mov     rax, [rbp+Context]
0x140007f82  mov     ecx, [rax+0Ch]
0x140007f85  imul    rax, rcx, 1A8h
0x140007f8c  mov     rcx, [rbp+arg_8]
0x140007f90  mov     rax, [rax+rsi+1A238h]
0x140007f98  call    _guard_dispatch_icall
0x140007f9d  mov     dword ptr [r13+18h], 0C000009Ah
0x140007fa5  jmp     loc_140007D0E
0x140007faa  mov     [rax], r12
0x140007fad  mov     rax, [rbp+Context]
0x140007fb1  mov     ecx, [rax+0Ch]
0x140007fb4  mov     [rdx+8], ecx
0x140007fb7  mov     rax, [rbp+arg_8]
0x140007fbb  mov     [rdx+10h], rax
0x140007fbf  or      rdx, 2
0x140007fc3  mov     [r15], rdx
0x140007fc6  jmp     short loc_140007FCF
0x140007fc8  mov     rax, [rbp+RunRef]
0x140007fcc  mov     [r15], rax
0x140007fcf  mov     r14d, 5
0x140007fd5  jmp     loc_140007D25
0x140007fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140007fe1  cmp     word ptr [rcx+48h], 0
0x140007fe6  jz      short loc_140008004
0x140007fe8  mov     rcx, [rcx+40h]
0x140007fec  mov     r9d, 0Bh
0x140007ff2  mov     r8d, 3
0x140007ff8  mov     qword ptr [rsp+80h+BugCheckOnFailure], rsi
0x140007ffd  mov     dl, 5
0x140007fff  call    WPP_RECORDER_SF_
0x140008004  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000800b  jmp     loc_140007C86
0x140008010  lea     rax, WPP_RECORDER_INITIALIZED
0x140008017  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000801e  jz      short loc_14000804A
0x140008020  mov     rcx, cs:WPP_GLOBAL_Control
0x140008027  lea     rax, WPP_bfe012b1c2333f2b0a3e712473f8d73f_Traceguids
0x14000802e  mov     r9d, 0Dh
0x140008034  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140008039  mov     r8d, 3
0x14000803f  mov     dl, 2
0x140008041  mov     rcx, [rcx+40h]
0x140008045  call    WPP_RECORDER_SF_
0x14000804a  mov     [r13+18h], r15d
0x14000804e  jmp     loc_140007D0E
0x140008053  mov     r15, [rcx+30h]
0x140008057  jmp     loc_140007DFC
0x14000805c  mov     rdx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
