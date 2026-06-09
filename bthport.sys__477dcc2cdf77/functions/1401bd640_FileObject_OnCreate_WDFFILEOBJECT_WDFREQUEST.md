# FileObject::OnCreate(WDFFILEOBJECT__ *,WDFREQUEST__ *)

- ea: `0x1401bd640`
- end: `0x1401bd8d2`
- name: `?OnCreate@FileObject@@SAJPEAUWDFFILEOBJECT__@@PEAUWDFREQUEST__@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(struct WDFFILEOBJECT__ *, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1401bd8d8`

## callees

- `0x140004368`
- `0x140013820`
- `0x14002a2d4`
- `0x14002a504`
- `0x14002b9f4`
- `0x14002bf94`
- `0x14002bff8`
- `0x140165540`
- `0x140165580`
- `0x1401bd0d4`
- `0x1401bd210`
- `0x1401bd640`
- `0x140209650`
- `0x14020984c`

## import_xrefs

- `ntoskrnl!IoGetInitiatorProcess` at `0x1401bd6d0`
- `ntoskrnl!IoGetInitiatorProcess` at `0x1401bd6d0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401bd6e4`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401bd6e4`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bd719`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401bd719`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1401bd805`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1401bd805`

## pseudocode

```c
__int64 __fastcall FileObject::OnCreate(struct WDFFILEOBJECT__ *a1, struct WDFREQUEST__ *a2)
{
  struct WDFDEVICE__ *v4; // rax
  Fdo *v5; // r14
  char v6; // di
  __int64 v7; // rsi
  __int64 v8; // r13
  struct _KPROCESS *CurrentProcess; // rbx
  int ActivityIdIrp; // eax
  __int64 v11; // rdx
  LUID *v12; // r8
  int IsAppContainer; // ebx
  unsigned int RecorderLog; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  struct FileObject *v17; // rax
  unsigned int v18; // ebx
  KPROCESSOR_MODE v19; // dl
  struct FileObject *v20; // rax
  bool v22; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING *v23[3]; // [rsp+68h] [rbp-1h] BYREF
  LUID PrivilegeValue[2]; // [rsp+80h] [rbp+17h] BYREF

  v4 = (struct WDFDEVICE__ *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFFILEOBJECT__ *))(WdfFunctions_01031 + 1112))(
                               WdfDriverGlobals,
                               a1);
  v5 = Fdo::FromWdfDevice(v4);
  v6 = 1;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01031 + 2280))(
         WdfDriverGlobals,
         a2);
  v8 = *(_QWORD *)(v7 + 184);
  if ( *(_BYTE *)(v7 + 64) != 1
    || (CurrentProcess = (struct _KPROCESS *)IoGetInitiatorProcess(*(_QWORD *)(v8 + 48))) == 0 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  }
  FileObject::GetProcessCommandLine(v23, CurrentProcess, v5);
  if ( (unsigned int)Feature_53100197__private_IsEnabledDeviceUsageNoInline() )
  {
    *(_OWORD *)&PrivilegeValue[0].LowPart = 0;
    ActivityIdIrp = IoGetActivityIdIrp(v7, PrivilegeValue);
    v12 = PrivilegeValue;
    if ( ActivityIdIrp < 0 )
      v12 = 0;
    if ( (Microsoft_Windows_BTH_BTHPORTEnableBits & 2) != 0 )
      McTemplateK0p_EtwWriteTransfer(0, v11, v12, a1);
  }
  v22 = 0;
  if ( *(_BYTE *)(v7 + 64) != 1 )
    goto LABEL_18;
  IsAppContainer = QueryIsAppContainer(CurrentProcess, &v22);
  if ( IsAppContainer < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      v6 = 0;
    RecorderLog = (unsigned int)Fdo::GetRecorderLog(v5);
    v16 = *(_QWORD *)v5;
    LOBYTE(v16) = v6;
    WPP_RECORDER_AND_TRACE_SF_qdZ(*(_QWORD *)(v15 + 24), v16, v15, RecorderLog);
    v17 = FileObject::FromWdfFileObject(a1);
    if ( v17 )
    {
      PrivilegeValue[0] = (LUID)v23[0];
      v23[0] = 0;
      FileObject::FileObject(v17, v5, 0, PrivilegeValue);
    }
    goto LABEL_33;
  }
  if ( !v22 )
  {
LABEL_18:
    v19 = 1;
    PrivilegeValue[0] = (LUID)10LL;
    if ( (*(_BYTE *)(v8 + 2) & 1) == 0 )
      v19 = *(_BYTE *)(v7 + 64);
    if ( SeSinglePrivilegeCheck(PrivilegeValue[0], v19) )
    {
      v18 = 2;
    }
    else
    {
      v18 = 0;
      if ( *(_BYTE *)(v7 + 64) != 1 )
        goto LABEL_30;
      if ( IsCallingProcess(`IsCallingProcessUserModeDriverHost'::`2'::s_sdUserModeDriverHost, 1) )
        v18 = 2;
    }
    if ( *(_BYTE *)(v7 + 64) == 1 )
    {
      if ( IsCallingProcess(`IsCallingProcessBthservEx'::`2'::s_sdBthserv, 1) )
        v18 |= 4u;
      if ( IsCallingProcess(`IsCallingProcessBluetoothAudioService'::`2'::s_sdBthAvctpSvc, 1) )
        v18 |= 8u;
    }
    goto LABEL_30;
  }
  v18 = 1;
LABEL_30:
  v20 = FileObject::FromWdfFileObject(a1);
  if ( v20 )
  {
    PrivilegeValue[0] = (LUID)v23[0];
    v23[0] = 0;
    FileObject::FileObject(v20, v5, v18, PrivilegeValue);
  }
  IsAppContainer = 0;
LABEL_33:
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(v23);
  return (unsigned int)IsAppContainer;
}

```

## disassembly

```asm
0x1401bd640  mov     [rsp-8+arg_10], rbx
0x1401bd645  mov     [rsp-8+arg_18], rsi
0x1401bd64a  push    rbp
0x1401bd64b  push    rdi
0x1401bd64c  push    r13
0x1401bd64e  push    r14
0x1401bd650  push    r15
0x1401bd652  lea     rbp, [rsp-37h]
0x1401bd657  sub     rsp, 0A0h
0x1401bd65e  mov     rax, cs:__security_cookie
0x1401bd665  xor     rax, rsp
0x1401bd668  mov     [rbp+57h+var_30], rax
0x1401bd66c  mov     rax, cs:WdfFunctions_01031
0x1401bd673  mov     rbx, rdx
0x1401bd676  mov     r15, rcx
0x1401bd679  mov     rdx, rcx
0x1401bd67c  mov     rcx, cs:WdfDriverGlobals
0x1401bd683  mov     rax, [rax+458h]
0x1401bd68a  call    _guard_dispatch_icall
0x1401bd68f  mov     rcx, rax; struct WDFDEVICE__ *
0x1401bd692  call    ?FromWdfDevice@Fdo@@SAAEAV1@PEAUWDFDEVICE__@@@Z; Fdo::FromWdfDevice(WDFDEVICE__ *)
0x1401bd697  mov     rcx, cs:WdfFunctions_01031
0x1401bd69e  mov     r14, rax
0x1401bd6a1  mov     rdx, rbx
0x1401bd6a4  mov     rax, [rcx+8E8h]
0x1401bd6ab  mov     rcx, cs:WdfDriverGlobals
0x1401bd6b2  call    _guard_dispatch_icall
0x1401bd6b7  mov     edi, 1
0x1401bd6bc  mov     rsi, rax
0x1401bd6bf  mov     r13, [rax+0B8h]
0x1401bd6c6  cmp     [rax+40h], dil
0x1401bd6ca  jnz     short loc_1401BD6E4
0x1401bd6cc  mov     rcx, [r13+30h]
0x1401bd6d0  call    cs:__imp_IoGetInitiatorProcess
0x1401bd6d7  nop     dword ptr [rax+rax+00h]
0x1401bd6dc  mov     rbx, rax
0x1401bd6df  test    rax, rax
0x1401bd6e2  jnz     short loc_1401BD6F3
0x1401bd6e4  call    cs:__imp_PsGetCurrentProcess
0x1401bd6eb  nop     dword ptr [rax+rax+00h]
0x1401bd6f0  mov     rbx, rax
0x1401bd6f3  mov     r8, r14
0x1401bd6f6  lea     rcx, [rbp+57h+var_58]
0x1401bd6fa  mov     rdx, rbx
0x1401bd6fd  call    ?GetProcessCommandLine@FileObject@@CA?AV?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@PEAU_EPROCESS@@AEBVFdo@@@Z; FileObject::GetProcessCommandLine(_EPROCESS *,Fdo const &)
0x1401bd702  call    Feature_53100197__private_IsEnabledDeviceUsageNoInline
0x1401bd707  test    eax, eax
0x1401bd709  jz      short loc_1401BD742
0x1401bd70b  xorps   xmm0, xmm0
0x1401bd70e  lea     rdx, [rbp+57h+PrivilegeValue]
0x1401bd712  mov     rcx, rsi
0x1401bd715  movups  xmmword ptr [rbp+57h+PrivilegeValue.LowPart], xmm0
0x1401bd719  call    cs:__imp_IoGetActivityIdIrp
0x1401bd720  nop     dword ptr [rax+rax+00h]
0x1401bd725  xor     ecx, ecx
0x1401bd727  lea     r8, [rbp+57h+PrivilegeValue]
0x1401bd72b  test    eax, eax
0x1401bd72d  cmovs   r8, rcx
0x1401bd731  test    cs:Microsoft_Windows_BTH_BTHPORTEnableBits, 2
0x1401bd738  jz      short loc_1401BD742
0x1401bd73a  mov     r9, r15
0x1401bd73d  call    McTemplateK0p_EtwWriteTransfer
0x1401bd742  mov     [rbp+57h+var_60], 0
0x1401bd746  cmp     [rsi+40h], dil
0x1401bd74a  jnz     loc_1401BD7ED
0x1401bd750  lea     rdx, [rbp+57h+var_60]
0x1401bd754  mov     rcx, rbx
0x1401bd757  call    QueryIsAppContainer
0x1401bd75c  mov     ebx, eax
0x1401bd75e  test    eax, eax
0x1401bd760  jns     short loc_1401BD7E0
0x1401bd762  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401bd769  mov     ecx, [r8+2Ch]
0x1401bd76d  test    dil, cl
0x1401bd770  jz      short loc_1401BD779
0x1401bd772  cmp     byte ptr [r8+29h], 2
0x1401bd777  jnb     short loc_1401BD77C
0x1401bd779  xor     dil, dil
0x1401bd77c  mov     rcx, r14; this
0x1401bd77f  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1401bd784  mov     rdx, [rbp+57h+var_58]
0x1401bd788  mov     r9, rax
0x1401bd78b  mov     rcx, [r8+18h]
0x1401bd78f  mov     [rsp+0C0h+var_70], rdx
0x1401bd794  mov     rdx, [r14]
0x1401bd797  mov     [rsp+0C0h+var_78], ebx
0x1401bd79b  mov     [rsp+0C0h+var_80], rdx
0x1401bd7a0  mov     dl, dil
0x1401bd7a3  call    WPP_RECORDER_AND_TRACE_SF_qdZ
0x1401bd7a8  mov     rcx, r15; struct WDFFILEOBJECT__ *
0x1401bd7ab  call    ?FromWdfFileObject@FileObject@@SAAEAV1@PEAUWDFFILEOBJECT__@@@Z; FileObject::FromWdfFileObject(WDFFILEOBJECT__ *)
0x1401bd7b0  test    rax, rax
0x1401bd7b3  jz      loc_1401BD89E
0x1401bd7b9  mov     rcx, [rbp+57h+var_58]
0x1401bd7bd  lea     r9, [rbp+57h+PrivilegeValue]
0x1401bd7c1  mov     qword ptr [rbp+57h+PrivilegeValue.LowPart], rcx
0x1401bd7c5  xor     r8d, r8d
0x1401bd7c8  mov     rcx, rax
0x1401bd7cb  mov     [rbp+57h+var_58], 0
0x1401bd7d3  mov     rdx, r14
0x1401bd7d6  call    ??0FileObject@@AEAA@AEAVFdo@@W4CallerIdentityFlags@@V?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@@Z; FileObject::FileObject(Fdo &,CallerIdentityFlags,utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>>)
0x1401bd7db  jmp     loc_1401BD89E
0x1401bd7e0  cmp     [rbp+57h+var_60], 0
0x1401bd7e4  jz      short loc_1401BD7ED
0x1401bd7e6  mov     ebx, edi
0x1401bd7e8  jmp     loc_1401BD86D
0x1401bd7ed  mov     dl, dil
0x1401bd7f0  mov     qword ptr [rbp+57h+PrivilegeValue.LowPart], 0Ah
0x1401bd7f8  test    [r13+2], dil
0x1401bd7fc  jnz     short loc_1401BD801
0x1401bd7fe  mov     dl, [rsi+40h]; PreviousMode
0x1401bd801  mov     rcx, qword ptr [rbp+57h+PrivilegeValue.LowPart]; PrivilegeValue
0x1401bd805  call    cs:__imp_SeSinglePrivilegeCheck
0x1401bd80c  nop     dword ptr [rax+rax+00h]
0x1401bd811  test    al, al
0x1401bd813  jz      short loc_1401BD81C
0x1401bd815  mov     ebx, 2
0x1401bd81a  jmp     short loc_1401BD83B
0x1401bd81c  xor     ebx, ebx
0x1401bd81e  cmp     [rsi+40h], dil
0x1401bd822  jnz     short loc_1401BD86D
0x1401bd824  mov     dl, dil
0x1401bd827  lea     rcx, ?s_sdUserModeDriverHost@?1??IsCallingProcessUserModeDriverHost@@9@4QBKB; SecurityDescriptor
0x1401bd82e  call    IsCallingProcess
0x1401bd833  test    al, al
0x1401bd835  lea     eax, [rbx+2]
0x1401bd838  cmovnz  ebx, eax
0x1401bd83b  cmp     [rsi+40h], dil
0x1401bd83f  jnz     short loc_1401BD86D
0x1401bd841  mov     dl, dil
0x1401bd844  lea     rcx, ?s_sdBthserv@?1??IsCallingProcessBthservEx@@9@4QBKB; SecurityDescriptor
0x1401bd84b  call    IsCallingProcess
0x1401bd850  test    al, al
0x1401bd852  jz      short loc_1401BD857
0x1401bd854  or      ebx, 4
0x1401bd857  mov     dl, dil
0x1401bd85a  lea     rcx, ?s_sdBthAvctpSvc@?1??IsCallingProcessBluetoothAudioService@@9@4QBKB; SecurityDescriptor
0x1401bd861  call    IsCallingProcess
0x1401bd866  test    al, al
0x1401bd868  jz      short loc_1401BD86D
0x1401bd86a  or      ebx, 8
0x1401bd86d  mov     rcx, r15; struct WDFFILEOBJECT__ *
0x1401bd870  call    ?FromWdfFileObject@FileObject@@SAAEAV1@PEAUWDFFILEOBJECT__@@@Z; FileObject::FromWdfFileObject(WDFFILEOBJECT__ *)
0x1401bd875  test    rax, rax
0x1401bd878  jz      short loc_1401BD89C
0x1401bd87a  mov     rcx, [rbp+57h+var_58]
0x1401bd87e  lea     r9, [rbp+57h+PrivilegeValue]
0x1401bd882  mov     qword ptr [rbp+57h+PrivilegeValue.LowPart], rcx
0x1401bd886  mov     r8d, ebx
0x1401bd889  mov     rcx, rax
0x1401bd88c  mov     [rbp+57h+var_58], 0
0x1401bd894  mov     rdx, r14
0x1401bd897  call    ??0FileObject@@AEAA@AEAVFdo@@W4CallerIdentityFlags@@V?$unique_ptr@U_UNICODE_STRING@@U?$default_delete@U_UNICODE_STRING@@@utl@@@utl@@@Z; FileObject::FileObject(Fdo &,CallerIdentityFlags,utl::unique_ptr<_UNICODE_STRING,utl::default_delete<_UNICODE_STRING>>)
0x1401bd89c  xor     ebx, ebx
0x1401bd89e  lea     rcx, [rbp+57h+var_58]
0x1401bd8a2  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x1401bd8a7  mov     eax, ebx
0x1401bd8a9  mov     rcx, [rbp+57h+var_30]
0x1401bd8ad  xor     rcx, rsp; StackCookie
0x1401bd8b0  call    __security_check_cookie
0x1401bd8b5  lea     r11, [rsp+0C0h+var_20]
0x1401bd8bd  mov     rbx, [r11+40h]
0x1401bd8c1  mov     rsi, [r11+48h]
0x1401bd8c5  mov     rsp, r11
0x1401bd8c8  pop     r15
0x1401bd8ca  pop     r14
0x1401bd8cc  pop     r13
0x1401bd8ce  pop     rdi
0x1401bd8cf  pop     rbp
0x1401bd8d0  retn
```
