# AfdDispatch

- ea: `0x140020500`
- end: `0x14002096a`
- name: `AfdDispatch`
- size: `1130`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14001ef30`
- `0x14001f018`
- `0x14001f120`
- `0x14001ffa4`
- `0x140020400`
- `0x140020500`
- `0x140020970`
- `0x1400218d4`
- `0x1400220d8`
- `0x140022214`
- `0x140022470`
- `0x140032db0`
- `0x140043904`
- `0x14004ffc0`
- `0x140072840`
- `0x140093008`
- `0x14009327c`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400205f4`
- `ntoskrnl!IofCompleteRequest` at `0x140020869`
- `ntoskrnl!IofCompleteRequest` at `0x1400208aa`
- `ntoskrnl!IofCompleteRequest` at `0x1400205f4`
- `ntoskrnl!IofCompleteRequest` at `0x140020869`
- `ntoskrnl!IofCompleteRequest` at `0x1400208aa`
- `ntoskrnl!IoGetCurrentProcess` at `0x140020939`
- `ntoskrnl!IoGetCurrentProcess` at `0x140020939`
- `ntoskrnl!EtwWrite` at `0x140020744`
- `ntoskrnl!EtwWrite` at `0x140020744`
- `NETIO!NetioNrtIsTrackerDevice` at `0x140020535`
- `NETIO!NetioNrtIsTrackerDevice` at `0x140020535`
- `NETIO!NetioNrtDispatch` at `0x140020835`
- `NETIO!NetioNrtDispatch` at `0x140020835`

## pseudocode

```c
__int64 __fastcall AfdDispatch(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 MajorFunction; // r9
  _WORD *v6; // rdi
  unsigned int Security; // eax
  __int64 v8; // rsi
  PVOID FsContext; // rdi
  unsigned int v10; // edi
  CCHAR v11; // dl
  __int64 result; // rax
  PFILE_OBJECT FileObject; // rax
  IRP *v14; // rcx
  __int64 v15; // rax
  PEPROCESS CurrentProcess; // rax
  PFILE_OBJECT v17; // rax
  __int64 v18; // rsi
  PVOID v19; // rdi
  __int64 v20; // rsi
  CCHAR v21; // dl
  int v22; // [rsp+30h] [rbp-69h] BYREF
  int v23; // [rsp+38h] [rbp-61h] BYREF
  int v24; // [rsp+40h] [rbp-59h] BYREF
  PEPROCESS v25; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR v26; // [rsp+50h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-39h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-19h] BYREF
  int *v30; // [rsp+90h] [rbp-9h]
  __int64 v31; // [rsp+98h] [rbp-1h]
  PEPROCESS *v32; // [rsp+A0h] [rbp+7h]
  __int64 v33; // [rsp+A8h] [rbp+Fh]
  EVENT_DESCRIPTOR *v34; // [rsp+B0h] [rbp+17h]
  __int64 v35; // [rsp+B8h] [rbp+1Fh]
  int *v36; // [rsp+C0h] [rbp+27h]
  __int64 v37; // [rsp+C8h] [rbp+2Fh]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( !(unsigned __int8)NetioNrtIsTrackerDevice(a1) )
  {
    MajorFunction = CurrentStackLocation->MajorFunction;
    if ( (_DWORD)MajorFunction == 18 )
    {
      v8 = 0;
      FsContext = CurrentStackLocation->FileObject->FsContext;
      if ( g_AfdEtwTraceEnable )
      {
        *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_CLEANUP;
        *(_WORD *)&EventDescriptor.Opcode = -5616;
        HIBYTE(EventDescriptor.Task) = 3;
        v15 = 0;
        if ( FsContext )
        {
          LOBYTE(v15) = *(_WORD *)FsContext != 0xAFD1;
          ++v15;
        }
        EventDescriptor.Level = 4;
        v24 = 0;
        EventDescriptor.Keyword = v15 | 0x8000000000000004uLL;
        *(_QWORD *)&v26.Id = FsContext;
        v23 = 2002;
        v22 = 0;
        v25 = 0;
        *(_QWORD *)ActivityId.Data4 = 0;
        *(_QWORD *)&ActivityId.Data1 = FsContext;
        if ( FsContext )
          CurrentProcess = (PEPROCESS)*((_QWORD *)FsContext + 6);
        else
          CurrentProcess = IoGetCurrentProcess();
        v25 = CurrentProcess;
        *(_QWORD *)&UserData.Size = 4;
        UserData.Ptr = (ULONGLONG)&v22;
        v31 = 4;
        v30 = &v23;
        v32 = &v25;
        v34 = &v26;
        v36 = &v24;
        v33 = 8;
        v35 = 8;
        v37 = 4;
        EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 5u, &UserData);
      }
      if ( (xmmword_1400875E0 & 4) != 0 )
      {
        if ( (*(_WORD *)FsContext & 0xAFD2) == 0xAFD2 )
          v8 = *((_QWORD *)FsContext + 24);
        WPP_SF_qqq(
          1026,
          10,
          WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids,
          CurrentStackLocation->FileObject,
          FsContext,
          v8,
          v22);
      }
      Security = AfdCleanupCore(CurrentStackLocation->FileObject, (__int16 *)FsContext);
LABEL_12:
      v10 = Security;
    }
    else
    {
      if ( CurrentStackLocation->MajorFunction )
      {
        switch ( CurrentStackLocation->MajorFunction )
        {
          case 2u:
            v6 = CurrentStackLocation->FileObject->FsContext;
            if ( g_AfdEtwTraceEnable )
            {
              v18 = 0;
              *(_DWORD *)&v26.Id = AFD_EVENT_CLOSE;
              *(_WORD *)&v26.Opcode = -5873;
              HIBYTE(v26.Task) = 3;
              *(_QWORD *)ActivityId.Data4 = 0;
              *(_QWORD *)&ActivityId.Data1 = v6;
              if ( v6 )
              {
                LOBYTE(v18) = *v6 != 0xAFD1;
                ++v18;
              }
              v26.Level = 4;
              v26.Keyword = v18 | 0x8000000000000004uLL;
              AFDETW_TRACESTATUS(&v26);
            }
            if ( (xmmword_1400875E0 & 4) != 0 )
              WPP_SF_qq(1026, 18, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids, CurrentStackLocation->FileObject, v6);
            Security = AfdCloseCore(v6);
            goto LABEL_12;
          case 3u:
            FileObject = CurrentStackLocation->FileObject;
            CurrentStackLocation->Parameters.Create.Options = 0;
            v14 = a2;
            if ( *(_WORD *)FileObject->FsContext == 6909 )
              goto LABEL_18;
            result = AfdReceive(a2);
            break;
          case 4u:
            v17 = CurrentStackLocation->FileObject;
            CurrentStackLocation->Parameters.Create.Options = 0;
            v14 = a2;
            if ( *(_WORD *)v17->FsContext == 6909 )
LABEL_18:
              result = AfdSanRedirectRequest(v14);
            else
              result = AfdSend(a2);
            break;
          case 0xEu:
            result = AfdDispatchDeviceControl(a1, a2);
            break;
          case 0xFu:
            result = AfdWskDispatchInternalDeviceControl(a1, a2);
            break;
          case 0x14u:
            Security = AfdGetSecurity(
                         (__int64)CurrentStackLocation->FileObject->FsContext,
                         CurrentStackLocation->Parameters.Read.Length,
                         CurrentStackLocation->Parameters.Create.Options,
                         a2->UserBuffer,
                         &a2->IoStatus.Information);
            goto LABEL_12;
          case 0x15u:
            Security = AfdSetSecurity(
                         (__int64)CurrentStackLocation->FileObject->FsContext,
                         CurrentStackLocation->Parameters.Read.Length,
                         CurrentStackLocation->Parameters.QueryDirectory.FileName);
            goto LABEL_12;
          case 0x1Bu:
            result = AfdPnpPower(a2);
            break;
          default:
            if ( (BYTE10(xmmword_1400875E0) & 0x20) != 0 )
              WPP_SF_d(1301, 10, WPP_750cd5b025b73ac1a6ce4c47647b8469_Traceguids, MajorFunction);
            v21 = AfdPriorityBoost;
            a2->IoStatus.Status = -1073741822;
            IofCompleteRequest(a2, v21);
            result = 3221225474LL;
            break;
        }
        return result;
      }
      v10 = AfdCreate(a2);
      if ( v10 == 259 )
        return v10;
    }
    v11 = AfdPriorityBoost;
    a2->IoStatus.Status = v10;
    IofCompleteRequest(a2, v11);
    return v10;
  }
  v19 = CurrentStackLocation->FileObject->FsContext;
  v20 = (unsigned int)NetioNrtDispatch(a1, a2);
  if ( CurrentStackLocation->FileObject->FsContext )
    v19 = CurrentStackLocation->FileObject->FsContext;
  AFDETW_NRT_TRACE(CurrentStackLocation->MajorFunction, v19, v20);
  a2->IoStatus.Status = v20;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140020500  mov     [rsp-8+arg_10], rbx
0x140020505  mov     [rsp-8+arg_18], rsi
0x14002050a  push    rbp
0x14002050b  push    rdi
0x14002050c  push    r14
0x14002050e  lea     rbp, [rsp-47h]
0x140020513  sub     rsp, 0E0h
0x14002051a  mov     rax, cs:__security_cookie
0x140020521  xor     rax, rsp
0x140020524  mov     [rbp+57h+var_20], rax
0x140020528  mov     r14, [rdx+0B8h]
0x14002052f  mov     rbx, rdx
0x140020532  mov     rsi, rcx
0x140020535  call    cs:__imp_NetioNrtIsTrackerDevice
0x14002053c  nop     dword ptr [rax+rax+00h]
0x140020541  test    al, al
0x140020543  jnz     loc_140020827
0x140020549  movzx   r9d, byte ptr [r14]
0x14002054d  cmp     r9d, 12h
0x140020551  jz      short loc_1400205B6
0x140020553  test    r9d, r9d
0x140020556  jz      loc_140020627
0x14002055c  lea     eax, [r9-2]; switch 26 cases
0x140020560  cmp     eax, 19h
0x140020563  ja      def_140020584; jumptable 0000000140020584 default case, cases 5-13,16-19,22-26
0x140020569  lea     rdx, cs:140000000h
0x140020570  cdqe
0x140020572  movzx   eax, ds:(byte_14007FD89 - 140000000h)[rdx+rax]
0x14002057a  mov     ecx, ds:(jpt_140020584 - 140000000h)[rdx+rax*4]
0x140020581  add     rcx, rdx
0x140020584  jmp     rcx; switch jump
0x14002058a  cmp     cs:g_AfdEtwTraceEnable, 0; jumptable 0000000140020584 case 2
0x140020591  mov     rax, [r14+30h]
0x140020595  mov     rdi, [rax+18h]
0x140020599  jnz     loc_1400207BB
0x14002059f  test    byte ptr cs:xmmword_1400875E0, 4
0x1400205a6  jnz     loc_1400208C0
0x1400205ac  mov     rcx, rdi
0x1400205af  call    AfdCloseCore
0x1400205b4  jmp     short loc_1400205E5
0x1400205b6  mov     rax, [r14+30h]
0x1400205ba  xor     esi, esi
0x1400205bc  cmp     cs:g_AfdEtwTraceEnable, esi
0x1400205c2  mov     rdi, [rax+18h]
0x1400205c6  jnz     loc_140020669
0x1400205cc  test    byte ptr cs:xmmword_1400875E0, 4
0x1400205d3  jnz     loc_14002094A
0x1400205d9  mov     rcx, [r14+30h]; Object
0x1400205dd  mov     rdx, rdi
0x1400205e0  call    AfdCleanupCore
0x1400205e5  mov     edi, eax
0x1400205e7  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x1400205ee  mov     rcx, rbx; Irp
0x1400205f1  mov     [rbx+30h], edi
0x1400205f4  call    cs:__imp_IofCompleteRequest
0x1400205fb  nop     dword ptr [rax+rax+00h]
0x140020600  mov     eax, edi
0x140020602  mov     rcx, [rbp+57h+var_20]
0x140020606  xor     rcx, rsp; StackCookie
0x140020609  call    __security_check_cookie
0x14002060e  lea     r11, [rsp+0F0h+var_10]
0x140020616  mov     rbx, [r11+30h]
0x14002061a  mov     rsi, [r11+38h]
0x14002061e  mov     rsp, r11
0x140020621  pop     r14
0x140020623  pop     rdi
0x140020624  pop     rbp
0x140020625  retn
0x140020627  mov     rdx, r14
0x14002062a  mov     rcx, rbx; Irp
0x14002062d  call    AfdCreate
0x140020632  mov     edi, eax
0x140020634  cmp     eax, 103h
0x140020639  jnz     short loc_1400205E7
0x14002063b  jmp     short loc_140020600
0x14002063d  mov     rax, [r14+30h]; jumptable 0000000140020584 case 3
0x140020641  xor     esi, esi
0x140020643  mov     [r14+10h], esi
0x140020647  mov     rdx, r14
0x14002064a  mov     rcx, [rax+18h]
0x14002064e  mov     eax, 1AFDh
0x140020653  cmp     [rcx], ax
0x140020656  mov     rcx, rbx; Irp
0x140020659  jnz     short loc_140020662
0x14002065b  call    AfdSanRedirectRequest
0x140020660  jmp     short loc_140020602
0x140020662  call    AfdReceive
0x140020667  jmp     short loc_140020602
0x140020669  mov     eax, cs:AFD_EVENT_CLEANUP
0x14002066f  mov     dword ptr [rbp+57h+EventDescriptor.Id], eax
0x140020672  movzx   eax, cs:word_14007DC2D
0x140020679  mov     word ptr [rbp+57h+EventDescriptor.Opcode], ax
0x14002067d  movzx   eax, cs:byte_14007DC2F
0x140020684  mov     byte ptr [rbp+57h+EventDescriptor.Task+1], al
0x140020687  mov     rax, rsi
0x14002068a  test    rdi, rdi
0x14002068d  jnz     loc_140020755
0x140020693  mov     rcx, 8000000000000004h
0x14002069d  mov     [rbp+57h+EventDescriptor.Level], 4
0x1400206a1  or      rax, rcx
0x1400206a4  mov     [rbp+57h+var_B0], esi
0x1400206a7  mov     [rbp+57h+EventDescriptor.Keyword], rax
0x1400206ab  mov     qword ptr [rbp+57h+var_A0.Id], rdi
0x1400206af  mov     [rbp+57h+var_B8], 7D2h
0x1400206b6  mov     [rbp+57h+var_C0], esi
0x1400206b9  mov     [rbp+57h+var_A8], rsi
0x1400206bd  mov     qword ptr [rbp+57h+ActivityId.Data4], rsi
0x1400206c1  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x1400206c5  test    rdi, rdi
0x1400206c8  jz      loc_140020939
0x1400206ce  mov     rax, [rdi+30h]
0x1400206d2  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x1400206d9  lea     r8, [rbp+57h+ActivityId]; ActivityId
0x1400206dd  mov     [rbp+57h+var_A8], rax
0x1400206e1  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400206e5  lea     rax, [rbp+57h+var_C0]
0x1400206e9  mov     qword ptr [rbp+57h+var_70.Size], 4
0x1400206f1  mov     [rbp+57h+var_70.Ptr], rax
0x1400206f5  mov     r9d, 5; UserDataCount
0x1400206fb  lea     rax, [rbp+57h+var_B8]
0x1400206ff  mov     [rbp+57h+var_58], 4
0x140020707  mov     [rbp+57h+var_60], rax
0x14002070b  lea     rax, [rbp+57h+var_A8]
0x14002070f  mov     [rbp+57h+var_50], rax
0x140020713  lea     rax, [rbp+57h+var_A0]
0x140020717  mov     [rbp+57h+var_40], rax
0x14002071b  lea     rax, [rbp+57h+var_B0]
0x14002071f  mov     [rbp+57h+var_30], rax
0x140020723  lea     rax, [rbp+57h+var_70]
0x140020727  mov     [rsp+0F0h+UserData], rax; UserData
0x14002072c  mov     [rbp+57h+var_48], 8
0x140020734  mov     [rbp+57h+var_38], 8
0x14002073c  mov     [rbp+57h+var_28], 4
0x140020744  call    cs:__imp_EtwWrite
0x14002074b  nop     dword ptr [rax+rax+00h]
0x140020750  jmp     loc_1400205CC
0x140020755  mov     ecx, 0AFD1h
0x14002075a  cmp     [rdi], cx
0x14002075d  setnz   al
0x140020760  inc     rax
0x140020763  jmp     loc_140020693
0x140020768  mov     rcx, [r14+30h]; jumptable 0000000140020584 case 20
0x14002076c  lea     rax, [rbx+38h]
0x140020770  mov     r9, [rbx+70h]
0x140020774  mov     r8d, [r14+10h]
0x140020778  mov     edx, [r14+8]
0x14002077c  mov     rcx, [rcx+18h]
0x140020780  mov     [rsp+0F0h+UserData], rax
0x140020785  call    AfdGetSecurity
0x14002078a  jmp     loc_1400205E5
0x14002078f  mov     rax, [r14+30h]; jumptable 0000000140020584 case 4
0x140020793  xor     esi, esi
0x140020795  mov     [r14+10h], esi
0x140020799  mov     rdx, r14
0x14002079c  mov     rcx, [rax+18h]
0x1400207a0  mov     eax, 1AFDh
0x1400207a5  cmp     [rcx], ax
0x1400207a8  mov     rcx, rbx; Irp
0x1400207ab  jz      loc_14002065B
0x1400207b1  call    AfdSend
0x1400207b6  jmp     loc_140020602
0x1400207bb  mov     eax, cs:AFD_EVENT_CLOSE
0x1400207c1  xor     esi, esi
0x1400207c3  mov     dword ptr [rbp+57h+var_A0.Id], eax
0x1400207c6  movzx   eax, cs:word_14007DBED
0x1400207cd  mov     word ptr [rbp+57h+var_A0.Opcode], ax
0x1400207d1  movzx   eax, cs:byte_14007DBEF
0x1400207d8  mov     byte ptr [rbp+57h+var_A0.Task+1], al
0x1400207db  mov     qword ptr [rbp+57h+ActivityId.Data4], rsi
0x1400207df  mov     qword ptr [rbp+57h+ActivityId.Data1], rdi
0x1400207e3  test    rdi, rdi
0x1400207e6  jnz     short loc_140020816
0x1400207e8  mov     rcx, 8000000000000004h
0x1400207f2  mov     [rbp+57h+var_A0.Level], 4
0x1400207f6  or      rsi, rcx
0x1400207f9  mov     r9, rdi
0x1400207fc  lea     rcx, [rbp+57h+var_A0]; EventDescriptor
0x140020800  mov     [rbp+57h+var_A0.Keyword], rsi
0x140020804  xor     edx, edx
0x140020806  mov     r8d, 7D0h
0x14002080c  call    AFDETW_TRACESTATUS
0x140020811  jmp     loc_14002059F
0x140020816  mov     ecx, 0AFD1h
0x14002081b  cmp     [rdi], cx
0x14002081e  setnz   sil
0x140020822  inc     rsi
0x140020825  jmp     short loc_1400207E8
0x140020827  mov     rax, [r14+30h]
0x14002082b  mov     rdx, rbx
0x14002082e  mov     rcx, rsi
0x140020831  mov     rdi, [rax+18h]
0x140020835  call    cs:__imp_NetioNrtDispatch
0x14002083c  nop     dword ptr [rax+rax+00h]
0x140020841  mov     r8, [r14+30h]
0x140020845  mov     esi, eax
0x140020847  movzx   ecx, byte ptr [r14]
0x14002084b  mov     r9, [r8+18h]
0x14002084f  mov     r8d, eax
0x140020852  test    r9, r9
0x140020855  cmovnz  rdi, r9
0x140020859  mov     rdx, rdi
0x14002085c  call    AFDETW_NRT_TRACE
0x140020861  xor     edx, edx; PriorityBoost
0x140020863  mov     [rbx+30h], esi
0x140020866  mov     rcx, rbx; Irp
0x140020869  call    cs:__imp_IofCompleteRequest
0x140020870  nop     dword ptr [rax+rax+00h]
0x140020875  mov     eax, esi
0x140020877  jmp     loc_140020602
0x14002087c  mov     rdx, rbx; jumptable 0000000140020584 case 14
0x14002087f  mov     rcx, rsi
0x140020882  call    AfdDispatchDeviceControl
0x140020887  jmp     loc_140020602
0x14002088c  test    byte ptr cs:xmmword_1400875E0+0Ah, 20h; jumptable 0000000140020584 default case, cases 5-13,16-19,22-26
0x140020893  jnz     loc_14002091E
0x140020899  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x1400208a0  mov     rcx, rbx; Irp
0x1400208a3  mov     dword ptr [rbx+30h], 0C0000002h
0x1400208aa  call    cs:__imp_IofCompleteRequest
0x1400208b1  nop     dword ptr [rax+rax+00h]
0x1400208b6  mov     eax, 0C0000002h
0x1400208bb  jmp     loc_140020602
0x1400208c0  mov     r9, [r14+30h]
0x1400208c4  lea     r8, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids
0x1400208cb  mov     edx, 12h
0x1400208d0  mov     [rsp+0F0h+UserData], rdi
0x1400208d5  mov     ecx, 402h
0x1400208da  call    WPP_SF_qq
0x1400208df  jmp     loc_1400205AC
0x1400208e4  mov     rdx, r14; jumptable 0000000140020584 case 27
0x1400208e7  mov     rcx, rbx; Irp
0x1400208ea  call    AfdPnpPower
0x1400208ef  jmp     loc_140020602
0x1400208f4  mov     rdx, rbx; jumptable 0000000140020584 case 15
0x1400208f7  mov     rcx, rsi
0x1400208fa  call    AfdWskDispatchInternalDeviceControl
0x1400208ff  jmp     loc_140020602
0x140020904  mov     rcx, [r14+30h]; jumptable 0000000140020584 case 21
0x140020908  mov     r8, [r14+10h]
0x14002090c  mov     edx, [r14+8]
0x140020910  mov     rcx, [rcx+18h]
0x140020914  call    AfdSetSecurity
0x140020919  jmp     loc_1400205E5
0x14002091e  mov     edx, 0Ah
0x140020923  lea     r8, WPP_750cd5b025b73ac1a6ce4c47647b8469_Traceguids
0x14002092a  mov     ecx, 515h
0x14002092f  call    WPP_SF_d
0x140020934  jmp     loc_140020899
0x140020939  call    cs:__imp_IoGetCurrentProcess
0x140020940  nop     dword ptr [rax+rax+00h]
0x140020945  jmp     loc_1400206D2
0x14002094a  movzx   eax, word ptr [rdi]
0x14002094d  mov     ecx, 0AFD2h
0x140020952  and     ax, cx
0x140020955  cmp     ax, cx
0x140020958  jnz     loc_140077AD8
0x14002095e  mov     rsi, [rdi+0C0h]
0x140020965  jmp     loc_140077AD8
0x140077ad8  mov     r9, [r14+30h]
0x140077adc  lea     r8, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids
0x140077ae3  mov     edx, 0Ah
0x140077ae8  mov     [rsp+0F0h+var_C8], rsi
0x140077aed  mov     ecx, 402h
0x140077af2  mov     [rsp+0F0h+UserData], rdi
0x140077af7  call    WPP_SF_qqq
0x140077afc  nop
0x140077afd  jmp     loc_1400205D9
```
